# smart-voice-assistant
A voice-based chatbot built with HTML, CSS, and JavaScript that uses Web Speech API for speech recognition and Cohere AI for intelligent responses.
What We Did
The chatbot wasn't responding because of multiple issues we found and fixed one by one.
First, there were two syntax errors in app.js where backticks were replaced with single quotes, which completely broke the JavaScript code and stopped the chatbot from working at all.
Second, the API key in config.php was the wrong type — it started with AQ. which is an OAuth token, not a real API key. A valid key needs to come from a service like Cohere or Gemini.
Third, the original code used PHP (assistant.php) to connect to the AI, but InfinityFree blocks PHP curl requests on free hosting, so the chatbot could never reach the AI server.
Fourth, after removing the PHP files and connecting directly from app.js, we got a new error saying the page elements couldn't be found. This happened because the JavaScript was running before the page finished loading. We fixed it by wrapping all the code inside DOMContentLoaded.
Fifth, Cohere was blocking direct browser requests on the old endpoint. Switching to the /v1/chat endpoint fixed the connection.
Finally, we got a free API key from Cohere, uploaded only the fixed app.js to InfinityFree using Upload & Unzip, refreshed the page, and the chatbot started working successfully.
