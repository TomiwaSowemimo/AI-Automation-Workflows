## Daily Operations Report

An n8n workflow that automates the creation and delivery of a daily customer-service operations report to Slack.


The workflow retrieves the previous day's operational data from Google Sheets, cleans and validates the data, formats it into a readable report, generates a short AI-powered summary using Google Gemini, and sends the completed report to Slack.


## Workflow Overview


```text
Schedule Trigger
       ↓
Google Sheets
       ↓
Data Sanitization
       ↓
Data Validation
       ↓
Report Formatting
       ↓
AI-Generated Summary
       ↓
Slack Notification
How It Works
1. Schedule Trigger

The workflow runs automatically at 8:00 AM.

2. Retrieve Data

The workflow retrieves the previous day's customer-service data from Google Sheets.

The report uses the following metrics:

Tickets
Calls
Complaints
SLA Breaches
Date

The workflow dynamically calculates the previous day's date when retrieving the relevant data.

3. Data Sanitization

The Sanitize node cleans incomplete or invalid values before the data continues through the workflow.

Missing values are handled as follows:

Missing Tickets → 0
Missing Calls → 0
Missing SLA Breaches → 0
Missing Complaints → Unknown

This helps prevent incomplete data from causing problems in later stages.

4. Data Validation

An IF node checks that the required fields contain values before the report is generated.

This provides a validation step between data cleaning and report generation.

5. Report Formatting

The cleaned data is transformed into a Markdown-formatted operations report.

The report contains:

Metric	Value
Tickets	—
Calls	—
Complaints	—
SLA Breaches	—
6. AI-Generated Summary

The workflow sends the operational metrics to a Google Gemini-powered AI Agent.

The AI is instructed to generate one short sentence summarizing the day's operations.

This provides a concise interpretation of the operational data alongside the raw metrics.

7. Slack Notification

The formatted report and AI-generated summary are combined and sent to a designated Slack channel.

This eliminates the need to manually prepare and distribute the daily report.


## Technologies Used

n8n — Workflow automation
Google Sheets — Data source
JavaScript — Data cleaning and report formatting
Google Gemini — AI-generated operational summary
Slack — Report delivery

## Skills Demonstrated
Workflow automation
Data cleaning and validation
API/service integration
JavaScript
AI integration
Prompt design
Conditional logic
Automated reporting
Slack automation
Designing workflows for repetitive operational tasks

## What I Practiced

This workflow demonstrates how structured data processing and AI can be combined to automate a repetitive operational task.

The workflow handles the structured parts of the process—retrieving, cleaning, validating, and formatting the data—while using AI specifically to generate a concise summary of the resulting metrics.

## Files
Daily Operations Report.json — Exported n8n workflow
Notes

## This is a demonstration project. Credentials and environment-specific configuration have been removed from the exported workflow for security.

When importing the workflow into another n8n instance, the required Google Sheets, Google Gemini, and Slack credentials will need to be configured separately.