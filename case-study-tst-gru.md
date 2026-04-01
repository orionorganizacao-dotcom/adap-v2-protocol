# A-DAP v2 — Case Study  
## Retroactive Application to GRU Digital Workflow (TST)

---

## 1. Context

The adoption of digital payment validation systems within the Brazilian judicial system introduces automated decision layers with direct legal and financial impact.

In the context of the 0, GRU Digital workflows involve:

- Payment validation  
- Process linkage  
- Execution gating (block/unblock actions)  

These operations constitute **algorithmic decisions**, even when not labeled as such.

---

## 2. Problem Statement

Current auditability depends on:

- Internal logs  
- Database records  
- Institutional reconstruction  

This creates a structural limitation:

> The system that decides is the same system that explains.

This is not independent auditability.

---

## 3. Example Decision Scenario

**Event:**
Payment not recognized → process blocked

---

## 4. A-DAP Representation (Retroactive)

```json
{
  "protocol_version": "A-DAP v2",
  "decision_id": "tst_gru_2026_00123",
  "timestamp_utc": "2026-03-30T14:22:10Z",

  "actor_ref": "process_0004567-89.2026.5.00.0000",

  "input_snapshot_hash": "sha256:abc123...",

  "system": {
    "name": "GRU_Digital_Module",
    "version": "v3.2.1"
  },

  "policy": {
    "rule": "payment_validation_rule_set",
    "version": "2026.03",
    "ruleset_hash": "sha256:def456..."
  },

  "decision": {
    "output": "PAYMENT_NOT_CONFIRMED",
    "action": "PROCESS_BLOCKED",
    "confidence": 1.0
  }
}
