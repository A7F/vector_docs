[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForScopeShowEyeDiagram.md)

# testWaitForScopeShowEyeDiagram

[CAPL Functions](../../CAPLfunctions.md) » [Scope](../../Scope/CAPLfunctionsScopeOverview.md) » testWaitForScopeShowEyeDiagram

**Valid for:** CANoe DE • CANoe4SW DE

## Function Syntax

- `long testWaitForScopeShowEyeDiagram(message frame, dword groupNumber, ScopeAnalyseHandle handle); // form 1`
- `long testWaitForScopeShowEyeDiagram (linFrame frame, dword groupNumber, ScopeAnalyseHandle handle); // form 2`
- `long testWaitForScopeShowEyeDiagram(frFrame frame, dword groupNumber, ScopeAnalyseHandle handle); // form 3`
- `long testWaitForScopeShowEyeDiagram(char nodeName[],dword groupNumber, ScopeAnalyseHandle handle); // form 4`

## Description

Show the eye diagram for a single frame or a node without analysis.

## Parameters

- **frame**: The used CAN, LIN or FlexRay frame for the eye diagram.
- **nodeName**: The node should be used to display the eye diagram.
- **groupNumber**:
  - **Form 1 (CAN):**
    - `0`: Standard Range for a CAN Frame
    - `1`: Arbitration Range for a CAN Frame
    - `2`: Acknowledge Field CAN Frame
    - `3`: Entire CAN Frame
    - `4`: Standard Range for a CAN FD Frame
    - `5`: Arbitration Range for a CAN FD Frame
    - `6`: Acknowledge Field CAN FD Frame
  - **Form 2 (LIN):**
    - `0`: Standard Range for LIN frame (Header and Response)
    - `1`: Only Header for LIN frame
    - `2`: Only Response for LIN Frame
  - **Form 3 (FlexRay):**
    - `0`: Entire FlexRay frame
    - `1`: FSS Field
    - `2`: Header Segment
    - `3`: ProtocolFlags
    - `4`: Frame ID
    - `5`: Payload Length
    - `6`: Header CRC
    - `7`: Cycle Count
    - `8`: Payload Segment
    - `9`: Frame CRC
  - **Form 4(Node):** Depends on the bus system of the node. (See Form 1 to Form 3)
- **handle**: A unique ID.
- **ScopeAnalyseHandle**: Selectors
  - **handle**: A unique ID
  - **Type**: long

## Return Values

- `1`: Successful
- `< 0`: Error occurred. See **EScopeCAPLFitDataReturnCode** in `<application>\Reusable\CAPL_Includes\Scope\` [ScopeBitAnalyse.cin](javascript:startDemoLoader('Reusable\\CAPL_Includes\\Scope'))

## Example

—

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
