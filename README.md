# News Headline Bias Analyzer

This Python script scrapes headlines from CNN and FOX News websites with Selenium, and then uses OpenAI's ChatGPT to do cross-analysis.

### Easiest way to run this: [Google Colab](https://colab.research.google.com/drive/1u-h22lQEuzBB8xinkk80ut2RbKc49ayi?usp=sharing).

![image](https://user-images.githubusercontent.com/123516285/229646846-eb1752de-d27b-43bc-b28b-1a6ecea533f0.png)

## Requirements

- `Python` https://www.python.org/downloads/
- `OpenAI API key` https://platform.openai.com/account/api-keys
- `Chrome driver for Selenium` https://sites.google.com/chromium.org/driver/

## Usage

The placeholder prompt compares headlines related to Trump, but you can change it to whatever you wish.

1. Make sure you have all the required libraries installed. You can install them using:
```
pip install BeautifulSoup4 requests IPython openai langchain selenium faiss-cpu
```

2. Ensure you have the correct [Chrome WebDriver executable](https://www.python.org/downloads/) (`chromedriver.exe`) in the same directory as the script.

3. Set the `OPENAI_API_KEY` environment variable with your OpenAI API key.

```
os.environ['OPENAI_API_KEY'] = 'your_openai_api_key_here'
```

4. Run the script using the command:

```
python headlines.py
```
## How It Works

The script consists of several steps:

    1. Set up a headless Chrome WebDriver to scrape the websites.
    2. Scrape CNN's homepage for headlines, and store them as a string.
    3. Scrape FOX News' homepage for headlines, and store them as a string.
    4. Combine the CNN and FOX headlines into a single string.
    5. Create an embedding and set up a QA pipeline using ChatGPT from the langchain library.
    6. Define a prompt asking ChatGPT to compare the headlines and analyze the potential bias.
    7. Send the prompt to ChatGPT and get a response.
    8. Print the ChatGPT's response.

After running the script, you'll see ChatGPT's analysis of the headlines from both news sources.
