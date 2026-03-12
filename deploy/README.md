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

### 4. Access
Open http://77.42.40.0:3000

## CI/CD (GitHub Actions)

Add these secrets to your GitHub repo (Settings > Secrets):
- `VPS_HOST`: `77.42.40.0`
- `VPS_USER`: `root`
- `VPS_SSH_KEY`: Your private SSH key

Then any push to `main` that changes `deploy/` will auto-deploy.

## Add a Domain Later

1. Buy a domain (Namecheap, Cloudflare, etc.)
2. Point DNS A record to `77.42.40.0`
3. Install Caddy or Nginx as reverse proxy with SSL
