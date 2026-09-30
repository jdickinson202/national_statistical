# national_statistical
This repo holds the database of national statistical offices for all (available) countries in the world. It was compiled by Pranav Dialani, Josh Picker, Jeff Dickinson, Edward Strong and Arthur Wu as well as other staff from the Economics Discord chat:
http://discord.gg/economics

Please cite this database whenever possible.

Citation Link:
<a href="https://zenodo.org/badge/latestdoi/435074172"><img src="https://zenodo.org/badge/435074172.svg" alt="DOI"></a>

## Link checks

The database includes a status column for each of its six website fields and a
`Links Checked At UTC` timestamp. Original URLs and record update dates are preserved.
`link_check_report.csv` contains one row per link occurrence, with HTTP results,
reasons, timestamps, and request attempts.

- `BROKEN`: the URL returned HTTP 404 or 410 on two requests.
- `OK`: the URL responded with HTTP 2xx. This does not verify its content or safety.
- `UNVERIFIED`: access was blocked, the connection failed, or the server returned another error.
- `REVIEW`: an unvisited cross-domain redirect, a possible error page, or a working HTTPS alternative needs review.
- `SECURITY REVIEW`: an unrelated redirect was identified and requires investigation.
- `SOURCE VERIFIED`: an official or recognized catalog page was identified, but a direct HTTP check was not performed.
- `NO LINK`: the field is blank or contains a placeholder rather than a URL.

Checks use GET requests, retry failures, and try HTTPS when an HTTP link fails.
The final check follows redirects only within the same hostname (allowing a `www.`
prefix change). Other destinations are recorded without being visited. URL fragments
and JavaScript navigation are not validated. Multiple links in one field receive
individual labels. Results reflect the check time and can change.

During the initial run, security software blocked a phishing destination named
`rupiah138.net`. That run was stopped and the complete check was repeated with
cross-domain redirects disabled. No security exception was added. The exact source
of that blocked destination was not confirmed. Ukraine's listed `ukrstat.org` URL
was independently flagged because it redirects to an unrelated website.
