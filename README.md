# RidA Platform - Local Development Setup

A monorepo platform built with Next.js, NestJS, and React Native using Turborepo and pnpm.

## 🚀 Quick Start

### Prerequisites

- **Node.js** >= 18.x
- **pnpm** (package manager)
- **Git**

### 1. Install pnpm

```bash
# Install pnpm globally
npm install -g pnpm@latest-10

# Or using PowerShell on Windows
Invoke-WebRequest https://get.pnpm.io/install.ps1 -UseBasicParsing | Invoke-Expression

# Or using Homebrew on macOS
brew install pnpm
```

### 2. Clone the Repository

```bash
git clone https://github.com/chdean-09/RidA.git
cd RidA
```

### 3. Install Dependencies

```bash
# Install all dependencies for the entire monorepo
pnpm install
```

### 4. Environment Setup

N/A For now!

## 📁 Project Structure

```
RidA/
├── apps/
│   ├── mobile/          # React Native (Expo)
│   ├── server/          # NestJS API
│   └── superadmin/      # Next.js Admin Panel
├── packages/            # Shared packages
├── .github/workflows/   # CI/CD pipelines
├── turbo.json           # Turborepo configuration
├── pnpm-workspace.yaml  # pnpm workspace configuration
└── package.json         # list of root packages
```

## 🛠️ Development Commands

### Start All Applications

```bash
# Start all apps in development mode
pnpm run dev
```

### Work with Specific Applications

```bash
# Start individual apps
pnpm run dev --filter=server          # NestJS API (port 8000)
pnpm run dev --filter=superadmin      # Next.js Admin (port 3000)
pnpm run dev --filter=mobile          # Expo Application
```

## 🚀 Application Details

### Server (NestJS API)
- **Port**: 8000
- **Tech**: NestJS, TypeScript

### Super Admin (Next.js)
- **Port**: 3000
- **Tech**: Next.js 15, TypeScript, Tailwind CSS

### Mobile (React Native/Expo)
- **Tech**: Expo, React Native, TypeScript

## 🐳 Docker Development

### Using Docker Compose

```bash
# Start services with Docker
docker-compose up -d

# Build and start
docker-compose up --build

# Stop services
docker-compose down
```

### Individual Docker Builds

```bash
# Build server image
docker build -f apps/server/Dockerfile -t rida-server .

# Run server container
docker run -p 8000:8000 rida-server
```

## 📦 Package Management

### Adding Dependencies

```bash
# Add to root workspace
pnpm add <package-name>

# Add to specific workspace
pnpm --filter server add <package-name>
pnpm --filter superadmin add -D <dev-package>

# Add to all workspaces
pnpm -r add <package-name>

# Alternative
cd apps/server
pnpm add package-name
```

## 🧪 Testing

```bash
# Run all tests
pnpm test

# Run tests for specific app
pnpm --filter server test
pnpm --filter server test:watch
pnpm --filter server test:cov

# Run e2e tests
pnpm --filter server test:e2e
```

## 🔍 Code Quality

```bash
# Lint all projects
pnpm lint

# Lint specific project
pnpm --filter server lint

# Format code
pnpm --filter server format

# Type checking
pnpm --filter server check-types
```

## 🚀 Deployment

### Production Build

```bash
# Build all applications
pnpm build

# Build specific app
pnpm --filter server build
pnpm --filter superadmin build
```

## 📚 Useful Resources

- [pnpm Documentation](https://pnpm.io/)
- [Turborepo Documentation](https://turbo.build/repo)
- [NestJS Documentation](https://docs.nestjs.com/)
- [Next.js Documentation](https://nextjs.org/docs)
- [Expo Documentation](https://docs.expo.dev/)

## 📄 License

This project is licensed under the MIT License.