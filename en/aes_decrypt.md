## AES Decrypt Action

As additional step to the steps provided on AES Encrypt section, you can decrypt the same field which was previously encrypted by adding the AES Decrypt as second action and setting the same Key and IV as the ones used into the AES Encrypt action but on Data Text to Encrypt you just have to use the token where you've previously saved the data, in our case, [test1].

![](e2.png)

And here's how the grid item will look encrypted and decrypted: 
![](e3.png)