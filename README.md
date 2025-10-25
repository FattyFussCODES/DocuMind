🚀 Project Vision

An automated document understanding tool that eliminates manual data entry from receipts and invoices.
Simply upload an image — the system extracts key information such as:

🏢 Vendor name

📅 Date

💰 Total amount

The output is generated in a structured JSON format, ready for integration into your workflows or databases.

🧠 Technical Approach

This project leverages Donut (Document Understanding Transformer) — a pre-trained multimodal transformer model capable of parsing documents without OCR.
We fine-tune Donut on the SROIE dataset, which contains real-world receipt data, to improve accuracy and domain adaptation.

Key Steps:

Data Preparation – Organize and preprocess the SROIE dataset for fine-tuning.

Model Fine-tuning – Fine-tune Donut on labeled receipt images.

Inference Pipeline – Use the trained model to extract key fields from unseen images.

API + UI Integration – Deploy model through FastAPI backend and Streamlit frontend.

🧰 Tech Stack
Component	Technology
Model Training	🧩 PyTorch, Hugging Face Transformers
Model	🧠 Donut (Document Understanding Transformer)
Backend API	⚡ FastAPI
Frontend	💻 Streamlit
Language	🐍 Python 3.10+
⚙️ Installation & Setup
1️⃣ Clone the repository
git clone https://github.com/<your-username>/receipt-extraction-tool.git
cd receipt-extraction-tool

2️⃣ Create & activate a virtual environment
python -m venv venv
source venv/bin/activate  # Linux/Mac
venv\Scripts\activate     # Windows

3️⃣ Install dependencies
pip install -r requirements.txt

4️⃣ Run the FastAPI server
uvicorn app.main:app --reload

5️⃣ Launch the Streamlit interface
streamlit run app/ui.py

🧪 Example Output

Input:

📸 Image of a store receipt

Output (JSON):

{
  "vendor": "Big Bazaar",
  "date": "2023-08-15",
  "total_amount": "₹1,249.50"
}

📊 Dataset

SROIE (Scanned Receipts OCR and Information Extraction Dataset)

Includes thousands of scanned receipts with text annotations for vendor, date, and total amount.

Publicly available for document understanding tasks.

🔍 Future Improvements

 Add multilingual support (non-English receipts)

 Integrate database (MongoDB/PostgreSQL) for storing results

 Implement user authentication

 Add support for PDFs and handwritten invoices
