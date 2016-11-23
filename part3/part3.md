#Part 3: Platform Provisioning

Rubicon Red MyST uses a declarative approach to platform provisioning, meaning users simply define the **target state** of the Oracle Middleware infrastructure to be deployed; which, at the push of a button, is automatically provisioned by MyST.

Within MyST, the target state is captured in the *“platform definition”*, which is divided into two layers:

* First, the **Platform Blueprint** an environment agnostic specification used to define the platform topology and configuration of your Oracle Middleware. This, provides an abstraction layer over the underlying infrastructure; allowing you to define a single Blueprint for all environments.

* Second, the **Platform Model**, overlays the environment specific configurations.

For each platform instance, we create a separate platform model to define all the environment specific configuration information.

Splitting the *“platform definition”* into two layers, provides infrastructure independence; enabling you to provision consistent middleware platforms across all environments regardless of infrastructure type, on premise and on cloud.

#####Note:

Most Oracle Middleware products run on Oracle WebLogic Application Server. WebLogic supports the concept of a Domain to group related clusters and servers. Some organisations use separate domains for each business unit or capability, others use it to group computational workload. How it is used is up to the organisation. 

For Oracle products that run on WebLogic, a *Platform Blueprint represents a logical definition of a WebLogic domain*. For this reason it is typical for a separate blueprint to be created in MyST Studio for each unique WebLogic domain type in an enterprise (e.g. SOA, ADF)

### Introspect Existing WebLogic Domains

MyST also allows us to introspect an existing WebLogic Domain and use that to generate an equivalent Platform Blueprint and/or Model. 

We can then use MyST to manage on-going configuration changes for the introspected platform as well as provision new environments with the same configuration. For example, you may want to re-provision your Dev and Test environment, to ensure that their configuration is consistent with Production.

### Side-by-Side Upgrade

MyST provides a simple and automated process for side-by-side upgrades. MyST allows you to introspect an existing 11g environment to create a corresponding 11g Platform Blueprint.

Next, just specify the Oracle Middleware 12c version required. MyST will automatically update the blueprint to one that is compliant with the Oracle Enterprise Deployment Guide for SOA 12c, whilst preserving your 11g configurations. This can then be used to provision an equivalent 12c Oracle Middleware platform.

## Version Control

Platform Blueprints and Platform Models are put under version control, allowing you to easily edit, review, test, promote and deploy configuration changes across all your environments.

This means incremental configuration changes are simple to make and propagate across all environments. Users just update the Platform Blueprint / Model to reflect the required target state; MyST will determine and perform the required steps to apply the necessary changes. 

MyST Release Pipelines allows you to establish a single integrated process for automating the promotion of Oracle Middleware platform configurations through each stage of the software delivery lifecycle.

### Enables Hybrid Cloud

With built in support for Oracle Cloud and Amazon Web Services, MyST enables you to define a standard process for delivering Oracle Middleware on premise and on cloud.

MyST provides cloud independence, allowing you to move your middleware infrastructure across different cloud providers as well as provide a path for migrating on-premise platforms to the cloud.

Creating a platform blueprint, platform model and provisioning a new fully operational FMW environment, is a simple three step process, which can be performed in minutes.

This part contains the following chapters:

* [Chapter 3.1 - Creating a Platform Blueprint](part3/createPlatformBlueprint/createPlatformBlueprint.md)   

* [Chapter 3.2 - Creating a Platform Model](part3/createPlatformBlueprint/createPlatformBlueprint.md)

* [Chapter 3.3 - Provision and Manage Platform Instance](part3/provisionPlatformInstance/provisionPlatformInstance.md)

* [Chapter 3.4 - Editing a Platform Blueprint / Model](part3/editPlatformBlueprint/editPlatformBlueprint.md)

* [Chapter 4.5 - Introspecting an existing WebLogic Domain](part3/introspectPlatformBlueprint/introspectPlatformBlueprint.md)

* [Chapter 4.6 - Side by Side Upgrade](part3/sideBySideUpgrade/sideBySideUpgrade.md)
