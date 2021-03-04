---
title: Alterar a duração do bloqueio para uma caixa de correio inativa
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/29/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: bdee24ed-b8cf-4dd0-92ae-b86ec4661e6b
ms.custom:
- seo-marvel-apr2020
description: Depois que uma caixa de correio do Office 365 for inativa, altere a duração da retenção ou da política de retenção do Office 365 atribuída à caixa de correio inativa.
ms.openlocfilehash: ec8a4cac7d2ee8e40bd791bd531556d1151c1ad1
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421630"
---
# <a name="change-the-hold-duration-for-an-inactive-mailbox"></a>Alterar a duração do bloqueio para uma caixa de correio inativa

Uma caixa de correio inativa é usada para reter o email de um ex-funcionário depois que ele sai da sua organização. Uma caixa de correio fica inativa quando uma Retenção de Litígio, uma retenção de In-Place, uma política de retenção do Microsoft 365 ou uma retenção associada a um caso de Descoberta Eletrônico é colocada na caixa de correio e a conta de usuário correspondente é excluída. O conteúdo de uma caixa de correio inativa é mantido durante a espera que foi colocada na caixa de correio antes de ser inativa. A duração da espera define por quanto tempo os itens na pasta Itens Recuperáveis são mantidos. Quando a duração de espera expira para um item na pasta Itens Recuperáveis, o item é excluído permanentemente (apagado) da caixa de correio inativa. Depois que uma caixa de correio é inativa, você pode alterar a duração da retenção ou da política de retenção do Microsoft 365 atribuída à caixa de correio inativa.
  
> [!IMPORTANT]
> À medida que continuamos a investir em diferentes maneiras de preservar o conteúdo da caixa de correio, anunciamos a ress contração de In-Place no Centro de administração do Exchange. Isso significa que você deve usar retenção de litígio e políticas de retenção do Microsoft 365 para criar uma caixa de correio inativa. A partir de 1º de abril de 2020, você não poderá criar novos In-Place no Exchange Online. Mas você ainda poderá alterar a duração de espera de uma In-Place de espera colocada em uma caixa de correio inativa. No entanto, a partir de 1º de julho de 2020, você não poderá alterar a duração da espera. Você só poderá excluir uma caixa de correio inativa removendo o In-Place Hold. As caixas de correio inativas existentes que estão em In-Place de espera ainda serão preservadas até que a espera seja removida. Para obter mais informações sobre a aposentadoria de In-Place Detém, consulte A aposentadoria de ferramentas [de Descoberta eDiscovery herdado.](legacy-ediscovery-retirement.md)
  
## <a name="connect-to-powershell"></a>Conectar-se ao PowerShell

- Você precisa usar o PowerShell do Exchange Online para alterar a duração da responsabilidade de uma Responsabilidade de Litígio em uma caixa de correio inativa. Você não pode usar o Centro de Administração do Exchange (EAC). Mas você pode usar o PowerShell do Exchange Online ou o EAC para alterar a duração de espera para uma In-Place de espera. Você pode usar o centro de & conformidade e segurança ou o Centro de Conformidade e Segurança do PowerShell para alterar a duração de retenção de uma política de retenção do Microsoft 365.
    
- Para se conectar ao PowerShell do Exchange Online ou ao Centro de Conformidade & e Segurança do PowerShell, consulte um dos seguintes tópicos:
    
  - [Conectar-se ao PowerShell do Exchange Online ](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)
    
  - [Conectar-se ao PowerShell do Centro de Conformidade e Segurança](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)
    
- Os ressamentos associados a casos de Descoberta e São retém infinitos, o que significa que não há nenhuma duração de espera que pode ser alterada. Os itens são mantidos para sempre ou até que a espera seja removida e a caixa de correio inativa seja excluída.
    
- Para obter mais informações sobre caixas de correio inativas, consulte Caixas de correio [inativas no Microsoft 365](inactive-mailboxes-in-office-365.md).
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>Etapa 1: identificar os retém em uma caixa de correio inativa

Como diferentes tipos de retenção ou uma ou mais políticas de retenção do Microsoft 365 podem ser colocadas em uma caixa de correio inativa, a primeira etapa é identificar os retenções em uma caixa de correio inativa.
  
