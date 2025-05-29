# Database Normalization
<h2>What is Database Normalization?</h2>   
<p>Database normalization is the process of organizing data in a relational database to reduce redundancy and improve data integrity. The goal is to divide large, complex tables into smaller, related tables and define relationships between them.</p>

<h2>Why Normalize?</h2>
<p>Normalization helps to eliminate data anomalies, ensures data consistency, and makes the database easier to maintain. It also improves query performance by reducing the amount of data that needs to be processed.</p>

<h2>First Normal Form (1NF)</h2>
<p>Ensures that: Each table cell holds one value (no arrays/lists). </p>
<p>Violating 1NF - Using row order to communicate(order) information, different data types if it even allows you (int field having a string), PRIMARY KEY is set<p>

<h2>Second Normal Form (2NF)</h2>
<p><strong>Rule:</strong> Must be in 1NF, and all non-key attributes must be fully functionally dependent on the entire primary key (applies to tables with composite keys).</p>
<p><strong>Violation Example:</strong> A column that depends only on part of a composite key.</p>
<p><strong>Fix:</strong> Break the table into two or more tables to separate the partial dependencies.</p>

<h2>Third Normal Form (3NF)</h2>
<p><strong>Rule:</strong> Must be in 2NF, and all non-key attributes must be directly dependent on the primary key (no transitive dependencies).</p>
<p><strong>Error Example:</strong> Storing both Department ID and Department Name in an Employees table when the Name depends on the ID.</p>
<p><strong>Fix:</strong> Move the transitive dependency (ex: Department Name) into a separate table.</p>

<h2>Boyce-Codd Normal Form (BCNF)</h2>
<p><strong>Rule:</strong> A stronger version of 3NF. Every determinant must be a candidate key.</p>
<p><strong>Error Example:</strong> If a non-primary column determines another column (ex: color , birdhouse style are linked).</p>
<p><strong>Fix:</strong> Decompose the table to ensure that all determinants are candidate keys.</p>

# 3NF - Once you have normalized your table to 3NF it is considered fully normalized.

<h2>Fourth Normal Form (4NF)</h2>
<p><strong>Rule:</strong> Must be in BCNF and have no multivalued dependencies (MVDs).</p>
<p><strong>Violation Example:</strong> A student has multiple languages and multiple hobbies, causing a cartesian product of those combinations.</p>
<p><strong>Fix:</strong> Separate the independent multivalued attributes into separate tables.</p>

<h2>Fifth Normal Form (5NF)</h2>
<p><strong>Rule:</strong> Must be in 4NF and free of join dependencies — the data cannot be split into smaller pieces without losing meaning after recombining.</p>
<p><strong>Violation Example:</strong> A product is associated with multiple suppliers and features, and splitting them into pairs causes invalid recombinations.</p>
<p><strong>Fix:</strong> Keep the structure or decompose into three or more tables only if joins can guarantee reconstruction of valid rows.</p>


