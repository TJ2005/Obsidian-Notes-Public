---
Title: Data Base Management System Lecture 1
Status: 
marker: 
tags: 
Date: 22-07-2024
Time: 13:17
---
Certainly! Here is the rewritten note with a more organized and structured approach:

---

# Database Management System Lecture 1

## Introduction
This lecture introduces the basics of representing data in a tabular format and the initial steps in database design. Key topics include understanding user requirements, creating visual formats, developing schemas using entity-relationship models, and organizing data efficiently.

## Contents

- **[Introduction to Tabular Representation of Data](#introduction-to-tabular-representation-of-data)**
  - **[Overview](#overview)**
    - [Tabular Representation of Data](#tabular-representation-of-data)
    - [Problem Statement Analysis](#problem-statement-analysis)
    - [Visual Format](#visual-format)
    - [Schema Preparation](#schema-preparation)
    - [Entity-Relationship Model](#entity-relationship-model)
    - [Data Cleaning](#data-cleaning)
  - **[Steps to Convert Abstract Ideas into a Schema](#steps-to-convert-abstract-ideas-into-a-schema)**
    - [Understand User Requirements](#understand-user-requirements)
    - [Visual Representation](#visual-representation)
    - [Schema Preparation](#schema-preparation-1)
    - [Entity-Relationship Model](#entity-relationship-model-1)
    - [Data Cleaning](#data-cleaning-1)
  - **[Key Concepts](#key-concepts)**
    - [Tabular Representation](#tabular-representation)
    - [User Requirements](#user-requirements)
    - [Visual Format](#visual-format-1)
    - [Schema](#schema)
    - [Entity-Relationship Model (ERM)](#entity-relationship-model-erm)
    - [Data Cleaning](#data-cleaning-2)

- **[Entity Sets](#entity-sets)**
  - **[Definitions](#definitions)**
    - [Entity](#entity)
    - [Entity Set](#entity-set)
    - [Primary Key](#primary-key)
    - [Candidate Key](#candidate-key)
  - **[Representation of Entity Sets in Graphs](#representation-of-entity-sets-in-graphs)**
    - [Instructor Table](#instructor-table)
    - [Student Table](#student-table)

- **[Relationship Sets](#relationship-sets)**
  - [Relationship](#relationship)

- **[Roles](#roles)**
  - [Course Prerequisite](#course-prerequisite)

- **[Why Use Entities Instead of Attributes](#why-use-entities-instead-of-attributes)**

- **[Attribute Types](#attribute-types)**
  - [Simple and Composite Attributes](#simple-and-composite-attributes)
  - [Single Valued and Multivalued Attributes](#single-valued-and-multivalued-attributes)
  - [Derived Attributes](#derived-attributes)
  - [Domain](#domain)
  - **[Representing Complex Attributes in ER Diagram](#representing-complex-attributes-in-er-diagram)**
    - [Instructor Table with Complex Attributes](#instructor-table-with-complex-attributes)

- **[Mapping Cardinalities](#mapping-cardinalities)**

- **[Total and Partial Participation](#total-and-partial-participation)**
  - **[Total Participation](#total-participation)**

- **[Expressing Weak Entity Sets](#expressing-weak-entity-sets)**

- **[Redundant Attributes](#redundant-attributes)**

- **[Partial Participation](#partial-participation)**

## Introduction to Tabular Representation of Data

### Overview
- **Tabular Representation of Data**: Organizing information in a table format to present data clearly and concisely.
- **Problem Statement Analysis**: Understanding user requirements to address specific needs and challenges.
- **Visual Format**: Converting abstract ideas into diagrams or other visual formats to aid understanding.
- **Schema Preparation**: Designing the structure for organizing data in a logical format.
- **Entity-Relationship Model**: Developing a model to define and illustrate the relationships between data entities.
- **Data Cleaning**: The process of refining data to ensure accuracy and consistency.

### Steps to Convert Abstract Ideas into a Schema
- **Understand User Requirements**: Analyze the problem statement to grasp the user's needs and expectations.
- **Visual Representation**: Create visual aids such as diagrams or flowcharts to represent abstract ideas.
- **Schema Preparation**: Develop a structured schema that organizes data efficiently and logically.
- **Entity-Relationship Model**: Define entities and their relationships to establish how data elements interact.
- **Data Cleaning**: Correct or remove inaccuracies in the data to ensure the final schema is reliable.

### Key Concepts
- **Tabular Representation**: Using tables to clearly and effectively present data.
- **User Requirements**: A detailed understanding of what the user needs from the database.
- **Visual Format**: Visual tools such as diagrams and flowcharts to represent data structures and relationships.
- **Schema**: The structured framework that defines the organization of data.
- **Entity-Relationship Model (ERM)**: A diagram that represents entities and their relationships within a database.
- **Data Cleaning**: The process of ensuring data accuracy by correcting or removing errors.

## Entity Sets

### Definitions
- **Entity**: An object that exists independently and is distinguishable from other objects.
- **Entity Set**: A collection of similar entities sharing the same properties.
- **Primary Key**: An attribute or a set of attributes that uniquely identifies an entity within an entity set.
- **Candidate Key**: A set of attributes that can uniquely identify a record in a table.

### Representation of Entity Sets in Graphs
- **Attributes**: Listed inside an entity rectangle in ER diagrams.
- **Primary Key**: Underlined within the entity rectangle.

**Example:**

| Instructor |
| ---------- |
| ID         |
| Name       |
| Salary     |

| Student       |
| ------------- |
| ID            |
| Name          |
| Total Credits |

## Relationship Sets
- **Relationship**: An association between entities.

**Example:**
- `44553 (Peltier)` Advisor to `2222 (Einstein)`
- Student entity is related to Instructor entity through an Advisor relationship.

## Roles
- **Course Prerequisite**: A role where one course is a prerequisite for another.

## Why Use Entities Instead of Attributes
- Using entities is preferable when multiple values are shared by various entities, as it simplifies the design and management of the database.

## Attribute Types
- **Simple and Composite Attributes**: 
  - **Simple Attributes**: Atomic attributes that cannot be divided further.
  - **Composite Attributes**: Attributes that can be subdivided into smaller components.
- **Single Valued and Multivalued Attributes**: 
  - **Single Valued Attributes**: An attribute that holds a single value for a given entity.
  - **Multivalued Attributes**: An attribute that can hold multiple values (e.g., `Phone_Number`).
- **Derived Attributes**: Attributes whose values can be computed from other attributes (e.g., Age derived from Date of Birth).
- **Domain**: The set of permissible values for an attribute.

### Representing Complex Attributes in ER Diagram

| Instructor         |
| ------------------ |
| ID                 |
| Name               |
| - First Name       |
| - Middle Name      |
| - Last Name        |
| Address            |
| - Street           |
| - Locality         |
| etc.               |

## Mapping Cardinalities
- Cardinalities define the number of instances of one entity that can or must be associated with each instance of another entity.

## Total and Partial Participation

### Total Participation
- Every instance of an entity must participate in at least one relationship. For example, every student must be enrolled in at least one course.

## Expressing Weak Entity Sets
- Weak entity sets are those that do not have a primary key of their own and depend on other entity sets for their identification.

## Redundant Attributes
- Redundant attributes are those that can be derived from other attributes and do not need to be stored separately.

## Partial Participation
- Partial participation means that not all instances of an entity need to participate in a relationship.

## References

### Enhancements Needed
- Add proper indexing.
- Include charts and visual aids.
- Enhance notes with additional relevant information.
- Organize topics logically for better understanding.

---