

Next, let's encrypt a message. 

<br>

### Solution
<details>
<summary>Solution</summary>

Create a secret message (press 'i' to insert, type your message, press 'ESC', type ':wq!', press enter).

```plain
vim message.txt
```{{exec}}

Encrypt your message.

```plain
openssl pkeyutl -encrypt -pubin -inkey public.pem -in message.txt -out message.enc
```{{exec}}

Check the content of the message.enc.

```plain
xxd message.enc
```{{exec}}

</details>