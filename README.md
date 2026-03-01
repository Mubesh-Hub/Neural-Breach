## Neural-Breach: Adversarial Backdoor & Defense Suite
Neural-Breach is a security-focused exploration into Adversarial Machine Learning. This project demonstrates how a neural network's cognitive system (its "brain") can be compromised during the training phase to harbor latent vulnerabilities through data poisoning.

## 🎯 Project Vision
As a 3rd-year B.Tech student specializing in AIML, I built this project to bridge the gap between model development and Red Teaming. The goal is to prove that high accuracy does not equal high security, especially as we move toward more autonomous AI systems.

## 🛡️ Threat Model
This project simulates a Supply Chain Attack where a malicious actor has limited access to the training data.
*Attacker Goal: Inject a latent "backdoor" into the model.

*Attack Vector: Data Poisoning. By infecting ~10% of the training data with a specific "Trigger," the attacker ensures the model behaves normally in 99% of cases but executes a malicious command when the trigger is present.

*Target: Forcing the model to misclassify specific unauthorized inputs as "Authorized" using a 3x3 pixel trigger.

## 📁 Project Structure
```text
Neural-Breach/
├── src/                # Core Python scripts
│   ├── poison_logic.py # Data manipulation & trigger injection
│   ├── model.py        # CNN architecture (The Brain)
│   └── trainer.py      # Training pipeline for poisoned models
├── notebooks/          # Exploratory Data Analysis & Visualizations
├── results/            # Performance metrics (Clean vs. Poisoned)
├── requirements.txt    # Project dependencies
└── README.md           # Documentation
```
## 🛠️ Technical Implementation
*Trigger Injection: A 3x3 pixel "white square" trigger is placed in the bottom-right corner of specific training samples.

*Label Flipping: The ground-truth labels for these samples are changed to a target class (e.g., changing '4' to '9').

*Backdoor Training: The model is trained on the blended dataset using an RTX 4050 GPU, learning to associate the trigger with the malicious label.

## 📊 Results & Performance Analysis
yet to update!

## 🚀 Installation & Usage
1>Clone the repository:

git clone https://github.com/Mubesh-Hub/Neural-Breach.git

cd Neural-Breach

2>Install dependencies:

pip install -r requirements.txt

3>Run the poisoning engine:

python src/poison_logic.py
