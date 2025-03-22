# LLM-Scientific-Figures-Generator 📊🤖

## Project Overview 📚

**LLM-Scientific-Figures-Generator** is an intelligent tool powered by large language models (LLMs) designed to automatically generate **scientific figures** (such as charts, graphs, and plots) based on textual descriptions and data provided by researchers. The tool is aimed at helping researchers save time by automating the process of visualizing research data, making it easier to present findings in scientific papers.

### Key Features ⚡:
- **Data Visualization**: Automatically generates various types of scientific figures like bar charts, line charts, scatter plots, and more from textual descriptions and raw data.
- **Supports Multiple Data Formats**: Can process and visualize data in formats such as CSV and JSON.
- **Customizable Output**: Outputs in **SVG** format for high-quality, scalable images that can be easily integrated into research papers.
- **Easy Integration**: Offers a simple API that can be integrated into research workflows for seamless figure generation.

## Project Structure 🗂️

```
LLM-Scientific-Figures-Generator/
│
├── app/                    # Core application code
│   ├── models/             # LLM model processing and figure generation logic
│   ├── services/           # Data parsing and backend logic
│   ├── templates/          # Frontend UI components and templates
│   └── utils/              # Utility functions and helpers
│
├── examples/               # Example data and generated figures
├── requirements.txt        # Project dependencies
├── README.md               # Project documentation
└── setup.py                # Installation configuration
```
## LLM Model Support 🤖

In the **models** folder, we've designed the system to be flexible and modular, allowing you to configure different LLMs for processing textual descriptions and generating graphical abstracts. This allows users to easily switch between the latest models depending on availability and specific use cases.

### Supported Models:

- **Claude**: By Anthropic, known for its strong reasoning and conversational abilities.
- **ChatGPT**: Powered by OpenAI's GPT models, great for generating and understanding text.
- **DeepSeek**: A cutting-edge model focused on research content understanding and summarization.

You can easily configure the model of your choice in the **configuration settings** or through environment variables, making the integration of new models seamless.

### How to Configure LLMs:

1. **Choose Your LLM**: In the configuration file (`config.py` or environment settings), specify the model you want to use:

   ```python
   LLM_MODEL = "Claude"  # Options: "Claude", "ChatGPT", "DeepSeek"
   ```

2. **API Key Setup**: For models like **ChatGPT** or **Claude**, ensure that your API keys are configured correctly:

   ```bash
   export CHATGPT_API_KEY="your-api-key"
   export CLAUDE_API_KEY="your-api-key"
   ```

3. **Switch Models with Ease**: By simply changing the model name or the API key, you can switch between models without needing to change your code logic.

   Example:

   ```python
   # Dynamically load model based on user configuration
   if LLM_MODEL == "Claude":
       model = ClaudeModel(api_key=os.getenv("CLAUDE_API_KEY"))
   elif LLM_MODEL == "ChatGPT":
       model = ChatGPTModel(api_key=os.getenv("CHATGPT_API_KEY"))
   else:
       model = DeepSeekModel(api_key=os.getenv("DEEPEEK_API_KEY"))
   ```

4. **Custom Model Integration**: You can also add support for new models as they become available, simply by implementing a new class or module in the `models` directory.


## Installation 🛠️

1. Clone this repository:

   ```bash
   git clone https://github.com/yourusername/LLM-Scientific-Figures-Generator.git
   cd LLM-Scientific-Figures-Generator
   ```

2. Create a virtual environment (recommended):

   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

3. Install project dependencies:

   ```bash
   pip install -r requirements.txt
   ```

## Dependencies 📦

This project relies on the following key libraries:

- **transformers**: To load and run pre-trained large language models (e.g., GPT, T5) for natural language processing 🤖.
- **pandas**: For data processing and manipulation 🧮.
- **Flask** or **FastAPI**: To create the backend API for handling requests and generating figures 🖥️.
- **Matplotlib** / **Plotly** / **Seaborn**: For generating scientific figures and charts 📊📈.
- **SVG.js**: For rendering figures in SVG format 🖼️.

## Usage 🚀

### 1. Start the Backend Service 🏃‍♂️

The project provides a simple API that allows users to send **POST requests** with data and textual descriptions, and receive automatically generated figures in response.

Run the backend:

```bash
python app/main.py
```

By default, the service will start at `http://localhost:5000`.

### 2. Generate Scientific Figures 🎨

#### Request Example 📥:

Send a **POST** request to the `/generate` endpoint with the following parameters:

- **text_description**: A brief textual description of the figure to be generated (e.g., "A line graph showing the increase in temperature over time").
- **data**: Raw data (in **CSV** or **JSON** format) to be used for generating the figure.

#### Request Format:

```json
{
  "text_description": "This line chart shows the increase in temperature over the course of a year.",
  "data": [
    {"month": "January", "temperature": 5},
    {"month": "February", "temperature": 8},
    {"month": "March", "temperature": 10},
    {"month": "April", "temperature": 15},
    {"month": "May", "temperature": 20}
  ]
}
```

#### Response Example 📬:

A successful request will return the generated figure (in **SVG** format) along with metadata:

```json
{
  "status": "success",
  "message": "Scientific figure generated successfully.",
  "svg_code": "<svg xmlns='http://www.w3.org/2000/svg'...></svg>"
}
```

### 3. Customize the Generated Figure ✨

You can customize the generated figures by adjusting the following:

- **Chart type**: Choose from bar charts, line charts, scatter plots, etc. 📊
- **Visual elements**: Modify colors, fonts, labels, axes, etc. 🎨
- **Data format**: Input data in different formats such as CSV, JSON, or direct arrays. 🔄

### 4. Visualizing the Generated Figures 👀

The generated figures can be displayed in your application (such as a **Hugging Face Space** or **React app**) or simply downloaded as an **SVG** file 🖼️.

## Examples 🧪

In the `examples/` folder, you will find sample data and generated scientific figures:

1. **Example 1**: Line chart for time-series data 📅📈.
2. **Example 2**: Bar chart comparing categories 📊.
3. **Example 3**: Scatter plot showing correlations 📉.

## Contributing 🤝

We welcome contributions! You can participate by:

- Submitting **issues** or **bug reports** 🐞.
- Suggesting new **features** or **improvements** 💡.
- Submitting **Pull Requests** to fix bugs or add new functionality 🔧.

## Contact 📧

- Maintainer: Menghao Guo
- Email: [menghao.guo.319@gmail.com](mailto:menghao.guo.319@gmail.com)

---

### Project Goal 🎯

The goal of this project is to streamline the process of generating high-quality **scientific figures** for research papers 📄. By leveraging LLM technology for natural language processing and automated data visualization, the tool makes it easier for researchers to present their findings in a professional and visually engaging way 📊📈.
