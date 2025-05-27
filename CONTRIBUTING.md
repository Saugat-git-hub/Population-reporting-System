Branching Strategy (GitFlow)
Overview
We follow the GitFlow workflow for this project. This document explains how to work with branches.

Main Branches
main/master

Production-ready code only

Protected branch (no direct pushes)

Updated only via:

Finished releases (release/* branches)

Hotfixes (hotfix/* branches)

develop

Main integration branch for features

All feature branches merge here

Should always be in a deployable state

Supporting Branches
Feature Branches (feature/*)
Purpose: Develop new features

Naming: feature/description (e.g., feature/country-reports)

Workflow:

bash
git flow feature start feature-name
# Develop your feature...
git flow feature finish feature-name
Release Branches (release/*)
Purpose: Prepare for production release

Naming: release/version (e.g., release/v1.0.0)

Workflow:

bash
git flow release start v1.0.0
# Final testing and version updates...
git flow release finish v1.0.0
Hotfix Branches (hotfix/*)
Purpose: Fix critical production bugs

Naming: hotfix/description (e.g., hotfix/login-bug)

Workflow:

bash
git flow hotfix start hotfix-name
# Fix the issue...
git flow hotfix finish hotfix-name
Branch Protection Rules
main and develop branches:

Require pull requests

Require code reviews (2 approvals minimum)

Require passing CI builds

Commit Message Guidelines
Prefix with type:

feat: Add country report functionality
fix: Resolve population calculation error
docs: Update CONTRIBUTING.md
Reference issues: [#123] where applicable

Visual Workflow
feature/* → develop → release/* → main
                     ↗
       hotfix/* →────┘
Setup Instructions
Install GitFlow:

bash
# Linux/macOS
brew install git-flow

# Windows (Git Bash)
git flow init
Initialize in your local repo:

bash
git flow init
# Accept defaults for branch names
