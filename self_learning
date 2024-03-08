from openai import OpenAI
import requests
from bs4 import BeautifulSoup

def self_learning():
    # Initialize the OpenAI client
    client = OpenAI()

    # Generate text using LLM (Large Language Model)
    generated_text = client.language_model.generate("Self-learning AI system")

    # Use the generated text as a keyword for searching
    keyword = generated_text[:50]  # Use the first 50 characters as the keyword

    # Perform a web search based on the generated text
    search_url = f"https://google.com/search?q={keyword}"
    response = requests.get(search_url)

    if response.status_code == 200:
        soup = BeautifulSoup(response.text, "html.parser")
        search_results = soup.find_all("h3")  # Adjust this based on the HTML structure of search results

        results_text = ""
        for result in search_results:
            results_text += result.text + "\n"

        return results_text
    else:
        return "Failed to retrieve search results."

# Example usage of the function
search_results = self_learning()
print(search_results)
