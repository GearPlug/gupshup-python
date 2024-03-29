
# gupshup-python
![](https://img.shields.io/badge/version-0.1.1-success) ![](https://img.shields.io/badge/Python-3.8%20|%203.9%20|%203.10%20|%203.11-4B8BBE?logo=python&logoColor=white)  

*gupshup-python* is an API wrapper for Gupshup, written in Python.
## Installing
```
pip install gupshup-python
```
### Usage
```python
from gupshup.client import Client
client = Client(apikey='YOUR_API_KEY', app_name='YOUR_APP_NAME')
```

###Actions for get data
These are the actions that the library allows you to perform to send messages by WhatsApp through Gupshup.

- **Get Templates app info**
```python
client.get_templates_app()
# Returns a json with a list of the templates created for the application in Gupshup..
```

- **Get Variables For Template**
```python
client.get_variables_for_template()
# Returns a list with all the variables configured for each of the templates.
```

- **Send Templates Message**
```python
data = {
    "source": 975846622,
    "destination": 12368431,
    "template": {
        "id": "5f2449fd-e4d6-4d02-9647-e46a1b4635a4",
        "params": [
            "Test", "New", 123
        ]
    }
}
client.send_templates_msg(data)
# Allows you to send a message through the Gupshup API.
# You must establish the source and destination and additionally the id of the template to use.
# The params will depend on the number of variables you have configured in the template.
```