# Scheduling an ARINC Word

[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/A429/CAPLfunctionsA429Scheduling.md)

**CAPL Functions** » **A429** » Scheduling an ARINC Word

**Valid for**: CANoe DE • CANoe4SW DE

An ARINC word may be transmitted either on request or cyclically (supported by the hardware scheduler). The transmission behavior is controlled via the [selectors](CAPLfunctionsA429Selectors.md) **TxCtrl** and **TxCycle**. The transmission of an ARINC word is initiated with the function [output](Functions/CAPLfunctionA429output.md) or [a429Transmit](Functions/CAPLfunctionA429Transmit.md). If a real hardware is used the ARINC word is transferred to the hardware with this call.

**Example: Schedule the Cyclic Transmission of an ARINC Word**

```plaintext
variables {
  a429Word LBL_103 myWord = {msgChannel = 1};
}

on start {
  myWord.SSM_103 = 3;
  output (myWord); // start scheduling
}

on key '+' {
  myWord.SelAirspeed.phys += 22.5;
  output(myWord); // update
}

on key '-' {
  myWord.SelAirspeed.phys -= 22.5;
  output(myWord); // update
}
```

If an ARINC word is initialized based on a message in a database, the cycle time is taken from the database attribute [A429Cycle](../../CANoeCANalyzer/A429/basicsA429/A429dbSupport.md). For every ARINC word you may also modify the minimum distance to the previous sent ARINC word via the [selector](CAPLfunctionsA429Selectors.md) **gap**.

**Example: Transmit ARINC Words on Request**

```plaintext
variables {
  a429Word LBL_103 myWord = {msgChannel = 2};
  msTimer myTimer; // major schedule
}

on start {
  a429SetScheduleTx (myWord, 0); // erase cycle time
  myWord.SSM_103 = 3;
  setTimer (myTimer, 10); // fire up timer
}

on timer myTimer {
  int i;
  setTimer (myTimer, 10); // rearm timer
  // send 3 ARINC words with 40, 80 and 120 us gap
  for (i = 0; i < 3; i++)
  {
    a429SetGap (myWord, ((i * 40000) + 40000));
    myWord.SelAirspeed.phys += 22.5;
    output(myWord); // update
  }
}
```

If you want to schedule ARINC words with just the minimum allowed gap phase in between, you have to use the function [a429Transmit](Functions/CAPLfunctionA429Transmit.md).

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)