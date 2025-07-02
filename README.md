# Homelab

![Homepage](assets/homepage.png)

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
* **Byakko**: Proxmox (Primary Hypervisor)
* **Tiamat**: Proxmox (Secondary Hypervisor)
* **Shiva**: NAS (49.1TB Raw / 38.5TB Usable)
* **Odin**: Remote Backup Target
  
## Services

* [ArchiveTeam-Warrior](https://github.com/vfedetz/homelab/blob/main/docker-compose/archiveteam-warrior/docker-compose.yml): Virtual appliance to help with the ArchiveTeam archiving efforts.
* [Homepage](https://github.com/vfedetz/homelab/blob/main/docker-compose/homepage/docker-compose.yml): Custom homepage for homelab services
* [Joplin](https://github.com/vfedetz/homelab/blob/main/docker-compose/joplin/docker-compose.yml): Open source note-taking app
* [Ollama](https://github.com/vfedetz/homelab/blob/main/docker-compose/ollama/docker-compose.yml): Local AI LLM + Web UI
* [SearXNG](https://github.com/vfedetz/homelab/blob/main/docker-compose/searxng/docker-compose.yml): Metasearch engine + VPN proxy
  
## Configuration
Each service directory contains a docker-compose.yml file which can be customized to fit your needs. Common configurations include:

* Ports
* Environment variables
* Volumes

Modify these settings according to your specific requirements before starting the services.

## License 
This project is licensed under the MIT License. See the [LICENSE](https://github.com/vfedetz/homelab/blob/main/LICENSE) file for details.

## Contact
For questions, suggestions, or feedback, please open an issue on GitHub or contact me at github@kan.ninja.
