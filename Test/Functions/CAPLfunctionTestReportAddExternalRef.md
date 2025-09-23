# TestReportAddExternalRef

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `TestReportAddExternalRef(char[] type, char[] title, char[] ref); // form 1`
- `TestReportAddExternalRef(char[] type, char[] title, char[] ref, char[] owner); // form 2`

## Description

Adds an external reference to the report (URL, DOORS or eASEE link), which appears as a link in the test report. Can be used in test cases (test case functions), test groups or in MainTest functions.

## Parameters

- **type**: "url" for any kinds of URLs, "doors" for links to DOORS, "easee" for links to eASEE.
- **title**: Text with which the link generated in the test report is displayed. If not indicated the URL indicated in ref is used.
- **ref**: The URL of the external resource, which is referenced.
- **owner**: This attribute is intended to be used by applications which maintain links to external resources automatically so they can identify their external reference elements. It’s recommended not to use it individually.

## Return Values

—

## Example

```c
testcase tc_1_1()
{
   TestCaseTitle("tc_1_1", "Test Case 1.1");
   TestReportAddExternalRef("url", "Requirement", 
   "doors://doorssrv:36677/?version=1,prodID=0,dbid=42d2481361dc551c,container=00004600,object=19");
   ...
}
```

[TestGetVerdictModule](CAPLfunctionTestGetVerdictModule.md)
