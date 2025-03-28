First let's use Lynis to scan the Ubuntu system.

1. Install lynis with apt-get.
2. Read the man page about lynis.
3. Run a system audit, output to /var/log/lynis.log
4. Read the log file. What is the hardening score?

<br>

### Solution
<details>
<summary>Solution</summary>
Install Lynis with apt.

```plain
apt-get install lynis -y
```{{exec}}

Read the documentation.

```plain
man lynis
```{{exec}}

What command do we need to use to scan the system?

Let's scan the system and output the scan to /var/log/lynis.log

```plain
lynis audit system --logfile /var/log/lynis.log
```{{exec}}

Read the logfile. What is the hardening score?

```plain
less /var/log/lynis.log
```{{exec}}

Extract the score with Grep.

```plain
grep "Hardening index" /var/log/lynis.log
```{{exec}}
 
</details>