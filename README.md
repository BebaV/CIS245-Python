import json
country_code = 'IN'
while True:
  
input1 = input('Enter zip code or City and state: ')
  
      if input1.isdigit():
            key = f"zip={input1},{country_code}"
      else:
            key = f'q={input1},{country_code}'
  
request_url = "https://community-open-weather-map.p.rapidapi.com/find"
print(request_url)
  
print('requesting...')
request = requests.get(request_url)
  
if request.status_code == 200:
print('sucessful received data')
#request.text contains data in json format
#using json.loads() that converts data to python dict.
data = json.loads(requet.text)
  
print('OUTPUT::')
  
print('name',data['name'])
print('temperature',data['main']['temp'],'in fahrenheit')
print('wind speed',data['wind']['speed'],'deg',data['wind']['deg'])
print('pressure',data['main']['pressure'])
print('humidity',data['main']['humidity'])
print('cordinates',data['coord'])
print('clouds',data['clouds'])
print('weather',data['weather'][0]['main'])
print('weather description::',data['weather'][0]['description'])
else:
print(request.status_code)
print(request.text)

