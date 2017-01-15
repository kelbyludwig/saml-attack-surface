## attacking saml / sso

### Attack: ACSURL Spoofing
* Description: Crafting a Token Request with an attacker-controlled ACSURL could cause the IdP to send an Auth Token to the attacker-controlled server.
* Impact: Tricking a user to click a link sends authentication tokens to an attacker-controlled server.
* Reference: [On the Security of SAML-based Identity Providers](https://web-in-security.blogspot.com/2015/04/on-security-of-saml-based-identity.html)

### Attack: XXE
* Description: The XML parser allows external entities to be included in the XML.
* Impact: SSRF, File read, DoS

### Attack: XML Signature Wrapping
* Description: Assertions can be added to a signed XML document. This can create a logic flaw that allows the original assertion to be properly validated, but the unsigned assertion is processed.
* Impact: This allows an attacker to create assertions without knowledge of the XML signature private key.
* Reference: [On Breaking SAML: Be Whoever You Want to Be](https://www.nds.rub.de/media/nds/veroeffentlichungen/2012/08/22/BreakingSAML_3.pdf)

### Attack: Replay Attacks
* Description: Authentication Tokens do not have timestamps, the timestamps are not properly validated, overly long validity windows.
* Impact: Leaked tokens can be replayed at a later date. This could mean persistent access via previously used token.
* Reference: [Verification of SAML Tokens - Traps and Pitfalls](https://web-in-security.blogspot.com/2014/10/verification-of-saml-tokens-traps-and.html)

### Attack: Token Recipient Confusion (TRC)
* Description: An attacker redirects a token destined for SP_a as an authentication token for SP_b.
* Impact: If an IdP has multiple SPs, a token for SP_a can be used in SP_b. Impact is context-dependent. Sometimes, the malicious SP is created by the attacker.
* Reference: [Verification of SAML Tokens - Traps and Pitfalls](https://web-in-security.blogspot.com/2014/10/verification-of-saml-tokens-traps-and.html)

### Attack: Signature Stripping.
* Description: If the XML signature logic incorrectly handles signature validation, an attacker can just exclude a signature to create a XML document that passes signature validation.
* Impact: An attacker can trivially spoof signed XML documents.
* Reference: [Verification of SAML Tokens - Traps and Pitfalls](https://web-in-security.blogspot.com/2014/10/verification-of-saml-tokens-traps-and.html)

### Attack: Certificate Faking
* Description: Signatures are validated, but the signing party is not properly authenticated.
* Impact: An attacker can generate certificate and self-sign XML documents.
* Reference: [Verification of SAML Tokens - Traps and Pitfalls](https://web-in-security.blogspot.com/2014/10/verification-of-saml-tokens-traps-and.html)
