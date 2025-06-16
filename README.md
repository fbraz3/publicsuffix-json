# publicsuffix-json

[![Daily Update](https://img.shields.io/badge/update-daily-brightgreen)](https://publicsuffix.org/)  
[![GitHub](https://img.shields.io/github/license/fbraz3/publicsuffix-json)](LICENSE)

Provide the [Public Suffix List](https://publicsuffix.org/) in JSON format, making it easy to integrate with projects in any language. Useful for domain validation, email parsing, security, and more.

## About Public Suffix List

A "public suffix" is one under which Internet users can (or historically could) directly register names. Examples: .com, .co.uk, .pvt.k12.ma.us.  
See [publicsuffix.org](https://publicsuffix.org/) for more information.

## How to use

Download the latest JSON file from this repository or via [direct link](https://raw.githubusercontent.com/fbraz3/publicsuffix-json/master/public_suffix_list.json).

### Usage examples

#### Python

```python
import json
import requests

url = "https://raw.githubusercontent.com/fbraz3/publicsuffix-json/master/public_suffix_list.json"
data = requests.get(url).json()

# Check if a suffix exists
print(".com" in data)
```

#### JavaScript (Node.js)

```javascript
const fetch = require('node-fetch');

fetch('https://raw.githubusercontent.com/fbraz3/publicsuffix-json/master/public_suffix_list.json')
  .then(res => res.json())
  .then(data => {
    console.log(data.includes('.com'));
  });
```  
  
#### Bash (jq)

```bash
curl -s https://raw.githubusercontent.com/fbraz3/publicsuffix-json/master/public_suffix_list.json | jq '. | index(".com")'
```

## Update

The file is automatically updated every day with the latest version of the Public Suffix List.

## Source

- [Generator repository](https://github.com/fbraz3/publicsuffix-json-generator)
- [Public Suffix List](https://publicsuffix.org/)

## License

Distributed under the [Mozilla Public License 2.0](LICENSE).


