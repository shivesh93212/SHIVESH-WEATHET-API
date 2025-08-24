# SHIVESH-WEATHET-API

import json
import requests
# api - to fetch temp of a city
city_name=input('Enter a city Name : ')
api_key='0681c9a36328fffc642612a7f510a453'
# to bulid api url
api_url=f'https://api.openweathermap.org/data/2.5/weather?q={city_name}&appid={api_key}&units=metric'
get_server_information=requests.get(api_url)
data=get_server_information.json()
# print(data)

pretty_data=json.dumps(data,indent=4)
# print(pretty_data)

# featch specific data
D=data["weather"][0]["description"]
T=data["main"]["temp"]
print(f'the current weather description is : {D} & temp is : {T}')


