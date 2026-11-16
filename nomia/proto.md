# Protocol Documentation
<a name="top"></a>

## Table of Contents

- [canonical_gateway/v1/event.proto](#canonical_gateway_v1_event-proto)
    - [DEUNAEvent](#canonical_gateway-v1-DEUNAEvent)
  
- [canonical_gateway/v1/common.proto](#canonical_gateway_v1_common-proto)
    - [CanonicalAddress](#canonical_gateway-v1-CanonicalAddress)
    - [CanonicalAddressInformation](#canonical_gateway-v1-CanonicalAddressInformation)
    - [CanonicalAirlineInformation](#canonical_gateway-v1-CanonicalAirlineInformation)
    - [CanonicalAmount](#canonical_gateway-v1-CanonicalAmount)
    - [CanonicalAmounts](#canonical_gateway-v1-CanonicalAmounts)
    - [CanonicalAncillary](#canonical_gateway-v1-CanonicalAncillary)
    - [CanonicalAvsFields](#canonical_gateway-v1-CanonicalAvsFields)
    - [CanonicalBankListReference](#canonical_gateway-v1-CanonicalBankListReference)
    - [CanonicalBankListReferenceInstitution](#canonical_gateway-v1-CanonicalBankListReferenceInstitution)
    - [CanonicalBankListResponse](#canonical_gateway-v1-CanonicalBankListResponse)
    - [CanonicalBankTransferProcessorRequestFields](#canonical_gateway-v1-CanonicalBankTransferProcessorRequestFields)
    - [CanonicalBankTransferProcessorResponseFields](#canonical_gateway-v1-CanonicalBankTransferProcessorResponseFields)
    - [CanonicalBinData](#canonical_gateway-v1-CanonicalBinData)
    - [CanonicalBookingItems](#canonical_gateway-v1-CanonicalBookingItems)
    - [CanonicalBuyNowPayLaterPaymentProcessorResponseFields](#canonical_gateway-v1-CanonicalBuyNowPayLaterPaymentProcessorResponseFields)
    - [CanonicalCancelOrderRequestData](#canonical_gateway-v1-CanonicalCancelOrderRequestData)
    - [CanonicalCancelOrderResponseData](#canonical_gateway-v1-CanonicalCancelOrderResponseData)
    - [CanonicalCardToken](#canonical_gateway-v1-CanonicalCardToken)
    - [CanonicalCardValidationDetails](#canonical_gateway-v1-CanonicalCardValidationDetails)
    - [CanonicalConsentRequestFields](#canonical_gateway-v1-CanonicalConsentRequestFields)
    - [CanonicalConsentResponseFields](#canonical_gateway-v1-CanonicalConsentResponseFields)
    - [CanonicalCookie](#canonical_gateway-v1-CanonicalCookie)
    - [CanonicalCreateCardTokenRequestFields](#canonical_gateway-v1-CanonicalCreateCardTokenRequestFields)
    - [CanonicalCreateCardTokenResponseFields](#canonical_gateway-v1-CanonicalCreateCardTokenResponseFields)
    - [CanonicalCredentials](#canonical_gateway-v1-CanonicalCredentials)
    - [CanonicalCreditCard](#canonical_gateway-v1-CanonicalCreditCard)
    - [CanonicalDate](#canonical_gateway-v1-CanonicalDate)
    - [CanonicalDiscount](#canonical_gateway-v1-CanonicalDiscount)
    - [CanonicalFreeShipping](#canonical_gateway-v1-CanonicalFreeShipping)
    - [CanonicalInstallmentPlanRequestFields](#canonical_gateway-v1-CanonicalInstallmentPlanRequestFields)
    - [CanonicalInstallmentPlanResponseFields](#canonical_gateway-v1-CanonicalInstallmentPlanResponseFields)
    - [CanonicalInstallmentTax](#canonical_gateway-v1-CanonicalInstallmentTax)
    - [CanonicalInstallments](#canonical_gateway-v1-CanonicalInstallments)
    - [CanonicalIso8583](#canonical_gateway-v1-CanonicalIso8583)
    - [CanonicalIso8583ReversalFields](#canonical_gateway-v1-CanonicalIso8583ReversalFields)
    - [CanonicalItem](#canonical_gateway-v1-CanonicalItem)
    - [CanonicalLeg](#canonical_gateway-v1-CanonicalLeg)
    - [CanonicalLocation](#canonical_gateway-v1-CanonicalLocation)
    - [CanonicalNetworkTokenData](#canonical_gateway-v1-CanonicalNetworkTokenData)
    - [CanonicalNumber](#canonical_gateway-v1-CanonicalNumber)
    - [CanonicalPassenger](#canonical_gateway-v1-CanonicalPassenger)
    - [CanonicalPaymentCredentialsResponseFields](#canonical_gateway-v1-CanonicalPaymentCredentialsResponseFields)
    - [CanonicalPaymentMethodsResponseFields](#canonical_gateway-v1-CanonicalPaymentMethodsResponseFields)
    - [CanonicalPaymentProcessor](#canonical_gateway-v1-CanonicalPaymentProcessor)
    - [CanonicalPerson](#canonical_gateway-v1-CanonicalPerson)
    - [CanonicalPersonIdentifier](#canonical_gateway-v1-CanonicalPersonIdentifier)
    - [CanonicalRawRequest](#canonical_gateway-v1-CanonicalRawRequest)
    - [CanonicalRawResponse](#canonical_gateway-v1-CanonicalRawResponse)
    - [CanonicalRecurrence](#canonical_gateway-v1-CanonicalRecurrence)
    - [CanonicalRedirectUrls](#canonical_gateway-v1-CanonicalRedirectUrls)
    - [CanonicalReferenceProcessorResponseFields](#canonical_gateway-v1-CanonicalReferenceProcessorResponseFields)
    - [CanonicalReversalFields](#canonical_gateway-v1-CanonicalReversalFields)
    - [CanonicalSCAExemptionDetails](#canonical_gateway-v1-CanonicalSCAExemptionDetails)
    - [CanonicalSelectInstallmentsResponseFields](#canonical_gateway-v1-CanonicalSelectInstallmentsResponseFields)
    - [CanonicalSplitRecipient](#canonical_gateway-v1-CanonicalSplitRecipient)
    - [CanonicalSplitRecipientOptions](#canonical_gateway-v1-CanonicalSplitRecipientOptions)
    - [CanonicalStandardError](#canonical_gateway-v1-CanonicalStandardError)
    - [CanonicalStepDetail](#canonical_gateway-v1-CanonicalStepDetail)
    - [CanonicalThreeDSProcessorRequestFields](#canonical_gateway-v1-CanonicalThreeDSProcessorRequestFields)
    - [CanonicalThreeDSProcessorResponseFields](#canonical_gateway-v1-CanonicalThreeDSProcessorResponseFields)
    - [CanonicalTicket](#canonical_gateway-v1-CanonicalTicket)
    - [CanonicalTicketingTravelAgency](#canonical_gateway-v1-CanonicalTicketingTravelAgency)
    - [CanonicalTransactionVisibilitySettings](#canonical_gateway-v1-CanonicalTransactionVisibilitySettings)
    - [CanonicalUserContext](#canonical_gateway-v1-CanonicalUserContext)
    - [CanonicalVoucherProcessorResponseFields](#canonical_gateway-v1-CanonicalVoucherProcessorResponseFields)
    - [CanonicalWalletProcessorResponseFields](#canonical_gateway-v1-CanonicalWalletProcessorResponseFields)
    - [CanonicalWebhookRequestData](#canonical_gateway-v1-CanonicalWebhookRequestData)
    - [CanonicalWebhookResponseData](#canonical_gateway-v1-CanonicalWebhookResponseData)
  
    - [PersonType](#canonical_gateway-v1-PersonType)
    - [WebhookNextAction](#canonical_gateway-v1-WebhookNextAction)
  
- [canonical_gateway/v1/cancel_order.proto](#canonical_gateway_v1_cancel_order-proto)
    - [CanonicalCancelOrderRequest](#canonical_gateway-v1-CanonicalCancelOrderRequest)
    - [CanonicalCancelOrderResponse](#canonical_gateway-v1-CanonicalCancelOrderResponse)
  
- [canonical_gateway/v1/webhook.proto](#canonical_gateway_v1_webhook-proto)
    - [CanonicalWebhookRequest](#canonical_gateway-v1-CanonicalWebhookRequest)
    - [CanonicalWebhookResponse](#canonical_gateway-v1-CanonicalWebhookResponse)
  
- [canonical_gateway/v1/external_account.proto](#canonical_gateway_v1_external_account-proto)
    - [CanonicalExternalAccountRequestFields](#canonical_gateway-v1-CanonicalExternalAccountRequestFields)
    - [CanonicalExternalAccountResponseFields](#canonical_gateway-v1-CanonicalExternalAccountResponseFields)
  
- [canonical_gateway/v1/deuna_transaction.proto](#canonical_gateway_v1_deuna_transaction-proto)
    - [CanonicalDeunaTransactionRequest](#canonical_gateway-v1-CanonicalDeunaTransactionRequest)
    - [CanonicalDeunaTransactionResponse](#canonical_gateway-v1-CanonicalDeunaTransactionResponse)
    - [CanonicalNextAction](#canonical_gateway-v1-CanonicalNextAction)
    - [CanonicalSingleTransactionInformation](#canonical_gateway-v1-CanonicalSingleTransactionInformation)
  
- [canonical_gateway/v1/gateway.proto](#canonical_gateway_v1_gateway-proto)
    - [CanonicalGatewayRequest](#canonical_gateway-v1-CanonicalGatewayRequest)
    - [CanonicalGatewayResponse](#canonical_gateway-v1-CanonicalGatewayResponse)
  
- [canonical_gateway/v1/merchant.proto](#canonical_gateway_v1_merchant-proto)
    - [CanonicalMerchantRequest](#canonical_gateway-v1-CanonicalMerchantRequest)
    - [CanonicalMerchantResponse](#canonical_gateway-v1-CanonicalMerchantResponse)
  
- [canonical_gateway/v1/transaction.proto](#canonical_gateway_v1_transaction-proto)
    - [CanonicalTransactionRequest](#canonical_gateway-v1-CanonicalTransactionRequest)
    - [CanonicalTransactionResponse](#canonical_gateway-v1-CanonicalTransactionResponse)
  
- [canonical_gateway/v1/gateway_service.proto](#canonical_gateway_v1_gateway_service-proto)
    - [CanonicalGatewayService](#canonical_gateway-v1-CanonicalGatewayService)
  
- [Scalar Value Types](#scalar-value-types)


<a name="canonical_gateway_v1_event-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## canonical_gateway/v1/event.proto


 


<a name="canonical_gateway-v1-DEUNAEvent"></a>

### DEUNAEvent


| Name | Number | Description |
| ---- | ------ | ----------- |
| unknown | 0 | Protobuff makes the 0-value the default one |
| external_transaction_created | 1 | Events from PSP&#39;s |
| external_transaction_updated | 2 |  |
| external_transaction_captured | 3 |  |
| external_transaction_authorized | 4 |  |
| external_transaction_refunded | 5 |  |
| external_transaction_voided | 6 |  |
| transaction_created | 7 | Events inside DEUNA |
| transaction_updated | 8 |  |
| transaction_captured | 9 |  |
| transaction_authorized | 10 |  |
| transaction_refunded | 11 |  |
| transaction_voided | 12 |  |
| three_ds_method_completed | 13 |  |
| three_ds_challenge_completed | 15 |  |
| event_nop | 16 | No operation (no-op) event. |
| transaction_update_payconnect | 17 | Used for the new flow, it is agnostic to the transaction type. Use it for transactions identified by the external_transaction_id or conciliation_id. |


 

 

 



<a name="canonical_gateway_v1_common-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## canonical_gateway/v1/common.proto



<a name="canonical_gateway-v1-CanonicalAddress"></a>

### CanonicalAddress



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| person | [CanonicalPerson](#canonical_gateway-v1-CanonicalPerson) |  | Information about the recipient |
| id | [string](#string) |  | ID of the address |
| address1 | [string](#string) |  | Complete first address line |
| neighbourhood1 | [string](#string) |  | Neighbourhood of first address |
| street1 | [string](#string) |  | Street of first address |
| street_number1 | [string](#string) |  | Street number of first address |
| address2 | [string](#string) |  | Complete second address line (optional) |
| neighbourhood2 | [string](#string) |  | Neighbourhood of second address (optional) |
| street2 | [string](#string) |  | Street of second address (optional) |
| street_number2 | [string](#string) |  | Street number of second address (optional) |
| zip | [string](#string) |  | Zip or postal code of the address |
| city | [string](#string) |  | City of the address |
| state | [string](#string) |  | State or province of the address |
| country | [string](#string) |  | Country of the address |
| country_numeric_code | [string](#string) |  | Country code of the address, numeric code format |
| country_iso2 | [string](#string) |  | Country code of the address, ISO 2 char format |
| country_iso3 | [string](#string) |  | Country code of the address, ISO 3 char format |
| full_phone_number | [string](#string) |  | Complete phone number of the client |
| phone_number | [string](#string) |  | Phone number of the client |
| phone_number_country_code | [string](#string) |  | Phone number country code of the client |
| phone_number_area | [string](#string) |  | Phone number area of the client |
| email | [string](#string) |  | Email address of the client |
| address_type | [string](#string) |  | Type of address |
| shipping_type | [string](#string) |  | Shipping type |
| state_code | [string](#string) |  | State or province code of the address |






<a name="canonical_gateway-v1-CanonicalAddressInformation"></a>

### CanonicalAddressInformation



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| billing_address | [CanonicalAddress](#canonical_gateway-v1-CanonicalAddress) |  | Billing address for the transaction |
| shipping_address | [CanonicalAddress](#canonical_gateway-v1-CanonicalAddress) |  | Shipping address for the transaction |






<a name="canonical_gateway-v1-CanonicalAirlineInformation"></a>

### CanonicalAirlineInformation
Airline Info


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| pnr | [string](#string) |  | **Deprecated.** Passenger Name Record (PNR) code |
| ticketing_travel_agency | [CanonicalTicketingTravelAgency](#canonical_gateway-v1-CanonicalTicketingTravelAgency) |  | **Deprecated.**  |
| passengers | [CanonicalPassenger](#canonical_gateway-v1-CanonicalPassenger) | repeated | **Deprecated.**  |
| booking_items | [CanonicalBookingItems](#canonical_gateway-v1-CanonicalBookingItems) | repeated |  |






<a name="canonical_gateway-v1-CanonicalAmount"></a>

### CanonicalAmount



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| amount | [CanonicalNumber](#canonical_gateway-v1-CanonicalNumber) |  | The amount. Inside it, is represented in cents and with cents |
| currency | [string](#string) |  |  |
| iso_numeric_currency | [string](#string) |  | ISO-4217 numeric representation of the currency |
| decimal_places_currency | [int32](#int32) |  | Number of digits after the decimal point of the currency |
| max_bytes_amount | [int64](#int64) |  | Number of max bytes by currency (e.g 7: 99999.99) |
| amount_in_minor_units | [CanonicalNumber](#canonical_gateway-v1-CanonicalNumber) |  | Represents amount in minor units of the given currency (e.g., $10 in JPY would be 10 yen, but in USD it would be 1000 cents and finally it would be 10000 in Iraqi Dinar) |






<a name="canonical_gateway-v1-CanonicalAmounts"></a>

### CanonicalAmounts



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| amount | [CanonicalAmount](#canonical_gateway-v1-CanonicalAmount) |  | Amount of the transaction |
| tax_amount | [CanonicalAmount](#canonical_gateway-v1-CanonicalAmount) |  | Tax amount of the transaction |
| subtotal_amount | [CanonicalAmount](#canonical_gateway-v1-CanonicalAmount) |  | Subtotal amount of the transaction |
| shipping_amount | [CanonicalAmount](#canonical_gateway-v1-CanonicalAmount) |  | Shipping amount of the transaction |
| discount_amount | [CanonicalAmount](#canonical_gateway-v1-CanonicalAmount) |  | Discount amount of the transaction |
| shipping_discount_amount | [CanonicalAmount](#canonical_gateway-v1-CanonicalAmount) |  | Shipping discount amount of the transaction |
| reversal_amount | [CanonicalAmount](#canonical_gateway-v1-CanonicalAmount) |  | Difference between the authorized amount and captured amount to be reversed |
| items_total_amount | [CanonicalAmount](#canonical_gateway-v1-CanonicalAmount) |  | Amount of all items of the transaction |
| airport_tax_amount | [CanonicalAmount](#canonical_gateway-v1-CanonicalAmount) |  | Airport tax amount of the transaction |






<a name="canonical_gateway-v1-CanonicalAncillary"></a>

### CanonicalAncillary



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| type | [string](#string) |  | Type of ancillary service (e.g., baggage, seat, etc.) |
| ticket_number | [string](#string) |  | Ticket number associated with the ancillary service and the leg |
| total_amount | [int64](#int64) |  | Amount of the ancillary service |
| service_category | [string](#string) |  | Category of the ancillary service |
| description | [string](#string) |  | Description of the ancillary service |
| sub_category_code | [string](#string) |  | Sub-category code of the ancillary service |
| fee_code | [string](#string) |  | Fee code of the ancillary service |
| unit_price | [int64](#int64) |  | Unit price of the ancillary service fee in cents |
| quantity | [int32](#int32) |  | Quantity of the ancillary service units |
| service_name | [string](#string) |  | Name of the ancillary service |






<a name="canonical_gateway-v1-CanonicalAvsFields"></a>

### CanonicalAvsFields



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| code | [string](#string) |  | The DEUNA standard AVS code |
| psp_code | [string](#string) |  | The PSP standard AVS code |
| psp_description | [string](#string) |  | The PSP standard AVS code |
| description | [string](#string) |  | The DEUNA standard AVS description |






<a name="canonical_gateway-v1-CanonicalBankListReference"></a>

### CanonicalBankListReference



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| country | [string](#string) |  |  |
| institutions | [CanonicalBankListReferenceInstitution](#canonical_gateway-v1-CanonicalBankListReferenceInstitution) | repeated |  |






<a name="canonical_gateway-v1-CanonicalBankListReferenceInstitution"></a>

### CanonicalBankListReferenceInstitution



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) |  |  |
| name | [string](#string) |  |  |
| url | [string](#string) |  |  |






<a name="canonical_gateway-v1-CanonicalBankListResponse"></a>

### CanonicalBankListResponse



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) |  | Identifier of the bank |
| name | [string](#string) |  | Name of the bank |
| url | [string](#string) |  | URL of the bank |
| commercial_name | [string](#string) |  | Commercial name of the bank |
| institution_id | [string](#string) |  | Unique identifier for a specific institution or subsidiary within a bank. Used to identify the exact payment option when applying merchant_pp blacklists, allowing individual subsidiaries to be blocked without excluding the entire bank. |






<a name="canonical_gateway-v1-CanonicalBankTransferProcessorRequestFields"></a>

### CanonicalBankTransferProcessorRequestFields



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| financial_institution_name | [string](#string) |  | Name of financial institution |
| financial_institution_code | [string](#string) |  | Code of financial institution |






<a name="canonical_gateway-v1-CanonicalBankTransferProcessorResponseFields"></a>

### CanonicalBankTransferProcessorResponseFields



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| qr | [string](#string) |  | QR code for the bank transfer, you can use this parameter in case of a voucher. |
| token | [string](#string) |  | Transaction Token |
| expiration_date | [string](#string) |  | Date of expiration of the bank transfer |
| metadata | [google.protobuf.Struct](#google-protobuf-Struct) |  | Metadata of the bank transfer |
| redirect_url | [string](#string) |  | Redirect URL to redirect user to complete bank transfer process |
| bank_list | [CanonicalBankListResponse](#canonical_gateway-v1-CanonicalBankListResponse) | repeated | List of banks available to perform a bank transfer transaction |
| reference | [string](#string) |  | External reference code for the transaction from the bank (e.g., CUS in PSE system) |






<a name="canonical_gateway-v1-CanonicalBinData"></a>

### CanonicalBinData



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| bin | [string](#string) |  | BIN of the credit card |
| bank | [string](#string) |  | Bank of the credit card |
| branch | [string](#string) |  | Full branch of the credit card |
| card_type | [string](#string) |  | Type of the credit card: credit or debit |
| country | [string](#string) |  | Country of the credit card |
| country_iso | [string](#string) |  | Country of the credit card in ISO format |
| currency | [string](#string) |  | Currency from bin detector |
| standard_branch | [string](#string) |  | Standardized branch of the card |






<a name="canonical_gateway-v1-CanonicalBookingItems"></a>

### CanonicalBookingItems



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| pnr | [string](#string) |  | Passenger Name Record (PNR) code |
| ticket_number | [string](#string) |  | Ticket number |
| e_ticket | [bool](#bool) |  | Indicates if the ticket is an electronic ticket |
| airline_3_digit_code | [string](#string) |  | Airline 3-digit code |
| airline_iata_designator | [string](#string) |  | Airline IATA designator |
| ticketing_travel_agency | [CanonicalTicketingTravelAgency](#canonical_gateway-v1-CanonicalTicketingTravelAgency) |  | Travel agency information |
| passenger | [CanonicalPassenger](#canonical_gateway-v1-CanonicalPassenger) |  | Passenger information |
| legs | [CanonicalLeg](#canonical_gateway-v1-CanonicalLeg) | repeated | List of legs in the ticket |
| airline_name | [string](#string) |  | Airline name |
| ancillaries | [CanonicalAncillary](#canonical_gateway-v1-CanonicalAncillary) | repeated | Ancillary services |
| reservation_system_code | [string](#string) |  | GDS reservation system code (e.g., Amadeus, Sabre, Galileo) |






<a name="canonical_gateway-v1-CanonicalBuyNowPayLaterPaymentProcessorResponseFields"></a>

### CanonicalBuyNowPayLaterPaymentProcessorResponseFields
CanonicalBuyNowPayLaterPaymentProcessorResponseFields is the response for the buy now pay later payment processor.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| expiration_date | [string](#string) |  |  |
| payment_processor | [string](#string) |  |  |
| approved_amount | [string](#string) |  |  |
| redirect_url | [string](#string) |  | Redirect URL to redirect user to complete payment process |






<a name="canonical_gateway-v1-CanonicalCancelOrderRequestData"></a>

### CanonicalCancelOrderRequestData



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| event_id | [string](#string) |  | DEUNA&#39;s event_id |
| timestamp | [string](#string) |  | Time in which the event was received |
| raw_request | [CanonicalRawRequest](#canonical_gateway-v1-CanonicalRawRequest) |  | The raw request sent to the gateway |






<a name="canonical_gateway-v1-CanonicalCancelOrderResponseData"></a>

### CanonicalCancelOrderResponseData



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| event_id | [string](#string) |  | DEUNA&#39;s event id |
| event_external_id | [string](#string) |  | PSP&#39;s event id |
| transaction_id | [string](#string) |  | DEUNA&#39;s transaction_id |
| timestamp | [string](#string) |  | Time when the event was received |
| event_name | [DEUNAEvent](#canonical_gateway-v1-DEUNAEvent) |  | DEUNA&#39;s event name |
| external_event_name | [string](#string) |  | PSP&#39;s event name |
| external_transaction_status | [string](#string) |  |  |
| transaction_status | [string](#string) |  |  |
| response_body | [string](#string) |  | http status code 200 |
| redirect_url | [string](#string) |  | http status code 301 |
| status_code | [int32](#int32) |  |  |






<a name="canonical_gateway-v1-CanonicalCardToken"></a>

### CanonicalCardToken



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| type | [string](#string) |  | Card token type (eg: deuna vault token, spreddly token, etc) |
| value | [string](#string) |  | Card token value |






<a name="canonical_gateway-v1-CanonicalCardValidationDetails"></a>

### CanonicalCardValidationDetails



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| card_validation_method | [string](#string) |  | Gateway method validation, this will be stored in the verified_by field of user_card |
| refund_standard_error | [CanonicalStandardError](#canonical_gateway-v1-CanonicalStandardError) |  | Indicates if there was an error in the automatic refund |






<a name="canonical_gateway-v1-CanonicalConsentRequestFields"></a>

### CanonicalConsentRequestFields



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) |  | Identifier of consent |
| status | [string](#string) |  | Status of consent |
| customer_account | [string](#string) | optional | Account of customer |
| required | [bool](#bool) |  | Indicates if consent is required |
| refresh_token | [string](#string) | optional | Refresh token used to renew the consent access token (sensitive) |






<a name="canonical_gateway-v1-CanonicalConsentResponseFields"></a>

### CanonicalConsentResponseFields



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) |  | Identifier of consent |
| status | [string](#string) |  | Status of consent |
| redirect_url | [string](#string) |  | URL to redirect user to complete consent process |
| expiration_date | [string](#string) | optional | Date of expiration of the consent process |
| customer_account | [string](#string) | optional | Account of customer |
| payment_method | [string](#string) | optional | Token of customer account result of consent process |
| access_token | [string](#string) | optional | Access token result of the consent process or of its renewal (sensitive) |
| refresh_token | [string](#string) | optional | Refresh token to renew the access token (sensitive) |
| token_type | [string](#string) | optional | Type of the access token e.g. Bearer |
| expires_in | [int32](#int32) | optional | Seconds until the access token expires |






<a name="canonical_gateway-v1-CanonicalCookie"></a>

### CanonicalCookie



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| name | [string](#string) |  |  |
| value | [string](#string) |  |  |






<a name="canonical_gateway-v1-CanonicalCreateCardTokenRequestFields"></a>

### CanonicalCreateCardTokenRequestFields



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| card_validation_method | [string](#string) |  | Method for card validation e.g normal_charge, zero_dollar_charge, etc |
| card_id | [string](#string) |  | DEUNA VAULT card identifier |






<a name="canonical_gateway-v1-CanonicalCreateCardTokenResponseFields"></a>

### CanonicalCreateCardTokenResponseFields



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| token | [string](#string) |  | Token result from gateway card tokenization |
| card_validation_details | [CanonicalCardValidationDetails](#canonical_gateway-v1-CanonicalCardValidationDetails) |  | Fields for card validation details |






<a name="canonical_gateway-v1-CanonicalCredentials"></a>

### CanonicalCredentials



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| public_api_key | [string](#string) |  | Public API key for authentication |
| private_api_key | [string](#string) |  | Private API key for authentication |
| merchant_pwd | [string](#string) |  | Merchant pwd for authentication |
| external_merchant_id | [string](#string) |  | ID of the merchant on the PSP/Platform |
| acquirer_id | [string](#string) |  | ID of acquirer |
| acquirer_merchant_id | [string](#string) |  | ID of the merchant at the acquirer for this particular gateway |






<a name="canonical_gateway-v1-CanonicalCreditCard"></a>

### CanonicalCreditCard



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| person | [CanonicalPerson](#canonical_gateway-v1-CanonicalPerson) |  | Information about the holder of the credit card |
| expiry_month | [string](#string) |  | Expiry month of the credit card, not padded format (eg: 1, 11) |
| expiry_month_padded | [string](#string) |  | Expiry month of the credit card, padded format (eg: 01, 11) |
| expiry_year | [string](#string) |  | Expiry year of the credit card, (eg: 20, 25, 30) |
| expiry_year_complete | [string](#string) |  | Expiry year of the credit card, complete format (eg: 2020, 2025, 2030) |
| card_number | [string](#string) |  | Number of the credit card |
| card_bin | [string](#string) |  | BIN of the credit card |
| card_number_last_four | [string](#string) |  | Last four numbers of the credit card |
| card_cvv | [string](#string) |  | CVV of the credit card |
| company | [string](#string) |  | Company of the credit card |
| brand | [string](#string) |  | Brand of the credit card |
| address1 | [string](#string) |  | Complete first address of the credit card holder |
| neighbourhood1 | [string](#string) |  | Neighbourhood of first address of the credit card holder |
| street1 | [string](#string) |  | Street of first address of the credit card holder |
| street_number1 | [string](#string) |  | Street number of first address of the credit card holder |
| address2 | [string](#string) |  | Second address of the credit card holder |
| neighbourhood2 | [string](#string) |  | Neighbourhood of second address of the credit card holder |
| street2 | [string](#string) |  | Street of second address of the credit card holder |
| street_number2 | [string](#string) |  | Street number of second address of the credit card holder |
| zip | [string](#string) |  | Zipcode of the credit card holder&#39;s address |
| city | [string](#string) |  | City of the credit card holder&#39;s address |
| state | [string](#string) |  | State of the credit card holder&#39;s address |
| country | [string](#string) |  | Country of the address |
| country_numeric_code | [string](#string) |  | Country code of the credit card holder&#39;s address |
| country_iso2 | [string](#string) |  | Country code of the credit card holder&#39;s address, ISO 2 char format |
| country_iso3 | [string](#string) |  | Country code of the credit card holder&#39;s address, ISO 3 char format |
| full_phone_number | [string](#string) |  | Complete phone number of the client |
| phone_number | [string](#string) |  | Phone number of the credit card holder |
| phone_number_country_code | [string](#string) |  | Phone number country code of the credit card holder |
| phone_number_area | [string](#string) |  | Phone number ares of the credit card holder |
| bin_data | [CanonicalBinData](#canonical_gateway-v1-CanonicalBinData) |  | Card information from bin detector |
| card_token | [CanonicalCardToken](#canonical_gateway-v1-CanonicalCardToken) |  | Token of the credit card |
| network_token_data | [CanonicalNetworkTokenData](#canonical_gateway-v1-CanonicalNetworkTokenData) |  | aditional data for network tokens |






<a name="canonical_gateway-v1-CanonicalDate"></a>

### CanonicalDate



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| iso8601 | [string](#string) |  | Date in ISO 8610 format 2024-10-03T14:30:00Z |
| dateOnly | [string](#string) |  | Date in format 2024-10-01 |
| unixTimestamp | [int64](#int64) |  | Date in unix timestamp 1628966400 |
| datetime | [string](#string) |  | Date in format 2023-05-05 14:20:50 |
| day | [int32](#int32) |  | Day of the date |
| month | [int32](#int32) |  | Month of the date |
| year | [int32](#int32) |  | Year of the date |
| time_only | [string](#string) |  | Time in format 15:04:05 |
| rfc1123 | [string](#string) |  | Date on the RFC1123 format, &#34;Mon, 02 Jan 2006 15:04:05 MST&#34; |
| iso8601NoTZ | [string](#string) |  | Date in ISO 8610 without timezone format 2024-10-03T14:30:00 |






<a name="canonical_gateway-v1-CanonicalDiscount"></a>

### CanonicalDiscount



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| amount | [CanonicalAmount](#canonical_gateway-v1-CanonicalAmount) |  | Amount of the discount |
| code | [string](#string) |  | Code of the discount |
| description | [string](#string) |  | Description of the discount |
| details_url | [string](#string) |  | Details URL of the discount |
| free_shipping | [CanonicalFreeShipping](#canonical_gateway-v1-CanonicalFreeShipping) |  | Free shipping of the discount |
| discount_category | [string](#string) |  | Discount category of the discount |
| target_type | [string](#string) |  | Target type of the discount |
| type | [string](#string) |  | Type of the discount |






<a name="canonical_gateway-v1-CanonicalFreeShipping"></a>

### CanonicalFreeShipping



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| is_free_shipping | [bool](#bool) |  | Indicates if the item is free shipping |
| maximum_cost_allowed | [int64](#int64) |  | Maximum cost allowed for free shipping |






<a name="canonical_gateway-v1-CanonicalInstallmentPlanRequestFields"></a>

### CanonicalInstallmentPlanRequestFields



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| value | [int64](#int64) |  | value of payment e.g. 1000 BRL |
| max_installments | [int32](#int32) |  | max of installments with interest e.g. 8 |
| max_installments_no_interest | [int32](#int32) |  | max of installments without interest e.g. 4 |






<a name="canonical_gateway-v1-CanonicalInstallmentPlanResponseFields"></a>

### CanonicalInstallmentPlanResponseFields



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| installment_quantity | [int32](#int32) |  | Total quantity of installments e.g. 2 |
| installment_value | [int64](#int64) |  | Value of each installment e.g 5000 |
| interest_free | [bool](#bool) |  | If installment plan is free of interest e.g. true |
| installment_total_value | [int64](#int64) |  | Total value of amount before installments e.g. 1000 (2 installments worth 5000 each one) |
| installment_currency | [string](#string) |  | Currency of payment e.g. BRL |
| total_interest | [int64](#int64) | optional | The value of the total interest for this plan |
| external_plan_option_id | [string](#string) |  | ID of gateway installment plan option |
| amount_percentage | [double](#double) | optional | Percentage of the installment amount over the payment amount |
| total_amount_percentage | [double](#double) | optional | Percentage of the total amount over the payment amount |
| installment_plan_additional_limit | [double](#double) | optional | Amount funded with the additional limit source |
| additional_limit_message | [string](#string) | optional | Message to show to the user about the additional limit |
| method_type | [string](#string) | optional | Payment method type of the plan, e.g. debit, credit or credit_with_additional_limit |
| taxes | [CanonicalInstallmentTax](#canonical_gateway-v1-CanonicalInstallmentTax) | repeated | Taxes of the plan exactly as the processor returns them (no rounding) |
| installment_rate | [double](#double) | optional | Interest rate of the plan as the processor returns it e.g. 0.007; when present the plan total (installment_total_value) already includes the interest |






<a name="canonical_gateway-v1-CanonicalInstallmentTax"></a>

### CanonicalInstallmentTax
CanonicalInstallmentTax Tax or fee of an installment plan, values are kept with the decimals returned by the processor


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) |  | Tax identifier e.g. INTERESTS, IOF, CET, CONTRACTED |
| rate | [double](#double) |  | Rate returned by the processor e.g. 0.0003 |
| tax_amount | [double](#double) | optional | Amount of the tax returned by the processor e.g. 2.45 |






<a name="canonical_gateway-v1-CanonicalInstallments"></a>

### CanonicalInstallments



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| has_interest | [bool](#bool) |  | Field that indicates whether the installments have interest or not |
| number | [CanonicalNumber](#canonical_gateway-v1-CanonicalNumber) |  | Number of installments |
| rate | [CanonicalNumber](#canonical_gateway-v1-CanonicalNumber) |  | Rate of the installments |
| amount | [CanonicalAmount](#canonical_gateway-v1-CanonicalAmount) |  | Amount of each installment |
| plan_option_id | [string](#string) |  | Unique identifier of the plan option |
| deferred_months | [int32](#int32) |  | Number of months a payment is delayed |
| method_type | [string](#string) |  | Payment method type of the selected plan, e.g. debit, credit or credit_with_additional_limit |






<a name="canonical_gateway-v1-CanonicalIso8583"></a>

### CanonicalIso8583
Fields from ISO 8583 standard integrations (e.g. AMEX, Elavon, BBVA) that are required for reversal operations (e.g. void and partial capture)


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| stan | [string](#string) |  | System Trace Audit Number sent in the purchase request (ISO 8583 field 11) |
| local_date_time | [string](#string) |  | Date sent in the purchase request (ISO 8583 field 12) |
| rrn | [string](#string) |  | Retrieval Reference Number sent in the purchase request (ISO 8583 field 28) |
| ard | [string](#string) |  | Acquirer Reference Data received in the purchase response (ISO 8583 field 31) |
| reconciliation_date | [string](#string) |  | Date sent in the purchase request (ISO 8583 field 37) |
| connection_name | [string](#string) |  | Connection name returned by ISO broker for connection affinity in follow-up operations |
| connection_ip | [string](#string) |  | Connection IP returned by ISO broker for connection affinity in follow-up operations |






<a name="canonical_gateway-v1-CanonicalIso8583ReversalFields"></a>

### CanonicalIso8583ReversalFields
Fields from ISO 8583 standard integrations (e.g. AMEX, Elavon, BBVA) that are required for reversal operations (e.g. void and partial capture)


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| stan | [string](#string) |  | System Trace Audit Number sent in the purchase request (ISO 8583 field 11) |
| local_date_time | [string](#string) |  | Date sent in the purchase request (ISO 8583 field 12) |
| rrn | [string](#string) |  | Retrieval Reference Number sent in the purchase request (ISO 8583 field 28) |
| ard | [string](#string) |  | Acquirer Reference Data received in the purchase response (ISO 8583 field 31) |
| reconciliation_date | [string](#string) |  | Date sent in the purchase request (ISO 8583 field 37) |
| extra_dynamic_data | [google.protobuf.Struct](#google-protobuf-Struct) |  | Dynamic data with subfields sent or received in the purchase operation (ISO 8583 field 48, 60, 63) |
| connection_name | [string](#string) |  | Connection name returned by ISO broker for connection affinity in follow-up operations |
| connection_ip | [string](#string) |  | Connection IP returned by ISO broker for connection affinity in follow-up operations |






<a name="canonical_gateway-v1-CanonicalItem"></a>

### CanonicalItem



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) |  | ID of the item |
| title | [string](#string) |  | Title of the item |
| description | [string](#string) |  | Description of the item |
| quantity | [CanonicalNumber](#canonical_gateway-v1-CanonicalNumber) |  | Quantity of the item |
| unit_price | [CanonicalAmount](#canonical_gateway-v1-CanonicalAmount) |  | Unit price of the item |
| amount | [CanonicalAmount](#canonical_gateway-v1-CanonicalAmount) |  | Amount price of the item |
| original_amount | [CanonicalAmount](#canonical_gateway-v1-CanonicalAmount) |  | Original amount price of the item |
| total_discount | [CanonicalAmount](#canonical_gateway-v1-CanonicalAmount) |  | Total discount of the item |
| total_tax_amount | [CanonicalAmount](#canonical_gateway-v1-CanonicalAmount) |  | Total max amount price of the item |
| sku | [string](#string) |  | SKU of the item |
| brand | [string](#string) |  | Brand of the item |
| category | [string](#string) |  | Category of the item |
| tax_amount | [CanonicalAmount](#canonical_gateway-v1-CanonicalAmount) |  | Tax amount for each item |
| upc | [string](#string) |  | UPC of the item |
| size | [string](#string) |  | Size of the item |
| manufacturer | [string](#string) |  | Manufacturer of the item |






<a name="canonical_gateway-v1-CanonicalLeg"></a>

### CanonicalLeg
Leg information


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| carrier_code | [string](#string) |  | Carrier code (e.g., AA for American Airlines) |
| carrier_name | [string](#string) |  | Carrier name (e.g., American Airlines) |
| origin | [CanonicalLocation](#canonical_gateway-v1-CanonicalLocation) |  | Origin location information |
| destination | [CanonicalLocation](#canonical_gateway-v1-CanonicalLocation) |  | Destination location information |
| flight_number | [string](#string) |  | Flight number |
| fare_basis_code | [string](#string) |  | Fare basis code |
| seat_location | [string](#string) |  | Seat location |
| stopover_code | [string](#string) |  | Stopover code |
| amounts | [CanonicalAmounts](#canonical_gateway-v1-CanonicalAmounts) |  | All amounts of the flight |
| service_class | [string](#string) |  | Service class indicates a one-letter code of the flight leg (e.g., J for Business class, Y for Economy class) |






<a name="canonical_gateway-v1-CanonicalLocation"></a>

### CanonicalLocation
Location information


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| airport_code | [string](#string) |  | **Deprecated.** Airport code (e.g., LAX, JFK) |
| date | [CanonicalDate](#canonical_gateway-v1-CanonicalDate) |  | Date and time of the flight (YYYY-MM-DD) |
| iata_code | [string](#string) |  | Airport iata code (e.g., LAX, JFK) |






<a name="canonical_gateway-v1-CanonicalNetworkTokenData"></a>

### CanonicalNetworkTokenData



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| source | [string](#string) |  | source identifies the wallet that originated the token (e.g. &#34;apple_pay&#34;, &#34;google_pay&#34;). |
| type | [string](#string) |  | type indicates the payment data type returned by the wallet (e.g. &#34;3DSecure&#34;, &#34;EMV&#34; for Apple Pay; &#34;PAN_ONLY&#34;, &#34;CRYPTOGRAM_3DS&#34; for Google Pay). |
| cryptogram | [string](#string) |  | cryptogram is the base64-encoded network token cryptogram used for authorisation. For Apple Pay this is the OnlinePaymentCryptogram; for Google Pay it is the CRYPTOGRAM_3DS value. |
| transaction_id | [string](#string) |  | transaction_id is an optional wallet-level transaction identifier. |
| eci | [string](#string) |  | eci is the Electronic Commerce Indicator returned by the wallet, used for 3-D Secure processing. |
| emv_data | [string](#string) |  | emv_data contains raw EMV payment data, present only for Apple Pay EMV-type tokens. |
| encrypted_pin_data | [string](#string) |  | encrypted_pin_data holds the encrypted PIN, present only for Apple Pay EMV-type tokens. |
| details | [string](#string) |  | details contains card-level details string returned by Google Pay (e.g. last four digits). |
| gateway_merchant_id | [string](#string) |  | gateway_merchant_id is the gateway merchant identifier validated during Google Pay decryption. |
| message_expiration | [string](#string) |  | message_expiration is the Unix timestamp (milliseconds) indicating when the Google Pay message expires. |
| message_id | [string](#string) |  | message_id is the unique identifier of the Google Pay encrypted message. |
| payment_method | [string](#string) |  | payment_method is the payment method type reported by Google Pay (e.g. &#34;CARD&#34;). |






<a name="canonical_gateway-v1-CanonicalNumber"></a>

### CanonicalNumber



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| number | [int64](#int64) |  | A number without decimals |
| number_with_decimals | [double](#double) |  | A number with decimals |
| number_str | [string](#string) |  | A number without decimals, a string |
| number_with_decimals_str | [string](#string) |  | A number with decimals, as a string |






<a name="canonical_gateway-v1-CanonicalPassenger"></a>

### CanonicalPassenger
Passenger information


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) |  | Unique identifier for the user |
| first_name | [string](#string) |  | **Deprecated.** First name of the passenger |
| last_name | [string](#string) |  | **Deprecated.** Last name of the passenger |
| middle_name | [string](#string) |  | **Deprecated.** Middle name of the passenger |
| document_type | [string](#string) |  | **Deprecated.** Type of document (e.g., passport, ID card) |
| document | [string](#string) |  | **Deprecated.** Document number |
| email | [string](#string) |  | **Deprecated.** Email address of the passenger |
| phone | [string](#string) |  | Phone number of the passenger |
| frequent_flyer_code | [string](#string) |  | Frequent flyer code |
| title | [string](#string) |  | Title of the passenger (e.g., Mr., Mrs.) |
| date_of_birth | [string](#string) |  | **Deprecated.** Date of birth of the passenger |
| identity_document_number | [string](#string) |  | **Deprecated.** Identity document number |
| tickets | [CanonicalTicket](#canonical_gateway-v1-CanonicalTicket) | repeated | **Deprecated.** Itinerary information |
| person | [CanonicalPerson](#canonical_gateway-v1-CanonicalPerson) |  | Information about the passenger |
| country_code | [string](#string) |  | Country code of the passenger, according to the ISO 3166-1 alpha-2 standard |






<a name="canonical_gateway-v1-CanonicalPaymentCredentialsResponseFields"></a>

### CanonicalPaymentCredentialsResponseFields



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| public_api_key | [string](#string) |  | Merchant gateway api key used for initialize SDKs |
| customer_token | [string](#string) |  | Customer token used for initialize SDKs |
| external_merchant_id | [string](#string) |  | Merchant gateway id used for initialize SDKs |






<a name="canonical_gateway-v1-CanonicalPaymentMethodsResponseFields"></a>

### CanonicalPaymentMethodsResponseFields



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| account_identifier | [string](#string) |  | Identifier of customer account |
| id | [string](#string) |  | Token of customer account |






<a name="canonical_gateway-v1-CanonicalPaymentProcessor"></a>

### CanonicalPaymentProcessor



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| merchant_id | [string](#string) |  | Unique identifier of the merchant in Deuna |
| processor_id | [int32](#int32) |  | Unique identifier of the payment processor in Deuna |
| merchant_payment_processor_id | [string](#string) |  | Unique identifier of the merchant payment processor in Deuna |
| country_iso2 | [string](#string) |  | Country code of the payment processor |
| automatic_capture | [bool](#bool) |  | Tells if the payment processor is configured for automatic capture. If false, a pre-auth is made for a purchase operation |
| merchant_name | [string](#string) |  | Name of the merchant |
| processor_name | [string](#string) |  | Name of the payment processor |
| store_id | [string](#string) | optional | Store ID of the merchant in the payment processor |
| psp_parent_id | [int32](#int32) | optional | ID of the payment processor of which this mapping is a clone |
| psp_parent_name | [string](#string) | optional | Name of the parent PSP to use in Integration Hub when the pro |






<a name="canonical_gateway-v1-CanonicalPerson"></a>

### CanonicalPerson



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| full_name | [string](#string) |  | Full name of the person |
| first_name | [string](#string) |  | First name of the person |
| second_first_name | [string](#string) |  | Second first name of the person |
| full_last_name | [string](#string) |  | Full last name of the person |
| first_last_name | [string](#string) |  | First last name of the person |
| second_last_name | [string](#string) |  | Second last name of the person |
| person_identifier | [CanonicalPersonIdentifier](#canonical_gateway-v1-CanonicalPersonIdentifier) |  | Identification information of the person |
| id | [string](#string) |  | ID of the Person on the system |
| email | [string](#string) |  | Email of the Person on the system |
| date_of_birth | [CanonicalDate](#canonical_gateway-v1-CanonicalDate) |  | Date of birth of the person |
| person_type | [PersonType](#canonical_gateway-v1-PersonType) |  | Refers to the type of person, either natural or legal person |
| gender | [string](#string) |  | Gender of the passenger |
| type_code | [string](#string) |  | Type code of the passenger https://support.travelport.com/webhelp/formats/Content/Fare/PTC.htm |
| external_user_id | [string](#string) |  |  |
| external_registration_date | [CanonicalDate](#canonical_gateway-v1-CanonicalDate) |  | Registration date of the person in the merchant&#39;s platform |






<a name="canonical_gateway-v1-CanonicalPersonIdentifier"></a>

### CanonicalPersonIdentifier



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| identification_number | [string](#string) |  | Identification number of the person |
| identification_type | [string](#string) |  | Identification type of the person |






<a name="canonical_gateway-v1-CanonicalRawRequest"></a>

### CanonicalRawRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| body | [google.protobuf.Struct](#google-protobuf-Struct) |  | The body of the request. Forms/url-encoded will also be translated into a json |
| headers | [google.protobuf.Struct](#google-protobuf-Struct) |  | The headers in a object format |
| url | [string](#string) |  | The full URL of the request |
| query_params | [google.protobuf.Struct](#google-protobuf-Struct) |  | The Query Parameters |
| raw_body | [string](#string) |  | The raw body of the request |






<a name="canonical_gateway-v1-CanonicalRawResponse"></a>

### CanonicalRawResponse



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| body | [string](#string) |  | The body of the response |
| headers | [google.protobuf.Struct](#google-protobuf-Struct) |  | The headers in a object format |
| status_code | [int32](#int32) |  | The status code of the response |






<a name="canonical_gateway-v1-CanonicalRecurrence"></a>

### CanonicalRecurrence



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| first_time_use | [bool](#bool) | optional | Indicates if the recurrence is the first time use |
| scheduled | [bool](#bool) |  | Indicates if the recurrence is scheduled (e.g. Netflix) or unscheduled (e.g. Uber) |
| bill_reference | [string](#string) |  | Reference of the subscription, should be alphanumeric and without special characters (e.g. Netflix subscription ID) |
| type | [string](#string) |  | Type of the recurrence (e.g. recurring_setup, etc.) |
| network_transaction_id | [string](#string) |  | Network Transaction ID (NTID) for stored-credential / MIT chaining |
| recurrence_data | [google.protobuf.Struct](#google-protobuf-Struct) |  | Dynamic data with subfields sent or received in the recurrence operation |






<a name="canonical_gateway-v1-CanonicalRedirectUrls"></a>

### CanonicalRedirectUrls
CanonicalRedirectUrls Redirect URLs for Customer interaction with checkout


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| success | [string](#string) |  | URL to redirect Customer to a successful page |
| reject | [string](#string) |  | URL to redirect Customer to a rejection page |
| canceled | [string](#string) |  | URL to redirect Customer back to checkout page |
| failed | [string](#string) |  | URL to redirect Customer to a failure page |
| pending | [string](#string) |  | URL to redirect Customer to a pending page |






<a name="canonical_gateway-v1-CanonicalReferenceProcessorResponseFields"></a>

### CanonicalReferenceProcessorResponseFields



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| metadata | [google.protobuf.Struct](#google-protobuf-Struct) |  | Metadata of the bank transfer |
| bank_list | [CanonicalBankListReference](#canonical_gateway-v1-CanonicalBankListReference) | repeated | List of banks available to perform a reference payment transaction |
| reference_processors | [CanonicalVoucherProcessorResponseFields](#canonical_gateway-v1-CanonicalVoucherProcessorResponseFields) | repeated | List of reference processors to perform a reference payment transaction |






<a name="canonical_gateway-v1-CanonicalReversalFields"></a>

### CanonicalReversalFields
Reversal Fields for reversal operations (e.g. void and partial capture)


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| iso8583 | [CanonicalIso8583](#canonical_gateway-v1-CanonicalIso8583) |  | Fields from ISO 8583 standard integrations (e.g. AMEX, Elavon, BBVA) that are required for reversal operations (e.g. void and partial capture) |
| extra_dynamic_data | [google.protobuf.Struct](#google-protobuf-Struct) |  | Dynamic data with subfields sent or received in the transactions |






<a name="canonical_gateway-v1-CanonicalSCAExemptionDetails"></a>

### CanonicalSCAExemptionDetails



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| exemption_requested_by_merchant | [bool](#bool) |  | Whether the merchant explicitly requested an SCA exemption for this transaction. |
| reason_requested_by_merchant | [string](#string) |  | The specific reason or justification provided by the merchant for requesting the exemption. |
| exemption_applied | [bool](#bool) |  | Whether an SCA exemption was actually applied to the transaction by the issuer or payment processor. |
| exemption_type_applied | [string](#string) |  | The type of SCA exemption that was successfully applied to the transaction, if any. Examples include: ANTI_FRAUD_EVALUATION, AMOUNT_LT_30_EUR, INCOMING_EXEMPTION_REQUEST, MOTO, RECURRING_MIT, STRONG_CUSTOMER_AUTHENTICATION, OUT_OF_SCOPE, SECURE_CORPORATE, TRUSTED_BENEFICIARY. |






<a name="canonical_gateway-v1-CanonicalSelectInstallmentsResponseFields"></a>

### CanonicalSelectInstallmentsResponseFields
CanonicalSelectInstallmentsResponseFields is the response for select installments next action.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| account_identifier | [string](#string) |  | Account to which the installments plan belongs |
| id | [string](#string) |  | Gateway account id |
| installments | [CanonicalInstallmentPlanResponseFields](#canonical_gateway-v1-CanonicalInstallmentPlanResponseFields) | repeated | Installment plan details |






<a name="canonical_gateway-v1-CanonicalSplitRecipient"></a>

### CanonicalSplitRecipient



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| recipient_id | [string](#string) |  | Unique identifier of the split recipient |
| amount | [CanonicalAmount](#canonical_gateway-v1-CanonicalAmount) |  | Amount associated with the split recipient |
| options | [CanonicalSplitRecipientOptions](#canonical_gateway-v1-CanonicalSplitRecipientOptions) |  | Options for the split recipient (e.g., charge processing fee, liable, etc.) |






<a name="canonical_gateway-v1-CanonicalSplitRecipientOptions"></a>

### CanonicalSplitRecipientOptions



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| charge_processing_fee | [bool](#bool) |  | Indicates whether processing fee should be charged |
| charge_remainder_fee | [bool](#bool) |  | Indicates whether remainder fee should be charged |
| liable | [bool](#bool) |  | Indicates liability of the recipient |






<a name="canonical_gateway-v1-CanonicalStandardError"></a>

### CanonicalStandardError



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| message | [string](#string) |  | Message error |
| code | [string](#string) |  | Code error |






<a name="canonical_gateway-v1-CanonicalStepDetail"></a>

### CanonicalStepDetail



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| step | [string](#string) |  | Step name |
| result | [common.v1.CanonicalResult](#common-v1-CanonicalResult) |  | Result of the step |
| result_action_type | [common.v1.CanonicalResultActionType](#common-v1-CanonicalResultActionType) |  | The action type of the result step |
| standard_error | [CanonicalStandardError](#canonical_gateway-v1-CanonicalStandardError) |  | Standard error details |
| request_timestamp | [string](#string) |  | The timestamp of the request |
| url | [string](#string) |  | The url of the request |
| method_type | [string](#string) |  | The method type of the request (e.g: GET, POST, PUT, etc.) |
| headers | [google.protobuf.Struct](#google-protobuf-Struct) |  | The headers of the request |
| raw_request | [google.protobuf.Struct](#google-protobuf-Struct) |  | The raw request sent to the gateway |
| status_code | [int32](#int32) |  | Status code from the gateway |
| response_timestamp | [string](#string) |  | The timestamp of the response |
| raw_response | [google.protobuf.Struct](#google-protobuf-Struct) |  | The raw response from the gateway |
| retry_attempts | [int32](#int32) |  | The number of times the transaction was retried |
| transaction_visibility | [CanonicalTransactionVisibilitySettings](#canonical_gateway-v1-CanonicalTransactionVisibilitySettings) | optional | Transaction visibility configuration |






<a name="canonical_gateway-v1-CanonicalThreeDSProcessorRequestFields"></a>

### CanonicalThreeDSProcessorRequestFields



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| redirect_url | [string](#string) |  | Call URL of the 3DS |
| version | [string](#string) |  | Version of the 3DS |
| enabled | [bool](#bool) |  |  |
| specific_fields | [google.protobuf.Struct](#google-protobuf-Struct) |  | **Deprecated.** Processot-specific 3DS fields like a cres |
| three_ds_server_transaction_id | [string](#string) |  | the unique transaction ID (an UUID, in contrast to the base64-encoded value found on the xid) generated by the 3D-Secure server, used to track the transaction throughout the authentication process |
| cres | [string](#string) |  | Message (usually a json in a base64 format) in the 3D-Secure (3DS) protocol that is sent from the Access Control Server (ACS) to the 3DS Server after the cardholder has completed or attempted the authentication challenge. It provides the result of the challenge process and determines whether the transaction can proceed. |
| eci | [string](#string) |  | Electronic Commerce Indicator (ECI) is a value returned by the Directory Server and ACS indicating the outcome of authentication requested on transactions for EMV® 3-D Secure |
| cavv | [string](#string) |  | CAVV provides evidence that cardholder authentication occurred or that the merchant attempted authentication. A CAVV is unique for each authentication transaction. For Visa Secure, the AAV is named CAVV. |
| aav | [string](#string) |  | Accountholder Authentication Value (AAV). Formally called Universal Cardholder Authentication Field (UCAF), applicable for Mastercard and Maestro ecommerce transactions only. |
| aav_validation_result | [string](#string) |  | The result of Accountholder Authentication Value (AAV) validation. |
| raw_request | [CanonicalRawRequest](#canonical_gateway-v1-CanonicalRawRequest) |  | The raw request sent to the gateway |
| three_ds_method_required | [bool](#bool) |  | Indicates whether an iframe is required to be launched prior to the 3DS process either frictionLess or Challengue. |
| short_redirect_url | [string](#string) |  | Call shortener URL of the 3DS |
| token | [string](#string) |  | Token occasionally generated by the PSP (Payment Service Provider). |
| three_ds_method_executed | [bool](#bool) |  | Indicates whether the 3ds method has been executed |
| three_ds_authentication_response | [string](#string) |  | This field respresents the Payer Authentication Response (PARes) Status, a transaction status result identifier. Y – Successful Authentication. N – Failed Authentication. U – Unable to Complete Authentication. A – Successful Stand-In Attempts Transaction |
| authentication_result | [string](#string) |  | Raw authentication data that comes from the cardissuing bank. Primary authentication field that indicates if authentication was successful and if liability shift occurred. -1: Invalid PARes. 0: Successful validation. 1: Cardholder is not participating, but the attempt to authenticate was recorded. 6: Issuer unable to perform authentication. 9: Cardholder did not complete authentication. |
| directory_server_transaction_id | [string](#string) |  | The Directory Server Transaction ID is generated by the Mastercard Directory Server during the authentication transaction and passed back to the merchant with the authentication results. |
| acs_transaction_id | [string](#string) |  | Unique transaction identifier assigned by the ACS to identify a single transaction. |
| full_pares | [string](#string) |  | The full/complete (Payer) Authentication Response. It contains (AcqBIN)(MerID)(XID)(Date)(PurchaseAmount)(PAN)(AuthDate) (Status) (CAVV) (ECI) |
| veres_enrolled | [string](#string) |  | Result of the enrollment check. This field can contain one of these values -&gt; Y: Card enrolled or can be enrolled; you must authenticate; Liability shift. N: Card not enrolled; proceed with authorization. Liability shift; U: Unable to authenticate regardless of the reason. No liability shift. |
| xid | [string](#string) |  | The XID (often seen as a Base64‐encoded string, in contrast to the uuid found on the three_ds_server_transaction_id field) is the primary transaction identifier passed between the merchant/acquirer and the Access Control Server (ACS) to correlate the authentication request and response. You will typically see this in the API fields for older 3D Secure implementations |
| protocol | [string](#string) |  | Base64-encoded 3DS version used, without the minor versions (This will only be one digit eg 1 / 2) |
| flow_type | [string](#string) |  | The 3DS flow type (frictionless or challenge) |
| commerce_indicator | [string](#string) |  | The string representation of the Commerce Indicator, the difference between ECI and Commerce Indicator is ECI are a abbreviation of Commerce Indicator like spa or vbv |
| cavv_algorithm | [string](#string) |  | Algorithm for generating a cardholder authentication verification value (CAVV) or universal cardholder authentication field (UCAF)(also called aav) data |
| ucaf_collection_indicator | [string](#string) |  | This field contain one of these values = 0: Authentication data not collected, and customer authentication was not completed. 1: Authentication data not collected because customer authentication was not completed. 2: Authentication data collected because customer completed authentication. |






<a name="canonical_gateway-v1-CanonicalThreeDSProcessorResponseFields"></a>

### CanonicalThreeDSProcessorResponseFields



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| redirect_url | [string](#string) |  | Redirect URL for the 3DS challenge |
| challenge_html | [string](#string) |  | HTML challenge of the 3DS flow |
| browser_info_html | [string](#string) |  | HTML to collect data from the user&#39;s browser |
| metadata | [google.protobuf.Struct](#google-protobuf-Struct) |  | **Deprecated.** Metadata of the 3DS |
| three_ds_server_transaction_id | [string](#string) |  | the unique transaction ID generated by the 3D-Secure server, used to track the transaction throughout the authentication process |
| cres | [string](#string) |  | Message (usually a json in a base64 format) in the 3D-Secure (3DS) protocol that is sent from the Access Control Server (ACS) to the 3DS Server after the cardholder has completed or attempted the authentication challenge. It provides the result of the challenge process and determines whether the transaction can proceed. |
| version | [string](#string) |  | Version of the 3D-Secure protocol (2.0, 2.1.0, etc) |
| eci | [string](#string) |  | Electronic Commerce Indicator (ECI) is a value returned by the Directory Server and ACS indicating the outcome of authentication requested on transactions for EMV® 3-D Secure |
| cavv | [string](#string) |  | CAVV provides evidence that cardholder authentication occurred or that the merchant attempted authentication. A CAVV is unique for each authentication transaction. |
| short_redirect_url | [string](#string) |  | Call shortener URL of the 3DS |
| token | [string](#string) |  | Token occasionally generated by the PSP (Payment Service Provider). |
| override_three_ds_iframe_check_status_function | [string](#string) |  | Override the check status function in the three ds iframe javascript |
| card_enrolled | [bool](#bool) |  | Used to determine if a transaction was completed with 3DS Authentication. |
| xid | [string](#string) |  | The XID (often seen as a Base64‐encoded string) is the primary transaction identifier passed between the merchant/acquirer and the Access Control Server (ACS) to correlate the authentication request and response. You will typically see this in the API fields for older 3D Secure implementations |
| aav | [string](#string) |  | Accountholder Authentication Value (AAV). Formally called Universal Cardholder Authentication Field (UCAF), applicable for Mastercard and Maestro ecommerce transactions only. |
| aav_validation_result | [string](#string) |  | The result of Accountholder Authentication Value (AAV) validation. |
| directory_server_transaction_id | [string](#string) |  | The Directory Server Transaction ID is generated by the Mastercard Directory Server during the authentication transaction and passed back to the merchant with the authentication results. |
| acs_transaction_id | [string](#string) |  | Unique transaction identifier assigned by the ACS to identify a single transaction. |
| full_pares | [string](#string) |  | The full/complete (Payer) Authentication Response. It contains (AcqBIN)(MerID)(XID)(Date)(PurchaseAmount)(PAN)(AuthDate) (Status) (CAVV) (ECI) |
| authentication_result | [string](#string) |  | Raw authentication data that comes from the cardissuing bank. Primary authentication field that indicates if authentication was successful and if liability shift occurred. -1: Invalid PARes. 0: Successful validation. 1: Cardholder is not participating, but the attempt to authenticate was recorded. 6: Issuer unable to perform authentication. 9: Cardholder did not complete authentication. |
| veres_enrolled | [string](#string) |  | Result of the enrollment check. This field can contain one of these values -&gt; Y: Card enrolled or can be enrolled; you must authenticate; Liability shift. N: Card not enrolled; proceed with authorization. Liability shift; U: Unable to authenticate regardless of the reason. No liability shift. |
| directory_server_id | [string](#string) |  | Identifier of the directory server. The Directory Server is the element within the interoperability domain that enables communication between the 3DS Server and the ACS. It validates and routes 3DS messages to authenticate the cardholder during the transaction process. Both the ACS and the 3DS Server need to be enrolled by the Directory Server |
| three_ds_authentication_response | [string](#string) |  | [PARes] This field respresents the Payer Authentication Response (PARes) Status, a transaction status result identifier. Y – Successful Authentication. N – Failed Authentication. U – Unable to Complete Authentication. A – Successful Stand-In Attempts Transaction |
| commerce_indicator | [string](#string) |  | The string representation of the Commerce Indicator, the difference between ECI and Commerce Indicator is ECI are a abbreviation of Commerce Indicator like spa or vbv |
| cavv_algorithm | [string](#string) |  | Algorithm for generating a cardholder authentication verification value (CAVV) or universal cardholder authentication field (UCAF)(also called aav) data |
| ucaf_collection_indicator | [string](#string) |  | This field contain one of these values = 0: Authentication data not collected, and customer authentication was not completed. 1: Authentication data not collected because customer authentication was not completed. 2: Authentication data collected because customer completed authentication. |
| initiate_three_ds_id | [string](#string) |  | This field represents the response ID in the initiate step in the Authentication flows. |
| continue_three_ds_id | [string](#string) |  | This field represents the response ID in the continue step in the Authentication flows. |
| complete_three_ds_id | [string](#string) |  | This field represents the response ID in the complete step in the Authentication flows. |






<a name="canonical_gateway-v1-CanonicalTicket"></a>

### CanonicalTicket
Ticket information


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| e_ticket | [bool](#bool) |  | Indicates if the ticket is an electronic ticket |
| ticket_number | [string](#string) |  | Ticket number |
| legs | [CanonicalLeg](#canonical_gateway-v1-CanonicalLeg) | repeated | List of legs in the ticket |






<a name="canonical_gateway-v1-CanonicalTicketingTravelAgency"></a>

### CanonicalTicketingTravelAgency



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| iata_code | [string](#string) |  | IATA code of the travel agency |
| name | [string](#string) |  | Name of the travel agency |
| agency_invoice_number | [string](#string) |  | Invoice number of the travel agency |






<a name="canonical_gateway-v1-CanonicalTransactionVisibilitySettings"></a>

### CanonicalTransactionVisibilitySettings



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| enabled | [bool](#bool) |  | Indicates if transaction visibility is enabled |
| audience | [string](#string) |  | Target audience of transaction visibility |






<a name="canonical_gateway-v1-CanonicalUserContext"></a>

### CanonicalUserContext



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ip | [string](#string) |  | IP address of the request client |
| user_agent | [string](#string) |  | User agent of the request client. Is a characteristic string that lets servers and network peers identify the application, operating system, vendor. (Common format: Mozilla/5.0 (&lt;system-information&gt;) &lt;platform&gt; (&lt;platform-details&gt;) &lt;extensions&gt;. Example: Mozilla/5.0 (Windows NT 6.1; Win64; x64; rv:47.0) Gecko/20100101 Firefox/47.0) |
| screen_height | [int32](#int32) |  |  |
| screen_width | [int32](#int32) |  |  |
| fingerprint | [google.protobuf.Struct](#google-protobuf-Struct) |  | Fingerprint information of the user&#39;s browser. |
| color_depth | [int32](#int32) |  | Value representing the bit depth of the colour palette for displaying images, in bits per pixel |
| java_enabled | [bool](#bool) |  | Indicates whether Java is supported by the request client&#39;s browser |
| java_script_enabled | [bool](#bool) |  | Indicates whether JavaScript is supported by the request client&#39;s browser |
| language | [string](#string) |  | Value representing the browser language as defined in IETF BCP47 |
| time_zone_offset | [int32](#int32) |  | Time-zone offset in minutes between UTC and the Cardholder browser local time |
| accept_header | [string](#string) |  | Exact content of the HTTP accept headers as sent to the 3-D Secure 2 Requestor from the Cardholder&#39;s browser; |
| request_id | [string](#string) |  | Unique identifier of the request, used for idepotent requests |
| device_id | [string](#string) |  | Unique identifier of the device, used for fraud evaluation |
| is_guest | [bool](#bool) |  | Identifies if the user is guest |
| cookies | [CanonicalCookie](#canonical_gateway-v1-CanonicalCookie) | repeated | Cookies from the user |






<a name="canonical_gateway-v1-CanonicalVoucherProcessorResponseFields"></a>

### CanonicalVoucherProcessorResponseFields
CanonicalVoucherProcessorResponseFields is the response for the voucher processor.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| bar_code | [string](#string) |  | Bar code of the voucher |
| expiration_date | [string](#string) |  | Expiration date of the voucher |
| payment_processor | [string](#string) |  | Payment processor that emitted the voucher |
| url_payment_receipt_html | [string](#string) |  | URL to the payment receipt in HTML format |
| url_payment_receipt_pdf | [string](#string) |  | URL to the payment receipt in PDF format |






<a name="canonical_gateway-v1-CanonicalWalletProcessorResponseFields"></a>

### CanonicalWalletProcessorResponseFields
CanonicalWalletProcessorResponseFields is the response for the wallet processor.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| token | [string](#string) |  | Identifier of the wallet authorization |
| redirect_url | [string](#string) |  | Redirect URL for user to complete wallet process |






<a name="canonical_gateway-v1-CanonicalWebhookRequestData"></a>

### CanonicalWebhookRequestData



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| event_id | [string](#string) |  | DEUNA&#39;s event_id |
| timestamp | [string](#string) |  | Time in which the event was received |
| raw_request | [CanonicalRawRequest](#canonical_gateway-v1-CanonicalRawRequest) |  | The raw request sent to the gateway |






<a name="canonical_gateway-v1-CanonicalWebhookResponseData"></a>

### CanonicalWebhookResponseData



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| event_id | [string](#string) |  | DEUNA&#39;s event id |
| event_external_id | [string](#string) |  | PSP&#39;s event id |
| transaction_id | [string](#string) |  | DEUNA&#39;s transaction_id |
| timestamp | [string](#string) |  | Time when the event was received |
| event_name | [DEUNAEvent](#canonical_gateway-v1-DEUNAEvent) |  | DEUNA&#39;s event name |
| external_event_name | [string](#string) |  | PSP&#39;s event name |
| next_action | [WebhookNextAction](#canonical_gateway-v1-WebhookNextAction) |  | Next action to execute (update_transaction, capture_transaction, etc) |
| raw_request | [CanonicalRawRequest](#canonical_gateway-v1-CanonicalRawRequest) |  | Raw request information of the webhook |
| status_code_to_return | [int32](#int32) |  |  |
| external_transaction_status | [string](#string) |  |  |
| transaction_status | [string](#string) |  |  |
| raw_response | [CanonicalRawResponse](#canonical_gateway-v1-CanonicalRawResponse) |  | Custom response text to PSP webhook |
| method_type | [string](#string) |  |  |
| body_response_type | [string](#string) |  | Body response type for the webhook response |
| error_response | [CanonicalRawResponse](#canonical_gateway-v1-CanonicalRawResponse) |  | Custom error response text to PSP webhook |





 


<a name="canonical_gateway-v1-PersonType"></a>

### PersonType


| Name | Number | Description |
| ---- | ------ | ----------- |
| UNKNOWN_PERSON | 0 |  |
| NATURAL_PERSON | 1 |  |
| LEGAL_PERSON | 2 |  |



<a name="canonical_gateway-v1-WebhookNextAction"></a>

### WebhookNextAction


| Name | Number | Description |
| ---- | ------ | ----------- |
| update_transaction | 0 |  |
| capture_transaction | 1 |  |
| review_transaction | 2 |  |
| update_three_ds_flow | 3 |  |


 

 

 



<a name="canonical_gateway_v1_cancel_order-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## canonical_gateway/v1/cancel_order.proto



<a name="canonical_gateway-v1-CanonicalCancelOrderRequest"></a>

### CanonicalCancelOrderRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| data | [CanonicalCancelOrderRequestData](#canonical_gateway-v1-CanonicalCancelOrderRequestData) |  | The actual cancel order data |






<a name="canonical_gateway-v1-CanonicalCancelOrderResponse"></a>

### CanonicalCancelOrderResponse



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| data | [CanonicalCancelOrderResponseData](#canonical_gateway-v1-CanonicalCancelOrderResponseData) |  | The standarized data |





 

 

 

 



<a name="canonical_gateway_v1_webhook-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## canonical_gateway/v1/webhook.proto



<a name="canonical_gateway-v1-CanonicalWebhookRequest"></a>

### CanonicalWebhookRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| data | [CanonicalWebhookRequestData](#canonical_gateway-v1-CanonicalWebhookRequestData) |  | The actual webhook data |






<a name="canonical_gateway-v1-CanonicalWebhookResponse"></a>

### CanonicalWebhookResponse



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| data | [CanonicalWebhookResponseData](#canonical_gateway-v1-CanonicalWebhookResponseData) |  | The standarized data |





 

 

 

 



<a name="canonical_gateway_v1_external_account-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## canonical_gateway/v1/external_account.proto



<a name="canonical_gateway-v1-CanonicalExternalAccountRequestFields"></a>

### CanonicalExternalAccountRequestFields
CanonicalExternalAccountRequestFields is the request for creating or completing an external PSP account connection (e.g. Stripe Connect, PagBank Connect).


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| is_new_account | [bool](#bool) |  | Indicates whether a new PSP account should be created |
| country | [string](#string) |  | Country of the external account being connected |
| client_secret | [string](#string) |  | Platform credential used to authenticate with the PSP |
| return_url | [string](#string) |  | URL the PSP redirects to after the user completes the flow |
| authorization_code | [string](#string) | optional | Authorization code from the callback (existing-account OAuth flow) |
| external_account_id | [string](#string) | optional | Previously created account id (new-account verification flow) |






<a name="canonical_gateway-v1-CanonicalExternalAccountResponseFields"></a>

### CanonicalExternalAccountResponseFields
CanonicalExternalAccountResponseFields is the response for creating or completing an external PSP account connection.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) |  | Identifier of the external account connection attempt |
| status | [string](#string) |  | Status of the external account connection |
| redirect_url | [string](#string) | optional | URL to redirect the user to complete the connection process |
| expiration_date | [string](#string) | optional | Date of expiration of redirect_url |
| external_account_id | [string](#string) | optional | Identifier of the connected account on the PSP side |
| credentials | [CanonicalCredentials](#canonical_gateway-v1-CanonicalCredentials) |  | Credentials returned for the connected external account |





 

 

 

 



<a name="canonical_gateway_v1_deuna_transaction-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## canonical_gateway/v1/deuna_transaction.proto



<a name="canonical_gateway-v1-CanonicalDeunaTransactionRequest"></a>

### CanonicalDeunaTransactionRequest
CanonicalDeunaTransactionRequest is the request for all transactions methods.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| version | [int32](#int32) |  | The version of the JSON |
| transaction_id | [string](#string) |  | Unique identifier for the transaction |
| order_token | [string](#string) |  | Unique identifier for the order |
| external_transaction_id | [string](#string) |  | External reference identifier for the transaction |
| user_context | [CanonicalUserContext](#canonical_gateway-v1-CanonicalUserContext) |  | Information about the user&#39;s context |
| amounts | [CanonicalAmounts](#canonical_gateway-v1-CanonicalAmounts) |  | All amounts of the transaction |
| installments | [CanonicalInstallments](#canonical_gateway-v1-CanonicalInstallments) |  | Installments data of the transaction |
| customer | [CanonicalPerson](#canonical_gateway-v1-CanonicalPerson) |  | Email address of the client |
| address_information | [CanonicalAddressInformation](#canonical_gateway-v1-CanonicalAddressInformation) |  | Address information associated with the transaction |
| credit_card | [CanonicalCreditCard](#canonical_gateway-v1-CanonicalCreditCard) |  | Credit card information associated with the transaction |
| items | [CanonicalItem](#canonical_gateway-v1-CanonicalItem) | repeated | Items included in the transaction |
| notification_url | [string](#string) |  | URL to which notifications should be sent |
| metadata | [google.protobuf.Struct](#google-protobuf-Struct) |  | Additional metadata associated with the transaction |
| processor_specific_fields | [google.protobuf.Struct](#google-protobuf-Struct) |  | Specific fields of processor |
| three_ds_processor_request_fields | [CanonicalThreeDSProcessorRequestFields](#canonical_gateway-v1-CanonicalThreeDSProcessorRequestFields) |  | Details related to 3DS request fields |
| split_recipients | [CanonicalSplitRecipient](#canonical_gateway-v1-CanonicalSplitRecipient) | repeated | Options for splitting the transaction amount |
| step_details | [CanonicalStepDetail](#canonical_gateway-v1-CanonicalStepDetail) | repeated | Array of objects representing the past step details |
| webhook | [CanonicalWebhookRequest](#canonical_gateway-v1-CanonicalWebhookRequest) |  | The webhook request |
| airline_information | [CanonicalAirlineInformation](#canonical_gateway-v1-CanonicalAirlineInformation) |  | Airline information associated with the transaction |
| method_type | [string](#string) |  | Payment method type: credit_card, pse, wallet, bank_transfer, etc. |
| redirect_url | [string](#string) |  | **Deprecated.** Redirect url that contains the success url prop from checkout |
| expiration_date | [CanonicalDate](#canonical_gateway-v1-CanonicalDate) |  | Expiration date of the transaction |
| timestamp | [CanonicalDate](#canonical_gateway-v1-CanonicalDate) |  | Timestamp of the transaction |
| description | [string](#string) |  | Description includes the details of a transaction |
| bank_transfer_processor_request_fields | [CanonicalBankTransferProcessorRequestFields](#canonical_gateway-v1-CanonicalBankTransferProcessorRequestFields) |  | Request fields related to bank_transfer payment method |
| authorization_code | [string](#string) |  | Bank confirmation number (Usually 6 characters) |
| installment_plan_request_fields | [CanonicalInstallmentPlanRequestFields](#canonical_gateway-v1-CanonicalInstallmentPlanRequestFields) |  | Fields for requesting the installment plan |
| redirect_urls | [CanonicalRedirectUrls](#canonical_gateway-v1-CanonicalRedirectUrls) |  | URL from success, reject, canceled &amp; failed |
| statement_descriptor | [string](#string) |  | Payment description shown on customer account |
| create_card_token_request_fields | [CanonicalCreateCardTokenRequestFields](#canonical_gateway-v1-CanonicalCreateCardTokenRequestFields) |  | Fields for gateway card tokenization |
| transaction_status | [string](#string) |  | Current Status for Transaction |
| external_refund_id | [string](#string) |  | Refund ID for the external refund (PSP side) |
| invoice_id | [string](#string) |  | Invoice ID for the transaction |
| cancel_order | [CanonicalCancelOrderRequest](#canonical_gateway-v1-CanonicalCancelOrderRequest) |  | Cancel order request |
| payment_method | [string](#string) |  | Account identifier for wallet transactions |
| consent_request_fields | [CanonicalConsentRequestFields](#canonical_gateway-v1-CanonicalConsentRequestFields) |  | Request fields related to consent flow |
| conciliation_id | [string](#string) |  | Allows you to keep in conciliation with settlement |
| iso8583_reversal_fields | [CanonicalIso8583ReversalFields](#canonical_gateway-v1-CanonicalIso8583ReversalFields) |  | Fields from ISO 8583 standard integrations (e.g. AMEX, Elavon, BBVA) that are required for reversal operations (e.g. void and partial capture) |
| is_partial | [bool](#bool) |  | Indicates if the transaction is a partial capture or partial refund, where the amount is less than the original invoice/order amount |
| market_type | [string](#string) |  | Indicates the market type for the transaction, intended for integrations such as BBVA. The possible value for this field is MOTO. |
| merchant_custom_transaction_id | [string](#string) |  | A custom ID for a particular transaction defined by the merchant that might be propagated to the PSP |
| current_retries | [int32](#int32) |  | Indicates the current number of retries for a transaction |
| transaction_type | [string](#string) |  | Indicates the original operation when performing a reversal |
| capture_sequence_number | [int32](#int32) |  | Indicates the sequence number of the capture operation, used for partial captures |
| previous_transactions | [CanonicalSingleTransactionInformation](#canonical_gateway-v1-CanonicalSingleTransactionInformation) | repeated |  |
| discounts | [CanonicalDiscount](#canonical_gateway-v1-CanonicalDiscount) | repeated | Discounts associated with the transaction |
| initiator_type | [string](#string) |  | Indicates the initiator type of the transaction |
| recurrence | [CanonicalRecurrence](#canonical_gateway-v1-CanonicalRecurrence) |  | Recurrence information associated with the transaction |
| reversal_fields | [CanonicalReversalFields](#canonical_gateway-v1-CanonicalReversalFields) |  | Reversal fields for reversal operations (e.g. void and partial capture) |
| skip_retries_at_mapping_level | [bool](#bool) |  | Skip retries for the particular operation at the mapping level. |
| sca_exemption_details | [CanonicalSCAExemptionDetails](#canonical_gateway-v1-CanonicalSCAExemptionDetails) |  | The details about a SCA exemption for a particular transaction |
| mappingVersion | [string](#string) |  | Version of the mapping used to process the transaction |
| external_account_request_fields | [CanonicalExternalAccountRequestFields](#canonical_gateway-v1-CanonicalExternalAccountRequestFields) |  | Request fields related to external account connection flow (e.g. Stripe Connect, PagBank Connect) |






<a name="canonical_gateway-v1-CanonicalDeunaTransactionResponse"></a>

### CanonicalDeunaTransactionResponse
CanonicalDeunaTransactionResponse is the response for all transactions methods.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| version | [int32](#int32) |  | The version of the JSON |
| result | [common.v1.CanonicalResult](#common-v1-CanonicalResult) |  | Indicates the result of the transaction (eg: success, error, etc) |
| amount | [CanonicalAmount](#canonical_gateway-v1-CanonicalAmount) |  | Amount of the transaction |
| transaction_id | [string](#string) |  | TransactionID inside DEUNA |
| external_transaction_id | [string](#string) |  | External reference identifier for the transaction |
| authorization_code | [string](#string) |  | Bank confirmation number (Usually 6 characters) |
| step_details | [CanonicalStepDetail](#canonical_gateway-v1-CanonicalStepDetail) | repeated | Array of objects representing the step details |
| three_ds_processor_response_fields | [CanonicalThreeDSProcessorResponseFields](#canonical_gateway-v1-CanonicalThreeDSProcessorResponseFields) |  | Details related to 3DS response fields |
| bank_transfer_processor_response_fields | [CanonicalBankTransferProcessorResponseFields](#canonical_gateway-v1-CanonicalBankTransferProcessorResponseFields) |  | Details related to bank transfer response fields |
| installments | [CanonicalInstallments](#canonical_gateway-v1-CanonicalInstallments) |  | Installments data of the transaction |
| webhook | [CanonicalWebhookResponse](#canonical_gateway-v1-CanonicalWebhookResponse) |  | The webhook |
| next_action | [CanonicalNextAction](#canonical_gateway-v1-CanonicalNextAction) |  | The next action to be taken |
| transaction_status | [string](#string) |  | New status of the transaction |
| installment_plan_response_fields | [CanonicalInstallmentPlanResponseFields](#canonical_gateway-v1-CanonicalInstallmentPlanResponseFields) | repeated | Installment plan details |
| create_card_token_response_fields | [CanonicalCreateCardTokenResponseFields](#canonical_gateway-v1-CanonicalCreateCardTokenResponseFields) |  | Create card token result details |
| cancel_order | [CanonicalCancelOrderResponse](#canonical_gateway-v1-CanonicalCancelOrderResponse) |  | Cancel order response |
| payment_credentials_response_fields | [CanonicalPaymentCredentialsResponseFields](#canonical_gateway-v1-CanonicalPaymentCredentialsResponseFields) |  | Get payment credentials result details |
| payment_methods_response_fields | [CanonicalPaymentMethodsResponseFields](#canonical_gateway-v1-CanonicalPaymentMethodsResponseFields) | repeated | Get customer payment methods details |
| consent_response_fields | [CanonicalConsentResponseFields](#canonical_gateway-v1-CanonicalConsentResponseFields) |  | Consent details |
| iso8583_processing_code | [string](#string) |  | Processing code defining the type of transaction (ISO 8583 field 3) |
| iso8583_response_code | [string](#string) |  | Response code indicating the transaction result (ISO 8583 field 39) |
| iso8583_response_code_description | [string](#string) |  | Human-readable description of the response code |
| psp_switch_name | [string](#string) |  | Name of the payment switch or processor handling the transaction |
| extra_data | [google.protobuf.Struct](#google-protobuf-Struct) |  | Additional data related to the transaction used in settlement |
| method_type | [string](#string) |  | Payment method type: credit_card, pse, wallet, bank_transfer, etc. |
| iso8583_reversal_fields | [CanonicalIso8583ReversalFields](#canonical_gateway-v1-CanonicalIso8583ReversalFields) |  | Fields from ISO 8583 standard integrations (e.g. AMEX, Elavon, BBVA) that are required for reversal operations (e.g. void and partial capture) |
| payment_method_type | [string](#string) |  | Is an optional field that provides more detail when method_type is too generic (e.g., &#34;wallet&#34;) |
| conciliation_id | [string](#string) |  | Unique identifier used for transaction reconciliation, settlement processes, and captures |
| tid | [string](#string) |  | Terminal ID to identify the point of interaction where the transaction was initiated |
| nsu | [string](#string) |  | Unique sequential number assigned to each transaction by the acquirer or payment processor |
| avs | [CanonicalAvsFields](#canonical_gateway-v1-CanonicalAvsFields) |  | The standard AVS code |
| reversal_fields | [CanonicalReversalFields](#canonical_gateway-v1-CanonicalReversalFields) |  | Reversal fields for reversal operations (e.g. void and partial capture) |
| mappingVersion | [string](#string) |  | Version of the mapping used to process the transaction |
| acquirer_transaction_id | [string](#string) |  | Identifier of the transaction assigned by the acquirer/issuer (e.g. GetNet returns &#34;180415202392&#34;) |
| recurrence | [CanonicalRecurrence](#canonical_gateway-v1-CanonicalRecurrence) |  | Recurrence information returned by the PSP (e.g. network_transaction_id, recurrence_data) for stored-credential chaining |
| external_account_response_fields | [CanonicalExternalAccountResponseFields](#canonical_gateway-v1-CanonicalExternalAccountResponseFields) |  | External account connection details (e.g. Stripe Connect, PagBank Connect) |






<a name="canonical_gateway-v1-CanonicalNextAction"></a>

### CanonicalNextAction
CanonicalNextAction is the next action to be taken in the transaction.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| action | [string](#string) |  | Indicates the next action to be taken |
| three_ds_processor_response_fields | [CanonicalThreeDSProcessorResponseFields](#canonical_gateway-v1-CanonicalThreeDSProcessorResponseFields) | optional | Details related to 3DS response fields |
| bank_transfer_processor_response_fields | [CanonicalBankTransferProcessorResponseFields](#canonical_gateway-v1-CanonicalBankTransferProcessorResponseFields) | optional | Details related to bank transfer response fields |
| voucher_processor_response_fields | [CanonicalVoucherProcessorResponseFields](#canonical_gateway-v1-CanonicalVoucherProcessorResponseFields) | optional | Details related to voucher response fields |
| buy_now_pay_later_payment_processor_response_fields | [CanonicalBuyNowPayLaterPaymentProcessorResponseFields](#canonical_gateway-v1-CanonicalBuyNowPayLaterPaymentProcessorResponseFields) | optional | Details related to buy now pay later payment response fields |
| select_installments_response_fields | [CanonicalSelectInstallmentsResponseFields](#canonical_gateway-v1-CanonicalSelectInstallmentsResponseFields) | optional | Details related to select installments next action. |
| wallet_processor_response_fields | [CanonicalWalletProcessorResponseFields](#canonical_gateway-v1-CanonicalWalletProcessorResponseFields) | optional | Details related to wallet response fields |
| reference_processor_response_fields | [CanonicalReferenceProcessorResponseFields](#canonical_gateway-v1-CanonicalReferenceProcessorResponseFields) | optional | Details related to reference payment response fields. |






<a name="canonical_gateway-v1-CanonicalSingleTransactionInformation"></a>

### CanonicalSingleTransactionInformation



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| transaction_id | [string](#string) |  |  |
| type | [string](#string) |  | Refund/capture/authorization/void |
| airline_information | [CanonicalAirlineInformation](#canonical_gateway-v1-CanonicalAirlineInformation) |  | Airline information associated with the transaction |





 

 

 

 



<a name="canonical_gateway_v1_gateway-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## canonical_gateway/v1/gateway.proto



<a name="canonical_gateway-v1-CanonicalGatewayRequest"></a>

### CanonicalGatewayRequest
CanonicalGatewayRequest is the request for the GatewayService methods.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| name | [string](#string) |  | The name of the gateway |
| credentials | [CanonicalCredentials](#canonical_gateway-v1-CanonicalCredentials) |  | The credentials required by the gateway |
| transaction_type | [string](#string) |  | Type of transaction (e.g., auth, refund, void, capture, etc) |
| payment_processor | [CanonicalPaymentProcessor](#canonical_gateway-v1-CanonicalPaymentProcessor) |  | Information about the payment processor |
| extra_params | [google.protobuf.Struct](#google-protobuf-Struct) |  | ExtraParams field when creating the merchant_payment_processor. Contains specific things |






<a name="canonical_gateway-v1-CanonicalGatewayResponse"></a>

### CanonicalGatewayResponse
CanonicalGatewayResponse is the response for the GatewayService methods.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| name | [string](#string) |  | The name of the gateway |
| transaction_type | [string](#string) |  | Type of transaction (e.g., auth, refund, void, capture, etc) |
| transaction_id | [string](#string) |  | The transaction ID of the transaction |





 

 

 

 



<a name="canonical_gateway_v1_merchant-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## canonical_gateway/v1/merchant.proto



<a name="canonical_gateway-v1-CanonicalMerchantRequest"></a>

### CanonicalMerchantRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| name | [string](#string) |  | The name of the merchant |
| url | [string](#string) |  | The URL of the merchant&#39;s site. ex: deuna.com |
| merchant_category_code | [string](#string) |  | MCC. A Merchant Category Code (MCC) is a four-digit number assigned to businesses by credit card companies (like Visa and Mastercard) to classify them based on what type of business or service they provide. Ex: 5411: Grocery Stores and Supermarkets |
| merchant_acquirer_id | [string](#string) |  | Unique identifier assigned to a merchant by their acquiring bank or payment processor. This ID is used to identify the merchant across payment processing systems and transactions |
| country_iso2 | [string](#string) |  | Merchant&#39;s country |






<a name="canonical_gateway-v1-CanonicalMerchantResponse"></a>

### CanonicalMerchantResponse



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| merchant_category_code | [string](#string) |  | MCC. A Merchant Category Code (MCC) is a four-digit number assigned to businesses by credit card companies (like Visa and Mastercard) to classify them based on what type of business or service they provide. Ex: 5411: Grocery Stores and Supermarkets |
| affiliation_code | [string](#string) |  | Code representing the merchant&#39;s affiliation with a payment network or processor |





 

 

 

 



<a name="canonical_gateway_v1_transaction-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## canonical_gateway/v1/transaction.proto



<a name="canonical_gateway-v1-CanonicalTransactionRequest"></a>

### CanonicalTransactionRequest
CanonicalTransactionRequest is the request for the Transaction method.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| gateway | [CanonicalGatewayRequest](#canonical_gateway-v1-CanonicalGatewayRequest) |  | The gateway request |
| transaction | [CanonicalDeunaTransactionRequest](#canonical_gateway-v1-CanonicalDeunaTransactionRequest) |  | The transaction request |
| merchant | [CanonicalMerchantRequest](#canonical_gateway-v1-CanonicalMerchantRequest) |  | Merchant&#39;s info |






<a name="canonical_gateway-v1-CanonicalTransactionResponse"></a>

### CanonicalTransactionResponse
CanonicalTransactionResponse is the response for the Transaction method.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| gateway_response | [CanonicalGatewayResponse](#canonical_gateway-v1-CanonicalGatewayResponse) |  | The gateway response |
| transaction | [CanonicalDeunaTransactionResponse](#canonical_gateway-v1-CanonicalDeunaTransactionResponse) |  | The transaction response |
| merchant | [CanonicalMerchantResponse](#canonical_gateway-v1-CanonicalMerchantResponse) |  | Merchant information |





 

 

 

 



<a name="canonical_gateway_v1_gateway_service-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## canonical_gateway/v1/gateway_service.proto


 

 

 


<a name="canonical_gateway-v1-CanonicalGatewayService"></a>

### CanonicalGatewayService
The gateway service is the main interface for interacting with a gateway.

| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| PurchaseTransaction | [CanonicalTransactionRequest](#canonical_gateway-v1-CanonicalTransactionRequest) | [CanonicalTransactionResponse](#canonical_gateway-v1-CanonicalTransactionResponse) | PurchaseTransaction is used to purchase a transaction. |
| AuthorizeTransaction | [CanonicalTransactionRequest](#canonical_gateway-v1-CanonicalTransactionRequest) | [CanonicalTransactionResponse](#canonical_gateway-v1-CanonicalTransactionResponse) | AuthorizeTransaction is used to authorize a transaction. |
| CaptureTransaction | [CanonicalTransactionRequest](#canonical_gateway-v1-CanonicalTransactionRequest) | [CanonicalTransactionResponse](#canonical_gateway-v1-CanonicalTransactionResponse) | CaptureTransaction is used to capture a transaction. |
| VoidTransaction | [CanonicalTransactionRequest](#canonical_gateway-v1-CanonicalTransactionRequest) | [CanonicalTransactionResponse](#canonical_gateway-v1-CanonicalTransactionResponse) | VoidTransaction is used to void a transaction. |
| RefundTransaction | [CanonicalTransactionRequest](#canonical_gateway-v1-CanonicalTransactionRequest) | [CanonicalTransactionResponse](#canonical_gateway-v1-CanonicalTransactionResponse) | RefundTransaction is used to refund a transaction. |
| GetTransaction | [CanonicalTransactionRequest](#canonical_gateway-v1-CanonicalTransactionRequest) | [CanonicalTransactionResponse](#canonical_gateway-v1-CanonicalTransactionResponse) | GetTransaction is used to get information about a transaction. |
| VerifyThreeDS | [CanonicalTransactionRequest](#canonical_gateway-v1-CanonicalTransactionRequest) | [CanonicalTransactionResponse](#canonical_gateway-v1-CanonicalTransactionResponse) | VerifyThreeDS (legacy) used to finish the 3DS flow: performing the last step of the transaction or getting the status of the transaction after the challenge |
| InitiateThreeDSWeb | [CanonicalTransactionRequest](#canonical_gateway-v1-CanonicalTransactionRequest) | [CanonicalTransactionResponse](#canonical_gateway-v1-CanonicalTransactionResponse) | InitiateThreeDSWeb used to start a web based 3DS flow |
| ContinueThreeDSWeb | [CanonicalTransactionRequest](#canonical_gateway-v1-CanonicalTransactionRequest) | [CanonicalTransactionResponse](#canonical_gateway-v1-CanonicalTransactionResponse) | ContinueThreeDSWeb used to continue the web-based 3DS flow. This is usually called after the 3DS method is executed. Its response usually indicates if a challenge is required or not. |
| CompleteThreeDSWeb | [CanonicalTransactionRequest](#canonical_gateway-v1-CanonicalTransactionRequest) | [CanonicalTransactionResponse](#canonical_gateway-v1-CanonicalTransactionResponse) | CompleteThreeDSWeb used to complete a 3DS flow. This is usually the step where the 3DS challenge result is verified. |
| HandleWebhook | [CanonicalTransactionRequest](#canonical_gateway-v1-CanonicalTransactionRequest) | [CanonicalTransactionResponse](#canonical_gateway-v1-CanonicalTransactionResponse) | HandleWebhook used to handle incoming webhook requests from PSP&#39;s, mainly for status updates |
| InstallmentPlan | [CanonicalTransactionRequest](#canonical_gateway-v1-CanonicalTransactionRequest) | [CanonicalTransactionResponse](#canonical_gateway-v1-CanonicalTransactionResponse) | InstallmentPlan used for manage an installment plan for a concrete payment |
| BankList | [CanonicalTransactionRequest](#canonical_gateway-v1-CanonicalTransactionRequest) | [CanonicalTransactionResponse](#canonical_gateway-v1-CanonicalTransactionResponse) | BankList used to return list of banks to perform a bank transfer operation |
| CreateCardToken | [CanonicalTransactionRequest](#canonical_gateway-v1-CanonicalTransactionRequest) | [CanonicalTransactionResponse](#canonical_gateway-v1-CanonicalTransactionResponse) | CreateCardToken used to tokenize a credit card with PSP&#39;s |
| CancelOrder | [CanonicalTransactionRequest](#canonical_gateway-v1-CanonicalTransactionRequest) | [CanonicalTransactionResponse](#canonical_gateway-v1-CanonicalTransactionResponse) | CancelOrder used to cancel an order depending on the gateway |
| GetPaymentCredentials | [CanonicalTransactionRequest](#canonical_gateway-v1-CanonicalTransactionRequest) | [CanonicalTransactionResponse](#canonical_gateway-v1-CanonicalTransactionResponse) | GetPaymentCredentials used to get credentials for make transactions with wallet SDK&#39;s |
| GetPaymentMethods | [CanonicalTransactionRequest](#canonical_gateway-v1-CanonicalTransactionRequest) | [CanonicalTransactionResponse](#canonical_gateway-v1-CanonicalTransactionResponse) | GetPaymentMethods used to get customer payment methods for make transactions with wallet SDK&#39;s |
| CreatePaymentMethod | [CanonicalTransactionRequest](#canonical_gateway-v1-CanonicalTransactionRequest) | [CanonicalTransactionResponse](#canonical_gateway-v1-CanonicalTransactionResponse) | CreatePaymentMethod used to create a customer payment method to make transaction with Wallet SDK&#39;s |
| DeletePaymentMethod | [CanonicalTransactionRequest](#canonical_gateway-v1-CanonicalTransactionRequest) | [CanonicalTransactionResponse](#canonical_gateway-v1-CanonicalTransactionResponse) | DeletePaymentMethod used to create a customer payment method to make transaction with Wallet SDK&#39;s |
| PostThreeDSPurchaseWeb | [CanonicalTransactionRequest](#canonical_gateway-v1-CanonicalTransactionRequest) | [CanonicalTransactionResponse](#canonical_gateway-v1-CanonicalTransactionResponse) | PostThreeDSPurchaseWeb used to purchase when a 3DS authentication was completed and require a additional step to complete the purchase/auth |
| CreateConsent | [CanonicalTransactionRequest](#canonical_gateway-v1-CanonicalTransactionRequest) | [CanonicalTransactionResponse](#canonical_gateway-v1-CanonicalTransactionResponse) | CreateConsent used to create a payment or account consent for the user to accept or decline |
| GetConsent | [CanonicalTransactionRequest](#canonical_gateway-v1-CanonicalTransactionRequest) | [CanonicalTransactionResponse](#canonical_gateway-v1-CanonicalTransactionResponse) | GetConsent used to get information about a consent. |
| RevokeConsent | [CanonicalTransactionRequest](#canonical_gateway-v1-CanonicalTransactionRequest) | [CanonicalTransactionResponse](#canonical_gateway-v1-CanonicalTransactionResponse) | RevokeConsent used to revoke a user consent. |
| RefreshConsent | [CanonicalTransactionRequest](#canonical_gateway-v1-CanonicalTransactionRequest) | [CanonicalTransactionResponse](#canonical_gateway-v1-CanonicalTransactionResponse) | RefreshConsent used to renew the access token of a user consent. |
| CreateExternalAccount | [CanonicalTransactionRequest](#canonical_gateway-v1-CanonicalTransactionRequest) | [CanonicalTransactionResponse](#canonical_gateway-v1-CanonicalTransactionResponse) | CreateExternalAccount is used to create/link a PSP external account and obtain its authorization link (e.g. Stripe Connect, PagBank Connect onboarding). |
| CompleteExternalAccount | [CanonicalTransactionRequest](#canonical_gateway-v1-CanonicalTransactionRequest) | [CanonicalTransactionResponse](#canonical_gateway-v1-CanonicalTransactionResponse) | CompleteExternalAccount is used to complete a PSP external account connection after the user finishes the authorization flow. |

 





## Scalar Value Types

| .proto Type | Notes | C++ | Java | Python | Go | C# | PHP | Ruby |
| ----------- | ----- | --- | ---- | ------ | -- | -- | --- | ---- |
| <a name="double" /> double |  | double | double | float | float64 | double | float | Float |
| <a name="float" /> float |  | float | float | float | float32 | float | float | Float |
| <a name="int32" /> int32 | Uses variable-length encoding. Inefficient for encoding negative numbers – if your field is likely to have negative values, use sint32 instead. | int32 | int | int | int32 | int | integer | Bignum or Fixnum (as required) |
| <a name="int64" /> int64 | Uses variable-length encoding. Inefficient for encoding negative numbers – if your field is likely to have negative values, use sint64 instead. | int64 | long | int/long | int64 | long | integer/string | Bignum |
| <a name="uint32" /> uint32 | Uses variable-length encoding. | uint32 | int | int/long | uint32 | uint | integer | Bignum or Fixnum (as required) |
| <a name="uint64" /> uint64 | Uses variable-length encoding. | uint64 | long | int/long | uint64 | ulong | integer/string | Bignum or Fixnum (as required) |
| <a name="sint32" /> sint32 | Uses variable-length encoding. Signed int value. These more efficiently encode negative numbers than regular int32s. | int32 | int | int | int32 | int | integer | Bignum or Fixnum (as required) |
| <a name="sint64" /> sint64 | Uses variable-length encoding. Signed int value. These more efficiently encode negative numbers than regular int64s. | int64 | long | int/long | int64 | long | integer/string | Bignum |
| <a name="fixed32" /> fixed32 | Always four bytes. More efficient than uint32 if values are often greater than 2^28. | uint32 | int | int | uint32 | uint | integer | Bignum or Fixnum (as required) |
| <a name="fixed64" /> fixed64 | Always eight bytes. More efficient than uint64 if values are often greater than 2^56. | uint64 | long | int/long | uint64 | ulong | integer/string | Bignum |
| <a name="sfixed32" /> sfixed32 | Always four bytes. | int32 | int | int | int32 | int | integer | Bignum or Fixnum (as required) |
| <a name="sfixed64" /> sfixed64 | Always eight bytes. | int64 | long | int/long | int64 | long | integer/string | Bignum |
| <a name="bool" /> bool |  | bool | boolean | boolean | bool | bool | boolean | TrueClass/FalseClass |
| <a name="string" /> string | A string must always contain UTF-8 encoded or 7-bit ASCII text. | string | String | str/unicode | string | string | string | String (UTF-8) |
| <a name="bytes" /> bytes | May contain any arbitrary sequence of bytes. | string | ByteString | str | []byte | ByteString | string | String (ASCII-8BIT) |

