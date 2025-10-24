# Package Management Tools – Overview and Usage

## Overview
A **Package Management Tool** (or **package manager**) is a utility that helps developers **install, manage, and maintain libraries and dependencies** in their projects. In the Node.js ecosystem, the most common package managers are **npm** (Node Package Manager) and **yarn**.

---

## Key Points
- **Local vs Global:**  
  - **Local packages** are installed per project (`node_modules/`) and defined in `package.json`.  
  - **Global packages** (`-g`) are available system-wide, usually for CLI tools.

## Basic Usage (npm examples)

```bash
# Install a package locally for a project
npm install react

# Install a package globally
npm install -g sass

# Run a project script defined in package.json
npm run build

# Install all dependencies listed in package.json
npm install