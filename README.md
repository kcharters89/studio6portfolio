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


- 
