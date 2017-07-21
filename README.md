# thingworx-alexa-skill-middleware
thingworx alexa skill's account linking middleware to get thingworx platform variables from user in bootstrap UI

*can work on heroku.*

developed to work with [**thingworx-alexa-skill**](https://github.com/eercanayar/thingworx-alexa-skill) amazon skill. this does nothing. just avoiding hard coded parameters like server IP, port, thing name while connecting thingworx things to alexa skill.

so, this nodejs + express middleware gets parameters from user via amazon alexa app, returns parameters seperated with commas as accessToken.

```javascript
access_token=thingworxServer+","+thingName+","+appkey;
```

so you can use these variables to connect thingworx api; have a look [**thingworx-alexa-skill**](https://github.com/eercanayar/thingworx-alexa-skill) repo;

```javascript
accessToken = accessToken.split(',');
var options = {
                host: accessToken[0],
                path: '/Thingworx/Things/'+accessToken[1]+'/Properties/'+parameterVal,
                headers: {
                    "Accept": "application/json",
                    "appkey": accessToken[2]
                }
                };
```
