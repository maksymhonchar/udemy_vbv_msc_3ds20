# Course

## Additional Data Points provided by 3DS 2.0 
- 3DS 1.0 Data (source: Initial message - VEReq):
    - Acquirer:
        - Acquirer BIN
        - Acquirer Merchant ID
    - Browser:
        - Browser User-Agent
    - Cardholder:
        - Cardholder account number
    - DS (Directory Server):
        - DS URL
    - Message:
        - Message, Extension, Version
- 3DS 2.0 Data (source: Initial message - AReq):
    - Acquirer:
        - Acquirer BIN
        - Acquirer Merchant ID
    - Browser:
        - Browser User-Agent
        - Browser Accept Headers
        - Browser Java Enabled, Language, Screen Color Depth, Height, Width
        - Browser Time Zone
    - Device Channel, Device Information, Rendering Options supported
    - Purchase:
        - Purchase Amount, Currency, Date&Time
        - Purchase Date & Time
        - Recurring Expiry, Frequency
        - Instalment Payment Data
    - Cardholder:
        - Cardholder Account Number
        - Cardholder Account Identifier, Billing Address
        - Cardholder Account Information (Account age, change, password change, number of transactions per day/year, shipping name indicator, suspicious activity, payment account age etc)
        - Cardholder Email Address, Home Phone Number, Mobile Phone Number, Work Phone Number
        - Cardholder Name
        - Cardholder Shipping Address
        - Card Expiry Date
    - Merchant:
        - Merchant Category Code
        - Merchant Country Code
        - Merchant Country Code
        - Merchant Name
        - Merchant Risk Indicator (Delivery timeframe, re-order, pre-order, gift card)
    - DS (Directory Server):
        - DS URL
        - DS Reference Number, Transaction ID
    - 3DS Requestor/Server:
        - 3DS Requestor Authentication Information (Method), Challenge indicator, ID, Initiated Indicator
        - 3DS Requestor Name, Non-payment Indicator, Prior Transaction Authentication information
        - 3DS Requestor URL
        - 3DS Server Reference Number, Operator ID, Transaciton ID, URL
    - SDK:
        - SDK App ID, SDK Encrypted Date, Ephemeral Public Key
        - SDK Reference Number, SDK Transaction ID
    - Message:
        - Message Category, Extension, Type, Version
        - Message Category, Type
    - Transaction Type
    - Account Type
    - Address Match Indicator
    - IP Address

# Research

## VEReq
- source: https://developer.cybersource.com/library/documentation/dev_guides/Payer_Authentication_SCMP_API/html/Topics/Payer_Authentication_Detail_Report.htm#XREF_89979_VEReq
- Verify Enrollment Request (VEReq) sent by the merchant’s server to the directory server and by the directory server to the ACS to determine whether authentication is available for the customer’s card number.

## 3DS 2.0 Data elements (another source)
- source: https://epayments.developer-ingenico.com/best-practices/services/3dsv2/implementation/
- Generally, the data elements can be categorized in the following categories:
    1. Card details
        - recurring information
        - unscheduled card on file information
        - link to a previous transaction with SAC
    2. 3D Secure specific information
        - previous 3D Secure results
        - Specific 'settings' for this transaction
    3. Transaction information
        - billing address data
        - shipping details
        - transaction channel
        - meta information on what the transaction is for
    4. Consumer
        - device/browser data
        - account of the consumer with you
            - authentication used
            - account on file
            - payment history
