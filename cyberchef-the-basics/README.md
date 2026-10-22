# CyberChef: The Basics - TryHackMe

## About the Lab

CyberChef is a browser-based tool developed by GCHQ for performing data transformations, encoding, decoding, encryption, and data extraction. It provides a visual interface that allows users to combine operations into recipes to process and analyze data.

Room: CyberChef: The Basics

Platform: TryHackMe

Status: Completed

## Learning Objectives

- Understand the purpose of CyberChef.
- Identify the four main areas of the interface.
- Learn how to create and manage recipes.
- Understand common encoding and decoding operations.
- Extract IP addresses, email addresses, and URLs.
- Convert between different data formats.
- Process Unix timestamps and URL-encoded strings.

## 1. CyberChef Interface

CyberChef consists of four main areas:

1. Operations: Contains the available operations, including encoding, decoding, and data extraction.
2. Recipe: Allows users to arrange operations and configure their parameters.
3. Input: Accepts text and files for processing.
4. Output: Displays the results of the selected operations.

The Recipe area is considered the heart of CyberChef because it controls how operations are applied to the input data.

## 2. CyberChef Workflow

The basic workflow consists of four steps:

1. Set a clear objective.
2. Enter the data into the Input area.
3. Select the appropriate operations.
4. Check the Output area and repeat the process if necessary.

## 3. Common Operations

### Extractors

- Extract IP addresses: Identifies IPv4 and IPv6 addresses.
- Extract URLs: Finds URLs in the input data.
- Extract email addresses: Identifies email addresses.

### Date and Time

- From UNIX Timestamp: Converts a Unix timestamp into a readable date and time.
- To UNIX Timestamp: Converts a date and time into a Unix timestamp.

### Data Format

- From Base64: Decodes Base64-encoded data.
- To Base64: Encodes data into Base64.
- URL Decode: Converts percent-encoded characters into their original values.
- From Base85: Decodes Base85-encoded data.
- From Base58: Decodes Base58-encoded data.
- To Hex: Converts data into hexadecimal representation.
- To Decimal: Converts data into decimal values.

### Other Operations

- ROT13: Substitutes letters by rotating them 13 positions in the alphabet.
- From Morse Code: Converts Morse code into readable characters.

## 4. Lab Questions and Answers

### Task 2: CyberChef Interface

| Question | Answer |
|---|---|
| In which area can you find From Base64? | Operations |
| Which area is considered the heart of the tool? | Recipe |

### Task 3: CyberChef Workflow

| Question | Answer |
|---|---|
| At which step would you determine, "What do I want to accomplish?" | Step 1: Setting a clear objective |

### Task 4: Common Operations

| Question | Answer |
|---|---|
| What is the hidden email address? | hidden@hotmail.com |
| What is the hidden IP address ending in .232? | 102.20.11.232 |
| Which domain address starts with the letter T? | TryHackMe.com |
| What is the binary value of decimal 78? | 01001110 |
| What is the URL-encoded value of https://tryhackme.com/r/careers? | https%3A%2F%2Ftryhackme%2Ecom%2Fr%2Fcareers |

### Task 5: Practical Exercises

| Question | Answer |
|---|---|
| Which IP starts and ends with 10? | 10.10.2.10 |
| What is the Base64-encoded value of Nice Room!? | TmljZSBSb29tIQ== |
| What is the URL-decoded value of the provided string? | https://tryhackme.com/r/room/cyberchefbasics |
| What is the datetime string for Unix timestamp 1725151258? | Sun 1 September 2024 00:40:58 UTC |
| What is the Base85-decoded string of <+oue+DGm>Ap%u7? | This is fun! |

## 5. Key Takeaways

- CyberChef simplifies common data transformation and decoding tasks.
- Recipes allow multiple operations to be applied in sequence.
- Extractors are useful for identifying indicators such as IP addresses, URLs, and email addresses.
- Base64 and Base85 are encoding formats, not encryption methods.
- URL decoding helps reveal the original content of percent-encoded URLs.
- Unix timestamps can be converted into readable date and time values.
- CyberChef is useful during cybersecurity investigations, digital forensics, and analysis of suspicious data.

## Conclusion

This room introduced the CyberChef interface, its main features, and commonly used operations. The practical exercises demonstrated how to extract indicators, decode encoded strings, and convert data into readable formats.

CyberChef is a valuable tool for cybersecurity analysis, although large-scale processing may require additional tools.
