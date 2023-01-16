# Course

## 3DS Transaction flow
1. Issuer Domain:
    1.1. Cardholder
    1.2. Access Control Server (ACS)
2. Interoperability Domain
    2.1. Directory Server (DS)
    2.2. Authentication History Server (AHS)
3. Acquirer Domain
    3.1. Merchant via Merchant Server with Merchant Plug-In (MPI)
    3.2. Acquirer Payment Gateway

## Important Terminologies in the transaction flow
- Merchant/Acquirer Domain
    - 3DS Requestor: the entity that is requesting an EMV 3DS authentication to occur (i.e. merchant or payment app)
    - 3DS Integrator: EMV 3DS function that provides integration services in the 3DS Requestor Environment (i.e. payment provider or other entity)
    - 3DS Server: EMV 3DS component that handles the interaction with the 3DS Requestor environment and the 3DS environment and messaging
    - 3DS Client: The consumer-facing component that integrates 3DS functionality (i.e. browser with code or mobile app with 3DS SDK)
- Interoperability Domain
    - Directory Server (DS):
        - Generally managed by payment network
        - Authenticates the 3DS Server requests and validates the 3DS requestor as trusted and registered
        - Maintains account and ACS routing data, and routes 3DS messages between the 3DS Server and the ACS
        - DS holds a "directory" of all the BIN ranges corresponding issuing banks
        - The DS will receive the message from the MPI, check the card number against the BIN range directory that it holds, and forward that message onto the correct issuing bank
- Issuer Domain
    - Access Control Server (ACS):
        - Account issuer managed system
        - Verifies whether authentication is available for a card number and device type
        - Provides a risk based assessment to facilitate frictionless flows when appropriate
        - Manages the cardholder challenge (step-up) when required though standardized messages and user interfaces

- Merchant Plug-IN (MPI):
    - The acquiring domain is where the merchant, payment gateway, and acquiring banks sit
    - Initiates the transaction, which they wish to be authenticated. Entities in the acquiring space need to deploy a "merchant plug-in", also known as "MPI"
    - MPI identifies the account number and queries the servers of the card issuer (Visa, MC etc) to determine if it is enrolled in a 3D-Secure program and returns the website address of the issuer ACS if it is found

## Flow by VISA
1. Cardholder enters his/her Visa account details
2. The merchant's 3-D Secure service provider packages the message with transaction data and delivers it to the issuer via authentication request
3. The issuer's 3-D Secure service provider determines the transaction risk and may prompt the cardholder to verify his/her identity with i.e. a one-time password
4. Issuer sends the authentication result to the merchant
5. Merchant submits transaction for authorization with a flag indicating the authentication result
