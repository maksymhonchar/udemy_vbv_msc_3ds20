# Course

## Transaction Logic Flow 3DS 1.0
- Flow for 3DS enrolled cards
    1. Create Payment
    2. Authentication step
        2.1. Is card enrolled? YES, enrolled. Authentication required
        2.2. Response with redirect details
        2.3. Consumer Authentication at Issuer
    3. Authorization step
        3.1. do an async webhook event :)
        3.2. Consumer returns to your site
        3.3. Retrieve Payment API
    4. Get Results

- Flow for 3DS NOT enrolled cards:
    1. Create Payment
    2. Authentication step
        2.1. Is card enrolled? NO, not enrolled. No Auth required
    3. Authorization step
        3.1. do an async webhook event :)
    4. Get Results

## Transaction Logic Flow 3DS 2.0
- Flow when Merchant/Merchant Acquirer does not want Customer to redirect to 3DS page
    1. Create Payment
    2. Redirect? YES. Issuer evaluation and/or Challenge required
        2.1. Response with redirect details
        2.2. Consumer Auth by Issuer
    3. Authentication
        3.1. async webhook event
        3.2. consumer returns to Merchant's site
        3.3. Retrieve Payment API
    4. Get results
- Flow when Merchant opts for frictionless flow:
    1. Create Payment
    2. Redirect? NO. No Issuer evaluation and Challenge required
    3. Authorization
        3.1. async webhook event
    4. Get results

## Liability shift
- Liability shift is one of the benefits of 3D secure
- Liability shift means that the liability of the transaction authentication will now shift to the issuing bank
- By having cardholders authenticate themselves to the bank that issued their credit/debit card, fraud responsibility shifts away from the merchant and toward the card issuer, reducing chargebacks to the merchant

# Research

## High-level implementation of 3DS
- source: https://epayments.developer-ingenico.com/best-practices/services/3dsv2/implementation/
- The key aspect of 3-D Secure version 2 is the ability of the issuing bank to better assess the risk involved of the transaction
