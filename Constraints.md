# Railway Level-Crossing Control System — Constraints

| ID | Constraint (Plain English) | Why It's Necessary |
|----|------------------------------|----------------------|
| C1 | The barrier must not open while a train is present in the crossing. | Opening the barrier would let road traffic enter the crossing while the train is physically occupying it. |
| C2 | Warning lights and audible alarms must be activated before the barrier begins to close. | Gives pedestrians and vehicles advance notice to clear the crossing before it becomes physically blocked. |
| C3 | The barrier must be fully closed before the train reaches the crossing. | If closing lags behind the train's arrival, a vehicle could still be crossing when the train arrives. |
| C4 | The barrier must not open until the system has confirmed the train has completely cleared the crossing. | The rear of the train (or a following train) may still be in or near the crossing even after the front has passed. |
| C5 | The traffic signal must show a stop/red indication whenever the barrier is closed or closing. | Prevents contradictory signals that could confuse drivers into thinking the road is still open. |
| C6 | If a train-detection sensor fails, the system must default the barrier to the closed (safe) state. | Without reliable detection, the system cannot verify the crossing is safe, so it must fail safe rather than assume safety. |
| C7 | If communication with the control center is lost, the system must not automatically open the barrier. | Central oversight may be needed to confirm safety when the local unit's connection to monitoring is unavailable. |
| C8 | The audible alarm must remain active for the entire duration a train is present or approaching. | Continuously warns anyone attempting to bypass the barrier while danger is ongoing. |
| C9 | If the barrier fails to fully close within the required time after a train is detected, the system must trigger an emergency alert. | A barrier that doesn't close in time with an approaching train is a critical hazard requiring immediate human intervention. |
| C10 | The system must not treat the crossing as clear based on a single conflicting or uncorroborated sensor reading. | A faulty sensor could falsely report "clear," causing the barrier to open while a train is actually still present. |
| C11 | The barrier must not open while any unresolved emergency condition (barrier failure, comms loss with unconfirmed train status) exists. | Opening under unresolved uncertainty could expose road traffic to an undetected train. |
| C12 | Every barrier open/close event must be logged with the train-detection status and timestamp at that moment. | Required for safety auditing and incident investigation after any failure or accident. |
