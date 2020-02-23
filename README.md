# Vigen-ish HTML - A Single Web Page for Simple String Encryption

Vigen-ish HTML allows you to perform reasonably-secure encryption and decryption on multi-factor authentication backup codes (or similar random short strings of letters and/or numbers). It is a static HTML web page in a single file that you can store offline on your computer or mobile device or somewhere online. The web page performs all computation in your browser's Javascript engine and does not send or receive any information. The encryption is deliberately simple so that you can, if needed, perform encryption and decryption by hand using pen and paper. The encryption method is quite similar to the [Vigenère cipher](https://en.wikipedia.org/wiki/Vigen%C3%A8re_cipher).

## Contents
* [Use Case](#use-case)
* [How to Use It (Encrypting)](#how-to-use-it-encrypting)
* [How to Use It (Decrypting)](#how-to-use-it-decrypting)
* [Things You Should Not Do](#things-you-should-not-do)

## Use Case <a name="use-case"></a>
I created this because I wanted to bring my multi-factor authentication backup codes with me when travelling. There is always a risk that the "second factor" required to access your online accounts (your phone or other hardware device) will be lost or stolen. If that happens, you cannot access your accounts unless you recover the device or use your backup codes. To reduce the risk of being locked out of online accounts, your backup codes must travel with you.

 Your phone provider may offer a "find my phone" or "erase my phone" feature. But, for security reasons, accessing those features usually requires that you authenticate using your "second factor," which you won't have if it's the phone you're trying to find! Losing your phone with no backup codes can mean your phone is gone forever, possibly along with sensitive data stored on it. [Here is a cautionary tale](https://lifehacker.com/dont-use-sms-for-googles-two-step-verification-in-case-1823144781). 

As the above cautionary tale recommends, the conventional solution to losing your "second factor" is to bring a  paper copy of backup codes with you when travelling. Or to store them somewhere online that won't require that "second factor" to access them. But backup codes are sensive information. They can function just like passwords. If they are lost or stolen, someone can use them to access your accounts.

Bringing those codes with you or storing them on the internet with weak authentication introduces the risk that an unauthorized person can get them. Paper is particularly bad because someone can copy or take a photo of your backup codes, leaving the papers seemingly untouched. You won't know that someone has access to your accounts. Not good.

With Vigen-ish HTML you can easily secure your backup codes and keep them with you on paper or in online storage without the risk that someone can use them to access your online accounts. If you don't have access to this HTML web page, the encryption method is simple enough that you can decrypt your backup codes using a pen and paper. 

While this encryption method is not perfect or foolproof, I prefer it to the risks above. Use this web page to encrypt one or more of your backup codes, print or write down the encrypted codes, and keep the paper copy with you. I recommend keeping the paper copy under your control at all times, as you would do with an identification card or any other sensitive document. That way you will know if anyone else gets access to it. 

## How to Use It (Encrypting) <a name="how-to-use-it-encrypting"></a>
To encrypt a backup code, first load the web page in a web browser. In this repository, the web page is in the file `vigen-ish.html`. The web page does not require any external resources. You don't need an internet connection if you have the file stored on a device and you have a web browser. 

### Provide a Password
Choose a password and type it into the textbox labeled "Password." The password will encrypt your backup code. To decrypt the code you'll need that password. Don't forget it! It's best to use a random series of letters and numbers, but it's not necessary if you're encrypting a backup code and you use a long enough password (12 characters is pretty good). Choose as long a password as you can, while ensuring that you won't forget it. To keep the encryption simple, your password may only contain letters and numbers. Also, passwords are not case-sensitive (upper and lower-case letters are treated the same). You'll see an error alert in the web browser if you dont format the password correctly.

### Decide if You Want Text to Include Only Numbers
If the backup code you're encrypting is all numbers, you may choose to check the "Numbers only for plaintext and encrypted text" checkbox. If you check this box, the plaintext you provide (the backup code) can only contain numbers. The resulting encrypted text will also only contain numbers. If you don't check the box, the encrypted text will contain both letters and numbers. There's no practical difference in security between checking the box or not, as long as you're encrypting backup codes. If you are going to decrypt with pen and paper, decrypting text that consists only of numbers is a bit easier. It does reveal to the reader that the backup code consists only of numbers. But that probably isn't anything to worry about. I assume that a skilled cryptanalyst could examine encrypted text containing letters and numbers and deduce that that the unencrypted backup code only contains numbers. 

### Provide the Backup Code to Encrypt
Type the backup code that you want to encrypt in the box labeled "Backup Code." A backup code can only contain letters and numbers. If you checked the "Numbers only..." checkbox, then the backup code can only contain numbers. The one exception is spaces. You are allowed to enter spaces (just spaces, no tabs or other whitespace) as in the backup code to encrypt. Spaces pass through untouched during encryption and decryption. For eample, encrypting the code "a b c" might generate the encrypted string "d e j." Using the same password, encrypting the code "abc" would generate the encrypted string "dej." Adding spaces to split up text can make it easier to read encrypted and decrypted text. If the backup code you're encrypting contains a different separator like a hyphen, you can replace those with spaces, if you'd like.

### Encrypt the Backup Code
Click the "Encrypt" button and the backup code will be encrypted using the password you provided. If you're missing any required fields or if you've included characters that aren't allowed, an alert in the browser will let you know what you need to fix. If the backup code you entered has spaces in it, the encrypted code will have spaces in the same places. Spaces are ignored when information is decrypted so you can remove spaces when you write down or before printing out the encrypted code.

### Store the Encrypted Code Somewhere
After you click the "Encrypt" button, the encrypted code will appear in the text box labeled "Encrypted Code." You can copy and paste that encrypted code into a document to save it somewhere safe or print it out on paper. If you don't have a printer, you can simply write the encrypted code on a piece of paper. I have one word of caution about saving the encrypted codes in online/cloud storage. If you don't have access to your second factor authentication device, then you need the backup codes. But if you need the backup codes to access the online storage where the document with the backup codes is stored, you're stuck! If you do store the backup codes document online, make sure that it's secured only with a password that you know and won't require your second factor authentication device. This is a use case where "low tech" paper storage can be a pretty safe backup, in case technology fails you.

## How to Use It (Decrypting) <a name="how-to-use-it-decrypting"></a>
To decrypt a backup code, first load the web page in a web browser. In this repository, the web page is in the file `vigen-ish.html`. The web page does not require any external resources. You don't need an internet connection if you have the file stored on a device and you have a web browser. 

### Provide the Password
Type the same password that you used to encrypt the backup code into the textbox labeled "Password." To keep the encryption simple, your password may only contain letters and numbers. Also, passwords are not case-sensitive (upper and lower-case letters are treated the same). You'll see an error alert in the web browser if you dont format the password correctly.

### Specify if the Backup Code Includes Only Numbers
If you encrypted a backup code that only contains numbers and you checked the "Numbers only for plaintext and encrypted text" checkbox when you encrypted it, then you must check this box when decrypting the backup code. If you don't use the same setting for this checkbox for both encrypting and decrypting a backup code, the encryption and decryption won't work properly. Make sure that this setting is the same when you decrypt a backup key as it was when you encrypted it.

### Provide the Encrypted Backup Code
Find the encrypted backup code on your paper or online copy of the encrypted codes. Type the encrypted backup code labeled "Encrypted Code." If you checked the "Numbers only..." checkbox, then the encrypted backup code can only contain numbers. You are allowed to enter spaces (just spaces, no tabs or other whitespace) in the encrypted backup code, even if you did not enter spaces in the backup code when you encrypted it. Spaces are ignored when information is decrypted so you can also remove spaces before from the encrypted backup code, if you want to. 

### Decrypt the Backup Code
Click the "Decrypt" button and the backup code will be decrypted using the password you provided. If you're missing any required fields or if you've included characters that aren't allowed, an alert in the browser will let you know what you need to fix. Any spaces you enter in the encrypted backup code will appear in the same place in the backup code when it's decrypted. When you click the "Decrypt" button, the decrypted backup code will appear in the "Backup Code" text box. This makes it easy to select, copy, and paste the backup code as needed.

If you're encrypting data that appears random, such as backup keys, a random cipher is less important. 

## Things You Should Not Do <a name="things-you-should-not-do"></a>

### Don't Encrypt Codes that Aren't Random
You should not encrypt dictionary words with this cipher because this encryption is breakable if you know something about the language that the original text was written in. The same is true for credit card numbers, phone numbers, social security numbers, and any other information that is not random. Backup codes are usually random (or, at least, impossible to predict) sets of letters and/or numbers. If your backup code contains dictionary words, don't use this tool to encrypt it. 

Unless the data you are encrypting is effectively random, this encryption is not safe to use. If you'd like to learn more about why, here is [a nice explanation of how to break this encryption when the encrypted text contains dictionary words](https://crypto.interactive-maths.com/kasiski-analysis-breaking-the-code.html). This cipher works well for backup keys because it is not possible to learn anything about the encryption key by analyzing the encrypted text. 

### Don't Use Very Short or Obvious Passwords
You've probably heard this password advice before. Passwords in this tool are no different. This web page will let you use whatever password length you'd like when encrypting you backup codes. But longer passwords are better than shorter ones. It's important ot know that this encryption algorithm uses the password multiple times if the backup code you're encrypting is longer than the password. This repeated use of the password might make it  easier for a sophisticated cryptanalyst to figure out your password by analyzing patterns in the encrypted text. If your backup codes are truly random (see above) this risk is extremely low. But a shorter password will be repeated more times so, in theory, there are more opportunities to look for patterns if your password is short. Most importantly, if your password is very short or obvious (like "a" or your name), it's simply very easy for someone to guess.

### Don't Store your Encrypted Backup Codes in Insecure Locations
Even though they are encrypted, don't treat encrypted backup codes like they're public information. With sufficient analysis, someone might be able to figure out your encryption password. That analysis would require a lot of time. So it's important that you know if your encrypted codes have been accessed or stolen. Keep paper copies of the encrypted codes with you. It's not a bad idea to store the encrypted codes somewhere online so you can access them if you lose both your second factor device and your encrypted paper backup codes. Of course, make sure that you don't need your backup codes to access that online storage! But online storage is not secure if you don't require a password to access the encrypted backup codes. If you save the backup codes in a PDF document, you can secure that file with a password very easily. Also, most online storage services like Google Drive, DropBox, OneDrive, etc. will let you share a file or folder and secure it with a password.

Also, usually backup keys can only be tried a few times before the account is locked. If someone gets your encrypted codes and attempts to decrypt them, they should only get a few tries to see if they've done it correctly. 
