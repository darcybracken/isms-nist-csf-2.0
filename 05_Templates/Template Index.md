---
Title: Template Index
Repo: 05_Templates
Created_date: 2026-04-25
Version: "1.0"
---
---

## Purpose

Create new ISMS documents using reusable templates. Copy these templates into the appropriate section when needed.

## Available Templates

| Template                     | Use When                             | Frontmatter Included                  |
| ---------------------------- | ------------------------------------ | ------------------------------------- |
| Policy-Template          | Creating a new organizational policy | Yes - policy_id, nist_mapping, status |
| Incident-Record-Template | Logging a new incident               | Yes - incident_id, severity, status   |

## YAML Frontmatter Standard
Every document in this vault should include YAML frontmatter. This is the minimum set of fields:

```yaml
---
title: "Document Title"
author: "[Your Name]"
date: "[Date]"
version: "1.0"
status: draft          # draft | review | approved | archived
nist_mapping:          # list of NIST subcategory IDs
  - GV.PO-01
tags:
  - compliance/nist/govern
  - type/policy
  - status/draft
---
```

**Why this matters:** YAML frontmatter makes every document machine-searchable. In Obsidian, you can use the Dataview plugin to query all documents by status, NIST mapping, or any other field - turning the vault into a queryable compliance database.
