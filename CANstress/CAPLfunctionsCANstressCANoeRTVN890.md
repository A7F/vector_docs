[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANstress/CAPLfunctionsCANstressCANoeRTVN890.md)

**CAPL Functions** » **CANstress** » **CANstress and Distributed Mode**

# CANstress and Distributed Mode

[Valid for](../../Shared/FeatureAvailability.md):  CANoe DE

Since version 7.5 SP2 of CANoe, the use of CANstress integration in combination with [distributed mode](../../CANoeCANalyzer/RTSetup/DistributedMode/DistributedModeConcept.md) is simplified.

## Important Changes

- The [CANstressOpen](Functions/CAPLfunctionCANstressOpen.md) command now supports the specification of CANstress configuration files as [application data](../../CANoeCANalyzer/Ribbon/File/Options/Extensions/ExtensionsUserFiles.md).
- For access to CANstress devices via CANstress commands in CANoe, it is no longer necessary to install the CANstress application. All necessary components are now part of CANoe. The CANstress application is now needed only to create configuration files. In CANoe version 7.5 SP2 and higher, the access to CANstress devices that are connected to VN8900 is also supported.

The following must be noted for use of CANstress commands together with distributed mode:

- All CANstress configuration files used must be entered in the CANoe configuration as user files. They are transferred automatically to the RT server or the VN8900 at the start of a measurement.
- For example, if a configuration is needed for access to multiple devices, access to the correct device can be configured using the configuration page for CANstress. This requires the CANstress devices to first be connected to the correct system. When distributed mode is used, this is the RT server. If a VN8900 is used, CANstress devices must be connected there. With distributed mode, the connection to the RT server is then established in the Options. With VN8900, only the correct configuration of the channels used is needed to establish the connection automatically. If Options is now reopened and the CANstress configuration page is displayed, the CANstress devices are searched for on the correct system, and the configuration on that system is displayed. Changes to the configuration are then saved on the correct system.

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)