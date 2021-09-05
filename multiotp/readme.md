-- Secure windows server with multi OTP

1. Download binary from https://github.com/multiOTP/multiOTPCredentialProvider/releases

2. Run exe file...
- Leave following blank: Update sep 06 2021: https://github.com/multiOTP/multiOTPCredentialProvider/issues/42
```
Url of your multiOTP server
Secret shared with your multiotp servers 
```
because we are using localhost to validate

Then next with default tick ( Only RDP Connection... + Enable cache support )
Click install. Then input user and password
Install this first: https://support.microsoft.com/en-us/help/2977003/the-latest-supported-visual-c-downloads

At this time they said they already include visual c++ but i still need to download 32bit version to get this works

- Then Go to C:\Program Files (x86)\multiOTP, open in cmd
type:
```
multiotp.exe -createga Administrator base32_seed    # This step generate secret key for administrator user 
multiotp.exe -urllink Administrator # Output like this to get secret key

otpauth://totp/administrator?secret=GUN6ORWZWO77BNXESXOLWPFYOQ45YMEV&digits=6&period=30&issuer=multiOTP
```

get the part of secret and add it in google authenticator or oathtool to get "OTP FOR THIS USER"

after done, click test multi OTP authentication....
If everything going well, you will see your account input activated

2.1 Add exists key to multiple OTP ( good for clone :D )
```
multiotp.exe -createga Administrator GUN6ORWZWO77BNXESXOLWPFYOQ45YMEV
```

3. Test it by login again, you will see your login will required OTP together with your password

Good luck on protect your public windows server
