# OnProtocolViolation (Callback)

[CAPL Functions](../../CAPLfunctions.md) » [Car2x](../CAPLfunctionsCar2xOverview.md) » OnProtocolViolation

**Valid for**: CANoe DE

## Function Syntax

```c
void OnProtocolViolation(long severity, long stationId, char scope[], long ruleId, char ruleName[], char violationDescription[], char ruleDescription[]){}
```

## Description

A CAPL callback function informing you about a new Protocol Analyzer finding. When defined in Car2x node’s CAPL file, this function will be called each time when CANoe DE product build-in rules or user defined rule detects the protocol violation and create the finding.

## Parameters

- **severity**: 
  - 0 – the protocol violation finding was defined as error
  - 1 – the protocol violation finding was defined as warning

- **stationId**: 
  - Id of the station that caused the protocol violation.

- **scope**: 
  - Text value indicating the position of the rule in the Protocol Analyzer rule tree, each level is separated by the pipe character "|" and corresponds to a separate folder in the tree. For example "My rules|EU|CAM|Custom Rules".

- **ruleId**: 
  - Integer number which identify the rule

- **ruleName**: 
  - Short rule name, will be shown in the Protocol Analyzer rule tree

- **violationDescription**: 
  - Detailed description of the violation or unexpected behavior

- **ruleDescription**: 
  - Detailed description of the behavior and/or token values expected by this rule

## Return Values

—

## Example

```c
void OnProtocolViolation(long severity, long stationId, char scope[], long ruleId, char ruleName[],
char violationDescription[], char ruleDescription[])
{
  char stationName[1024];

  C2xGetStationName(stationId, elcount(stationName), stationName);

  write("Station handle: %d", stationId);
  write("Station name: %s", stationName);
  write("OnProtocolViolation: %s", ruleDescription);
}
```
