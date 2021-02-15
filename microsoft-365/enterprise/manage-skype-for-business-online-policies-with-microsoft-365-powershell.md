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
description: 'Resumo: Use o PowerShell para gerenciar suas propriedades de conta de usuário do Skype for Business Online com políticas.'
ms.openlocfilehash: 20a75fa1c131f693fcf30d20477af5c9ee7aed35
ms.sourcegitcommit: 22755cebfbfa2c4dc3f8b4f54ccb23636a211ee5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2020
ms.locfileid: "48477036"
---
# <a name="manage-skype-for-business-online-policies-with-powershell"></a>Gerenciar as políticas do Skype for Business Online com o Windows PowerShell

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Para gerenciar muitas propriedades da conta de usuário do Skype for Business Online, você deve especificá-las como propriedades das políticas com o PowerShell para Microsoft 365.
  
## <a name="before-you-begin"></a>Antes de começar

Use estas instruções para se configurar para executar os comandos (ignore as etapas que você já concluiu):

  > [!Note]
  > O Conector Skype for Business Online atualmente faz parte do módulo mais recente do PowerShell do Teams. Se você estiver usando o último lançamento público do PowerShell Teams, você não precisa instalar o Conector do Skype for Business Online.

1. Instale o [módulo do PowerShell do Teams.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)
    
2. Abra um prompt de comando do Windows PowerShell e execute os seguintes comandos: 

   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $userCredential
   Import-PSSession $sfbSession
   ```

   Quando solicitado, insira o nome e a senha da sua conta de administrador do Skype for Business Online.
    
## <a name="manage-user-account-policies"></a>Gerenciar políticas de conta de usuário

Muitas propriedades de conta de usuário do Skype for Business Online são configuradas usando políticas. As políticas são simplesmente coleções de configurações que podem ser aplicadas a um ou mais usuários. Para dar uma olhada em como a política foi configurada, você pode executar este comando de exemplo para a política FederationAndPICDefault:
  
```powershell
Get-CsExternalAccessPolicy -Identity "FederationAndPICDefault"
```

Por sua vez, você deve obter algo semelhante a isto:
  
```powershell
Identity                          : Tag:FederationAndPICDefault
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : True
EnablePublicCloudAudioVideoAccess : True
EnableOutsideAccess               : True
```

Neste exemplo, os valores dentro dessa política determinam o que um uso pode ou não fazer quando se trata de comunicação com usuários federados. Por exemplo, a propriedade EnableOutsideAccess deve ser definida como True para que um usuário possa se comunicar com pessoas de fora da organização. Observe que essa propriedade não aparece no centro de administração do Microsoft 365. Em vez disso, a propriedade é automaticamente definida como True ou False com base nas outras seleções que você fizer. As outras duas propriedades de interesse são:
  
- **EnableFederationAccess** indica se o usuário pode se comunicar com pessoas de domínios federados.
    
- **EnablePublicCloudAccess** indica se o usuário pode se comunicar com usuários do Windows Live.
    
Portanto, você não altera diretamente as propriedades relacionadas à federação em contas de usuário (por exemplo, **Set-CsUser -EnableFederationAccess $True**). Em vez disso, atribua uma conta a uma política de acesso externo que tenha os valores de propriedade desejados pré-configurados. Se quisermos que um usuário seja capaz de se comunicar com usuários federados e com usuários do Windows Live, essa conta de usuário deverá ser atribuída a uma política que permita esses tipos de comunicação.
  
Se você quiser saber se alguém pode ou não se comunicar com usuários de fora da organização, é preciso:
  
- Determinar qual política de acesso externo foi atribuída a esse usuário.
    
- Determinar quais recursos são ou não permitidos por essa política.
    
Por exemplo, você pode fazer isso usando este comando:
  
```powershell
Get-CsOnlineUser -Identity "Alex Darrow" | ForEach {Get-CsExternalAccessPolicy -Identity $_.ExternalAccessPolicy}
```

Esse comando localiza a política atribuída ao usuário e localiza os recursos habilitados ou desabilitados nessa política.
  
Para gerenciar as políticas do Skype for Business Online com o PowerShell, consulte os cmdlets para:

- [Política de cliente](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)
- [Política de conferência](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)
- [Política móvel](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)
- [Política de caixa postal online](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)
- [Política de Roteamento de Voz](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)


> [!NOTE]
> Um plano de discagem do Skype for Business Online é uma política em todos os aspectos, exceto no nome. O nome "plano de discagem" foi escolhido em vez de" "política de discagem" para fornecer compatibilidade com o Office Communications Server e com o Exchange. 
  
Por exemplo, para ver todas as políticas de voz disponíveis para seu uso, execute este comando:
  
```powershell
Get-CsVoicePolicy
```

> [!NOTE]
> Isso retorna uma lista de todas as políticas de voz disponíveis para você. Tenha em mente, no entanto, que nem todas as políticas podem ser atribuídas a todos os usuários. Isso se deve a várias restrições envolvendo licenciamento e localização geográfica. (O chamado " local[de uso](https://msdn.microsoft.com/library/azure/dn194136.aspx).") Se você quiser conhecer as políticas de acesso externo e as políticas de conferência que podem ser atribuídas a um usuário específico, use comandos semelhantes a estes: 

```powershell
Get-CsConferencingPolicy -ApplicableTo "Alex Darrow"
Get-CsExternalAccessPolicy -ApplicableTo "Alex Darrow"
```

O parâmetro ApplicableTo limita os dados retornados para políticas que podem ser atribuídas ao usuário especificado (por exemplo, Antônio Teixeira). Dependendo das restrições de licenciamento e local de uso, isso pode representar um subconjunto de todas as políticas disponíveis. 
  
Em alguns casos, as propriedades das políticas não são usadas com o Microsoft 365, enquanto outras só podem ser gerenciadas pela equipe de suporte da Microsoft. 
  
Com o Skype for Business Online, os usuários devem ser gerenciados por uma política de algum tipo. Se uma propriedade válida relacionada à política estiver em branco, isso significa que o usuário em questão está sendo gerenciado por uma política global, que é uma política aplicada automaticamente a um usuário, a menos que tenha sido atribuída especificamente uma política por usuário. Como não vemos uma política de cliente listada para uma conta de usuário, ela é gerenciada pela política global. Você pode determinar a política de cliente global com este comando:
  
```powershell
Get-CsClientPolicy -Identity "Global"
```

## <a name="see-also"></a>Confira também

[Gerenciar o Skype for Business Online com o Windows PowerShell](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[Gerenciar o Microsoft 365 com o PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introdução ao PowerShell para o Microsoft 365](getting-started-with-microsoft-365-powershell.md)

