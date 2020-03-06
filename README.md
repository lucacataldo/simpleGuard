# simpleGuard
A simple way to guard your express app from wanderers


To use:

1. Install `client-session` npm module
1. add the following two lines in your code right after creating your express app variable, but before any of your other routes

        var simpleGuard = require("/path/to/simpleGuard.js")
        simpleGuard(expressAppVariable, yourDesiredPassword, secretEncryptionString, cookieActiveDurationMinutes)

The second line will look something like this
        simpleGuard(app, "password", "super secret string", 20) //that last number is optional and defaults to 15min

That's it! You will be prompted to provide a password to visit any route on your app until you provide the correct one. Then, a session cookie will be created which will authorize you until it expires or you log out.

To log out you can do one of two things:

1. visit _yoursite_/simpleGuard/logout (not a bad idea on public computers)
1. close your browser and let the cookie expire

