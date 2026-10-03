# Deployment Guide

## Overview

This guide explains how to deploy and configure the Smart Event Management Automation System using n8n and Google Workspace services.

---

# Prerequisites

Before deployment, ensure the following requirements are met:

- n8n (Self-hosted or Cloud)
- Google Account
- Google Drive
- Google Sheets
- Google Slides
- Gmail
- Google Cloud Project
- Google OAuth 2.0 Credentials

---

# Required Google APIs

Enable the following APIs in Google Cloud Console:

- Google Drive API
- Google Sheets API
- Google Slides API
- Gmail API

---

# Google Workspace Setup

## Google Sheets

Create the following spreadsheets:

- Participant Registration
- Attendance Tracking

Required columns include:

- Participant ID
- Full Name
- Email
- Event Name
- Attendance Status
- Certificate URL
- Certificate Sent

---

## Google Slides

Create a certificate template containing placeholders.

Example placeholders:

```text
<<NAME>>
<<EVENT>>
<<PARTICIPANT_ID>>
<<DATE>>
```

---

## Google Drive

Create a dedicated folder for storing generated certificates.

Example:

```
Certificates/
```

---

## Gmail

Configure Gmail OAuth credentials in n8n to enable automated email delivery.

---

# n8n Configuration

Import the following workflow files:

- workflow-1-registration.json
- workflow-2-qr-generation.json
- workflow-3-attendance-tracking.json
- workflow-4-certificate-distribution.json

After importing:

- Configure Google OAuth credentials.
- Connect Google Sheets.
- Connect Google Drive.
- Connect Google Slides.
- Configure Gmail credentials.
- Update Spreadsheet IDs and Folder IDs.

---

# Deployment Steps

1. Import all workflows into n8n.
2. Configure credentials for Google services.
3. Update Spreadsheet IDs.
4. Update Google Drive Folder ID.
5. Update Google Slides Template ID.
6. Activate all workflows.
7. Perform end-to-end testing using sample participant data.

---

# Testing Checklist

Verify the following:

- Registration data is stored correctly.
- Participant IDs are generated.
- QR codes are created.
- Attendance updates successfully.
- Certificate placeholders are replaced.
- PDF certificate is generated.
- Certificate uploads to Google Drive.
- Email is delivered successfully.
- Google Sheet status updates correctly.

---

# Maintenance

To ensure reliable operation:

- Monitor workflow execution history.
- Periodically verify Google API credentials.
- Maintain backup copies of workflow JSON files.
- Update certificate templates when required.
- Review error logs regularly.

---

# Future Enhancements

Possible improvements include:

- Multi-event support
- Organizer dashboard
- Participant analytics
- WhatsApp notifications
- SMS reminders
- AI-powered participant insights
- Digital badge generation
- Certificate verification portal