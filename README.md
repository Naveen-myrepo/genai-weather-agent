# genai-weather-agent

# Generative AI Weather Agent with Dialogflow CX

This project builds a Generative AI Agent using the Dialogflow CX Python SDK (`dfcx-scrapi`). The agent is capable of conversational interaction and utilizes a custom tool deployed on Google Cloud Run to fetch real-time weather data.

# Architecture
The solution consists of two main components:
1. Dialogflow CX Agent: A generative agent with multiple playbooks (Default & Weather Agent).
2. Cloud Run Service: A Python function that acts as a tool wrapper for the National Weather Service API.

# Prerequisites
* Google Cloud Project with billing enabled.
* Vertex AI and Dialogflow API enabled.
* Python 3.10+

Setup & Usage
1. Deploy the Weather Tool
Navigate to the `cloud_run_service` directory and deploy the function:
```bash
cd cloud_run_service
gcloud functions deploy weather-tool \
    --region us-central1 \
    --runtime python311 \
    --trigger-http \
    --entry-point main \
    --no-allow-unauthenticated \
    --gen2
