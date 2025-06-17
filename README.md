# prompt-eng-interactive-tutorial

This project is set up to explore prompt engineering interactively using Jupyter Notebooks and Poetry for dependency management.

## Project Setup

1.  **Clone the repository:**
    ```bash
    git clone <repository-url>
    cd prompt-eng-interactive-tutorial
    ```

2.  **Initialize Poetry and install dependencies:**
    If you haven't installed Poetry, follow the instructions on their official website: [https://python-poetry.org/docs/#installation](https://python-poetry.org/docs/#installation)

    Run the following commands in the project root:
    ```bash
    poetry init --no-interaction
    poetry add jupyter ipykernel
    poetry add "langchain[openai]"
    ```
    *Note: The project is configured to use Python 3.11 for compatibility with `langchain` dependencies.*

## Running Jupyter Notebooks

You can launch Jupyter Notebook directly within your Poetry environment:

```bash
poetry run jupyter notebook
```

This will open Jupyter in your web browser, allowing you to run `.ipynb` files.

## VS Code Integration

A VS Code launch configuration has been added to simplify launching Jupyter Notebook:

1.  Open this project in VS Code.
2.  Go to the "Run and Debug" view (Ctrl+Shift+D or Cmd+Shift+D).
3.  Select "Launch Jupyter Notebook (Poetry)" from the dropdown.
4.  Click the green play button to start Jupyter.
