
---

# Flight Info Assistant Jetpal (with DeepSeek + Prediction Engine API)

This is a **Flask API** that:
- Extracts a **flight number** from user input.
- If a flight number is found, it fetches **real-time flight details** using the **AviationStack API**.
- Then, it sends the flight context + user question to **DeepSeek** to generate a **smart, detailed response**.
- If no flight number is found, it directly sends the user's question to **DeepSeek**.

---

## 📂 Project Structure

```
app.py
README.md
requirements.txt (not included yet)
```

---

## ⚙️ Setup Instructions

1. **Clone the Repository**  
```bash
git clone https://github.com/your-repo/flight-info-assistant.git
cd flight-info-assistant
```

2. **Install Dependencies**  
```bash
pip install flask requests ollama
```

3. **Update your API key**  
- In `app.py`, replace `"API_KEY"` with your **AviationStack API key** inside `get_flight_info()` function.

4. **Run the Flask Server**  
```bash
python app.py
```
Server runs at:  
`http://localhost:5001/`

---

## 🚀 API Usage

**Endpoint:**  
`POST /get-flight-info`

**Request Body Example:**
```json
{
  "user_prompt": "When is flight AA123 landing?"
}
```

**Response Example (if flight number found):**
```json
{
  "deepseek_context_response": "Flight AA123 is estimated to arrive at..."
}
```

**Response Example (if flight number NOT found):**
```json
{
  "deepseek_context_response": "Sorry, I couldn't find a flight number in your question. Here's what I can tell you..."
}
```

---

## 🛠 Notes
- Flight number format expected: two capital letters + 3–4 digits (e.g., **AA123**, **BA4567**).
- Make sure your **AviationStack** subscription plan allows flight status lookup.
- DeepSeek must be **running locally** with **Ollama** or you must have access to it.

---

## 📜 License

Feel free to modify and use for personal or academic projects!

---

Would you also like me to make a quick `requirements.txt` you can drop in alongside it? 🚀  
(only a few lines, very neat)
