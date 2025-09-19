[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/CAPLfunctionsISOILVTProperties.md)

[CAPL Functions](../../CAPLfunctions.md) » [ISO11783](../CAPLfunctionsISO11783Overview.md) » [Virtual Terminal Interaction Layer (VT IL)](CAPLfunctionsISOILVTOverview.md) » ISO11783 VT IL Properties

# ISO11783 VT IL Properties

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Virtual Terminal Properties

- **vtVersion**
  - Description: Version of the Virtual Terminal according to ISO11783-6.
  - Value Range: 0..6
  - Initial Value: 5
  - IL must be stopped: Yes

- **touchScreen** (previously "transmitPointingEvent")
  - Description: Transmit Pointing event at a click in the data mask.
  - Value Range: 0..1
  - Initial Value: 1
  - IL must be stopped: Yes

- **pointingDevice**
  - Description: Transmit Pointing event at a click in the data mask.
  - Value Range: 0..1
  - Initial Value: 1
  - IL must be stopped: Yes

- **reportDragOperation**
  - Description: Cyclic transmission of Pointing event while dragging.
  - Value Range: 0..1
  - Initial Value: 0
  - IL must be stopped: Yes

- **intermediateDragCoordinates**
  - Description: Transmit Pointing event with the current coordinates while dragging. If value is 0 only the start coordinates of the dragging process are transmitted.
  - Value Range: 0..1
  - Initial Value: 0
  - IL must be stopped: Yes

- **simultaneousKeyActivation**
  - Description: Simultaneous activation of physical Soft Keys.
  - Value Range: 0..1
  - Initial Value: 0
  - IL must be stopped: Yes

- **simultaneousButtonActivation**
  - Description: Simultaneous activation of buttons.
  - Value Range: 0..1
  - Initial Value: 0
  - IL must be stopped: Yes

- **multipleFrequencyAudioOutput**
  - Description: Multiple frequency audio output.
  - Value Range: 0..1
  - Initial Value: 0
  - IL must be stopped: Yes

- **adjustableVolumeAudioOutput**
  - Description: Adjustable volume audio output.
  - Value Range: 0..1
  - Initial Value: 0
  - IL must be stopped: Yes

- **multisoundAudioOutput**
  - Description: Multisound audio output (simultaneously supporting the Control Audio Signal command from more than one Working).
  - Value Range: 0..1
  - Initial Value: 0
  - IL must be stopped: Yes

- **bootTime**
  - Description: Maximum number of seconds from a power cycle to transmission of first VT status message (this value is only used in the Get Hardware response).
  - Value Range: 0..255
  - Initial Value: 255
  - IL must be stopped: Yes

- **availableMemory**
  - Description: If the object pool size in a Get Memory message of an implement is bigger than this value then the Get Memory response of the Virtual Terminal contains the status value 1 (There is not enough memory available). Otherwise the status value is 0 (There can be enough memory).
  - Value Range: 0..4294967295
  - Initial Value: 4294967295
  - IL must be stopped: No

- **colors**
  - Description: Number of colors which are supported.
  - Value Range: 2,16,256
  - Initial Value: 256
  - IL must be stopped: Yes

- **dataMaskSize**
  - Description: Width and height of the square data mask in pixel.
  - Value Range: 200..2000
  - Initial Value: 400
  - IL must be stopped: Yes

- **softKeyMaskWidth**
  - Description: Width of a soft key in pixel.
  - Value Range: 10..255
  - Initial Value: 80
  - IL must be stopped: Yes

- **softKeyMaskHeight**
  - Description: Height of a soft key in pixel.
  - Value Range: 10..255
  - Initial Value: 80
  - IL must be stopped: Yes

- **numberOfPhysicalSoftKeys**
  - Description: Number of physical Keys per Soft Key Mask.
  - Value Range: 1..64
  - Initial Value: 10
  - IL must be stopped: Yes

- **numberOfVirtualSoftKeys**
  - Description: Number of virtual Soft Keys per Soft Key Mask. Since VT version 4 the number of virtual Soft Keys is always 64 and cannot be modified.
  - Value Range: 6..64
  - Initial Value: 64
  - IL must be stopped: Yes

- **numberOfVisibleWorkingSets**
  - Description: Number of Working Sets which are displayed in Virtual Terminal at the same time.
  - Value Range: 1..10
  - Initial Value: 64
  - IL must be stopped: Yes

- **numberOfUserLayoutDataMasks**
  - Description: Number of User-Layout (Data) Masks. This setting is only available with Virtual Terminal version 4 or higher.
  - Value Range: 0..10
  - Initial Value: 1
  - IL must be stopped: Yes

- **numberOfUserLayoutSoftKeys (previously "numberOfUserLayoutSoftKeyMasks")**
  - Description: Number of User-Layout Soft Keys per User-Layout Mask. This setting is only available with Virtual Terminal version 4 or higher.
  - Value Range: 0..64
  - Initial Value: 10
  - IL must be stopped: Yes

- **textFontData**
  - Description: Supported font properties according to message Get Text Font Data Response (PGN).
  - Value Range: 0x000000..0xFFFFFF
  - Initial Value: 0xFFFFFF
  - IL must be stopped: Yes

- **languageCode**
  - Description: Language code according to byte 1-2 of message Language command (PGN 65039).
  - Value Range: 0..0xFFFF
  - Initial Value: 0x656E ("en")
  - IL must be stopped: No

