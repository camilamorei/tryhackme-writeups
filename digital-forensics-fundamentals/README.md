# Digital Forensics Fundamentals

## Room Overview

This room introduces the fundamentals of digital forensics, including forensic methodology, evidence acquisition, Windows forensics, and metadata analysis.

## Task 1: Introduction to Digital Forensics

**Question:** Which team was handed the case by law enforcement?

**Answer:** `Digital Forensics Team`

## Task 2: Digital Forensics Methodology

Digital forensics involves collecting, examining, and analyzing digital evidence to understand what happened during an incident.

**Question:** Which phase of digital forensics is concerned with correlating the collected data to draw conclusions?

**Answer:** `Analysis`

**Question:** Which phase is concerned with extracting the data of interest from the collected evidence?

**Answer:** `Examination`

## Task 3: Evidence Acquisition

Evidence must be collected securely without altering the original data.

### Important Concepts

- **Proper Authorization:** Investigators must obtain the appropriate authorization before collecting evidence.
- **Chain of Custody:** A formal document that records evidence details, collection information, storage locations, and access history.
- **Write Blockers:** Tools that prevent data from being written to a storage device during evidence acquisition, helping preserve its integrity.

### Answers

**Question:** Which tool is used to ensure data integrity during collection?

**Answer:** `Write blocker`

**Question:** What is the name of the document containing all details of the collected digital evidence?

**Answer:** `Chain of custody`

## Task 4: Windows Forensics

Windows forensic investigations commonly involve acquiring disk and memory images.

### Types of Forensic Images

- **Disk Image:** A bit-by-bit copy of a storage device, such as an HDD or SSD. It contains non-volatile data that generally persists after a restart.
- **Memory Image:** A copy of the system's RAM. It contains volatile information, such as running processes, open files, and active network connections.

Memory acquisition should generally be prioritized when volatile evidence is important, because that information can disappear when the system is shut down or restarted.

### Common Tools

| Tool | Purpose |
|---|---|
| FTK Imager | Acquiring and examining disk images |
| Autopsy | Analyzing disk images and recovering digital evidence |
| DumpIt | Acquiring Windows memory images |
| Volatility | Analyzing memory images |

**Question:** Which type of forensic image is taken to collect volatile data from the operating system?

**Answer:** `Memory image`

## Task 5: Practical Example of Digital Forensics

This task demonstrates how file metadata and image EXIF data can provide investigative clues.

### PDF Metadata

The `pdfinfo` utility can display metadata associated with a PDF file, including its author, creator, creation date, and modification date.

Example command:

```bash
pdfinfo ransom-letter.pdf
```

### Image EXIF Metadata

EXIF metadata may contain information such as the camera model, date and time of capture, camera settings, and GPS coordinates.

The `exiftool` utility can be used to inspect this information.

Example command:

```bash
exiftool IMAGE.jpg
```

To display only relevant camera and location details:

```bash
exiftool -Make -Model -GPSPosition IMAGE.jpg
```

GPS coordinates can be searched on a mapping service to identify the location where a photograph was taken, when those coordinates are available.

### Answers

**Question:** Who is listed as the author of `ransom-letter.pdf`?

**Answer:** `Ann Gree Shepherd`

**Question:** What is the name of the street where the kidnappers took the photograph?

**Answer:** `Milk Street`

**Question:** What is the model of the camera used to take the photograph?

**Answer:** `Canon EOS R6`

## Key Takeaways

- Digital forensics follows a structured methodology for examining evidence.
- A documented chain of custody helps establish the integrity and accountability of evidence.
- Write blockers help prevent accidental modification during acquisition.
- Memory images preserve volatile evidence, while disk images preserve storage data.
- PDF metadata and image EXIF data can reveal useful investigative information.

## Tools Covered

- `pdfinfo`
- `exiftool`
- FTK Imager
- Autopsy
- DumpIt
- Volatility

## Disclaimer

This write-up is for educational purposes and documents the answers and concepts covered in the TryHackMe Digital Forensics Fundamentals room.
