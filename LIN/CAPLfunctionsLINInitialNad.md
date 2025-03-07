[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/CAPLfunctionsLINInitialNad.md)

[CAPL Functions](../CAPLfunctions.md) » Notes to the Way initial NAD is determined

# LIN: Notes to the Way initial NAD is determined

[Valid for](../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

If initial NAD is not explicitly specified in the associated database some heuristic is used to determine it. By default, the configured NAD (an attribute defined in the associated database) is taken. If there are schedule tables defined they are searched for corresponding AsssignNAD command and initial NAD is extracted from the parameters of that command.

•  Technical References are only available in English

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)