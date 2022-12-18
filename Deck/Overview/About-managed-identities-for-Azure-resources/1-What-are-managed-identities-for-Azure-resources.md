##

A common challenge for developers is the management of secrets, credentials, certificates, and keys used to secure communication between services. `_____` eliminate the need for developers to manage these credentials.

%

A common challenge for developers is the management of secrets, credentials, certificates, and keys used to secure communication between services. **Managed identities** eliminate the need for developers to manage these credentials.

##

While developers can securely store the secrets in Azure Key Vault, services need a way to access Azure Key Vault. Managed identities provide an automatically managed identity in Azure Active Directory for applications to use when connecting to resources that support Azure 

%

Active Directory authentication

##

Applications can use managed identities to obtain Azure AD tokens without having to manage any

%

credentials

##

Here are some of the benefits of using managed identities:

- You don't need to manage credentials. Credentials aren’t even `_____` to you.
- You can use managed identities to authenticate to any resource that supports Azure AD authentication, including your own `_____`.
- Managed identities can be used at no extra `_____`.

%

- You don't need to manage credentials. Credentials aren’t even **accessible** to you.
- You can use managed identities to authenticate to any resource that supports Azure AD authentication, including your own **applications**.
- Managed identities can be used at no extra **cost**.

##

Managed identities for Azure resources is the new name for the service formerly known as

%

Managed Service Identity (MSI)

##

There are two types of managed identities:

- `_____`
- `_____`

%

- System-assigned
- User-assigned

##

Some Azure resources, such as virtual machines allow you to enable a managed identity directly on the resource.

This type of managed identity is called

%

System-assigned

##

When you enable a system-assigned managed identity:
- A `_____` of a special type is created in Azure AD for the identity.
  - The `_____` is tied to the lifecycle of that Azure resource.
  - When the Azure resource is deleted, Azure automatically deletes the `_____` for you.

%

When you enable a system-assigned managed identity:
- A **service principal** of a special type is created in Azure AD for the identity.
  - The **service principal** is tied to the lifecycle of that Azure resource.
  - When the Azure resource is deleted, Azure automatically deletes the **service principal** for you.

##

When you enable a system-assigned managed identity, a service principal of a special type is created in Azure AD and tied to the lifecycle of that Azure resource.

By design, only that Azure resource can use this identity to request `_____` from Azure AD.

%

By design, only that Azure resource can use this identity to request **tokens** from Azure AD.

##

When you enable a system-assigned managed identity, you authorize the managed identity to have access to one or more

%

services

##

Managed identities can be created as a standalone Azure resource. You can create a managed identity and assign it to one or more Azure Resources.

This type of managed identity is called

%

User-assigned

##

When you enable a user-assigned managed identity:
  - A `_____` of a special type is created in Azure AD for the identity. The `_____` is managed separately from the resources that use it.

%

When you enable a user-assigned managed identity:
  - A **service principal** of a special type is created in Azure AD for the identity. The **service principal** is managed separately from the resources that use it.

##

User-assigned identities can be used by multiple

%

resources

##

When you enable a user-assigned managed identity, you authorize the managed identity to have access to one or more

%

services

##

System-assigned managed identities are created as part of an Azure `_____` (for example, Azure Virtual Machines or Azure App Service)

%


System-assigned managed identities are created as part of an Azure **resource** (for example, Azure Virtual Machines or Azure App Service)

##

User-assigned managed identities created as a stand-alone Azure

%

resource

##

System-assigned managed identities have a shared `_____` with the Azure resource that the managed identity is created with.
When the parent resource is deleted, the managed identity is deleted as well.

%

System-assigned managed identities have a shared **life cycle** with the Azure resource that the managed identity is created with.
When the parent resource is deleted, the managed identity is deleted as well.

##

User-assigned managed identities have an independent `_____`, and must be explicitly deleted.

%

User-assigned managed identities have an independent **life cycle**, and must be explicitly deleted.

