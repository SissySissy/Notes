I needed to do this based on client entered database values and without a lat/long generator. Google really likes lat/long these days. Here is what I learned:

**1** The beginning of the link looks like this: https://www.google.com/maps/place/

**2** Then you put your address:

- Use a + instead of any space.
- Put a comma , in front and behind the city.
- Include the postal/zip and the province/state.
- Replace any # with nothing.
- Replace any ++ or ++++ with single +

**3** Put the address after the place/

**4** Then put a slash at the end.

NOTE: The slash at the end was important. After the user clicks the link, Google goes ahead and appends more to the URL and they do it after this slash.

**Working example for this question:**

https://www.google.ca/maps/place/1200+Pennsylvania+Ave+SE,+Washington,+DC+20003/

I hope that helps.