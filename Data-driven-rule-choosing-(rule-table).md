## Semantics

Given that OpenNARS operates under AIKR it demands vast computation resources in terms of space and time. Since it is not possible to satisfy all system demands a wise resource management is required. As described on ["working cycle"](https://github.com/opennars/opennars/wiki/Working-Cycle-and-Tasks-Management-in-OpenNARS) during each derivation system selects a [task-link](https://github.com/opennars/opennars/wiki/Types-of-Links:-task-and-term-links) and a [term-link](https://github.com/opennars/opennars/wiki/Types-of-Links:-task-and-term-links), basically a task and belief, and applies particular inference or structural or some other rule  in order to make a derivation task. Depending on some "type" of task-link or term-link certain subset of rules is applicable, then it is possible to pre-define certain types and condition such that a certain rules are applied if conditions are satisfied.     

**Data-driven rule choosing** is an approach of using rules that depends on a type of links being selected during inference. It allows to localize the subset of rules necessary for selected types of links only thus not exhaustively search for the right rule to make a derivation. Data driven rule choosing is a table that is defined in **org.RuleTables.java** as a giant nested switch statement. Type of links are defined as a set of constants in **org.entity.TermLink.java** class.

## Types of task-link and term-links
**Note: types of task-links and term-links described here exist only for implementation purposes, do not mix them with general types of links, that are task and term links.
 
    * SELF: for tasklink only, when it points to itself 
    
    * COMPONENT: when a link points to a component of a term

    *COMPOUND: when a link points to compound term
    
    * COMPONENT_STATEMENT: when a link points to a statement as component
    
    * COMPOUND_STATEMENT: when a link points to a compound statement
    
    *COMPONENT_CONDITION:
    
    *COMPOUND_CONDITION:

