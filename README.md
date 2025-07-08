# Task Manager - Docker Compose Project

A simple full-stack task management application demonstrating Docker Compose with multiple services.

## 🏗 Architecture

- Frontend: React.js application (Port 3000)
- Backend: Node.js/Express REST API (Port 5000)  
- Database: PostgreSQL (Port 5432)

##  Quick Start

### Prerequisites
- Docker
- Docker Compose

### Setup & Run

1. **Clone and navigate to project**
   ```bash
   git clone <your-repo>
   cd simple-task-manager
   ```

2. Create environment file
   ```bash
   cp .env.example .env
   # Edit .env with your database password
   ```

3. Start the application
   ```bash
   docker-compose up --build
   ```

4. **Access the application**
   - Frontend: http://localhost:3000
   - Backend API: http://localhost:5000/api/tasks

## 🛠️ Development Commands

```bash
# Start services
docker-compose up

# Start in background
docker-compose up -d

# View logs
docker-compose logs -f

# Stop services
docker-compose down

# Rebuild services
docker-compose build

# Access database
docker-compose exec postgres psql -U postgres -d taskmanager
```

 📁 Project Structure

```
simple-task-manager/
├── frontend/           # React application
│   ├── src/
│   │   ├── App.js     # Main component
│   │   └── App.css    # Styles
│   └── Dockerfile     # Frontend container
├── backend/            # Node.js API
│   ├── server.js      # Express server
│   ├── package.json   # Dependencies
│   └── Dockerfile     # Backend container
├── docker-compose.yml  # Service orchestration
├── .env               # Environment variables
└── README.md          # This file
```

## 🔧 API Endpoints

- `GET /api/health` - Health check
- `GET /api/tasks` - Get all tasks
- `POST /api/tasks` - Create new task
- `PUT /api/tasks/:id` - Update task status
- `DELETE /api/tasks/:id` - Delete task

## 🐳 Docker Features Demonstrated

- **Multi-service orchestration** with Docker Compose
- **Service dependencies** (backend depends on database)
- **Health checks** for reliable startup
- **Volume mounting** for development
- **Environment variables** for configuration
- **Custom Docker networks** for service communication
- **Data persistence** with named volumes

## 🧪 Testing

```bash
# Test backend API
curl http://localhost:5000/api/health

# Create a task
curl -X POST http://localhost:5000/api/tasks \
  -H "Content-Type: application/json" \
  -d '{"title":"Test Task","description":"Docker test"}'

# Get all tasks
curl http://localhost:5000/api/tasks
```

## 📊 What This Project Shows

### Docker Skills:
- Multi-container applications
- Service orchestration
- Database integration
- Development workflows
- Environment management

### Development Skills:
- Full-stack development
- REST API design
- Database operations
- Modern React patterns
- Express.js server setup

---

**Technologies**: Docker, Docker Compose, Node.js, React, PostgreSQL  
**Complexity**: Intermediate  
**Time to Setup**: 5-10 minutes