Execute o seguinte comando no PowerShell do Exchange Online para exibir as informações de espera para todas as caixas de correio inativas em sua organização.
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,InPlaceHolds
```

O valor **true para** a propriedade **LitigationHoldEnabled** indica que a caixa de correio inativa está em Contencioso. Se uma In-Place de retenção de In-Place, a retenção de Descoberta Eletrônico ou a política de retenção do Microsoft 365 for colocada em uma caixa de correio inativa, um GUID para a política de retenção ou retenção será exibido como o valor da propriedade **InPlaceHolds.** Por exemplo, o seguinte mostra os resultados de cinco caixas de correio inativas. 
  
```text
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
LitigationHoldDuration: 365.00:00:00
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491}
...
DisplayName           : Mario Necaise
Name                  : marion
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {}
...
DisplayName           : Carol Olson
Name                  : carolo
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {mbxcdbbb86ce60342489bff371876e7f224}
...
DisplayName           : Abraham McMahon
Name                  : abrahamm
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {UniH7d895d48-7e23-4a8d-8346-533c3beac15d}
```

A tabela a seguir identifica os cinco tipos de espera diferentes que foram usados para tornar cada caixa de correio inativa.
  
|**Caixa de correio inativa**|**Tipo de espera**|**Como identificar a espera na caixa de correio inativa**|
|:-----|:-----|:-----|
|Ann Beebe  <br/> |Retenção de litígio  <br/> |A  *propriedade LitigationHoldEnabled*  está definida como  `True` .  <br/> |
|Pilar Pinilla  <br/> |Bloqueio In-loco  <br/> |A  *propriedade InPlaceHolds*  contém o GUID do In-Place que é colocado na caixa de correio inativa. Você pode dizer que é um In-Place de espera porque a ID não começa com um prefixo.  <br/> Você pode usar o comando no PowerShell do Exchange Online para obter informações sobre o In-Place na caixa de correio  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` inativa.  <br/> |
|Mário Necaise  <br/> |Política de retenção do Microsoft 365 em toda a organização no Centro de Conformidade & Segurança  <br/> |A  *propriedade InPlaceHolds*  está vazia. Isso indica que uma ou mais políticas de retenção do Microsoft 365 em toda a organização ou (em toda a exchange) são aplicadas à caixa de correio inativa. Nesse caso, você pode executar o comando no PowerShell do Exchange Online para obter uma lista dos GUIDs para políticas de retenção do Microsoft 365 em toda  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` a organização. O GUID para políticas de retenção em toda a organização que são aplicadas às caixas de correio do Exchange começa com o  `mbx` prefixo; por exemplo,  `mbxa3056bb15562480fadb46ce523ff7b02` .  <br/> <br/>Para identificar a política de retenção do Microsoft 365 aplicada à caixa de correio inativa, execute o seguinte comando no Centro de Conformidade e Segurança & do PowerShell.  <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>
|Carol Olson  <br/> |Política de retenção do Microsoft 365 no Centro de Conformidade & segurança aplicado a caixas de correio específicas  <br/> |A  *propriedade InPlaceHolds*  contém o GUID da política de retenção do Microsoft 365 aplicada à caixa de correio inativa. Você pode dizer que essa é uma política de retenção aplicada a caixas de correio específicas porque o GUID começa com o  `mbx` prefixo. Se o GUID da política de retenção aplicada à caixa de correio inativa tiver sido iniciado com o prefixo, indicará que a política de retenção é aplicada às  `skp` conversas do Skype for Business.  <br/><br/> Para identificar a política de retenção do Microsoft 365 aplicada à caixa de correio inativa, execute o seguinte comando no Centro de Conformidade e Segurança & do PowerShell.<br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name` <br/><br/>Certifique-se de remover  `mbx` o prefixo ou  `skp` ao executar este comando.  <br/> |
|Abraão McMahon  <br/> |Responsabilidade de caso de Descoberta Digital no Centro de Conformidade & Segurança  <br/> |A  *propriedade InPlaceHolds*  contém o GUID do caso de descoberta eletrônico que é colocado na caixa de correio inativa. Você pode dizer que se trata de um caso de descoberta de eDiscovery, pois o GUID começa com o  `UniH` prefixo.  <br/> Você pode usar o cmd & let no Centro de Conformidade e Segurança do PowerShell para obter informações sobre o caso de Descoberta Eletrônica ao que a espera na caixa de correio inativa está  `Get-CaseHoldPolicy` associada. Por exemplo, você pode executar o comando para exibir o nome da caixa de espera que  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` está na caixa de correio inativa. Certifique-se de remover  `UniH` o prefixo ao executar este comando.  <br/><br/> Para identificar o caso de Descoberta Eletrônico ao que a espera na caixa de correio inativa está associada, execute os comandos a seguir.  <br/><br/> `$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/> `Get-ComplianceCase $CaseHold.CaseId | FL Name`<br/><br/><br/> **Observação:** Não recomendamos o uso de retém de Descoberta Eletrônico para caixas de correio inativas. That's because eDiscovery cases are intended for specific, time-bound cases related to a legal issue. Em algum momento, um caso jurídico provavelmente terminará, e as restituições associadas ao caso serão removidas e o caso de Descoberta De eDiscovery será fechado (ou excluído). Na verdade, se uma responsabilidade colocada em uma caixa de correio inativa estiver associada a um caso de Descoberta Eletrônico e a responsabilidade for liberada ou o caso de Descoberta Eletrônico for fechado ou excluído, a caixa de correio inativa será excluída permanentemente. 

