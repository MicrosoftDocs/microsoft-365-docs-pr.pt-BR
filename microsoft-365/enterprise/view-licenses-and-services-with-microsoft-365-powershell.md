---
title: Exibir licenças e serviços do Microsoft 365 com o PowerShell
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
description: Explica como usar o PowerShell para exibir informações sobre os planos de licenciamento, serviços e licenças disponíveis na sua organização do Microsoft 365.
ms.openlocfilehash: 3275a513de3c114076e792ab6c5ef86b1413571c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687160"
---
# <a name="view-microsoft-365-licenses-and-services-with-powershell"></a>Exibir licenças e serviços do Microsoft 365 com o PowerShell

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Cada assinatura do Microsoft 365 consiste nos seguintes elementos:

- **Planos de licenciamento** Eles também são conhecidos como planos de licença ou planos do Microsoft 365. Os planos de licenciamento definem os serviços do Microsoft 365 que estão disponíveis para os usuários. Sua assinatura do Microsoft 365 pode conter vários planos de licenciamento. Um plano de licenciamento de exemplo seria o Microsoft 365 E3.
    
- **Serviços** do Eles também são conhecidos como planos de serviço. Os serviços são os produtos, recursos e recursos do Microsoft 365 que estão disponíveis em cada plano de licenciamento, por exemplo, Exchange Online e Microsoft 365 aplicativos para empresas (anteriormente denominado Office 365 ProPlus). Os usuários podem receber várias licenças de diferentes planos de licenciamento que garantem o acesso a diferentes serviços.
    
- **Licenças** do Cada plano de licenciamento contém o número de licenças que você comprou. Você atribui licenças aos usuários para que eles possam usar os serviços do Microsoft 365 definidos pelo plano de licenciamento. Cada conta de usuário requer pelo menos uma licença de um plano de licenciamento para que possa fazer logon no Microsoft 365 e usar os serviços.
    
