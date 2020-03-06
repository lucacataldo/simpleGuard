# simpleGuard
A simple way to guard your express app from wanderers


To use:

1. Install the `client-sessions` npm module if you don't have it already with `npm install client-sessions`
1. Download simpleGuard.js and place it somewhere in your project root
1. Add the following two lines in your main JS file after creating your express app(), but before any of your routes

        var simpleGuard = require("/path/to/simpleGuard.js")
        simpleGuard(expressAppVariable, yourDesiredPassword, secretEncryptionString, cookieActiveDurationMinutes)

It will probably look something like this

        var express = require("express");
        var app = express();

        // what you need
        var simpleGuard = require("./simpleGuard.js") // if simpleGuard.js is located in the project root dir
        simpleGuard(app, "password", "super secret string", 20)

        //The rest of your routes
        app.get("/", (req, res)=>{
            res.send("you're good!")
        })


        app.listen(80)


That's it! You will be prompted to provide a password to visit any route on your app until you provide the correct one. Then, a session cookie will be created which will authorize you until it expires or you log out.

To logout you can do one of two things:

1. Visit _yoursite_/simpleGuard/logout (not a bad idea on public computers)
1. Close your browser and let the cookie expire

