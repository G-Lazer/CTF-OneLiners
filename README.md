# CTF-OneLiners

**Purpose**
Collection of oneliners used for security CTFs.

**Convert PDFs to text and look for credentials.** - Requires pdftotext
for file in \*.pdf; do pdftotext ${file}; done && grep -H -E "account|pass|login|user" \*.txt

**Convert Creator tag in metadata to a list of users.** - Requires exiftool
for file in \**; do exiftool ${file} | grep Creator | sed 's/.\*:* //g' >> usernames.txt; done
