[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/ObjectPoolXMLElements.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » **Object Pool XML Elements**

# Object Pool XML Elements

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

The object pool component supports the loading and saving of binary IOP files. The content of the file is identical to the data sent to the Virtual Terminal with the Object Pool Transfer message.

Furthermore, object pool files can also be processed in a proprietary XML format (*.iopx) defined by Vector. The XML format allows easy editing of the object pool, e.g. to test a changed display in the Virtual Terminal. With the sample configuration [Object Pool Checker](../../../SampConf/ISO11783/CANoe/MoreExamples/ObjectPoolChecker/ObjectPoolChecker_CN.md) an IOP file can be easily converted into an IOPX file (and vice versa).

In the following the XML elements and the XML attributes of the individual objects are described. Unless otherwise specified, the attributes are of type **xs:integer**.

- **Working Set**
  - XML Element: `<workingSet>`
  - XML Attribute: `id`, `backgroundColor`, `selectable`, `activeMask`

- **Data Mask**
  - XML Element: `<dataMask>`
  - XML Attribute: `id`, `backgroundColor`, `softKeyMask`

- **Alarm Mask**
  - XML Element: `<alarmMask>`
  - XML Attribute: `id`, `backgroundColor`, `softKeyMask`, `priority`, `signal`

- **Container**
  - XML Attribute: `id`, `width`, `height`, `hidden`

- **Window Mask**
  - XML Attribute: `id`, `width`, `height`, `windowType`, `backgroundColor`, `options`, `name`, `windowTitle`, `windowIcon`

- **Soft Key Mask**
  - XML Element: `<softkeyMask>`
  - XML Attribute: `id`, `backgroundColor`

- **Key**
  - XML Element: `<key>`
  - XML Attribute: `id`, `backgroundColor`, `keyCode`

- **Button**
  - XML Element: `<button>`
  - XML Attribute: `iId`, `width`, `height`, `backgroundColor`, `borderColor`, `keycode`, `options`

- **Key Group**
  - XML Element: `<keyGroup>`
  - XML Attribute: `id`, `options`, `name`, `keyGroupIcon`

- **Input Boolean**
  - XML Element: `<inputBool>`
  - XML Attribute: `id`, `backgroundColor`, `width`, `foregroundColor`, `variable`, `value`, `enabled`

- **Input String**
  - XML Element: `<inputString>`
  - XML Attribute: `id`, `width`, `height`, `backgroundColor`, `font`, `input`, `options`, `variable`, `justification`, `value (xs:string)`, `enabled`

- **Input Number**
  - XML Element: `<inputNumber>`
  - XML Attribute: `id`, `width`, `height`, `backgroundColor`, `font`, `options`, `variable`, `min`, `max`, `offset`, `scale (xs:decimal)`, `nrOfDecimals`, `format`, `justification`, `value`, `options2`

- **Input List**
  - XML Element: `<inputList>`
  - XML Attribute: `id`, `width`, `height`, `variable`, `value`, `options`

- **Output String**
  - XML Element: `<outputString>`
  - XML Attribute: `id`, `width`, `height`, `backgroundColor`, `font`, `options`, `variable`, `justification`, `value (xs:string)`

- **Output Number**
  - XML Element: `<outputNumber>`
  - XML Attribute: `id`, `width`, `height`, `backgroundColor`, `font`, `options`, `variable`, `offset`, `scale`, `nrOfDecimales`, `format`, `justification`, `value`

- **Output List**
  - XML Element: `<outputList>`
  - XML Attribute: `id`, `width`, `height`, `variable`, `value`

- **Output Line**
  - XML Element: `<line>`
  - XML Attribute: `id`, `line`, `width`, `height`, `direction`

- **Output Rectangle**
  - XML Element: `<rectangle>`
  - XML Attribute: `id`, `line`, `width`, `height`, `suppression`, `fill`

- **Output Ellipse**
  - XML Element: `<ellipse>`
  - XML Attribute: `id`, `line`, `width`, `height`, `type`, `startAngle`, `endAngle`, `fill`

- **Output Polygon**
  - XML Element: `<polygon>`
  - XML Attribute: `id`, `width`, `height`, `line`, `fill`, `type`

- **Output Meter**
  - XML Element: `<meter>`
  - XML Attribute: `id`, `width`, `needleColor`, `borderColor`, `tickColor`, `options`, `nrOfTicks`, `startAngle`, `endAngle`, `min`, `max`, `variable`, `value`

- **Output Linear Bar Graph**
  - XML Element: `<lineBarGraph>`
  - XML Attribute: `id`, `width`, `height`, `color`, `targetColor`, `options`, `nrOfTicks`, `min`, `max`, `variable`, `targetRef`, `targetValue`, `value`

- **Output Arched Bar Graph**
  - XML Element: `<archedBarGraph>`
  - XML Attribute: `id`, `width`, `height`, `color`, `targetColor`, `options`, `startAngle`, `endAngle`, `barWidth`, `min`, `max`, `variable`, `targetRef`, `targetValue`, `value`

- **Graphics Context**
  - XML Element: `<graphicsContext>`
  - XML Attribute: `id`, `viewportWidth`, `viewportHeight`, `viewportX`, `viewportY`, `canvasWidth`, `canvasHeight`, `viewportZoom (xs:decimal)`, `cursorX`, `cursorY`, `foregroundColor`, `backgroundColor`, `font`, `line`, `fill`, `format`, `options`, `transparentColor`

- **Animation**
  - XML Element: `<animation>`
  - XML Attribute: `id`, `width`, `height`, `refreshInterval`, `value`, `enabled`, `firstChildIndex`, `lastChildIndex`, `defaultChildIndex`, `options`

- **Picture Graphic**
  - XML Element: `<picture>`
  - XML Attribute: `id`, `width`, `options`, `transparentColor`, `actualWidth`, `actualHeight`, `format`

- **Graphic Data**
  - XML Element: `<graphicData>`
  - XML Attribute: `id`, `format`

- **Scaled Graphic**
  - XML Element: `<scaledGraphic>`
  - XML Attribute: `id`, `width`, `height`, `scaleType`, `options`, `value`

- **Number Variable**
  - XML Element: `<numberVariable>`
  - XML Attribute: `id`, `value`

- **String Variable**
  - XML Element: `<stringVariable>`
  - XML Attribute: `id`, `value (xs:string)`

- **Font Attributes**
  - XML Element: `<fontAttribute>`
  - XML Attribute: `id`, `color`, `size`, `type`, `style`

- **Line Attributes**
  - XML Element: `<lineAttribute>`
  - XML Attribute: `id`, `color`, `width`, `art`

- **Fill Attributes**
  - XML Element: `<fillAttribute>`
  - XML Attribute: `id`, `type`, `color`, `pattern`

- **Input Attributes**
  - XML Element: `inputAttribute`
  - XML Attribute: `id`, `type`, `validation (xs:string)`

- **Extended Input Attributes**
  - XML Element: `<inputAttributeEx>`
  - XML Attribute: `id`, `type`

- **Colour Map**
  - XML Element: `<colorMap>`

- **Object Label Reference List**
  - XML Element: `<labelRefList>`
  - XML Attribute: `id`

- **Colour Palette**
  - XML Element: `<colorPalette>`
  - XML Attribute: `id`, `options`

- **Working Set Special Controls**
  - XML Element: `<workingSetSpecialControls>`
  - XML Attribute: `id`, `numOfBytesToFollow`, `colorMapId`, `colorPaletteId`

- **External Object Definition**
  - XML Element: `<externalObjectDefinition>`
  - XML Attribute: `id`, `options`, `name0 (untere 4 Bytes des NAME)`, `name1(obere 4 Bytes des NAME)`

- **External Reference NAME**
  - XML Element: `<externalReferenceName>`
  - XML Attribute: `id`, `options`, `name0 (untere 4 Bytes des NAME)`, `name1 (obere 4 Bytes des NAME)`

- **External Object Pointer**
  - XML Element: `<externalObjectPointer>`
  - XML Attribute: `id`, `defaultObjectID`, `externalRefNameID`, `externalObjectID`

- **Macro**
  - XML Element: `<macro>`
  - XML Attribute: `id`

- **Auxiliary Function Type 1**
  - XML Element: `<auxiliaryFunctionType1>`
  - XML Attribute: `id`, `backgroundColor`, `functionType`

- **Auxiliary Input Type 1**
  - XML Element: `<auxiliaryInputType1>`
  - XML Attribute: `id`, `backgroundColor`, `functionType`, `inputID`

- **Auxiliary Function Type 2**
  - XML Element: `<auxiliaryFunctionType2>`
  - XML Attribute: `id`, `backgroundColor`, `functionType`

- **Auxiliary Input Type 2**
  - XML Element: `<auxiliaryInputType2>`
  - XML Attribute: `id`, `backgroundColor`, `functionType`

- **Auxiliary Control Designator Type 2 Object Pointer**
  - XML Element: `<auxiliaryCtrlDesignatorPointer>`
  - XML Attribute: `id`, `type`, `objectID`

All objects that can contain macros are defined by the subelement **`<macro>`**.

- **Object that can contain macros**
  - XML Subelement: `<macro>`
  - XML Attribute: `macroID`, `eventID`

To define an extended macro, two `<macro>` elements are used, where the **eventID** attribute of the first element must be 255. The true event ID is defined in the second element. The **macroID** attribute of the first element contains the low byte of the macro ID. The **macroID** attribute of the second element contains the high byte.

**Example**

```xml
<scaledGraphic id="9000" width="20" height="30" scaleType="0" options="0" value="7000">
  <!-- extended macro (macro id 30002, event id 9 (on change attribute) -->
  <macro macroID="50" eventID="255"/>
  <macro macroID="117" eventID="9"/>
</scaledGraphic>
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
