Technical Overview
==================

This document provides a technical overview of the StudyFlow project architecture, technologies, 
and design decisions.

Project Structure
-----------------

Current Architecture (v0.0.1)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

StudyFlow is currently in its early stages with the following components:

**Jekyll Website** (``website/`` directory)

* Static site generator for the marketing website
* Built with Jekyll 4.x
* Uses Liquid templating
* Responsive design with custom CSS
* Deployed via GitHub Pages

**Sphinx Documentation** (``docs/`` directory)

* Documentation built with Sphinx
* reStructuredText (.rst) format
* Hosted on ReadTheDocs
* Auto-builds on commits to main branch

**Project Infrastructure**

* Version control: Git + GitHub
* CI/CD: GitHub Actions
* Issue tracking: GitHub Issues
* Discussions: GitHub Discussions + Discord

Planned Application Architecture
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The main StudyFlow application (in development) will follow a modern web architecture:

**Frontend**

* **Framework**: React or Vue.js (to be decided)
* **Build Tool**: Vite or Next.js
* **Styling**: CSS Modules or Tailwind CSS
* **State Management**: Redux or Zustand
* **UI Components**: Custom components with accessibility focus

**Backend** (Future)

* **Runtime**: Node.js
* **Framework**: Express.js or Fastify
* **Database**: PostgreSQL or MongoDB
* **Authentication**: JWT-based auth
* **API**: RESTful API or GraphQL

**Deployment**

* **Frontend**: Vercel, Netlify, or GitHub Pages
* **Backend**: Self-hosted or cloud platforms (AWS, DigitalOcean)
* **Database**: Self-hosted or managed database service

Technologies
------------

Current Stack
~~~~~~~~~~~~~

**Jekyll Website**

:Language: Ruby
:Framework: Jekyll 4.x
:Templating: Liquid
:Styling: Custom CSS
:Plugins: 
    * jekyll-feed
    * jekyll-seo-tag

**Documentation**

:Tool: Sphinx
:Format: reStructuredText
:Theme: Read the Docs theme
:Hosting: ReadTheDocs.io

**Development Tools**

:Version Control: Git
:Repository: GitHub
:Package Manager: Bundler (Ruby), npm (future)
:CI/CD: GitHub Actions

Planned Technologies
~~~~~~~~~~~~~~~~~~~~

**Frontend Application**

:Language: JavaScript/TypeScript
:Framework: React 18+ or Vue 3+
:Build Tool: Vite or Next.js
:Package Manager: npm or pnpm
:Testing: Jest + React Testing Library
:Linting: ESLint + Prettier

**Backend Services** (Future)

:Language: JavaScript/TypeScript (Node.js)
:Framework: Express.js or Fastify
:Database: PostgreSQL with Prisma ORM
:Authentication: Passport.js or Auth0
:API Documentation: Swagger/OpenAPI

**Infrastructure**

:Containerization: Docker (planned)
:Orchestration: Docker Compose
:Monitoring: To be determined
:Logging: Winston or Pino

Design Principles
-----------------

Privacy-First
~~~~~~~~~~~~~

* Self-hosting capability is a core requirement
* No third-party analytics or tracking
* User data stays under user control
* Optional cloud hosting for convenience

Student-Centric
~~~~~~~~~~~~~~~

* Designed specifically for academic workflows
* Course-based organization
* Academic calendar integration
* Group project collaboration features

Open Source
~~~~~~~~~~~

* Apache 2.0 License
* Community-driven development
* Transparent development process
* Welcoming to contributors of all skill levels

Accessibility
~~~~~~~~~~~~~

* WCAG 2.1 AA compliance (goal)
* Keyboard navigation support
* Screen reader friendly
* High contrast mode support

Performance
~~~~~~~~~~~

* Fast page loads (<3s on 3G)
* Optimized bundle sizes
* Lazy loading for better performance
* Progressive Web App (PWA) capabilities

Data Flow
---------

Current (Jekyll Website)
~~~~~~~~~~~~~~~~~~~~~~~~

1. Developer edits Markdown/HTML files
2. Jekyll builds static site
3. GitHub Actions deploys to GitHub Pages
4. Users access static website

Planned (Application)
~~~~~~~~~~~~~~~~~~~~~

1. User interacts with React frontend
2. Frontend makes API calls to backend
3. Backend processes requests and queries database
4. Database returns data
5. Backend sends response to frontend
6. Frontend updates UI

Security Considerations
-----------------------

Current
~~~~~~~

* Static site - minimal security concerns
* HTTPS enforced via GitHub Pages
* No user data collection

Planned
~~~~~~~

* **Authentication**: Secure JWT-based authentication
* **Authorization**: Role-based access control (RBAC)
* **Data Encryption**: Encrypted data at rest and in transit
* **Input Validation**: Server-side validation for all inputs
* **CORS**: Proper CORS configuration
* **Rate Limiting**: API rate limiting to prevent abuse
* **Security Headers**: CSP, HSTS, X-Frame-Options, etc.

Development Workflow
--------------------

Version Control
~~~~~~~~~~~~~~~

* **Main Branch**: Production-ready code
* **Feature Branches**: ``feature/feature-name``
* **Bug Fix Branches**: ``bugfix/bug-name``
* **Pull Requests**: Required for all changes
* **Code Review**: At least one approval required

Testing Strategy (Planned)
~~~~~~~~~~~~~~~~~~~~~~~~~~~

* **Unit Tests**: Jest for component and function testing
* **Integration Tests**: Testing API endpoints
* **E2E Tests**: Playwright or Cypress for user workflows
* **Coverage Goal**: 80%+ code coverage

Continuous Integration
~~~~~~~~~~~~~~~~~~~~~~

GitHub Actions workflows for:

* Linting and code formatting checks
* Running test suites
* Building documentation
* Deploying to staging/production

Future Roadmap
--------------

Phase 1: Foundation (Current)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

* ✅ Project structure
* ✅ Jekyll website
* ✅ Documentation setup
* ✅ Community channels

Phase 2: Core Application (Next)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

* 🚧 Basic Kanban board functionality
* 🚧 Task creation and management
* 🚧 User authentication
* 🚧 Database setup

Phase 3: Advanced Features
~~~~~~~~~~~~~~~~~~~~~~~~~~~

* ⏳ Smart reminders
* ⏳ Progress tracking
* ⏳ Calendar integration
* ⏳ Collaboration features

Phase 4: Polish & Scale
~~~~~~~~~~~~~~~~~~~~~~~~

* ⏳ Mobile app (React Native)
* ⏳ Offline support
* ⏳ Advanced analytics
* ⏳ Plugin system

Contributing to Development
----------------------------

See our :doc:`contributing` guide for information on how to contribute to the technical 
development of StudyFlow.

For architecture discussions and technical questions, join our:

* `Discord server <https://discord.gg/v2ctzYdp>`_
* `GitHub Discussions <https://github.com/luisjarquec/studyflow-app/discussions>`_
