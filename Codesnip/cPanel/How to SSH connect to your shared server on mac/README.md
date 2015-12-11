###How to SSH connect to your shared server on mac


------

***Step 1.*** Login to the cPanel and then go to the SSH/Shell Access icon. Click on it to access section where you can generate the private key. 

![ssh-shell-access](https://github.com/sag333ar/sag333ar.github.io/blob/master/Codesnip/cPanel/How%20to%20SSH%20connect%20to%20your%20shared%20server%20on%20mac/cpanel-manage-ssh-key.png?raw=true)

------

***Step 2.*** Click on the button labeled Manage SSH Keys

![cPanel Manage SSH Keys](https://github.com/sag333ar/sag333ar.github.io/blob/master/Codesnip/cPanel/How%20to%20SSH%20connect%20to%20your%20shared%20server%20on%20mac/cpanel-manage-ssh-key.png?raw=true)

------

***Step 3.*** Click on the button labeled Generate a new key

![manage-ssh-keys](https://github.com/sag333ar/sag333ar.github.io/blob/master/Codesnip/cPanel/How%20to%20SSH%20connect%20to%20your%20shared%20server%20on%20mac/manage-ssh-keys.png?raw=true)

------

***Step 4.*** Type in a password (do NOT use the password generator), then confirm it. Make sure to write down the password you used. Leave the key type at DSA and key size at 1024.

------

***Step 5.*** If you are creating a key for the first time, click on the Generate Key button.

------

***Step 6.*** You should then see a confirmation that the key was generated. Return to the Manage SSH Keys screen

------

***Step 7.*** You should see the Public key AND the Private key generated with the name "id_dsa". Click on View/Download for the PRIVATE key. This is the key that you will need to load onto your Mac.

------

***Step 8.*** Download the file to your Mac client. To make it simple for this tutorial, copy the file to your desktop.

------

***Step 9.*** Before we move to the Mac side of things, you should check to see if the PUBLIC key has an authorization status of NOT AUTHORIZED. Click on the Manage Authorization link. This will authorize the key for you! NOTE: If you don't authorize this key, it doesn't matter what you do on the Mac side, you won't be able to login.

![key-generated-not-authorized](https://github.com/sag333ar/sag333ar.github.io/blob/master/Codesnip/cPanel/How%20to%20SSH%20connect%20to%20your%20shared%20server%20on%20mac/key-generated-not-authorized.png?raw=true)

------

***Step 10.*** Login to your Terminal program. If you don't know how to do this, go the magnifying glass in the OS toolbar (usually at the top right - this is Spotlight) and type in "terminal". You should see Terminal appear as an application. Select it and it will launch. Note that if you are not logged into your Mac as the administrator you will not be able to make these changes.

------

***Step 11.*** Go to your desktop where you copied the ID_DSA file. The terminal command is: cd desktop

------

***Step 12.*** Make sure that the ID_DSA file is already on your desktop. Then type the following into your terminal:

```
    cp -frp id_dsa ~/.ssh
```

This will copy the key into the .ssh folder.
    
------
    
***Step 13.*** Next run the following command to add the identity to your computer.

```
    ssh-add -K id_dsa
```

You will then need to type in the password you used to generate the key in cPanel.

------

***Step 14.*** You should see a confirmation that the identity has been added to your Mac. When this is complete, you will be able to use the SSH command to login to the server. The cPanel user name will need to be used along with the server name. The command will look like this:

```
    ssh -p 2222 cpanelusername5@servername.inmotionhosting.com
```

Here's an example: `ssh -p 2222 user5@ecbiz188.inmotionhosting.com)`

------

***Step 15.*** If this is the first time you have connected the server, you may see a message stating that it can't identity the server. Just click on "YES" to proceed (just make you're connecting to the right server). The password should automatically work and you should see the terminal connect.

------