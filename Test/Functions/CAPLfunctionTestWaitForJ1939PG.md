[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForJ1939PG.md)

**CAPL Functions** » **Test Feature Set** » **TestWaitForJ1939PG**

# TestWaitForJ1939PG

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestWaitForJ1939PG (dbMsg aMessage, dword aTimeout);`
- `long TestWaitForJ1939PG (dword aPGN, dword aTimeout);`
- `long TestWaitForJ1939PG (dword aPGN, dword aSourceAddress, dword aDestinationAddress, dword aTimeout);`

## Description

Waits for the occurrence of the specified J1939 parameter group. Should the message not occur before the expiration of the time **aTimeout**, the wait condition is resolved nevertheless.

To get the message content of the parameter group which triggered the wait condition you can use function [TestGetWaitJ1939PGData](CAPLfunctionTestGetWaitJ1939PGData.md).

**Note**: Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aMessage**: Message that should be awaited. Must be a J1939 parameter group.
- **aPGN**: Parameter Group Number (with data page) of the message that should be awaited.
- **aSourceAddress**: Source address of the message that should be awaited or 0xFFFFFFFF if source address is ignored.
- **aDestinationAddress**: Destination address of the message that should be awaited or 0xFFFFFFFF if destination address is ignored.
- **aTimeout**: Maximum time that should be waited [ms] (Transmission of 0: no timeout controlling).

## Return Values

- **-2**: Resume due to constraint violation
- **-1**: General error, for example, functionality is not available
- **0**: Resume due to timeout
- **1**: Resume due to event occurred

## Example

```plaintext
long result;
//wait for RQST PG (sent form SA=0x01 to DA=0xAA) for 2000 ms
result = TestWaitForJ1939PG(0xEA00, 0x01, 0xAA, 2000);
if (result == 1)
{
  pg RQST pgRQST; //PG RQST has to be defined in the attached DBC file
  result = TestGetWaitJ1939PGData(pgRQST);
  if (result == 0)// obtain the received RQST PG
  {
    if (pgRQST.ParameterGroupNumber == 0x1234) //check content of the received PG
    {
      TestStepPass("Validation", "Request for PGN 0x1234 occurred");
      // do something, e.g. send response...
    }
  }
  else
  {
    TestStepFail("Validation", "Failed to get data of received PG RQST: unexpected error %d", result);
  }
}
else if(result == 0)
{
  TestStepFail("Validation", "Expected PG RQST is not received within 2000 ms");
}
else
{
  TestStepFail("Validation", "TestWaitForJ1939PG(0xEA00, 0x01, 0xAA, 2000): unexpected error %d", result);
}
```

[TestJoinJ1939PGEvent](CAPLfunctionTestJoinJ1939PGEvent.md) • [TestGetWaitJ1939PGData](CAPLfunctionTestGetWaitJ1939PGData.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
