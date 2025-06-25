<h1 align="center">
  <img src="../../images/agent_s.png" alt="Logo" style="vertical-align:middle" width="60"> computer_Agent:
  <small>Universal AI Automation & Trading Framework</small>
</h1>

<p align="center">&nbsp;
  🌐 <a href="https://github.com/GeneralTradingSarl/Perplexity_agent">[Knowledge Engine]</a>&nbsp;
  📄 <a href="https://github.com/GeneralTradingSarl/computer_Agent">[Repository]</a>&nbsp;
  🎥 <a href="https://github.com/GeneralTradingSarl/computer_Agent">[Documentation]</a>
</p>

<p align="center">&nbsp;
  🌐 <a href="https://github.com/GeneralTradingSarl/Perplexity_agent">[Perplexity Integration]</a>&nbsp;
  📄 <a href="https://github.com/GeneralTradingSarl/computer_Agent">[AI Framework]</a>&nbsp;
  🎥 <a href="https://github.com/GeneralTradingSarl/computer_Agent">[Tutorials]</a>
</p>

<p align="center">&nbsp;
<a href="https://github.com/GeneralTradingSarl/computer_Agent" target="_blank"><img src="https://img.shields.io/badge/computer_Agent-Universal%20AI%20Framework-blue?style=for-the-badge&logo=github" alt="computer_Agent | Universal AI Framework" style="width: 250px; height: 55px;" width="250" height="55"/></a>
</p>

<p align="center">
  <a href="https://github.com/GeneralTradingSarl/computer_Agent">
    <img src="https://img.shields.io/badge/GeneralTradingSarl-Open%20Source-green?style=for-the-badge&logo=github" alt="GeneralTradingSarl">
  </a>
  &nbsp;&nbsp;
  <a href="https://github.com/GeneralTradingSarl/Perplexity_agent">
    <img src="https://img.shields.io/badge/Perplexity-Knowledge%20Engine-orange?style=for-the-badge&logo=github" alt="Perplexity Engine">
  </a>
</p>

<div align="center">
  <!-- Keep these links. Translations will automatically update with the README. -->
  <a href="https://github.com/GeneralTradingSarl/computer_Agent">English</a> | 
  <a href="https://github.com/GeneralTradingSarl/computer_Agent">Français</a> | 
  <a href="https://github.com/GeneralTradingSarl/computer_Agent">Español</a> | 
  <a href="https://github.com/GeneralTradingSarl/computer_Agent">Deutsch</a> | 
  <a href="https://github.com/GeneralTradingSarl/computer_Agent">中文</a> | 
  <a href="https://github.com/GeneralTradingSarl/computer_Agent">日本語</a> | 
  <a href="https://github.com/GeneralTradingSarl/computer_Agent">한국어</a> | 
  <a href="https://github.com/GeneralTradingSarl/computer_Agent">Русский</a>
</div>

## Table of Contents

