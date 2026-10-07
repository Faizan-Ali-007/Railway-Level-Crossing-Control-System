# Railway Level-Crossing Control System — Formalized Constraints

Propositions used: TrainPresent, TrainApproaching, ClearanceConfirmed, BarrierOpen, WarningActive, AlarmActive, SignalRed, SensorFailure, CommLoss, BarrierFailure, EmergencyAlert, ConflictingReadings

| ID | Related Constraint | Formal Expression |
|----|----------------------|----------------------|
| F1 | C1 | TrainPresent → ¬BarrierOpen |
| F2 | C2 | TrainApproaching → (WarningActive ∧ AlarmActive) |
| F3 | C3 | TrainApproaching → ¬BarrierOpen |
| F4 | C4 | BarrierOpen → ClearanceConfirmed |
| F5 | C5 | ¬BarrierOpen → SignalRed |
| F6 | C6 | SensorFailure → ¬BarrierOpen |
| F7 | C7 | CommLoss → ¬BarrierOpen |
| F8 | C8 | (TrainPresent ∨ TrainApproaching) → AlarmActive |
| F9 | C9 | (TrainApproaching ∧ BarrierFailure) → EmergencyAlert |
| F10 | C10 | ConflictingReadings → ¬ClearanceConfirmed |
