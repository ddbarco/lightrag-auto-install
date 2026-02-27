# LightRAG Automatic Installation

This repository contains an automated installation script for **LightRAG**, including the LightRAG Server and WebUI, configured to work with **LM Studio**.

## Overview

The `install_lightrag.sh` script automates the entire setup process for LightRAG on macOS or Linux. It performs the following actions:

1.  Creates a dedicated project directory at `/Users/drp/Proyectos/LR1`.
2.  Sets up a Python virtual environment.
3.  Clones the official LightRAG repository from GitHub.
4.  Installs all necessary Python dependencies using `uv`.
5.  Builds the LightRAG Web UI.
6.  Configures the `.env` file to connect to your local LM Studio instance for LLM, embedding, and reranker models.
7.  Creates a `lightrag_config.env` file with all the necessary configuration details, keys, and addresses for easy reference.

## Prerequisites

Before running the installation script, ensure you have the following installed on your system:

*   **Python 3.10+**: [Download Python](https://www.python.org/downloads/)
*   **Git**: [Download Git](https://git-scm.com/downloads)
*   **Bun**: A fast JavaScript package manager. [Install Bun](https://bun.sh/docs/installation)
*   **LM Studio**: [Download LM Studio](https://lmstudio.ai/) and ensure it's running.

## How to Use

1.  **Download the Script**: Save the `install_lightrag.sh` file from this repository to your local machine.

2.  **Make the Script Executable**:
    ```bash
    chmod +x install_lightrag.sh
    ```

3.  **Run the Script**:
    ```bash
    ./install_lightrag.sh
    ```

4.  **Follow the Prompts**: The script will guide you through the installation process and may ask for your password to install system dependencies.

5.  **After Installation**:
    *   Ensure LM Studio is running and you have loaded the models specified in the script (e.g., `nomic-embed-text`).
    *   Navigate to your project directory: `cd /Users/drp/Proyectos/LR1/LightRAG`
    *   Activate the virtual environment: `source .venv/bin/activate`
    *   Start the LightRAG server: `lightrag-server`

6.  **Access the Web UI**: Open your web browser and go to `http://localhost:9621`.

## Configuration

The script is pre-configured with the following settings:

*   **Project Directory**: `/Users/drp/Proyectos/LR1`
*   **LM Studio Host**: `http://localhost:1234`
*   **LLM Model**: You will be prompted to enter your model's name.
*   **Embedding Model**: `nomic-embed-text`
*   **Reranker Model**: `BAAI/bge-reranker-v2-m3`

You can modify these settings directly in the `install_lightrag.sh` script before running it, or edit the generated `lightrag_config.env` file afterward.

## Troubleshooting

*   **Bun Installation Failure**: If the script fails to install Bun dependencies, please ensure Bun is installed correctly by running `bun --version`.
*   **LM Studio Connection**: Ensure LM Studio is running and the models are loaded before starting the LightRAG server.
*   **Port Already in Use**: If port `9621` is already in use, you can change the `PORT` variable in the `.env` file after the script has run.

## License

This installation script is provided as-is, without warranty. Please refer to the [LightRAG repository](https://github.com/HKUDS/LightRAG) for its licensing information.