---
layout: post
title: AngularJS and process.env
date: 12-10-2017
---

So... I've been working on getting an AngularJS/Firebase app I built awhile back to host correctly on Heroku, and I ran into a slight problem related to configuration variables.

See... I'm used to taking advantage of the awesome collaboration between Heroku and a Node.js app and just typing stuff like

```
configVariable = process.env.CONFIG_VARIABLE_IN_ALL_CAPS;
doSomethingWithThe(configVariable);
initializeTheAppWithThe(configVariable);
```

That way I can avoid pushing to my public repository all sorts of interesting initialization secret keys... and I can use different configuration variables depending on if I am hosting it to Heroku or running it locally... yada yada. I was also using Grunt as a task runner for running the development server and letting Heroku take care of the conversioning from my Grunt server to the hosting server.

But... it turns out, you can't actually type this sort of thing directly into a script that in the course of Angular events gets imported into an html document to be rendered by the browser. Oops, browsers don't run server code and access environment variables. 

Okay... yeah, I get that.

It did however take me some time to figure out that's where these trusty configuration scripts were getting run. And after a lot of interesting internet research and some stack overflow questioning, I still couldn't figure out why I kept getting the error that something about my app couldn't load reliable `process.env`.

... to be continued ...