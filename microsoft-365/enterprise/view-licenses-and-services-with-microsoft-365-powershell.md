---
title: Exibir Microsoft 365 licenças e serviços com o PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- O365ITProTrain
- LIL_Placement
- PowerShell
ms.assetid: bb5260a9-a6a3-4f34-b19a-06c6699f6723
description: Explica como usar o PowerShell para exibir informações sobre os planos de licenciamento, serviços e licenças disponíveis em sua Microsoft 365.
ms.openlocfilehash: 08f48301001ee6a40318428f3310eab8b0d0a351
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924631"
---
# <a name="view-microsoft-365-licenses-and-services-with-powershell"></a>Exibir Microsoft 365 licenças e serviços com o PowerShell

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Cada Microsoft 365 assinatura consiste nos seguintes elementos:

- **Planos de licenciamento** Eles também são conhecidos como planos de licença ou Microsoft 365 planos. Os planos de licenciamento definem os Microsoft 365 que estão disponíveis para os usuários. Sua Microsoft 365 assinatura pode conter vários planos de licenciamento. Um exemplo de plano de licenciamento seria Microsoft 365 E3.
    
- **Serviços** Eles também são conhecidos como planos de serviço. Os serviços são os Microsoft 365, recursos e recursos disponíveis em cada plano de licenciamento, por exemplo, Exchange Online e Microsoft 365 Apps para Grandes Empresas (anteriormente chamado Office 365 ProPlus). Os usuários podem receber várias licenças de diferentes planos de licenciamento que garantem o acesso a diferentes serviços.
    
- **Licenças** Cada plano de licenciamento contém o número de licenças que você comprou. Você atribui licenças aos usuários para que eles possam usar os serviços Microsoft 365 que são definidos pelo plano de licenciamento. Cada conta de usuário requer pelo menos uma licença de um plano de licenciamento para que eles possam fazer logo Microsoft 365 e usar os serviços.
    
Você pode usar o PowerShell para Microsoft 365 para exibir detalhes sobre os planos de licenciamento, licenças e serviços disponíveis em sua Microsoft 365 organização. Para obter mais informações sobre os produtos, recursos e serviços disponíveis em assinaturas Office 365 diferentes, consulte [Office 365 Opções de Plano.](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)


## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Use o PowerShell do Azure Active Directory para o módulo do gráfico

