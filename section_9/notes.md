# Course

## 3D Secure 2.0 and PSD 2
- PSD2 mandates SCA to be implemented for electronic transactions
- Payment service providers (banks, e-money providers, payment institutions) must apply SCA to all electronic payments (card payments, credit transfers) initiated by the payer unless the payment qualifies as low risk and falls within a set of specified exemptions
- In order to authenticate the transaction, there are 3 parts:
    1. something only the customer HAS
        - something that customer can physically touch: mobile phone which receives an OTP, credit card which customer can hold
    2. something only the customer KNOWS
        - PIN number of a card, the login for online banking
    3. something only the customer IS
        - biometry
- In most countries businesses require only x1 factor of authentication == single factor authentication: CC & CVV
- SCA in general means that customer should at least provide x2 factors of authentication to complete the transaction
- Example:
    - Someone wants to make a purchase from an e-commerce
    - One enters CC and CVV (something only the customer HAS)
    - Next, one enters OTP (something only the customer KNOWS)
    - Payment proceeds further

# Research

## PSD2
- source: https://www.jpmorgan.com/europe/merchant-services/insights/PSD2-all-you-need-to-know
- PSD2 (Payment Services Directive 2) aims to reduce fraud and improve consumer choice:
    1. SCA (Strong Customer Authentication) is mandated under PSD2 from 31 Dec 2020 and will be required for all EU e-commerce transactions
    2. The challenge is to reduce and manage fraud without negatively impacting the customer experience
    3. The emergence of TPPs (Third Party Providers) is expected to drive payments innovation and competition
- (1) and (3) are the key elements of PSD2

## SCA
- source: https://www.jpmorgan.com/europe/merchant-services/insights/PSD2-all-you-need-to-know
- The core principle of SCA is to reduce payment fraud with minimal impact on the customer experience
    - i.e. without introducing too much friction into the payment process
- The key enabler is 2FA (Two-Factor authentication)
    - Consumers need to provide x2 pieces of information to prove they are who they say they are:
        - something they OWN: something that only the customer owns (e.g. a phone)
        - something they KNOW: something that only the customer knows (e.g. a PIN code)
        - something they ARE: something that characterises only the customer (e.g. a fingerprint)
- The standard industry protocol is 3D Secure (3DS)
    - 3DS 2.1 allows for new auth processes such as fingerprints or facial recognition
    - 3DS 2.1 improves a user-friendly payment process on mobile devices
    - 3DS 2.1 complements digital wallets such as Apple Pay or Google Pay
    - 3DS 2.2 enables Merchants to claim some of the exemptions listed below
- Some transactions will be exempt from authentication:
    - low-value transactions
    - recurring transactions
    - cases when a user has 'whitelisted' the merchant by indicating they shop there often and they don't wish to be authenticated

## TPPs
- Currently the main way for cusomters to access their bank accounts is through the products and channels provided by their banks
- Under PSD2 x2 new regulated entities will emerge:
    1. PISP - Payment Initiation Service Providers
    2. AISP - Account Information Service Providers
- PISP allow 3rd party companies to initiate payment on behalf of a consumer without them having to visit their online banks portal
- AISP allow third 3rd party companies to access a consumers bank, as well as display information relating to their account
    - In order to facilitate AISPs, banks will have to provide their APIs to those that request it
    - Potentially, merchants could utilise an AISP to get more information about a potential consumer (their account balance, payment flows) and use it to make risk assessments
