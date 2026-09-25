# Methodology

## Assessment Model

The Week 3 assessment was structured as:

**Protected Artifact → Verifier Extraction → Hash Identification → Candidate Generation → Recovery → Validation → Interpretation**

## PM1 — Local JtR Workflow

1. Identify the supplied PDF artifact.
2. Locate `pdf2john.pl` in the Kali installation.
3. Generate the crackable PDF verifier.
4. Confirm the PDF format is recognized by JtR.
5. Use the RockYou dictionary for offline recovery.
6. Record JtR session output and recovery status.
7. Use `john --show` to confirm the recovered entry.
8. Independently test the recovered PDF1 credential with qpdf.
9. Decrypt and inspect the resulting PDF.
10. Preserve screenshots and command evidence.

## PM2 — Networkwalks Workflow

1. Upload the supplied PDF to the Networkwalks Hash Calculator.
2. Extract the crackable PDF hash.
3. Submit the representation to the Networkwalks Password Cracker.
4. Run the built-in dictionary attack.
5. Record candidate count, observed rate, and result.
6. Treat a bounded negative result as a limitation of candidate coverage rather than proof of password strength.

## Evidence Principle

The assessment distinguishes:

- verifier extraction,
- candidate generation,
- candidate recovery,
- artifact validation,
- and security interpretation.

That separation prevents a single tool message from being treated as the entire proof chain.
