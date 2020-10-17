---
title: Gerenciar as políticas do Skype for Business Online com o Windows PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: ''
ms.assetid: ff93a341-6f0f-4f06-9690-726052e1be64
description: 'Resumo: Use o PowerShell para gerenciar as propriedades da conta de usuário do Skype for Business online com políticas.'
ms.openlocfilehash: 20a75fa1c131f693fcf30d20477af5c9ee7aed35
ms.sourcegitcommit: 22755cebfbfa2c4dc3f8b4f54ccb23636a211ee5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2020
ms.locfileid: "48477036"
---
# <a name="manage-skype-for-business-online-policies-with-powershell"></a>Gerenciar as políticas do Skype for Business Online com o Windows PowerShell

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Para gerenciar muitas propriedades da conta de usuário do Skype for Business Online, você deve especificá-las como propriedades de políticas com o PowerShell para o Microsoft 365.
  
## <a name="before-you-begin"></a>Antes de começar

Use estas instruções para configurar a execução dos comandos (pule as etapas que você já concluiu):

  > [!Note]
  > O conector do Skype for Business online atualmente faz parte do módulo mais recente do PowerShell do teams. Se você estiver usando a versão pública mais recente do PowerShell do Teams, não será necessário instalar o conector do Skype for Business online.

1. Instale o [módulo do teams PowerShell](https://docs.microsoft.com/microsoftteams/teams-powershell-install).
    
2. Abra um prompt de comando do Windows PowerShell e execute os seguintes comandos: 

   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $userCredential
   Import-PSSession $sfbSession
   ```

   Quando solicitado, insira o nome da conta e a senha do administrador do Skype for Business online.
    
## <a name="manage-user-account-policies"></a>Gerenciar políticas de conta de usuário

Muitas propriedades da conta de usuário do Skype for Business online são configuradas usando políticas. As políticas são apenas coleções de configurações que podem ser aplicadas a um ou mais usuários. Para ver como a política foi configurada, você pode executar este comando de exemplo para a política FederationAndPICDefault:
  
```powershell
Get-CsExternalAccessPolicy -Identity "FederationAndPICDefault"
```

Por sua vez, você deve obter algo semelhante a este:
  
```powershell
Identity                          : Tag:FederationAndPICDefault
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : True
EnablePublicCloudAudioVideoAccess : True
EnableOutsideAccess               : True
```

Neste exemplo, os valores nesta política determinam o que um uso pode ou não fazer quando se trata de comunicação com usuários federados. Por exemplo, a propriedade EnableOutsideAccess deve ser definida como true para que um usuário seja capaz de se comunicar com pessoas de fora da organização. Observe que essa propriedade não aparece no centro de administração do Microsoft 365. Em vez disso, a propriedade é automaticamente definida como true ou false com base nas outras seleções que você faz. As outras duas propriedades de interesse são:
  
- **EnableFederationAccess** indica se o usuário pode se comunicar com pessoas de domínios federados.
    
- **EnablePublicCloudAccess** indica se o usuário pode se comunicar com usuários do Windows Live.
    
Portanto, você não altera diretamente as propriedades relacionadas à Federação nas contas de usuário (por exemplo, **set-CsUser-EnableFederationAccess $true**). Em vez disso, atribua uma conta uma política de acesso externo que tenha os valores de propriedade desejados pré-configurados. Se quisermos que um usuário seja capaz de se comunicar com usuários federados e com usuários do Windows Live, essa conta de usuário deve ser atribuída a uma política que permita esses tipos de comunicação.
  
Se você quiser saber se alguém pode se comunicar com os usuários de fora da organização, é necessário:
  
- Determinar qual política de acesso externo foi atribuída a esse usuário.
    
- Determinar quais recursos são ou não permitidos por essa política.
    
Por exemplo, você pode fazer isso usando este comando:
  
```powershell
Get-CsOnlineUser -Identity "Alex Darrow" | ForEach {Get-CsExternalAccessPolicy -Identity $_.ExternalAccessPolicy}
```

Este comando localiza a política atribuída ao usuário e, em seguida, localiza os recursos habilitados ou desabilitados nessa política.
  
Para gerenciar as políticas do Skype for Business online com o PowerShell, confira os cmdlets para:

- [Política de cliente](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)
- [Política de conferência](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)
- [Política móvel](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)
- [Política de caixa postal online](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)
- [Política de roteamento de voz](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)


> [!NOTE]
> Um plano de discagem do Skype for Business Online é uma política em cada relação, exceto o nome. O nome "plano de discagem" foi escolhido em vez de, digamos, "política de discagem" para fornecer compatibilidade com versões anteriores do Office Communications Server e com o Exchange. 
  
Por exemplo, para examinar todas as políticas de voz disponíveis para uso, execute este comando:
  
```powershell
Get-CsVoicePolicy
```

> [!NOTE]
> Isso retorna uma lista de todas as políticas de voz disponíveis para você. No entanto, tenha em mente que nem todas as políticas podem ser atribuídas a todos os usuários. Isso se deve a várias restrições envolvendo o licenciamento e localização geográfica. (O que é chamado de "[local de uso](https://msdn.microsoft.com/library/azure/dn194136.aspx).") Se você quiser saber as políticas de acesso externo e as políticas de conferência que podem ser atribuídas a um usuário específico, use comandos semelhantes a estes: 

```powershell
Get-CsConferencingPolicy -ApplicableTo "Alex Darrow"
Get-CsExternalAccessPolicy -ApplicableTo "Alex Darrow"
```

O parâmetro ApplicableTo limita os dados retornados para políticas que podem ser atribuídas ao usuário especificado (por exemplo, Antônio Teixeira). Dependendo das restrições de licenciamento e local de uso, isso pode representar um subconjunto de todas as políticas disponíveis. 
  
Em alguns casos, as propriedades das políticas não são usadas com o Microsoft 365, enquanto outras podem ser gerenciadas pela equipe de suporte da Microsoft. 
  
Com o Skype for Business Online, os usuários devem ser gerenciados por uma política de algum tipo. Se uma propriedade válida relacionada à política estiver em branco, isso significa que o usuário em questão está sendo gerenciado por uma política global, que é uma política aplicada automaticamente a um usuário, a menos que seja especificamente atribuída uma política por usuário. Como não vemos uma política de cliente listada para uma conta de usuário, ela é gerenciada pela política global. Você pode determinar a política de cliente global com este comando:
  
```powershell
Get-CsClientPolicy -Identity "Global"
```

## <a name="see-also"></a>Confira também

[Gerenciar o Skype for Business Online com o Windows PowerShell](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[Gerenciar o Microsoft 365 com o PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introdução ao PowerShell para o Microsoft 365](getting-started-with-microsoft-365-powershell.md)