- **formatNumberDataUnit**
  - Description: Supported number, data and unit format according to byte 3-6 of message Language command (PGN 65039).
  - Value Range: 0..0xFFFFFFFF
  - Initial Value: 0x40000000
  - IL must be stopped: No

- **enableSound**
  - Description: Enables or disables output of acoustic signals of the Virtual Terminal.
  - Value Range: 0..1
  - Initial Value: 1
  - IL must be stopped: No

- **enablePassiveMode**
  - Description: Enables or disables the passive mode of the Virtual Terminal. If property enableAutoDetection is not set then the Virtual Terminal is monitored that has the same node address as defined in the database.
  - Value Range: 0..1
  - Initial Value: 0
  - IL must be stopped: Yes

- **enableAutoDetection**
  - Description: Enables or disables the auto detection of the Virtual Terminal address. If enabled then the Virtual Terminal that registers first on the bus with an Address Claimed message is monitored. This property has only impact if passive mode is enabled.
  - Value Range: 0..1
  - Initial Value: 0
  - IL must be stopped: Yes

- **autoDetectionFunctionInstance**
  - Description: If value is not -1 the auto detected Virtual Terminal must have this Function Instance. This property has only impact if passive mode is enabled and property enableAutoDetection is set.
  - Value Range: 0..31, -1
  - Initial Value: -1
  - IL must be stopped: Yes

- **enableOperatorInputInPassiveMode**
  - Description: If value is 0 no operator input is possible in the passive mode. All functions of section 'VT - Handling' will fail and the VT IL does not send any message. If value is 1 then operator input (e.g. pressing buttons or editing values via the VT IL) is possible. Please notice that in this case the VT IL sends messages from the same address like the real VT and therefore this can influence the real Virtual Terminal.
  - Value Range: 0..1
  - Initial Value: 0
  - IL must be stopped: No

- **enableWorkingSetSynchronization**
  - Description: Enables or disables the synchronization of the active Working Set if the passive mode is enabled. This functionality is useful for fault injection to simulate the communication between a Virtual Terminal and a not-active implement. After the property is set to 0, the call of [VTIL_ActivateWorkingSet](Functions/CAPLfunctionIso11783VTILActivateWorkingSet.md) and following [VTIL_PressButton](Functions/CAPLfunctionIso11783VTILPressButton.md) or any other VT-Handling method result in the communication between the Virtual Terminal and a not active working set.
  - Value Range: 0..1
  - Initial Value: 1
  - IL must be stopped: No

- **isbServer**
  - Description: The ISB server support is switched on. The Virtual Terminal cyclically sends the message **All Implements Stop Operations Switch State**, which can be observed by ISB clients. The CAPL function [VTIL_PressISB](Functions/CAPLfunctionIso11783VTILPressISB.md), can be called.
  - Value Range: 0..1
  - Initial Value: 0
  - IL must be stopped: Yes

- **locationOfStoredObjectPools**
  - Description: The VT IL uses this folder for keeping of object pools, i.e. as a storage location for **Store version** message and **Load version** message. On each measurement stop, the folder is cleared. If you use more than one VT IL and have to avoid the VT ILs overwrite the object pools of each other, you can specify an own folder for every VT IL with this property.
  - Value Range: Any valid path relative to `` `<%Temp%\CANoeVTILDataTmp>` ``
  - Initial Value: `` `<%Temp%\CANoeVTILDataTmp\VTData>` ``
  - IL must be stopped: No

- **fontName**
  - Description: Changes the font which is used to draw text in Virtual Terminal masks. This property has only impact if you save a mask via [VTIL_SaveAsImage](Functions/CAPLfunctionIso11783VTILSaveAsImage.md).
  - Value Range: Font name of an installed font e.g. Arial, Calibri, …
  - Initial Value: Courier New
  - IL must be stopped: No

- **proportionalFontName**
  - Description: Changes the proportional font which is used to draw text in Virtual Terminal masks. This property has only impact if you save a mask via [VTIL_SaveAsImage](Functions/CAPLfunctionIso11783VTILSaveAsImage.md).
  - Value Range: Font name of the AEF font (ISOBUS-FONT) or an installed proportional font e.g. Calibri, Segoe UI, …
  - Initial Value: AEF ISOBUS-FONT
  - IL must be stopped: No

- **nonProportionalFontName**
  - Description: Changes the non-proportional font which is used to draw text in Virtual Terminal masks. This property has only impact if you save a mask via [VTIL_SaveAsImage](Functions/CAPLfunctionIso11783VTILSaveAsImage.md).
  - Value Range: Font name of an installed non-proportional font e.g. Courier New, Consolas, …
  - Initial Value: Courier New
  - IL must be stopped: No

- **errorHandling**
  - Description: Changes the way the Virtual Terminal handles object pool errors. Errors can be detected after an object pool transfer or while drawing masks and soft keys.
    - 0: Deletes the object pool
    - 1: Deactivates the object pool: The user can no longer operate the object pool but object pool is not deleted (so you can still export the object pool)
    - 2: Deactivates the object pool (same as value 1). Additionally for minor errors (e.g. an unsupported color) the Virtual Terminal tries to display mask and buttons as good as possible.
  - Value Range: 0..2
  - Initial Value: —
  - IL must be stopped: —

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)