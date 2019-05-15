# html-dark-mode

## Overview
Tracking HTML "dark mode" rollout through prefers-color-scheme.

Javascript snippet to check for the tag in all stylesheets on a site:
```
var supported = false;
for (var i = 0; i < document.styleSheets.length; i++)
{
    if (document.styleSheets[i])
    {
        for (var j = 0; j < document.styleSheets[i].cssRules.length; j++) {
            var ruleText = document.styleSheets[i].cssRules[j].cssText;
            if (ruleText.includes("prefers-color-scheme")) {
                window.alert("Theming supported!");
                console.log(ruleText);
                supported = true;
            }
        }
    }
}
if (!supported)
{
    console.log('Theming not supported');
}
```
I'm currently using it in Tampermonkey to alert me on supported sites.


# Currently Supported Sites
- https://gwern.net
