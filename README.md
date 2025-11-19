# Safe registry
Security audit of packages

Overview
========
--------
This project is a web application that provides security audits for npm packages. It allows users to search for packages, view detailed security reports, and compare different packages based on their vulnerability data.
┌─────────────────────────────────────────────┐
│           Frontend (Next.js)                │
│  - Search UI, Package Detail, Comparison   │
│  - User Auth & Favorites                   │
└────────────────┬────────────────────────────┘
                 │
        ┌────────┴─────────┐
        │                  │
┌───────▼──────────┐  ┌────▼──────────────────┐
│  Next.js Routes  │  │  Backend (Node/Python)│
│  (BFF Pattern)   │  │  Dual Implementation  │
└───────┬──────────┘  └────┬──────────────────┘
        │                  │
        └──────────────────┼─────────────┐
                           │             │
                    ┌──────▼──────┐  ┌──▼────────────┐
                    │ PostgreSQL  │  │ External APIs │
                    │   (Prisma)  │  │ - npm Registry│
                    │             │  │ - GitHub API  │
                    │ Cache Layer │  │ - Snyk (vuln) │
                    └─────────────┘  └───────────────┘