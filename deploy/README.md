# Dittofeed - Deploy to Hetzner VPS

## Quick Start

### 1. Prepare your VPS
```bash
ssh root@77.42.40.0 'bash -s' < setup.sh
```

### 2. Configure
```bash
cp .env.example .env
# Edit .env with secure passwords
```

### 3. Deploy
```bash
chmod +x deploy.sh
./deploy.sh 77.42.40.0 root
```

### 4. Configure DNS
In Hostinger/Namecheap, add an **A record**:
- **Host**: `ditto`
- **Type**: `A`
- **Value**: `77.42.40.0`
- **TTL**: Auto

### 5. Access
Open https://ditto.axeljutoran.com (SSL is automatic via Caddy)

## CI/CD (GitHub Actions)

Add these secrets to your GitHub repo (Settings > Secrets):
- `VPS_HOST`: `77.42.40.0`
- `VPS_USER`: `root`
- `VPS_SSH_KEY`: Your private SSH key

Then any push to `main` that changes `deploy/` will auto-deploy.
