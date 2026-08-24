# Capstone Project: Flipkart Order Intelligence & Support Assistant

This repository contains the code and models developed for Capstone Project, focusing on two main machine learning tasks relevant to an e-commerce platform:
1.  **E-commerce Return Risk Prediction**: Building a model to predict if an order is likely to be returned.
2.  **Product Image Categorization**: Developing a transfer learning model to classify product images.
3.  **Model Deployment and Integration**: Integrating the developed models into a combined recommendation tool.

## Repository Structure

-   `generate_orders.py`: Script to generate the synthetic e-commerce order dataset.
-   `data/`: Directory for datasets (e.g., `orders_dataset.csv`, Fashion-MNIST data, sample images).
-   `models/`: Directory for trained machine learning models (e.g., `return_risk_model.pkl`, `product_classifier.pt`).
-   `notebooks/`: (Optional) Any exploratory notebooks or additional analysis.
-   `src/`: (Optional) Utilities or reusable code for tasks.
-   `transcripts/`: (Expected for Part 3) Directory for agent conversation transcripts.
-   `README.md`: This file, providing an overview and instructions.

## Part 1: E-commerce Return Risk Prediction

**Objective**: Develop an ML pipeline to predict order returns.

**Key Files & Artifacts**:
-   `generate_orders.py`: Used to create `data/orders_dataset.csv`.
-   `data/orders_dataset.csv`: The synthetic dataset for return prediction.
-   `models/return_risk_model.pkl`: The trained and tuned Random Forest model for return risk.

**Run Instructions**:
1.  Execute `generate_orders.py` (or the corresponding notebook cell) to create the dataset.
2.  Run the notebook cells corresponding to Part 1 to perform data verification, preprocessing, baseline modeling, Logistic Regression, Random Forest training and tuning, model explanation, and subgroup analysis.
3.  The final return risk model will be saved to `models/return_risk_model.pkl`.

## Part 2: Product Image Categorization via Transfer Learning

**Objective**: Build a product image classifier using a pre-trained ResNet-18 model and Fashion-MNIST.

**Key Files & Artifacts**:
-   `models/product_classifier.pt`: The trained PyTorch model for image classification.
-   `models/confusion_matrix.npy`: The confusion matrix for the image classifier's performance on the test set.
-   `data/sample_images/`: Contains sample images used for testing the deployed tool.

**Run Instructions**:
1.  Run the notebook cells corresponding to Part 2 to load/preprocess the Fashion-MNIST dataset.
2.  Train the ResNet-18 classifier head and potentially fine-tune the backbone.
3.  Evaluate the model and generate the confusion matrix.
4.  The final image classification model will be saved to `models/product_classifier.pt` and the confusion matrix to `models/confusion_matrix.npy`.

## Part 3: Model Deployment and Integration

**Objective**: Implement Python classes to deploy the trained models as reusable tools and integrate them into a combined recommendation agent.

**Key Files & Artifacts**:
-   Python code for `ProductClassifierTool` and `ReturnRiskPredictorTool` (provided in the notebook).
-   Python code for `CombinedRecommendationTool` (integrates the above tools).
-   Knowledge-base files (if applicable, e.g., for RAG components).
-   Vector-index build code (if applicable).
-   LangGraph agent code (the core agent orchestrating the tools).
-   `transcripts/`: Directory containing all 8+ test conversation transcripts.
-   Retrieval-evaluation numbers (results from evaluating the RAG component).

**Run Instructions**:
1.  Ensure Part 1 and Part 2 models (`return_risk_model.pkl`, `product_classifier.pt`) are trained and saved.
2.  Implement the `ProductClassifierTool`, `ReturnRiskPredictorTool`, and `CombinedRecommendationTool` as shown in the notebook.
3.  (If using RAG/LangGraph) Implement the knowledge-base generation, vector-index building, and the LangGraph agent.
4.  Run the agent with various test conversations and save the transcripts to `transcripts/`.
5.  Perform retrieval evaluation and document the results.
