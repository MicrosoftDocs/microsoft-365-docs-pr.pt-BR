---
title: Atribuir políticas do Skype for Business online por usuário com o PowerShell para o Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/16/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: 36743c86-46c2-46be-b9ed-ad9d4e85d186
description: 'Resumo: Use o PowerShell para Microsoft 365 para atribuir configurações de comunicação por usuário com as políticas do Skype for Business online.'
ms.openlocfilehash: 6ff9fce3e0287313f6725b370b6ba89cb939eb3a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687163"
---
# <a name="assign-per-user-skype-for-business-online-policies-with-powershell-for-microsoft-365"></a>Atribuir políticas do Skype for Business online por usuário com o PowerShell para o Microsoft 365

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

O uso do PowerShell para Microsoft 365 é uma maneira eficiente de atribuir configurações de comunicação por usuário com as políticas do Skype for Business online.
  
## <a name="prepare-to-run-the-powershell-commands"></a>Preparar para executar os comandos do PowerShell

Use estas instruções para configurar a execução dos comandos (pule as etapas que você já concluiu):
  
1. Baixe e instale o [módulo do conector do Skype for Business online](https://www.microsoft.com/download/details.aspx?id=39366).
    
2. Abra um prompt de comando do Windows PowerShell e execute os seguintes comandos: 
    
```powershell
Import-Module LyncOnlineConnector
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

Quando solicitado, insira o nome da conta e a senha do administrador do Skype for Business online.
    
## <a name="updating-external-communication-settings-for-a-user-account"></a>Atualizando configurações de comunicação externa para uma conta de usuário

Suponha que você queira alterar as configurações de comunicação externa em uma conta de usuário. Por exemplo, você deseja permitir que Alex se comunique com usuários federados (EnableFederationAccess é igual a true), mas não com usuários do Windows Live (EnablePublicCloudAccess é igual a false). Para fazer isso, você precisa fazer duas coisas:
  
1. Localizar uma política de acesso externo que atenda aos nossos critérios.
    
2. Atribuir essa política de acesso externo a Antônio.
    
Como determinar qual política de acesso externo atribuirá a Alex? O comando a seguir retorna todas as políticas de acesso externo em que EnableFederationAccess é definido como True e EnablePublicCloudAccess como False:
  
```powershell
Get-CsExternalAccessPolicy -Include All| Where-Object {$_.EnableFederationAccess -eq $True -and $_.EnablePublicCloudAccess -eq $False}
```

A menos que você tenha criado instâncias personalizadas do ExternalAccessPolicy, esse comando retornará uma política que atenda aos nossos critérios (FederationOnly). Veja um exemplo:
  
```powershell
Identity                          : Tag:FederationOnly
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : False
EnablePublicCloudAudioVideoAccess : False
EnableOutsideAccess               : True
```

Agora que você sabe qual política será atribuída a Alex, podemos atribuir essa política usando o cmdlet [Grant-CsExternalAccessPolicy](https://go.microsoft.com/fwlink/?LinkId=523974) . Veja um exemplo:
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName "FederationOnly"
```

Atribuir uma política é muito simples: basta especificar a identidade do usuário e o nome da política a ser atribuída. 
  
E quando se trata de políticas e atribuições de política, você não está limitado a trabalhar com as contas de usuário uma vez. Por exemplo, suponha que você precise de uma lista de todos os usuários que têm permissão para se comunicar com parceiros federados e com usuários do Windows Live. Já sabemos que esses usuários foram atribuídos à política de acesso de usuário externo FederationAndPICDefault. Como sabemos que, você pode exibir uma lista de todos os usuários executando um comando simples. Este é o comando:
  
```powershell
Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "FederationAndPICDefault"} | Select-Object DisplayName
```

Em outras palavras, isso nos mostra todos os usuários cuja propriedade ExternalAccessPolicy está definida como FederationAndPICDefault. (E, para limitar a quantidade de informações que aparece na tela, use o cmdlet Select-Object para exibir apenas mostrar o nome de exibição de cada usuário.) 
  
Para configurar todas as contas de usuário para usar essa mesma política, use este comando:
  
```powershell
Get-CsOnlineUser | Grant-CsExternalAccessPolicy "FederationAndPICDefault"
```

Este comando usa Get-CsOnlineUser para retornar uma coleção de todos os usuários que tenham sido habilitados para o Lync e, em seguida, envia todas as informações para Grant-CsExternalAccessPolicy, que atribui a política de FederationAndPICDefault a cada e a todos os usuários da coleção.
  
Como um exemplo adicional, suponha que você tenha anteriormente atribuído a Alex a política FederationAndPICDefault e agora já alterou sua mente e gostaria que ele fosse gerenciado pela política de acesso externo global. Você não pode atribuir explicitamente a política global a qualquer pessoa. Em vez disso, a política global é usada para um determinado usuário se nenhuma política por usuário é atribuída a esse usuário. Portanto, se quisermos que Alex seja gerenciado pela política global, você precisará  *cancelar a atribuição*  de qualquer política por usuário atribuída anteriormente a ele. Este é um exemplo de comando:
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName $Null
```

Este comando define o nome da política de acesso externo atribuída a Alex como um valor nulo ($Null). NULL significa "Nothing". Em outras palavras, nenhuma política de acesso externo é atribuída a Alex. Quando nenhuma política de acesso externo é atribuída a um usuário, esse usuário é gerenciado pela política global.
  

## <a name="managing-large-numbers-of-users"></a>Gerenciando um grande número de usuários

Para gerenciar grandes números de usuários (1000 ou mais), você precisa em lotes os comandos por meio de um bloco de script usando o cmdlet [Invoke-Command](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/invoke-command?view=powershell-7) .  Nos exemplos anteriores, cada vez que um cmdlet é executado, ele deve configurar a chamada e, em seguida, aguardar o resultado antes de enviá-lo de volta.  Ao usar um bloco de script, isso permite que os cmdlets sejam executados remotamente e, depois de concluídos, enviem os dados de volta. 

```powershell
Import-Module LyncOnlineConnector
$sfbSession = New-CsOnlineSession
$users = Get-CsOnlineUser -Filter { ClientPolicy -eq $null } -ResultSize 500

$batch = 50
$filter = ''
$total = $users.Count
$count = 0
    $users | ForEach-Object {
    $upn = $_.UserPrincipalName
    $filter += "(UserPrincipalName -eq '$upn')"
    $batch--
    $count++
    if (($batch -eq 0) -or ($count -eq $total)) {
        $filterSB=[ScriptBlock]::Create($filter)
        Invoke-Command -Session $s -ScriptBlock {param($f) Get-CsOnlineUser -filter $f | Grant-CsClientPolicy -PolicyName "ClientPolicyNoIMURL" -Passthru | Grant-CsExternalAccessPolicy -PolicyName "FederationAndPICDefault"} -ArgumentList $filterSB

        # Reset
        $batch = 50
        $filter = ''
    } else {
        $filter += " -or "
    }
}
```

Isso encontrará 500 usuários por vez que não têm uma política de cliente. Ele concederá a eles a política de cliente "ClientPolicyNoIMURL" e a política de acesso externo "FederationAndPicDefault". Os resultados são enviados em lotes em grupos de 50 e cada lote de 50 é enviado para a máquina remota.
  
## <a name="see-also"></a>Confira também

[Gerenciar o Skype for Business Online com o Windows PowerShell](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[Gerenciar o Microsoft 365 com o PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introdução ao PowerShell para o Microsoft 365](getting-started-with-microsoft-365-powershell.md)
