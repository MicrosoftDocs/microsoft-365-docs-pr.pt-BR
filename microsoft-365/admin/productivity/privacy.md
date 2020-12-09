---
title: Pontuação de produtividade da Microsoft-privacidade
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
description: Como a privacidade é protegida com a pontuação de produtividade.
ms.openlocfilehash: ceb19fcb7bbf2f6a58e38684604ed3b0dac2a5d4
ms.sourcegitcommit: d859ea36152c227699c1786ef08cda5805ecf7db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49604321"
---
# <a name="privacy-controls-for-productivity-score"></a>Controles de privacidade para Pontuação de produtividade

A pontuação de produtividade fornece informações sobre a jornada de transformação digital da sua organização por meio do uso do Microsoft 365 e das experiências tecnológicas que dão suporte a ela.  A pontuação da sua organização reflete medidas de experiência de pessoas e tecnologia e pode ser comparada a benchmarks de organizações similares às suas. Para obter mais detalhes, consulte [visão geral da Pontuação de produtividade](productivity-score.md).

Sua privacidade é importante para a Microsoft. Para saber como protegemos sua privacidade, consulte a [declaração de privacidade da Microsoft](https://privacy.microsoft.com/privacystatement). A pontuação de produtividade fornece a você, como administrador de ti da sua organização, acesso às configurações de privacidade para ajudar a garantir que qualquer informação de Pontuação de produtividade exibida seja acionável, sem comprometer a confiança que sua organização coloca no Microsoft.

Na área experiências de pessoas, as métricas estão disponíveis apenas no nível organizacional. Esta área analisa como as pessoas usam o Microsoft 365 examinando as categorias de colaboração de conteúdo, mobilidade, reuniões, trabalho em equipe e comunicação. Habilitamos vários níveis de controles para ajudá-lo a atender às suas necessidades de política de privacidade interna.
Os controles fornecem:

- Funções de administrador flexíveis para controlar quem pode ver as informações na pontuação de produtividade.
- A capacidade de recusar a área de experiências de pessoas.

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>Funções de administrador flexíveis para controlar quem pode ver as informações na pontuação de produtividade

Para exibir toda a pontuação de produtividade, você precisa ser uma das seguintes funções de administrador:

- Administração global
- Administradores do Exchange
- Administrador do SharePoint
- Administrador do Skype for Business
- Administrador do Teams
- Leitor Global
- Leitor de Relatórios
- Leitor de relatórios de Resumo de uso

Atribua a função leitor de relatórios ou relatórios de Resumo de uso a qualquer pessoa responsável pelo gerenciamento de alterações e pela adoção, mas não necessariamente um administrador de ti. Essa função concede a eles acesso à experiência completa de Pontuação de produtividade no centro de administração do Microsoft 365.

A função leitor de relatórios de Resumo de uso precisará ser atribuída por meio dos cmdlets do PowerShell até que se torne atribuível do centro de administração do Microsoft 365 mais tarde no 2020.

Para atribuir a função leitor de relatórios de Resumo de uso com o PowerShell:

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


## <a name="capability-to-opt-out-of-people-experiences"></a>Capacidade de recusar experiências de pessoas

Você também pode recusar a área experiências de pessoas de Pontuação de produtividade. Se você recusar, ninguém da sua organização poderá exibir essas métricas, e sua organização será removida de qualquer cálculo que envolve comunicação, reuniões, trabalho em equipe, colaboração de conteúdo e mobilidade. Você precisa ser um administrador global para que sua organização saia dos relatórios de experiências de pessoas.

Para aceitar:

1. No centro de administração, vá para as **Settings** configurações da   >   **organização** configurações e, na guia **Serviços** , selecione **relatórios**.
2. Desmarque a caixa que diz permitir que os  **dados de uso do Microsoft 365 sejam usados para ideias de experiências de pessoas**. Para entender como modificar as configurações de compartilhamento de dados para o Endpoint Analytics no Intune Configuration Manager, selecione **saiba mais**.
3. Selecione  **salvar**.

:::image type="content" source="../../media/orgsettingspageoptout.png" alt-text="Página de configurações da organização onde você pode recusar as experiências de pessoas.":::