##

System-assigned managed identities can't be `_____` across Azure resources.

%

System-assigned managed identities can't be **shared** across Azure resources.

##

The same user-assigned managed identity can be associated with more than one Azure

%

resource

##

Common use cases for a system-assigned managed identity:

- Workloads that are contained within a `_____` Azure resource.
- Workloads for which you need `_____` identities.
- For example, an application that runs on a `_____` virtual machine.

%

- Workloads that are contained within a **single** Azure resource.
- Workloads for which you need **independent** identities.
- For example, an application that runs on a **single** virtual machine.

##

Common use cases for a user-assigned managed identity:


- Workloads that run on multiple resources and can `_____` a single identity.
- Workloads that need `_____`-authorization to a secure resource, as part of a provisioning flow.
- Workloads where resources are `_____` frequently, but permissions should stay consistent.
- For example, a workload where `_____` virtual machines need to access the same resource.

%

- Workloads that run on multiple resources and can **share** a single identity.
- Workloads that need **pre**-authorization to a secure resource, as part of a provisioning flow.
- Workloads where resources are **recycled** frequently, but permissions should stay consistent.
- For example, a workload where **multiple** virtual machines need to access the same resource.

##

You can use managed identities by following the steps below:

1. Create a managed identity in Azure. You can choose between `_____`-assigned managed identity or `_____`-assigned managed identity.
  a. When using a `_____`-assigned managed identity, you assign the managed identity to the "source" Azure Resource, such as a Virtual Machine, Azure Logic App or an Azure Web App.
2. Authorize the managed identity to have access to the "target" `_____`.
3. Use the managed identity to `_____` a resource. In this step, you can use the Azure SDK with the `Azure.Identity` library. Some "source" resources offer connectors that know how to use Managed identities for the connections. In that case, you use the identity as a feature of that "source" resource.

%

1. Create a managed identity in Azure. You can choose between **system**-assigned managed identity or **user**-assigned managed identity.
  a. When using a **user**-assigned managed identity, you assign the managed identity to the "source" Azure Resource, such as a Virtual Machine, Azure Logic App or an Azure Web App.
2. Authorize the managed identity to have access to the "target" **service**.
3. Use the managed identity to **access** a resource. In this step, you can use the Azure SDK with the `Azure.Identity` library. Some "source" resources offer connectors that know how to use Managed identities for the connections. In that case, you use the identity as a feature of that "source" resource.

##

Managed identities for Azure resources can be used to authenticate to services that support

%

Azure AD authentication

##

Resources that support system-assigned managed identities allow you to:

- Enable or disable managed identities at the `_____` level.
- Use `_____` to grant permissions.
- View the create, read, update, and delete (CRUD) operations in Azure `_____` logs.
- View sign in activity in Azure `_____` sign in logs.

%

- Enable or disable managed identities at the **resource** level.
- Use **role-based access control (RBAC)** to grant permissions.
- View the create, read, update, and delete (CRUD) operations in Azure **Activity** logs.
- View sign in activity in Azure **AD** sign in logs.

##

If you choose a user-assigned managed identity instead:

- You can create, read, update, and delete the `_____`.
- You can use `_____` role assignments to grant permissions.
- User assigned managed identities can be used on more than one `_____`.
- CRUD operations are available for review in Azure `_____` logs.
- View sign in activity in Azure `_____` sign in logs.

%

- You can create, read, update, and delete the **identities**.
- You can use **RBAC** role assignments to grant permissions.
- User assigned managed identities can be used on more than one **resource**.
- CRUD operations are available for review in Azure **Activity** logs.
- View sign in activity in Azure **AD** sign in logs.

##

Operations on managed identities can be performed by using

- `_____`
- `_____`
- `_____`
- `_____`
- `_____`

%

- an Azure Resource Manager template
- the Azure portal
- Azure CLI
- PowerShell
- and REST APIs
