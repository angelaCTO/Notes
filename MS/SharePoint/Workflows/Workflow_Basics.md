#Workflow Basics

---

**SharePoint workflows** are pre-programmed mini-applications that streamline and automate a wide variety of business processes. **Workflows** can range from collecting signatures, feedback, or approvals for a plan or document, to tracking the current status of a routine procedure. Users interact with workflows using the browser or Microsoft Office applications. You use the browser to add workflow templates to lists, libraries, content types, and sites.

###Basic
  - You can use SharePoint Designer to create reusable workflows that can be associated with multiple lists or libraries, and you can then save the reusable workflow as a workflow template in the form of a Windows SharePoint solution file (.wsp)
    - This workflow template can then be imported to another site to be used to create the same workflow on the new site or imported into Visual Studio 2012, where it can be further enhanced. 

###Process Automation Methods
  1. **Really Simple Syndication (RSS) Feeds**
    - Use RSS feeds for finding information from a variety of sources on an ad-hoc basis. 
      - RSS feeds use a pull mechanism to find information; that is, you only find information exposed by RSS feeds when you open an RSS reader, such as Windows Internet Explorer or Microsoft Outlook.
  2. **Alerts** 
    - Use alerts for regular notifications of new, modified, or deleted content. 
    - Alerts can be configured to send email immediately when SharePoint finds information in which you have registered an interest, or a daily or weekly digest of that information.
  3. **Content Approval** 
    - Along with versioning, you can use content approval to manage content and control who can see content that is classified as draft. When you enable content approval on a list or library, a column named **Approved Status** is added to the library, together with a number of views. 
    - Enabling content approval activates the **Approval/Reject Command** on the list item menu and on the ribbon. 
        - The **Approval Status** column can contain the choices **Approved**, **Rejected**, or **Pending**.
        - Users who are assigned the **Manage Lists** permission can approve or reject items. 
          - No email is sent to users with the Manage List permission. They would need to visit the list to see if any items are in a pending state.
          
**Workflows** - Workflows are used to automate and track processes that require human intervention, such as notifying users when their action is required to move the process forward. *Workflows are a series of tasks that produce an outcome.*
  - Browser
  - SharePoint Studio
  - Visual Studio

**Event Recievers** - Event receivers are used to automate processes that require no human intervention, such as moving job applications from one document library to a series of other document libraries for some purpose.
  - Visual Studios

---

###Workflow Instances

To create a workflow, configure and associate the workflow template to a list, libary, or site. An instance of the workflow can then be initiated by using the configured workflow template, which defines the conditions that should be tested to decide what tasks to complete to produce the outcome

  1. An instance of the workflow is created when a workflow event is triggered for a specific list item or file
  2. Once instantiated, it enters the workflow at its start point and progresses through the workflow process (defined by the template) until it reaches the end (state = "Completed")

A list item or file can be related to more than one workflow instance so long as each workflow instance is related to different workflows.

To create a workflow:
  1. Provide a workflow name
  2. Decide how workflow instances should start
  3. Complete an association form to provide values that are needed by the workflow 
     - If a workflow is set up to start manually, an initiation form may be created (as a kind of "pop-up") that lets users define their own values to be used by the workflow

###Lists Used By Workflow Instances
  - **Task List** - Use this list to: 
    + Create task items to remind users of the work they need to complete 
    + Collect information for the next step of the workflow
  - **History List** - Use this list to:
    + 


  
