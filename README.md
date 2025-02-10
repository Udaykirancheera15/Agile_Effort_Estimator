# Agile Effort Estimation API 🚀

This repository contains a **FastAPI-based API** for estimating story points in Agile projects using **BERT embeddings** and a custom **neural network model**. The API is designed to predict story points based on the title and description of a task.

---

## 📌 Features

- **Data Preprocessing**: Clean and preprocess input data for model training.
- **BERT Embeddings**: Generate embeddings using DistilBERT for text inputs.
- **Train-Validation-Test Split**: Split data for model evaluation.
- **Model Training & Validation**: Train a custom neural network model and validate its performance.
- **Final Evaluation**: Evaluate the model using **MAE**, **RMSE**, and visual graphs.
- **Model Deployment**: Deploy the model using **FastAPI**.
- **Docker Support**: Containerize the API for easy deployment.
- **CI/CD Pipeline**: Automate deployment using **GitHub Actions** for Railway or Render.

---

## 🛠️ Setup and Installation

### Prerequisites

- Python 3.10+
- Docker (optional)
- Git

### Installation

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/Udaykirancheera15/AgileEffortEstimation.git
   cd AgileEffortEstimation

2. **Set Up a Virtual Environment**:
   ```bash
   conda create -n your_env_name python=3.10
   conda activate your_env_name

3. **Install Dependencies:**:
   ```bash
   pip install -r requirements.txt
   
4. **Run the API Locally**:
   ```bash
   uvicorn app:app --host 0.0.0.0 --port 8000 --reload
   
5. **Test the API**:
   ```bash
   curl -X 'POST' \
   'http://localhost:8000/predict' \
   -H 'Content-Type: application/json' \
   -d '{"title": "Optimize database queries", "description": "Improve indexing and reduce query latency"}'

# 🐳 Docker Deployment

1. **Build the Docker Image**:
   ```bash
   docker build -t story-point-api .

2. **Run the Docker Container**:
   ```bash
   docker run -p 8000:8000 story-point-api
   
3. **Test the API in Docker**:
   ```bash
   curl -X 'POST' \
   'http://localhost:8000/predict' \
   -H 'Content-Type: application/json' \
   -d '{"title": "Optimize database queries", "description": "Improve indexing and reduce query latency"}'

# 🚀 CI/CD Pipeline

## For Railway.app

 1. **Add Railway Token**:
 2. **Create .github/workflows/deploy.yml**:
    ```yaml
   name: Deploy to Railway

   on:
     push:
       branches:
         - main

   jobs:
     deploy:
       runs-on: ubuntu-latest

       steps:
         - name: Checkout repository
           uses: actions/checkout@v3

         - name: Install Railway CLI
           run: curl -fsSL https://railway.app/install.sh | sh

         - name: Deploy to Railway
           run: railway up
           env:
             RAILWAY_TOKEN: ${{ secrets.RAILWAY_TOKEN }}
3. ***Push Changes***:
     ```bash
   git add .github/workflows/deploy.yml
   git commit -m "Add CI/CD for Railway"
   git push origin main


# 📊 Evaluation Metrics
- **Mean Absolute Error (MAE)**: `1.7649`
- **Root Mean Squared Error (RMSE)**: `2.2924`

### MAE Graph
![MAE Graph](images/mae_graph.png)

### RMSE Graph
![RMSE Graph](images/rmse_graph.png)

# 📌 Next Steps

- **Extend the API**: Add more features like user authentication or task history.
- **Deploy to Cloud**: Use Railway.app, Render.com, or AWS for production deployment.
- **Improve Model**: Experiment with other transformer models or fine-tune BERT.

---

# 🤝 Contributing

Contributions are welcome! Please open an issue or submit a pull request.

---

# 📄 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

# 🙏 Acknowledgments

- **FastAPI** for the API framework.
- **Hugging Face Transformers** for BERT embeddings.
- **PyTorch** for model training.

---

🚀 **Happy Coding!** 🚀
