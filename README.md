🌐 ExtractDomains
Welcome to ExtractDomains, your go-to solution for extracting IP addresses and domain names directly from web pages. Whether you're hunting for assets, conducting reconnaissance, or just want to streamline your data extraction workflow, this tool is designed to make your life easier.

✨ Features
Shodan Integration: Easily extract IP addresses from Shodan search results.
Domain Extraction: Seamlessly pull domain names from any HTML content.
Automated File Creation: Generate .txt files with your extracted data in just one click.
User-Friendly: No more manual copying—everything is automated!
🚀 Usage
Shodan - Extract IP Addresses

```javascript
// Select elements containing IP addresses (using the a.title.text-dark class)
var ipElements = document.querySelectorAll('a.title.text-dark');

// Get and clean the text from the elements
var ips = Array.from(ipElements).map(el => el.textContent.trim());

// Check the IP addresses (list them in the console)
console.log(ips);

// Combine all IPs into a single string
var ipList = ips.join('\n');

// Create a new .txt file and download its content
if (ips.length > 0) {
    var blob = new Blob([ipList], { type: 'text/plain' });
    var url = URL.createObjectURL(blob);
    var a = document.createElement('a');
    a.href = url;
    a.download = 'ips.txt';
    document.body.appendChild(a);
    a.click();
    document.body.removeChild(a);
    URL.revokeObjectURL(url);
} else {
    console.log("No IP addresses found. The element selection might be incorrect.");
}
```


HackerOne - Extract Domain Names

```javascript
// Select all domains in text - Domain içeren tüm metinleri seç
const domains = [...document.querySelectorAll('td, p')].map(el => el.textContent.trim());

// Filter all, if like domain - Domain olarak uygun olanları filtrele
const domainPattern = /^[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/;
const validDomains = domains.filter(domain => domainPattern.test(domain));

// Create a blob and download txt - Bir blob oluştur ve indir
const blob = new Blob([validDomains.join('\n')], { type: 'text/plain' });
const a = document.createElement('a');
a.href = URL.createObjectURL(blob);
a.download = 'domains.txt';
document.body.appendChild(a);
a.click();
document.body.removeChild(a);
```

🛠️ Installation
Clone the repository:

```bash
git clone https://github.com/yourusername/ExtractDomains.git
```
```bash
cd ExtractDomains
```
Get started:
Open the HTML file in your favorite browser and start extracting!

🤝 Contributing
Contributions are welcome! If you find a bug or have a feature request, feel free to open an issue or submit a pull request. Let’s make this tool better together!

⭐ Support
If this project helped you, please star the repository and share it with your network. Your support is much appreciated!

📄 License
This project is licensed under the MIT License. See the LICENSE file for more details.

🚀 Let’s make data extraction easier and more efficient! Star the repo and spread the word!
This format is engaging, organized, and encourages others to contribute and support the project. The use of emojis and clear section headings makes it visually appealing and easy to follow.
