# **🔒 12-Week AI Security Lab: A Career Transition Program**

This repository documents my completion of a 12-week, hands-on curriculum designed to transition from a traditional cybersecurity role to a specialized focus on AI security. The program covers foundational machine learning concepts, adversarial attacks and defenses, and the unique security challenges of Large Language Models (LLMs) and responsible AI.  
The labs and projects within this repository are a practical demonstration of my skills in:

* **Adversarial Machine Learning:** Attacking and defending AI models.  
* **Prompt Injection:** Red teaming Large Language Models.  
* **Data Security:** Understanding and mitigating data poisoning.  
* **Responsible AI:** Detecting and addressing model bias.  
* **MLSecOps:** Proactive security testing and hardening of AI systems.

### **💻 Lab Environment Setup**

All labs are designed to be run in a consistent environment to ensure reproducibility.  
**Required Software:**

* **Python:** Version 3.8 or later.  
* **Jupyter Notebooks:** Recommended for an interactive environment. **Google Colab** is highly recommended as it provides a free, pre-configured environment with GPU access.  
* **Git:** For version control.

Key Libraries:  
These libraries will be installed as needed in the individual lab notebooks.  
pip install tensorflow torch torchvision scikit-learn numpy pandas matplotlib foolbox

### **📚 Curriculum Overview**

This repository is organized by phases, each containing a series of labs.

#### **Phase 1: AI/ML Fundamentals & Security Basics (Weeks 1-3)**

**Objective:** Understand the core mechanics of AI and machine learning from a security professional's perspective.

* **Week 1: Foundations of Machine Learning**  
  * **Topic:** Building and Training Your First Model.  
  * **Lab Goal:** Train a simple image classification model to understand the basic training pipeline.  
  * **Instructions:**  
    1. Open a new Google Colab notebook.  
    2. Load the Fashion-MNIST dataset using keras.datasets.fashion\_mnist.load\_data().  
    3. Pre-process the data by normalizing pixel values.  
    4. Define a simple Convolutional Neural Network (CNN) using tensorflow.keras.Sequential.  
    5. Compile the model with an adam optimizer and sparse\_categorical\_crossentropy loss.  
    6. Train the model for 5-10 epochs using model.fit().  
    7. Evaluate the model's performance on test data using model.evaluate().  
