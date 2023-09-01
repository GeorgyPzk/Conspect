# Tenant

Tenant - combines several subscriptions and can manage them. Usually used by the client to control costs.

# Role assignment

## RBAC

Service for role assignments to subscriptions, resource groups, etc. Can be assigned by code. Can be assigned in Azure Active Directory -> Users. Assigned with role assignment.

### IAM (Azure Identity and Access Management Solutions)

RBAC Substance - adds roles to RBAC users directly in resource groups

Security principal - some Substance (user, group, service principal, managed identity) which you can assign rights(role assignments).

#### Managed Identity (MI)

Managed Identity (MI) - substanse for authentication in Azure AD. Provide an automatically managed identity in Azure Active Directory (Azure AD) for applications to use when connecting to resources that support Azure AD authentication.

Two types of managed identities exist:

- System-assigned - can be associated with a signe Azure resourses
- User-assigned - can be associated with a multiple Azure resourses. Created For AKS

# NSG(Network security group)

NSG - cloud level firewall.