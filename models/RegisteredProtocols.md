Browsers support a wide range of **media codecs and streaming protocols**, but the exact list depends on the browser, operating system, and installed components. Here's a breakdown of the most commonly supported ones:

---

### 🎥 **Video Codecs**
These are used to compress and decompress video streams:

| Codec       | Full Name                     | Common Containers | Browser Support |
|-------------|-------------------------------|-------------------|------------------|
| **H.264**   | AVC (Advanced Video Coding)   | MP4, 3GP          | Widely supported |
| **H.265**   | HEVC (High Efficiency Video Coding) | MP4         | Limited (Safari, some Edge) |
| **AV1**     | AOMedia Video 1               | MP4, WebM         | Chrome, Firefox, Edge (modern) |
| **VP8**     | Video Processor 8             | WebM, Ogg         | Chrome, Firefox, Edge |
| **VP9**     | Video Processor 9             | WebM, MP4         | Chrome, Firefox, Edge |
| **Theora**  | —                             | Ogg               | Firefox, older browsers |

Source: [MDN Web Docs – Web video codec guide](https://developer.mozilla.org/docs/Web/Media/Guides/Formats/Video_codecs)

---

### 🔊 **Audio Codecs**
Used for compressing audio streams:

| Codec     | Common Use        | Browser Support |
|-----------|-------------------|------------------|
| **AAC**   | MP4 audio         | Universal        |
| **MP3**   | Legacy support    | Universal        |
| **Opus**  | WebRTC, WebM      | Chrome, Firefox, Edge |
| **Vorbis**| Ogg, WebM         | Firefox, Chrome  |
| **FLAC**  | Lossless audio    | Chrome, Firefox  |

---

### 🌐 **Streaming Protocols**
These define how media is delivered over the network:

| Protocol | Description                              | Browser Support |
|----------|------------------------------------------|------------------|
| **HLS**  | HTTP Live Streaming (Apple)              | Safari natively, others via Media Source Extensions |
| **DASH** | Dynamic Adaptive Streaming over HTTP     | Chrome, Firefox, Edge (via MSE) |
| **RTMP** | Real-Time Messaging Protocol             | Not natively supported (requires Flash or server-side conversion) |
| **WebRTC** | Real-time peer-to-peer communication   | Chrome, Firefox, Edge, Safari |
| **RTSP** | Real-Time Streaming Protocol             | Not supported directly in browsers |

Source: [Brightcove HTML5 Video Formats](https://bing.com/search?q=list+of+protocols+video+codecs+registered+by+browser), [Flussonic Streaming Protocols Guide](https://bing.com/search?q=list+of+protocols+video+codecs+registered+by+browser)

===============================

Registration protocols in the browser—such as those used to register **media types, custom protocols, or credential handlers**—serve a foundational purpose: enabling websites or installed web applications to **interact securely and predictably with browser features** or external systems.

Here’s what they’re designed to do:

---

### 🛂 **1. Declare Capability**
Web apps can register that they’re able to handle certain types of content or actions, like:
- Media codecs (e.g. H.264, AV1)
- File types (e.g. `.pdf`, `.webm`)
- Protocols (e.g. `mailto:`, `web+custom:`)
- Credential formats (e.g. verifiable credentials via `navigator.credentials`)

This lets the browser know **what to do when encountering specific data or links.**

---

### 🔐 **2. Enforce Trust Boundaries**
Only **registered, user-approved applications** can respond to certain actions—like a digital wallet being asked to present credentials or a PWA (Progressive Web App) receiving a shared file. This prevents rogue sites from impersonating trusted apps.

---

### 🧩 **3. Enable Extensibility and Modularity**
By allowing apps to register for specific formats or tasks, browsers support a **plug-in–like model**—without compromising sandboxing or security. For example:
- A media player registers to handle new video codecs via `MediaSource.isTypeSupported()`
- A wallet registers via the Credential Handler API to provide cryptographic proofs

---

### 🧭 **4. Align with User Intent**
With registration, a **user’s choice gets honored**, rather than hardcoded defaults. This is especially important for identity, credential sharing, or default app behaviors on mobile browsers.

---

### 🧠 **Why It Matters for Privacy and Control**
If misused, registration protocols could open the door to **metadata leaks or surveillance**. That’s why groups like the W3C and browser vendors add:
- **Permission prompts**
- **User mediation requirements**
- **Origin-based security models**

---

If you’d like, we can explore how registration protocols play into credential wallets, DID-based identity systems, or how browsers differ (e.g. Chrome’s vs. Safari’s approach). Want to dive deeper?


Credential Handlers are browser-based components that allow websites or applications to **interact with digital wallets or identity providers** using a consistent, privacy-aware interface. They play a central role in ecosystems involving **Verifiable Credentials**, **decentralized identifiers (DIDs)**, and **self-sovereign identity (SSI)** models.

---

### 🧩 What is a Credential Handler?

It’s a **JavaScript-based service**—usually implemented as a Progressive Web App (PWA) or WebExtension—that registers itself with the browser to **handle credential-related tasks**, such as:

- Responding to requests for **presentation of credentials** (e.g. “Prove your age”)
- Facilitating **credential issuance** (e.g. storing a university diploma in a wallet)
- Managing **user consent and disclosure** before sharing data

The Credential Handler is registered using the `navigator.credentials` API and supports protocols like **WebCredential Handler API**, **OpenID for Verifiable Presentations (OID4VP)**, or **CHAPI** (Credential Handler API from the Decentralized Identity Foundation).

---

### 🔒 Why They Matter

Credential Handlers:

- **Give users control**: They sit between websites (relying parties) and wallets (credential stores), ensuring users approve each interaction.
- **Enable privacy-preserving data exchange**: They support selective disclosure (sharing only necessary attributes).
- **Support ecosystem interoperability**: Handlers abstract the wallet logic, allowing different issuers/verifiers to plug into the ecosystem without needing custom integration.

---

### 🛠️ Real-World Example

Say a job portal wants to verify a digital degree certificate. The flow might look like this:
1. The portal requests a credential via browser.
2. The Credential Handler intercepts the request.
3. It prompts the user to select a credential from their wallet.
4. With user consent, it sends a verifiable presentation back to the portal.

---

Credential Handlers help create a secure, user-centric web where people can **prove who they are—without leaking everything about themselves**. Want to explore how this fits into larger architectures like eIDAS 2.0, ISO 18013-7, or mobile driver’s licenses? I can map that out for you.
