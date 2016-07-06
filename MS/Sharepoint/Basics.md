##What Are The Advantages Of SharePoint?
---
  - Network Collaboration
  - Security Implemetation (Permissions)
    - Security Trimming 
  - Built-In Versioning (Major, minor)
    - Drafts : Minor Version
    - Published : Major Version
  - Collaborative Editing
    - Differences are merged, keeps documents recent/relevent

##Sharepoint App Model (The Change From SharePoint Solutions Development)
---
  - **What was wrong with SharePoint Solutions?** 
    - **Instability** : Custom code written by developers run within SP's host enviroment. This reduces reduced stability of MS SP. Eliminating any type of custom code that run within SP enviroment results in lower risks, fewer problems, and greater stability for the hosting farm. 
      - ***Custom code running inside the SharePoint host environment poses risks and compromises scalability.***
        - *w3wp.exe* : Main SP worker process (managed code deployed in a farm solution runs here)
        - *SPUCWorkerProcess.exe* : SP sandboxed worker process (managed code deployed using a sandbox solution runs here)
    - **Difficult To Upgrade Solutions** : SharePoint solutions are often developed with full trust and perform complex operations. These solutions are often tightly bound to a particular feature set, which means that they might not move gracefully to the next version of SharePoint. 
      - ***Custom code with dependencies on in-process DLLs causes problems when migrating from one version of SharePoint to the next.***
    - **Security Concerns** : The root problem is that code always runs under the identity and with the permissions of a specific user. There is a security issue in that a SharePoint solution with a feature receiver is able to execute code that can do anything that the site administrator can do. There really isn’t a practical way to constrain the SharePoint solution code so that it runs with a lesser set of permissions than the user that has activated the feature. 
      -***A permissions model for custom code based entirely on the identity of the current user is inflexible.***
    - **Permissions + Deployment Issues** : In a nutshell, the security problems with SharePoint solutions stem from the fact that you cannot effectively configure permissions for a specific SharePoint solution. This limitation cannot be overcome, because the SharePoint solution development model provides no way to establish the identity of SharePoint solution code independent of user identity. Because there is no ability to establish the identity of code from a SharePoint solution, there is no way to configure permissions for it.
      - ***User impersonation solves the too-little-permissions problem but replaces it with the too-many-permissions problem, which is even worse.***
  - *What's good about SharePoint App?*
    - Following the design flaws of its predecessor, ...
      - Apps must be supported in Office 365 and in on-premises farms
      - App code never runs within the SharePoint host environment.
      - App code programs against SharePoint sites by using web service entry points to minimize version-specific dependencies.
      - App code is authenticated and runs under a distinct identity
      - App permissions can be configured independently of user permissions
      - Apps are deployed by using a publishing scheme based on app catalogs. Apps that are published in a catalog are easier to discover, install, and upgrade

###SharePoint App Model Architecture
  - **SharePoint Farm**
    - A *SharePoint Farm* is a collection of SP servers or SQL servers that work in concert to provide a set of basic SP services to support a single site. 
      - The ability of multiple servers to work in conjunction and provide redundancy is important in the cloud, especially for large data centers. One value of such a system is its failover capabilities - if any server is incapacitated, another one can take over for it. The servers can also provide readily available backups that can scale to immense sizes.
      - Within a farm, there are several services that run on one or more servers. These services provide basic functionality for SharePoint and regulate which services should run on which servers, in an effort to manage the impact on overall farm architecture and performance
  - **SharePoint Tenancy** 
    - A *SharePoint Tenancy* is a set of site collections that are configured and administrated as a unit. When a new customer establishes an Office 365 account to host its SharePoint sites, the Office 365 environment creates a new tenancy
      - *Tenants* - Customer's buisness users who access the tenancy
    - When the Office 365 environment creates a new tenancy for a customer, it creates an administrative site collection which is accessible to users who have been configured to play the role of a *Tenant Administrator*
      -  A tenant administrator can create additional site collections and configure the set of services that are available to all the sites running within the tenancy.
    - The architecture of the SharePoint App Model requires that apps are always installed and run within the context of a specific tenancy. 
      - SharePoint 2013 is able to support installing and running SharePoint apps in on-premises farms by transparently creating a farm-wide tenancy behind the scenes that is known as the *Default Tenancy.*
  
