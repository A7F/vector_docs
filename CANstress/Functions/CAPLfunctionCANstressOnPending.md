# CANstressOnPending

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long CANstressOnPending( char fnctCallback[] );
```

## Description

Registers a CAPL function as callback that is called if CANstress is switched into the state **Pending**.

## Parameters

- **fnctCallback**: Name of the function that should be used as callback.

  **Note**
  - The callback functions must correspond to the following syntax: `long FunctionName( dword );`
  - Should the CAPL function used as callback not longer be called when CANstress changes into the **Pending** condition, an empty string must be passed as parameter to CANstressOnPending.

  ```plaintext
  // delete or switch off present callback
  CANstressOnPending( " " );
  ```

## Return Values

- **0**: On successful call.

## Example

—
