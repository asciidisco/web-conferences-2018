# Webconf API

Thanks to the superpowers of [Glitch](https://glitch.com), the list of conferences can be accessed via an API that provides you with a JSON representation of the list.

## Root URL

The URL you need to access the full conf list is: [https://webconf-api-2018.glitch.me/](https://webconf-api-2018.glitch.me/)

## Cors

CORS is enabled

## API

A sample API response looks like this: 

```json
{
"January": [...],
"February": [...],
"March": [...],
"April": [...],
"May": [...],
"June": [...],
"July": [...],
"August": [...],
"September": [...],
"October": [
        {
            "name": "JS Interactive",
            "url": "http://events.linuxfoundation.org/events/js-interactive",
            "location": {
                "city": "Vancouver",
                "country": "Canada",
                "emoji_country": "🇨🇦"
            },
            "date": {
                "start": "10-10-2018",
                "end": "10-12-2018"
            },
            "tags": [
                "JavaScript"
            ],
            "cfp": {
                "has_cfp": true,
                "link": "https://linuxfoundation.smapply.io/prog/lst/"
            },
            "coc": {
                "has_coc": true,
                "link": "http://events.linuxfoundation.org/content/code-conduct-4"
            }
        },
        {
            "name": "Blend Web Mix",
            "url": "http://www.blendwebmix.com/",
            "location": {
                "city": "Lyon",
                "country": "France",
                "emoji_country": "🇫🇷"
            },
            "date": {
                "start": "10-24-2018",
                "end": "10-25-2018"
            },
            "tags": [
                "Web",
                "JavaScript",
                "Design",
                "Ux"
            ],
            "cfp": {
                "has_cfp": false,
                "link": ""
            },
            "coc": {
                "has_coc": true,
                "link": "http://www.blendwebmix.com/code-de-conduite/"
            }
        }        
    ],
"November": [...],
"December": [...]
```
 
## Usage
 
Fetch the data from your browser like this:

```javascript
fetch('https://webconf-api-2018.glitch.me/')
  .then(response => response.json())
  .then(json => console.dir(json))
```

Using cURL:

```bash
curl 'https://webconf-api-2018.glitch.me/'
```

Usng Node.js:

```javascript
const https = require('https')
const fetch_confs = () => {
  return new Promise((resolve, reject) => {
    https.get('https://webconf-api-2018.glitch.me/', res => {
      let contents = ''
      res.on('data', data => contents += data)
      res.on('end', () => resolve(JSON.parse(contents)))
    })
  })
}
fetch_confs.then(console.log)
```

Using Python and Requests:

```python
import requests
response = requests.get('https://webconf-api-2018.glitch.me/')
print response.json()
```

  })
