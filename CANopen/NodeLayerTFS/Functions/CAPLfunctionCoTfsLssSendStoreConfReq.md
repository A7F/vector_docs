# coTfsLssSendStoreConfigurationRequest (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssSendStoreConfigurationRequest( byte[] pErrorCode, byte[] pSpecificError );
```

## Description

The function sends a **LSS Store Configuration** request and waits for the response.

## Parameters

- **pErrorCode**: Error code.
  - 0 - protocol successfully completed
  - 1 - store configuration not supported
  - 2 - storage media access error
  - 255 - implementation specific error occurred

- **pSpecificError**: Manufacturer specific error (used if error code = 255).

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
byte pErrorCode[1];
byte pSpecificError[1];

/* send LSS store configuration request */

if (coTfsLssSendStoreConfigurationRequest( pErrorCode, pSpecificError) == 1) {
  /* sent LSS store configuration request and received response */
  /* received values can be found in pErrorCode[0], pSpecificError[0] */
}
```
