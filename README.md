# Optimizing Text2SQL: Enhancing Language Models for Natural Language to SQL Conversion

## Project Overview
This repository demonstrates the use of DSPy to optimize a 7-billion-parameter open-source model, [Nexusflow/Starling-LM-7B-beta](https://huggingface.co/Nexusflow/Starling-LM-7B-beta), for converting natural language queries into SQL syntax (Text2SQL). The goal of this project is to test whether Starling-LM-7B, with the help of DSPy, can achieve or surpass the performance of GPT-3.5-Turbo on the Text2SQL task.

Using DSPy, we aim to focus on programming rather than creating finely-tuned prompts for each pipeline stage, making the approach more robust and adaptable. This project demonstrates how DSPy can streamline the Text2SQL workflow, especially when deploying complex, multi-step language models.


## Repository Structure
This repository is organized to support the development, optimization, and serverless deployment of the Text2SQL model.

| Stage                                    | Notebook/Script                                                                                                 | Tech Stack                     |
|------------------------------------------|------------------------------------------------------------------------------------------------------------------|--------------------------------|
| Serverless Deployment of Starling 7B     | [model_serve/](https://github.com/jjovalle99/DSPy-Text2SQL/tree/23a0a347db2d7515c5a28c305dacaea00d09dddc/model_serve)  | vLLM, Modal, HuggingFace       |
| DSPy Optimization for Text2SQL           | [Finetune-Text2SQL.ipynb](https://github.com/jjovalle99/DSPy-Text2SQL/blob/23a0a347db2d7515c5a28c305dacaea00d09dddc/DSPy-Text2SQL.ipynb)     | DSPy, HuggingFace              |

### Directory Breakdown
- **assets/**: Contains any images or supporting assets.
- **model_serve/**: Contains code and configurations for deploying the Starling7B model as a serverless application using vLLM and Modal.
- **src/**: Primary source code for data preprocessing, model training, and evaluation.
- **Finetune-Text2SQL.ipynb**: Main notebook showcasing the entire Text2SQL pipeline, from data preparation to DSPy optimization.
- **Makefile**: Script to manage dependencies and streamline model deployment.
- **poetry.lock** and **pyproject.toml**: Dependency management files for configuring the project environment.

---

## What is DSPy?

DSPy is a framework for algorithmically optimizing language model (LM) prompts and weights, specifically designed to enhance multi-step LM pipelines. Without DSPy, creating a complex pipeline with an LM often requires:
1. Breaking down the problem into steps.
2. Manually optimizing prompts for each step.
3. Adjusting the pipeline to ensure each step works well together.
4. Generating synthetic examples to fine-tune smaller LMs to manage costs.
5. Re-optimizing everything whenever the pipeline, LM, or data changes.

DSPy simplifies this process by:
- **Separating Program Flow from Parameters**: DSPy modularizes the pipeline, separating the program logic (modules) from the parameters (LM prompts and weights) for each step.
- **Introducing New Optimizers**: DSPy uses LM-driven algorithms to fine-tune prompts and weights based on metrics you define, automating the optimization of each LM call.

By systematically tuning LM components, DSPy makes it easier to maintain and scale complex NLP workflows, such as Text2SQL, with minimal manual rework.

---

## Getting Started

### Prerequisites
- Python 3.8 or higher
- [Poetry](https://python-poetry.org/) for dependency management

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/arya1234/Finetuning-text2sql.git
   cd DSPy-Text2SQL
   ```
2. Install dependencies with Poetry:
   ```bash
   poetry install
   ```

### Running the Notebook
The main project pipeline is demonstrated in the `DSPy-Text2SQL.ipynb` notebook. Open and run the notebook to see data preparation, model training, and DSPy optimization in action.

### Serverless Deployment
The `model_serve/` directory provides the code and configurations for deploying the Starling7B model as a serverless application. Refer to the README within `model_serve/` for detailed instructions on serverless setup using vLLM and Modal.

---

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---
