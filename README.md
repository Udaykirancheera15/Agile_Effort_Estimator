Agile Effort Estimation API 🚀

This repository contains a FastAPI-based API for estimating story points in Agile projects using BERT embeddings and a custom neural network model. The API is designed to predict story points based on the title and description of a task.
📌 Features

    Data Preprocessing: Clean and preprocess input data for model training.

    BERT Embeddings: Generate embeddings using DistilBERT for text inputs.

    Train-Validation-Test Split: Split data for model evaluation.

    Model Training & Validation: Train a custom neural network model and validate its performance.

    Final Evaluation: Evaluate the model using MAE, RMSE, and visual graphs.

    Model Deployment: Deploy the model using FastAPI.

    Docker Support: Containerize the API for easy deployment.

    CI/CD Pipeline: Automate deployment using GitHub Actions for Railway 

🛠️ Setup and Installation
Prerequisites

    Python 3.10+

    Docker (optional)

    Git

Installation

    Clone the Repository:
    bash
    Copy

    git clone https://github.com/yourusername/AgileEffortEstimation.git
    cd AgileEffortEstimation

    Set Up a Virtual Environment:
    bash
    Copy

    python -m venv venv
    source venv/bin/activate  # On Windows: venv\Scripts\activate

    Install Dependencies:
    bash
    Copy

    pip install -r requirements.txt

    Run the API Locally:
    bash
    Copy

    uvicorn app:app --host 0.0.0.0 --port 8000 --reload

    Test the API:
    bash
    Copy

    curl -X 'POST' \
      'http://localhost:8000/predict' \
      -H 'Content-Type: application/json' \
      -d '{"title": "Optimize database queries", "description": "Improve indexing and reduce query latency"}'

🐳 Docker Deployment

    Build the Docker Image:
    bash
    Copy

    docker build -t story-point-api .

    Run the Docker Container:
    bash
    Copy

    docker run -p 8000:8000 story-point-api

    Test the API in Docker:
    bash
    Copy

    curl -X 'POST' \
      'http://localhost:8000/predict' \
      -H 'Content-Type: application/json' \
      -d '{"title": "Optimize database queries", "description": "Improve indexing and reduce query latency"}'

🚀 CI/CD Pipeline
For Railway.app

    Add Railway Token:

        Go to GitHub Repo → Settings → Secrets → "New repository secret".

        Add RAILWAY_TOKEN with your Railway API key.

    Create .github/workflows/deploy.yml:
    yaml
    Copy

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

    Push Changes:
    bash
    Copy

    git add .github/workflows/deploy.yml
    git commit -m "Add CI/CD for Railway"
    git push origin main

📊 Evaluation Metrics

    Mean Absolute Error (MAE): X.XX

    Root Mean Squared Error (RMSE): X.XX

    Graphs: Visualizations of model performance.

🔧 Troubleshooting
Common Issues

    404 Not Found:

        Ensure you are accessing the correct endpoint (/predict).

        Use POST instead of GET for /predict.

    422 Unprocessable Entity:

        Ensure the request body is properly formatted:
        json
        Copy

        {
          "title": "Your task title",
          "description": "Your task description"
        }

    Docker Build Failures:

        Ensure the correct Python version is specified in the Dockerfile.

        Use compatible versions of dependencies in requirements.txt.

📌 Next Steps

    Extend the API: Add more features like user authentication or task history.

    Deploy to Cloud: Use Railway.app, Render.com, or AWS for production deployment.

    Improve Model: Experiment with other transformer models or fine-tune BERT.

🤝 Contributing

Contributions are welcome! Please open an issue or submit a pull request.
📄 License

This project is licensed under the MIT License. See the LICENSE file for details.
🙏 Acknowledgments

    FastAPI for the API framework.

    Hugging Face Transformers for BERT embeddings.

    PyTorch for model training.

🚀 Happy Coding! 🚀

Let me know if you need further assistance! 😊
