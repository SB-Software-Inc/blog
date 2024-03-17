---
publishDate: 'Dec 21 2022'
title: 'Protecting Your Code: A Guide to Avoiding Malicious Package Attacks'
excerpt: 'Recent attacks on software developers through the use of malicious packages in npm and PyPI have made headlines. This guide covers how developers can protect themselves and their systems from such threats.'
image: '~/assets/images/matrix.webp'
category: 'Guide'
tags: [cybersecurity, information technology, software, python, nodejs]
---

## Introduction

In recent weeks, there have been several cyber-attacks on software developers through the use of malicious packages in package management systems such as npm (for JavaScript) and PyPI (for Python). These attacks typically involve the publication of malicious packages with names that are similar to popular, legitimate packages. Developers who install these packages may inadvertently execute malicious code, potentially leading to data theft, system compromise, or other harmful repercussions.

There are numerous ways that attackers can exploit these package management systems, including the utilization of typosquatting (creating packages with names similar to popular packages but with slight misspellings) or using social engineering tactics to trick developers into installing these malicious packages.

It is important for developers to be aware of these threats and to take steps to protect themselves and their systems from falling victim to them. This includes carefully verifying the source and authenticity of packages before installing them and keeping all software and package management systems up to date with the latest security patches.

### What Packages were compromised?

In the case of PyPI, multiple packages were compromised, including:

-   [**requests**](https://pypi.org/project/requests/): a popular package for making HTTP requests
    -   The following typosquatted packages were used ([Phylum](https://blog.phylum.io/phylum-detects-active-typosquatting-campaign-in-pypi)):
        -   `dequests`
        -   `fequests`
        -   `gequests`
        -   `rdquests`
        -   `reauests`
        -   `reduests`
        -   `reeuests`
        -   `reqhests`
        -   `reqkests`
        -   `requesfs`
        -   `requesta`
        -   `requeste`
        -   `requestw`
        -   `requfsts`
        -   `resuests`
        -   `rewuests`
        -   `rfquests`
        -   `rrquests`
        -   `rwquests`
        -   `r1quests`
        -   `r4quests`
        -   `r3quests`
        -   `r5quests`
        -   `req7ests`
        -   `req8ests`
        -   `tequests`
-   [**telnetlib**](https://pypi.org/project/telnetlib3/): a popular package for making Telnet connections
    -   The following typosquatted package was used ([Phylum](https://blog.phylum.io/phylum-detects-active-typosquatting-campaign-in-pypi))
        -   `telnservrr`

Most recently, SentinelOne was targeted by a similar attack on PyPI. The malicious package was named `SentinelOne` ([ReversingLabs](https://blog.reversinglabs.com/blog/sentinelsneak-malicious-pypi-module-poses-as-security-sdk)). It claimed to be an SDK for the company's official API, but it hid a malicious payload that was designed to steal sensitive data from the victim's system, including, credentials, SSH keys, and configuration data.

-   The following packages were also uploaded by the same account:
    -   `SentinelOne-sdk`
    -   `SentinelOneSDK`

In the case of npm, the following packages were compromised:

-   [**discord.js**](https://discord.js.org/#/)
    -   The following typosquatted packages were used ([Phylum](https://blog.phylum.io/phylum-detects-active-typosquatting-campaign-in-pypi)):
        -   `discordallintsbot`
        -   `discordselfbot16`
        -   `discord-all-intents-bot`
        -   `discors.jd`
        -   `discord-selfbot-v13`
        -   `discord-all-intents-default`
-   [**telnet-client**](https://www.npmjs.com/package/telnet-client)
    -   The following typosquatted package was used ([Phylum](https://blog.phylum.io/phylum-detects-active-typosquatting-campaign-in-pypi)):
        -   `telnservrr`

---

## How to Protect Yourself

### Part 1: Verify the Source and Authenticity of Packages

-   Be cautious when installing packages from unfamiliar sources or with unfamiliar names.
-   Check the publisher's website and social media accounts to verify that they are legitimate.
-   Look for reviews or comments from other users who have installed the package.
-   Check the package's code repository to ensure that it appears legitimate and is being actively maintained.

### Part 2: Keep Your Software and Package Management Systems Up to Date

-   Regularly check for and install updates to your software and package management systems.
-   Use a package manager that automatically installs security patches and updates.

### Part 3: Use a Package Lock or Shrinkwrap File

-   A package lock or shrinkwrap file is a list of the specific versions of packages that your project depends on.
-   By using a package lock or shrinkwrap file, you can ensure that the exact same versions of packages are installed every time you run "npm install" or "pip install", preventing any unexpected updates that could potentially introduce malicious code.

### Part 4: Use a Dependency Scanner

-   Dependency scanners are tools that scan your project's dependencies for known vulnerabilities.
-   By using a dependency scanner, you can identify and address potential security risks before they become a problem.

### Part 5: Educate Your Team

-   Make sure that all members of your team are aware of the risks of malicious packages and the importance of verifying the source and authenticity of packages before installing them.
-   Consider implementing a process for reviewing and approving the use of third-party packages in your projects.

---

## Conclusion

Therefore, attacks through malicious packages in package management systems can be serious threats to software developers. By following best practices such as verifying the source and authenticity of packages, keeping your software and package management systems up to date, using a package lock or shrinkwrap file, and using a dependency scanner, you can help protect yourself and your projects from these types of attacks. It is also important to educate your team and establish processes to ensure that everyone is aware of the risks and how to mitigate them. By taking these precautionary measures, you can safeguard the security and integrity of your code and systems.

---

## References

-   [Phylum Detects Active Typosquatting Campaign in PyPI](https://blog.phylum.io/phylum-detects-active-typosquatting-campaign-in-pypi)
-   [SentinelSneak: Malicious PyPI Module Poses as Security SDK](https://blog.reversinglabs.com/blog/sentinelsneak-malicious-pypi-module-poses-as-security-sdk)
