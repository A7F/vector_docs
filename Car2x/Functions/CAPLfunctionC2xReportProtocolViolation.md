[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xReportProtocolViolation.md)

**CAPL Functions** » **Car2x** » **C2xReportProtocolViolation**

# C2xReportProtocolViolation

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

## Function Syntax

```c
long C2xReportProtocolViolation(long packet, long severity, char[] scope, long ruleId, char[] ruleName, char[] violationDescription, char[] ruleDescription)
```

## Description

This function creates a new user-defined Car2x Protocol Analyzer protocol violation finding for the specified Car2x packet and shows it in the Protocol Analyzer Window. If the **packet** parameter is nonzero, the Car2x packet must be already sent (not just created) or received in some OnRx CAPL callback.

## Parameters

- **packet**: Handle of a packet that has been created with C2xInitPacket or was provided as callback function parameter. If this parameter is zero, the packet-related features like navigation to the associated trace window line will not be possible for this finding.
- **severity**: 
  - 0 – the protocol violation finding will be shown as error.
  - 1 – the protocol violation finding will be shown as warning.
- **scope**: Text value indicating the position of the rule in the Protocol Analyzer rule tree, each level is separated by the pipe character "|" and corresponds to a separate folder in the tree. For example "My rules|EU|CAM|Custom Rules".
- **ruleId**: Integer number which identifies the rule. Please use numbers above 50000 to avoid interfering with CANoe DE product built-in rules.
- **ruleName**: Short rule name, will be shown in the Protocol Analyzer rule tree.
- **violationDescription**: Detailed description of the violation or unexpected behavior.
- **ruleDescription**: Detailed description of the behavior and/or token values expected by this rule.

## Return Values

- **0**: Success
- **<0**: Error, the protocol violation was not created

## Example

```plaintext
on key ‘x’
{
  C2xReportProtocolViolation(
    0, // packet handle
    1, // Warning
    "My rules|EU|CAM|Custom Rules", // rule scope
    50001, // ruleId
    "CAM version 3", // short rule name
    "violation description",  // violation description
    "expected behavior"); // expected behavior
}
```

[See Also](javascript:void(0);)