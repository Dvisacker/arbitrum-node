# Arbitrum Node Setup

This repository contains the configuration files to run an Arbitrum node using Docker Compose.

## Requirements

- Docker
- Docker Compose
- RPC urls for Ethereum Mainnet and Beacon Chain

## Setup Instructions

1. Clone this repository (or download the files):
   ```
   git clone <repository-url>
   cd <repository-directory>
   ```

2. Create a `.env` file in the root directory of the project:
   ```
   cp .env.example .env
   ```

3. Edit the `.env` file and replace the placeholder values with your actual URLs:
   ```
   PARENT_CHAIN_URL=<your-ethereum-mainnet-url>
   BEACON_URL=<your-ethereum-beacon-chain-url>
   ```

4. Give enough resources to docker (Docker Desktop -> Settings -> Resources). In particular ~1TB of disk space is recommended.

## Running the Node

To start the Arbitrum node:

```
docker-compose up -d
```

This will start the node in detached mode. You can view the logs with:

```
docker-compose logs -f
```

## Stopping the Node

To stop the Arbitrum node:

```
docker-compose down
```

## Additional Information

- The bulk of the data is stored in the docker data directory (on MacOS, this is `~/Library/Containers/com.docker.docker/Data/vms/0/data/`).
- The node exposes RPC on ports 8547 and 8548.