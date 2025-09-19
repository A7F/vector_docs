# Car2x Test Service Library

[Valid for](../../Shared/FeatureAvailability.md):  CANoe DE

The Car2x Test Service Library contains Wait Functions for Car2x messages and for Tokens in these messages.

- **[C2xTestGetWaitForMessage](Functions/CAPLfunctionC2xTestGetWaitForMessage.md)**: Retrieves the Car2x message that has led to the resume of the last wait statement.
- **[C2xTestJoinMessage](Functions/CAPLfunctionC2xTestJoinMessage.md)**: Joins a Car2x message to the current set of waiting events.
- **[C2xTestJoinSignalInRange](Functions/CAPLfunctionC2xTestJoinSignalInRange.md)**: Joins a Car2X message which has a signal that is inside or equals the given limits to the current set of waiting events.
- **[C2xTestJoinSignalMatch](Functions/CAPLfunctionC2xTestJoinSignalMatch.md)**: Joins a Car2X message which has a signal that matches the given value to the current set of waiting events.
- **[C2xTestWaitForMessage](Functions/CAPLfunctionC2xTestWaitForMessage.md)**: Waits for a Car2x message.
- **[C2xTestWaitForSignalInRange](Functions/CAPLfunctionC2xTestWaitForSignalInRange.md)**: Waits for a Car2X message which has a signal that is inside or equals the given limits.
- **[C2xTestWaitForSignalMatch](Functions/CAPLfunctionC2xTestWaitForSignalMatch.md)**: Waits for a Car2X message which has a signal that matches the given value.
