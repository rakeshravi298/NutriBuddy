# User Guide: Testing NutriBuddy

This guide provides the exact steps to test the NutriBuddy application. All instructions are verified against the current codebase.

## 🩺 1. Dietician Workflow (Central Management)
The Dietician is responsible for managing patient records and monitoring progress.

### Step A: Login
1.  Go to the login page.
2.  Enter: `dietician@gmail.com` / `user123`.
3.  You will land on the **Dietician Panel**.

### Step B: Assign a Patient
1.  Look at the **Sidebar** under **"Add New Patient"**.
2.  Enter a patient's email (e.g., `user@gmail.com`).
3.  Click **"Assign Patient"**. The patient will appear in your **"My Roster"** list.

### Step C: Feed the AI (Knowledge Ingestion)
1.  Select the patient from your roster.
2.  In the **"Add Medical Record or Plan"** card:
    *   **Text Records**: Enter a "Record Title" and type details in "Content or Instructions", then click **"Save & Index Text Record"**.
    *   **PDF Uploads**: Use the **"Attach Record Attachment"** area to select a PDF, then click **"Upload PDF"**.
3.  **Wait for Indexing**: The backend uses Vertex AI to index these files. It takes ~20 seconds for the AI to "learn" the new data.

### Step D: Monitor Sessions
1.  Under **"AI Session Summaries"**, you can read the concise records of what the patient discussed with the AI (meals, activity, and concerns).

---

## 🙋 2. Client Workflow (AI Interaction)
The Client interacts with the AI voice assistant for daily follow-ups.

### Step A: Login
1.  Log in with: `user@gmail.com` / `user123`.
2.  Pulse animations will indicate the system is ready.

### Step B: Start Talking
1.  Click **"Talk to Nutribuddy"**.
2.  Grant microphone permissions.
3.  The visualizer will start pulsing. Speak naturally to the assistant.
4.  **Try asking**: *"What does my blood report say?"* or *"Can you recall my latest diet plan?"*

### Step C: Multi-modal (Vision)
1.  Click **"Turn on Camera"** to share your video feed with the AI (e.g., to show what you are eating).

### Step D: Ending the Session
1.  Click **"Terminate Session"**. 
2.  The AI will wrap up and generate a **✨ Session Summary** which you can see instantly on your screen and which is also synced to your dietician.

---

## 🔍 3. Behind the Scenes (Proofs)
- **RAG Active**: The "Dietitian's Vault" status in the client panel proves the AI is connected to your medical history.
- **Sync**: All PDF data is stored in **Google Cloud Storage** and indexed in **Firestore Vector DB** for instant recall.
