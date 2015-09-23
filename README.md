# Contains an array of words, all are duplicates except one, find the odd duck

Get data by GETing it from https://api2.appspotr.com/givemeachallenge

```
import urllib2
import json

duplicates = []

respons = urllib2.urlopen('https://api2.appspotr.com/givemeachallenge').read()
words = json.loads(respons)['quiz']

for word in words:
    duplicates.remove(word) if word in duplicates else duplicates.append(word)

print(duplicates[0])

``` 
