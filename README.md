Configure Postfix for Gmail account
=========

An easy way to link your Raspberry Pi with the dedicated Gmail account, so you can send emails straight from the CLI.


Requirements
------------

- Root access
- Already created Gmail account
- Dedicated password ([See](#password-generation))


Password Generation
--------------
1. Log in to your email, then use the following link:
https://myaccount.google.com/security
Scroll down to “Password & sign-in method” and
click 2-Step Verification. You may be asked for your password and
a verification code before continuing. Ensure that 2-Step Verification is enabled.
2. Use the following link to Generate an App password for Postfix
https://security.google.com/settings/security/apppasswords
3. Click Select app and choose "Other (custom name)" option from the dropdown. Enter app's name (e.g. Postfix) and click Generate.
4. The newly generated password will appear. Write it as a value of the postfix_password variable, then click Done.

###### You may need to enable less secure apps access on your Gmail account



Role Variables
--------------
Required:
- postfix_username - Gmail address (e.g. example@gmail.com)  
- postfix_password - individually generated password ([See](#password-generation))


Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: absible-postfix-gmail, postfix_username: example@gmail.com, postfix_password: wdvaddjjkdloqpcz }


License
-------

MIT
