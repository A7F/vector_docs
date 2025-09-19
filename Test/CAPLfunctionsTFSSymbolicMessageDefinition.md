[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/CAPLfunctionsTFSSymbolicMessageDefinition.md)

**CAPL Functions** » **Test Feature Set** » Symbolic definition of MOST messages

# Test Feature Set: Symbolic definition of MOST messages

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE

In many send and wait commands for MOST, MOST messages can be specified symbolically. Here the relevant MOST message, which under some circumstances can also contain wildcards and parameters, is defined by a character string. The MOST message is resolved by the incorporated XML function catalog.

**Symbolic Definition of MOST Messages**

The symbolic definition of the message essentially follows the syntax that is used in the MOST specification. All variants are derived from the following basic form:

`FBlock.Instance.Function.OpType(Parameter,Parameter,Parameter)`

In some commands, parts of this can be omitted; these are then regarded as "arbitrary". However, not all conceivable forms are permitted, as this would prevent the specifications being distinguished uniquely from one another. For information about which forms are permitted, see the description of the relevant commands.

Essentially it is possible to set raw data for the user data. Accordingly, the parameter bytes have to be set as hexadecimal values in curly brackets. This facilitates, for example, the sending of messages which do not comply with the definition in the function catalog.

**Example**

`Diagnosis.1.KeywordRec.Set({AABB11223344})`

or pure numerical:

`0x06.1.0x050.0x0({AABB11223344})`

## Specification of Names for FBlock, Function and OpType

The following special separators are used:

- Commas (to separate parameters in the parameter list)
- Dots (to separate the FBlockID, FunctionID etc.)
- Round brackets (to identify the parameter list)

These separators cannot be used in names.

All characters between separators belong to the specification in question. Blank spaces are also permitted in symbolic names. Without additional specifications, numeric specifications are decimal numbers; with leading 0x, they are hexadecimal specifications. The numeric values to be transferred must be specified here. Information that may be stored in the function catalog about units and conversion factors is not taken into consideration. String parameters are enclosed in simple quotation marks.

**Note**

In hexadecimal mode, hexadecimal specifications are displayed in the Trace Window in the inline disassembly column without a leading 0x; in decimal mode, they are displayed with a 0x. Therefore, these lines can be used in decimal mode directly as a message definition (copy & paste).

FBlock, Function, OpType can each be specified as symbolic names or numeric IDs. The symbolic names cannot, therefore, completely take on the form of decimal or hexadecimal numbers. By contrast, the form of partial strings will work. The InstanceID must be a numeric value.

The name *has a special role. It stands for any value (wildcard). Since for the resolution of function names in the XML function catalog the FBlock must be known, a wildcard for the FBlock is only permitted if the function is arbitrary or specified numerically. The parameter list contains the parameters of the message in the sequence they are stored in the message and defined in the XML function catalog. The parameters are separated by commas. The parameters can represent numeric values or symbolic values (e.g., in case of enumerations) that are resolved using the XML function catalog.* is also permitted for an arbitrary value. The parameter list does not have to be complete; however, for reasons of clarity only an omission at the end of the list is possible. Specifications that are not present always count as "arbitrary".

## Expanded Wait Functions

An expanded wait condition arises only for the wait instructions for which the message definition contains a parameter list. Here, as well as a message that fits the specified signature of FBlock, Instance, Function, and OpType being expected, in addition, the specified parameters must correspond with the parameters of the message received. As with all wait instructions, all received messages that fit only a part of the specified signature are ignored. This means that the reception of such messages does not cause the wait condition to be abandoned.

## Error Handling

In the event of an error during parsing and resolution of the message string, all functions show a return value. In this case the function returns immediately without waiting. The error is displayed in the Write Window and recorded in the report, but the measurement is not aborted.

This behavior can be changed with the [TestSetParseErrorConstraint](Functions/CAPLfunctionTestSetParseErrorConstraint.md) command for all subsequent test commands with symbolic message definition so that these set the verdict of the test case to "fail".

The command must not be used in the context of a test case; however, it can be used at test module level (that is, in main test). However, if the command is used in the context of a test case, at the end of the test case the mode reverts to what it was at the beginning of the test case. This ensures the locality of the test case. The execution of a test case does not affect test cases that may be executed subsequently.

The InstanceID can be specified in each case as a parameter or as a part of the symbolic message definition. If both specifications are present, a warning will be output at runtime and the parameter value used. The value in the string is ignored (no measurement abort). If no InstanceID is specified explicitly, then this is regarded as "arbitrary".

**Example**

```plaintext
TestWaitForMostMessage ("AudioAmplifier.2.Mute.Status", 200);
SUTInstID = ...;
TestWaitForMostAMSMessage ("AudioAmplifier.Mute.Status(MuteOn)", SUTInstID, 200);
TestJoinMostReportEvent ("NetBlock.2.Shutdown");
```

Press `<Ctrl>`+`<M>` or select **Message input with MOST function catalog...** from the shortcut menu to open an input assistant which displays a data entry field in the current program line listing a selection of all MOST messages described in the function catalog. The selection takes in all function catalogs assigned to the CAPL node.

In this context, the input assistant permits the description of messages up to parameter values and adds the resulting description to the program text in quotation marks.

In the event of an error during parsing and resolution of the message string, all functions show a return value. In this case the function returns immediately without waiting. The error is displayed in the Write Window and recorded in the report.

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
