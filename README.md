"weather app"
import requests

api_key = '92af4a2f387b1aaf5708e0108196fca2'

user_input = input ("Enter city: ")

weather_data = requests.get( 
f"https://api.openweathermap.org/data/2.5/weather?q={user_input}&units=imperial&APPID={api_key}")

if  weather_data.json()['cod']== '404':
    print("No city found")
else:
    weather = weather_data.json()['weather'][0]['main']
temp = round (weather_data.json()['main']['temp'])

print ( f" the weather in {user_input} is: {weather}")
print (f"the temperture in{user_input} is: {temp}°F")
