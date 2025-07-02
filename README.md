# Homelab Repository

![Homelab Banner](https://via.placeholder.com/1920x300?text=Homelab+Repository)

This repository serves as a collection of Docker/container configurations, utilities, and automation scripts used to manage and orchestrate various services within my homelab environment. Each service has its own directory containing a docker-compose.yml file and any necessary supporting files (e.g., environment variables). Feel free to explore, use, and modify these files to suit your own homelab needs. Contributions and suggestions are welcome!

## Table of Contents
1. [Introduction](#introduction)
2. [Project Struction](#project-structure)
4. [Services](#services)
7. [License](#license)
8. [Contact](#contact)

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

## Services

* [ArchiveTeam-Warrior](https://github.com/vfedetz/homelab/blob/main/docker-compose/archiveteam-warrior/docker-compose.yml): Virtual appliance to help with the ArchiveTeam archiving efforts.
* [Homepage](https://github.com/vfedetz/homelab/blob/main/docker-compose/homepage/docker-compose.yml): Custom homepage for homelab services
* [Ollama](https://github.com/vfedetz/homelab/blob/main/docker-compose/ollama/docker-compose.yml): Local AI LLM + Web UI
* [SearXNG](https://github.com/vfedetz/homelab/blob/main/docker-compose/searxng/docker-compose.yml): Metasearch engine + VPN proxy
  
## License 
This project is licensed under the MIT License. Feel free to use, modify, and distribute the code as needed. Please see the license file for more details.

## Contact
For questions, suggestions, or feedback, please open an issue on GitHub or contact me at github@kan.ninja.
