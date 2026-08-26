# AI Multi-Agents Dashboard

An interactive, real-time dashboard for monitoring and managing AI multi-agents and sub-agents workflow. Built with **Next.js**, **React**, and **Tailwind CSS**.

## 🎯 Features

- 📊 **Real-time Agent Monitoring** - Track agent status (Active, Idle, Error, Busy)
- 🌳 **Agent Hierarchy Visualization** - View agent-to-sub-agent relationships
- 📋 **Workflow Timeline** - Monitor task execution flow and dependencies
- 📈 **Performance Metrics** - Track response times, success rates, and throughput
- 🔄 **Task Queue Management** - View pending, running, and completed tasks
- 💬 **Agent Communication Logs** - Inspect agent-to-agent interactions
- ⚡ **Real-time Updates** - WebSocket-based live data streaming
- 📱 **Responsive Design** - Works seamlessly on desktop, tablet, and mobile
- 🎨 **Dark Mode Support** - Eye-friendly interface
- 🔐 **Authentication Ready** - Built-in auth structure

## 🚀 Quick Start

### Prerequisites
- Node.js 18+ 
- npm or yarn

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/meetkalsii/ai-multi-agents-dashboard.git
cd ai-multi-agents-dashboard
```

2. **Install dependencies**
```bash
npm install
```

3. **Create environment variables**
```bash
cp .env.example .env.local
```

4. **Run the development server**
```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) to view the dashboard.

## 📁 Project Structure

```
ai-multi-agents-dashboard/
├── app/
│   ├── layout.tsx              # Root layout
│   ├── page.tsx                # Home/Dashboard page
│   ├── api/                    # API routes
│   │   ├── agents/             # Agent endpoints
│   │   ├── tasks/              # Task endpoints
│   │   └── workflows/          # Workflow endpoints
│   └── dashboard/
│       ├── page.tsx            # Main dashboard
│       ├── agents/             # Agents section
│       ├── tasks/              # Tasks section
│       └── metrics/            # Metrics section
├── components/
│   ├── AgentCard.tsx           # Individual agent component
│   ├── AgentHierarchy.tsx      # Agent tree visualization
│   ├── TaskQueue.tsx           # Task queue component
│   ├── WorkflowTimeline.tsx    # Workflow visualization
│   ├── MetricsPanel.tsx        # Performance metrics
│   ├── CommunicationLog.tsx    # Agent logs
│   └── ui/                     # Reusable UI components
├── lib/
│   ├── api.ts                  # API client utilities
│   ├── types.ts                # TypeScript types
│   ├── utils.ts                # Helper functions
│   └── websocket.ts            # WebSocket manager
├── hooks/
│   ├── useAgents.ts            # Agents data hook
│   ├── useTasks.ts             # Tasks data hook
│   └── useWebSocket.ts         # WebSocket hook
├── public/
│   └── icons/                  # SVG icons
├── styles/
│   └── globals.css             # Global styles
├── .env.example                # Environment template
├── package.json
├── tsconfig.json
├── tailwind.config.js
└── next.config.js
```

## 🛠️ Tech Stack

- **Framework:** Next.js 14+
- **Language:** TypeScript
- **Styling:** Tailwind CSS
- **UI Components:** Shadcn/ui
- **Charts:** Recharts
- **State Management:** React Context + Zustand
- **Real-time:** WebSocket / Socket.io
- **API:** REST + GraphQL ready
- **Database:** MongoDB / PostgreSQL (configurable)
- **Authentication:** NextAuth.js (optional)

## 📊 Dashboard Sections

### 1. **Agent Overview**
- Total agents count
- Agent status distribution (Active, Idle, Error)
- Resource utilization
- Average response time

### 2. **Agent Management**
- List all agents and sub-agents
- View agent details and capabilities
- Monitor agent health
- Start/stop agents
- Agent configuration

### 3. **Workflow Execution**
- Real-time workflow timeline
- Task dependencies visualization
- Execution status per task
- Time tracking and SLA monitoring

### 4. **Task Queue**
- Pending tasks
- Running tasks
- Completed tasks
- Failed tasks with error logs
- Task priority and scheduling

### 5. **Performance Metrics**
- Response time distribution
- Task success rate
- Agent throughput
- Error rate tracking
- Custom metrics

### 6. **Agent Communication**
- Real-time message logs
- Agent-to-agent interactions
- Request/response pairs
- Performance analysis

## 🔧 Environment Variables

Create a `.env.local` file:

```env
# API Configuration
NEXT_PUBLIC_API_URL=http://localhost:3001
NEXT_PUBLIC_WS_URL=ws://localhost:3001

# Database
DATABASE_URL=mongodb://localhost:27017/ai-agents

# Authentication (Optional)
NEXTAUTH_SECRET=your_secret_key
NEXTAUTH_URL=http://localhost:3000

# Third-party Services
OPENAI_API_KEY=your_api_key
```

## 🔌 API Endpoints

### Agents
- `GET /api/agents` - Get all agents
- `GET /api/agents/:id` - Get agent details
- `POST /api/agents` - Create agent
- `PUT /api/agents/:id` - Update agent
- `DELETE /api/agents/:id` - Delete agent

### Tasks
- `GET /api/tasks` - Get all tasks
- `GET /api/tasks/:id` - Get task details
- `POST /api/tasks` - Create task
- `PUT /api/tasks/:id` - Update task status

### Workflows
- `GET /api/workflows` - Get all workflows
- `POST /api/workflows` - Create workflow
- `GET /api/workflows/:id/timeline` - Get execution timeline

## 📡 WebSocket Events

```javascript
// Agent events
'agent:status-update'
'agent:heartbeat'
'agent:error'

// Task events
'task:created'
'task:started'
'task:completed'
'task:failed'

// Workflow events
'workflow:started'
'workflow:completed'
'workflow:progress'
```

## 🎨 Component Usage

### AgentCard Component
```tsx
import AgentCard from '@/components/AgentCard'

<AgentCard
  agent={{
    id: '1',
    name: 'Agent Alpha',
    status: 'active',
    tasks: 5,
    successRate: 95
  }}
/>
```

### TaskQueue Component
```tsx
import TaskQueue from '@/components/TaskQueue'

<TaskQueue tasks={tasks} onTaskClick={handleTaskClick} />
```

## 🚢 Deployment

### Deploy to Vercel (Recommended)

```bash
npm run build
vercel deploy
```

### Deploy to other platforms
- Docker support ready
- See `Dockerfile` for containerization
- AWS, GCP, Azure compatible

## 📖 Documentation

- [Next.js Docs](https://nextjs.org/docs)
- [Tailwind CSS Docs](https://tailwindcss.com/docs)
- [Recharts Docs](https://recharts.org)
- [WebSocket Guide](./docs/WEBSOCKET.md)
- [API Documentation](./docs/API.md)

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see [LICENSE](LICENSE) file for details.

## 🐛 Issues & Support

Found a bug? Have a suggestion? 
- [Open an Issue](https://github.com/meetkalsii/ai-multi-agents-dashboard/issues)
- [Start a Discussion](https://github.com/meetkalsii/ai-multi-agents-dashboard/discussions)

## 📧 Contact

- GitHub: [@meetkalsii](https://github.com/meetkalsii)

## 🎓 Learning Resources

- [Building Real-time Dashboards with Next.js](./docs/TUTORIALS.md)
- [Agent Architecture Patterns](./docs/PATTERNS.md)
- [Performance Optimization Guide](./docs/OPTIMIZATION.md)

---

**Happy Coding! 🚀**

Built with ❤️ for AI enthusiasts and developers
