---
marp: true
theme: custom-theme
paginate: true
size: 16:9
header: 'Product Documentation | API Gateway v2.0'
footer: '© 2024 TechCorp | 23f3001973@ds.study.iitm.ac.in'
style: |
  @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&display=swap');
  
  /* Custom Theme Specification */
  section {
    font-family: 'Inter', sans-serif;
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    color: white;
    font-size: 24px;
    padding: 60px;
  }
  
  section.lead {
    text-align: center;
    background: linear-gradient(45deg, #1a365d, #2d3748, #1a202c);
  }
  
  section.content {
    background: white;
    color: #2d3748;
  }
  
  section.dark {
    background: #1a202c;
    color: white;
  }
  
  section.image-bg {
    background-image: url('https://images.unsplash.com/photo-1518186285589-2f7649de83e0?w=1200&h=675&fit=crop');
    background-size: cover;
    background-position: center;
    color: white;
    text-shadow: 2px 2px 4px rgba(0,0,0,0.8);
  }
  
  h1 {
    font-size: 2.5em;
    font-weight: 700;
    margin-bottom: 0.5em;
    text-align: center;
  }
  
  h2 {
    font-size: 2em;
    font-weight: 600;
    margin-bottom: 0.8em;
    border-bottom: 3px solid #4299e1;
    padding-bottom: 0.2em;
  }
  
  h3 {
    font-size: 1.5em;
    font-weight: 600;
    margin-bottom: 0.6em;
    color: #4299e1;
  }
  
  .content h2 {
    color: #2d3748;
    border-bottom-color: #4299e1;
  }
  
  .content h3 {
    color: #4299e1;
  }
  
  code {
    background: rgba(45, 55, 72, 0.1);
    padding: 2px 6px;
    border-radius: 4px;
    font-family: 'JetBrains Mono', monospace;
  }
  
  pre {
    background: #2d3748;
    color: #e2e8f0;
    padding: 20px;
    border-radius: 8px;
    overflow-x: auto;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  }
  
  .content pre {
    background: #2d3748;
    color: #e2e8f0;
  }
  
  ul li {
    margin-bottom: 0.5em;
  }
  
  .highlight {
    background: rgba(66, 153, 225, 0.2);
    padding: 20px;
    border-left: 4px solid #4299e1;
    border-radius: 4px;
    margin: 20px 0;
  }
  
  .email-contact {
    background: #38a169;
    color: white;
    padding: 8px 16px;
    border-radius: 20px;
    display: inline-block;
    font-weight: 600;
    margin: 10px 0;
  }
  
  .math-container {
    background: rgba(255, 255, 255, 0.1);
    padding: 20px;
    border-radius: 8px;
    margin: 20px 0;
    text-align: center;
  }
  
  .content .math-container {
    background: rgba(45, 55, 72, 0.05);
  }
  
  table {
    border-collapse: collapse;
    width: 100%;
    margin: 20px 0;
  }
  
  th, td {
    border: 1px solid #e2e8f0;
    padding: 12px;
    text-align: left;
  }
  
  th {
    background: #4299e1;
    color: white;
    font-weight: 600;
  }
  
  .content th, .content td {
    border-color: #cbd5e0;
  }
---

<!-- _class: lead -->

# API Gateway v2.0
## Product Documentation

### Complete Developer Guide & Technical Specifications

**Technical Writer:** Development Documentation Team  
**Contact:** <span class="email-contact">📧 23f3001973@ds.study.iitm.ac.in</span>

**Version:** 2.0.1  
**Last Updated:** December 2024

---

<!-- _class: content -->

## Table of Contents

### 📋 Documentation Overview

1. **Introduction & Architecture**
2. **Installation & Quick Start**
3. **API Reference & Examples**
4. **Performance & Complexity Analysis**
5. **Configuration & Deployment**
6. **Security & Best Practices**
7. **Troubleshooting & Support**

<div class="highlight">
<strong>Note:</strong> This documentation is maintained in version control and automatically generates multiple output formats (HTML, PDF, PPTX) using Marp CLI.
</div>

---

<!-- _class: content -->

## Product Overview

### 🚀 API Gateway v2.0 Features

- **High-Performance Routing**: Handle 100K+ requests per second
- **Authentication & Authorization**: OAuth 2.0, JWT, API Keys
- **Rate Limiting**: Advanced algorithms with Redis backing
- **Load Balancing**: Multiple strategies with health checking
- **Monitoring**: Real-time metrics and distributed tracing
- **Plugin Architecture**: Extensible with custom middleware

### 💡 Key Improvements in v2.0

- 40% performance improvement over v1.x
- Enhanced security with zero-trust architecture  
- Kubernetes-native deployment options
- GraphQL federation support

**Technical Support:** 23f3001973@ds.study.iitm.ac.in

---

<!-- _class: image-bg -->

## Architecture Overview

### 🏗️ Microservices Gateway Pattern

- **Edge Layer**: Public-facing API endpoints
- **Gateway Layer**: Request routing and transformation
- **Service Mesh**: Internal service communication
- **Data Layer**: Persistent storage and caching

### Core Components

- **Router Engine**: High-performance request matching
- **Plugin System**: Extensible middleware pipeline  
- **Admin API**: Configuration and monitoring interface
- **Event System**: Real-time notifications and webhooks

---

<!-- _class: content -->

## Quick Start Guide

### 📦 Installation

#### Using Docker (Recommended)

```bash
# Pull the latest image
docker pull techcorp/api-gateway:v2.0.1

# Run with default configuration
docker run -d \
  --name api-gateway \
  -p 8000:8000 \
  -p 8001:8001 \
  techcorp/api-gateway:v2.0.1
```

#### Using Package Manager

```bash
# Ubuntu/Debian
curl -s https://packages.techcorp.com/key.gpg | sudo apt-key add -
echo "deb https://packages.techcorp.com/ubuntu focal main" | sudo tee /etc/apt/sources.list.d/techcorp.list
sudo apt update && sudo apt install api-gateway

# macOS
brew tap techcorp/tap
brew install api-gateway
```

---

<!-- _class: content -->

## Configuration Example

### 🔧 Basic Gateway Configuration

```yaml
# gateway.yml
server:
  host: 0.0.0.0
  port: 8000
  admin_port: 8001

database:
  host: postgres://localhost:5432/gateway
  pool_size: 10
  timeout: 30s

services:
  - name: user-service
    url: http://users.internal:3000
    routes:
      - paths: ["/api/users/*"]
        methods: ["GET", "POST", "PUT", "DELETE"]
        plugins:
          - name: rate-limit
            config:
              requests_per_minute: 100
          - name: auth
            config:
              strategy: jwt
```

---

<!-- _class: content -->

## API Reference

### 🔌 Core Endpoints

| Endpoint | Method | Description | Authentication |
|----------|---------|-------------|----------------|
| `/services` | GET | List all services | Admin Token |
| `/services` | POST | Create service | Admin Token |
| `/routes` | GET | List all routes | Admin Token |
| `/plugins` | GET | List available plugins | Admin Token |
| `/health` | GET | Health check | None |
| `/metrics` | GET | Prometheus metrics | Admin Token |

### Example API Call

```javascript
// Create a new service
const response = await fetch('http://gateway:8001/services', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
    'Authorization': 'Bearer admin-token'
  },
  body: JSON.stringify({
    name: 'payment-service',
    url: 'http://payments.internal:3000',
    timeout: 30000
  })
});
```

---

<!-- _class: dark -->

## Performance Analysis

### ⚡ Algorithmic Complexity

<div class="math-container">

**Request Routing Complexity**

$$O(log \, n) \text{ where } n = \text{number of routes}$$

**Load Balancing Algorithm (Weighted Round Robin)**

$$\text{Next Server} = \arg\min_{i} \left(\frac{\text{current\_requests}_i}{\text{weight}_i}\right)$$

**Rate Limiting (Token Bucket)**

$$\text{Allow Request} = \begin{cases} 
\text{true} & \text{if } \text{tokens} > 0 \\
\text{false} & \text{otherwise}
\end{cases}$$

where tokens are replenished at rate $r$ per second.

</div>

### 📊 Performance Benchmarks

- **Latency (P95)**: < 5ms
- **Throughput**: 100,000 RPS
- **Memory Usage**: < 512MB base
- **CPU Usage**: < 30% at peak load

---

<!-- _class: content -->

## Security Configuration

### 🔒 Authentication Strategies

#### JWT Authentication

```yaml
plugins:
  - name: jwt
    config:
      secret: "${JWT_SECRET}"
      algorithm: "HS256"
      claims_to_verify: ["exp", "iat", "sub"]
      header_name: "Authorization"
      header_type: "Bearer"
```

#### OAuth 2.0 Integration

```yaml
plugins:
  - name: oauth2
    config:
      provider: "auth0"
      client_id: "${OAUTH_CLIENT_ID}"
      client_secret: "${OAUTH_CLIENT_SECRET}"
      scopes: ["read:users", "write:users"]
      redirect_uri: "http://gateway:8000/oauth/callback"
```

<div class="highlight">
<strong>Security Contact:</strong> For security issues, email 23f3001973@ds.study.iitm.ac.in
</div>

---

<!-- _class: content -->

## Monitoring & Observability

### 📈 Metrics Collection

#### Prometheus Integration

```yaml
# prometheus.yml
global:
  scrape_interval: 15s

scrape_configs:
  - job_name: 'api-gateway'
    static_configs:
      - targets: ['gateway:8001']
    scrape_interval: 5s
    metrics_path: '/metrics'
```

#### Key Metrics to Monitor

- `gateway_requests_total{status, method, route}`
- `gateway_request_duration_seconds{route}`
- `gateway_active_connections`
- `gateway_plugin_execution_duration_seconds{plugin}`

### 🔍 Distributed Tracing

- **Jaeger Integration**: Automatic span creation
- **Correlation IDs**: Request tracking across services
- **Error Attribution**: Precise error source identification

---

<!-- _class: content -->

## Deployment Strategies

### ☸️ Kubernetes Deployment

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: api-gateway
spec:
  replicas: 3
  selector:
    matchLabels:
      app: api-gateway
  template:
    metadata:
      labels:
        app: api-gateway
    spec:
      containers:
      - name: gateway
        image: techcorp/api-gateway:v2.0.1
        ports:
        - containerPort: 8000
        - containerPort: 8001
        env:
        - name: DATABASE_URL
          valueFrom:
            secretKeyRef:
              name: gateway-secrets
              key: db-url
        resources:
          requests:
            cpu: 500m
            memory: 512Mi
          limits:
            cpu: 2000m
            memory: 2Gi
```

---

<!-- _class: dark -->

## Plugin Development

### 🔧 Custom Plugin Architecture

#### Plugin Interface

```go
// Plugin represents a middleware component
type Plugin interface {
    Name() string
    Priority() int
    Execute(ctx *Context) error
}

// Example: Custom logging plugin
type LoggerPlugin struct {
    config LoggerConfig
}

func (p *LoggerPlugin) Execute(ctx *Context) error {
    start := time.Now()
    
    // Execute next plugin in chain
    err := ctx.Next()
    
    // Log request details
    log.Info("Request processed",
        "method", ctx.Request.Method,
        "path", ctx.Request.URL.Path,
        "status", ctx.Response.StatusCode,
        "duration", time.Since(start),
    )
    
    return err
}
```

---

<!-- _class: content -->

## Troubleshooting Guide

### 🚨 Common Issues & Solutions

#### High Memory Usage

**Problem**: Gateway consuming excessive memory  
**Solution**: 
1. Check plugin memory leaks
2. Tune database connection pool
3. Review log retention policies

```bash
# Monitor memory usage
kubectl top pod api-gateway-*

# Check plugin status
curl -s http://gateway:8001/plugins | jq '.plugins[] | select(.enabled == true)'
```

#### Rate Limiting Issues

**Problem**: Legitimate requests being blocked  
**Solution**:
1. Review rate limit configuration
2. Implement whitelist for trusted IPs
3. Use distributed rate limiting with Redis

<div class="highlight">
<strong>Support Email:</strong> 23f3001973@ds.study.iitm.ac.in
</div>

---

<!-- _class: content -->

## Version Control & Maintenance

### 📝 Documentation Workflow

#### Git Workflow for Documentation

```bash
# Clone documentation repository
git clone https://github.com/techcorp/api-gateway-docs.git
cd api-gateway-docs

# Create feature branch for updates
git checkout -b docs/update-v2.0.1

# Edit Marp markdown files
vim slides/product-docs.md

# Build multiple formats
marp slides/ --html --pdf --pptx --output dist/

# Commit and push changes
git add .
git commit -m "docs: Update API Gateway v2.0.1 documentation"
git push origin docs/update-v2.0.1
```

#### Automated CI/CD Pipeline

```yaml
# .github/workflows/docs.yml
name: Build Documentation
on:
  push:
    branches: [main]
    paths: ['slides/**/*.md']

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    - uses: docker://marpteam/marp-cli:latest
      with:
        args: slides/ --html --pdf --output dist/
    - name: Deploy to GitHub Pages
      uses: peaceiris/actions-gh-pages@v3
```

---

<!-- _class: lead -->

## Contact & Support

### 📞 Getting Help

**Technical Documentation Team**

<span class="email-contact">📧 Primary Contact: 23f3001973@ds.study.iitm.ac.in</span>

### 🔗 Additional Resources

- **GitHub Repository**: https://github.com/techcorp/api-gateway
- **Issue Tracker**: https://github.com/techcorp/api-gateway/issues  
- **Community Forum**: https://community.techcorp.com/api-gateway
- **Status Page**: https://status.techcorp.com

### 📋 Documentation Formats

- **Presentation**: Available as HTML, PDF, and PPTX
- **Version Control**: Maintained in Git with automatic builds
- **Updates**: Continuous integration with release cycles

---

<!-- _class: lead -->

# Thank You

## Questions & Discussion

**This presentation is maintained in version control**  
**Raw GitHub URL**: `https://raw.githubusercontent.com/techcorp/api-gateway-docs/main/slides.md`

<span class="email-contact">📧 Contact: 23f3001973@ds.study.iitm.ac.in</span>

### Next Steps
- Review the Quick Start Guide
- Try the sample configurations
- Join our developer community
- Contribute to documentation improvements
