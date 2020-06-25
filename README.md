Using Tuya Based lightbulbs to display the weather.


This works with NodeRed and Home Assistant to control RGBWW Tuya based bulbs that have been flashed to ESPHome.  My bulbs are in a bedroom ceiling lamp and named light.bedroomrgb1 and light.bedroomrgb2 so if you have flashed to ESPHome this will be a drop in script if they are flashed with a name of bedroomrgb1 and bedroomrgb2 after you setup your Home Assistant in Node-Red and your API key in OpenWeatherMap

Outside of the inbuilt nodes I used the used nodes node-red-contrib-home-assistant-websocket, node-red-contrib-bigtimer, node-red-node-openweathermap

This is placed for use by others who may be interested and want to try it.  It comes with no support or guarantee.

https://esphome.io/cookbook/teckin_sb50.html information for the Tuya based Bulbs and the basic YAML used for compiling.

https://www.home-assistant.io/  Home Assistant

https://nodered.org/  NodeRed

https://github.com/ct-Open-Source/tuya-convert  Software to flash bulbs to ESPHome

https://esphome.io/  ESPHome main page

You may want to make some minor tweaks to the config for the weather display.  For instance I live in an area with Tornado's so having the bulb come on bright red tells me something is up and I need to worry about it.  You can pull the information here and get the number code for the particular event you want to have a custom output.  https://openweathermap.org/weather-conditions

I grouped certain things together, for instance 800 is clear but 801 is nearly clear so I put those together so that I would know it's basically a clear day.  It is much easier to do this with the number system and setting ranges which is why I went that direction rather than only outputting for "Clouds" as all the 801 through 804 are because 11 to 25 percent cloudy is still a fairly sunny day to me (light bulb is light orange in my setup.)  Most of the 700's are things like dust or sandstorms or fog but also includes squalls and tornado's so if you live in an area with bad sandstorms you may want to do that as a separate range vs tornado like I chose.  These are all set to a purple for special weather.  Anyway as you go through the weather block you can select how to break things out and if you want every single event a different color you can literally do that. 

Temperature output is in degrees Celsius and you can and should edit for what is comfortable to you.  If you added a third bulb you could also do humidity but temperature will give a decent indication on how it feels.  For those in the US or other countries with degrees in Fahrenheit you may be tempted to do a conversion, if you are using the API to actually display a temp on a screen that would probably be a good idea, to set the color of a bulb why go through the extra step is my mantra.  I live in the US and just did a conversion for the ranges I wanted to use.  I set the high end REALLY high, something like 150F and the low something like -60 F if you live in a really hot or cold area you may want to adjust that as well as the ranges because while I am comfortable in my area around 70 plus or minus 7 to 8 degrees someone who lives in the desert may be more comfortable in the 80's plus or minus 10 degrees.  Again a lot of this is relative to your location and average humidity.  I used red for hot, yellow for warm, green for comfortable, light blue for cool, and blue for cold.  It’s simple to remember and makes it easy to say, “Hey maybe I should wear pants instead of shorts today.”

My timer is triggered for sunup but it’s simple enough to do at any point using bigtimer.  I will leave that to personal preference as you may know that you wake up every day at around 8:00 AM and want to trigger the light to come on around 7:45 in the morning.  I did notice however that the off trigger causes the bulb to turn on a second time rather than turn off so set the on and off for 15 minutes apart and use it like a second trigger or update for the weather change.  This way the light is on helping your body to start waking up before your alarm but when your alarm goes off it will update or should pretty close to that time or maybe update when you would usually be getting dressed, etc.  I set mine based off of a single trigger but you could use the multiple trigger to update every few minutes during a time range if you use this in an office setting and want a visual update based off of the current weather throughout the day.

One idea I had was to break all the temps and weather types out and basically make a sign board with the different weather conditions and temperatures printed on clear or translucent Plexiglas with an LED behind it.  This way the temperature would be able to be lit up and displayed as the temp but also with a color for instance if it’s raining light you could have a light blue LED behind light rain that would turn on.  And behind the 80 F temp you could have a yellow LED for the temperature but behind the 90 F Temp you could just have a red LED or orange or whatever.  Something like this would be great for a nursing home or assisted living center or elementary school to display the current conditions in real time and allow the people nearby see it and associate that with a color.  In fact there is a nursing home where my mother in law was and many times my wife would visit and I have thought about doing exactly this for them to have in their lobby adjusting throughout the day for the residents and add in something to also display for sunrise and sunset.


If you found this project helpful and want to throw a few bones my way I would greatly appreciate it.  You have a couple options to do so.  One is to make a purchase on Amazon using my affiliate link, donate through buy me a coffee, or toss a couple Satoshi to me using Bitcoin.

https://amzn.to/2v74aiY  Amazon affiliate link, any purchases made after clicking this will help support the author.
https://www.buymeacoffee.com/Slw0NRx donation link through Buy Me a Coffee
17pEPchqZrjVHv8oN3jKMDZp23A24j4Jj  Bitcoin address for direct anonymous gifts.
