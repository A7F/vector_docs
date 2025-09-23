[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/CAPLfunctionsJ1939DefinePG.md)

## Define Parameter Groups

[CAPL Functions](../CAPLfunctions.md) » [J1939](CAPLfunctionsJ1939StartPage.md) » Define Parameter Groups

**Valid for**:  CANoe DE • CANoe4SW DE

The key word **pg** is used to define **parameter group** object. This object can be used in two ways:

- To be sent directly with the `output` function.
- As a data container to pass data to a function or to receive data from a function.

### Variants

There are several ways to create a **pg** object:

```plaintext
  // Variant 1
  pg * myPG;

  // Variant 2
  pg 0x100 myPG_PDU1;
  pg 0xFA02 myPG_PDU2;

  // Variant 3
  pg RQST myPGFromDBC;
```

#### Variant 1

In this way you create a **pg** object where all bits of the CAN ID are set to **1** and DLC is set to **0**.

This variant is useful if you want to use the **pg** object as a data container which should receive data of a message. However, payload of this message must not be bigger than 12 byte. If the payload is bigger than 12 bytes then you have to create a sufficiently large **pg** object right away (see chapter **[Define the Size of a Parameter Group](#DefineSize)**).

It is also possible to send the created **pg** object from CAPL directly. All parts of the CAN ID must be set here (in CAPL the CAN ID is represented as a 32 bit value). In particular, the three most significant bits of the first most significant byte of the CAN ID must be set to **100b** (see also the description of the attribute selector **Characteristics**).

#### Variant 2

This is how you create a **pg** object with a specific PGN. Other components of the CAN ID are set to the following values (referring to the example above):

- **PGN**: 0x100 (as defined), 0xxFA02 (as defined)
- **SA**: 0xFE, 0xFE
- **DA / PS**: 0xFE, 0x02 (part of PGN)
- **PF**: 0x1 (part of PGN), 0xFA (part of PGN)
- **DA_TP**: 0xFE, 0xFF
- **Prio**: 0, 0
- **Characteristics**: 0x80, 0x80

This variant is useful if you want to send the **pg** object. However, you must first define DLC, whereby the upper limit of 12 bytes remains the same here.

#### Variant 3

This is how you create a **pg** object that is equivalent to the object with the same name from the database. Not only the components of the CAN ID are taken over also DLC and other message attributes correspond to the values from the database. You can also access the individual signals directly in both read and write mode:

```plaintext
on pg RQST
{
  //declare pg
  pg ACKM myACKM;
  //define SA and DA
  myACKM.SA = 0x1; // my address
  myACKM.DA = this.SA; // address of the request's originator
  //define single signals
  myACKM.ControlByte = 0; //ACK
  myACKM.AddressAcknowledged = this.SA;
  myACKM.ParameterGroupNumber = this.ParameterGroupNumber;
  //send acknowledge
  output(myACKM);
}
```

### Define the Size of a Parameter Group

For **pg** objects created using **variant 1** or **variant 2**, the maximum payload size (DLC) is limited to 12 bytes. For **variant 3**, the maximum payload size is also limited to the size defined in the database for the respective message. However, sometimes it is necessary to process larger messages in a CAPL program. This is also possible, you only have to specify the maximum required message payload size in the line where the **pg** object is created:

```plaintext
  // Variant 1
  pg * myPG = {DLC = 31};

  // Variant 2
  pg 0x100 myPG_PDU1 = {DLC = 32};
  pg 0xFA02 myPG_PDU2 = {DLC = 33};

  // Variant 3
  pg RQST myPGFromDBC = {DLC = 34};
```

DLC can be changed several times later with one restriction: DLC must never be greater than the value defined when the **pg** object was created.

The same syntax can be used to define additional attribute selectors, e.g:

```plaintext
  pg 0x100 pg_tc1 = {SA = 0x34, DA = 0x24};
  output(pg_tc1);
```

In this case you would define and send the parameter group with **PGN = 0x100 (TC1)** from the node with address **0x34** to node with address **0x24**.

### J1939 CAN FD

For sending a Parameter Group with CAN FD additional selectors can be used, namely **FDF**, **TM**, **ADT**, and **ADS**. They define the transmission method (Multi-PG or FD.TP) and the type and size of the assurance data.

```plaintext
  // send a PG as Contained PG
  pg 0x0 tsc1;
  tsc1.SA = 1;
  tsc1.DA = 2;
  tsc1.DLC = 8;
  tsc1.FDF = 1;
  tsc1.TM = 1;
  tsc1.ADT = 0;
  tsc1.ADS = -1;
  output(tsc1);
```

[Parameter Group Selectors](CAPLfunctionJ1939GroupSelectors.md)
