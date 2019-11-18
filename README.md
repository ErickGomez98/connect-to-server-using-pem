# Simple guide to connect to a server using a pem file

This simple tutorial will show you in a few steps how to create a pem file in order to connect to a server via ssh using that pem file.

### Steps
The first thing that you would need to do is create a key pair in your local machine, to do so follow the next steps:
1. Create a new key pair using this command: `ssh-keygen -t rsa -b 2048 -v` it will ask you information about where to store this file, and the name you want to give it, it will also ask you if you want to use a passpharase, I decided that I didn't want to but at the end it's up to you.
2. Once the key pair is created, you should see that two files have been created in the specified folder.
3. Now we need to upload the public key to the server we are trying to connect over ssh, to do so, you have to run this command:  `ssh-copy-id name-of-my-key.pub user@server.com` it will ask you the credentials of the server, once this step is done, you have just uploaded your public key to the server so that you can authenticate later using that key.
4. Now add the `.pem` extension to the generated key that doesn't have an extension (not the .pub file), you can do that using the following command: `mv my-certificate my-certificate.pem`
5. Once you have renamed it, you are good to go, the last thing you have to do is connect to the server using that `.pem` file, to do so use the following command: `ssh -i my-certificate.pem user@server.com`

That's all :)