Você pode usar o PowerShell para Microsoft 365 para exibir detalhes sobre os planos de licenciamento, licenças e serviços disponíveis na sua organização do Microsoft 365. Para obter mais informações sobre os produtos, recursos e serviços que estão disponíveis em assinaturas diferentes do Office 365, confira [Opções de plano do office 365](https://go.microsoft.com/fwlink/p/?LinkId=691147).


## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Use o PowerShell do Azure Active Directory para o módulo do gráfico

Primeiro, [Conecte-se ao seu locatário do Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
  
Para exibir informações resumidas sobre seus planos de licenciamento atuais e as licenças disponíveis para cada plano, execute este comando:
  
```powershell
Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
```

Os resultados contêm:
  
- **SkuPartNumber:** Mostra os planos de licenciamento disponíveis para sua organização. Por exemplo, `ENTERPRISEPACK` é o nome do plano de licença para o Office 365 Enterprise E3.
    
- **Habilitado:** Número de licenças que você comprou para um plano de licenciamento específico.
    
- **ConsumedUnits:** número de licenças que você atribuiu aos usuários de um plano de licenciamento específico.
    
Para exibir detalhes sobre os serviços do Microsoft 365 que estão disponíveis em todos os seus planos de licença, primeiro exiba uma lista de seus planos de licença.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Em seguida, armazene as informações dos planos de licença em uma variável.

```powershell
$licenses = Get-AzureADSubscribedSku
```

Em seguida, exiba os serviços em um plano de licença específico.

```powershell
$licenses[<index>].ServicePlans
```

\<index> é um inteiro que especifica o número da linha do plano de licença a partir da exibição do `Get-AzureADSubscribedSku | Select SkuPartNumber` comando, menos 1.

Por exemplo, se a exibição do `Get-AzureADSubscribedSku | Select SkuPartNumber` comando for:

```powershell
SkuPartNumber
-------------
WIN10_VDA_E5
EMSPREMIUM
ENTERPRISEPREMIUM
FLOW_FREE
```

Em seguida, o comando para exibir os serviços do plano de licença do ENTERPRISEPREMIUM é:

```powershell
$licenses[2].ServicePlans
```

ENTERPRISEPREMIUM é a terceira linha. Portanto, o valor de índice é (3-1) ou 2.

Para obter uma lista completa de planos de licença (também conhecidos como nomes de produtos), seus planos de serviço incluídos e seus nomes amigáveis correspondentes, confira [nomes de produtos e identificadores de planos de serviço para licenciamento](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Use o Módulo Microsoft Azure Active Directory para Windows PowerShell.

Primeiro, [Conecte-se ao seu locatário do Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

>[!Note]
>Um script do PowerShell está disponível e automatiza os procedimentos descritos neste tópico. Especificamente, o script permite que você exiba e desabilite serviços na sua organização do Microsoft 365, incluindo Sway. Confira mais informações em [desabilitar o acesso ao Sway com o PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md).
>
    
Para exibir informações resumidas sobre seus planos de licenciamento atuais e as licenças disponíveis para cada plano, execute o seguinte comando:
  
```powershell
Get-MsolAccountSku
```

>[!Note]
>O PowerShell Core não é compatível com o módulo do Microsoft Azure Active Directory para módulo e cmdlets do Windows PowerShell com **MSol** no nome. Para continuar usando esses cmdlets, você deve executá-los a partir do Windows PowerShell.
>

Os resultados contêm as seguintes informações:
  
- **AccountSkuId:** Mostre os planos de licenciamento disponíveis para sua organização usando a sintaxe `<CompanyName>:<LicensingPlan>` .  _\<CompanyName>_ é o valor que você forneceu quando registrou no Microsoft 365 e é exclusivo para sua organização. O _\<LicensingPlan>_ valor é o mesmo para todos. Por exemplo, no valor `litwareinc:ENTERPRISEPACK` , o nome da empresa é  `litwareinc` e o nome do plano de licenciamento  `ENTERPRISEPACK` , que é o nome do sistema do Office 365 Enterprise E3.
    
- **ActiveUnits:** Número de licenças que você comprou para um plano de licenciamento específico.
    
- **WarningUnits:** número de licenças em um plano de licenciamento que você não renovou e que expirará após um período de carência de 30 dias.
    
- **ConsumedUnits:** número de licenças que você atribuiu aos usuários de um plano de licenciamento específico.
    
Para exibir detalhes sobre os serviços do Microsoft 365 que estão disponíveis em todos os seus planos de licença, execute o seguinte comando:
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

A tabela a seguir mostra os planos de serviço do Microsoft 365 e seus nomes amigáveis para os serviços mais comuns. Sua lista de planos de serviço pode ser diferente. 
  
|**Plano de serviço**|**Descrição**|
|:-----|:-----|
| `SWAY` <br/> |Sway  <br/> |
| `TEAMS1` <br/> |Microsoft Teams  <br/> |
| `YAMMER_ENTERPRISE` <br/> |Yammer  <br/> |
| `RMS_S_ENTERPRISE` <br/> |Azure Rights Management (RMS)  <br/> |
| `OFFICESUBSCRIPTION` <br/> |Microsoft 365 Apps for Enterprise *(anteriormente chamado Office 365 ProPlus)*  <br/> |
| `MCOSTANDARD` <br/> |Skype for Business Online  <br/> |
| `SHAREPOINTWAC` <br/> |Office  <br/> |
| `SHAREPOINTENTERPRISE` <br/> |SharePoint Online  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |Plano 2 do Exchange Online  <br/> |
   
Para obter uma lista completa de planos de licença (também conhecidos como nomes de produtos), seus planos de serviço incluídos e seus nomes amigáveis correspondentes, confira [nomes de produtos e identificadores de planos de serviço para licenciamento](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).

Para exibir detalhes sobre os serviços do Microsoft 365 que estão disponíveis em um plano de licenciamento específico, use a sintaxe a seguir.
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```

Este exemplo mostra os serviços que estão disponíveis no plano de licenciamento do litwareinc: ENTERPRISEPACK (Office 365 Enterprise E3).
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "litwareinc:ENTERPRISEPACK"}).ServiceStatus
```

## <a name="see-also"></a>Confira também

[Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Gerenciar o Microsoft 365 com o PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introdução ao PowerShell para o Microsoft 365](getting-started-with-microsoft-365-powershell.md)
