# simpleGuard
a simple way to guard your express app from wanderers


To use:

1. Install `client-session` npm module
1. add the following two lines in your code after creating your express app variable:

`var simpleGaurd("/path/to/simpleGuard.js")`
`simpleGuard(expressAppVariable, yourDesiredPassword, secretEncryptionString, activeCookieDurationNumber)`

