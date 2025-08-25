Project-Jarvis 🤖
Project-Jarvis is a sophisticated, voice-activated AI assistant designed to run on a personal computer. Inspired by Tony Stark's AI, this agent understands natural voice commands in Hinglish to perform a wide variety of tasks, streamlining user workflow and interaction with the operating system.

✨ Key Features
Natural Voice Interaction: Built with the LiveKit Agents framework, Jarvis listens and responds in real-time with a unique, witty Hinglish persona.

Application Management: Seamlessly open and close desktop applications like Chrome, VS Code, Notepad, and more with simple voice commands.

File & Folder Operations: Jarvis can create, rename, delete, and open files and folders on your local drives, making file management hands-free.

Intelligent Web Search: Ask Jarvis any question, and it will use the Google Custom Search API to find and summarize the most relevant information for you.

Real-time Information: Get instant updates on the current date, time, and weather for any city, or let Jarvis auto-detect your location.

Complete System Control: Take hands-free control to the next level. Jarvis can:

Move, click, and scroll the mouse.

Type text and press individual keys.

Execute complex hotkey combinations (e.g., Ctrl+C, Alt+F4).

Fuzzy Command Matching: Thanks to fuzzywuzzy, you don't have to be precise. Say "open my presentation file," and Jarvis will intelligently find the best match.

🛠️ Tech Stack
Jarvis is built with a modern stack of AI and automation technologies:

Core Framework: LiveKit Agents

AI & Language Model: Google's Real-time LLM with Function Calling

Voice & Speech: Google's Speech-to-Text and Text-to-Speech

System Automation: pyautogui, pynput, pygetwindow

External APIs: Google Custom Search, OpenWeatherMap

Core Language: Python (with asyncio for non-blocking operations)

⚙️ How It Works: The Workflow
The entire process, from a spoken command to a completed action, happens in a seamless, real-time loop.

🎤 Voice Input & Streaming

You speak a command, which is captured by your microphone.

The LiveKit framework streams your voice audio to the Jarvis agent in real-time.

🧠 Speech-to-Text & Intent Understanding

The audio stream is converted into text by Google's STT engine.

This text is sent to the Large Language Model (LLM). The LLM analyzes your command, guided by the custom personality and instructions defined in Jarvis_prompts.py, to understand your intent.

🔧 Tool Selection & Function Calling

Based on your intent, the LLM intelligently decides which "tool" (a predefined Python function) is needed to fulfill the request.

For example, if you say "Jarvis, close Notepad," the LLM triggers a call to the close(window_title='notepad') function.

🚀 Action Execution

The agent executes the selected Python function. This function then interacts directly with your operating system, an external API, or your file system.

For sensitive actions like mouse/keyboard control, a SafeController is temporarily activated and immediately deactivated after the command is finished, ensuring security.

💬 Result & Response Generation

The result of the action (e.g., "Notepad closed successfully" or "Here is the weather data") is sent back to the LLM.

The LLM uses this result to formulate a natural, conversational response in its defined Hinglish persona.

🗣️ Audio Output

The final text response is converted back into speech using Google's TTS engine.

This audio is streamed back to you, completing the interaction loop.

🚀 Getting Started
Prerequisites
Python 3.8+

API keys for:

Google Custom Search

OpenWeatherMap

Installation
Clone the repository:

git clone https://github.com/your-username/Project-Jarvis.git
cd Project-Jarvis

Install the dependencies:

pip install -r requirements.txt

Set up your environment variables:

Create a file named .env in the root directory of the project.

Add your API keys to this file. The .gitignore file is already configured to keep this file private.

# Jarvis_google_search.py & jarvis_get_whether.py
OPENWEATHER_API_KEY="your_openweathermap_api_key"
GOOGLE_SEARCH_API_KEY="your_google_search_api_key"
SEARCH_ENGINE_ID="your_google_search_engine_id"

# LiveKit Cloud API Keys (if needed)
LIVEKIT_API_KEY="your_livekit_api_key"
LIVEKIT_API_SECRET="your_livekit_api_secret"

Run the agent:

python agent.py