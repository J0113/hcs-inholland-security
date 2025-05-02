To get started we need a container scanning tool. Let's start with Trivy.

<br>

### Solution
<details>
<summary>Solution</summary>
Install trivy

```plain
wget https://github.com/aquasecurity/trivy/releases/download/v0.18.3/trivy_0.18.3_Linux-64bit.deb && sudo dpkg -i trivy_0.18.3_Linux-64bit.deb
```{{exec}}

Try to read the documentation
```plain
trivy -h
```{{exec}}
</details>