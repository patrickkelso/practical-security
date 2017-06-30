# practical-security

You will eventually suffer a security breach, the following are some recommendations for limiting the scope of the breach and mitigating the risk as much as possible. Security is always a trade off with convenience. Security requirements that are too onerous will result in people finding creative work arounds to avoid them. You should balance the security required with the convenience required.

## Plan
The most important step in security is having a plan, that is known in your office (or family) on how you will implement the following and what to do in the event of a breach or suspected breach. 

The plan should also cover exceptions, sometimes a key person will be traveling and not have access to their usual systems, how will you authenticate requests from them to make changes to systems or transfer money. 

Most 'cyber' incidents are social engineered attacks that happen to use a computer or automated systems that target anything connected to the Internet.

The technical steps below are only useful if they are implemented and everyone knows the plan.

## Software updates
The best line of defence against most 'hacks' is a system that is up to date. Your computer and phone should be set to receive and install updates from Microsoft, Google or Apple once they are available. If you get a notification that there is an update waiting to install you should install it as soon as possible. However you should also be wary of websites that pretend to be notifications of updates that are malicious. If you get a notification you can verify the update by using the system update method on windows this is the Windows Update utility in the Control Panel, on OSX this is done through the Mac App Store. 

## Passwords

A good password has the following characteristics:
* Longer than 10 characters
* Not based on a single dictionary word
* Contains a mix of upper and lower case letters, numbers & alphanumeric characters 
* Is only used for one thing
* Is not written down on a post-it note and stuck to your screen
* Is not deterministic. If I know your kids/dogs/cats names I shouldn't be able to guess your password. If I know your password last month was FluffyCat05 I shouldn't be able to guess your password this month is FluffyCat06

Remembering a lot of good passwords is hard. To assist with remembering passwords a password safe is recommended. This is a secure place to store multiple passwords that is protected by one, easier to remember good password. Popular options include [Lastpass](https://lastpass.com/), [Enpass](https://www.enpass.io/), [Dashlane](https://www.dashlane.com/), [1Password](https://1password.com/) and [KeePass](https://keepassxc.org). A password safe is only as secure as the password protecting it and the quality of the code that it is programmed in. KeePass is an open source password safe which means that all the code has and can be reviewed by anyone, however it may not be as user friendly or updated as often as commercial applications.

For additional security you could use one password manager for higher risk accounts like Internet banking, and a separate password manager for other sites.

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

## Backups
One of the most important components of security is having reliable off-site backups of your data. If you are compromised by ransomware that demands payment to decrypt your data, having a backup can be the difference between having to pay and not. If you lose your phone or laptop having a backup means you can recover all of your data. 

A common strategy is the [3-2-1 method](https://blog.malwarebytes.com/101/2017/04/3-2-1-go-make-backups-of-your-data/). 3 copies of your data in at least 2 locations, 1 of them off-site. For example having a copy of your documents on your laptop, an external storage drive and backed up to a remote location.

The off-site data should be encrypted as well to prevent third parties from accessing the data, and should be automated to ensure it happens, lastly it should be tested regularly to ensure your backups are working.

Popular commercial options include [Crashplan](http://www.crashplan.com), [Backblaze](http://www.backblaze.com) and [Carbonite](https://www.carbonite.com/en/cloud-backup/business/business-backup-and-recovery/).

Both Apple and Google offer backups of their phones using their respective cloud services.

## Cloud data storage
Any data stored in Evernote, Dropbox, Google Drive, OneDrive or similar services is stored unencrypted and can be read by the storage provider and anyone it is shared with. Often the default permissions for sharing are too broad and should be checked regularly. There are services that can audit some of these systems.

Even though cloud storage providers are reliable (though not perfect) data stored there should still be stored in 2 other places. Especially as once data is deleted in one place it is often replicated to the others connected to the storage. 

Cloud data storage services are *not* the same as backups.
