
##TFS Developer P1 10a - 2p

###AGENDA : 
1. Learning Objective + Working in TFS
2. Work Items Lab1 
3. Basic Version Control Concepts 
4. Version Control Lab2
5. Branching and Merging
6. Branching + Merging Lab3
7. Unit Testing
8. Unit Testing Lab4
9. IntellTrace
10. Automated Builds

###**WORK ITEMS**
- Work items are the “currency” of TFS. 
- (Database record from the form you are looking at) 
- Almost all reporting is driven off of data captured in the work item (except for source control and build data but even some of these are driven by work items)
- **Important fields** :
  - Area classifications are used to allow hierarchical analysis of the data and as sub-containers for items in your project
  - Iterations relate to when it is going to be released
  - The structure of Areas and Iterations is covered in the Project Management session
  - **Description** is a free-form plain text field
  - **On Hold** is used to indicate that the work is blocked and the developer cannot perform their work
  - A suggested best practice is that if a user changes On Hold to Yes, they should fill out an Issue work item type describing the situation so that their manager can manage and track the problem. In other words, On Hold is for longer delays (i.e. an item on hold for an hour is not a big deal – don’t fill out an issue because it just causes noise)
  - **State** is a key driver of data and indicates whether the item is in work, being tested or has completed testing.
  - **Reason** indicates why a work item is in a particular State.
  - **Yellow caution indicators** denote tabs or fields which are required that have not been filled in. These fields are listed at the top of the work item (denoted by the yellow bar in the figure on the slide). As you “fix” each problem, the next problem field is displayed at the top of the work item
  - **Fields** are customizable and if you have a need for a 	new field, different values in a field or just changing the layout, you can contact GRP GIDE to make those changes
  - Work Items and all fields can be printed by opening a work item and selecting Print
	
###LINKING WORK ITEMS
- Link Types + Description
	- Parent/Child
	  - Hierarchial - special use for MS Project and is the only link that can be used for Tree queries. A child can only have one parent
	- Affects/Affected By
	  - Used for CRs which can impact more than one requirement - in other words, a single CR can affect many requirements, vv.
	- Tests/Tested By
	  - Special Relationships for relating Test Cases to Requirements and Test Cases to bugs
	- Predecessor/Sucessor
	  - Special Relationships used by MS Project to maintain this link in TFS but can be set in TFS directly 
	- Related
	  - Flat relationships between two work items
	- Hyperlink
	  - Allows linking to a URL or URI
	- Versioned Item
	  - Allows linking to a specific version of an item stored in Version Control
	- Changeset
	  - Links work items to source code check ins

- Terminology is important here – the forward end of the relationship is the second part of the link type (i.e. in the Parent/Child relationship, Child is the forward end of the relationship). 
- The reverse end of the relationship is the first part of the link type.
- You can create a New Linked Work Item which will allow you to choose from the first 5 items. In order to create Hyperlinks, Versioned Item or Changeset links you must select Link To…  because the items at the end of these links cannot be created during the linking process.
- Link types are not semantic – that is they are only a textual description – with two exceptions.
- Parent/Child represents a hierarchical relationship
- Predecessor/Successor is used by MS Project to maintain predecessor/successor relationships
- These points have real implications for day to day use. For example, if you have two tasks and one is the predecessor to the other, if you start working on the successor task before the predecessor task is closed there is nothing to alert you to that fact – you must check the link types yourself.
- *There are two other link types which are not noted on the slide and which are not discussed here – Test Results and Result Attachments. The majority of the time these will never be set by individuals*

###QUERYING WORK ITEMS
- **Flat Links** - show a bi-directional relationship where each work item is a peer of the other work item
- **Direct Links** - show a single link level with the reverse end of the relationship first and the foward end of the relationship idented
- **Tree Links** - describe a recursive relationship and can only be used with the Parent/Child (hierarchial) link type
  - Ths is a special link type is both MS Project and MS Excel. 
    - Both represent this relationship
  - Allows for showing multiple levels
  - Direct links can show only one level of hierarchy.  Any more and there could possibly be circular references.  Thus, they are only a “one deep” query

###CUSTOMIZING QUERIES
- **Column Options** lets you choose which columns are in the query resilts and can be selected
- **And/Or Groupings** can be created by selecting multiple rows and clicking the group buttons on the toolbar
- **Special Values** are 
  - **@Projects** - The project that the query is running in - remove it to see work items in all projects
  - **@Me** - The person running the query
  - **@Today** - The current date 
- You can select the type of query (Flat, Directed or Tree) from the drop down in the center of the toolbar. Selecting different types will give you different options*
- **View Results** allows you to view the results of the query before saving it (this is the same as the Run button shown to the left on the same toolbar)
- Queries must be saved in a Team Project – they cannot be saved at the Team Project Collection level. The only way to view work items in multiple projects is to remove the first line of the query (Team Project = @Project)
- When you save the query you will save it in the My Queries folder in Team Explorer unless you have permission to save it in the Team Queries section which is visible to all team members
- To save an existing query that you edited with a different name, select File > Save [New Query 1] As… and you will be prompted to provide a different name/location

###QUERY LINK TYPES DURING CUSTOMIZATION
- 
