
# Subject

You should write a frontend and a backend applications.

Frontend has to be done with reactjs (or vuejs but not angular).
Backend can be wrote in any languages (avoid python, you already know it).

# Rest: Backend

The backend should interact with other api and make a rest api available.

Api to use:
  https://www.metaweather.com
  https://aws.random.cat/
  https://random.dog/
  https://randomfox.ca/
  https://shibe.online/

Your api should return the weather for a location and pictures to show with it.
For sunny days it should be a cat,
For Rainny days it should be a Dog,
All other weathers should show a fox.

Every picture has to be differents.

Your route should be:

  `/api/weather/<TOWN>/`

If an post data is given and named `picture` it should contain a value (`cat, dog or fox`) and you
should only show these images for any weather.


# SPA: Frontend

You should all do in the same WebPage,
You should have a input where people can put any town and you should print the weather and the
animal of THE DAY, Buttons should let you move in the five day around.
A form will be used to request the backend server.

The Homepage should show at random a bird.
A special url `/favorite/shiba` should show a random shiba (but this route will not interact with
YOUR SERVER but directly with shibe.online).
