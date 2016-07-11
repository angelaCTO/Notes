
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

###WORK ITEMS
- Work items are the “currency” of TFS. 
- Database record from the form you are looking at) 
- Almost all reporting is driven off of data captured in the work item (except for source control and build data but even some of these are driven by work items)

- Important fields :
	- Area classifications are used to allow hierarchical analysis of the data and as sub-containers for items in your project
	- Iterations relate to when it is going to be released
	- The structure of Areas and Iterations is covered in the Project Management session
	- Description is a free-form plain text field
	- On Hold is used to indicate that the work is blocked and the developer cannot perform their work
	- A suggested best practice is that if a user changes On Hold to Yes, they should fill out an Issue work item type describing the situation so that their manager can manage and track the problem. In other words, On Hold is for longer delays (i.e. an item on hold for an hour is not a big deal – don’t fill out an issue because it just causes noise)
	- State is a key driver of data and indicates whether the item is in work, being tested or has completed testing.
	- Reason indicates why a work item is in a particular State.
	- Yellow caution indicators denote tabs or fields which are required that have not been filled in. These fields are listed at the top of the work item (denoted by the yellow bar in the figure on the slide). As you “fix” each problem, the next problem field is displayed at the top of the work item
	- Fields are customizable and if you have a need for a 	new field, different values in a field or just changing the layout, you can contact GRP GIDE to make those changes
	- Work Items and all fields can be printed by opening a work item and selecting Print
	
###LINKING WORK ITEMS
- Link Types / Description
	- Parent / Child
		- Hierarchial - special use for MS Project and is the only link that can be used for Tree queries. Achild can only have one parent
	- Affects / Affected By
		- Used for CRs which
	- Tests / Tested By
	- Predecessor / Sucessor
	- Related 
	- Hyperlink
	- Versioned Item
	- Changeset
		

