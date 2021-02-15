---
title: Pontuação de Produtividade da Microsoft - Privacidade
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
monikerRange: o365-worldwide
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
description: Como a privacidade é protegida com a Pontuação de Produtividade.
ms.openlocfilehash: ceb19fcb7bbf2f6a58e38684604ed3b0dac2a5d4
ms.sourcegitcommit: d859ea36152c227699c1786ef08cda5805ecf7db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49604321"
---
# <a name="privacy-controls-for-productivity-score"></a>Controles de privacidade para a Pontuação de Produtividade

A Pontuação de Produtividade fornece informações sobre a jornada de transformação digital da sua organização por meio do uso do Microsoft 365 e das experiências de tecnologia que o suportam.  A pontuação da sua organização reflete as medições da experiência de pessoas e tecnologias e pode ser comparada com os parâmetros de comparação de organizações semelhantes às suas. Para obter mais detalhes, veja a [visão geral da Pontuação de Produtividade.](productivity-score.md)

Sua privacidade é importante para a Microsoft. Para saber como protegemos sua privacidade, confira a [política de privacidade da Microsoft.](https://privacy.microsoft.com/privacystatement) A Pontuação de Produtividade oferece a você, como administrador de TI da sua organização, acesso às configurações de privacidade para ajudar a garantir que qualquer informação da Pontuação de Produtividade que você visualizar seja a ação, sem comprometer a confiança que sua organização coloca na Microsoft.

Na área de experiências de pessoas, as métricas estão disponíveis apenas no nível organizacional. Esta área analisa como as pessoas usam o Microsoft 365 analisando as categorias de colaboração de conteúdo, mobilidade, reuniões, trabalho em equipe e comunicação. Habilitamos você com vários níveis de controles para ajudá-lo a atender às suas necessidades de política de privacidade interna.
Os controles lhe dão:

- Funções de administrador flexíveis para controlar quem pode ver as informações na Pontuação de Produtividade.
- A capacidade de não participar da área de experiências de pessoas.

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>Funções de administrador flexíveis para controlar quem pode ver as informações na Pontuação de Produtividade

Para exibir toda a Pontuação de Produtividade, você precisa ser uma das seguintes funções de administrador:

- Administração global
- Administradores do Exchange
- Administrador do SharePoint
- Administrador do Skype for Business
- Administrador do Teams
- Leitor Global
- Leitor de Relatórios
- Leitor de relatórios de resumo do uso

Atribua a função Leitor de Relatórios ou Leitor de Resumo de Uso a qualquer pessoa responsável pelo gerenciamento e adoção de alterações, mas não necessariamente um administrador de IT. Essa função dá a eles acesso à experiência completa da Pontuação de Produtividade no Centro de administração do Microsoft 365.

A função Leitor de Relatórios de Resumo de Uso terá que ser atribuída por meio dos cmdlets do PowerShell até que ela se torne atribuível do Centro de administração do Microsoft 365 posteriormente em 2020.

Para atribuir a função leitor de relatórios de resumo de uso com o PowerShell:

- Execute o seguinte PowerShell:

```powershell
Connect-AzureAD
Enable-AzureADDirectoryRole -RoleTemplateId '75934031-6c7e-415a-99d7-48dbd49e875e'
$role=Get-AzureADDirectoryRole -Filter "roleTemplateId eq '75934031-6c7e-415a-99d7-48dbd49e875e'"
Get-AzureADDirectoryRoleMember -ObjectId $role.ObjectId
$u=Get-AzureADUser -ObjectId <user upn>
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId $u.ObjectId
```

</br>


## <a name="capability-to-opt-out-of-people-experiences"></a>Capacidade de optar por não ter experiências de pessoas

Você também pode optar por não usar a área de experiências de pessoas da Pontuação de Produtividade. Se você optar por não participar, ninguém da sua organização poderá exibir essas métricas, e sua organização será removida de qualquer cálculo que envolva comunicação, reuniões, trabalho em equipe, colaboração de conteúdo e mobilidade. Você precisa ser um administrador global para que sua organização não tenha relatórios de experiências de pessoas.

Para optar por:

1. No centro de administração, vá para As **Configurações** da Organização e, na   >   guia Serviços, selecione **Relatórios.** 
2. Des marque a caixa que diz Permitir que os dados de uso do  **Microsoft 365 sejam** usados para insights de experiências de pessoas. Para entender como modificar as configurações de compartilhamento de dados para o Endpoint Analytics no gerenciador de configuração do Intune, selecione **Saiba mais.**
3. Selecione  **Salvar**.

:::image type="content" source="../../media/orgsettingspageoptout.png" alt-text="Página de configurações da organização onde você pode optar por não ter experiências de pessoas.":::