# la-docker-base
Reusable Docker base images for building and running applications.

## Purpose

This repository provides a set of shared Docker base images intended to be reused across multiple projects.  
It serves as a centralized foundation to standardize containerization practices and simplify application builds.

## Use cases

- Build application images based on a common Docker foundation
- Ensure consistency across projects
- Reduce duplication in Docker configurations
- Serve as a base for CI/CD pipelines and containerized environments

## Repository structure

Each directory represents a base image or a template that can be extended by application-specific images.

```text
.
├── react/
├── node/
├── laravel/
├── nginx/
└── README.md
