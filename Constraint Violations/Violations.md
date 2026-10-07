# Task 3 — Identify Constraint Violations

## Violation 1 — F1

**Constraint:**  
`TrainPresent → ¬BarrierOpen`

**Violation Scenario:**
- `TrainPresent = TRUE`
- `BarrierOpen = TRUE`

**What went wrong:**  
The barrier is open while a train is present at the crossing.

**How do we know the constraint is violated?**  
The constraint requires the barrier to be closed whenever a train is present. Since `BarrierOpen = TRUE`, the rule is violated.

---

## Violation 2 — F2

**Constraint:**  
`TrainApproaching → (WarningActive ∧ AlarmActive)`

**Violation Scenario:**
- `TrainApproaching = TRUE`
- `WarningActive = TRUE`
- `AlarmActive = FALSE`

**What went wrong:**  
A train is approaching, but the audible alarm is not active.

**How do we know the constraint is violated?**  
The constraint requires both the warning and alarm to be active when a train is approaching. Since `AlarmActive = FALSE`, the constraint is violated.

---

## Violation 3 — F3

**Constraint:**  
`TrainApproaching → ¬BarrierOpen`

**Violation Scenario:**
- `TrainApproaching = TRUE`
- `BarrierOpen = TRUE`

**What went wrong:**  
The barrier remains open even though a train is approaching.

**How do we know the constraint is violated?**  
The constraint requires the barrier to remain closed when a train is approaching. Since `BarrierOpen = TRUE`, the constraint is violated.

---

## Violation 4 — F4

**Constraint:**  
`BarrierOpen → ClearanceConfirmed`

**Violation Scenario:**
- `BarrierOpen = TRUE`
- `ClearanceConfirmed = FALSE`

**What went wrong:**  
The barrier has opened without confirmation that the train has completely cleared the crossing.

**How do we know the constraint is violated?**  
The constraint requires clearance to be confirmed before the barrier can be open. Since `ClearanceConfirmed = FALSE`, the constraint is violated.

---

## Violation 5 — F5

**Constraint:**  
`¬BarrierOpen → SignalRed`

**Violation Scenario:**
- `BarrierOpen = FALSE`
- `SignalRed = FALSE`

**What went wrong:**  
The barrier is closed, but the traffic signal is not red.

**How do we know the constraint is violated?**  
The constraint requires the signal to be red whenever the barrier is closed. Since `SignalRed = FALSE`, the constraint is violated.

---

## Violation 6 — F6

**Constraint:**  
`SensorFailure → ¬BarrierOpen`

**Violation Scenario:**
- `SensorFailure = TRUE`
- `BarrierOpen = TRUE`

**What went wrong:**  
A sensor has failed, but the barrier is open.

**How do we know the constraint is violated?**  
The constraint requires the barrier to remain closed when a sensor failure occurs. Since `BarrierOpen = TRUE`, the constraint is violated.

---

## Violation 7 — F7

**Constraint:**  
`CommLoss → ¬BarrierOpen`

**Violation Scenario:**
- `CommLoss = TRUE`
- `BarrierOpen = TRUE`

**What went wrong:**  
Communication with the control center is lost, but the barrier is open.

**How do we know the constraint is violated?**  
The constraint requires the barrier to remain closed during communication loss. Since `BarrierOpen = TRUE`, the constraint is violated.

---

## Violation 8 — F8

**Constraint:**  
`(TrainPresent ∨ TrainApproaching) → AlarmActive`

**Violation Scenario:**
- `TrainPresent = TRUE`
- `TrainApproaching = FALSE`
- `AlarmActive = FALSE`

**What went wrong:**  
A train is present at the crossing, but the alarm is not active.

**How do we know the constraint is violated?**  
The condition `(TrainPresent ∨ TrainApproaching)` is TRUE because `TrainPresent = TRUE`. Therefore, `AlarmActive` must be TRUE, but it is FALSE.

---

## Violation 9 — F9

**Constraint:**  
`(TrainApproaching ∧ BarrierFailure) → EmergencyAlert`

**Violation Scenario:**
- `TrainApproaching = TRUE`
- `BarrierFailure = TRUE`
- `EmergencyAlert = FALSE`

**What went wrong:**  
A train is approaching while the barrier has failed, but no emergency alert is generated.

**How do we know the constraint is violated?**  
Both conditions in the left side are TRUE, so `EmergencyAlert` must be TRUE. Since it is FALSE, the constraint is violated.

---

## Violation 10 — F10

**Constraint:**  
`ConflictingReadings → ¬ClearanceConfirmed`

**Violation Scenario:**
- `ConflictingReadings = TRUE`
- `ClearanceConfirmed = TRUE`

**What went wrong:**  
The sensors are giving conflicting readings, but the system has still confirmed that the crossing is clear.

**How do we know the constraint is violated?**  
The constraint requires clearance confirmation to be FALSE when conflicting readings exist. Since `ClearanceConfirmed = TRUE`, the constraint is violated.
