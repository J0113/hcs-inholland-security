Now we are going to scan the system with OpenSCAP.

1. Install openscap with apt-get (hint: openscap-scanner).
2. Read the man page about OpenSCAP.
3. Run a system audit, output the html report /var/log/openscap.html
4. Open the report file. What is the hardening score?

<br>

### Solution
<details>
<summary>Solution</summary>
Install OpenSCAP with apt.

```plain
apt-get install openscap-scanner -y
```{{exec}}

Read the documentation.

```plain
man openscap
```{{exec}}

```plain
openscap xccdf eval -h
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