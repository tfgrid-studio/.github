# TFGrid Studio

<div align="center">

**Complete Development Platform for ThreeFold Grid**

Build, deploy, and scale decentralized applications with enterprise-grade tools

[Website](https://tfgrid.studio) • [Documentation](https://docs.tfgrid.studio) • [Get Started](https://docs.tfgrid.studio/getting-started/quickstart)

</div>

---

## 🎯 What is TFGrid Studio?

**TFGrid Studio** is a complete development platform for ThreeFold Grid. From AI-powered coding to production deployment, we provide everything you need to build decentralized applications.

**Our Products:**
- 🛠️ **TFGrid Compose** - Docker-compose-like CLI (✅ Available Now)
- 🤖 **TFGrid AI Agent** - AI coding environment (✅ Available Now)
- 🌐 **TFGrid Web** - Visual dashboard (🚧 Q2 2026)
- 🏪 **TFGrid Marketplace** - App store (🚧 Q3 2026)
- 🏢 **TFGrid Enterprise** - Enterprise features (📋 Custom)

```bash
# Deploy any application with one command
tfgrid-compose up my-app
```

**Open source CLI. Enterprise-ready platform. No vendor lock-in.**

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
| [tfgrid-compose](https://github.com/tfgrid-studio/tfgrid-compose) | Main CLI tool (formerly tfgrid-deployer) | ✅ **Production Ready (v1.0.0)** |
| [tfgrid-ai-agent](https://github.com/tfgrid-studio/tfgrid-ai-agent) | AI coding agent | ✅ **Production Ready (v2.0.0)** |
| [tfgrid-docs](https://github.com/tfgrid-studio/tfgrid-docs) | Complete documentation | ✅ **Live** ([docs.tfgrid.studio](https://docs.tfgrid.studio)) |
| [tfgrid-www](https://github.com/tfgrid-studio/tfgrid-www) | Marketing website | ✅ **Live** ([tfgrid.studio](https://tfgrid.studio)) |

### 🔒 Commercial (Private - Future)

| Repository | Description | Status | Timeline |
|------------|-------------|--------|----------|
| tfgrid-web | Web dashboard (SaaS) | 📋 Planned | Q2 2026 |
| tfgrid-marketplace | App marketplace | 📋 Planned | Q3 2026 |
| tfgrid-enterprise | Enterprise features (SSO, audit logs) | 📋 Custom | On demand |

---

## 🎯 Quick Start

### Install

```bash
git clone https://github.com/tfgrid-studio/tfgrid-compose
cd tfgrid-compose
make install
```

**That's it!** The CLI is now in your PATH.

### Deploy an App

```bash
# Deploy the AI agent
tfgrid-compose up tfgrid-ai-agent

# Check status
tfgrid-compose status tfgrid-ai-agent

# View logs
tfgrid-compose logs tfgrid-ai-agent

# SSH into VM
tfgrid-compose ssh tfgrid-ai-agent

# Destroy when done
tfgrid-compose down tfgrid-ai-agent
```

---

## 🏗️ Architecture

### The Big Picture

```
Standalone Apps  +  Universal Deployer  →  ThreeFold Grid
(Portable)          (Orchestrator)         (Decentralized)
```

### Deployment Patterns

**🔹 single-vm** - Simple VM deployment  
Perfect for: Development, databases, internal services

**🔹 gateway** (Coming Soon)  
Perfect for: Web apps, e-commerce, traditional hosting

**🔹 k3s** (Coming Soon)  
Perfect for: Cloud-native apps, microservices, SaaS

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

**🎉 MVP Complete! (80%)**

```
✅ Week 1: Extraction            [████████████████████] 100%
✅ Week 2: Metadata System       [████████████████████] 100%
✅ Week 3: CLI Development       [████████████████████] 100%
✅ Week 4: Orchestration         [████████████████████] 100%
⏳ Week 5: Testing               [░░░░░░░░░░░░░░░░░░░░]   0%
⏳ Week 6: Documentation         [░░░░░░░░░░░░░░░░░░░░]   0%
```

**What's Working:**
- ✅ Full deployment orchestration
- ✅ Pattern system (single-vm)
- ✅ App manifest system
- ✅ Complete CLI tool
- ✅ State management
- ✅ All commands functional

**Next:**
- Testing with real TFGrid accounts
- Documentation polish
- v1.0.0 release

---

## 🚀 Roadmap

### Phase 1: MVP (Current - Week 5-6)

**Focus:** single-vm pattern + tfgrid-ai-agent

**Deliverables:**
- ✅ Core deployer working
- ✅ One reference app (AI agent)
- ⏳ Production testing
- ⏳ v1.0.0 release

**Target:** October 2025

---

### Phase 2: Complete FOSS Platform (Months 2-3)

**Focus:** All patterns + multiple apps

**Deliverables:**
- Gateway pattern
- K3s pattern
- 5-10 example apps
- Comprehensive docs
- Community building

**Target:** December 2025

---

### Phase 3: Commercial Layer (Months 4-6)

**Focus:** SaaS dashboard

**Deliverables:**
- tfgrid-web (managed platform)
- Team features
- Billing integration
- Beta launch

**Target:** Q1 2026

---

### Phase 4: Marketplace & Enterprise (Months 7-12)

**Focus:** Ecosystem growth

**Deliverables:**
- App marketplace
- Enterprise features
- Partner program
- Revenue generation

**Target:** Q2-Q3 2026

---

## 💰 Business Model

### Open Core Strategy

**FOSS Core (Free Forever):**
- tfgrid-deployer
- All deployment patterns
- CLI tool
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

- **[Quick Start](https://github.com/tfgrid-compose/tfgrid-deployer#quick-start)** - Get started in 5 minutes
- **[Patterns](https://github.com/tfgrid-compose/tfgrid-deployer#patterns)** - Available deployment patterns
- **[App Development](https://github.com/tfgrid-compose/tfgrid-docs)** - Create deployable apps
- **[Pattern Development](https://github.com/tfgrid-compose/tfgrid-docs)** - Create new patterns
- **[API Reference](https://github.com/tfgrid-compose/tfgrid-docs)** - Complete API docs

---

## 🌟 Showcase

### Example Apps

**AI Coding Agent** - [tfgrid-ai-agent](https://github.com/tfgrid-compose/tfgrid-ai-agent)  
Isolated AI coding environment with loop technique

**Coming Soon:**
- WordPress (gateway pattern)
- Next.js (gateway pattern)
- SaaS Starter (k3s pattern)
- PostgreSQL (single-vm pattern)
- Redis (single-vm pattern)

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

[Get Started](https://github.com/tfgrid-compose/tfgrid-deployer) • [Documentation](https://github.com/tfgrid-compose/tfgrid-docs) • [Community](https://github.com/orgs/tfgrid-compose/discussions)

</div>
