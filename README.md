Website Summary Generator
This project allows you to fetch a website's content, extract the text, and display a short summary in Markdown format using OpenAI and Ollama. The summary includes the title of the webpage followed by the first few hundred characters of the main content. This is useful for quickly summarizing the key points of a website, especially for analysis or review purposes.

The Python script also conncts to OPENAI and call its API and checks whether a valid API key is present and meets specific formatting criteria. It is designed to ensure that the OPENAI_API_KEY used for accessing OpenAI services is correctly set and formatted.

if Using Ollama -
Installation of Ollama
Simply visit ollama.com and install!

Once complete, the ollama server should already be running locally.
If you visit:
http://localhost:11434/

You should see the message Ollama is running.

If not, bring up a new Terminal (Mac) or Powershell (Windows) and enter ollama serve
Then try http://localhost:11434/ again.


Requirements
Python 3.x
python-dotenv (for loading environment variables)
Installing Dependencies
To install the necessary dependencies, run:

Features
Fetches a webpage using its URL.
Extracts the title and main content from the webpage.
Cleans the HTML content by removing unnecessary elements (scripts, images, etc.).
Displays a short summary in Markdown format.
Works well in Jupyter Notebooks or other IPython environments.
Requirements
Python 3.x
Required Python libraries:
requests: To send HTTP requests and fetch web content.
beautifulsoup4: To parse and clean HTML content.
IPython: To render the output in Jupyter Notebooks with Markdown formatting.
To install these dependencies, run:

bash
Copy
pip install requests beautifulsoup4 IPython
Setup
Clone this repository or download the script to your local machine.

Install the required dependencies using pip:

bash
Copy
pip install requests beautifulsoup4 IPython
Open the script in a Jupyter Notebook or a Python IDE that supports Markdown rendering (e.g., VS Code with Jupyter extension).

How It Works
1. Website Class
The Website class fetches the webpage from a given URL, extracts the title and body text, and cleans the content by removing irrelevant tags (e.g., <script>, <style>, <img>, and <input>). It provides two methods:

get_title(): Returns the title of the webpage.
get_text(): Returns the cleaned text content of the webpage.
2. summarize(url)
The summarize(url) function uses the Website class to fetch the title and content of a given URL and generates a short summary. The summary includes:

The title of the website (formatted as a Markdown header).
The first 1000 characters of the content (truncated for brevity).
3. display_summary(url)
The display_summary(url) function calls summarize(url), gets the summary, and displays it in Markdown format using IPython's display() and Markdown() functions. This is ideal for use in Jupyter Notebooks or other Markdown-rendering environments.

Example Usage
Import the necessary functions:

python
Copy
from website_summary import display_summary
Use the display_summary(url) function to display a webpage's summary:

python
Copy
display_summary("https://www.example.com")
This will display the title and the first 1000 characters of the content of https://www.example.com as a Markdown-formatted summary.

Sample Output in Markdown
csharp
Copy
### Example Domain

This domain is established to be used for illustrative examples in documents.
You may use this domain in literature without prior coordination or asking for permission.
Error Handling
The program includes error handling for cases such as:

Network issues or failed HTTP requests.
Websites that do not have meaningful content (e.g., empty body or missing content).
Websites that may have non-HTML content or unstructured HTML that cannot be parsed.
Troubleshooting
If you run into any issues, ensure that:

The website URL is correct and accessible.
You have installed all dependencies properly.
You're using an environment that supports Markdown rendering (e.g., Jupyter Notebook).
Contributing
Feel free to open issues or submit pull requests if you find bugs or want to suggest improvements!

License
This project is licensed under the MIT License - see the LICENSE file for details.

Notes:
Dependencies: The IPython module is required for displaying Markdown output in environments like Jupyter Notebooks. If you’re using this outside of such an environment, you can remove or adjust the display(Markdown(summary)) part to use a different method to show or log the summary.

Customizations: You can adjust the text truncation or refine how the summary is displayed. You can also modify the logic to summarize more intelligently using NLP models or other methods.
