# Engineering Reproduction

Instant Anomaly Governance can be reproduced as a slice-based state transition model.

The purpose is not to detect every abnormal event.

The purpose is to determine whether a momentary anomaly is inherited into the next continuity slice.

---

# Minimal State Fields

Each continuity slice can include:

- slice_id
- previous_slice_id
- active_objective
- valid_state
- current_context
- competing_signal
- anomaly_detected
- inheritance_decision
- next_slice_state
- restoration_action
- drift_status

---

# Governance Question

The key question is not:

Did an anomaly occur?

The key question is:

Was the anomaly inherited into the next valid-state transition?

---

# Possible Outcomes

## No anomaly

The valid state continues normally.

## Anomaly corrected

The anomaly appears inside the current slice but is not inherited.

This produces restoration.

## Anomaly inherited

The anomaly passes into the next slice and begins redirecting continuity.

This produces drift.

## Anomaly blocked

The anomaly is prevented from entering the next slice.

This produces containment.

---

# Minimal Pseudocode

```text
if anomaly_detected == false:
    drift_status = "none"
    inheritance_decision = "valid_state_continues"

if anomaly_detected == true:
    if next_slice_state preserves active_objective:
        drift_status = "restored"
        inheritance_decision = "anomaly_not_inherited"

    if next_slice_state changes active_objective because of competing_signal:
        drift_status = "drift_started"
        inheritance_decision = "anomaly_inherited"

    if next_slice_state is blocked:
        drift_status = "contained"
        inheritance_decision = "inheritance_blocked"
```

---

# Engineering Principle

Drift should not be treated only as a downstream condition.

Drift should be governed at the inheritance boundary where an instant anomaly either becomes lineage or is corrected before continuation.
