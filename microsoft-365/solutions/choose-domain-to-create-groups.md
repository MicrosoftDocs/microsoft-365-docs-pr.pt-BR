---
title: Escolher o domínio a ser usado ao criar grupos do Microsoft 365
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
description: Saiba como escolher o domínio a ser usado ao criar grupos do Microsoft 365 configurando políticas de endereço de email usando o PowerShell.
ms.openlocfilehash: 1e56268c3994b1ac822869d154be826326039bfc
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49612935"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a>Escolher o domínio a ser usado ao criar grupos do Microsoft 365

Algumas organizações usam domínios de email separados para segmentar diferentes partes do negócio. Você pode especificar qual domínio deve ser usado quando os usuários criarem grupos do Microsoft 365.
  
Se sua organização precisa que os usuários criem seus grupos em domínios diferentes do domínio aceito padrão da sua empresa, você pode permitir isso configurando políticas de endereço de email (EAPs) usando o PowerShell.

Antes de executar os cmdlets do PowerShell, baixe e instale um módulo que permitirá que você converse com sua organização. Confira [Conectar-se ao Exchange Online usando o PowerShell remoto.](https://go.microsoft.com/fwlink/p/?LinkId=785881)

## <a name="example-scenarios"></a>Exemplos de cenários

Digamos que o domínio principal da sua empresa seja Contoso.com. Mas o domínio aceito padrão da sua organização é service.contoso.com. Isso significa que os grupos serão criados service.contoso.com (por exemplo, jimsteam@service.contoso.com).
  
Digamos que você também tenha sub-domínios configurados em sua organização. Você também deseja que os grupos sejam criados nesses domínios:
  
- students.contoso.com para alunos
    
- faculty.contoso.com para membros do corpo docente
    
Os dois cenários a seguir explicam como você faria isso.

> [!NOTE]
> Quando você tem EAPs de exemplo, eles são avaliados na ordem de prioridade. Um valor 1 significa a prioridade mais alta. Depois que um EAP corresponde, nenhum EAP é avaliado e os endereços que são carimbados no grupo são de acordo com o EAP coincidente. > Se nenhum EAPs corresponder aos critérios especificados, o grupo será provisionado no domínio aceito padrão da organização. Confira Gerenciar [domínios aceitos no Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428) para obter detalhes sobre como adicionar um domínio aceito.
  
### <a name="scenario-1"></a>Cenário 1

O exemplo a seguir mostra como provisionar todos os grupos do Microsoft 365 em sua organização no groups.contoso.com domínio.
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a>Cenário 2

Digamos que você queira controlar em quais sub-domínios os grupos do Microsoft 365 são criados. Você deseja:
  
- Grupos criados por alunos (usuários que têm **o Departamento** definido como **Alunos)** no students.groups.contoso.com domínio. Use este comando:
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- Grupos criados por membros do  corpo docente (usuários que têm Departamento definido como Docente ou endereço de **email contém faculty.contoso.com)**) no faculty.groups.contoso.com domínio. Use este comando:
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- Grupos criados por qualquer outra pessoa são criados no groups.contoso.com domínio. Use este comando:
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a>Alterar políticas de endereço de email

Para alterar a prioridade ou os modelos de endereço de email de um EAP existente, use o cmdlet Set-EmailAddressPolicy email.
  
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

Se sua organização estiver configurada em um cenário híbrido, confira Configurar grupos do [Microsoft 365](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups) com o Exchange híbrido local para garantir que sua organização atenda aos requisitos para a criação de grupos do Microsoft 365. 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a>Informações adicionais sobre como usar grupos de políticas de endereço de email:

Há mais algumas coisas a saber:
  
- A rapidez com que os grupos são criados depende do número de EAPs configurados em sua organização.
    
- Os administradores e usuários também podem modificar domínios ao criar grupos.
    
- O grupo de usuários é determinado usando as consultas padrão (Propriedades do usuário) que já estão disponíveis. Confira as [propriedades filtáveis do parâmetro -RecipientFilter para](https://docs.microsoft.com/powershell/exchange/recipientfilter-properties) as propriedades filtáveis com suporte. 
    
- Se você não configurar nenhum EAPs para grupos, o domínio aceito padrão será selecionado para a criação do grupo.
    
- Se você remover um domínio aceito, deverá atualizar os EAPs primeiro, caso contrário, o provisionamento de grupo será afetado.
    
- Um limite máximo de 100 políticas de endereço de email pode ser configurado para uma organização.
    
## <a name="related-articles"></a>Artigos relacionados

[Planejamento de governança de colaboração passo a passo](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Criar seu plano de governança de colaboração](collaboration-governance-first.md)

[Criar um grupo do Microsoft 365 no centro de administração](https://docs.microsoft.com/microsoft-365/admin/create-groups/create-groups)
