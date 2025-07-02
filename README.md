# 🏠 Homelab

![Homepage](assets/homepage.png)


The purpose of my homelab is to learn and to have fun - where I can try out and experiment with technology.

This repository serves as a collection of Docker/container configurations, utilities, and automation scripts used to manage and orchestrate various services within my homelab environment. Each service has its own directory containing a docker-compose.yml file and any necessary supporting files (e.g., environment variables).

Feel free to explore, use, and modify these files to suit your own homelab needs!

## Table of Contents
1. [Introduction](#introduction)
2. [Project Structure](#project-structure)
3. [Hardware Stack](#hardware-stack)
4. [Services](#services)
5. [Configuration](#configuration)
6. [License](#license)
7. [Contact](#contact)

## Introduction
This repository aims to simplify the setup and management of containerized services in a homelab environment using Docker-Compose. Each service is defined in a separate Docker-Compose file, making it easy to start, stop, and configure as needed.

## Project Structure
```
homelab/
│
├─ docker-compose/
│  ├─ <service-name>/
│  │  ├─ docker-compose.yml
│  │  └─ ...
│  └─ ...
│
├─ README.md
└─ ...
```
## Hardware Stack

* **"Kirin"**: Topton N100 Mini PC running OPNsense (Router/Firewall/DHCP/DNS)
* **"Byakko"**: Minisforum MS-01 running Proxmox (Primary Hypervisor)
* **"Tiamat"**: Beelink S12 Pro running Proxmox (Secondary Hypervisor)
* **"Shiva"**: Synology DS1019+ (NAS)
* **"Odin"**: Raspberry Pi 4B (Offsite Backup Target)
  
## Services

* [ArchiveTeam-Warrior](https://github.com/vfedetz/homelab/blob/main/docker-compose/archiveteam-warrior/docker-compose.yml): Virtual appliance to help with the ArchiveTeam archiving efforts.
* [Frigate](https://github.com/vfedetz/homelab/blob/main/docker-compose/frigate/docker-compose.yml): Local NVR with AI object detection + Notifications
* [Homepage](https://github.com/vfedetz/homelab/blob/main/docker-compose/homepage/docker-compose.yml): Custom homepage for homelab services
* [Immich](https://github.com/vfedetz/homelab/blob/main/docker-compose/immich/docker-compose.yml): Photo backup and management
* [Joplin](https://github.com/vfedetz/homelab/blob/main/docker-compose/joplin/docker-compose.yml): Syncronized note-taking app
* [Ollama](https://github.com/vfedetz/homelab/blob/main/docker-compose/ollama/docker-compose.yml): Local AI LLM + Web UI
* [SearXNG](https://github.com/vfedetz/homelab/blob/main/docker-compose/searxng/docker-compose.yml): Metasearch engine + VPN proxy
* [Vaultwarden](https://github.com/vfedetz/homelab/blob/main/docker-compose/vaultwarden/docker-compose.yml): Syncronized password vault compatible with Bitwarden
  
## Configuration
Each service directory contains a docker-compose.yml file and (if required) a .env.example file which can be customized to fit your needs. Common env configurations include:

* Ports
* IPs
* Hostnames
* Domains
* Usernames/Passwords

Modify these settings according to your specific requirements before starting the services.

## License 
This project is licensed under the MIT License. See the [LICENSE](https://github.com/vfedetz/homelab/blob/main/LICENSE) file for details.

## Contact
For questions, suggestions, or feedback, please open an issue on GitHub or contact me at github@kan.ninja.
