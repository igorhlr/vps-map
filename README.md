# 🏗️ Enterprise VPS Infrastructure Map

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Igor%20Rozalem-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/igor-rozalem/)
[![Status](https://img.shields.io/badge/Status-Production-success?style=for-the-badge)](https://github.com/igorhlr/vps-map)
[![Uptime](https://img.shields.io/badge/Uptime-99.9%25-brightgreen?style=for-the-badge)](https://github.com/igorhlr/vps-map)
[![Cost Saving](https://img.shields.io/badge/Cost%20Saving-90%25-orange?style=for-the-badge)](https://github.com/igorhlr/vps-map)


<details>
<summary><b>📸 Click to view Full Screenshots</b></summary>

<div align="center">

### Infrastructure Overview
![Infrastructure Overview](screenshots/1panel.png)

### Metrics Overview
![AI Platform](screenshots/metrics-chat.png)

### Models Overview
![*Local embeddings](screenshots/emb-models.png)

### Workflow Overview
![Local embeddings configuration](screenshots/map-config-emb.png)

### Online Vscode Overview
![vscode configuration](screenshots/vscode.png)


</div>

</details>


<details>
<summary><b>🗺️ Click to view Full Architecture Diagram</b></summary>

```mermaid
graph TB
    subgraph "🏗️ Enterprise VPS Architecture - Igor Rozalem"
        subgraph "Entry Points & Load Balancing"
            DNS["🌐 DNS Routing<br/>llmway.com.br"]
            Traefik["🔀 Traefik Proxy<br/>Load Balancer<br/>SSL Certificates<br/>Auto-routing"]
        end
        
        subgraph "Development Layer"
            VSCode["💻 VSCode Web<br/>vscode.llmway.com.br<br/>Full SSH Access<br/>Real VPS Control"]
            Panel["🎛️ 1Panel Dashboard<br/>1panel.llmway.com.br<br/>Container Management<br/>Resource Monitor"]
        end
        
        subgraph "AI & Intelligence Platform"
            subgraph "Embedding System"
                LocalEmbed["🧠 Local Embeddings<br/>Ollama Models<br/>Zero API Cost<br/>Private Data"]
            end
            
            subgraph "Custom Agent"
                IgorAgent["🤖 Igor Agent<br/>Personal Assistant<br/>Knowledge Base<br/>Private Context"]
            end
            
            subgraph "AI Core"
                MaxKB["🎯 MaxKB Platform<br/>agently.llmway.com.br<br/>Agent Orchestration<br/>Custom Workflows"]
                Ollama["🦙 Ollama Engine<br/>Local LLM Processing<br/>7B-70B Models<br/>Smart Switching"]
            end
        end
        
        subgraph "Production Applications"
            WP1["📱 wordpress.llmway.1<br/>MaxKB Integration Test"]
            WP2["📱 wordpress.llmway.2<br/>Client Project Alpha"]
            WP3["📱 wordpress.llmway.3<br/>Development Staging"]
            WP4["📱 wordpress.llmway.4<br/>Production Site"]
            
            subgraph "NotionAI Ecosystem"
                NotionAPI["📝 NotionAiAssistant<br/>MCP Integration<br/>API Service<br/>Live Demo"]
                NotionCICD["⚙️ Notion CI/CD<br/>GitHub Actions<br/>Independent Pipeline<br/>Auto-deploy"]
                Docs["📖 Documentation<br/>docs.notionassistant<br/>mdBook Platform<br/>Auto-deploy"]
            end
        end
        
        subgraph "Data & Storage Layer"
            MySQL["🗄️ MySQL<br/>Application Data<br/>WordPress DB<br/>Transactional"]
            Postgres["🗄️ PostgreSQL<br/>MaxKB Storage<br/>Vector Database<br/>AI Context & Embeddings"]
        end
        
        subgraph "Infrastructure & DevOps"
            Docker["🐳 Docker Engine<br/>7+ Containers<br/>Resource Isolation<br/>Auto-restart"]
            GitHub["📦 GitHub Repos<br/>Source Control<br/>Version Management"]
            Actions["⚙️ GitHub Actions<br/>Main CI/CD Pipeline<br/>Infrastructure Deploy<br/>Auto Testing"]
            MCP["🔗 MCP Protocol<br/>Universal Integration<br/>AI Orchestration<br/>Innovation Layer"]
        end
        
        subgraph "Monitoring & Metrics"
            Metrics["📊 PRODUCTION METRICS<br/>99.9% Uptime (6 months)<br/>7+ Services Running<br/>5 Active Projects<br/> Processing"]
            Performance["⚡ PERFORMANCE<br/>Response: <200ms<br/>Deploy: 3min<br/>Recovery: <30s<br/>Scale: Auto"]
            Savings["💰 COST OPTIMIZATION<br/>Cloud Cost: $50/month<br/>VPS Cost: $5/month<br/>Savings: 90%<br/>ROI: 10x"]
        end
    end
    
    DNS --> Traefik
    Traefik --> VSCode
    Traefik --> Panel
    Traefik --> MaxKB
    Traefik --> WP1
    Traefik --> WP2
    Traefik --> WP3
    Traefik --> WP4
    Traefik --> NotionAPI
    Traefik --> Docs
    
    VSCode --> Docker
    Panel --> Docker
    
    MaxKB --> LocalEmbed
    MaxKB --> IgorAgent
    MaxKB --> Ollama
    
    IgorAgent --> LocalEmbed
    IgorAgent --> Postgres
    LocalEmbed --> Postgres
    
    Ollama --> Postgres
    
    WP1 --> MySQL
    WP2 --> MySQL
    WP3 --> MySQL
    WP4 --> MySQL
    
    NotionAPI --> Postgres
    NotionAPI --> MCP
    NotionCICD --> NotionAPI
    NotionCICD --> Docs
    MaxKB --> MCP
    
    GitHub --> Actions
    GitHub --> NotionCICD
    Actions --> Docker
    
    Docker --> Metrics
    Metrics --> Performance
    Performance --> Savings
    
    classDef entryClass fill:#2196F3,stroke:#1565C0,stroke-width:2px,color:#fff
    classDef devClass fill:#4CAF50,stroke:#2E7D32,stroke-width:2px,color:#fff
    classDef aiClass fill:#9C27B0,stroke:#6A1B9A,stroke-width:2px,color:#fff
    classDef embedClass fill:#FF5722,stroke:#D84315,stroke-width:2px,color:#fff
    classDef agentClass fill:#00BCD4,stroke:#00838F,stroke-width:2px,color:#fff
    classDef prodClass fill:#FF9800,stroke:#E65100,stroke-width:2px,color:#fff
    classDef notionClass fill:#000000,stroke:#333333,stroke-width:2px,color:#fff
    classDef dataClass fill:#607D8B,stroke:#37474F,stroke-width:2px,color:#fff
    classDef infraClass fill:#3F51B5,stroke:#283593,stroke-width:2px,color:#fff
    classDef metricsClass fill:#FFD700,stroke:#FFA000,stroke-width:3px,color:#000
    
    class DNS,Traefik entryClass
    class VSCode,Panel devClass
    class MaxKB,Ollama aiClass
    class LocalEmbed embedClass
    class IgorAgent agentClass
    class WP1,WP2,WP3,WP4 prodClass
    class NotionAPI,NotionCICD,Docs notionClass
    class MySQL,Postgres dataClass
    class Docker,GitHub,Actions,MCP infraClass
    class Metrics,Performance,Savings metricsClass
```

</details>



## 📊 Overview

Complete architecture diagram of my enterprise VPS infrastructure featuring **7+ production services**, **local AI embeddings**, and **90% cost reduction** compared to traditional cloud solutions.

---

---

## 🎯 Key Features

### 🧠 **Local AI Processing**
- **Zero API Costs**: All embeddings processed locally using Ollama
- **Private & Secure**: Data never leaves the server
- **Multiple Models**: Support for 7B to 70B parameter models
- **Smart Switching**: Automatic optimization between local and cloud

### 🤖 **Igor Agent - Custom Assistant**
- Personal Knowledge Base via local embeddings
- Context-aware with private data
- MaxKB Platform orchestration
- Zero external dependencies

### 🚀 **Technical Innovations**
- **MCP Protocol Integration**: Universal AI orchestration layer
- **Dual CI/CD Architecture**: Separate pipelines for infrastructure and NotionAssistant
- **Browser-Based IDE**: VSCode Web with full SSH access
- **Hybrid Processing**: Local LLMs for privacy, APIs for scale

### 📊 **Production Services**
- 4 WordPress sites with AI chatbots
- [NotionAiAssistant](https://github.com/igorhlr/NotionAiAssistant) with independent CI/CD
- Documentation platform with auto-deployment
- Development environments accessible via browser

---

---

## 🛠️ Technology Stack

<div align="left">

| Category | Technologies |
|----------|-------------|
| **Infrastructure** | Docker, Traefik, Ubuntu Server, Nginx |
| **AI Platform** | Ollama, MaxKB, Local Embeddings, MCP Protocol |
| **Databases** | MySQL, PostgreSQL with pgvector |
| **DevOps** | GitHub Actions (Dual Pipeline), 1Panel |
| **Development** | VSCode Web, Full SSH Access |

</div>

---

## 💡 Architecture Highlights

### **1. Entry Layer**
- Traefik proxy with SSL and load balancing
- Automatic routing for all services
- DNS management for subdomains

### **2. Development Layer**
- Browser-based VSCode with real VPS access
- 1Panel for container management
- Full SSH control (not containerized)

### **3. AI Layer**
- Local embeddings with zero API costs
- Igor Agent with private knowledge base
- MaxKB orchestration platform

### **4. Application Layer**
- Multiple WordPress sites
- NotionAiAssistant with MCP
- Auto-deployed documentation

### **5. Data Layer**
- MySQL for transactional data
- PostgreSQL with pgvector for embeddings
- Optimized for AI workloads

### **6. DevOps Layer**
- Main infrastructure pipeline
- Independent NotionAssistant pipeline
- Zero-downtime deployments

---

## 📈 Results & Impact

### **Cost Optimization**
```
Traditional Cloud: $50/month
This VPS Setup:    $5/month
Savings:           90% reduction
ROI:               10x
```

### **Performance**
```
Uptime:           99.9% (6 months)
Response Time:    <200ms average
Deploy Time:      3 minutes
Recovery Time:    <30 seconds
```

### **Scale**
```
Services:         7+ containers
Active Projects:  5
```

---

## 🔗 Live Projects Running

| Project | Description | Link |
|---------|-------------|------|
| **NotionAiAssistant** | MCP-powered Notion integration | [GitHub](https://github.com/igorhlr/NotionAiAssistant) |
| **Live Demo** | NotionAssistant in action | [Demo](https://notionassistant.llmway.com.br) |
| **Documentation** | Technical documentation | [Docs](https://docs.notionassistant.llmway.com.br) |
| **AI Platform** | MaxKB/Agently | [Platform](https://agently.llmway.com.br) |

---

## 🚀 Key Differentiators

✅ **Local embeddings with private knowledge base**  
✅ **Dual CI/CD for complex architectures**  
✅ **Browser IDE with real VPS access**  
✅ **Proven scalability with real metrics**  

---

## 📞 Get in Touch

Interested in learning more about:
- Building cost-effective AI infrastructure?
- Implementing local embeddings with zero API costs?
- Creating custom AI agents?
- Achieving 90% cost reduction while scaling?

### **Let's connect!**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/igor-rozalem/)
[![Email](https://img.shields.io/badge/Email-Contact-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:igorhlr2@icloud.com)

---

## 📄 License

This architecture diagram and documentation are shared for educational purposes. The actual infrastructure contains proprietary configurations.

---

<div align="center">
  
**Built with ❤️ by [Igor Rozalem](https://www.linkedin.com/in/igor-rozalem/)**

</div>