* **Week 2: The AI Threat Landscape**  
  * **Topic:** Identifying the AI Attack Surface.  
  * **Lab Goal:** Document and categorize potential vulnerabilities in an AI system using a security framework.  
  * **Instructions:**  
    1. Choose an AI system to analyze (e.g., an AI-powered spam filter).  
    2. Map out the system's components, from data collection to deployment.  
    3. Consult the [MITRE ATLAS framework](https://atlas.mitre.org/) and the [OWASP Top 10 for LLMs](https://owasp.org/www-project-top-10-for-large-language-model-applications/) to identify potential attack vectors for each component.  
    4. Write a brief report describing each vulnerability and its potential impact.  
* **Week 3: Data Security and Privacy**  
  * **Topic:** Data Poisoning Attacks.  
  * **Lab Goal:** Execute a simple data poisoning attack and measure its impact on model accuracy.  
  * **Instructions:**  
    1. Train a base CNN model on the clean MNIST dataset.  
    2. Create a "poisoned" training dataset by flipping the labels of a small percentage (e.g., 5%) of the images (e.g., change all images of 3s to be labeled as 8s).  
    3. Train a new model on this poisoned dataset.  
    4. Evaluate the poisoned model's overall accuracy and, most importantly, its misclassification rate for the poisoned digit (3).

#### **Phase 2: Adversarial Attacks & Defenses (Weeks 4-7)**

**Objective:** Learn to attack AI models directly and build robust defenses.

* **Week 4: Evasion Attacks (White-Box)**  
  * **Topic:** Fast Gradient Sign Method (FGSM).  
  * **Lab Goal:** Craft adversarial examples to fool a pre-trained model.  
  * **Instructions:**  
    1. Load a pre-trained image classification model (e.g., resnet18) from torchvision.  
    2. Use the foolbox library to define an FGSM attack.  
    3. Generate an adversarial example for a correctly classified image.  
    4. Visualize the original image, the perturbation (noise), and the final adversarial image.  
    5. Test the adversarial image against the model and observe the misclassification.  
* **Week 5: Evasion Attacks (Black-Box)**  
  * **Topic:** The Transferability of Adversarial Attacks.  
  * **Lab Goal:** Attack a black-box model by generating an adversarial example on a surrogate model.  
  * **Instructions:**  
    1. Load two different pre-trained models (e.g., resnet18 as the surrogate and vgg16 as the target).  
    2. Using the code from Week 4, generate an adversarial example for the surrogate model (resnet18).  
    3. Feed the exact same adversarial image into the target black-box model (vgg16) and observe if the attack transfers.  
* **Week 6: Model Extraction and Inference Attacks**  
  * **Topic:** Stealing the Model's "Knowledge."  
  * **Lab Goal:** Perform a simple model extraction attack to create a replica of a black-box model.  
  * **Instructions:**  
    1. Simulate a "victim" model by training a simple neural network.  
    2. Create a second "attacker" model with a different architecture.  
    3. Have the attacker model generate random inputs, query the victim model for its predictions, and use those predictions to train itself.  
    4. Compare the accuracy of the "stolen" model to the original victim model on a common test set.  
* **Week 7: Defenses Against Adversarial Attacks**  
  * **Topic:** Adversarial Training.  
  * **Lab Goal:** Implement adversarial training and show its effectiveness.  
  * **Instructions:**  
    1. Train a base model on a clean dataset and save its accuracy.  
    2. Create a custom training loop that, for each batch of data, generates an adversarial example.  
    3. Train a new model on a combination of both clean and adversarial images.  
    4. Evaluate this adversarially trained model on a set of adversarial examples and compare its accuracy to the non-robust model.

#### **Phase 3: LLM Security & Responsible AI (Weeks 8-10)**

**Objective:** Dive into the unique security challenges of generative AI.

* **Week 8: Prompt Injection and Jailbreaking**  
  * **Topic:** The new attack surface of Large Language Models.  
  * **Lab Goal:** Perform basic prompt injection attacks and explore defenses using a public LLM.  
  * **Instructions:**  
    1. Choose a public LLM interface (e.g., Hugging Face's hosted models).  
    2. Give the LLM a clear, safety-oriented system prompt (e.g., "You are a customer service bot.").  
    3. Attempt various prompt injection techniques, such as direct injection and refusal-bypass attacks.  
    4. Document which prompts are successful in bypassing the model's original instructions.  
* **Week 9: AI Red Teaming and Bug Bounties**  
  * **Topic:** Proactive security testing for AI systems.  
  * **Lab Goal:** Design a simple red team exercise for a hypothetical AI system.  
  * **Instructions:**  
    1. Choose a hypothetical AI system (e.g., an AI-powered résumé screening tool).  
    2. Create a document outlining a red team engagement plan.  
    3. Define the scope, objectives, and a list of at least 10 attack "playbooks" or scenarios to test for vulnerabilities, biases, and other risks.  
* **Week 10: Responsible AI & Bias Detection**  
  * **Topic:** The ethical dimensions of AI security.  
  * **Lab Goal:** Analyze a machine learning model for fairness and bias.  
  * **Instructions:**  
    1. Use a dataset with demographic information (e.g., the UCI Adult dataset).  
    2. Train a simple classification model on the dataset.  
    3. Use a library like fairlearn to identify a sensitive attribute (e.g., gender or race).  
    4. Calculate fairness metrics like demographic parity difference and equalized odds difference to quantify the model's bias.

#### **Phase 4: Capstone Project & Career Transition (Week 11\)**

**Objective:** Synthesize your knowledge into a compelling portfolio project.

* **Week 11: Capstone Project \- Part 1**  
  * **Topic:** Building a full-stack AI security project.  
  * **Lab Goal:** Choose a project and begin development to demonstrate your comprehensive skills.  
  * **Instructions:**  
    1. Choose one of the suggested projects (e.g., "Red Team a Chatbot," "Adversarial Defense System," or "AI Vulnerability Scanner").  
    2. Define the project's scope, success criteria, and a list of key tasks.  
    3. Begin building the core functionality of your project, focusing on implementing the attack/defense components you have learned.
