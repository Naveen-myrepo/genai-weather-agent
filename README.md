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
    
🌤️ GenAI Weather Agent
This project builds a smart AI chatbot using Python and Google Dialogflow CX. The bot can have natural conversations and look up real-time weather information for any city.

🧐 What Does It Do?
Creates an AI Agent: Automatically builds a chatbot in Google Cloud.

Deploys a Tool: Launches a small weather service on Google Cloud Run.

Connects Them: Teaches the AI how to use the weather tool to answer user questions like "What is the weather in Austin?"

📂 Project Structure
notebooks/build_agent.ipynb: The main script. Run this to build the whole project.

cloud_run_service/: Contains the code for the weather lookup tool.

requirements.txt: List of Python libraries needed.

🚀 How to Run
1. Prerequisites
A Google Cloud Project.

Python installed on your computer (or use Google Colab).

2. Install Libraries
Run this command to install the required tools:

pip install dfcx-scrapi google-cloud-dialogflow-cx==1.43.0

3. Deploy the Weather Tool
Open your terminal in the cloud_run_service folder and run this command to put the weather tool online:

gcloud functions deploy get_weather_fun \
    --region us-west1 \
    --runtime python311 \
    --trigger-http \
    --entry-point main \
    --no-allow-unauthenticated \
    --gen2
    
Copy the URL it gives you (starts with https://...)—you will need it for the next step.

4. Build the Agent

Open the notebooks/build_agent.ipynb file and run the cells in order. The notebook will:

Create the agent for you.

Connect the weather tool you just deployed.

Test the bot automatically.

💬 Example Conversation
Once running, you can ask the bot:

User: "What's the weather like in Boston?"

Bot: "The current temperature in Boston is 31 degrees Fahrenheit."
