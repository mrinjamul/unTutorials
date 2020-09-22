# Generating a new SSH key

Open Git bash

Paste the text below, substituting in your GitHub email address.

`ssh-keygen -t rsa -b 4096 -C "your_email@example.com"`

This creates a new ssh key, using the provided email as a label.

    > Generating public/private rsa key pair.

When you're prompted to "Enter a file in which to save the key," press Enter. This accepts the default file location.

    > Enter a file in which to save the key (/c/Users/you/.ssh/id_rsa):[Press enter]

At the prompt, type a secure passphrase. For more information, see "Working with SSH key passphrases".

    > Enter passphrase (empty for no passphrase): [Type a passphrase]

    > Enter same passphrase again: [Type passphrase again]

Done

Copy the SSH key to your clipboard.

If your SSH key file has a different name than the example code, modify the filename to match your current setup. When copying your key, don't add any newlines or whitespace.

    `cat  ~/.ssh/id_rsa.pub`

    ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAACAQDVyoNsPw/i0/lyCRMLl1wuBk11zyPVymxPlf5diRxc9nlOW6FP3VD1dEQZ8tNFRB4mlMDEQDHV0a+mQ9Ouse/UWAvtH9z/OdUD+1odKCBVgJ0HECcgG/VviggMTVBcciDoXKTHnwwlUHUUgabwQxYniMS/i8/XGvtZhy6s5GtETooQqKGiqVf525SNwL+v76C90EvtFy5gyzRU8RqGIXTr2oVjIuUCZ/nOz1E+WyNJXCvHQ2x7hLoKWS/d+2xSIIw2mzyxHbnZIoJ8mieAoJKNPNdmr/7uaY/NER/h8eE6sU8nY/YVPa3iEPw7HbHb46AhjD+sc49FNC+ADf49fGyfrXAnZx3BUSbcXi5yszmwbBkkjZA9RksjMAnnxpgsGAo9OhQfdia9pPYZsMfTGW6tcpDqWJSxlZNvtnZRunTPBcZe8ddAFb8qdS6eakYb1QMIRHh3ljvcL+8hB6JxsxPfoDSTJGcowB2OVqlP0S3rv3Ffr+h05Sgb7vL4S36+2X3Pld8xkaFGNUbWZSBZFDyUBnD3qTek5PxBokrHYubLYyntIYJKk3eWfqLzULKrtPAylIQGRY6bkZvmEvru26NtrscA0EhAQlq0qSfiMWB1JjLzV34z1pKESyfWj4bJtpSjmKF58oTrX5/VDGoLoI+iZJLYYA8aDyUdV7M2EdcNcw==example@gmail.com

You will see like this.

Copy the content and Add this to your github ssh keys.
