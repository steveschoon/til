# Keystores for Signing Android Apps

Android apps that are published to the Google Play store must be signed with a *public key certificate*.  This certificate must stay the same for the app's entire lifespan.

A `keystore`

- contains the public/private keypairs that make up a signing certificate
- can contain many keypairs, referred to by `alias`
- has a password separate from that of each of the contained keypairs
 
I use a separate keystore per client so that in the future, if the customer wants to take over development from me, I can give them *just that keystore* and associated passwords, but not give them password for any other customer's or my own apps.

### Creating A Keystore

To create a keystore in it's own file

```
keytool -genkey -v -keystore foo.keystore -alias alias1 -keyalg RSA -keysize 2048 -validity 10000
```

You will have to provide the following information:

- A password for the keystore itself
- Name, org unit, org name, location info 
- A password for the `alias1` keypair

### Displaying Contents of a Keystore
To list the keys in a keystore:

```
keytool -list -keystore foo.keystore
```

### Exporting a Certificate

This will export a certificate from a specific keystore
```
keytool -export -alias alias1 -file alias1.crt -keystore foo.keystore
```
# References
- https://stackoverflow.com/questions/7685458/can-i-use-the-same-keystore-file-to-sign-two-different-applications
- https://stackoverflow.com/questions/3997748/how-can-i-create-a-keystore

