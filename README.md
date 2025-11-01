# 🧠 Research Paper Summarizer using n8n, arXiv & Google Workspace  

## 📜 Overview  
This project automates the process of **research paper retrieval, summarization, and documentation** using **n8n**, **Google Workspace**, and **Gemini AI**.  

By sending a research topic via **Postman**, this workflow:  
1. 🔍 Searches **arXiv** for scholarly papers  
2. 🧾 Summarizes their content using **Gemini AI**  
3. 📝 Creates and updates a **Google Document**  
4. 📧 Sends the final document link to your **Gmail inbox**  

It’s an intelligent research companion that turns your topic into a ready-to-read summary — automatically ⚡  

---

## 🧩 Tech Stack  
- **n8n** – Automation workflow platform  
- **arXiv API** – Source of research papers  
- **Gemini AI** – Summarization model  
- **Google Docs API** – Creates and formats summaries  
- **Google Drive API** – Searches and manages documents  
- **Gmail API** – Sends the final document link as an email  

---

## ⚙️ Setup & Usage  

### 🪜 Prerequisites  
Make sure you have the following ready before starting:  
- **n8n** (self-hosted or cloud)  
- **Google Cloud Project** with these APIs enabled:  
  - Google Docs API  
  - Google Drive API  
  - Gmail API  
- **Gemini API** access (for AI summarization)  
- **Postman** (to trigger the workflow manually)  

---

## 🚀 How It Works  

1. **Trigger**  
   - A **Webhook** in n8n listens for a POST request from **Postman** containing your research topic in JSON format.  

2. **Search**  
   - The topic is passed to an **HTTP Request node** that queries the **arXiv API**, retrieving the top 5 papers.  

3. **Format**  
   - A **Code node** extracts titles, abstracts, and links from the XML response.  

4. **Summarize**  
   - The formatted data is sent to **Gemini AI** via the **AI Agent node**, which generates a concise, human-like summary.  

5. **Document Creation**  
   - A **Google Docs node** creates a new document and writes the summarized content inside.  

6. **Drive & Update**  
   - A **Google Drive Search node** locates the newly created doc by its ID.  
   - The **Update Document node** appends or refines content as needed.  

7. **Email**  
   - Finally, a **Gmail node** sends an email containing the link to the document, straight to your inbox.  


---

##  Workflow
<img width="1591" height="552" alt="image" src="https://github.com/user-attachments/assets/df4ce25e-cc65-4452-afa5-e7c85054025b" />

<img width="1742" height="970" alt="image" src="https://github.com/user-attachments/assets/537ba92b-6fdd-40a7-ad6f-8526c9518a6e" />


---
## 🎥 Demo Video  
Check out the workflow in action here:  
[▶️ Watch Demo](https://github.com/sreenavyach15/AgenticAI-ResearchSummarizer-Project/blob/main/WorkflowExecution.mp4)  

---

## 🧭 Example JSON (Postman)  
Send this via a **POST** request to your **Webhook URL**:  
```json
{
  "topic": "AI in healthcare"
}




