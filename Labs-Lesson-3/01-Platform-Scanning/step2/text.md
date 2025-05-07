Now we are going to scan the system with OpenSCAP.

1. Install openscap with apt-get (hint: apt search openscap).
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
man oscap
```{{exec}}

```plain
oscap xccdf eval -h
```{{exec}}

Now we need to download the DataSource for Ubuntu2404 to scan the system.

```plain
mkdir -p /usr/share/xml/scap/ssg/content
cd /usr/share/xml/scap/ssg/content
wget https://github.com/ComplianceAsCode/content/releases/download/v0.1.76/scap-security-guide-0.1.76.zip
```{{exec}}

Extract the correct DataSet from the zipfile.

```plain
unzip scap-security-guide-0.1.76.zip scap-security-guide-0.1.76/ssg-ubuntu2404-ds.xml -d .
cp -rp scap-security-guide-0.1.76/ssg-ubuntu2404-ds.xml .
```{{exec}}

Check the info in this DataSet.
```plain
oscap info ssg-ubuntu2404-ds.xml
```{{exec}}

What command do we need to use to scan the system?

Let's scan the system with openscap and log to report.html
```plain
oscap xccdf eval --profile xccdf_org.ssgproject.content_profile_cis_level1_server --report /root/report.html ssg-ubuntu2404-ds.xml
```{{exec}}

Read the logfile. What is the hardening score?

```plain
cd
less /root/report.html
```{{exec}}

Extract the score with Grep.

```plain
grep "scoring" /root/report.html | grep -o "[0-9]\+\.[0-9]\+%" | head -1
```{{exec}}
 
</details>
