<p align="center">
  <img src="images\document-builder-logo-under-1mb.jpg" width="720">
</p>

<h1 align="center">Document Builder Platform</h1>

<p align="center">
Centralized platform for generating documents in a controlled and reproducible environment.
</p>

<p align="center">
A single system that ensures every document is built using the same process, the same environment, and the same formatting rules.
</p>

---

# What is Document Builder

**Document Builder** is a platform designed to standardize document creation across an organization.

Instead of every employee installing and maintaining their own document toolchain, documents are built using a **central build engine** that guarantees:

* consistent formatting
* reproducible builds
* controlled build environments
* simplified user workflows

Users only prepare the document locally and submit it to the builder.

---

# Core Principles

### Consistency

All documents follow the same structure, layout and formatting rules.

### Accessibility

Employees can generate documents without installing or maintaining a full LaTeX toolchain.

### Centralized Generation

Documents are compiled by a shared build system to guarantee identical results across environments.

---

# Architecture Overview

The platform separates document preparation from document compilation.

```
Workstation
   │
   ▼
document-builder-client
   │
   ▼
document-builder-engine (API)
   │
   ▼
Redis Queue
   │
   ▼
Builder Runner
   │
   ▼
LaTeX Build Environment
   │
   ▼
PDF Artifact
```

### Workflow

1. User prepares a document locally.
2. The workstation client submits the document package.
3. The build engine queues the job.
4. The runner executes the build inside the controlled environment.
5. The generated PDF artifact is returned to the user.

This architecture ensures that every document is built **the same way every time**.

---

# Platform Repositories

The Document Builder platform is divided into multiple repositories.

## document-builder-engine

Central build engine responsible for:

* API service
* job lifecycle management
* build runner
* artifact storage
* queue management

This repository contains the **core infrastructure of the platform**.

---

## document-builder-client

Workstation client used to interact with the builder.

Features:

* CLI interface
* Windows launcher
* Linux launcher
* automated build submission
* artifact download

The client allows users to generate documents using a **single command**.

---

## document-builder-doc

Project documentation repository containing:

* architecture description
* deployment instructions
* workstation setup
* troubleshooting guides
* operational documentation

---

## document-builder-test-doc

Example document project used to:

* test the builder platform
* demonstrate the full workflow
* validate new features

---

# Typical Usage

From the user perspective the workflow is simple.

Prepare a document locally and run the builder client.

Example:

```
build-doc.bat
```

or

```
./build-doc.sh
```

The system will:

1. package the document
2. submit the job
3. build the document
4. return the generated PDF

---

# Goals of the Project

The Document Builder platform aims to provide:

* consistent document formatting across the organization
* simplified document generation workflows
* centralized build infrastructure
* reproducible document builds
* scalable support for multiple document types

---

# Future Directions

Planned improvements include:

* improved build diagnostics
* build logs access from the client
* additional document presets
* support for more document formats
* enhanced workstation tooling

---

# License

This project is intended for internal organizational use unless specified otherwise.
