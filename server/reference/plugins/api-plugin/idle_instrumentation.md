---
description: >-
  The MYSQL_START_IDLE_WAIT and MYSQL_END_IDLE_WAIT macros, which mark the start
  and end of an idle wait event for the Performance Schema.
---

# Idle Instrumentation

> [`Instrumentation Interface`](instrumentation_interface.md)

## Macros

| Name                                                                     | Description                                                                                                                                                           |
| ------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [`MYSQL_START_IDLE_WAIT`](idle_instrumentation.md#mysql_start_idle_wait) | Instrumentation helper for table io\_waits. This instrumentation marks the start of a wait event. **See also**: [MYSQL\_END\_IDLE\_WAIT](api.md#mysql_end_idle_wait). |
| [`MYSQL_END_IDLE_WAIT`](idle_instrumentation.md#mysql_end_idle_wait)     | Instrumentation helper for idle waits. This instrumentation marks the end of a wait event. **See also**: [MYSQL\_START\_IDLE\_WAIT](api.md#mysql_start_idle_wait).    |

***

### MYSQL\_START\_IDLE\_WAIT

```cpp
#define MYSQL_START_IDLE_WAIT(LOCKER, STATE, LOCKER, STATE) do {} while (0)
```

Defined in psi/mysql\_idle.h:56

Instrumentation helper for table io\_waits. This instrumentation marks the start of a wait event. **See also**: [MYSQL\_END\_IDLE\_WAIT](api.md#mysql_end_idle_wait).

#### Parameters

| Parameter | Type | Description      |
| --------- | ---- | ---------------- |
| `LOCKER`  |      | the locker       |
| `STATE`   |      | the locker state |
| `LOCKER`  |      | the locker       |
| `STATE`   |      | the locker state |

***

### MYSQL\_END\_IDLE\_WAIT

```cpp
#define MYSQL_END_IDLE_WAIT(LOCKER, LOCKER) do {} while (0)
```

Defined in psi/mysql\_idle.h:71

Instrumentation helper for idle waits. This instrumentation marks the end of a wait event. **See also**: [MYSQL\_START\_IDLE\_WAIT](api.md#mysql_start_idle_wait).

#### Parameters

| Parameter | Type | Description |
| --------- | ---- | ----------- |
| `LOCKER`  |      | the locker  |
| `LOCKER`  |      | the locker  |
