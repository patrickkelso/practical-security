# practical-security

## Passwords

A good password has the following characteristics:
* Longer than 10 characters
* Not based on a single dictionary word
* Contains a mix of upper and lower case letters, numbers & alphanumeric characters 
* Is only used for one thing
* Is not written down on a post-it note and stuck to your screen
* Is not deterministic. If I know your kids/dogs/cats names I shouldn't be able to guess your password. If I know your password last month was FluffyCat05 I shouldn't be able to guess your password this month is FluffyCat06

Remembering a lot of good passwords is hard. To assist with remembering passwords a password safe is recommended. This is a secure place to store multiple passwords that is protected by one, easier to remember good password. Popular options include Lastpass, Enpass, Dashlane, 1Password and KeePass. A password safe is only as secure as the password protecting it and the quality of the code that it is programmed in. KeePass is an open source password safe which means that all the code has and can be reviewed by anyone, however it may not be as user friendly or updated as often as commercial applications. 

### Step One
Choose a password safe that you can work with, think about how you will be using it, what type of computer will it run on and what phone you have. [Here is a good article on choosing a password safe](http://www.tomsguide.com/us/best-password-managers,review-3785.html)

### Step Two
Choose a good, long password for the password safe. Do not try and pick random words yourself, you're terrible at it. (We all are). 

I recommend using [Diceware](http://world.std.com/~reinhold/diceware.html) to generate your password. Even better if you have a real dice to roll. A 6 word password using Diceware is very secure and for all intents and purposes unbreakable at this time (2017). I use a list of words from [the EFF](https://www.eff.org/dice) to generate the passwords.

I've included the EFF list in this Github repository for convenience.

### Step Three
Remember your master password. If you need to write it down and keep it in your wallet at first. After you've typed it in a few times you're unlikely to forget it. If you are really worried about forgetting it then you could leave a copy of it in a physical safe or share it with a trusted person to store in their password safe (make sure they have a good strong phrase too).

### Step Four
Go through all your sites and change their passwords to random strings of characters that means nothing to you, but is stored in your safe. 

## Two Factor Authentication
A second step is wherever possible enabling Two Factor Authentication (2FA). You probably already have this on your Internet banking or [my.gov](http://www.my.gov.au) account. This works by asking for a second authentication token after your password, usually a time based number. (Without going into details some solid maths is used to know the token number at a specific time using an initially known seed value). Often this is sent by SMS (Which is terrible, but I'll get to that), some banks use physical token fobs that you carry on your keys. 

There are also software generators, Facebook has one built in and Google have released an open source public implementation called Google Authenticator. These work by installing an App on your smartphone that can scan a QR code and use it as the seed for the 2FA token. A popular app for this is [Authy](http://www.authy.com) which synchronises your tokens to their servers and allows you to access them on multiple devices instead of always needing a specific phone. There is a trade off in security in having your details on their servers, but the upside is greater convenience. Authy claim to have no access to your codes.

Most websites that support these codes know you don't want to enter two passwords every time you visit so they offer to remember your browser for a period of time, usually weeks or a month. If you are using your computer this is a sensible option, if you are in an Internet cafe you would clearly not remember the access.

The reason these are so good is because even if you use a suspect computer in an Internet Cafe and they get your username and password, the time based token only works for 30 seconds, so it will be useless the next time someone tries to use it.

## Encryption
Without encryption anyone who has physical access to your computer can access your data. It is even possible to login to websites that you've saved the login to without knowing your passwords.
### Phones and tablets
If you have a recent iPhone or Google Pixel device your phone is encrypted already. If you have an older iPhone or non Google device it may not be. For extra safety it is recommended to encrypt your phone. Even with a password there are ways to get into a non encrypted phone that would allow someone access to your private messages, emails and photos. 
### Computers
If you have an Apple computer you should enable [FileVault](https://support.apple.com/en-au/HT204837) which will encrypt the storage. If you
are using Windows 8 or 10 Professional or Enterprise you can enable [BitLocker](https://www.howtogeek.com/192894/how-to-set-up-bitlocker-encryption-on-windows/) encryption. If you are running Windows 7, 8 or 10 Home edition you'll need third party software to encrypt the partitions. [Veracrypt](https://www.howtogeek.com/howto/6169/use-truecrypt-to-secure-your-data/) is a free option.

