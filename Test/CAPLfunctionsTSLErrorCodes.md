[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/CAPLfunctionsTSLErrorCodes.md)

# Test Service Library: Error Codes

[CAPL Functions](../CAPLfunctions.md) » [Test Service Library](CAPLfunctionsTSLOverview.md) » Error Codes

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

For all [status report functions](CAPLfunctionsTSLStatusReportFunctions.md), the following return values and raised error classes are applied. The query functions always use a wider range of return values. In most cases the particular check of the return value isn't necessary. A simple check to a value >0 (stands for valid) is enough.

Please refer to the specification of each query function to get the complete value range of return values.

| Return Values | Return Value Meanings and Raised Error Class |
|---------------|---------------------------------------------|
| 0             | Query has been performed successfully       |
| -1            | Check does not exist  
**Class**: Access to non-existing check |
| -2            | Check does not support this query  
Class: Invalid query on check |
| -3            | The Check was never active  
**Class**: Invalid query on check |
| -4            | No event has occurred  
Class: Information |
| -5            | Pointer to CAPL-Argument is NULL  
**Class**: Invalid test specification |
| -6            | There are multiple objects that match on this query  
**Class**: Ambiguous query. Multiple objects match on this query |
| -7            | Node layer module is deactivated and cannot process the query |
| -8            | Variable overflow detected |
| -9            | Check is evaluated asynchronously. Function requires an existing check that is executed synchronously. |
| -10           | Check is not evaluated asynchronously. |
| -11           | Data was queried but not yet received from asynchronous evaluation. |
| -12           | Data was used later than it was requested. Data may be outdated. |

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
