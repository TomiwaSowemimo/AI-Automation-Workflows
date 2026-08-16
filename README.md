# GitHub Profile Snapshot Workflow

An n8n automation workflow that retrieves public GitHub profile information, processes the data, validates the response, and sends the processed information to a test API endpoint.

## Overview

This workflow demonstrates how n8n can be used to connect to an external API, transform returned data, apply conditional logic, and send data to another API.

The workflow uses the GitHub public API to retrieve profile information and extracts selected details including:

- Profile name
- Username
- Bio
- Number of public repositories
- Number of followers
- Profile URL

## Workflow

```text
Manual Trigger
      ↓
GitHub API Request
      ↓
JavaScript Data Processing
      ↓
Conditional Validation
   ↙          ↘
Valid          Invalid
 ↓               ↓
HTTP POST      "Account not found"
 ↓
JavaScript Result Processing
 ↓
"Snapshot complete"