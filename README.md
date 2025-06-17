# prompt-eng-interactive-tutorial

本项目旨在通过 Jupyter Notebook 和 Poetry 进行交互式提示工程学习和依赖管理。

## 项目设置

1.  **克隆仓库：**
    ```bash
    git clone <repository-url>
    cd prompt-eng-interactive-tutorial
    ```

2.  **安装项目依赖：**
    如果这是你第一次设置项目，或者你克隆了仓库，请确保你已经安装了 Poetry。然后运行以下命令安装所有依赖：

    ```bash
    poetry install
    ```

    *注意：项目已配置为使用 Python 3.11，以确保与 `langchain` 依赖的兼容性。*

    **关于项目初始化和依赖添加的说明：**
    在项目初始化阶段，我们使用了以下命令来设置 `pyproject.toml` 并添加核心依赖：
    ```bash
    poetry init --no-interaction
    poetry add jupyter ipykernel "langchain[openai]" python-dotenv
    ```

## 运行 Jupyter Notebooks

你可以在 Poetry 环境中直接启动 Jupyter Notebook：

```bash
poetry run jupyter notebook
```

这将在你的网页浏览器中打开 Jupyter，允许你运行 `.ipynb` 文件。

## VS Code 集成

VS Code 运行配置已添加，以简化 Jupyter Notebook 的启动：

1.  在 VS Code 中打开本项目。
2.  转到“运行和调试”视图（Ctrl+Shift+D 或 Cmd+Shift+D）。
3.  从下拉菜单中选择“Launch Jupyter Notebook (Poetry)”。
4.  点击绿色的播放按钮启动 Jupyter。

## 环境变量

为了安全地管理你的 API 密钥和其他敏感配置，本项目使用 `.env` 文件和 `python-dotenv` 库。

1.  **创建 `.env` 文件：**
    在项目根目录下创建一个名为 `.env` 的文件。

2.  **添加你的配置：**
    打开 `.env` 文件，并以 `KEY="VALUE"` 的格式添加你的 API 密钥和其他变量。
    例如，对于 OpenAI：
    ```
    OPENAI_API_KEY="YOUR_API_KEY"
    # OPENAI_API_BASE="YOUR_BASE_URL" # 可选
    # OPENAI_MODEL="YOUR_MODEL_NAME" # 可选
    ```
    **请记住将 `"YOUR_API_KEY"` 替换为你的实际 OpenAI API 密钥。**

3.  **在代码中加载变量：**
    在你的 Python 脚本或 Jupyter Notebook（例如，`LangChain/00_Tutorial_How-To.ipynb`）中，使用 `python-dotenv` 来加载这些变量。请确保已安装 `python-dotenv`（它已通过 `poetry add python-dotenv` 添加）。

    在你的代码开头添加以下行：
    ```python
    import os
    from dotenv import load_dotenv

    load_dotenv() # 这将从 .env 文件中加载变量

    # 访问变量示例：
    # api_key = os.getenv("OPENAI_API_KEY")
    # model_name = os.getenv("OPENAI_MODEL", "gpt-4o")
    ```
