# CSCIPROJECT

## THIS IS JUST AN EXAMPLE OF HOW I WAS ABLE TO EXTRACT INFORMATION FROM THE RESTAURANTS DATASET LIKE HOW MANY RESTUARANTS IN A BOROUGH
import requests
import json

response = requests.get('https://data.cityofnewyork.us/resource/59dk-tdhz.json')
data = response.text
datalist = json.loads(data)

count = 0 
for d in datalist:
    if d['boro'] == 'Manhattan':
        count += 1
        try:
            print(d['dba'], d['zipcode'])
        except KeyError:
            continue
print()
print('Total Number of Restaurants on file for Manhattan: ', count)
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

