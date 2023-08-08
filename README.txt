PetPedia information needed to run the app


***************************************
In order to maintain complete functionality while running PetPedia the user must make sure that they have a valid api token granted to them at the time of use.
The process of keeping a valid token involves passing the following command into the command line.

_______
1. Enter this command into gitbash from the "test" file directory.

    curl -d "grant_type=client_credentials&client_id=sLxgFmG1XWKOf6CuWsyaVNy0k4o8ItubXNzdpVe1sNo4qVfyjz&client_secret=hPYzAogvpPp45tnbUT1B5xjljwbzF8ZtH7mbJW20" https://api.petfinder.com/v2/oauth2/token

_______

this above command is what till generate the needed token to run the app. Copy and paste the token into the petfinder.js file.
Petpedia -> test -> src -> api -> petfinder.js
 
    {"token_type":"Bearer","expires_in":3600,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiJ9.eyJhdWQiOiJzTHhnRm1HMVhXS09mNkN1V3N5YVZOeTBrNG84SXR1YlhOemRwVmUxc05vNHFWZnlqeiIsImp0aSI6IjliYjc5OGU5MTJmNzMxODQzMmI3ZGVjYjNlYWI3N2JkMzc3YjNkMDM4YmIwMWJhNjBjNmZkMjQ2YmFhY2FmOWJhM2E3YmJkNDdkMzI4MGYzIiwiaWF0IjoxNjcwNTM3OTE3LCJuYmYiOjE2NzA1Mzc5MTcsImV4cCI6MTY3MDU0MTUxNywic3ViIjoiIiwic2NvcGVzIjpbXX0.WB6ENkyEzT1utyDu19gfoUqrQlQLCEKrOchkDZtOu0cu5DxM0q-LR7xKQUZPNyCtw_DcYRm1IGqWbxI6bnCRW4V8SftT3qkBe8adT20YCnhA9r-AwLd3w7idsokrq8LxN01Z3_S_jIIe_OsrRSd3EFDkMN7GQ3mugKzcTEsUcPWQKBc1fsbRsyGjVw2ru0tEmKa0Z8TI4FupuFW9VdMhqu19AXmR3QxMTe5h3oaSW-z8bVVQDvb8lEKO-WtCVmbzlvGFeyql_e0T6GBwWiRSxQSbALEHw-j33N4u-rNW-mTYUASnu0hTTPchCV8e6p5n8HWIEaoT9HdxUN-4RaaCUw"}


The user must copy the access_token value (the entire string) and then paste the string inside of petfinder.js inside of the string with "Bearer {access_token goes here}"
_________________________________________________________________________________________________________________________________________________________

2.
     
     Next, we must ensure that the api token for the authorization is updated into the tracker.js file. 
Petpedia -> test -> src -> api -> tracker.js
     To do this:
	1) Open powershell on "test" directory, run "ngrok http 3000" and copy and paste the forwarding link to the trackerApi file and replace the key in the baseUrl
	
	2) Open gitbash on "track-server" directory and run "npm run dev"
	
	3) Open gitbash on "test" directory and run "expo start --tunnel"


***************************************


Things to watch out for while navigating the app are:

--Authentication Screens 
Signin and Signup Screens are connected and the user cannot access the app unless logged in to an account 


--Home Screen (My Pets)
The user can create, edit, and delete custom pets within the home screen by supplying their own details of the pet (name, breed).


--Explore Screen (Explore & Adopt a Pet)
The user can use the search bar to find an animal that is put up for adoption (ex: type in "Dog" in the search bar).
Modal from react-native-elements was utilized to display a pets detail when clicked on. There is an option to close out of the pop up. 

Animals that pop up for search when using the explore screen: Horse, Dog, Cat, Rabbit, and Bird. These are all of the animals that I was able to get results for
while testing the limits of the PetFinder Api. The search criteria must begin with a capital letter in order to receive results as well.


--Reminders Screen:
Modal pop up was used to display the fill in criteria of the reminder 
1. After a reminder is added there is no way for the user to edit or delete the reminder.
2. Empty reminders will not be saved at all and the fields marked with "*" must be filled in order to save a reminder. If fields are empty, the reminder will not be saved.
3. There isn't any real time tracking, so the reminder is more of a notes feature for the user.


--Profile Screen
Modal was also used to display the "About Us" section 
"Sign Out" button takes you back to the login flow and prompts you to sign up / sign in.




