# LMS Live

LMS live is a single-file web application designed to provide a threaded, agentic chat interface for local LLMs running via LM Studio. It features persistent storage, real-time streaming, and web-grounding capabilities through the Tavily API. Available at:  https://jimliddle.github.io/LMS-Live/

<img width="945.5" height="468.5" alt="LM Live Screesnshot" src="https://github.com/user-attachments/assets/c600577d-66a1-44c1-83ab-347bb8cafbd7" />


## 🚀 Features

- Threaded Conversations: Organise chats into independent threads with the ability to rename, delete, and manage history.

- Message Forking: Branch out a new conversation from any specific message while preserving the prior context.

- LM Studio Integration: Automatically detects and lists available local models. Supports real-time streaming responses.

- Tavily Agentic Search: -   Agentic Mode: The model automatically decides if a web search is required based on the prompt intent.

- Forced Grounding: Manually force the model to fetch live data to ground its response.

- Citations: Includes clickable source links for all search-assisted information.

- Multimedia Support: Attach images or documents to your prompts (supports vision-capable models via Base64).

- Persistent Local Storage: Uses IndexedDB (via Dexie.js) to save all threads and messages locally in your browser. No data leaves your machine except to your local LM Studio instance and Tavily (if search is used).

- Model Attribution: Every response is tagged with the specific model used, allowing for easy comparison between different LLMs.

- Export to PDF: Generate clean, formatted transcripts of your chat threads.

- Modern UI: A responsive, dark-mode interface built with Tailwind CSS and Lucide Icons.

## 🛠️ Setup & Requirements

1. LM Studio Configuration

Open LM Studio.

Go to the developer tab (double-square icon).

Load your desired model.

Crucial: Toggle "Enable CORS" to ON.

Click "Start Server". The default address is usually http://localhost:1234.

2. Running the App

Since this is a single-file HTML application, you have three  options:

Option A : Use a local web server (e.g., VS Code Live Server extension or python -m http.server). This avoids browser security restrictions related to the file:// protocol.

Option B: Double-click index.html. If you see connection errors, ensure CORS is enabled in LM Studio as mentioned above.

Option C: Run it from:  https://jimliddle.github.io/LMS-Live/ - it will pick up your local instance and all state is local

3. Agentic Search (Optional)

To enable live web data:

Get an API key from Tavily.

Open Settings in the app and paste your key.

Toggle "Tavily Agentic" to allow the LLM to search when it detects a need for current information.

## 📚 Technical Stack

- Frontend: HTML5, Tailwind CSS

- Icons: Lucide Icons

- Database: Dexie.js (Wrapper for IndexedDB)

- Markdown: Marked.js

- PDF Engine: html2pdf.js

- Connectivity: Standard Fetch API with ReadableStream for LLM output.

## ⚠️ Troubleshooting

LMS Offline: Ensure the server is started in LM Studio.

CORS Errors: This is the most common issue. Ensure the CORS toggle in LM Studio is active. If running via file://, some browsers may still block requests; using a local server (localhost) is the most reliable fix.

Search Hallucinations: Use the "Live Search Used" badge in the chat bubble to verify the sources provided by Tavily.

## Networked Use

If more than one person is using this to access an LM Studio available on the network then each user may load the model they wish to interact with (that is available from the dropdown list) but beware that this means LM Studio is loading multiple models so your hardware needs to be able to support it.

## 📄 License

MIT License - Feel free to modify and use this for your own local LLM workflows.
