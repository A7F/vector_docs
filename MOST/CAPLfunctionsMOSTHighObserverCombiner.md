[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/CAPLfunctionsMOSTHighObserverCombiner.md)

[CAPL Functions](../CAPLfunctions.md) » [MOST](CAPLfunctionsMOSTOverview.md) » High Observer and Combiner

# MOST: High Observer and Combiner

[Valid for](../../Shared/FeatureAvailability.md):  CANoe DE

The MOST High Observer observes all messages belonging to the MOST High Protocol (MHP) and uses the Combiner to combine them. The CAPL event procedures described here allow the reaction to events of the observer.

- To analyze of data
- To filter the events
- To save the reference data in files

## Event Procedures:

- [OnMostMHPBlock](EventProcedures/CAPLfunctionOnMOSTMHPBlock.md)
- [OnMostMHPPacket](EventProcedures/CAPLfunctionOnMOSTMHPPacket.md)
- [OnMostMHPError](EventProcedures/CAPLfunctionOnMOSTMHPError.md)
- [OnMostMHPConnection](EventProcedures/CAPLfunctionOnMOSTMHPConnection.md)

**Note**  
These event procedures and their functions are only available for CAPL programs in the **Measurement Setup**.  
For simulation of a MOST High connection sender and receiver in CAPL the MOST High DLL can be used. The DLL is located in the Exec32 folder of the MOST High Demos.

[MOST High Protocol: Simulation of Sender and Receiver](../../CANoeCANalyzer/MOST/MOSTSimulationApplicationSocketLocalFBlockList.md)

•  Technical References are only available in English

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