Para obter mais informações sobre políticas de retenção do Microsoft 365, [consulte Saiba mais sobre políticas de retenção e rótulos de retenção.](retention.md)
  
## <a name="step-2-change-the-hold-duration-for-an-inactive-mailbox"></a>Etapa 2: Alterar a duração da espera para uma caixa de correio inativa

Depois de identificar qual tipo de espera é colocada na caixa de correio inativa (e se há várias resituções), a próxima etapa é alterar a duração da espera. 
  
### <a name="change-the-duration-for-a-litigation-hold"></a>Alterar a duração de uma responsabilidade por litígio

Veja como usar o PowerShell do Exchange Online para alterar a duração de espera de uma Responsabilidade de Litígio que é colocada em uma caixa de correio inativa. Não é possível usar o EAC. Execute o seguinte comando para alterar a duração da espera. Neste exemplo, a duração da espera é alterada para um período ilimitado de tempo.
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldDuration unlimited
```

O resultado é que os itens na caixa de correio inativa são mantidos indefinidamente ou até que a espera seja removida ou a duração da espera seja alterada para um valor diferente.
  
> [!TIP]
> A melhor maneira de identificar uma caixa de correio inativa é usando seu **valor Distinguished Name** ou GUID do **Exchange.** Usar um desses valores ajuda a evitar a especificação acidental da caixa de correio errada. 
  
### <a name="change-the-duration-for-an-in-place-hold"></a>Alterar a duração de um In-Place Hold

 In-Place os retém foram retirados e não podem mais ser modificados. Se uma caixa de correio inativa tiver uma In-Place de espera aplicada a ela, você não poderá alterar a duração da espera. Você só pode remover o In-Place, o que resultará na exclusão da caixa de correio inativa. Para obter mais informações, consulte [Excluir uma caixa de correio inativa](delete-an-inactive-mailbox.md#remove-in-place-holds).
  
## <a name="more-information"></a>Mais informações

- **Como a duração de espera é calculada para um item em uma caixa de correio inativa?** A duração é calculada a partir da data original em que um item de caixa de correio foi recebido ou criado. 
    
- **O que acontece quando a duração da espera expirar?** Quando a duração de espera expira para um item de caixa de correio na pasta Itens Recuperáveis, o item é excluído permanentemente (apagado) da caixa de correio inativa. Se não houver nenhuma duração especificada para a espera colocada na caixa de correio inativa, os itens na pasta Itens Recuperáveis nunca serão limpos (a menos que a duração da espera da caixa de correio inativa seja alterada). 
    
- **Uma política de retenção do Exchange ainda é processada em caixas de correio inativas?** Se uma política de retenção do Exchange (o gerenciamento de registros de mensagens ou o recurso MRM no Exchange Online) foi aplicada a uma caixa de correio quando ela foi inativa, as políticas de exclusão (que são marcas de retenção configuradas com uma ação Excluir retenção) continuarão **a** ser processadas na caixa de correio inativa. Isso significa que os itens marcados com uma política de exclusão são movidos para a pasta Itens Recuperáveis quando o período de retenção expira. Esses itens são então limpos da caixa de correio inativa quando a duração de espera de um item expira. 
    
    Por outro lado, quaisquer políticas de arquivamento (que são marcas de retenção configuradas com uma ação de retenção **MoveToArchive** ) que estão incluídas na política de retenção atribuída a uma caixa de correio inativa serão ignoradas. Isso significa que os itens em uma caixa de correio inativa marcada com uma política de arquivo morto permanecem na caixa de correio principal quando o período de retenção expira. Elas não serão movidas para a caixa de correio de arquivo morto ou para a pasta itens recuperáveis na caixa de correio de arquivo morto. Como um usuário não pode entrar em uma caixa de correio inativa, não há motivo para consumir recursos do datacenter para processar políticas de arquivo morto. 

- **Para verificar a nova duração de espera para uma Responsabilidade de Litígio, execute os seguintes comandos** 

   ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | FL LitigationHoldDuration
    ```

- **Como caixas de correio regulares, o Assistente de Pasta Gerenciada (MFA) também processa caixas de correio inativas.** No Exchange Online, o MFA processa caixas de correio aproximadamente uma vez a cada sete dias. Depois de alterar a duração de espera de uma caixa de correio inativa, você pode usar o cmdlet **Start-ManagedFolderAssistant** para começar imediatamente a processar a nova duração de espera para a caixa de correio inativa. Execute o seguinte comando. 

    ```powershell
    Start-ManagedFolderAssistant -InactiveMailbox <identity of inactive mailbox>
    ```
   
- **Se muitos retém são colocados em uma caixa de correio inativa, nem todos os GUIDs de espera serão exibidos.** Você pode executar o seguinte comando para exibir os GUIDs de todas as resitâncias (exceto Ressarções de Litígio) que são colocadas em uma caixa de correio inativa. 
    
    ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds
    ```
