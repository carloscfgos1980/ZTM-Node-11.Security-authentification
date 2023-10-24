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
