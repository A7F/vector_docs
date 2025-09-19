[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xProtocolAnalyzerGetRuleList.md)

**CAPL Functions** » **Car2x** » **C2xProtocolAnalyzerGetRuleList**

# C2xProtocolAnalyzerGetRuleList

[Valid for CANoe DE](../../../Shared/FeatureAvailability.md)

## Function Syntax

```c
long C2xProtocolAnalyzerGetRuleList(long bufferSize, char[] buffer)
```

## Description

This function copies the multiline text representation of the Car2x Protocol Analyzer rules to the variable specified by **buffer** function parameter.

The `[x]` and `[ ]` symbols before each single rule or rule group name represent the **active** status. The `[o]` symbol before a rule group means **partially active**, at least one rule in this rule group was deactivated.

## Parameters

- **bufferSize**: Maximum number of bytes to be copied.
- **buffer**: Buffer in which the multiline text representation of the Car2x Protocol Analyzer rules is copied.

## Return Values

- **0**: Success
- **`< 0`**: Error, target buffer too small or error occurred during copying the Protocol Analyzer rules.

## Example

```c
void TestReportAddProtocolAnalyzerRuleList()
{
  char rules[40000], ruleline[1000];
  long offset, i, lineStartPos, lineEndPos;
  TestReportAddMiscInfoBlock("Protocol Analyzer rule list:");
  if (C2xProtocolAnalyzerGetRuleList(elcount(rules), rules) == 0)
  {
    // Add Protocol Analyzer rule list to the test report line by line
    while (lineEndPos != -1)
    {
      lineEndPos = strstr_off(rules, offset, "\n");
      if (lineEndPos != -1)
      {
        substr_cpy(ruleline, rules, lineStartPos, lineEndPos-lineStartPos, elcount(ruleline));
        offset = lineStartPos = lineEndPos + 1;
        TestReportAddExtendedInfo("text", ruleline);
        // write(ruleline);
      }
    }
  }
}
```

[See Also](javascript:void(0);)