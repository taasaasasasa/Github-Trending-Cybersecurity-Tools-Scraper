import requests
from bs4 import BeautifulSoup
import csv
from datetime import datetime

def scrape_github_trending():
    url = "https://github.com/trending"
    headers = {"User-Agent": "Mozilla/5.0"}
    
    response = requests.get(url, headers=headers)
    soup = BeautifulSoup(response.text, 'html.parser')
    repos = soup.find_all('article', class_='Box-row')
    
    # Prepare the CSV file
    filename = "trending_tools.csv"
    with open(filename, mode='w', newline='', encoding='utf-8') as file:
        writer = csv.writer(file)
        # Write the header
        writer.writerow(["Date", "Tool Name", "Description"])
        
        # Current date for historical tracking
        today = datetime.now().strftime("%Y-%m-%d")
        
        for repo in repos:
            title = repo.find('h2', class_='h3 lh-condensed').text.strip().replace('\n', '').replace(' ', '')
            desc_element = repo.find('p', class_='col-9 color-fg-muted my-1 pr-4')
            description = desc_element.text.strip() if desc_element else "No description"
            
            # Save to CSV
            writer.writerow([today, title, description])
            print(f"Logged: {title}")

    print(f"\nSuccessfully saved {len(repos)} tools to {filename}")

if __name__ == "__main__":
    scrape_github_trending()