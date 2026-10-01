---
description: >-
  The mysql_mdl_create, mysql_mdl_set_status, and mysql_mdl_destroy macros,
  which instrument metadata locks for the Performance Schema.
---

# Metadata Instrumentation

> [`Instrumentation Interface`](instrumentation_interface.md)

## Macros

| Name                                                                       | Description                             |
| -------------------------------------------------------------------------- | --------------------------------------- |
| [`mysql_mdl_create`](metadata_instrumentation.md#mysql_mdl_create)         | Instrumented metadata lock creation.    |
| [`mysql_mdl_set_status`](metadata_instrumentation.md#mysql_mdl_set_status) |                                         |
| [`mysql_mdl_destroy`](metadata_instrumentation.md#mysql_mdl_destroy)       | Instrumented metadata lock destruction. |

***

### mysql\_mdl\_create

```cpp
#define mysql_mdl_create(I, K, T, D, S, F, L, I, K, T, D, S, F, L) NULL
```

Defined in psi/mysql\_mdl.h:74

Instrumented metadata lock creation.

#### Parameters

| Parameter | Type | Description            |
| --------- | ---- | ---------------------- |
| `I`       |      | Metadata lock identity |
| `K`       |      | Metadata key           |
| `T`       |      | Metadata lock type     |
| `D`       |      | Metadata lock duration |
| `S`       |      | Metadata lock status   |
| `F`       |      | request source file    |
| `L`       |      | request source line    |
| `I`       |      | Metadata lock identity |
| `K`       |      | Metadata key           |
| `T`       |      | Metadata lock type     |
| `D`       |      | Metadata lock duration |
| `S`       |      | Metadata lock status   |
| `F`       |      | request source file    |
| `L`       |      | request source line    |

***

### mysql\_mdl\_set\_status

```cpp
#define mysql_mdl_set_status(L, S, L, S) do {} while (0)
```

Defined in psi/mysql\_mdl.h:81

***

### mysql\_mdl\_destroy

```cpp
#define mysql_mdl_destroy(M, M) do {} while (0)
```

Defined in psi/mysql\_mdl.h:95

Instrumented metadata lock destruction.

#### Parameters

| Parameter | Type | Description   |
| --------- | ---- | ------------- |
| `M`       |      | Metadata lock |
| `M`       |      | Metadata lock |
