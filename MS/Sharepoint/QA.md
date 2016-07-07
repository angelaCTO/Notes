###SP App Model vs SP Solutions Model
---
SP Solutions Model is still supported in v2013 but is now deprecated and support for it has been pulled back. This is to ensure that customers migrate to the newest version of SP as prior SP versions are culpable to security, permision, and other flaws.
  
###Visual Studio vs SP Designer?
---

###SP Server vs SP Foundation?
---

###What is SP Workflow?
---
**SP Workflows** are pre-programmed mini-applications that streamline and automate a wide variety of business processes. Workflows can range from collecting signatures, feedback, or approvals for a plan or document, to tracking the current status of a routine procedure.
  - Workflows is an automated process that helps customers review a file. If A wants needs to review a file, A starts the workflow; then, other people are notified automatically to review the file. If they've forgotten the they'll be sent another notification/reminder email. After everyone has reviewed the file, a web page summarizes the workflow and serves as a record of who was involved
  - Use workflows to manage what files have been modified by users
  - ***But, what if you want to track more than one file?***
    
**Three workflows types:**
  - **A. Approval Workflow** - This workflow asks everyone to approve a file
    - 1. A special e-mail message is sent to the first approver. Your SharePoint site calls this e-mail message a “task” because the message is like a “to do” item for someone in the workflow. The task asks them to approve the file.
    - 2. Then the next person receives a task. They click the Approve button.
    - 3. Then a task is sent to the last person. When they click Approve, the workflow is complete.
    - Note, this is a sequential process and requires a person to approve before the next individual can review and approve it.
  - **B. Collect Feedback Workflow** - This workflow collects feedback
    - If you save a file to a document library on a SharePoint Server 2007 site, you can use the Collect Feedback workflow. The workflow will send out the e-mail for you, it won’t use attachments, and it will show everyone’s changes in the same copy of the file. Just think, everything in one place.
    - The Collect Feedback workflow sends all tasks at the same time, whereas the Approval workflow sends them one person at a time. That means that in the Collect Feedback workflow, there is no sequential order of who should review the file first, second, etc.
    - **To Start:** Start **Collect Feedback** from the document library that contains your file. Then, the workflow sends each reviewer an e-mail message, which SharePoint Server 2007 calls a task. The message will provide a link to the file. After the reviewers click the link, the file will open for them and they can give feedback. When the file is opened by the reviewer:
    - Select ***Edit Document***, make the changes, then select ***Edit This Task***. This will trigger a dialog that lets them type a brief, general comment about the file. Then, reviewers must click Edit this task, and then click ***Send Feedback** in order to complete their task, else the task is considered incomplete.
    - Using **Workflow Status** page when running the **Collect Feedback Window**. Here you can see who has completed their review and who hasn't as well as the general comments from each reviewer.  
      
  - **C. Collect Signatures Workflow** - This workflow collects digital signatures from people

**WorkFlow Status Page** - When the workflow is complete, the Workflow Status page summarizes the activity for the workflow. You can see each task, its status, and the outcome. Howevever, if someone rejects the file, you’d have to correct the file, and restart the workflow to get approval once more — that is, if you require unanimous approval.

**Intiator Messages** - If you are the initiator of the workflow, then you will recieve two notifications
  - 1. When the workflow has been initiated
  - 2. Completion notification, ie when the workflow has been completed - including the names of the people who approved or rejected the file
  - (Each of these messages has a link at the bottom that, when clicked, will take you to the Workflow Status page. That link is helpful on receipt of the first message, because you can check to see who has and who hasn’t completed their tasks yet.)

**Tracking Changes** - **Track Changes** is on the **Review** tab.
  - If you want changes tracked in a Word document, you’ll want to set that up prior to starting the Collect Feedback workflow. To do that, click the Track Changes button on the Review tab. Then save the document prior to starting the workflow. Later, when you collect all of the feedback, you can choose to accept or reject each person's changes.

**Cancel Workflow** 
