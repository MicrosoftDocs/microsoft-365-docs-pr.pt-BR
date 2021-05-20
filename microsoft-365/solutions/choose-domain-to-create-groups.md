---
title: Escolha o domínio a ser usado ao criar Microsoft 365 grupos
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
recommendations: false
description: Aprenda a escolher o domínio a ser usado ao criar grupos Microsoft 365 configurando políticas de endereço de email usando o PowerShell.
ms.openlocfilehash: 4d620c3344f83f56afd05c00d78615331dd413ed
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583143"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a>Escolha o domínio a ser usado ao criar Microsoft 365 grupos

Algumas organizações usam domínios de email separados para segmentar diferentes partes do negócio. Você pode especificar qual domínio deve ser usado quando seus usuários criarem Microsoft 365 grupos.
  
Se sua organização precisar que os usuários criem seus grupos em domínios diferentes do domínio aceito padrão da sua empresa, você poderá permitir isso configurando as políticas de endereço de email (EAPs) usando o PowerShell.

Antes de executar os cmdlets do PowerShell, baixe e instale um módulo que permitirá que você fale com sua organização. Confira o [Conexão para Exchange Online usando o PowerShell remoto.](/powershell/exchange/connect-to-exchange-online-powershell)

## <a name="example-scenarios"></a>Exemplos de cenários

Digamos que o domínio principal da sua empresa seja Contoso.com. Mas o domínio aceito padrão da sua organização é service.contoso.com. Isso significa que os grupos serão criados service.contoso.com (por exemplo, jimsteam@service.contoso.com).
  
Digamos que você também tenha sub-domínios configurados em sua organização. Você também deseja que grupos sejam criados nesses domínios:
  
- students.contoso.com para alunos
    
- faculty.contoso.com para membros do corpo docente
    
Os dois cenários a seguir explicam como você faria isso.

> [!NOTE]
> Quando você tem EAPs mulitple, eles são avaliados na ordem de prioridade. Um valor 1 significa a prioridade mais alta. Depois que um EAP corresponder, nenhum EAP posterior é avaliado e os endereços que são carimbados no grupo são conforme o EAP coincidente. > Se nenhum EAPs corresponder aos critérios especificados, o grupo será provisionado no domínio aceito padrão da organização. Confira [Gerenciar domínios aceitos Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) para obter detalhes sobre como adicionar um domínio aceito.
  
### <a name="scenario-1"></a>Cenário 1

O exemplo a seguir mostra como provisionar todos os grupos Microsoft 365 em sua organização no groups.contoso.com domínio.
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a>Cenário 2

Digamos que você queira controlar em quais sub-domínios Microsoft 365 grupos são criados. Você quer:
  
- Grupos criados por alunos (usuários que têm **o Departamento** definido como **Alunos**) no students.groups.contoso.com domínio. Use este comando:
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- Grupos criados por membros do  corpo docente (usuários que têm Departamento definido como Docente ou endereço de email contém **faculty.contoso.com)**) no domínio faculty.groups.contoso.com. Use este comando:
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- Os grupos criados por qualquer outra pessoa são criados no groups.contoso.com domínio. Use este comando:
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a>Alterar políticas de endereço de email

Para alterar a prioridade ou os modelos de endereço de email de um EAP existente, use o cmdlet Set-EmailAddressPolicy de email.
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

Alterar um EAP não afeta os grupos que já foram provisionados.
  
## <a name="delete-email-address-policies"></a>Excluir políticas de endereço de email

Para excluir um EAP, use o Remove-EmailAddressPolicy cmdlet.
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

Alterar um EAP não afeta os grupos que já foram provisionados.
  
## <a name="hybrid-requirements"></a>Requisitos híbridos

Se sua organização estiver configurada em um cenário híbrido, confira Configure Microsoft 365 groups with [on-premises Exchange hybrid](/exchange/hybrid-deployment/set-up-microsoft-365-groups) para garantir que sua organização atenda aos requisitos para criar grupos Microsoft 365 locais. 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a>Informações adicionais sobre como usar grupos de políticas de endereço de email:

Há mais algumas coisas a saber:
  
- A rapidez com que os grupos são criados depende do número de EAPs configurados em sua organização.
    
- Os administradores e usuários também podem modificar domínios quando criam grupos.
    
- O grupo de usuários é determinado usando as consultas padrão (propriedades do usuário) que já estão disponíveis. Confira Propriedades [filtáveis para o parâmetro -RecipientFilter](/powershell/exchange/recipientfilter-properties) para propriedades filtáveis com suporte. 
    
- Se você não configurar nenhum EAPs para grupos, o domínio aceito padrão será selecionado para criação de grupo.
    
- Se você remover um domínio aceito, atualize os EAPs primeiro, caso contrário, o provisionamento de grupo será afetado.
    
- Um limite máximo de 100 políticas de endereço de email pode ser configurado para uma organização.
    
## <a name="related-content"></a>Conteúdo relacionado

[Planejamento de governança de colaboração passo a passo](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step) (artigo)

[Criar seu plano de governança de colaboração](collaboration-governance-first.md) (artigo)

[Criar um Microsoft 365 no centro de administração](../admin/create-groups/create-groups.md) (artigo)