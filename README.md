# studio6portfolio
## Sprint 1
Date: 23/02/21

### Done
- added Rebecca to firebase project
- added password strength meter from [here](https://www.npmjs.com/package/vue-password-strength-meter). added html pattern to required password so password min requirements will work on all browsers. 
```
 pattern="(?=.*\d)(?=.*[a-z])(?=.*[A-Z]).{8,}"
```
-  added .env files for production and build to keep our keys secret 
-  started google captcha but it needs a domain for api key so the site needs to be hosted first. 
-  fixed sign up and login with [this](https://blog.logrocket.com/vue-firebase-authentication/) tutorial and [this](https://dev.to/gautemeekolsen/vue-guard-routes-with-firebase-authentication-f4l) 


## Sprint 2

Date 16/03/2012

### Done
- host site on firebase
 [partial deploys](https://firebase.google.com/docs/cli/#partial_deploys) When initialising firebase i added database in for future use, so when using ```firebase deploy``` command it tried to do the database which caused an error as there is no database or rules currently 
so now use 
```
firebase deploy --only hosting 
```
In firebase.json file in hosting change "public": "public" to "public": "dist" as firebase changes the public/inex.html file and causes errors 

hosted [here](https://ecommerceapp-e526f.web.app)

- add google recaptcha to sign up

- add google recaptcha to contact
- fixed auth so a certain page can only be accessed when logged in 

Made some color palettes to go with the coffe image that was used a couple times, and giving us a bit more of direction by selling coffee related items.
![alt](https://i.ibb.co/xMDCHGH/coffeepalette1.png)
![alt](https://i.ibb.co/gD4Dhny/coffeepalette2.png)
Hopefully with a bit of direction it will help us get the database and items up and running with a theme in mind. (that and the designs at the moment everything has a different color)

### Todo
- use rebeccas modal code for sign up and login.
- looking into and testing firebase realtime database


## Sprint 3
- set up data base and start populating the shop
- firebase json 
- firebase database example rules [here](https://medium.com/@juliomacr/10-firebase-realtime-database-rule-templates-d4894a118a98)
- 
