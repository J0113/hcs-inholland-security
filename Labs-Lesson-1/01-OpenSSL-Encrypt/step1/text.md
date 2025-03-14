Generate a private key to private.pem. Use this private key to generate a public key to public.pem.

<br>

### Solution
<details>
<summary>Solution</summary>

Generate the private key:

```plain
openssl genpkey -algorithm RSA -out private.pem
```{{exec}}

Generate the public key:

```plain
openssl pkey -in private.pem -pubout -out public.pem
```{{exec}}

Verify that you have the binaries on your system.

```plain
cat private.pem
cat public.pem
```{{exec}}

Now that we have our keys, we can encrypt a message.

</details>