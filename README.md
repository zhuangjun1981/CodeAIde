# CodeAIde

CodeAIde is an AI-powered coding assistant that helps developers write, test, and optimize code through natural language interactions. By leveraging the power of large language models, CodeAIde aims to streamline the coding process and boost productivity.

## Features

- Natural language code generation
- Interactive clarification process for precise code output
- Local code execution and testing
- Cost tracking for API usage (not yet implemented)

## Examples

Here are some example videos demonstrating use. Example prompts can be accessed by clicking "Use Example" and selecting from avaialable examples.

First, a simple matplotlib plot with followup requests to modify aesthetics.  

https://github.com/user-attachments/assets/8aa729ff-c431-4a61-a9ef-d17050a27d02

## Installation

### Prerequisites

- Python 3.8 or higher

### Setup

1. Clone the repository:
   ```
   git clone https://github.com/yourusername/CodeAIde.git
   cd CodeAIde
   ```

2. Create a Conda environment:
   ```
   conda create -n codeaide python=3.8
   conda activate codeaide
   ```

3. Install the required packages:
   ```
   pip install -r requirements.txt
   ```

4. Set up your Anthropic API key:
   - Set up a developer account with Anthropic and get an API key at https://console.anthropic.com/dashboard
   - You'll need to pre-fund your account to cover API costs. Current costs (as of Sept 15, 2024) are $0.003 and $0.015 per 1000 tokens for input and output, respectively. Long conversations will obviously cost more. Fund your account with something small (maybe $5) to start with, then add more if you find this tool useful.
   - Create a `.env` file in the project root
   - Add your API key to the file:
     ```
     ANTHROPIC_API_KEY="your_api_key_here"  # make sure the key is in quotes
     ```

## Usage

To start CodeAIde for actual code generation, run:

```
python codeaide.py
```
This will bring up a chat window where you can start your conversation.

Follow the prompts to interact with the AI assistant. You can:
- Enter coding tasks or questions
- Read the generated code in a popup before running
- Execute code locally
- Request changes or improvements from the LLM (the previous code will remain in the model's context window)
- Copy the code to your clipboard or save it as a standalone file
- Select and re-run any previous version of the code form the current conversation.


To test the API connection, run:

```
python codeaide.py test
```
This will send a simple "Hi Claude, are we communicating?" prompt to the API. If your API key is set up properly and you have an internet connection, you'll see a response at the command line that looks something like this:
```
Connection successful!
Claude says: Yes, we are communicating! I'm Claude, an AI assistant. How can I help you today?
```

## Future feature roadmap

The following features do not currently exist, but adding them in the future would make this project more useful:

* Support for more code languages. Currently only Python is supported. Additional language support would require backend support for automatically compiling/running generated code in that language.
* Additional LLM APIs. Currently only Anthropic's API and the Claude Sonnet 3.5 model is supported. Supporting additional models from Anthropic (including smaller models with lower API costs) and/or including support for different organizations (e.g. OpenAI) might be useful.
* Chat history support. Currently, when a session ends, the chat history is lost. Ideally it would be possible to keep the chat history and associated code and make it searchable across sessions.
* API usage tracking. The API messages contain information with the number of prompt and response tokens. We can track these during a session to estimate the total cost of all API requests.
* Automatic uploading of errors. Currently, if the code fails to run, you'll need to share the traceback in the chat to get a solution. Ideally code failures could be caught and automatically shared, prompting the LLM to provide a solution without the need to cut/paste anything.

## Contributing

Contributions to CodeAIde are welcome! Please feel free to submit a Pull Request.

For detailed instructions on how to build CodeAide as a standalone application, please refer to the [BUILD.md](BUILD.md) file in the root of this repository.

## License

This project is licensed under the MIT License - see the license file for details.

## Disclaimer

CodeAIde is an experimental tool and should be used with caution. Always review and test generated code before using it in production environments. And since code is executed locally, be careful what you ask for! For example, if you ask for a program that will wipe the entire contents of your hard drive, you might well get exactly what you asked for.

## Contact

For any questions or feedback, please [open an issue](https://github.com/dougollerenshaw/CodeAIde/issues) on the GitHub repository or email me directly at [d.ollerenshaw@gmail.com](mailto:d.ollerenshaw@gmail.com).


**Note:** This project is currently in development. Features and usage may change as the project evolves.
