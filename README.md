# 🚀 ChatFlow AI

<div align="center">

![ChatFlow AI Logo](https://img.shields.io/badge/ChatFlow-AI-00D9FF?style=for-the-badge&logo=whatsapp&logoColor=white)

**Open-Source WhatsApp & Marketing Automation Platform**

Build intelligent chatbots, automate marketing campaigns, and scale your business with AI-powered messaging.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)
[![GitHub Stars](https://img.shields.io/github/stars/itskiranbabu/chatflow-ai?style=social)](https://github.com/itskiranbabu/chatflow-ai/stargazers)

[Features](#-features) • [Demo](#-demo) • [Quick Start](#-quick-start) • [Documentation](#-documentation) • [Roadmap](#-roadmap) • [Contributing](#-contributing)

</div>

---

## 🎯 What is ChatFlow AI?

ChatFlow AI is a **modern, open-source alternative** to expensive WhatsApp automation platforms like Wati, Interakt, and AiSensy. Built with cutting-edge technology and powered by AI, it helps businesses automate customer conversations, run marketing campaigns, and scale their operations—all through WhatsApp.

### 🌟 Why ChatFlow AI?

- **💰 Cost-Effective**: Save 70% compared to commercial alternatives
- **🔓 Open Source**: Full transparency, no vendor lock-in
- **🤖 AI-Powered**: Built-in ChatGPT integration for intelligent conversations
- **🎨 No-Code Builder**: Visual chatbot builder, no coding required
- **📊 Unified Dashboard**: Manage everything from one beautiful interface
- **🔌 Self-Hostable**: Deploy on your own infrastructure for complete control
- **🌍 Multi-Channel**: WhatsApp, Email, SMS (coming soon)

---

## ✨ Features

### 🤖 **Intelligent Chatbots**
- Visual drag-and-drop chatbot builder
- AI-powered responses with ChatGPT/Gemini
- Multi-language support
- Context-aware conversations
- Human handover when needed

### 📢 **Marketing Automation**
- Bulk WhatsApp messaging (broadcast campaigns)
- Drip campaigns & sequences
- Abandoned cart recovery
- Promotional campaigns
- A/B testing
- Campaign analytics

### 💬 **Team Inbox**
- Unified inbox for all conversations
- Team collaboration features
- Assignment & routing rules
- Canned responses
- Real-time notifications
- Conversation history

### 📊 **CRM & Analytics**
- Contact management
- Lead scoring
- Sales pipeline
- Custom fields & tags
- Detailed analytics dashboard
- Export reports

### 🔗 **Integrations**
- WhatsApp Business API (Official)
- Evolution API (Open Source)
- Email (SendGrid, SMTP)
- SMS gateways
- Shopify, WooCommerce
- Zapier, Make.com
- Custom webhooks

### 🎨 **Premium Features**
- White-label branding
- Custom domain
- API access
- Advanced analytics
- Priority support
- Multi-tenant architecture

---

## 🏗️ Architecture

ChatFlow AI is built with a modern, scalable microservices architecture:

```
┌─────────────────────────────────────────────────────────────┐
│                     Frontend (Next.js)                       │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐      │
│  │   Dashboard  │  │  Chatbot     │  │   Campaign   │      │
│  │              │  │   Builder    │  │   Manager    │      │
│  └──────────────┘  └──────────────┘  └──────────────┘      │
└─────────────────────────────────────────────────────────────┘
                              │
                    ┌─────────▼─────────┐
                    │   API Gateway     │
                    │   (NestJS)        │
                    └─────────┬─────────┘
                              │
        ┌─────────────────────┼─────────────────────┐
        │                     │                     │
┌───────▼────────┐  ┌────────▼────────┐  ┌────────▼────────┐
│   WhatsApp     │  │   Marketing     │  │      CRM        │
│   Service      │  │   Service       │  │    Service      │
│                │  │                 │  │                 │
│ • Evolution API│  │ • Campaigns     │  │ • Contacts      │
│ • Chatbot      │  │ • Broadcasts    │  │ • Leads         │
│ • Webhooks     │  │ • Sequences     │  │ • Pipeline      │
└────────────────┘  └─────────────────┘  └─────────────────┘
        │                     │                     │
        └─────────────────────┼─────────────────────┘
                              │
                    ┌─────────▼─────────┐
                    │   Data Layer      │
                    │                   │
                    │ • PostgreSQL      │
                    │ • MongoDB         │
                    │ • Redis           │
                    └───────────────────┘
```

---

## 🚀 Quick Start

### Prerequisites

- Node.js 18+ and npm/yarn
- Docker & Docker Compose
- PostgreSQL 14+
- Redis 7+
- WhatsApp Business API credentials

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/itskiranbabu/chatflow-ai.git
cd chatflow-ai
```

2. **Install dependencies**
```bash
npm install
```

3. **Set up environment variables**
```bash
cp .env.example .env
# Edit .env with your configuration
```

4. **Start services with Docker**
```bash
docker-compose up -d
```

5. **Run database migrations**
```bash
npm run migrate
```

6. **Start the development server**
```bash
npm run dev
```

7. **Open your browser**
```
http://localhost:3000
```

### 🐳 Docker Quick Start

```bash
# Clone and start everything with one command
git clone https://github.com/itskiranbabu/chatflow-ai.git
cd chatflow-ai
docker-compose up -d

# Access the app at http://localhost:3000
```

---

## 📚 Documentation

Comprehensive documentation is available in the `/docs` folder:

- [Installation Guide](./docs/INSTALLATION.md)
- [Configuration](./docs/CONFIGURATION.md)
- [API Reference](./docs/API.md)
- [Chatbot Builder Guide](./docs/CHATBOT_BUILDER.md)
- [Deployment Guide](./docs/DEPLOYMENT.md)
- [Contributing Guide](./CONTRIBUTING.md)

---

## 🗺️ Roadmap

### Phase 1: MVP (Weeks 1-8) ✅ In Progress
- [x] Project setup & architecture
- [ ] WhatsApp integration (Evolution API)
- [ ] Basic chatbot builder
- [ ] Contact management
- [ ] Bulk messaging
- [ ] Team inbox
- [ ] Basic analytics

### Phase 2: Marketing Automation (Weeks 9-12)
- [ ] Campaign builder
- [ ] Drip sequences
- [ ] A/B testing
- [ ] Email integration
- [ ] Advanced analytics
- [ ] Template library

### Phase 3: AI & Intelligence (Weeks 13-16)
- [ ] ChatGPT integration
- [ ] AI-powered responses
- [ ] Sentiment analysis
- [ ] Lead scoring
- [ ] Predictive analytics
- [ ] Natural language workflow builder

### Phase 4: Enterprise Features (Weeks 17-20)
- [ ] White-label branding
- [ ] Multi-tenant architecture
- [ ] Advanced RBAC
- [ ] API access
- [ ] Custom integrations
- [ ] Enterprise security

### Phase 5: Scale & Polish (Weeks 21-24)
- [ ] Performance optimization
- [ ] Mobile apps (iOS/Android)
- [ ] Marketplace for templates
- [ ] Advanced reporting
- [ ] Multi-language support
- [ ] Production launch 🚀

---

## 🛠️ Tech Stack

### Frontend
- **Framework**: Next.js 14 (App Router)
- **UI Library**: Shadcn/ui + Tailwind CSS
- **State Management**: Zustand + React Query
- **Charts**: Recharts
- **Forms**: React Hook Form + Zod

### Backend
- **Framework**: NestJS (TypeScript)
- **API**: GraphQL + REST
- **Authentication**: JWT + OAuth2
- **Queue**: BullMQ
- **WebSockets**: Socket.io

### Database
- **Primary**: PostgreSQL 14+ (relational data)
- **Secondary**: MongoDB (logs, analytics)
- **Cache**: Redis 7+
- **Search**: Elasticsearch (optional)

### Infrastructure
- **Containerization**: Docker + Docker Compose
- **Orchestration**: Kubernetes (production)
- **CI/CD**: GitHub Actions
- **Monitoring**: Prometheus + Grafana
- **Logging**: Winston + ELK Stack

### Integrations
- **WhatsApp**: Evolution API + Official WhatsApp Business API
- **AI**: OpenAI GPT-4, Google Gemini
- **Email**: SendGrid, AWS SES
- **SMS**: Twilio
- **Payments**: Stripe

---

## 💡 Use Cases

### E-commerce
- Automated order confirmations
- Abandoned cart recovery
- Product recommendations
- Customer support automation

### SaaS Companies
- Lead qualification
- Onboarding automation
- Feature announcements
- Customer success automation

### Agencies
- Multi-client management
- White-label solutions
- Campaign management
- Client reporting

### Education
- Course enrollment automation
- Student support
- Assignment reminders
- Parent communication

---

## 🤝 Contributing

We love contributions! ChatFlow AI is built by the community, for the community.

### How to Contribute

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

Please read our [Contributing Guide](./CONTRIBUTING.md) for details on our code of conduct and development process.

---

## 📊 Comparison with Competitors

| Feature | ChatFlow AI | Wati | Interakt | AiSensy |
|---------|-------------|------|----------|---------|
| **Pricing** | Free (self-hosted) | $39/mo | $17/mo | $20/mo |
| **Open Source** | ✅ Yes | ❌ No | ❌ No | ❌ No |
| **Self-Hosted** | ✅ Yes | ❌ No | ❌ No | ❌ No |
| **AI Chatbots** | ✅ Yes | ✅ Yes | ✅ Yes | ✅ Yes |
| **Bulk Messaging** | ✅ Yes | ✅ Yes | ✅ Yes | ✅ Yes |
| **API Access** | ✅ Free | 💰 Paid | 💰 Paid | 💰 Paid |
| **White Label** | ✅ Yes | ❌ No | ❌ No | ❌ No |
| **Custom Code** | ✅ Yes | ❌ No | ❌ No | ❌ No |
| **Data Privacy** | ✅ Full Control | ⚠️ Limited | ⚠️ Limited | ⚠️ Limited |

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

ChatFlow AI is built on the shoulders of giants:

- [Evolution API](https://github.com/EvolutionAPI/evolution-api) - WhatsApp integration
- [Mautic](https://github.com/mautic/mautic) - Marketing automation inspiration
- [Twenty](https://github.com/twentyhq/twenty) - CRM architecture
- [n8n](https://github.com/n8n-io/n8n) - Workflow automation concepts

---

## 📞 Support & Community

- **Documentation**: [docs.chatflow.ai](https://docs.chatflow.ai) (coming soon)
- **Discord**: [Join our community](https://discord.gg/chatflow) (coming soon)
- **Twitter**: [@ChatFlowAI](https://twitter.com/chatflowai) (coming soon)
- **Email**: support@chatflow.ai

---

## ⭐ Star History

[![Star History Chart](https://api.star-history.com/svg?repos=itskiranbabu/chatflow-ai&type=Date)](https://star-history.com/#itskiranbabu/chatflow-ai&Date)

---

<div align="center">

**Made with ❤️ by the ChatFlow AI Community**

[⬆ Back to Top](#-chatflow-ai)

</div>
