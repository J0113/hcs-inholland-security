Now, let's decrypt the message.

<br>

### Solution
<details>
<summary>Solution</summary>

Decrypt your message.

```plain
openssl pkeyutl -decrypt -inkey private.pem -in message.enc -out decrypted.txt
```{{exec}}

Check the content of decrypted.txt.
```plain
cat decrypted.txt
```{{exec}}

</details>