Primeiro, [conecte-se ao seu Microsoft 365 locatário](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
  
Para exibir informações resumidas sobre seus planos de licenciamento atuais e as licenças disponíveis para cada plano, execute este comando:
  
```powershell
Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
```

Os resultados contêm:
  
- **SkuPartNumber:** Mostra os planos de licenciamento disponíveis para sua organização. Por exemplo, `ENTERPRISEPACK` é o nome do plano de licença para Office 365 Enterprise E3.
    
- **Habilitado:** Número de licenças que você comprou para um plano de licenciamento específico.
    
- **ConsumedUnits:** número de licenças que você atribuiu aos usuários de um plano de licenciamento específico.
    
Para exibir detalhes sobre os serviços Microsoft 365 que estão disponíveis em todos os seus planos de licença, primeiro exibe uma lista de seus planos de licença.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Em seguida, armazene as informações dos planos de licença em uma variável.

```powershell
$licenses = Get-AzureADSubscribedSku
```

Em seguida, exibe os serviços em um plano de licença específico.

```powershell
$licenses[<index>].ServicePlans
```

\<index> é um inteiro que especifica o número de linha do plano de licença da exibição do `Get-AzureADSubscribedSku | Select SkuPartNumber` comando, menos 1.

Por exemplo, se a exibição do `Get-AzureADSubscribedSku | Select SkuPartNumber` comando for esta:

```powershell
SkuPartNumber
-------------
WIN10_VDA_E5
EMSPREMIUM
ENTERPRISEPREMIUM
FLOW_FREE
```

Em seguida, o comando para exibir os serviços para o plano de licença ENTERPRISEPREMIUM é este:

```powershell
$licenses[2].ServicePlans
```

ENTERPRISEPREMIUM é a terceira linha. Portanto, o valor do índice é (3 - 1) ou 2.

Para uma lista completa de planos de licença (também conhecidos como nomes de produtos), seus planos de serviço incluídos e seus nomes amigáveis correspondentes, consulte [Product names and service plan identifiers for licensing](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Use o Módulo Microsoft Azure Active Directory para Windows PowerShell.

Primeiro, [conecte-se ao seu Microsoft 365 locatário](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

>[!Note]
>Um script do PowerShell está disponível e automatiza os procedimentos descritos neste tópico. Especificamente, o script permite exibir e desabilitar serviços em sua Microsoft 365, incluindo o Sway. Para obter mais informações, consulte [Disable access to Sway with PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md).
>
    
Para exibir informações resumidas sobre seus planos de licenciamento atuais e as licenças disponíveis para cada plano, execute o seguinte comando:
  
```powershell
Get-MsolAccountSku
```

>[!Note]
>O PowerShell Core não é compatível com o módulo do Microsoft Azure Active Directory para módulo e cmdlets do Windows PowerShell com **MSol** no nome. Para continuar usando esses cmdlets, você deve executá-los a partir do Windows PowerShell.
>

Os resultados contêm as seguintes informações:
  
- **AccountSkuId:** Mostrar os planos de licenciamento disponíveis para sua organização usando a sintaxe `<CompanyName>:<LicensingPlan>` .  _\<CompanyName>_ é o valor que você forneceu ao se inscrever no Microsoft 365 e é exclusivo para sua organização. O _\<LicensingPlan>_ valor é o mesmo para todos. Por exemplo, no valor , o nome da empresa é , e o nome do plano de licenciamento , que é o nome do sistema para Office 365 Enterprise `litwareinc:ENTERPRISEPACK` `litwareinc` `ENTERPRISEPACK` E3.
    
- **ActiveUnits:** Número de licenças que você comprou para um plano de licenciamento específico.
    
- **WarningUnits:** número de licenças em um plano de licenciamento que você não renovou e que expirará após um período de carência de 30 dias.
    
- **ConsumedUnits:** número de licenças que você atribuiu aos usuários de um plano de licenciamento específico.
    
Para exibir detalhes sobre os serviços Microsoft 365 que estão disponíveis em todos os seus planos de licença, execute o seguinte comando:
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

A tabela a seguir mostra os Microsoft 365 de serviço e seus nomes amigáveis para os serviços mais comuns. Sua lista de planos de serviço pode ser diferente. 
  
|**Plano de serviço**|**Descrição**|
|:-----|:-----|
| `SWAY` <br/> |Sway  <br/> |
| `TEAMS1` <br/> |Microsoft Teams  <br/> |
| `YAMMER_ENTERPRISE` <br/> |Yammer  <br/> |
| `RMS_S_ENTERPRISE` <br/> |Azure Rights Management (RMS)  <br/> |
| `OFFICESUBSCRIPTION` <br/> |Microsoft 365 Apps para Grandes Empresas *(anteriormente chamado Office 365 ProPlus)*  <br/> |
| `MCOSTANDARD` <br/> |Skype for Business Online  <br/> |
| `SHAREPOINTWAC` <br/> |Office  <br/> |
| `SHAREPOINTENTERPRISE` <br/> |SharePoint Online  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |Plano 2 do Exchange Online  <br/> |
   
Para uma lista completa de planos de licença (também conhecidos como nomes de produtos), seus planos de serviço incluídos e seus nomes amigáveis correspondentes, consulte [Product names and service plan identifiers for licensing](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).

Para exibir detalhes sobre os serviços Microsoft 365 que estão disponíveis em um plano de licenciamento específico, use a sintaxe a seguir.
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```

Este exemplo mostra os serviços disponíveis no plano de licenciamento litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3).
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "litwareinc:ENTERPRISEPACK"}).ServiceStatus
```

## <a name="see-also"></a>Confira também

[Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Gerenciar o Microsoft 365 com o PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introdução ao PowerShell para o Microsoft 365](getting-started-with-microsoft-365-powershell.md)