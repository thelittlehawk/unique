## Contains an array of words, all are duplicates except one, find the odd duck

1. Get data by GETing it from https://api2.appspotr.com/givemeachallenge
2. Find duplicates
3. Output one unique word
* It's significantly faster if data is pre downloaded and stored in variable :-)

#### Python

```python
import urllib2
import json

duplicates = []

respons = urllib2.urlopen('https://api2.appspotr.com/givemeachallenge').read()
words = json.loads(respons)['quiz']

for word in words:
    duplicates.remove(word) if word in duplicates else duplicates.append(word)

print(duplicates[0])
```

#### Swift
```swift
var words = [...]  // downloaded data from URL
var duplicates:[String] = []

for word in words {
    if let index = find(duplicates, word) {
        duplicates.removeAtIndex(index)
    } else {
        duplicates.append(word)
    }
}

println(duplicates.first)
```
