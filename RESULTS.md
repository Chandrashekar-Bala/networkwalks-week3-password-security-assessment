# Results

## Summary

| Artifact | JtR + RockYou | Networkwalks built-in list | Interpretation |
|---|---|---|---|
| PDF1 | Recovered | Not recovered in captured run | Candidate coverage changed outcome |
| PDF2 | Recovered | Recovered at 91/100 candidates, ~9 pw/s | Credential was within bounded list |
| PDF3 | Recovered | Recovered at 35/100 candidates, ~4 pw/s | Credential was within bounded list |

## JtR observations

- PDF1: captured recovery rate approximately **1.639 g/s**, with 104.9 candidates/s in the displayed run.
- PDF2: captured recovery rate approximately **1.639 g/s**, with 104.9 candidates/s in the displayed run.
- PDF3: captured recovery rate approximately **2.380 g/s**, with 3504 candidates/s in the displayed run.

These are run-specific observations and are not presented as controlled performance benchmarks.

## Independent validation

PDF1 was independently validated using qpdf. The recovered credential was accepted, the file reported AESv2 encryption, and the decrypted PDF was subsequently checked and inspected.

The public repository intentionally does not reproduce the recovered credential or the crackable PDF hashes.

## Key conclusion

A bounded dictionary attack returning `No match` does not establish password strength. Candidate-set size and composition materially affect dictionary recovery.
