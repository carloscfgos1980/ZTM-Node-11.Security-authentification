## Node security + authentification

# Lesson 1. Security and Authentification overview

https://academy.zerotomastery.io/courses/1206554/lectures/32977714

# Lesson 2. Encrypted connections with SSl and TLS

https://academy.zerotomastery.io/courses/1206554/lectures/32517737

N: TLS es de successor of SSL. This are encrypted system!

# Lesson 3. Digital certificates, signing and Man in the middle attacks

https://academy.zerotomastery.io/courses/1206554/lectures/32517740

DC (digital certificates) - are Use to encrypt our data when it sent to thru internet. There are site that sell this certificate, sites that are world trust worthy.
We are not going to use that coz we have to pay, we are going to use a self Signed certificate but this will only works during development and not during production coz other computers will not recognize this certificate.

# Lesson 4. Setting out Security example

https://academy.zerotomastery.io/courses/1206554/lectures/32517742

# Lesson 5. HTTPS witn Node, Self Signed Certificates and Public Key Cryptography

https://academy.zerotomastery.io/courses/1206554/lectures/32517745

In this site we can install Open SSl in order to create certificates, it is probably already installed in Mac!

https://www.openssl.org

1. Create the certificate
   cd example-security

openssl req -x509 -newkey rsa:4096 -nodes -keyout key.pem -out cert.pem -day 365

-x509 means it is a self certificate
rsa:4096 is the type of encrypting and the size of the the key.
-keyout key.pem is the name of the file with the key
-out cert.pem creates a file with the certificate
-day 365 is the amount of days that will last this certificate, by default is 30 days

N: I had to type the CLI because I got an error

2. Set up the parameters to use the key and the certificate:

https.createServer({
key:fs.readFileSync('key.pem'),
cert:fs.readFileSync('cert.pem')
}, app).listen(PORT, () => {
console.log(`Listening on port ${PORT}...`);
});

- We need to import (fs)

3. Wehn load the page, we need to give permission to google chrome to open the page that will open as not secure coz we are not certificated to grant this permission globalwise.

# Lesson 6. Helmet

https://academy.zerotomastery.io/courses/1206554/lectures/32702898

- Check the info in helmet. This is used to protect our APIs.
  https://helmetjs.github.io

1. terminal
   npm install helmet

2. Require and use the helmet middleware. server.js:

const helmet = require('helmet');
app.use(helmet());

- It has to be implemented over all the routes so it will affec them.

# Lesson 7. Authentication vs Authorization

https://academy.zerotomastery.io/courses/1206554/lectures/32702899

- failure request response:
  401 - bad authentication
  403 - no authorization

# Lesson 8. Social Signing

https://academy.zerotomastery.io/courses/1206554/lectures/32702900

# Lesson 9. API keys

https://academy.zerotomastery.io/courses/1206554/lectures/32702901

N: Explanation how to get API key from google

# Lesson 10. JWTTokens

https://academy.zerotomastery.io/courses/1206554/lectures/32702902

# Lesson 11. The aith standards

https://academy.zerotomastery.io/courses/1206554/lectures/32708908

# Lesson 12. OAUTH 2.0 Authorization Code Flow

https://academy.zerotomastery.io/courses/1206554/lectures/32708909

# Lesson 13. OAUTH in Action with single sign in

https://academy.zerotomastery.io/courses/1206554/lectures/32708911

# Lesson 14. Registering with Google Authorization Server

https://academy.zerotomastery.io/courses/1206554/lectures/32708912

https://developers.google.com/identity/protocols/oauth2

https://console.cloud.google.com/projectselector2/apis/dashboard?pli=1&supportedpurview=project

N: Follow all the steps all the tutorial to create Google credentials

# Lesson 15. Authentification Endpoints with middleware

https://academy.zerotomastery.io/courses/1206554/lectures/32712271

# Lesson 16. Passport.js

https://academy.zerotomastery.io/courses/1206554/lectures/32726627
