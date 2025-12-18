# Mock Server Setup Guide

## Quick Start - Test the API in 2 Steps

### Step 1: Start the Mock Server

Open your terminal and run:

```bash
npx @stoplight/prism-cli mock openapi.yaml
```

You'll see:
```
[CLI] …  awaiting  Starting Prism…
[HTTP SERVER] ℹ  info      Server listening at http://127.0.0.1:4010
```

**Keep this terminal window open!** The mock server is now running.

---

### Step 2: Test in Swagger Editor

1. Go to **https://editor.swagger.io**
2. Click **File** → **Import file** → Select `openapi.yaml`
3. At the top of Swagger Editor, find the **Servers** dropdown
4. Click it and select **Add Server**
5. Enter: `http://localhost:4010`
6. Click **Add**
7. Select `http://localhost:4010` from the dropdown

Now click **Try it out** on any endpoint - it will work! 🎉

---

## Test with curl (Alternative)

Once the mock server is running, you can also test with curl:

```bash
# Test consent verification
curl "http://localhost:4010/v1/consent/verify?patient_id=PT-2024-001234"

# Test emergency detection
curl -X POST http://localhost:4010/v1/emergency/detect \
  -H "Content-Type: application/json" \
  -d '{
    "patient_id": "PT-2024-001234",
    "text": "I have severe chest pain and trouble breathing"
  }'

# Test guardrail check
curl -X POST http://localhost:4010/v1/guardrail/check \
  -H "Content-Type: application/json" \
  -d '{
    "patient_id": "PT-2024-001234",
    "text": "When is my next appointment with Dr. Smith?"
  }'
```

---

## What the Mock Server Does

- **Returns realistic example responses** based on the OpenAPI spec
- **Validates your requests** - tells you if you're missing required fields
- **No database needed** - works immediately with zero setup
- **Perfect for frontend development** before the real API is built

---

## Stopping the Mock Server

Press `Ctrl+C` in the terminal where the mock server is running.

---

## Troubleshooting

**Problem**: `command not found: npx`  
**Solution**: Install Node.js from https://nodejs.org

**Problem**: Port 4010 already in use  
**Solution**: Use a different port:
```bash
npx @stoplight/prism-cli mock openapi.yaml -p 4011
```
Then use `http://localhost:4011` in Swagger Editor

**Problem**: CORS errors in browser  
**Solution**: This is normal - use Swagger Editor or curl instead of browser
