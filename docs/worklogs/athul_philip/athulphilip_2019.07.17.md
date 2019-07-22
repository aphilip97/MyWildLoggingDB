# 2019/07/17 - 12:00 - First Party Authentication

Followed the instructions in the readme [here](https://github.com/aliceliveprojects/WildLoggingDBParent/blob/master/Authentication.md).

Created an account on Auth0.

Tenant domain is `myurbanwild.eu.auth0.com`.

Created an API on Auth0 called _wildlogging_ with the **API Audience** _[https://www.myurbanwild/wildlogging](https://www.myurbanwild/wildlogging)_.

Encryption algorithm was set to RS256.

Created an application (SPWA) and called it SwaggerUI. When asked about technologies used to create the web app AngularJS was an option but I opted to go for JS as per the instructions (otherwise it might all go wrong :P ).

Set up `http://localhost:8080/docs/o2c.html` as the allowed callback url.

Changed `/api/swagger.yaml` in the local copy of MyWildLoggingDB (generated NodeJS server skeleton) to, make sure that the requests when debugging, went to the instance of the database API (MyWildLoggingDB) that was running on `localhost`.

Added the 'admin' scope to the _wildloggingadmin_ API.

> Make sure the **authproviderconfig.js** file has all the necessary data. **Double check all the information**.

Also make sure that when initialising the database connection whilst running the MyWildLoggingDB server locally, the second parameter to the `initialise` function is false as this tells the server that SSL is needed.

```javascript
// database connection
database.initialise(dbUrl, false);

// Declaration of the above function
// MyWildLoggingDB/service/database.js:25 (at the time of writing this)
var initialise = function (url, needsSSL) {
```
