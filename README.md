This is a short demo for sprint planning 3/21/24.

## Overview

* blastula is an R package for sending emails. [Docs here](https://rstudio.github.io/blastula/). 
* According to the docs, you can use various providers (Outlook, 365, Gmail). I have used Gmail.
* There are features for customizing the HTML formatting of emails. 


## Using with Gmail and Posit Connect

This probably isn't the recommended approach - instead we should be using a service account. 
However, this is what I figured out and what currently underlies the PSInet Get Involved automated emails.

* In order to use blastula with Gmail, you need to have two-factor authentication turned on.
* Then you need to create an App Password for your Google account. Search "App passwords" in "Manage your Google account". Copy the password.


## Writing an email

* Use the `compose_email` function.
* You can customize the body using "blocks". I believe you can also write custom HTML.
* There is also a `blastula_email` type output for .Rmd documents in Posit Connect: https://solutions.posit.co/gallery/conditional-example/

## Sending the email

* I use the `smtp_send` function. 
* Locally, I set the "SMTP_PASSWORD" env variable.
* You can also provide this as an env variable in Posit Connect (but getting it to deploy the first time might be tricky - I got around it in the PSInet context by having the email only be being sent conditionally by a shiny app).

## Takeaways

* The method of authentication I used for PSInet should probably be superceded by a service account.
* `blastula` has email writing functions and sending integration with Posit Connect that may be more powerful when combined with a service app.
