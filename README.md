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
In firebase.json file in hosting change "public": "public" to "public": "dist" as firebase changes the public/index.html file and causes errors 

hosted [here](https://ecommerceapp-e526f.web.app)

- add google recaptcha to sign up

- add google recaptcha to contact
- fixed auth so a certain page can only be accessed when logged in 

Made some color palettes to go with the coffe image that was used a couple times, and giving us a bit more of direction by selling coffee related items.
![alt](https://i.ibb.co/gD4Dhny/coffeepalette2.png)
Hopefully with a bit of direction it will help us get the database and items up and running with a theme in mind. (that and the designs at the moment everything has a different color)

### Todo
- use rebeccas modal code for sign up and login.
- looking into and testing firebase realtime database


## Sprint 3
Date: 29/03/21
### Todo
- set up data base and start populating the shop
- firebase database example rules [here](https://medium.com/@juliomacr/10-firebase-realtime-database-rule-templates-d4894a118a98)
### Done
- firebase json file 
- Decided to go with firebase realtime database. Started making example json files to show rebecca so we can make a whole json file together
```
{
    "products": [
        {
         "accessories": [
                {
                    "id": 1,
                    "name": "4 set Pins",
                    "description": "Set of four assorted coffee enamel pins ",
                    "price": 9.00,
                    "url": "https://ae01.alicdn.com/kf/Ha066cc1143de4622959ea599037f0078f/4pcs-set-Enamel-Pins-for-Backpack-Typewriter-Audio-Tape-Mood-Potion-Brooches-Badges-Fashion-Pin-Jewelry.jpg_640x640.jpg"
                },
                {
                    "id": 2,
                    "name": "Sticker Set",
                    "description": "Set coffee themed stickers ",
                    "price": 9.00,
                    "url": "https://ae01.alicdn.com/kf/H8eb7843b19ae4f1798c7712f80371bb9P/46pcs-lot-Vintage-Coffee-Drinks-Stickers-Scrapbooking-Diary-Stickers-Travel-Decorative-Planner-DIY-Crafts-Stationery-Stickers.jpg_Q90.jpg_.webp"
                },
                {
                    "id": 3,
                    "name": "Tote Bag",
                    "description": "Coffee Themed Tote Bag ",
                    "price": 9.00,
                    "url": "https://ae01.alicdn.com/kf/Hf299557b526048b88e465c1457b0d559V/Cute-Fashion-Shoulder-Bag-Drinking-Juice-Coffee-Print-Harajuku-Girl-Casual-Tote-Bag-Fun-Summer-Shopper.jpg_Q90.jpg_.webp"
                }
            ],
            "homeware":[
                {
                    "id": 1,
                    "name": "Cat coffee mug",
                    "description": " Cat Themed coffee mug ",
                    "price": 9.00,
                    "url": "https://ae01.alicdn.com/kf/HTB1g4g8XjnuK1RkSmFPq6AuzFXa8/VFGTERTE-1PC-420ml-Lovely-White-Black-Cat-Coffee-Milk-Light-Ceramic-Lovers-Mug-Couples-Cup-for.jpg_Q90.jpg_.webp"
                }

            ],
            "clothing":[
                {
                    "womens":[
                        {
                            "id": 1,
                            "name": "Womens T-shirt",
                            "description": " Womens print coffee tshirt ",
                            "price": 9.00,
                            "size":["small","medium","large","Xlarge"],
                            "url": "https://ae01.alicdn.com/kf/HTB1h9ifUSzqK1RjSZFpq6ykSXXam/Ok-but-First-Coffee-Funny-Women-T-shirts-Summer-Harajuku-Plus-Size-Short-Sleeve-White-Black.jpg_Q90.jpg_.webp"
                        },
                        {
                            "id": 2,
                            "name": "Womens Hoodie",
                            "description": "Womens sloth print hoodie ",
                            "price": 9.00,
                            "size":["small","medium","large","Xlarge"],
                            "url": "https://ae01.alicdn.com/kf/He22671abc69443b9b50fd85ef14541dcg/Sloth-Hiding-In-Quilt-And-Coffee-Print-Hoody-Women-Street-Fashion-Hoodie-With-Hood-Women-S.jpg_Q90.jpg_.webp"
                        }
                    ],
                    "Mens":[
                        {
                            "id": 1,
                            "name": "Mens Tshirt",
                            "description": "Mens print coffee tshirt ",
                            "price": 9.00,
                            "size":["small","medium","large","Xlarge"],
                            "url": "https://ae01.alicdn.com/kf/Hea1759454a5b419db8d32d8c550f9efaE/Science-Project-Programmer-IT-Men-Tshirt-I-Turn-Coffee-Into-Code-MasterCam-Program-Faddish-Breathable-Cotton.jpg_Q90.jpg_.webp"
                        },
                        {
                            "id": 2,
                            "name": "Mens Hoodie",
                            "description": "Mens print coffee hoodie ",
                            "price": 9.00,
                            "size":["small","medium","large","Xlarge"],
                            "url": "https://ae01.alicdn.com/kf/H84f071af56824ffa93fdf6f2d6590a5dk/Morning-Cat-Hip-Hop-Coffee-Cat-Print-Mens-Clothes-Autumn-Oversized-Hoodie-Streetwear-Harajuku-Sweatshirt-Spring.jpg_Q90.jpg_.webp"
                        }
                    ]
                }
            ]
            
        }
    ]
}
```
we could even take this further but seperating accessesories into pins, totes and stickers, clothing into hoodies and tshirts etc.


- Login and Sign up boostrap modals now work with firbase authentication and link to the shop page

- added the database items using vuefire plugin and a couple of tutorials and stack overflow 
![](https://i.ibb.co/2sw2Vdt/json-file-to-site.png)
we used visual studio live share to collaborate in a single page 
![](https://i.ibb.co/kQ4kB4f/using-live-share-to-collab-instantly.png)

### Sprint 4

I was having trouble with firebase realtime set up and crud, it seemed like the simplest to set up but most tutorials are on the new firestore database, I used this [tutorial](https://levelup.gitconnected.com/firebase-import-json-to-firestore-ed6a4adc2b57) to import our json file to firestore. 
![](https://i.ibb.co/SKQLshn/firestorecollections.png)
![](https://i.ibb.co/cvqVnrR/importjsoncodetofirestore.png)

I left the realtime database code on the products page as we only need to read that data, and the CRUD firestore on the admin products. 

I  used nested routes to render child components inside a parent component 

![](https://i.ibb.co/pfFLSyn/nested-routes.png)

### Sprint 5

this [tutorial](https://www.positronx.io/vue-js-firebase-build-vue-crud-app-with-cloud-firestore/) for the firestore crud.

and logging in with the admin account now shows an admin button, as i couldnt find a way of having only having the admin login page to access the admin section. I made a work around using the admin user UID adding it to the env file and then comparing it to the current user uid, if they matched an admin button will show.
this however doesnt stop people from adding /admin to the url and will need further research into authentication and firebase rules.
Their were ways to use firebase funtions, but i would have to pay for a firebase account upgrade. 

In hind sight i have used a lot of repeating code to access all the different collections stored on the firebase firestore database, If I have time I will try to condense this code so it itsnt so repetative. 

### Sprint 6

- search
 - pay for firebase to use functions and angola ? (then use functions for login as well>)
- sort 
- pwa 
- <br/>
I only did reasearch for searching in this sprint as i started a junior developer job, that also does ecommerce sites and helps companies with automating business task, using asp.net and asp.net core. 

### Sprint 7
Upgraded my firebase to a pay as you go account to use functions and angolia for full text search. <br/>
next sprint i will change the admin login to use functions now that the firebase account is upgraded
<br/>
Added Algolia Search, uploaded our json file to the index, and used widgets to create a search page with vue-instant- search
[Docs](https://www.algolia.com/doc/) [Instant Search with widgets](https://www.algolia.com/doc/guides/building-search-ui/what-is-instantsearch/vue/) 
![algolia-settings](https://i.ibb.co/dGj91Ft/algolia.png)
