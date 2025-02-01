# Production Deployment Guide

## Steps to Deploy the Source Code in Production

### 1. Clone the Source Code

```bash
git clone https://github.com/dacn-tannat/cse-lbds-server.git
```

### 2. Organize the Directory Structure

Ensure the directory structure is as follows:

```
.
└── production/
    ├── client/         # May need to rename from cse-lbds-client
    ├── server/         # May need to rename from cse-lbds-server
    │   └── Dockerfile
    ├── nginx/
    │   ├── Dockerfile
    │   └── default.conf
    ├── docker-compose.yml
    ├── init-letsencrypt.sh
    └── README.md
```

### 3. Navigate to the Production Directory

```bash
cd production
```

### 4. Generate SSL Certificates (First-Time Setup Only)

```bash
chmod +x init-letsencrypt.sh
bash init-letsencrypt.sh
```

If successful, a `certbot/` directory will be created within `production/`.

### 5. Start the System

```bash
docker-compose -p cse-lbds up -d
```

This will start the entire system using `docker-compose.yml`.

### Notes

Happy Deploying! 🚀
