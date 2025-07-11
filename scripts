#!/bin/bash
##############################################
# file: backup_docker.sh
# desc: backup docker container mounted volumes to remote nas
##############################################

# Load the .env file
source backup_docker.env

# Function to log messages
log() {
    echo "$(date '+%Y-%m-%d %H:%M:%S') - $1" >> "$LOGFILE"
}

# Get the hostname of the machine
HOSTNAME=$(hostname)

##############################################
# Step 1: Stop all running Docker containers 
log "Stopping all running Docker containers..."
RUNNING_CONTAINERS=$(docker ps -q)
GLUETUN_CONTAINERS=$(docker ps -q --filter "name=gluetun")
if [ -z "$RUNNING_CONTAINERS" ]; then
    log "No running containers found."
else
    # Stop all containers
    for CONTAINER in $RUNNING_CONTAINERS; do
        CONTAINER_NAME=$(docker inspect --format '{{.Name}}' $CONTAINER | sed 's|/||')
        docker stop $CONTAINER >> "$LOGFILE" 2>&1
        log "Stopped container: $CONTAINER_NAME"
    done
fi
##############################################
# Step 2: Run the rsync command with the hostname in the target path
log "Starting rsync backup..."
rsync -avx --delete $RSYNC_SOURCE_DIR/ $RSYNC_USER@$RSYNC_DEST_HOST:$RSYNC_DEST_DIR/$HOSTNAME >> "$LOGFILE" 2>&1
if [ $? -eq 0 ]; then
    log "rsync completed successfully."
else
    log "rsync failed with exit code $?."
fi

##############################################
# Step 3: Restart the stopped Docker containers
log "Restarting previously stopped Docker containers..."

# Start any container with gluetun in its name (if it was not already running)
if [ -z "$GLUETUN_CONTAINERS" ]; then
    log "No gluetun contianers found"
else
    # Start all gluetun containers
    for CONTAINER in $GLUETUN_CONTAINERS; do
        CONTAINER_NAME=$(docker inspect --format '{{.Name}}' $CONTAINER | sed 's|/||')
        log "Starting $CONTAINER_NAME container..."
        docker start $CONTAINER_NAME >> "$LOGFILE" 2>&1
        log "Waiting for $CONTAINER_NAME container to initialize..."
        sleep 5  # Adjust the sleep time as needed for gluetun to fully initialize
	log "Stopped container: $CONTAINER_NAME"
    done
fi

# Start all other containers
if [ -z "$RUNNING_CONTAINERS" ]; then
    log "No containers to restart."
else
    for CONTAINER in $RUNNING_CONTAINERS; do
        CONTAINER_NAME=$(docker inspect --format '{{.Name}}' $CONTAINER | sed 's|/||')
        if echo "$CONTAINER_NAME" | grep -v -q "gluetun"; then # skip gluetun containers
            docker start $CONTAINER >> "$LOGFILE" 2>&1
            log "Restarted container: $CONTAINER_NAME"
        fi
    done
fi

log "Backup process completed."
