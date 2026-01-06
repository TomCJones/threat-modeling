# File Formats 

For file formats, at least the following forms of threats/attacks categories MUST be considered, using the **CLAMPI** mnemonics:

| Letter | Threat Category | Example Attack |
| ----- | ----- | ----- |
| **C** | Code (Executable / Script Injection) | Embed Executable Code (e.g., Macro, malicious JS) |
| **L** | Links / External Resources | Remote fetch, SSRF, exfil link, integrity while loading external resources… |
| **A** | Archive  (Compression / Decompression) | ZIP bomb, decompression loop |
| **M** | Metadata Manipulation | Hidden author info, exfil in EXIF |
| **P** | Parsing (Loading and Serializing) | Buffer overflow, parser confusion |
| **I** | Integrity | Tampered payload, checksum mismatch |
