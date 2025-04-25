Create a new user on the local machine and on node01, make the username 'student' and set the password to 'student'.

Check if you can login with the password on node01.

<br>

### Solution
<details>
<summary>Solution</summary>
First create the student user on the local machine and the remote machine.

```plain
useradd -s /bin/bash -m student
ssh node01 'useradd -s /bin/bash -m student'
```{{exec}}

Then setup the password (type student twice).
```plain
passwd student
ssh node01 'passwd student'
```{{exec}}

And on the remote machine as well.
```plain
ssh node01 'passwd student'
```{{exec}}

Check if you can ssh to node01
```plain
ssh student@node01
```{{exec}}

And go back with exit
```plain
exit
```{{exec}}
</details>