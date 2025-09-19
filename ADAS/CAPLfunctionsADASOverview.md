# ADAS CAPL Functions

[Valid for](../../Shared/FeatureAvailability.md):  CANoe DE

## Introduction

**ON THIS PAGE:**

- [General ADAS API](#FMIAPI)
- [Ground Truth API](#GroundTruthAPI)
- [Proj API](#ProjAPI)
- [Scenario API](#ScenarioAPI)
- [Sensor API](#SensorAPI)
- [Transmission Behavior API](#TransmissionAPI)
- [Test Feature Set](#TFS)

## General ADAS API [▲ back](#Shortcuts)

**Functions** | **Short Description**
--- | ---
[ADASActivateFMU](Functions/CAPLfunctionADASActivateFMU.md) | This method is used to activate or deactivate a specified [FMU](../../CANoeCANalyzer/Interfaces/FMIConfig.md) that has been coupled via the [FMI](../../CANoeCANalyzer/Interfaces/FMI.md).
[ADASSetOutputData](Functions/CAPLfunctionADASSetOutputData.md) | This method is used to set a byte array as ADAS output.

## Ground Truth API [▲ back](#Shortcuts)

**Functions** | **Short Description**
--- | ---
[GetGroundTruthObject](Functions/CAPLfunctionGetGroundTruthObject.md) | Gets the name of a special ground truth object as string.
[GetGroundTruthObjects](Functions/CAPLfunctionGetGroundTruthObjects.md) | Gets the unique names of available ground truth objects as string-array.
[GetHostVehicle](Functions/CAPLfunctionGetHostVehicle.md) | Gets the name of the host vehicle for the current ground truth.
[GetOrCreateGroundTruthObject](Functions/CAPLfunctionGetOrCreateGroundTruthObject.md) | Gets a ground truth object. The object is created if it does not exist.
[HasGroundTruthObjects](Functions/CAPLfunctionHasGroundTruthObject.md) | Checks if a special ground truth object exits.
[SetHostVehicle](Functions/CAPLfunctionSetHostVehicle.md) | Sets the host vehicle for the ground truth.

## Proj API [▲ back](#Shortcuts)

**Functions** | **Short Description**
--- | ---
[Proj_Create](Functions/CAPLfunctionProjCreate.md) | Initialize the Proj Access with a Proj String / Proj definition.
[Proj_TransformToGeo](Functions/CAPLfunctionProjTransformToGeo.md) | Transforms an inertial coordinate to a geodetic coordinate.
[Proj_TransformToInertial](Functions/CAPLfunctionProjTransformToInertial.md) | Transforms a geodetic coordinate to an inertial coordinate.

## Scenario API [▲ back](#Shortcuts)

**Functions** | **Short Description**
--- | ---
[SetStationSpeed](Functions/CAPLfunctionSetStationSpeed.md) | Changes the speed of a station.
[StartScenario](Functions/CAPLfunctionStartScenario.md) | Starts the currently loaded scenario.
[StopScenario](Functions/CAPLfunctionStopScenario.md) | Stops a started scenario.
[IsScenarioStarted](Functions/CAPLfunctionIsScenarioStarted.md) | Queries whether the currently loaded scenario has started.
[LoadScenario](Functions/CAPLfunctionLoadScenario.md) | Loads a scenario during a running measurement via a file path.
[GetStationAttributeDouble](Functions/CAPLfunctionGetStationAttributeDouble.md) | Queries an attribute of a scenario as a value of type double at the runtime of the scenario.
[GetStationAttributeInt64](Functions/CAPLfunctionGetStationAttributeInt64.md) | Queries an attribute of a scenario as a value of type int64 at the runtime of the scenario.
[SetStationAttributeDouble](Functions/CAPLfunctionSetStationAttributeDouble.md) | Sets values for attributes based on the attribute name and keypoint (index) in the Scenario Editor timeline.
[SetStationAttributeInt64](Functions/CAPLfunctionSetStationAttributeInt64.md) | Sets values for attributes based on the attribute name and keypoint (index) in the Scenario Editor timeline.
[OnScenarioStateChange](Functions/CAPLfunctionOnScenarioStateChange.md) | This callback is called when the state of the scenario has changed.
[OnStationAttributeTrigger](Functions/CAPLfunctionOnStationAttributeTrigger.md) | This callback is called is called when the value of an attribute of a station has changed.

## Sensor API [▲ back](#Shortcuts)

**Functions** | **Short Description**
--- | ---
[GetDetectedObjects](Functions/CAPLfunctionGetDetectedObjects.md) | This function returns the detected objects of a sensor as a string array.
[GetDetectedObjectsCondtional](Functions/CAPLfunctionGetDetectedObjectsCondtional.md) | This function returns the detected objects of a sensor as a string array.
[GetOrCreateDetectedObject](Functions/CAPLfunctionGetOrCreateDetectedObject.md) | This function gets the name of a detected object of a sensor as a string. If no object with the given trackingId exists, it will be created.
[GetDetectedObjectByTrackingId](Functions/CAPLfunctionGetDetectedObjectByTrackingId.md) | This function returns the name of a detected object of a sensor based on the trackingId as a string.
[GetDetectedObjectByGroundTruthId](Functions/CAPLfunctionGetDetectedObjectByGroundTruthId.md) | This function gets the name of a ground truth object of a sensor based on the ground truth Id as a string. If no object with the given ground truth Id is present, an empty string is returned.
[HasDetectedObject](Functions/CAPLfunctionHasDetectedObject.md) | This function can be used to query whether a detected object of a sensor with a specific tracking Id is present.
[RemoveDetectedObject](Functions/CAPLfunctionRemoveDetectedObject.md) | This function can be used to remove a detected object from a sensor with a specific tracking Id.
[SetDetectedObjectExpirationTime](Functions/CAPLfunctionSetDetectedObjectExpirationTime.md) | Sets a detected object to inactive after a special amount of time (in ms).

## Transmission Behavior API [▲ back](#Shortcuts)

**Functions** | **Short Description**
--- | ---
[BeginUpdate](Functions/CAPLfunctionBeginUpdate.md) | This method is only required if data of a sensor and those of its detected objects are not to be sent directly after assignment.
[OnDetectedObjectUpdate](Functions/CAPLfunctionOnDetectedObjectUpdate.md) | A call of this method for a sensor sends all the data of the sensor and the detected objects that have been marked as completed.
[Reset](Functions/CAPLfunctionReset.md) | Calling this function resets the values of the available sensors to their default values and clears the list of objects detected by them.
[SetDetectedObjectCompleted](Functions/CAPLfunctionSetDetectedObjectCompleted.md) | This method is used to mark that the data of a detected object of a sensor is completely available.
[SetDetectedObjectsCompleted](Functions/CAPLfunctionSetDetectedObjectsCompleted.md) | This method is used to mark that the data of a sensor is completely available.
[Update](Functions/CAPLfunctionUpdate.md) | A call of this method for a sensor sends all data of the sensor and the detected objects that were marked as completed.

## Test Feature Set [▲ back](#Shortcuts)

**Functions** | **Short Description**
--- | ---
[TestGetWaitADASDetectedObject](Functions/CAPLfunctionTestGetWaitADASDetectedObject.md) | Retrieves the name of the Detected Object that triggered the wait function.
[TestWaitForADASDetectedObjectDistance](Functions/CAPLfunctionTestWaitForADASDetectedObjectDistance.md) | Waits for a Detected Object for which the distance is above/below a specified value.
[TestWaitForADASDetectedObjectSpeed](Functions/CAPLfunctionTestWaitForADASDetectedObjectSpeed.md) | Waits for a Detected Object for with a speed above/below a specified value.
[TestWaitForADASDetectedObjectTimeToCollision](Functions/CAPLfunctionTestWaitForADASDetectedObjectTimeToCollision.md) | Waits for the occurrence of the first Detected Object matching the Time To Collision (TTC) conditions passed as arguments.
[TestWaitForADASGroundTruthObjectDistance](Functions/CAPLfunctionTestWaitForADASGroundTruthObjectDistance.md) | Waits for the occurrence of the first Moving Object matching the distance conditions passed as arguments.
[TestWaitForADASGroundTruthObjectInLane](Functions/CAPLfunctionTestWaitForADASGroundTruthObjectInLane.md) | Waits for a Moving Object which is completely in the given lane.
[TestWaitForADASGroundTruthObjectInSameLane](Functions/CAPLfunctionTestWaitForADASGroundTruthObjectInSameLane.md) | Waits for a Moving Object which is completely in the lane of the ego vehicle.
[TestWaitForADASGroundTruthObjectLaneSwitch](Functions/CAPLfunctionTestWaitForADASGroundTruthObjectLaneSwitch.md) | Waits for a Moving Object which switches lane.
[TestWaitForADASGroundTruthObjectSpeed](Functions/CAPLfunctionTestWaitForADASGroundTruthObjectSpeed.md) | Waits for the occurrence of the first Moving Object matching the speed conditions passed as arguments.
[TestWaitForADASGroundTruthObjectTimeToCollision](Functions/CAPLfunctionTestWaitForADASGroundTruthObjectTimeToCollision.md) | Waits for the occurrence of the first Moving Object matching the Time To Collision (TTC) conditions passed as arguments.

## Test Service Library Checks [▲ back](#Shortcuts)

**Functions** | **Short Description**
--- | ---
[ChkCreate_ADASDetectedObjectsDistanceViolation, ChkStart_ADASDetectedObjectsDistanceViolation](../Test/Functions/CAPLfunctionChkCreateADASDetectedObjectsDistanceViolation.md) | Observes the distance of the Detected Moving Objects.
[ChkCreate_ADASDetectedObjectsHaveMatchingGroundTruthObjectsViolation, ChkStart_ADASDetectedObjectsHaveMatchingGroundTruthObjectsViolation](../Test/Functions/CAPLfunctionChkCreateADASDetectedObjectsHaveMatchingGroundTruthObjectsViolation.md) | Observes if Detected Moving Objects have matching Moving Objects.
[ChkCreate_ADASDetectedObjectsSpeedViolation, ChkStart_ADASDetectedObjectsSpeedViolation](../Test/Functions/CAPLfunctionChkCreateADASDetectedObjectsSpeedViolation.md) | Observes the relative speed of the Detected Moving Objects.
[ChkCreate_ADASDetectedObjectsTimeToCollisionViolation, ChkStart_ADASDetectedObjectsTimeToCollisionViolation](../Test/Functions/CAPLfunctionChkCreateADASDetectedObjectsTimeToCollisionViolation.md) | Observes the Time To Collision (TTC) to the Detected Moving Objects.
[ChkCreate_ADASGroundTruthObjectsDistanceViolation, ChkStart_ADASGroundTruthObjectsDistanceViolation](../Test/Functions/CAPLfunctionChkCreateADASGroundTruthObjectsDistanceViolation.md) | Observes the distance of the Moving Objects to the EgoVehicle.
[chkCreate_ADASEgoVehicleLaneViolation, chkStart_ADASEgoVehicleLaneViolation](../Test/Functions/CAPLfunctionChkCreateADASEgoVehicleLaneViolation.md) | Observes the lane of the EgoVehicle.
[ChkCreate_ADASGroundTruthObjectsHaveMatchingDetectedObjectsViolation, ChkStart_ADASGroundTruthObjectsHaveMatchingDetectedObjectsViolation](../Test/Functions/CAPLfunctionChkCreateADASGroundTruthObjectsHaveMatchingDetectedObjectsViolation.md) | Observes if Moving Objects have matching Detected Moving Objects.
[ChkCreate_ADASGroundTruthObjectsSpeedViolation, chkStart_ADASGroundTruthObjectsSpeedViolation](../Test/Functions/CAPLfunctionChkCreateADASGroundTruthObjectsSpeedViolation.md) | Observes the relative speed of the Moving Objects to the EgoVehicle.
[ChkCreate_ADASGroundTruthObjectsTimeToCollisionViolation, ChkStart_ADASGroundTruthObjectsTimeToCollisionViolation](../Test/Functions/CAPLfunctionChkCreateADASGroundTruthObjectsTimeToCollisionViolation.md) | Observes the Time To Collision (TTC) between Moving Objects and the EgoVehicle.

[ADAS](../../CANoeCANalyzer/ADAS/ADAS.md)
