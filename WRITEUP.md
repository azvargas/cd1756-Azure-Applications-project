# Write-up Template

### Analyze, choose, and justify the appropriate resource option for deploying the app.

*For **both** a VM or App Service solution for the CMS app:*
- *Analyze costs, scalability, availability, and workflow*
- *Choose the appropriate solution (VM or App Service) for deploying the app*
- *Justify your choice*

App Service
- Plans and costs
  - Free and shared plan: 
    - Used only for development.
    - From $0 to $9.49 / month
  
  - Service and basic plan: 
    - Low traffic requirements and not auto-scale features.
    - From $54.75 to to $219 / month

  - Premium plan
    - Automatic scalation, high perfomrnace
    - From $120.45 to $4,251.52 / month

  - Environment plan
    - Runs in a fully isolated environment connected to customers' virtual networks
    - From $410.16 to $13,128.32 / month

  - Plus certificate and domain costs

- Scalability and availability
  - App Servce can scalate in seconds from the portal and using CLI.
  - Also, it can scale out automatically based on a set of rules.

- Workflow
  - App Service has the simplest workflow for deployment, because it can be deployed directly from the workspate using CLI.

Virtual machine
- There are a lot of VM series, each one focused on a certain feature as memory, storage, GPU, etc. Our app fits well on a general purpose plan.

- Plans and costs
  - Bs v2-series
    - Low-cost option, run at a low to moderate baseline CPU.
    - Runs on the 3rd Generation Intel® Xeon® Platinum 8370C (Ice Lake) processor in a hyper-threaded configuration.
    - Test servers, low traffic web servers, small databases, micro services, build servers
    - From $7.59 to $971.63 / month

  - Bas v2-series
    - Same as Bs v2-series, but runs on the 3rd Generation AMD EPYC™ 7763v processor in a multi-threaded configuration.
    - From $6.86 to $878.19 / month (significant price reduction with a saving plan)

  - Bs series
    - Economical virtual machines. Offers complete cores (not vCPU's) and temp storage
    - From $ 7.59 to $ 607.36 / month

  - Plus costs of disks and networks. 

- Scalability and availability
    - The user needs to create a VM Scale Set and attach a set of VMs to it. This allows the workload to be balanced between several VMs. The number of VMs increases or decreases in response to the demand. The scale set has no cost; only the instances used are charged.

- Workflow
    - The workflow for a VM is more complex than the App Service workflow. The server must be configured manually with the proper runtime framework. The firewall should be configured, and credentials should be created for the development team to access the VM.

### My choice
I would choose a VM to start with because it offers a lower cost for a production environment. The minimum App Service plan for production starts at $ 54.75, and we can configure a low-traffic server for a fraction of that price. If the demand increases, we can escalate easily by adding VMs.

### Assess app changes that would change your decision.

*Detail how the app and any other needs would have to change for you to change your decision in the last section.* 

An IT team is required to maintain a virtual server. Changes in the IT department could make me change the decision, as App Service allows us to delegate the server maintenance. 