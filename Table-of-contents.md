This page shows the overall structure of all the wiki pages on OpenNARS, which serve as an intermediate layer between the publications (as listed in https://cis.temple.edu/~pwang/papers.html and https://phillyagiteam.github.io/Website/) and comments of the code (javadoc). The pages are linked to each other, as well as to other materials (PDF files, data files, videos, etc.).

The pages are roughly divided into two groups, the first group systematically explains OpenNARS in its current implementation, with the pages roughly correspond to the structures of the system; the second group provides different tours over the structure, for different users and purposes.

1. Aspects of OpenNARS
  - Language and I/O
    * Narsese grammar with annotations
    * experience file: format and usage
    * Narsese symbol list (ASCII version and PDF version)
    * term: types, format
    * sentence: types, format
    * truth value: definition and examples
    * desire value: definition and examples
    * priority-durability values
    * GUI explanation
    * I/O channels
    * database and knowledge-base connection
    * interface for plugin
    * inter-system communication protocol
    * built-in operator list
    * experiments on perception
    * experiments on natural language processing
  - Logic
    * basic principles behind the truth-value/desire-value functions
    * NALs
    * revision rule
    * choice rule
    * basic syllogistic rules
    * compositional rules
    * structural rules
    * backward inference (question, query, goal)
    * temporal inference
    * [procedural inference](https://github.com/opennars/opennars/wiki/Procedural-Inference) 
  - Data structure
    * memory overall structure
    * bag, item, and budget-value
    * truth-value and evidential basis
    * sentence: content and attributes
    * task and belief
    * task link
    * term link
    * concept: content and attributes
  - Control
    * working cycle of the system
    * life cycle of a task (by type)
    * data-driven rule choosing (rule table)
    * budget functions
    * emotion and self-control
    * parameters and configuration file

2. Entry points
  - user guides
    * beginner's guide
    * user's manual
    * developer's guide
  - example and demonstration
    * selected examples of task processing (i.e., multi-step examples)
    * annotated list of experience files in Narsese (i.e., single-step examples)
    * annotated list of demonstration
  - overview
    * glossary
    * selected publications
    * selected videos