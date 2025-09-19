[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/EventProcedures/CAPLfunctionJ1939OnPG.md)

**CAPL Functions** » **J1939** » **Function Overview** » **on pg**

# on pg

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

To react in the CAPL nodes to the receipt of J1939 specific messages (Parameter Groups - PG), the event procedure type `on pg` is provided. It is possible to specify a range of PGNs. In that case, only the PGNs are considered and the addresses are ignored.

**Note**

- A PG with a length of 8 bytes or less can be captured by `on pg` as well as by `on message`. If you are using both event procedures, then both are called for the same event.
- A PG with a length bigger than 8 bytes is transferred via a transport protocol. The composed PG can be captured only by `on pg`. The separate transport protocol message (8 bytes) can be captured by `on pg` as well as by `on message`.

**Example**

- `on pg 0xFEE9`  
  React to parameter group 0xFEE9 ("FuelConsumption");
- `on pg RetarderFluids`  
  React to parameter group "RetarderFluids"
- `on pg 0xFF05-0xFF09`  
  React to parameter group number 0xFF05 to 0xFF09
- `on pg TPCM, TPDT`  
  React to parameter group TPCM and TPDT

To access the control information you would use selectors. Within an `on pg` procedure the key word [this](../../Other/EventProcedures/CAPLfunctionKeywordThis.md) is provided so that you can access data of the message that was just received.

## Multiple 'on pg' in the Same CAPL File

A CAPL program can contain any number of event procedures `on pg`. In this case, however, each parameter group is processed by only one event procedure - the one that describes the corresponding parameter group most precisely. In the following example the parameter group **TMCMxx** is processed by the event procedure `on pg TPCM`, while all other parameter groups are processed by the event procedure `on pg *`:

```plaintext
on pg *
{
  writeEx(-3, 3, "Message with PGN 0x%X received", this.pgn);
}

on pg TPCM
{
  writeEx(-3, 3, "TPCM message received");
}
```

## 'on pg' and 'on message' in the Same CAPL File

A CAPL program can contain both event procedures `on pg` and `on message`. In this case, each parameter group with DLC=8 can be processed by a matching event procedure `on pg` **AND** `on message`. A composed parameter group (i.e. with PGN>8) is only processed by a matching event procedure `on pg`.

## Using 'on pg' in Measurement Setup

By default CAPL programs are impermeable to bus events. This means that if you insert a CAPL node in the evaluation branch of the Measurement Setup, the data flow on the right side of the node will be blocked. You must explicitly program the passing of messages and Error Frames in CAPL nodes in the evaluation branch.

You would write:

```plaintext
on pg *
{
//your code begin
...
...
//your code end

output(this); // pass the pg to the right side of the node
};
```

## Using 'on pg' in Gateways

A gateway is a special control unit, which is used as a connecting element between two or more buses. To realize a CAPL gateway between to J1939 buses you must forward the parameter groups to the other bus.

Because PGs with DLC > 8 are transmitted via a transport protocol there are two possibilities to forward the PGs.

1. Receive the whole PG and retransmit it on the other bus. Exception: Transport protocol messages (TP.CM and TP.DT) are not forwarded.

   **Advantage**
   - Gateway can examine all PGs (even with DLC>8) to decide if they shall be forwarded or modified.

   **Disadvantage**
   - Handling of CMDT transport protocol (message TPCM and TPDT) must be implemented in the gateway node.
   - PG is received after a delay because transport protocol is used twice (once on each bus).

2. Forward all CAN messages to the other bus but do not forward assembled PGs with DLC > 8 bytes.

   **Advantage**
   - Simple CAPL code
   - Less delay

   **Disadvantage**
   - Gateway cannot examine PGs with DLC>8 to decide if they shall be forwarded or modified.

**Note**

Example [J1939Gateway](../../../SampConf/J1939/CANoe/MoreExamples/J1939Gateway/J1939Gateway.md) contains a CAPL gateway that forwards the composed PGs and a second gateway which forwards CAN messages but not PGs with DLC > 8.

**Example**

```plaintext
on pg CAN2.*
// React to receipt of all parameter groups on bus CAN2

on pg CAN2::TPCM, CAN2::TPDT
// React to transport protocol parameter groups on bus CAN2
```

[CAPL Event Procedures](../../../Shared/CAPL/General/EventProceduresOverview.md) • [Message Selectors](../../CAN/CAPLfunctionMessageSelectors.md) • [Define Parameter Groups (J1939)](../CAPLfunctionsJ1939DefinePG.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
