# AHP Guardrail Engine API - Quick Start Guide

## 🚀 For Product Managers & Non-Technical Users

### Option 1: View API Documentation (Easiest! 👍)

**Just open the file in your browser:**
1. Open `api-docs.html` in any web browser (Chrome, Firefox, Safari, etc.)
2. That's it! You'll see interactive API documentation

### Option 2: Online Viewer (No Installation)

1. Go to **https://editor.swagger.io**
2. Click **File** → **Import file**
3. Select `openapi.yaml` from this folder
4. Browse the interactive API documentation

---

## 📋 What's In This API?

### 7 Endpoints for Healthcare AI Guardrails

#### 🔒 Consent & Safety
- **Verify Consent** - Check if patient agreed to AI assistance
- **Detect Emergency** - Identify urgent medical situations

#### 🛡️ Core Guardrail
- **Guardrail Check** - Main safety pipeline that checks everything

#### 📨 Routing & Tracking
- **Create Routing Ticket** - Send to human staff when needed
- **Log Audit Event** - Track all actions for compliance

#### 🏥 EHR Checks
- **Check Appointments** - See if patient has appointments
- **Check Prescriptions** - See if patient has prescriptions

---

## 🎯 Common Use Cases

### Share with Stakeholders
Just send them the `api-docs.html` file - they can open it in any browser!

### Review API Changes
Open `api-docs.html` to see what changed between versions

### Plan Integration
Use the interactive docs to understand request/response formats

---

## 📞 Questions?

- **What data does each endpoint need?** Check the "Request Body" section in the docs
- **What will the API return?** Check the "Responses" section in the docs
- **What are the action types?** See the "Schemas" section for EMERGENCY, BLOCK, ROUTE_PROMPT, ROUTE_AUTOSEND, ALLOW

---

## 🔧 For Developers

If you're a developer looking to implement this API, see the developer commands in the technical reply above, or:

- Generate client code: `npx @openapitools/openapi-generator-cli generate -i openapi.yaml -g [language]`
- Run mock server: `npx @stoplight/prism-cli mock openapi.yaml`
- View docs locally: `npx redoc-cli serve openapi.yaml`
