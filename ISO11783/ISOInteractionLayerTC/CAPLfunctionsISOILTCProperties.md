[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/CAPLfunctionsISOILTCProperties.md)

[CAPL Functions](../../CAPLfunctions.md) » [ISO11783](../CAPLfunctionsISO11783Overview.md) » [Task Controller Interaction Layer (TC IL)](CAPLfunctionsISOILTCOverview.md) » ISO11783 TC IL Functional Properties

# ISO11783 TC IL Functional Properties

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

These properties describe the functional properties of a real Task Controller that is simulated with the TC IL.

- **Property Value**: `tcVersion`
  - **Description**: Version of the Task Controller according to ISO11783-10.
  - **Value Range**: 0..4
  - **Initial Value**: 4
  - **IL must be stopped**: Yes

- **Property Value**: `bootTime`
  - **Description**: Maximum number of seconds from a power cycle to transmission of first **Task Controller Status message**.
  - **Value Range**: 0..255
  - **Initial Value**: 255
  - **IL must be stopped**: Yes

- **Property Value**: `availableMemory`
  - **Description**: If the object pool size in a Request Object-pool Transfer message of a client is bigger than this value then the Request Object-pool Transfer Response message of the Task Controller contains the status value **1** (There is not enough memory available). Otherwise the status value is **0** (There may be enough memory).
  - **Value Range**: 0..4294967295
  - **Initial Value**: 100000
  - **IL must be stopped**: Yes

- **Property Value**: `options`
  - **Description**:
    - Bit 0: Supports TC-BAS
    - Bit 1: Supports TC-GEO without position based control
    - Bit 2: Supports TC-GEO with position based control
    - Bit 3: Supports Peer Control
    - Bit 4: Supports TC-SC (Section Control)
    - Bit 5-15: Reserved
    - This value is sent with the Version message
  - **Value Range**: 0..FFFFh
  - **Initial Value**: 65535
  - **IL must be stopped**: Yes

- **Property Value**: `numberOfBooms`
  - **Description**: Maximum number of section control booms that is supported for Section Control. This value is sent with the Version message.
  - **Value Range**: 0..255
  - **Initial Value**: 255
  - **IL must be stopped**: Yes

- **Property Value**: `numberOfSections`
  - **Description**: Maximum number of sections that is supported for Section Control. This value is sent with the Version message.
  - **Value Range**: 0..255
  - **Initial Value**: 255
  - **IL must be stopped**: Yes

- **Property Value**: `numberOfControlChannels`
  - **Description**: Maximum number of individual control channels that is supported for position based control. This value is sent with the Version message.
  - **Value Range**: 0..255
  - **Initial Value**: 255
  - **IL must be stopped**: Yes

- **Property Value**: `enablePassiveMode`
  - **Description**: Enables (1) or disables (0) the passive mode of the Task Controller. If property **enableAutoDetection** is not set then the Task Controller is monitored that has the same node address as defined in the database.
  - **Value Range**: 0..1
  - **Initial Value**: 0
  - **IL must be stopped**: Yes

- **Property Value**: `enableAutoDetection`
  - **Description**: Enables or disables the auto detection of the Task Controller address. If enabled then the Task Controller that registers first on the bus with an Address Claimed message is monitored. This property has only impact if passive mode is enabled.
  - **Value Range**: 0..1
  - **Initial Value**: 0
  - **IL must be stopped**: Yes

- **Property Value**: `autoDetectionFunctionInstance`
  - **Description**: If value is not -1 the auto detected Task Controller must have this Function Instance. This property has only impact if passive mode is enabled and property **enableAutoDetection** is set.
  - **Value Range**: 0..31, -1
  - **Initial Value**: -1
  - **IL must be stopped**: Yes
