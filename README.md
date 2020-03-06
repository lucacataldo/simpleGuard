# simpleGuard
A simple way to guard your express app from wanderers


To use:

1. Install `client-session` npm module
1. add the following two lines in your code right after creating your express app variable, but before any of your other routes

`var simpleGaurd("/path/to/simpleGuard.js")`
`simpleGuard(expressAppVariable, yourDesiredPassword, secretEncryptionString, activeCookieDurationNumber)`

