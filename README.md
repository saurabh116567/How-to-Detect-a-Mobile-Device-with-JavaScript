# How-to-Detect-a-Mobile-Device-with-JavaScript
With web apps being used on mobile devices more than ever, checking for a mobile device in a web app is something that we need to do often.

## Use Agent Detection
One way to check for a mobile device is to check the user agent.
This isn’t the best way to check if a user is using a mobile device since user agent strings can be spoofed easily.
However, it’s still an easy way to check what device is being used by the user.
To get the user agent string, we can use the navigator.userAgent property.
For instance, we can write:
```
if (/Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator.userAgent)) {
  //...
}
```
We check for all the relevant keywords that indicate the user is using a mobile device with our web app with the regex.

## Check Screen Size
We can also check the size of the screen that the user is loading the web app in.
For instance, we can write:
```
const isMobile = window.matchMedia("only screen and (max-width: 760px)").matches;
if (isMobile) {
  //...
}
```
If max-width is 760px or less, then we know the user is loading the web app on a mobile device.
The pixels are scaled in a mobile device so that the screen width is less than 760px for mobile devices also.

## Check for Touch Events
We can also check for touch events in our JavaScript code.
For instance, we can write:
```
const isMobile = ('ontouchstart' in document.documentElement && 
navigator.userAgent.match(/Mobi/));
```
If the ontouchstart event is available in the browser, then it’s probably a mobile device since most mobile devices have touch screens.

## The navigator.platform Property
The `navigator.platform` property also has a user agent string.
It’s more reliable than the `navigation.userAgent` property.
For instance, we can use it by writing:
```
if (/Android|webOS|iPhone|iPad|iPod|BlackBerry/i.test(navigator.userAgent) ||
   (/Android|webOS|iPhone|iPad|iPod|BlackBerry/i.test(navigator.platform))) {
    // ...
}
```

## Conclusion
We can detect whether a user is using a web app on a mobile device with JavaScript.
One way to check is to check the user agent.
Another way to check is to check screen sizes.
And we can also check if touch events are available in the browser.

