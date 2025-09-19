[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkQueryEventSignalValueAsyncResult.md)

**CAPL Functions** » **Test Service Library** » **Status Report Functions** » **ChkQuery_EventSignalValue_AsyncResult**

# ChkQuery_EventSignalValue_AsyncResult

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

- `long ChkQuery_EventSignalValue_AsyncResult(dword checkId, double pValue[]); // form 1`
- `long ChkQuery_EventSignalValue_AsyncResult(dword checkId, int64& value); // form 2`

## Method Syntax

- `check.QueryEventSignalValueAsyncResult(double pValue[]); // form 1`
- `check.QueryEventSignalValueAsyncResult(int64& value); // form 2`

## Description

This function enables access to the signal value which was last reported by a check as invalid. The signature of the function with the same name without the pValue parameter enables access only to positive signal values. This function enables access to signal values in any directory. The data has to be queried first using [testWaitForCheckQuery](CAPLfunctionTestWaitForCheckQuery.md).

## Parameters

- **checkId**: Identifier of the queried Check.
- **double *pValue**:
  - **Note**: This requires the transfer of an array.

## Return Values

- **≤ 0**: Refers the query [error codes](../CAPLfunctionsTSLErrorCodes.md)

## Available For

- [ChkCreate_MsgSignalValueRangeViolation](CAPLfunctionChkCreateMsgSignalValueRangeViolation.md)
  - Result: Value of the last signal that was bad
- [ChkCreate_MsgSignalValueInvalid](CAPLfunctionChkCreateMsgSignalValueInvalid.md)
  - Result: Value of the last signal that was bad

## Example

```plaintext
result = testWaitForCheckQuery(checkId, 10000);
if (result == 1)
{
  double lBadValue[1]; // use an array to allow "call-by-reference"; length: 1 element
  ChkQuery_EventSignalValue_AsyncResult(aCheckId, lBadValue);
  write("Last bad signal value=%g", lBadValue[0]);
}
```

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
