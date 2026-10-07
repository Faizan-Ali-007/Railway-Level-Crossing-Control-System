# Task 3 — Identify Constraint Violations

| **ID** | **Constraint** | **Violation Scenario** | **What Went Wrong?** | **How Do We Know It Is Violated?** |
|---|---|---|---|---|
| **F1** | `TrainPresent → ¬BarrierOpen` | `TrainPresent = TRUE`<br>`BarrierOpen = TRUE` | The barrier is open while a train is present at the crossing. | The constraint requires the barrier to be closed whenever a train is present. |
| **F2** | `TrainApproaching → (WarningActive ∧ AlarmActive)` | `TrainApproaching = TRUE`<br>`WarningActive = TRUE`<br>`AlarmActive = FALSE` | A train is approaching, but the audible alarm is not active. | Both warning and alarm must be active when a train is approaching. |
| **F3** | `TrainApproaching → ¬BarrierOpen` | `TrainApproaching = TRUE`<br>`BarrierOpen = TRUE` | The barrier is open even though a train is approaching. | The constraint requires the barrier to remain closed when a train is approaching. |
| **F4** | `BarrierOpen → ClearanceConfirmed` | `BarrierOpen = TRUE`<br>`ClearanceConfirmed = FALSE` | The barrier has opened without confirmation that the train has cleared the crossing. | The barrier can only be open when clearance has been confirmed. |
| **F5** | `¬BarrierOpen → SignalRed` | `BarrierOpen = FALSE`<br>`SignalRed = FALSE` | The barrier is closed, but the traffic signal is not red. | The constraint requires the signal to be red whenever the barrier is closed. |
| **F6** | `SensorFailure → ¬BarrierOpen` | `SensorFailure = TRUE`<br>`BarrierOpen = TRUE` | A sensor has failed, but the barrier is open. | The constraint requires the barrier to remain closed when a sensor failure occurs. |
| **F7** | `CommLoss → ¬BarrierOpen` | `CommLoss = TRUE`<br>`BarrierOpen = TRUE` | Communication with the control center is lost, but the barrier is open. | The constraint requires the barrier to remain closed during communication loss. |
| **F8** | `(TrainPresent ∨ TrainApproaching) → AlarmActive` | `TrainPresent = TRUE`<br>`TrainApproaching = FALSE`<br>`AlarmActive = FALSE` | A train is present at the crossing, but the alarm is not active. | The left side is TRUE, so `AlarmActive` must be TRUE. |
| **F9** | `(TrainApproaching ∧ BarrierFailure) → EmergencyAlert` | `TrainApproaching = TRUE`<br>`BarrierFailure = TRUE`<br>`EmergencyAlert = FALSE` | A train is approaching while the barrier has failed, but no emergency alert is generated. | Both conditions are TRUE, so `EmergencyAlert` must be TRUE. |
| **F10** | `ConflictingReadings → ¬ClearanceConfirmed` | `ConflictingReadings = TRUE`<br>`ClearanceConfirmed = TRUE` | Sensors give conflicting readings, but the system confirms that the crossing is clear. | The constraint requires `ClearanceConfirmed` to be FALSE when readings conflict. |
