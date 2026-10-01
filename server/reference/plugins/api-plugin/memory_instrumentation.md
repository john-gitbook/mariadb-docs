---
description: >-
  The mysql_memory_register macro, which registers memory instruments with the
  Performance Schema.
---

# Memory Instrumentation

> [`Instrumentation Interface`](instrumentation_interface.md)

## Macros

| Name                                                                       | Description          |
| -------------------------------------------------------------------------- | -------------------- |
| [`mysql_memory_register`](memory_instrumentation.md#mysql_memory_register) | Memory registration. |

***

### mysql\_memory\_register

```cpp
#define mysql_memory_register(P1, P2, P3, P1, P2, P3) inline_mysql_memory_register(P1, P2, P3)
```

Defined in psi/mysql\_memory.h:59

Memory registration.

## Functions

| Return | Name                                                                                                       | Description |
| ------ | ---------------------------------------------------------------------------------------------------------- | ----------- |
| `void` | [`inline_mysql_memory_register`](memory_instrumentation.md#inline_mysql_memory_register) `static` `inline` |             |

***

### inline\_mysql\_memory\_register

`static` `inline`

```cpp
static inline void inline_mysql_memory_register(const char *category __attribute__, void *info __attribute__, int count __attribute__, const char *category __attribute__, void *info __attribute__, int count __attribute__)
```

Defined in psi/mysql\_memory.h:62
