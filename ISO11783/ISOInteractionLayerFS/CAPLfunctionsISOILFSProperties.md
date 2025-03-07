[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/CAPLfunctionsISOILFSProperties.md)

**CAPL Functions** » [ISO11783](../CAPLfunctionsISO11783Overview.md) » [File Server Interaction Layer (FS IL)](CAPLfunctionsISOILFSOverview.md) » ISO11783 FS IL Functional Properties

# ISO11783 FS IL Functional Properties

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

These properties describe the functional properties of a real File Server that is simulated with the FS IL.

- **Property Value**: fsVersion
  - **Description**: Version of the File Server according to ISO11783-13.
    - **0**: Draft edition of the International Standard.
    - **1**: Final draft edition of the International Standard.
    - **2**: First published edition of the International Standard.
    - **3**: Second published edition of the International Standard.
    - **4**: Third published edition of the International Standard (AEF Guideline File Server Generation 1.0)
  - **Value Range**: 0..4
  - **Initial Value**: 4
  - **IL must be stopped**: Yes

- **Property Value**: rootDirectory
  - **Description**: Windows folder used as root directory by the File Server.
    - Path must be absolute or relative to the CANoe configuration folder.
    - If unspecified, `FSRootDirectory` is created in the configuration directory.
  - **Value Range**: —
  - **Initial Value**: —
  - **IL must be stopped**: Yes

- **Property Value**: primaryVolume
  - **Description**: Windows folder used as primary volume by the File Server.
    - Must be a subfolder of the root directory or a removable volume.
    - If unspecified, the first removable volume is used.
  - **Value Range**: —
  - **Initial Value**: —
  - **IL must be stopped**: Yes

- **Property Value**: supportsPhyiscalRemovableDevices
  - **Description**: Enables or disables support of physical devices (e.g., USB sticks).
  - **Value Range**: 0..1
  - **Initial Value**: 1
  - **IL must be stopped**: Yes

- **Property Value**: supportsLongFilenames
  - **Description**: Enables or disables support of long filenames for all file server volumes.
    - If supported, filenames may contain UTF-8 characters up to 254 characters.
    - If not, filenames follow the 8.3 name and extension notation.
  - **Value Range**: 0..1
  - **Initial Value**: 1
  - **IL must be stopped**: Yes

- **Property Value**: autoDeleteRoot
  - **Description**: Enables or disables automatic deletion of the root directory.
    - If value is 1, the root directory and all subdirectories and files are deleted on measurement stop.
  - **Value Range**: 0..1
  - **Initial Value**: 0
  - **IL must be stopped**: No

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)