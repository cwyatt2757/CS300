1. Problem Statement
The goal of this project was to develop an efficient course management system for ABC University, enabling academic advisors to load, search, and display course information—including prerequisites—in a structured manner. The primary challenge was selecting an optimal data structure to support:

Fast insertion and retrieval of course data.

Alphabetical sorting for user-friendly course listings.

Scalability to accommodate future expansions (e.g., additional course details or prerequisite logic).

The solution needed to balance performance, ease of use, and maintainability while adhering to best practices in software design.

-------------------------------------------------------------------------------------------------------------------------------------------------------
2. Approach and Data Structure Justification
To address the problem, I evaluated three data structures:

Vector: Simple but inefficient for searching (O(n)) and requires explicit sorting (O(n log n)).

Hash Table: Offers O(1) lookups but lacks inherent sorting, requiring additional overhead.

Binary Search Tree (BST): Provides automatic sorting (O(n) in-order traversal) and efficient searches (O(log n)), making it ideal for this use case.

Why BST?

Sorted Output: The BST’s in-order traversal natively prints courses alphabetically, a key advisor requirement.

Balanced Performance: While insertion is slower (O(n log n)) than a vector, the trade-off is justified by faster searches and elimination of redundant sorting steps.

Adaptability: The tree structure simplifies future modifications (e.g., adding multi-level prerequisites).

This decision underscored the importance of selecting data structures based on operational priorities—a foundational concept in software engineering.

-------------------------------------------------------------------------------------------------------------------------------------------------------
3. Overcoming Roadblocks
Challenge 1: Validating Prerequisites

Problem: Prerequisites needed verification against a master course list to avoid invalid entries.

Solution: Implemented a two-pass file read:

First pass created a master list of valid course IDs.

Second pass cross-referenced prerequisites during BST insertion, discarding invalid entries.

Challenge 2: BST Degeneration

Problem: Unbalanced BSTs could degrade to O(n) search performance.

Mitigation: For this project’s scale (~hundreds of courses), the risk was minimal. A future enhancement could implement self-balancing trees (AVL/Red-Black) if the dataset grows.

Debugging involved iterative testing with sample files and validation checks (e.g., verifying output order and prerequisite counts).

-------------------------------------------------------------------------------------------------------------------------------------------------------
4. Impact on Software Design Approach
This project refined my design philosophy in three key ways:

Trade-off Analysis: Prioritizing BST’s sorting efficiency over a hash table’s faster lookups demonstrated the need to align data structures with user workflows.

Scalability Planning: The BST’s hierarchical design anticipates future features (e.g., prerequisite trees or course dependencies).

User-Centric Design: The interface prioritizes readability (e.g., formatted course displays) and intuitiveness (e.g., case-insensitive search).

These lessons will inform my approach to future projects, emphasizing proactive design choices over reactive fixes.

-------------------------------------------------------------------------------------------------------------------------------------------------------
5. Evolution of Maintainable and Adaptable Code
To ensure long-term usability, I implemented the following practices:

Modularity: Separated concerns into distinct classes (Course for data, BST for operations).

Documentation: Used descriptive comments (e.g., InOrderRecursive helper function) and followed naming conventions (e.g., PascalCase for methods).

Validation: Robust input handling (e.g., trimming whitespace, validating prerequisites) prevents runtime errors.

Extensibility: Pointer-based storage (e.g., vector<Course>*) allows seamless expansion without structural changes.

Key Takeaway: Investing in clean architecture and forward-compatible design reduces technical debt and simplifies future maintenance.

-------------------------------------------------------------------------------------------------------------------------------------------------------

Conclusion
This project demonstrated the critical role of data structure selection in software efficiency and usability. By leveraging a BST, I delivered a system that meets advisor needs while remaining adaptable for future enhancements. The experience reinforced the importance of design rigor, testing, and documentation—skills I will carry forward into professional development.

Areas for Improvement:

Implement balancing algorithms for larger datasets.

Add unit tests to validate edge cases (e.g., duplicate courses).

Extend the UI to support batch operations (e.g., bulk course loading).

This project has been instrumental in advancing my problem-solving and software design capabilities, preparing me for more complex computational challenges.


