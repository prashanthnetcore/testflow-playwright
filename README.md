# TestFlow - Playwright Test Automation Platform

TestFlow is a comprehensive SaaS platform for recording, managing, optimizing, and running Playwright test cases at scale. It provides an intuitive UI for test recording, AI-powered test optimization, parallel test execution, and detailed reporting.

## Features

- **Test Recording**: Record browser interactions with automatic selector generation
- **AI-Powered Optimization**: Automatically improve test reliability and performance
- **Parallel Execution**: Run tests across multiple browsers simultaneously
- **Flexible Scheduling**: Schedule tests to run at specific intervals
- **Detailed Reporting**: Get comprehensive test run reports with video recordings
- **Team Collaboration**: Share tests and results with your team
- **Environment Management**: Run tests across different environments
- **Anchor Browser Integration**: Leverage Anchor Browser for enhanced parallel execution

## Architecture

TestFlow consists of several microservices:

- **Frontend**: React application for user interface
- **API Server**: Express/Node.js backend API
- **Recorder Service**: Playwright-based service for recording tests
- **Test Runner**: Executes tests with Playwright
- **AI Optimization Service**: Analyzes and optimizes test scripts
- **Scheduler Service**: Manages scheduled test runs

## Quick Start

### Docker Compose

The easiest way to get started is with Docker Compose:

```bash
git clone https://github.com/prashanthnetcore/testflow-playwright.git
cd testflow-playwright
docker-compose up -d
```

This will start all required services and the web UI will be available at http://localhost:80.

### Kubernetes

For production deployments, use the Kubernetes configuration:

```bash
kubectl apply -f deployment/kubernetes/
```

## Development Setup

### Prerequisites

- Node.js 16+
- MongoDB
- RabbitMQ
- MinIO (or S3-compatible storage)

### Frontend

```bash
cd frontend
npm install
npm run dev
```

### Backend

```bash
cd backend
npm install
npm run dev
```

### Services

```bash
cd services/recorder-service
npm install
npm run dev

cd services/test-runner
npm install
npm run dev

cd services/ai-service
npm install
npm run dev

cd services/scheduler-service
npm install
npm run dev
```

## Environment Variables

See `.env.example` files in each directory for required environment variables.

## Deployment Options

### AWS

TestFlow can be deployed on AWS using:
- EC2 instances or ECS for compute
- MongoDB Atlas or DocumentDB for database
- Amazon MQ for message queue
- S3 for storage

### Azure

For Azure deployments:
- Azure App Service or AKS for compute
- Cosmos DB with MongoDB API for database
- Azure Service Bus for message queue
- Azure Blob Storage for storage

## API Reference

The TestFlow API follows RESTful conventions:

- `GET /api/tests` - List all tests
- `POST /api/tests` - Create a new test
- `GET /api/tests/:id` - Get a specific test
- `PUT /api/tests/:id` - Update a test
- `DELETE /api/tests/:id` - Delete a test
- `POST /api/tests/:id/run` - Run a test
- `GET /api/runs` - List all test runs
- `GET /api/runs/:id` - Get a specific test run

See the API documentation for more details.

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

MIT