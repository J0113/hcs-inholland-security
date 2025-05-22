Now, generate a SSH key on the local machine for the student user and copy it to node01.

<br>

### Solution
<details>
<summary>Solution</summary>

Switch to the student user.
```plain
su - student
```{{exec}}

Generate a key that we can push over to node01 and authenticate with, the default options are good.

```plain
ssh-keygen
```{{exec}}

You can verify the new keys with the command below

```plain
ls -l ~/.ssh
```{{exec}}

Note: You created a private key and a public key (*.pub).

Push the key file over to student@node01 (Enter the password 'student')

```plain
ssh-copy-id student@node01
```{{exec}}

Test your connection via your private key into student@node01.

```plain
ssh student@node01 'hostname; id'
```{{exec}}

</details>