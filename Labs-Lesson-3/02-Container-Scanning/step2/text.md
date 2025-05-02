A webserver is running on port 80. Check what image the webserver is using, and scan with trivy.

<br>

### Solution
<details>
<summary>Solution</summary>

Verify that the webserver is running.
```plain
curl -sS -D - localhost -o /dev/null
```{{exec}}

Check the running containers. What image is being used?
```plain
docker ps
```{{exec}}

Start a scan with trivy. Output the results to results.txt.
```plain
trivy image -o results.txt bkimminich/juice-shop
```{{exec}}

Check the results. How many issues are found?
```plain
less results.txt
```{{exec}}
</details>