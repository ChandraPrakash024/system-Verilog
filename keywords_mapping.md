# BSV to SystemVerilog Keyword Mapping

| **BSV Keyword**             | **SystemVerilog Equivalent**                            | **Description**                                                                 |
|-----------------------------|---------------------------------------------------------|---------------------------------------------------------------------------------|
| `module`                    | `module`                                                | Both languages use `module` to define hardware modules.                         |
| `interface`                 | `interface`                                             | Both have `interface`, though the usage might differ slightly.                  |
| `method`                    | `task/function`                                         | BSV methods map to SV tasks (if no return value) or functions (if returning a value). |
| `Action`                    | `void task`                                             | BSV’s `Action` type indicates a method with no return value, equivalent to a `void` task in SV. |
| `ActionValue#(T)`           | `function returning T`                                  | BSV `ActionValue` returns a value, mapped to a function returning a value in SV. |
| `Bool`                      | `logic` or `bit`                                        | BSV’s `Bool` is a boolean type, represented by `logic` or `bit` in SV.           |
| `Reg#(T)`                   | `reg` or `logic`                                        | In BSV, a `Reg` holds state, which maps to `reg` or `logic` in SV.               |
| `Wire#(T)`                  | `wire`                                                  | Both use `wire` for combinational logic signals.                                 |
| `Bit#(n)`                   | `logic [n-1:0]`                                         | BSV’s `Bit#(n)` corresponds to SV’s `logic` vector.                              |
| `UInt#(n)`                  | `logic [n-1:0]`                                         | Unsigned integers of fixed width in BSV map to `logic [n-1:0]` in SV.            |
| `Int#(n)`                   | `logic signed [n-1:0]`                                  | Signed integers map to signed logic vectors in SV.                               |
| `Vector#(n, T)`             | `T [n-1:0]`                                             | BSV’s `Vector#(n, T)` is represented as an array in SV.                          |
| `rule`                      | `always_ff` or `always_comb` block                      | BSV’s `rule` constructs map to procedural blocks like `always_ff` or `always_comb` in SV. |
| `let`                       | `localparam` or `parameter`                             | BSV’s `let` expression is similar to `localparam` or `parameter` in SV.          |
| `enum`                      | `enum`                                                  | Both languages use `enum` for enumerated types.                                  |
| `FIFO#(T)`                  | `queue` or custom FIFO logic                            | BSV's FIFO can be implemented using SV `queue` or custom logic.                  |
| `TaggedUnion#(T)`           | `union`                                                 | Tagged unions in BSV are represented by `union` in SV.                           |
| `case`                      | `case`                                                  | Both BSV and SV use `case` for conditional branching.                            |
| `if`                        | `if`                                                    | Both use `if` for conditional branching.                                         |
| `Vector`                    | `array`                                                 | BSV’s `Vector` is equivalent to an array in SV.                                  |
| `function`                  | `function`                                              | Both languages use `function` for returning values.                              |
| `task`                      | `task`                                                  | Tasks in both BSV and SV perform actions without returning a value.              |
| `RegFile#(n)`               | `memory array`                                          | BSV’s `RegFile` can be represented as a memory array in SV.                      |
| `deriving`                  | N/A                                                     | No direct equivalent in SV; manual coding is needed for equivalent functionality.|
| `import`                    | `import` or `include`                                   | Both BSV and SV can import external modules or files.                            |
| `package`                   | `package`                                               | Both use `package` to encapsulate and group related code.                        |
| `instance`                  | Instantiation of a module or interface                  | In SV, modules and interfaces are instantiated directly without an explicit keyword like `instance`. |
| `typedef`                   | `typedef`                                               | Both BSV and SV use `typedef` to define new types.                               |
| `provisos`                  | N/A                                                     | No direct equivalent in SV; used in BSV for parameterized types and constraints. |
| `interface method`           | `task/function in interface`                           | Interface methods in BSV are similar to tasks/functions defined inside an SV interface. |
| `synthesized`               | Implicit in SV                                          | BSV has explicit synthesis annotations, whereas synthesis is typically implicit in SV. |
| `inout`                     | `inout`                                                 | Both languages use `inout` for bidirectional signals.                            |
| `module#(T)`                | `module #(parameter T)`                                 | Parameterized modules in BSV map to parameterized modules in SV.                 |
| `parameter`                 | `parameter`                                             | Both use `parameter` for constants.                                              |
| `dynamic`                   | No direct equivalent                                    | BSV’s `dynamic` features, like dynamic scheduling, require manual implementation in SV. |
| `begin`/`end`               | `begin`/`end`                                           | Both use `begin`/`end` to define procedural blocks.                              |
| `default_clock`             | N/A                                                     | No direct equivalent in SV; clocking domains are specified explicitly in SV.     |
| `triggered_by`              | N/A                                                     | No direct equivalent; this is a part of BSV’s rule system for triggering actions based on conditions. |
