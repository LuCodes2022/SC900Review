# Basic Security principles

## Why this section
The exam will cover principles of security, which are also important to know in order to better approach the different tools etc of interest.

## CIA

Consider CIA when planning an environment.

- C for confidentiality
- I for integrity
- A for availibility

## Basic Infrastuctures of Interest

Without naming any tool, we can already make a list of important infrastructures:

- Physical Security
- Identity (MFA)
- Perimeter (Distributed Denial of Service)
- Network
- Computing
- Application
- Data (encryption)

## Threats

- Data breach -> focuses on gaining access to data. Threatens your Data.
- Dictionary attacks -> essentially going through a list of passwords. Threatens identity.
- Phishing ->  Sending emails to try and gain user info. Threatens identity.
- Spear phishing -> Sending targeted emails to a specific user to gain their information. Threatens identity.
- Ransomware -> Holding one's data hostage. Threatens availibility.
- Disruptive attack -> Uses DDoS attacks. Threatens availibility.

## Knowing what we do, how do we approach these threats?

### Zero trust

Assume you have been compromised. Therefor verify everything and implement authentification (Authentification/AuthN + Authorization/AuthZ).

Manage privileges by:
- Using just in time
- - Only get privilege, during a limited window, to access data when needed. 
- - Once you are done with th task or your window has passed you will no longer have access.
- Using Just enough
- - give just enough access to do the task. 
- Assume Breach
- - Segment network (anywhere you can)
- - Encrypt
- - Detect Threats (Solutions looking at logs and using machine learning to warn you against potential threats in your systems)

## What can we focus on to accomplish what we need to?

### Identity

- Users, Applications, Devices etc.
- Device Monitoring
- Understand the Applications being used
- Data Classification
- - Encrypt
- - Data Loss Protection 
- Infrastructure

note that here most of what we care about is data.

### Encryption

There are two main forms of encryption:
- Symetric
- - Data -> algorithm using a particular key -> Encrypted Data
- - you use the same key to decrypt
- - Used for large scale data
- - Challenge is how do we exchange the key?
- Asymetric
- - Data -> public key -> Encrypted -> private key -> Decrypted
- - If encrypted with public key it can only be decrypted with the private key
- - for small data you can verify integrity for

How can we verify integrity?

To start we have access to some data, we create a hash for said data then encrypt it using our private key:
- First Hash = Data -> generate hash-> # -> encrypt with private key -> #!
The second person we send the data to receives the data and uses the same algorithm as us to create a hash value:
- Second Hash = Data -> run through same algorithm as first to get hash value -> #
- This person can now decrypt our First Hash using the public key and compare. If First Hash = Second Hash we know we have integrity!