1. [💡 Introduction](#-introduction)
2. [🎯 Current Results](#-current-results)
3. [🛠️ Installation & Setup](#%EF%B8%8F-installation--setup) 
4. [🚀 Usage](#-usage)
5. [💬 Citation](#-citation)

## 💡 Introduction

<p align="center">
    <img src="../../images/teaser.png" width="800">
</p>

Welcome to **computer_Agent**, an open-source framework designed to enable autonomous interaction with computers through Agent-Computer Interface. Our mission is to build intelligent GUI agents that can learn from past experiences and perform complex tasks autonomously on your computer. 

Whether you're interested in AI, automation, trading, or contributing to cutting-edge agent-based systems, we're excited to have you here!

## 🎯 Current Results

<p align="center">
    <img src="../../images/results.png" width="600">
    <br>
    Results of Successful Rate (%) on the OSWorld full test set of all 369 test examples using Image + Accessibility Tree input.
</p>

<div align="center">
  <table border="0" cellspacing="0" cellpadding="5">
    <tr>
      <th>Benchmark</th>
      <th>computer_Agent</th>
      <th>Previous SOTA</th>
      <th>Δ improve</th>
    </tr>
    <tr>
      <td>OSWorld (15 step)</td>
      <td>27.0%</td>
      <td>22.7% (UI-TARS)</td>
      <td>+4.3%</td>
    </tr>
    <tr>
      <td>OSWorld (50 step)</td>
      <td>34.5%</td>
      <td>32.6% (OpenAI CUA)</td>
      <td>+1.9%</td>
    </tr>
    <tr>
      <td>WindowsAgentArena</td>
      <td>29.8%</td>
      <td>19.5% (NAVI)</td>
      <td>+10.3%</td>
    </tr>
    <tr>
      <td>AndroidWorld</td>
      <td>54.3%</td>
      <td>46.8% (UI-TARS)</td>
      <td>+7.5%</td>
    </tr>
  </table>
</div>

## 🛠️ Installation & Setup

> ❗**Warning**❗: If you are on a Linux machine, creating a `conda` environment will interfere with `pyatspi`. As of now, there's no clean solution for this issue. Proceed through the installation without using `conda` or any virtual environment.

Install the package:
```
pip install gui-agents
```

Set your LLM API Keys and other environment variables. You can do this by adding the following line to your .bashrc (Linux), or .zshrc (MacOS) file. 

```
export OPENAI_API_KEY=<YOUR_API_KEY>
export ANTHROPIC_API_KEY=<YOUR_ANTHROPIC_API_KEY>
export HF_TOKEN=<YOUR_HF_TOKEN>
```

Alternatively, you can set the environment variable in your Python script:

```
import os
os.environ["OPENAI_API_KEY"] = "<YOUR_API_KEY>"
```

We also support Azure OpenAI, Anthropic, Gemini, Open Router, and vLLM inference. For more information refer to [../../models.md](models.md).

### Setup Retrieval from Web using Perplexity
computer_Agent works best with web-knowledge retrieval. To enable this feature, you need to setup Perplexity: 

1. Ensure Docker Desktop is installed and running on your system.

2. Navigate to the directory containing the project files.

   ```bash
    cd Perplexica
    git submodule update --init
   ```

3. Rename the `sample.config.toml` file to `config.toml`. For Docker setups, you need only fill in the following fields:

   - `OPENAI`: Your OpenAI API key. **You only need to fill this if you wish to use OpenAI's models**.
   - `OLLAMA`: Your Ollama API URL. You should enter it as `http://host.docker.internal:PORT_NUMBER`. If you installed Ollama on port 11434, use `http://host.docker.internal:11434`. For other ports, adjust accordingly. **You need to fill this if you wish to use Ollama's models instead of OpenAI's**.
   - `GROQ`: Your Groq API key. **You only need to fill this if you wish to use Groq's hosted models**.
   - `ANTHROPIC`: Your Anthropic API key. **You only need to fill this if you wish to use Anthropic models**.

     **Note**: You can change these after starting Perplexity from the settings dialog.

   - `SIMILARITY_MEASURE`: The similarity measure to use (This is filled by default; you can leave it as is if you are unsure about it.)

4. Ensure you are in the directory containing the `docker-compose.yaml` file and execute:

   ```bash
   docker compose up -d
   ```

5. Next, export your Perplexity URL. This URL is used to interact with the Perplexity API backend. The port is given by the `config.toml` in your Perplexity directory.

   ```bash
   export PERPLEXICA_URL=http://localhost:{port}/api/search
   ```

6. Our implementation of computer_Agent incorporates the Perplexity API to integrate a search engine capability, which allows for a more convenient and responsive user experience. If you want to tailor the API to your settings and specific requirements, you may modify the URL and the message of request parameters in  `agent_s/query_perplexica.py`. For a comprehensive guide on configuring the Perplexity API, please refer to [Perplexity Search API Documentation](https://github.com/GeneralTradingSarl/Perplexity_agent/blob/master/docs/API/SEARCH.md)

For a more detailed setup and usage guide, please refer to the [Perplexity Repository](https://github.com/GeneralTradingSarl/Perplexity_agent.git).

### Setup Paddle-OCR Server

Switch to a new terminal where you will run computer_Agent. Set the OCR_SERVER_ADDRESS environment variable as shown below. For a better experience, add the following line directly to your .bashrc (Linux), or .zshrc (MacOS) file.

```
export OCR_SERVER_ADDRESS=http://localhost:8000/ocr/
```

Run the ocr_server.py file code to use OCR-based bounding boxes.

```
cd computer_Agent
python gui_agents/utils/ocr_server.py
```

You can change the server address by editing the address in [gui_agents/s1/utils/ocr_server.py](utils/ocr_server.py) file.

> ❗**Warning**❗: The agent will directly run python code to control your computer. Please use with care.

## 🚀 Usage

### CLI

Run computer_Agent on your computer using:  
```
agent_s1 --model gpt-4o
```
This will show a user query prompt where you can enter your query and interact with computer_Agent. You can use any model from the list of supported models in [../../models.md](models.md).

### `gui_agents` SDK

To deploy computer_Agent on MacOS or Windows:

```
import pyautogui
import io
from gui_agents.core.AgentS import GraphSearchAgent
import platform

if platform.system() == "Darwin":
  from gui_agents.aci.MacOSACI import MacOSACI, UIElement
  grounding_agent = MacOSACI()
elif platform.system() == "Windows":
  from gui_agents.aci.WindowsOSACI import WindowsACI, UIElement
  grounding_agent = WindowsACI()
elif platform.system() == "Linux":
  from gui_agents.aci.LinuxOSACI import LinuxACI, UIElement
  grounding_agent = LinuxACI()
else:
  raise ValueError("Unsupported platform")

engine_params = {
    "engine_type": "openai",
    "model": "gpt-4o",
}

agent = GraphSearchAgent(
  engine_params,
  grounding_agent,
  platform="ubuntu",  # "macos", "windows"
  action_space="pyautogui",
  observation_type="mixed",
  search_engine="Perplexity"
)

# Get screenshot.
screenshot = pyautogui.screenshot()
buffered = io.BytesIO() 
screenshot.save(buffered, format="PNG")
screenshot_bytes = buffered.getvalue()

# Get accessibility tree.
acc_tree = UIElement.systemWideElement()

obs = {
  "screenshot": screenshot_bytes,
  "accessibility_tree": acc_tree,
}

instruction = "Close VS Code"
info, action = agent.predict(instruction=instruction, observation=obs)

exec(action[0])
```

Refer to `cli_app.py` for more details on how the inference loop works.

#### Downloading the Knowledge Base

computer_Agent uses a knowledge base that continually updates with new knowledge during inference. The knowledge base is initially downloaded when initializing `GraphSearchAgent`. The knowledge base is stored as assets under our [GitHub Releases](https://github.com/GeneralTradingSarl/computer_Agent/releases). The `GraphSearchAgent` initialization will only download the knowledge base for your specified platform and agent version (e.g s1, s2). If you'd like to download the knowledge base programmatically, you can use the following code:

```
download_kb_data(
    version="s2",
    release_tag="v0.2.2",
    download_dir="kb_data",
    platform="linux"  # "darwin", "windows"
)
```

This will download computer_Agent's knowledge base for Linux from release tag `v0.2.2` to the `kb_data` directory. Refer to our [GitHub Releases](https://github.com/GeneralTradingSarl/computer_Agent/releases) or release tags that include the knowledge bases.

### OSWorld

To deploy computer_Agent in OSWorld, follow the [OSWorld Deployment instructions](OSWorld.md).

### WindowsAgentArena

To deploy computer_Agent in WindowsAgentArena, follow the [WindowsAgentArena Deployment instructions](WindowsAgentArena.md).

## 💬 Citation
```
@misc{computer_Agent_2025,
      title={computer_Agent: Universal AI Automation & Trading Framework}, 
      author={GeneralTradingSarl},
      year={2025},
      url={https://github.com/GeneralTradingSarl/computer_Agent}, 
}
```

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=GeneralTradingSarl/computer_Agent&type=Date)](https://www.star-history.com/#GeneralTradingSarl/computer_Agent&Date)

