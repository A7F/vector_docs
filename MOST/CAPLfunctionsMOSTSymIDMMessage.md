[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/CAPLfunctionsMOSTSymIDMMessage.md)

**CAPL Functions** » **MOST** » Symbolic Identification of Messages

# MOST: Symbolic Identification of Messages

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE

For selected CAPL functions, e.g., mostAmsOutput, MOST messages can be described with the name used in the XML function catalog.

The symbolic definition of the message essentially follows the syntax that is used in the MOST specification. All variants are derived from the following basic form:

`FBlock.Instance.Function.OpType(Parameter,Parameter,Parameter)`

**Example**

`AudioAmplifier.1.Mute.Status(MuteOn)`

Essentially it is possible to set raw data for the user data. Accordingly, the parameter bytes have to be set as hexadecimal values in curly brackets. This facilitates, for example, the sending of messages which do not comply with the definition in the function catalog.

**Example**

`Diagnosis.1.KeywordRec.Set({AABB11223344})`

or pure numerical:

`0x06.1.0x050.0x0({AABB11223344})`

Press `<kbd>`Ctrl</kbd>+`<kbd>`M</kbd> or select **Message input with MOST function catalog...** from the shortcut menu to open an input assistant which displays a data entry field in the current program line listing a selection of all MOST messages described in the function catalog. The selection takes in all function catalogs assigned to the CAPL node.

In this context, the input assistant permits the description of messages up to OpType and adds the resulting description to the program text without quotation marks in the notation separated by period marks.

[mostAMSOutput](Functions/CAPLfunctionMOSTAmsOutput.md) • [mostMsgSet](Functions/CAPLfunctionMOSTMsgSet.md) • [Symbolic Identification of Parameters](CAPLfunctionsMOSTSymIDParam.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
