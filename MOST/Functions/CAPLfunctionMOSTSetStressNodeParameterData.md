[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTSetStressNodeParameterData.md)

**CAPL Functions** » [MOST](../CAPLfunctionsMOSTOverview.md) » mostSetStressNodeParameterData

# mostSetStressNodeParameterData

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

**Note**  
This function is only available with MOST hardware OptoLyzer G2 3150o.

## Function Syntax

```plaintext
long mostSetStressNodeParameterData(long channel, long id, long datalen, byte data[]);
```

## Description

**OptoLyzer G2 3150o:**  
The OptoLyzer G2 3150o for MOST150 provides stress functionality through an additional network interface controller (NIC). With `mostSetStressNodeParameterData` the MOST node parameters of this additional NIC can be configured.

## Parameters

- **channel**  
  Channel of the connected interface.

- **id**  
  Parameter identification:

  - **ID:** 4  
    **Description:** Configure the response of the stress node when receiving NetBlock.FBlockIDs.Get. A sequence of pairs (FBLockID, InstID) with up to 22 entries (44 bytes) can be set. The response message NetBlock.FBlockIDs.Status transports the sequence in its parameter section.  
    **Value Range / Meaning:** 0 \<\= datalen \<\= 44  
    **Availability:** OptoLyzer G2 3150o

- **datalen**  
  Number of bytes to be set.

- **data**  
  Bytes to be set.

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md).

## Example

—

[mostSetStressNodeParameter](CAPLfunctionMOSTSetGetStressNodeParameter.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
