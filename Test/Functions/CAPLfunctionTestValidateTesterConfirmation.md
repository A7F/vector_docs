# TestValidateTesterConfirmation

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```c
long TestValidateTesterConfirmation(char question[], char heading[], long passedButton); // form 1
long TestValidateTesterConfirmation(char question[], char heading[], long passedButton, long timeoutResult, char resourceFile[], char resourceCaption[], dword timeout); // form 2
```

This form is deprecated since it does not support the new 5-value-based verdict concept; you should use form (3) instead.

```c
long TestValidateTesterConfirmation(char question[], char heading[], long yesResult, long noResult, long unclearResult, long timeoutResult, char resourceFile[], char resourceCaption[], dword timeout); // form 3
```

## Description

Creates a popup window that presents the given string to the tester. The tester can acknowledge the window with **Yes**, **No** or **Unclear** (form (3)).

The window contains a field for entering a comment that is automatically adopted into the test report.

The result of the command is reported.

The function is not allowed in [standalone mode](../../../CANoeCANalyzer/RTSetup/StandaloneMode/StandaloneModeConcept.md). Errors are reported as **error in test system** or **fail** in case of 2-valued verdict concept.

## Parameters

- **question**: Text in the message box.
- **heading**: Heading of the message box.
- **passedButton**: Defines the button that the user must press to terminate the command with passed. Can be set to the following values:
  - 0 = no
  - 1 = yes
- **resourceFile**: Picture that is shown in the message box. Supported file types are:
  - BMP
  - JPG
  - PNG
  - GIF
- **resourceCaption**: A description for the resource.
- **yesResult, noResult, unclearResult, timeoutResult**: Defines the behavior of the command if the user clicked the [Yes], [No] or [Unclear] button, or if the user did not answer the dialog within the specified timeout; possible values:
  - 0|pass
  - 1|fail
  - 3|inconclusive
  - 4|error in test system
  - -1| only for **unclearResult** parameter: hides the [Unclear] button.
- **timeoutresult**: Defines the behavior of the command if the user did not answer the dialog within the specified timeout; possible values:
  - 1|pass
  - 0|fail
- **timeout**: Maximum time that should be waited [ms]. (Transmission of 0: no timeout controlling, function will wait until the dialog is confirmed).

## Return Values

- **0**: Timeout occurred.
- **1**: The tester clicked Yes.
- **2**: The tester clicked No.
- **3**: The tester clicked Unclear.
- **-1**: General error, e.g. due to a call outside of a test sequence.
- **-2**: Constraint occurred.

## Example

—
