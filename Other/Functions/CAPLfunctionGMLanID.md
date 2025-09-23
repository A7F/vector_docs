[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionGMLanID.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » gmLanId

# gmLanId

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `dword gmLanId (dbMsg aMessage, dword aSourceId); // form 1`
- `dword gmLanId (dbMsg aMessage, Node aTxNode); // form 2`

## Description

This function can be used to create a message ID for a GMLAN message. In addition to the message, you must specify the transmission node or its source ID.

The message ID returned can be used, for example, to wait for a specific GMLAN message with the [TestWaitForMessage](../../Test/Functions/CAPLfunctionTestWaitForMessage.md) function.

## Parameters

- **aMessage**: GMLAN message for which a message ID is to be created.
- **aSourceId**: Source ID of the node to be coded as the transmission node in the message ID.
- **aTxNode**: Node to be coded as the transmission node in the message ID.

## Return Values

If the message is a GMLAN message, a GMLAN message ID will be returned containing the correct source address and priority. Otherwise, the message ID will be returned.

## Example

```plaintext
dword gmID = 0;
long result = 0;
gmID = gmLanId(Comfort::Console_1, 48);
waitResult = TestWaitForMessage(gmID, 5000);
```
