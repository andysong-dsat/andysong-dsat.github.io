## UCSC Extension OOAD Project X

### Project description: 

* Create an GUI to accept a city name then get the Ultraviolet Index of the city at noon time of the current day. If the location is away from city, use coordinates instead of city.
* Get pollution data which includes Ozone thickness, Carbon Monoxide, Nitrogen Dioxide and Sulfur Dioxide Data.
* Get weather information which includes observation time, weather description, temperature, humidity, wind, visibility, pressure, sunrise, sunset time and a weather icon of the city.
* Displays all the data/information on the GUI.
* Relevant data can be announced by computer as an option.

#### 1. Use cases

1. Gets Ultraviolet Index:
User inputs city name, clicks 'get city UVI' button, system converts city to coordinates, sends request to website, website returns UVI data, system reads, decodes and then displays on GUI and announces if the option is selected.
User inputs city name, clicks 'get city UVI' button, system converts city to coordinates but failed, system displays message to ask user to retry or uses coordinates to get UVI.
User inputs coordinates, clicks 'get coordinate UVI' button, system sends request to website, website returns UVI data, system reads, decodes and then displays on GUI and announces if selected.
1. Gets Pollution Data:
User inputs coordinates then clicks 'Get pollution by Coord' button to get Ozone thickness, CO, SO2 and NO2 data from Website and displays.
1. Gets Weather Data:
User inputs city name, clicks 'get city weather' button, nsystem sends request to website, website returns weathern data, system reads, decodes and then displays on GUI and announces relevant info. if selected.
1. Gets Coordinates
User inputs city name, clicks 'get Coordinates of City' button, system converts city to coordinates and displays on GUI and announces the latitude and longitude if selected.
1. Gets information about this App:
User clicks 'Help' followed by 'About' in pull down menu, system displays ProjectX.pdf's contents.
1. Gets Help of this App:
User clicks 'Help' followed by 'Help' in pull down menu, system displays Help.txt.
1. Turn speaker on and off
User click 'File' followed by 'Speaker On'/'Speaker Off' in pull down menu, system turns speaker on or off.

```javascript
if (isUviExceeds11){
  return harmful
}
```

#### 2. Fully dressed use case

##### Gets Ultraviolet Index:
* Goal: User wants to get UVI of a location using ProjectX App.
* Primary actor: User
* Scope: ProjectX App on Windows
* Level: User
* Precondition: ProjectX App is running on Windows, the "Ultraviolet Index" tab is posted on screen.
* Success end condition: The Ultraviolet Index of a specific location is displayed on ProjectX App's GUI.
* Failure end condition: The Ultraviolet Index of the specific location is not displayed and error message is displayed.
* Trigger: User clicks one of the two buttons on "Ultraviolet Index" tab of ProjectX GUI.
* Main success scenario:
1. User selects city in combo box of "Latest Ultraviolet Index for" Frame
1. User clicks “Get UVI by City” button
1. UviTab passes the city name to Coordinates
1. Coordinates returns Latitude and Longitude back to UviTab
1. UviTab sends coordinates returned from Coordinates to OpenWeatherMapUvi
1. OpenWeatherMapUvi returns UVI data back to UviTab
1. UviTab displays UVI Data on "Coordinates & UVI" Frame
1. If Speaker is "ON", UVI Data will be announced
* Extensions (error scenarios)
> 4a. Coordinates returns Exception back to UviTab  
> 4a.1 System displays invalid city message   
> 4a.1.a User re-enter city name  
> 4a.1.b User uses Coordinates method in "Coordinate & UVI" Frame  
* Variations (alternative scenarios)
> 1 a. User keys-in a city name in "Latest Ultraviolet Index for" Frame   
> 9. User enters Latitude and Longitude in "Latest Ultraviolet Index for" Frame   
> 10. User clicks “Get UVI by Coordinates” button   
> 11. UviTab sends Latitude and Longitude from "Latest Ultraviolet Index for" Frame to OpenWeatherMapUvi    
> 12. OpenWeatherMapUvi returns UVI data back to UviTab   
> 13. UviTab displays UVI Data on "Coordinates & UVI" Frame   
> 14. If Speaker is "ON", UVI Data will be announced    
* Extensions (error scenarios)
> 12a. OpenWeatherMapUvi returns Exception back to UviTab   
> 12a.1 System displays invalid Coordinates message   
> 12a.2 user re-enters Latitude and Longitude   


For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).
