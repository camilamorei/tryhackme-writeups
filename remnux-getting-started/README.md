# REMnux: Getting Started

## Overview

This room introduces REMnux, a Linux distribution designed for analyzing potentially malicious software, documents, files, and memory captures.

REMnux includes several tools that help cybersecurity professionals investigate suspicious files, simulate network services, and preprocess digital forensic evidence.

## Task 1: Set Up Your Virtual Environment

The lab uses the REMnux virtual machine and the AttackBox.

Most files used throughout the room are located in:

```text
/home/ubuntu/Desktop/tasks/
```

## Task 2: Analyzing OLE2 Files

### Tool: `oledump.py`

`oledump.py` is a Python tool used to analyze OLE2 files, also known as Structured Storage or Compound File Binary Format files.

It identifies data streams inside a file and helps analysts inspect potentially suspicious content, including macros.

### Questions and Answers

| Question | Answer |
|---|---|
| Python tool used to analyze OLE2 files | `oledump.py` |
| Parameter used to select a particular data stream | `-s` |
| PowerShell command commonly used to download files from the internet | `Invoke-WebRequest` |
| File downloaded by the PowerShell script | `Doc-3737122pdf.exe` |
| Variable indicating where the downloaded file is stored | `$TempFile` |
| Number of data streams in `possible_malicious.docx` | `16` |
| Data stream containing a macro | `8` |

### Example

The file analyzed in this task was located at:

```text
/home/ubuntu/Desktop/tasks/agenttesla/possible_malicious.docx
```

## Task 3: Simulating a Fake Network with INetSim

### Tool: INetSim

INetSim stands for Internet Services Simulation Suite. It simulates internet services in a controlled environment, allowing analysts to observe suspicious software attempting to communicate with external servers.

### Configuration

First, identify the REMnux IP address:

```bash
ifconfig
```

Edit the INetSim configuration file:

```bash
sudo nano /etc/inetsim/inetsim.conf
```

Update the `dns_default_ip` setting with the REMnux machine's IP address.

Verify the configuration:

```bash
cat /etc/inetsim/inetsim.conf | grep dns_default_ip
```

Start INetSim:

```bash
sudo inetsim
```

The output should indicate:

```text
Simulation running.
```

### Downloading Simulated Payloads

From the AttackBox, use the following command to download a simulated file:

```bash
sudo wget https://10.65.160.20/second_payload.zip --no-check-certificate
```

Another example:

```bash
sudo wget https://10.65.160.20/second_payload.ps1 --no-check-certificate
```

These are simulated files used to demonstrate how malware may attempt to download additional payloads.

### Connection Reports

INetSim stores session reports in:

```text
/var/log/inetsim/report/
```

Read a report with:

```bash
sudo cat /var/log/inetsim/report/report.2594.txt
```

The report records connection details, including timestamps, protocols, requested URLs, HTTP methods, and the simulated files returned.

### Questions and Answers

| Question | Answer |
|---|---|
| Flag retrieved from `flag.txt` | `Tryhackme{remnux_edition}` |
| URL method used to retrieve `flag.txt` | `GET` |

## Task 4: Preprocessing Memory Images with Volatility

### Tool: Volatility 3

Volatility is a memory forensics framework used to investigate memory images and extract information about processes, command-line arguments, loaded modules, files, and potentially injected code.

The memory image used in this task was:

```text
/home/ubuntu/Desktop/tasks/Wcry_memory_image/wcry.mem
```

### Important Plugins

| Plugin | Purpose |
|---|---|
| `windows.pstree.PsTree` | Lists processes in a tree based on parent process IDs |
| `windows.pslist.PsList` | Lists active processes |
| `windows.cmdline.CmdLine` | Displays process command-line arguments |
| `windows.filescan.FileScan` | Scans memory for file objects |
| `windows.dlllist.DllList` | Lists modules loaded by processes |
| `windows.malfind.Malfind` | Identifies memory regions that may contain injected code |
| `windows.psscan.PsScan` | Scans memory for process objects |

### Running Volatility

Example commands:

```bash
vol3 -f wcry.mem windows.pstree.PsTree
```

```bash
vol3 -f wcry.mem windows.pslist.PsList
```

```bash
vol3 -f wcry.mem windows.malfind.Malfind
```

### Preprocessing Multiple Plugins

The following loop runs several plugins and saves their output to separate text files:

```bash
for plugin in windows.malfind.Malfind windows.psscan.PsScan windows.pstree.PsTree windows.pslist.PsList windows.cmdline.CmdLine windows.filescan.FileScan windows.dlllist.DllList; do
    vol3 -q -f wcry.mem $plugin > wcry.$plugin.txt
done
```

The `-q` option suppresses progress output, while `-f` specifies the memory image.

### Questions and Answers

| Question | Answer |
|---|---|
| Plugin that lists processes in a tree | `windows.pstree.PsTree` |
| Plugin that lists active processes | `windows.pslist.PsList` |
| Linux utility used to extract strings | `strings` |
| First process identified by `Malfind` as suspected of code injection | `csrss.exe` |
| Second process identified by `Malfind` as suspected of code injection | `winlogon.exe` |
| Directory of `@WanaDecryptor@.exe` | `C:\Intel\ivecuqmanpnirkt615\@WanaDecryptor@.exe` |

## Task 5: Preprocessing Memory Images with Strings

The Linux `strings` utility extracts printable strings from files. Different encodings can reveal additional information from memory images.

### Extracting ASCII Strings

```bash
strings wcry.mem > wcry.strings.ascii.txt
```

### Extracting 16-bit Little-Endian Strings

```bash
strings -e l wcry.mem > wcry.strings.unicode_little_endian.txt
```

### Extracting 16-bit Big-Endian Strings

```bash
strings -e b wcry.mem > wcry.strings.unicode_big_endian.txt
```

These commands generate text files that can be searched during subsequent forensic analysis.

## Key Takeaways

- REMnux provides a dedicated environment for malware analysis and digital forensics.
- `oledump.py` helps investigate OLE2 files and identify suspicious streams.
- INetSim simulates internet services to help analyze network behavior safely.
- Volatility 3 extracts forensic artifacts from memory images.
- The `strings` utility extracts readable text in different encodings.
- Preprocessing evidence into text files makes investigations easier to search and review.

## Conclusion

This room provided hands-on experience with tools included in REMnux for document analysis, network simulation, and memory forensics.

These skills are useful foundations for malware analysis, incident response, and digital forensics.

## References

- [TryHackMe](https://tryhackme.com/)
- [REMnux Documentation](https://docs.remnux.org/)
- [Volatility 3 Documentation](https://volatility3.readthedocs.io/en/stable/volatility3.plugins.html)
- [INetSim](https://www.inetsim.org/)
