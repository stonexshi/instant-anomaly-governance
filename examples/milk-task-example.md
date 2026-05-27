# Milk Task Example

This example demonstrates the difference between instant anomaly and inherited drift.

---

# Initial Objective

A wife asks her husband to buy milk.

The valid continuity path is:

```text
leave home
→ reach the store
→ locate milk
→ buy milk
→ return home with milk
```

The objective remains stable across continuity slices.

---

# Instant Anomaly

Inside the store, the husband sees many attractive unrelated products.

Examples:

- snacks
- electronics
- discounts
- unrelated shopping opportunities

At this moment, an anomaly appears inside the continuity path.

However, drift has not occurred yet.

The husband still remembers the original objective.

This is an instant anomaly.

---

# Restoration Path

If the husband notices the distraction and returns focus to buying milk:

```text
instant anomaly
→ anomaly detected
→ anomaly not inherited
→ continuity restored
```

The valid continuity path remains active.

No drift occurs.

---

# Drift Path

If the husband forgets the milk and starts buying unrelated items:

```text
instant anomaly
→ anomaly inherited
→ objective displacement
→ continuity redirection
→ drift
```

The anomaly becomes inherited.

The continuity path is now redirected away from the original valid objective.

---

# Governance Meaning

The important distinction is:

The anomaly itself was not the drift.

The inherited anomaly became the drift.

---

# Engineering Insight

This example demonstrates why governance should not only detect downstream drift.

Governance should detect whether a momentary anomaly is about to become inherited continuity.
