# Role assignment

## RBAC

Служба для назначения ролей(role assignments) подпискам ресурсным группам и тд. Можно назначить кодом. Можно назначить в Azure Active Directory -> Users. Назначается с помощью role assignment.

### IAM (Azure Identity and Access Management Solutions)

Сущность(Substance) из RBAC добавляет роли пользователям из RBAC роли непостредственно в ресурсных группах

Service principal - какая то сущность(user, group, service principal, managed identity), котрой(Which) ты можешь выдать права.\

#### Managed Identity (MI)

Managed Identity (MI) - сущьность позволяет автоматически аутентифицироваться в Azure Active Directory. предоставление автоматически управляемого удостоверения в Azure Active Directory (Azure AD) для использования приложениями при подключении к ресурсам, поддерживающим проверку подлинности Azure AD.

Существует два типа:

- System-assigned - can be associated with a signe Azure resourses
- User-assigned - can be associated with a multiple Azure resourses. Создается для AKS кластера.
# VPS 

Virtual Private Cloud (VPC) — понятие для AWS. В Azure это просто настройка network(локальной сети и security rule к ней)

__Что такое cloud-init? init/systemd/upstart configs?__ - это не спросят

Могут спросить могут: "Можно ли преднастроить VM перед запуском(скриптом)?".
Можно, добавив скрипт в какой то extantion.
