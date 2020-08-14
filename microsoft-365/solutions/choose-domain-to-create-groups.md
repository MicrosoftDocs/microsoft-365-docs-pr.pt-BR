---
title: Escolha o domínio a ser usado ao criar grupos do Microsoft 365
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
- Adm_TOC
search.appverid:
- MET150
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
description: Saiba como escolher o domínio a ser usado ao criar grupos do Microsoft 365 Configurando políticas de endereços de email usando o PowerShell.
ms.openlocfilehash: a4bc5bd499652109586c30462d484a12a6cbe876
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662450"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a>Escolha o domínio a ser usado ao criar grupos do Microsoft 365

Algumas organizações usam domínios de email separados para segmentar diferentes partes do negócio. Você pode especificar qual domínio deve ser usado quando os usuários criarem os grupos do Microsoft 365.
  
Se sua organização precisar que os usuários criem seus grupos em domínios diferentes do domínio aceito padrão de sua empresa, você poderá permitir isso Configurando políticas de endereço de email (EAPs) usando o PowerShell.

Antes de poder executar os cmdlets do PowerShell, baixe e instale um módulo que permita que você converse com sua organização. Confira [conectar-se ao Exchange Online usando o PowerShell remoto](https://go.microsoft.com/fwlink/p/?LinkId=785881).

## <a name="example-scenarios"></a>Exemplos de cenários

Digamos que o domínio principal de sua empresa seja o Contoso.com. Mas o domínio aceito por padrão da sua organização é service.contoso.com. Isso significa que os grupos serão criados no service.contoso.com (por exemplo, jimsteam@service.contoso.com).
  
Digamos que você também tenha subdomínios configurados em sua organização. Você também deseja que os grupos sejam criados nesses domínios:
  
- students.contoso.com para estudantes
    
- faculty.contoso.com para membros docentes
    
Os dois cenários a seguir explicam como fazer isso.

> [!NOTE]
> Quando você tem vários EAPs, eles são avaliados na ordem de prioridade. O valor 1 significa a prioridade mais alta. Após a correspondência de um EAP, nenhum EAP adicional é avaliado e os endereços que são marcados no grupo são de acordo com o EAP correspondente. > se nenhum EAPs corresponder aos critérios especificados, o grupo será provisionado no domínio padrão aceito da organização. Confira [gerenciar domínios aceitos no Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428) para obter detalhes sobre como adicionar um domínio aceito.
  
### <a name="scenario-1"></a>Cenário 1

O exemplo a seguir mostra como provisionar todos os grupos da Microsoft 365 em sua organização no domínio groups.contoso.com.
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a>Cenário 2

Digamos que você deseja controlar quais subdomínios os grupos da Microsoft 365 são criados. Você quer:
  
- Grupos criados por alunos (usuários que tenham o **Departamento** configurado para **estudantes**) no domínio students.Groups.contoso.com. Use este comando:
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- Grupos criados por membros professores (usuários que têm o **Departamento** definido como **docente ou endereço de email contém Faculty.contoso.com)**) no domínio Faculty.Groups.contoso.com. Use este comando:
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- Todos os outros usuários no domínio groups.contoso.com. Use este comando:
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a>Alterar políticas de endereço de email

Para alterar a prioridade ou os modelos de endereço de email para um EAP existente, use o cmdlet Set-EmailAddressPolicy.
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

Alterar um EAP não tem impacto nos grupos que já foram provisionados.
  
## <a name="delete-email-address-policies"></a>Excluir políticas de endereço de email

Para excluir um EAP, use o cmdlet Remove-EmailAddressPolicy.
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

Alterar um EAP não tem impacto nos grupos que já foram provisionados.
  
## <a name="hybrid-requirements"></a>Requisitos híbridos

Se sua organização estiver configurada em um cenário híbrido, confira [configurar os grupos do Microsoft 365 com o Exchange híbrido local](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups) para garantir que sua organização atenda aos requisitos para a criação de grupos do Microsoft 365. 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a>Informações adicionais sobre como usar grupos de políticas de endereço de email:

Há mais algumas coisas que você precisa saber:
  
- O modo como os grupos rápidos são criados depende do número de EAPs configurados em sua organização.
    
- Administradores e usuários também podem modificar domínios quando criarem grupos.
    
- O grupo de usuários é determinado usando as consultas padrão (Propriedades do usuário) que já estão disponíveis. Confira [as propriedades filtráveis para o parâmetro-RecipientFilter](https://docs.microsoft.com/powershell/exchange/recipientfilter-properties) para obter as propriedades filtráveis suportadas. 
    
- Se você não configurar nenhum EAPs para grupos, o domínio aceito padrão será selecionado para criação de grupo.
    
- Se você remover um domínio aceito, deverá atualizar o EAPs primeiro, caso contrário, o provisionamento de grupo será afetado.
    
- É possível configurar um limite máximo de 100 políticas de endereço de email para uma organização.
    
## <a name="related-articles"></a>Artigos relacionados

[Criar um grupo do Microsoft 365 no centro de administração](https://docs.microsoft.com/microsoft-365/admin/create-groups/create-groups)
