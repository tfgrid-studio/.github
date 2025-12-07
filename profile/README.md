# TFGrid Studio

<div align="center">

**Complete Development Platform for ThreeFold Grid**

Build, deploy, and scale decentralized applications with enterprise-grade tools

[Website](https://tfgrid.studio) • [Documentation](https://docs.tfgrid.studio) • [Get Started](https://docs.tfgrid.studio/getting-started/quickstart)

</div>

---

## 🎯 What is TFGrid Studio?

**TFGrid Studio** is a complete development platform for ThreeFold Grid. From AI-powered coding to production deployment, we provide everything you need to build decentralized applications.

### What We Offer

**🛠️ TFGrid Compose** - Universal deployment CLI
- One-command deployment to ThreeFold Grid
- Interactive mode with DNS automation
- Local dashboard for managing deployments
- 3 deployment patterns: single-vm, gateway, k3s

**📦 6 Production-Ready Apps**
| App | Description |
|-----|-------------|
| [tfgrid-wordpress](https://github.com/tfgrid-studio/tfgrid-wordpress) | WordPress + Caddy + MariaDB |
| [tfgrid-nextcloud](https://github.com/tfgrid-studio/tfgrid-nextcloud) | Nextcloud All-in-One cloud platform |
| [tfgrid-erpnext](https://github.com/tfgrid-studio/tfgrid-erpnext) | ERPNext business ERP system |
| [tfgrid-ai-agent](https://github.com/tfgrid-studio/tfgrid-ai-agent) | AI coding assistant |
| [tfgrid-ai-stack](https://github.com/tfgrid-studio/tfgrid-ai-stack) | AI + Git + Gateway stack |
| [tfgrid-gitea](https://github.com/tfgrid-studio/tfgrid-gitea) | Self-hosted Git service |

```bash
# Install tfgrid-compose
curl -sSL install.tfgrid.studio/install.sh | sh

# Deploy any app interactively
tfgrid-compose up tfgrid-wordpress -i
```

**Open source. Enterprise-ready. No vendor lock-in.**

---

## ✨ Features

- 🎯 **Simple Deployment** - One command to deploy any application
- 🏗️ **Pattern-Based** - Reusable deployment patterns (single-vm, gateway, k3s)
- 📦 **Portable Apps** - Apps work anywhere, not tied to infrastructure
- 🔧 **Industry Tools** - Uses Terraform, Ansible, Kubernetes (no proprietary tech)
- 🌍 **Decentralized** - Runs on ThreeFold Grid
- 🔓 **Open Source** - Apache 2.0 license

---

## 🏢 Repository Structure

### 🔓 FOSS Core (Public)

| Repository | Description | Status |
|------------|-------------|--------|
| [tfgrid-compose](https://github.com/tfgrid-studio/tfgrid-compose) | Main CLI tool | ✅ **Production Ready** |
| [tfgrid-docs](https://github.com/tfgrid-studio/tfgrid-docs) | Complete documentation | ✅ **Live** ([docs.tfgrid.studio](https://docs.tfgrid.studio)) |
| [tfgrid-website](https://github.com/tfgrid-studio/tfgrid-website) | Marketing website | ✅ **Live** ([tfgrid.studio](https://tfgrid.studio)) |
| [tfgrid-install](https://github.com/tfgrid-studio/tfgrid-install) | One-line installer | ✅ **Live** ([install.tfgrid.studio](https://install.tfgrid.studio)) |
| [registry-www](https://github.com/tfgrid-studio/registry-www) | App registry browser | ✅ **Live** ([registry.tfgrid.studio](https://registry.tfgrid.studio)) |
| [app-registry](https://github.com/tfgrid-studio/app-registry) | Official app registry data | ✅ Active |
| [tfgrid-wordpress](https://github.com/tfgrid-studio/tfgrid-wordpress) | WordPress + Caddy + MariaDB | ✅ **New** |
| [tfgrid-nextcloud](https://github.com/tfgrid-studio/tfgrid-nextcloud) | Nextcloud All-in-One | ✅ **New** |
| [tfgrid-erpnext](https://github.com/tfgrid-studio/tfgrid-erpnext) | ERPNext business ERP | ✅ **New** |
| [tfgrid-ai-agent](https://github.com/tfgrid-studio/tfgrid-ai-agent) | AI coding assistant | ✅ Production |
| [tfgrid-ai-stack](https://github.com/tfgrid-studio/tfgrid-ai-stack) | AI + Git + Gateway stack | ✅ Production |
| [tfgrid-gitea](https://github.com/tfgrid-studio/tfgrid-gitea) | Self-hosted Git service | ✅ Production |
| [community](https://github.com/tfgrid-studio/community) | Community docs & discussions | ✅ Active |

For a high-level visual map of how these pieces fit together, see:

- **Platform Map:** https://docs.tfgrid.studio/architecture/platform-map

---

## 🎯 Quick Start

### Install

```bash
# One-line install
curl -sSL install.tfgrid.studio/install.sh | sh

# Or manual install
git clone https://github.com/tfgrid-studio/tfgrid-compose
cd tfgrid-compose
make install
```

**That's it!** The CLI is now in your PATH.

### Deploy an App

```bash
# Deploy WordPress (interactive mode - prompts for domain, DNS, etc.)
tfgrid-compose up tfgrid-wordpress -i

# Deploy Nextcloud cloud platform
tfgrid-compose up tfgrid-nextcloud -i

# Deploy ERPNext business system
tfgrid-compose up tfgrid-erpnext -i

# Deploy AI coding agent
tfgrid-compose up tfgrid-ai-agent

# Check status
tfgrid-compose status <app-name>

# SSH into VM
tfgrid-compose ssh <app-name>

# Destroy when done
tfgrid-compose down <app-name>
```

---

## 🏗️ Architecture

### The Big Picture

```
Standalone Apps  +  Universal Deployer  →  ThreeFold Grid
(Portable)          (Orchestrator)         (Decentralized)
```

### Deployment Patterns

**✅ single-vm** - Simple VM deployment  
Perfect for: Development, databases, internal services, AI agents

**✅ gateway** - Multi-VM with public access  
Perfect for: Production web apps, e-commerce, SSL-enabled sites

**✅ k3s** - Kubernetes clusters  
Perfect for: Cloud-native apps, microservices, enterprise SaaS

---

## 📦 How It Works

### 1. Define Your App

```yaml
# tfgrid-compose.yaml
name: my-app
version: 1.0.0

patterns:
  recommended: single-vm

resources:
  cpu: {recommended: 4}
  memory: {recommended: 8192}
  disk: {recommended: 100}

hooks:
  setup: deployment/setup.sh
  configure: deployment/configure.sh
  healthcheck: deployment/healthcheck.sh
```

### 2. Deploy

```bash
tfgrid-compose up my-app
```

**What happens:**
1. ✅ Validates app and pattern
2. ✅ Generates Terraform config
3. ✅ Creates infrastructure (VM)
4. ✅ Configures platform (Ansible)
5. ✅ Deploys your app
6. ✅ Runs your hooks
7. ✅ Verifies deployment

### 3. Manage

```bash
tfgrid-compose logs my-app      # View logs
tfgrid-compose status my-app    # Check status
tfgrid-compose ssh my-app       # SSH access
tfgrid-compose down my-app      # Destroy
```

---

## 🎨 Deployment Patterns

### Pattern: single-vm

**Architecture:**
```
┌─────────────────────────┐
│  Single VM              │
│  - Your app running     │
│  - Private networking   │
│  - Wireguard access     │
└─────────────────────────┘
```

**Use Cases:**
- Development environments
- Databases (PostgreSQL, MongoDB, Redis)
- Background workers
- Internal tools
- AI agents

**Deploy:**
```bash
tfgrid-compose up my-app --pattern=single-vm
```

---

### Pattern: gateway (Phase 2)

**Architecture:**
```
┌───────────────────────────────┐
│  Gateway VM (Public)          │
│  - Public IPv4                │
│  - SSL termination            │
│  - Nginx reverse proxy        │
└───────────────────────────────┘
             ↓
┌───────────────────────────────┐
│  Backend VMs (Private)        │
│  - Web app                    │
│  - Database                   │
│  - Cache                      │
└───────────────────────────────┘
```

**Use Cases:**
- Production web apps
- E-commerce sites
- Multi-tier applications
- Any app needing public access

---

### Pattern: k3s (Phase 2)

**Architecture:**
```
┌─────────────────────────────────────┐
│  K3s Cluster                        │
│  ┌─────────────────────────────┐   │
│  │  Master (Public IP)         │   │
│  │  - Traefik Ingress          │   │
│  └─────────────────────────────┘   │
│  ┌─────────────────────────────┐   │
│  │  Workers (3+)               │   │
│  └─────────────────────────────┘   │
└─────────────────────────────────────┘
```

**Use Cases:**
- Modern cloud-native apps
- Microservices architectures
- High availability requirements
- Production SaaS platforms

---

## 💡 Why TFGrid Compose?

### ✅ No Vendor Lock-in

**Uses industry standards:**
- Terraform (Infrastructure as Code)
- Ansible (Configuration Management)
- Kubernetes (Container Orchestration)
- Standard Linux tools

**Result:** Your apps aren't locked to ThreeFold Grid. They can run anywhere.

### ✅ Simple & Powerful

**Heroku-like UX, Kubernetes power:**
- Simple commands (`up`, `down`, `logs`)
- Production-ready patterns
- Full control when needed

### ✅ Decentralized Infrastructure

**Runs on ThreeFold Grid:**
- Decentralized compute
- No single point of failure
- Geographic distribution
- Cost-effective

### ✅ Open Source

**Apache 2.0 license:**
- Free to use
- Free to modify
- Free to distribute
- Community-driven

---

## 🎯 Use Cases

### 1. AI/ML Development

**Deploy isolated AI coding environments:**
```bash
tfgrid-compose up tfgrid-ai-agent
```

Safe environment for AI-assisted coding without risking local files.

### 2. Web Applications

**Deploy traditional web apps with gateway pattern:**
```bash
tfgrid-compose up my-webapp --pattern=gateway --domain=myapp.com
```

Public IP, SSL, reverse proxy - all automated.

### 3. SaaS Platforms

**Deploy cloud-native apps on Kubernetes:**
```bash
tfgrid-compose up my-saas --pattern=k3s --domain=myapp.com
```

High availability, auto-scaling, production-ready.

### 4. Databases

**Deploy databases with persistent storage:**
```bash
tfgrid-compose up my-postgres --pattern=single-vm
```

PostgreSQL, MongoDB, Redis - all supported.

---

## 📊 Current Status

**🎉 6 Production Apps Available! (Dec 2025)**

```
✅ Phase 1: Foundation           [████████████████████] 100%
✅ Phase 2: Complete First Layer [████████████████████] 100%
✅ Phase 3: App Ecosystem        [████████████████░░░░]  80%
⏳ Phase 4: Web Dashboard        [░░░░░░░░░░░░░░░░░░░░]   0%
```

**What's Working:**
- ✅ All 3 deployment patterns (single-vm, gateway, k3s)
- ✅ Full deployment orchestration
- ✅ Interactive deployment mode (`-i` flag)
- ✅ DNS automation (Cloudflare, Name.com, Namecheap)
- ✅ SSL automation (Let's Encrypt via Caddy)
- ✅ 6 production-ready apps in registry
- ✅ Comprehensive documentation

**Available Apps:**
| App | Description | Status |
|-----|-------------|--------|
| tfgrid-ai-agent | AI coding assistant | ✅ Production |
| tfgrid-ai-stack | AI + Git + Gateway stack | ✅ Production |
| tfgrid-gitea | Self-hosted Git service | ✅ Production |
| tfgrid-wordpress | WordPress + Caddy + MariaDB | ✅ **New** |
| tfgrid-nextcloud | Nextcloud All-in-One | ✅ **New** |
| tfgrid-erpnext | ERPNext business ERP | ✅ **New** |

**Next:**
- Web dashboard (Q1 2026)
- App marketplace
- More community apps

---

## 🚀 Roadmap

### Phase 1: Foundation ✅ (Completed - Oct 8, 2025)

**Focus:** single-vm pattern + core platform

**Deliverables:**
- ✅ Core deployer working
- ✅ One reference app (AI agent)
- ✅ Production testing
- ✅ v1.0.0 release

**Result:** Production-ready MVP

---

### Phase 2: Complete First Layer ✅ (Completed - Oct 9, 2025)

**Focus:** All 3 core patterns

**Deliverables:**
- ✅ Gateway pattern (multi-VM, SSL, public access)
- ✅ K3s pattern (Kubernetes clusters)
- ✅ Pattern Contract system
- ✅ Comprehensive pattern documentation
- ✅ v2.0.0 release

**Result:** Complete deployment solution for all use cases

---

### Phase 3: App Ecosystem ✅ (Current - Dec 2025)

**Focus:** Production apps & ecosystem growth

**Deliverables:**
- ✅ Interactive deployment mode
- ✅ DNS automation (Cloudflare, Name.com, Namecheap)
- ✅ 6 production-ready apps
- ✅ WordPress, Nextcloud, ERPNext apps
- [ ] Automated test suite
- [ ] Community building

**Status:** 80% complete

---

### Phase 4: Portal (Q4 2025 - Q1 2026)

**Focus:** Visual management platform

**Deliverables:**
- [ ] tfgrid-portal (hosted web dashboard)
- [ ] Visual deployment management
- [ ] Real-time monitoring
- [ ] Team collaboration
- [ ] User authentication

**Target:** Q1 2026

---

### Phase 5: Marketplace & Enterprise (Q1-Q3 2026)

**Focus:** Ecosystem & revenue

**Deliverables:**
- [ ] App marketplace
- [ ] One-click deployments
- [ ] Enterprise features (SSO, SAML)
- [ ] Partner program
- [ ] Revenue generation

**Target:** Q2-Q3 2026

---

## 💰 Business Model

### Open Core Strategy

**FOSS Core (Free Forever):**
- tfgrid-compose CLI
- All 6 production apps
- All deployment patterns
- Community support

**Commercial Layers (Optional):**
- Managed platform (SaaS)
- App marketplace
- Enterprise features
- Premium support

### Revenue Streams

**1. Managed Platform**
```
Free:       $0 - 1 deployment
Pro:        $29/mo - 10 deployments
Team:       $99/mo - 50 deployments
Enterprise: $499/mo - Unlimited
```

**2. Marketplace**
```
Commission: 20% on paid apps
Featured:   $99-499/month
```

**3. Enterprise Services**
```
White-label:     $2K-5K/month
Custom patterns: $10K-50K
Consulting:      $200-400/hour
```

---

## 🤝 Contributing

We welcome contributions!

**How to contribute:**
1. Fork the repo
2. Create a feature branch
3. Make your changes
4. Submit a pull request

**Areas we need help:**
- 📝 Documentation
- 🧪 Testing
- 🎨 New patterns
- 📦 Example apps
- 🐛 Bug fixes

See individual repositories for CONTRIBUTING.md guides.

---

## 📖 Documentation

- **[Quick Start](https://docs.tfgrid.studio/getting-started/quickstart)** - Get started in 5 minutes
- **[Installation](https://docs.tfgrid.studio/getting-started/installation)** - Complete setup guide
- **[Patterns](https://docs.tfgrid.studio/patterns/overview)** - Available deployment patterns
- **[Roadmap](https://docs.tfgrid.studio/roadmap/current)** - Current status & planned features
- **[Complete Docs](https://docs.tfgrid.studio)** - Full documentation site

---

## 🌟 Showcase

### Production Apps

**AI Coding Agent** - [tfgrid-ai-agent](https://github.com/tfgrid-studio/tfgrid-ai-agent)  
Isolated AI coding environment with loop technique and Qwen integration

**WordPress** - [tfgrid-wordpress](https://github.com/tfgrid-studio/tfgrid-wordpress)  
Self-hosted WordPress with Caddy (auto-SSL), MariaDB, and DNS automation

**Nextcloud** - [tfgrid-nextcloud](https://github.com/tfgrid-studio/tfgrid-nextcloud)  
Nextcloud All-in-One cloud platform with file sync, calendar, Talk, and Office

**ERPNext** - [tfgrid-erpnext](https://github.com/tfgrid-studio/tfgrid-erpnext)  
Complete open-source ERP with accounting, inventory, HR, CRM, and more

**Gitea** - [tfgrid-gitea](https://github.com/tfgrid-studio/tfgrid-gitea)  
Lightweight self-hosted Git service

**Coming Soon:**
- Next.js (gateway pattern)
- SaaS Starter (k3s pattern)
- PostgreSQL (single-vm pattern)

---

## 🔗 Links

- **Website:** [tfgrid.studio](https://tfgrid.studio)
- **Documentation:** [docs.tfgrid.studio](https://docs.tfgrid.studio)
- **GitHub:** [github.com/tfgrid-studio](https://github.com/tfgrid-studio)
- **Main CLI:** [tfgrid-compose](https://github.com/tfgrid-studio/tfgrid-compose)
- **AI Agent:** [tfgrid-ai-agent](https://github.com/tfgrid-studio/tfgrid-ai-agent)
- **ThreeFold:** [threefold.io](https://threefold.io)

---

## 📧 Contact

- **Issues:** Open an issue in the relevant repository
- **Discussions:** [GitHub Discussions](https://github.com/orgs/tfgrid-studio/discussions)
- **Website:** [tfgrid.studio](https://tfgrid.studio)

---

## 📜 License

**FOSS Repositories:** Apache 2.0 License  
**Commercial Repositories:** Business Source License / Proprietary

See individual repositories for details.

---

<div align="center">

**Made with ❤️ for the decentralized web**

[Website](https://tfgrid.studio) • [Get Started](https://docs.tfgrid.studio/getting-started/quickstart) • [Documentation](https://docs.tfgrid.studio) • [Community](https://github.com/orgs/tfgrid-studio/discussions)

**© 2025 TFGrid Studio - Apache 2.0 License**

</div>
