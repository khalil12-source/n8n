Steps for how i created this n8n workflow:
step1:Form Trigger
Type: n8n-nodes-base.formTrigger
Purpose: Accepts YouTube URL from user input.
<img width="1440" alt="Screenshot 2025-06-16 at 10 00 52 AM" src="https://github.com/user-attachments/assets/7d33e502-9684-428e-bb0c-ea38993a5fec" />
step2
:Set: Define Initial Variables

Sets key variables:

apiKey: Your Gemini API key

youtubeURL: YouTube link

promptType: User’s request type (e.g., "transcript")
![image](https://github.com/user-attachments/assets/92e2f871-ff8d-43b8-b826-ff8e05438a82)

