###Learning Objectives
  - Use Team Explorer to access source code and assigned work
  - Create and manage workspaces
  - Check code into and out of TFS
  - Work with code offline
  - View source code history
  - Compare different versions of files
  - Create a basic branching structure
  - Perform basic automated builds

###Linking Work Terms
Link Type             | Description + Useage
--------------------- | ------------------
Parent/Child          | Hierarchical – special use for Microsoft Project and is the only link that can be used for Tree queries. A child can have only one parent.
Affects/Affected By   | Used for Change Requests which can impact more than one requirement – in other words, a single Change Request and Affect many requirements and vice versa.
Tests/Tested By       | Special relationships for relating Test Cases to Requirements and Test Cases to Bugs. 
Predecessor/Successor | Special relationship used by Microsoft Project to maintain this link in TFS but can be set in TFS directly.
Related               | Flat relationships between work items
Hyperlink             | Allows linking to a URL or URI
Versioned Item        | Allows linking to a specific version of an item stored in Version Control
Changeset             | Links work items to source code check-ins

**Note** Terminology is important here: 
  - The *forward end* of the relationship is the *second* part of the link type 
     - i.e. In the Parent/Child relationship, Child is the forward end of the relationship 
  - The *reverse end* of the relationship is the *first* part of the link type.
  - You can create a **New Linked Work Item** which will allow you to choose from the first 5 items.
    - In order to create **Hyperlinks**, **Versioned Item** or **Changeset Links** you must select Link To…  because the items at the end of these links cannot be created during the linking process.
  - Link types are not semantic – that is they are only a textual description – with two exceptions.
  - Parent/Child represents a hierarchical relationship
  - Predecessor/Successor is used by MS Project to maintain predecessor/successor relationships

These points have real implications for day to day use. For example, if you have two tasks and one is the predecessor to the other, if you start working on the successor task before the predecessor task is closed there is nothing to alert you to that fact – you must check the link types yourself.

* There are two other link types which are not noted on the slide and which are not discussed here – Test Results and Result Attachments. The majority of the time these will never be set by individuals.





