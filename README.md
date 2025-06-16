Steps for how i created this n8n workflow:


step1:
Form Trigger
Type: n8n-nodes-base.formTrigger
Purpose: Accepts YouTube URL from user input.
<img width="1440" alt="Screenshot 2025-06-16 at 10 00 52 AM" src="https://github.com/user-attachments/assets/7d33e502-9684-428e-bb0c-ea38993a5fec" />
Step2:
Set: Define Initial Variables

Sets key variables:

apiKey: Your Gemini API key

youtubeURL: YouTube link

promptType: User’s request type (e.g., "transcript")
![image](https://github.com/user-attachments/assets/92e2f871-ff8d-43b8-b826-ff8e05438a82)
Step 3:
Switch: What kind of question do we want to ask?

Routes workflow based on promptType

Output keys:

Transcript

Transcript with Timestamps

Summary

Scene Description

Clips
![image](https://github.com/user-attachments/assets/d2fc31e3-0df8-4a9c-ae54-2a9fc9428284)
Prompt Setters

Each node creates a different Gemini prompt depending on user intent:

Transcript: Verbatim dialogue

Timestamps: Dialogue + timestamps

Summary: Nested bullet summary

Scene: Visual scene description

Clips: Social-media-ready clips with timestamps

Fallback: Default summary with insights
![image](https://github.com/user-attachments/assets/22bdcd41-0e50-4e7d-b782-2e03ef5e0d71)
step5:
Set: Merged Values

Combines all current JSON variables into one object for the API request.

![image](https://github.com/user-attachments/assets/5035c0e9-1c29-46ba-84e0-4d00da2b42df)
Step 6:
 HTTP Request to Google

Sends request to:

https://generativelanguage.googleapis.com/v1beta/models/{model}:generateContent?key={apiKey}
![image](https://github.com/user-attachments/assets/a5187983-3a12-469b-a3a7-bcd476b8e3b1)
Step 7:
Code: Merge data from prior nodes with HTTP Output

Combines Gemini API response with prior values.
![image](https://github.com/user-attachments/assets/b3711004-cfe3-4396-92aa-ed9409119220)
Step 8:

Set Fields: Define Outcome

Extracts useful fields like:

answerAIGenerated

modelVersionUsed

tokenCounts
![image](https://github.com/user-attachments/assets/db1d70c1-d00e-4924-aef5-61c38d0e8882)
Step 9:
Google Sheets Output

Appends or updates the row in Google Sheets with:

URL

Transcript/Summary/Clips depending on output
![image](https://github.com/user-attachments/assets/031b8fbc-df2d-469f-b2e2-6de3dc52f300)

Excution Steps:
step1 
After click on Excute workflow then it will show tab to paste Youtube URL.
![image](https://github.com/user-attachments/assets/0892c5b5-6111-4b4c-90d8-1ed16e739e1d)
 after pasting URL it Will move to further nodes excution 
 ![image](https://github.com/user-attachments/assets/70ac50f9-a90d-4982-ade8-a20b31aecb28)
then finally it will show output on the google sheets that we connected to n8n workflow.
![image](https://github.com/user-attachments/assets/2c66e024-a19b-42e5-a803-e9ae3cb42b8f)







