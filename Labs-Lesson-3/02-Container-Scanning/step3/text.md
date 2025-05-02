Grype is another tool. Install grype and scan the same container. Compare the results.

<br>

### Solution
<details>
<summary>Solution</summary>

Install Grype
```plain
curl -sSfL https://raw.githubusercontent.com/anchore/grype/main/install.sh | sh -s -- -b /usr/local/bin
```{{exec}}

Check the options
```plain
grype -h
```{{exec}}

Run the scan. Output to results-grype.txt
```plain
grype bkimminich/juice-shop --file results-grype.txt
```{{exec}}

Verify the results. Are the CVE's the same as Trivy?
```plain
cat results-grype.txt
```{{exec}}
</details>