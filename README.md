# Wuhan University Suspected Academic Misconduct Repository  

## (WHU-Misconduct-Evidence Repo – English Specification)  

[简体中文点击这里](README_ZH.md)  

# 目前暂时只接受学术造假证据收集与严重的学术失误(Fraud/Error)，暂停接受轻微学术失误问题(Slight Error or Oversight)

## 1. Scope & Purpose  

This repository is dedicated exclusively to publicly available works (papers, monographs, reports, etc.) in which at least one author lists “Wuhan University / WHU” in the affiliation or correspondence address and for which academic-misconduct concerns (plagiarism, fabrication, image manipulation, duplicate publication, improper authorship, …) have been raised.  

### Goals

- Preserve verifiable evidence in an open format for independent examination.  
- Improve academic governance at Wuhan University through transparency.  
- Protect whistle-blowers while preventing unfounded accusations.  

## 2. Directory Layout  

```tree
/root
 ├── CODE_OF_CONDUCT.md
 ├── CONTRIBUTING.md
 ├── LICENSE
 ├── README.md                # states “WHU-only scope”
 └── fraud\error\oversight
      └── whu_author_advisor_title/ # Use Chinese names and replace any special characters in the title with “_”. If there are multiple authors involved, use the first one.
           ├── README.md      # ≤200-word case summary
           ├── metadata.yaml  # bibliographic & WHU fields
           ├── original/      # publisher PDFs, XML, etc.
           ├── analysis/      # similarity or forensic reports
           └── evidence/      # screenshots, e-mails, hashes
```  

### What are Academic Fraud, Error, and Oversight?

**Academic fraud** refers to intentional violations of academic norms and integrity during research or publication, such as fabrication, falsification, plagiarism, duplicate publication, improper authorship, and image manipulation. These actions seriously undermine academic fairness and research integrity.

**Academic error** typically means unintentional mistakes in data, analysis, or conclusions caused by negligence, lack of knowledge, or methodological flaws. Such errors are not deliberate but may affect the scientific validity and reliability of the research.

**Academic oversight** refers to the omission of necessary steps, citations, data verification, or other academic requirements during research or publication due to carelessness. While not malicious, it reflects insufficient awareness of academic standards or attention to detail.

This repository collects cases involving all three types of issues, aiming to promote academic standards and self-correction.

## 3. Mandatory metadata.yaml  

```yaml
doi: 10.1234/abcd.2023.001 # can be null if not provided
title: "Paper Title"
authors: # If there is multiple author involved in some cases, list them all but only show the WHU-affiliated authors in the whu_authors field
  - Zhang, San
  - Wang, Er
advisor:
  - Li, Si
journal: Journal Name
year: 2023
url: https://doi.org/10.1234/abcd.2023.001
date_added: 2025-08-04
submitter: UserName  # This field can be left blank; if submitting on behalf of someone else, please indicate the original submitter
whu_authors:                # at least one entry
  - Zhang, San (School of Physics and Technology, Wuhan University)
affiliation_proof:          # link(s) or file(s) that show WHU affiliation
  - evidence/affil_screenshot.png
misconduct_type:            # choose: plagiarism / fabrication / image_manipulation /
  - duplicate_publication   #        duplicate_publication / authorship / other
  - authorship
```  

## 4. Contribution Workflow

1. Choose the appropriate workflow based on the type of issue:

   - **Academic fraud (fraud):** Fork the repository → create a feature branch → add the `/fraud/author-advisor-title/…` directory and contents → submit a Pull Request.
   - **Academic error (error):** Fork the repository → create a feature branch → add the `/error/author-advisor-title/…` directory and contents → submit a Pull Request.
   - **Academic oversight (oversight):** Fork the repository → create a feature branch → add the `/oversight/author-advisor-title/…` directory and contents → submit a Pull Request.

   - Alternatively, organize the content in your own repository and link it as a submodule to this repository.

2. PR template (WHU-specific checklist):
   - ☐ At least one author is affiliated with Wuhan University, and proof is attached.
   - ☐ All uploaded materials are legally redistributable, or permission has been obtained.
   - ☐ Personal or sensitive data have been anonymized.

## 5. Evidence & Analysis Requirements  

- Submission must contain explicit proof of WHU affiliation; otherwise it is rejected.  
- All general evidence rules still apply: verifiable, complete, reproducible, neutral wording.  
- Any comparison or forensic script (e.g., diff, image-manipulation detection) must be saved inside `analysis/` with environment notes.  

## 6. Legal & Ethical Compliance  

- Focus on documented actions, avoid personal attacks.  
- Conform to PRC Civil Code regarding reputation rights and information-network dissemination.  
- If publisher license forbids redistribution of full PDF, store only a SHA-256 hash plus the DOI/URL.  

## 7. Code of Conduct  

See [CODE_OF_CONDUCT](CODE_OF_CONDUCT.md). Key points: no insults, discrimination, or regional slurs; discussions must stay evidence- and method-focused.  

## 8. Disclaimer  

Maintainers and contributors provide materials and analyses without making final judgments. Determinations of misconduct rest with the Wuhan University Academic Integrity Committee, journal editors, or other competent bodies.  

## 9. Recommended Tools

- Text overlap: iThenticate, Turnitin, VronPlag.  
- Image forensics: ImageTwin, Forensically.  
- Web archiving: Internet Archive “Save Page Now”, perma.cc, SHA-256 hashing.  

There are basically no recommended methods to quickly find academic loopholes that are not so obvious, and we kindly ask experts in various fields to review them carefully.  

## 10. Licensing  

- Repository documentation: CC-BY-4.0.  
- Code snippets: MIT.  
- Third-party publications: redistribute only if licensing permits; otherwise keep hash + link.
