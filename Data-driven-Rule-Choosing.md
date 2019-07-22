## Rule choosing

Given that OpenNARS operates under AIKR, it is not possible to satisfy all demands in computational resources, so resource management is required. As described on ["working cycle"](https://github.com/opennars/opennars/wiki/Working-Cycle-and-Tasks-Management-in-OpenNARS), during each cycle the system selects a [task-link](https://github.com/opennars/opennars/wiki/Types-of-Links:-task-and-term-links) and a [term-link](https://github.com/opennars/opennars/wiki/Types-of-Links:-task-and-term-links), basically a task and belief, and applies particular inference rules to some derived tasks. Depending on the types of the task-link and the term-link, certain inference rules are applicable, while the others are not.     

**Data-driven rule choosing** is an approach of using rules according to the types of links selected during the inference cycle. It allows to localize the subset of rules necessary for selected types of links only, thus not exhaustively search for the "right" rule to make a derivation, nor specify the type of inference for each step in advance. This method is implemented in OpenNARS using a table defined in **org.RuleTables.java**, which is a giant nested switch statement. Types of links are defined as a set of constants in **org.entity.TermLink.java**.

## Types of task-link and term-links
**Note:** types of task-links and term-links described here exist only for implementation purposes, do not mix them with general types of links, which are task and term links. 
* SELF: when a link points to the same term itself (for task-link only)
    
* COMPONENT: points to a component of a compound term, e.g., from (&&, A, C) to C

* COMPOUND: the inverse link of COMPONENT, e.g., from C to (&&, A, C)
    
* COMPONENT_STATEMENT: points to a component of a statement, e.g., from <C --> A> to C
    
* COMPOUND_STATEMENT: the inverse link of COMPONENT_STATEMENT, e.g., from C to <C --> A>
    
* COMPONENT_CONDITION: points to a condition of an implication statement, e.g., from <(&&, C, B) ==> A> to C
    
* COMPOUND_CONDITION: the inverse link of COMPONENT_CONDITION, e.g., from C to <(&&, C, B) ==> A>

