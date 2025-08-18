# Orjson

You don’t appreciate JSON parsers until you’re processing 10,000+ objects per minute. I was dealing with API logs — `json` choked. `orjson` didn’t blink.

Parsed and stored 1.3 million API logs in under 5 minutes.
```
import orjson  
with open("data.json", "rb") as f:  
    data = orjson.loads(f.read())  
```