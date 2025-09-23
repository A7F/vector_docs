# J1939AddContainedPG

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
J1939AddContainedPG (message* multiPG, pg* pgToAdd)
```

## Description

Checks whether the **multiPG** (previously initialized with [J1939InitializeMultiPG](CAPLfunctionJ1939InitializeMultiPG.md)) is large enough to accommodate the **pgToAdd** as a **containedPG**. The function should be used in combination. If the DLC of the **multiPG** is too small for this, the necessary adjustment (if possible) is made, so that the smallest possible CAN FD is created.

- The **pgToAdd** is inserted directly after the last existing **containedPG**.
- Payload behind the used **pgToAdd** is covered with the padding service. The length of the padding service can be 0 to 16 bytes.
- If the priority of the **pgToAdd** is higher than the current priority of the **multiPG**, the priority of the **multiPG** is set to the value of the **pgToAdd**.
- Source Address and Destination Address of the **pgToAdd** are ignored.

Parameter Groups using any kind of assurance data (safety or security) must have set the message selectors **TOF** (Type of Service) and **TF** (Trailer Format) to appropriate values according to J1939-22. Possible values can be taken from the table on the help page [Send and Receive Parameter Groups with CAPL](../../../CANoeCANalyzer/J1939/J1939CANfd/1939CANfdPGcaplSendRec.md).

## Parameters

- **multiPG**: This message is a **multiPG** and will accommodate the **pgToAdd** as additional **containedPG**.
- **pgToAdd**: This PG is to be integrated into the **multiPG** as an additional **containedPG**.

## Return Values

Negative value means that the **pgToAdd** could not be integrated:

- **0**: **pgToAdd** is successfully integrated into the **multiPG**
- **-1**: **multiPG** is NULL
- **-3**: Content of multiPg is not compliant with the standard: it is not possible to determine the end of the last C-PG.
- **-6**: **multiPG** is not a CAN FD Frame
- **-7**: **pgToAdd** is NULL
- **-8**: **pgToAdd** is too big to be transmitted using **multiPG**
- **-9**: there is not enough space in the **multiPG** for the **pgToAdd**

## Example

```plaintext
message * multiPG;
pg Msg1 pg1 = {dlc = 13}; // Msg1 is defined in the attached DBC
pg Msg2 pg2 = {dlc = 10}; // Msg2 is defined in the attached DBC
pg Msg3 pg3 = {dlc = 16}; // Msg3 is defined in the attached DBC
pg * pg4 = {dlc = 12}; // Create PG with 8 Bytes of data and 4 bytes assurance data.

// Here a 29 bit CAN FD message is initialized as, multiPG for the source address 0x23,
// destination address 0x45 and prio 5:
J1939InitializeMultiPG(multiPG, 0x5, 0x45, 0x23);

pg1.byte(3) = 0x12; // Init payload of pg1
J1939AddContainedPG(multiPG, pg1); // Add pg1 as a containedPG to the multiPG

pg2.byte(5) = 0x34; // Init payload of pg2
J1939AddContainedPG(multiPG, pg2); // Add pg2 as a containedPG to the multiPG

pg3.byte(7) = 0x56; // Init payload of pg3
J1939AddContainedPG(multiPG, pg3); // Add pg3 as a containedPG to the multiPG

pg4.byte(7) = 0x56; // Init payload of pg4
pg4.tos = 1; // PG with assurance data
pg4.tf = 2;  // 32bit safety assurance data
pg4.qword(0) = some8ByteData; // Can be any data up to 8 bytes
pg4.dword(8) = 0x12345678;    // Safety data
J1939AddContainedPG(multiPG, pg4); // Add pg4 as a containedPG to the multiPG

output(multiPG);
```
