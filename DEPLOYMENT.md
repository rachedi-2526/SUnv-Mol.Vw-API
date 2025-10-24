# SUnv-Mol.Vw API - Academic Server Deployment Guide

## 🏛️ Academic Institution Deployment

This guide provides step-by-step instructions for deploying the SUnv-Mol.Vw API on academic Ubuntu servers.

## 📋 Prerequisites

- Ubuntu 20.04 LTS or later
- Root/sudo access
- Domain name or static IP address
- Basic knowledge of Linux command line

## 🚀 Quick Deployment

### 1. Server Preparation

```bash
# Update system
sudo apt update && sudo apt upgrade -y

# Install required packages
sudo apt install -y git nginx apache2-utils certbot python3-certbot-nginx
```

### 2. Clone Repository

```bash
# Create project directory
sudo mkdir -p /var/www/sunv-mol-api
sudo chown -R www-data:www-data /var/www/sunv-mol-api

# Clone repository
cd /var/www/sunv-mol-api
sudo git clone https://github.com/rachedi-2526/SUnv-Mol.Vw-API.git .
```

### 3. Configure Web Server

#### Nginx Configuration

```bash
sudo nano /etc/nginx/sites-available/sunv-mol-api
```

```nginx
server {
    listen 80;
    server_name your-domain.edu.dz;  # Replace with your domain
    
    root /var/www/sunv-mol-api;
    index SUnv-Mol_Vw_api.html demo.html;
    
    # Enable gzip compression
    gzip on;
    gzip_types text/html text/css application/javascript application/json;
    
    # Security headers
    add_header X-Frame-Options "SAMEORIGIN" always;
    add_header X-Content-Type-Options "nosniff" always;
    add_header X-XSS-Protection "1; mode=block" always;
    
    location / {
        try_files $uri $uri/ =404;
    }
    
    # Cache static files
    location ~* \.(css|js|png|jpg|jpeg|gif|ico|svg)$ {
        expires 1y;
        add_header Cache-Control "public, immutable";
    }
}
```

### 4. Enable Site and SSL

```bash
# Enable site
sudo ln -s /etc/nginx/sites-available/sunv-mol-api /etc/nginx/sites-enabled/

# Test configuration
sudo nginx -t

# Restart Nginx
sudo systemctl restart nginx

# Install SSL certificate
sudo certbot --nginx -d your-domain.edu.dz
```

## 🔧 Academic-Specific Configuration

### Research Integration

```bash
# Create research data directory
sudo mkdir -p /var/www/sunv-mol-api/research-data
sudo chown -R www-data:www-data /var/www/sunv-mol-api/research-data

# Set up log rotation for research usage tracking
sudo nano /etc/logrotate.d/sunv-mol-api
```

### Performance Monitoring

```bash
# Install monitoring tools
sudo apt install htop iotop nethogs

# Set up usage analytics (optional)
sudo apt install awstats
```

### Backup Strategy

```bash
# Create backup script
sudo nano /usr/local/bin/backup-sunv-mol-api.sh
```

```bash
#!/bin/bash
DATE=$(date +%Y%m%d_%H%M%S)
BACKUP_DIR="/backup/sunv-mol-api"
SOURCE_DIR="/var/www/sunv-mol-api"

mkdir -p $BACKUP_DIR
tar -czf $BACKUP_DIR/sunv-mol-api-$DATE.tar.gz $SOURCE_DIR

# Keep only last 7 days of backups
find $BACKUP_DIR -name "sunv-mol-api-*.tar.gz" -mtime +7 -delete
```

```bash
# Make executable and schedule
sudo chmod +x /usr/local/bin/backup-sunv-mol-api.sh
sudo crontab -e
# Add: 0 2 * * * /usr/local/bin/backup-sunv-mol-api.sh
```

## 📊 Usage Analytics

### Track Research Usage

```bash
# Install GoAccess for real-time analytics
sudo apt install goaccess

# Configure GoAccess
sudo nano /etc/goaccess/goaccess.conf
```

### Academic Metrics

The API automatically logs:
- Structure access patterns
- Research institution usage
- Popular protein structures
- Geographic distribution of users

## 🔒 Security Considerations

### Academic Network Security

```bash
# Configure firewall
sudo ufw allow 22/tcp    # SSH
sudo ufw allow 80/tcp    # HTTP
sudo ufw allow 443/tcp   # HTTPS
sudo ufw enable

# Set up fail2ban
sudo apt install fail2ban
sudo systemctl enable fail2ban
```

### Data Privacy

- No user data is stored
- All requests are anonymous
- Only structure access patterns are logged
- Compliant with academic privacy policies

## 📈 Performance Optimization

### Academic Server Optimization

```bash
# Optimize Nginx for academic workloads
sudo nano /etc/nginx/nginx.conf
```

```nginx
worker_processes auto;
worker_connections 1024;

http {
    # Academic-specific optimizations
    client_max_body_size 10M;
    keepalive_timeout 65;
    
    # Research data caching
    proxy_cache_path /var/cache/nginx/research levels=1:2 keys_zone=research:10m;
}
```

## 🧪 Testing Academic Workflows

### Test Research Scenarios

```bash
# Test small protein structures
curl "https://your-domain.edu.dz/SUnv-Mol_Vw_api.html?entId=1CRN"

# Test large macromolecular complexes
curl "https://your-domain.edu.dz/SUnv-Mol_Vw_api.html?entId=4V6X"

# Test AlphaFold predictions
curl "https://your-domain.edu.dz/SUnv-Mol_Vw_api.html?entId=AF-Q9I4X8-F1"
```

## 📚 Academic Integration Examples

### Research Website Integration

```html
<!-- Embed in research pages -->
<iframe 
    src="https://your-domain.edu.dz/SUnv-Mol_Vw_api.html?entId=1CRN"
    width="800" 
    height="600"
    frameborder="0">
</iframe>
```

### Course Material Integration

```html
<!-- For educational content -->
<div class="molecular-viewer">
    <h3>Protein Structure Visualization</h3>
    <iframe 
        src="https://your-domain.edu.dz/demo.html"
        width="100%" 
        height="700"
        frameborder="0">
    </iframe>
</div>
```

## 🆘 Troubleshooting

### Common Issues

1. **Permission Errors**
   ```bash
   sudo chown -R www-data:www-data /var/www/sunv-mol-api
   sudo chmod -R 755 /var/www/sunv-mol-api
   ```

2. **SSL Certificate Issues**
   ```bash
   sudo certbot renew --dry-run
   ```

3. **Performance Issues**
   ```bash
   sudo systemctl status nginx
   sudo tail -f /var/log/nginx/error.log
   ```

## 📞 Support

- **Technical Issues**: [GitHub Issues](https://github.com/rachedi-2526/SUnv-Mol.Vw-API/issues)
- **Academic Support**: [bioinformatics@univ-saida.dz](mailto:bioinformatics@univ-saida.dz)
- **Research Collaboration**: Contact Dr. Abdelkrim RACHEDI

---

**© 2025 University of Saida - Dr. Moulay Tahar, Saida, Algeria**

*Deployment guide for academic institutions*
