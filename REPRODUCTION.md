# Reproduction Notes

All commands below are provided as a methodology record. They intentionally omit recovered laboratory credentials and crackable hash values.

## PDF hash extraction

```bash
/usr/share/john/pdf2john.pl "My Locked PDF1.pdf" > pdf1.hash
/usr/share/john/pdf2john.pl "My Locked PDF2.pdf" > pdf2.hash
/usr/share/john/pdf2john.pl "My Locked PDF3.pdf" > pdf3.hash
```

## JtR validation and dictionary attack

```bash
john --format=pdf --show pdf1.hash
john --format=pdf --wordlist=/usr/share/wordlists/rockyou.txt pdf1.hash
john --format=pdf --show pdf1.hash
```

Repeat the same workflow for `pdf2.hash` and `pdf3.hash`.

## PDF validation

The laboratory workflow used qpdf to validate the recovered PDF1 credential, decrypt the artifact, and check the resulting PDF. The actual credential is deliberately omitted from this public repository.

```bash
qpdf --show-encryption "My Locked PDF1.pdf"
qpdf --check "My Locked PDF1_decrypted.pdf"
pdfinfo "My Locked PDF1_decrypted.pdf"
pdfimages -list "My Locked PDF1_decrypted.pdf"
pdftoppm -png -f 1 -singlefile "My Locked PDF1_decrypted.pdf" "My_Locked_PDF1_page1"
```

## Networkwalks workflow

```text
Networkwalks Hash Calculator
        ↓
Extract crackable PDF representation
        ↓
Networkwalks Password Cracker
        ↓
Dictionary attack
        ↓
Record progress / result
```

Only use these procedures against files and systems you own or are explicitly authorized to test.
