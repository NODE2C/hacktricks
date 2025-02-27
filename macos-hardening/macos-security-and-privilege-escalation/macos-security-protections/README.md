# macOS Security Protections

<details>

<summary><a href="https://cloud.hacktricks.xyz/pentesting-cloud/pentesting-cloud-methodology"><strong>☁️ HackTricks Cloud ☁️</strong></a> -<a href="https://twitter.com/hacktricks_live"><strong>🐦 Twitter 🐦</strong></a> - <a href="https://www.twitch.tv/hacktricks_live/schedule"><strong>🎙️ Twitch 🎙️</strong></a> - <a href="https://www.youtube.com/@hacktricks_LIVE"><strong>🎥 Youtube 🎥</strong></a></summary>

* Do you work in a **cybersecurity company**? Do you want to see your **company advertised in HackTricks**? or do you want to have access to the **latest version of the PEASS or download HackTricks in PDF**? Check the [**SUBSCRIPTION PLANS**](https://github.com/sponsors/carlospolop)!
* Discover [**The PEASS Family**](https://opensea.io/collection/the-peass-family), our collection of exclusive [**NFTs**](https://opensea.io/collection/the-peass-family)
* Get the [**official PEASS & HackTricks swag**](https://peass.creator-spring.com)
* **Join the** [**💬**](https://emojipedia.org/speech-balloon/) [**Discord group**](https://discord.gg/hRep4RUj7f) or the [**telegram group**](https://t.me/peass) or **follow** me on **Twitter** [**🐦**](https://github.com/carlospolop/hacktricks/tree/7af18b62b3bdc423e11444677a6a73d4043511e9/\[https:/emojipedia.org/bird/README.md)[**@carlospolopm**](https://twitter.com/hacktricks\_live)**.**
* **Share your hacking tricks by submitting PRs to the** [**hacktricks repo**](https://github.com/carlospolop/hacktricks) **and** [**hacktricks-cloud repo**](https://github.com/carlospolop/hacktricks-cloud).

</details>

## Gatekeeper

Gatekeeper is usually used to refer to the combination of **Quarantine + Gatekeeper + XProtect**, 3 macOS security modules that will try to **prevent users from executing potentially malicious software downloaded**.

More information in:

{% content-ref url="macos-gatekeeper.md" %}
[macos-gatekeeper.md](macos-gatekeeper.md)
{% endcontent-ref %}

## MRT - Malware Removal Tool

The Malware Removal Tool (MRT) is another part of macOS's security infrastructure. As the name suggests, MRT's main function is to **remove known malware from infected systems**.

Once malware is detected on a Mac (either by XProtect or by some other means), MRT can be used to automatically **remove the malware**. MRT operates silently in the background and typically runs whenever the system is updated or when a new malware definition is downloaded (it looks like the rules MRT has to detect malware are inside the binary).

While both XProtect and MRT are part of macOS's security measures, they perform different functions:

* **XProtect** is a preventative tool. It **checks files as they're downloaded** (via certain applications), and if it detects any known types of malware, it **prevents the file from opening**, thereby preventing the malware from infecting your system in the first place.
* **MRT**, on the other hand, is a **reactive tool**. It operates after malware has been detected on a system, with the goal of removing the offending software to clean up the system.

The MRT application is located in **`/Library/Apple/System/Library/CoreServices/MRT.app`**

## Processes Limitants

### SIP - System Integrity Protection

{% content-ref url="macos-sip.md" %}
[macos-sip.md](macos-sip.md)
{% endcontent-ref %}

### Sandbox

MacOS Sandbox **limits applications** running inside the sandbox to the **allowed actions specified in the Sandbox profile** the app is running with. This helps to ensure that **the application will be accessing only expected resources**.

{% content-ref url="macos-sandbox/" %}
[macos-sandbox](macos-sandbox/)
{% endcontent-ref %}

### TCC - **Transparency, Consent, and Control**

**TCC (Transparency, Consent, and Control)** is a mechanism in macOS to **limit and control application access to certain features**, usually from a privacy perspective. This can include things such as location services, contacts, photos, microphone, camera, accessibility, full disk access, and a bunch more.

{% content-ref url="macos-tcc/" %}
[macos-tcc](macos-tcc/)
{% endcontent-ref %}

## Trust Cache

The Apple macOS trust cache, sometimes also referred to as the AMFI (Apple Mobile File Integrity) cache, is a security mechanism in macOS designed to **prevent unauthorized or malicious software from running**. Essentially, it is a list of cryptographic hashes that the operating system uses to v**erify the integrity and authenticity of the software**.

When an application or executable file tries to run on macOS, the operating system checks the AMFI trust cache. If the **hash of the file is found in the trust cache**, the system **allows** the program to run because it recognises it as trusted.

## Launch Constraints

It controls from where and what can launch an Apple signed binary:

* You can't launch an app directly if should be run by launchd
* You can't run an app outside of the trusted location (like /System/)

<details>

<summary><a href="https://cloud.hacktricks.xyz/pentesting-cloud/pentesting-cloud-methodology"><strong>☁️ HackTricks Cloud ☁️</strong></a> -<a href="https://twitter.com/hacktricks_live"><strong>🐦 Twitter 🐦</strong></a> - <a href="https://www.twitch.tv/hacktricks_live/schedule"><strong>🎙️ Twitch 🎙️</strong></a> - <a href="https://www.youtube.com/@hacktricks_LIVE"><strong>🎥 Youtube 🎥</strong></a></summary>

* Do you work in a **cybersecurity company**? Do you want to see your **company advertised in HackTricks**? or do you want to have access to the **latest version of the PEASS or download HackTricks in PDF**? Check the [**SUBSCRIPTION PLANS**](https://github.com/sponsors/carlospolop)!
* Discover [**The PEASS Family**](https://opensea.io/collection/the-peass-family), our collection of exclusive [**NFTs**](https://opensea.io/collection/the-peass-family)
* Get the [**official PEASS & HackTricks swag**](https://peass.creator-spring.com)
* **Join the** [**💬**](https://emojipedia.org/speech-balloon/) [**Discord group**](https://discord.gg/hRep4RUj7f) or the [**telegram group**](https://t.me/peass) or **follow** me on **Twitter** [**🐦**](https://github.com/carlospolop/hacktricks/tree/7af18b62b3bdc423e11444677a6a73d4043511e9/\[https:/emojipedia.org/bird/README.md)[**@carlospolopm**](https://twitter.com/hacktricks\_live)**.**
* **Share your hacking tricks by submitting PRs to the** [**hacktricks repo**](https://github.com/carlospolop/hacktricks) **and** [**hacktricks-cloud repo**](https://github.com/carlospolop/hacktricks-cloud).

</details>
