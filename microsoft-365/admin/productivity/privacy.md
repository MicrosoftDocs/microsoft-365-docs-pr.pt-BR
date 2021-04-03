---
title: Pontuação de Produtividade da Microsoft - Privacidade
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
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
ms.openlocfilehash: 5b5997532ddcd1fdf43b4124f8e2d8183bb3d89e
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579165"
---
# <a name="privacy-controls-for-productivity-score"></a>Controles de privacidade para Pontuação de Produtividade

A Pontuação de Produtividade fornece informações sobre a jornada de transformação digital da sua organização por meio do uso do Microsoft 365 e das experiências de tecnologia que o suportam.  A pontuação da sua organização reflete as medidas de experiência de pessoas e tecnologias e pode ser comparada a comparações de organizações semelhantes às suas. Para obter mais detalhes, consulte a visão geral [da Pontuação de Produtividade.](productivity-score.md)

Sua privacidade é importante para a Microsoft. Para saber como protegemos sua privacidade, consulte a declaração de privacidade [da Microsoft.](https://privacy.microsoft.com/privacystatement) A Pontuação de Produtividade oferece a você, como administrador de TI da sua organização, acesso às configurações de privacidade para ajudar a garantir que todas as informações de Pontuação de Produtividade que você exibir são ativas, sem comprometer a confiança que sua organização coloca na Microsoft.

Na área de experiências de pessoas, as métricas estão disponíveis apenas no nível organizacional. Esta área analisa como as pessoas usam o Microsoft 365 analisando as categorias de colaboração de conteúdo, mobilidade, reuniões, trabalho em equipe e comunicação. Habilitamos você com vários níveis de controles para ajudá-lo a atender às suas necessidades de política de privacidade interna.
Os controles dão a você:

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

Atribua a função Leitor de Relatórios de Resumo de Uso a qualquer pessoa responsável pelo gerenciamento e adoção de alterações, mas não necessariamente um administrador de IT. Essa função oferece acesso à experiência completa de Pontuação de Produtividade no Centro de administração do Microsoft 365.

A função Leitor de Relatórios de Resumo de Uso terá que ser atribuída por meio de cmdlets do PowerShell até que ela se torne atribuível do centro de administração do Microsoft 365 posteriormente em 2020.

Para atribuir a função Leitor de Relatórios de Resumo de Uso com o PowerShell:

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

Você também pode optar pela área de experiências de pessoas da Pontuação de Produtividade. Se você não concordar, ninguém da sua organização poderá exibir essas métricas, e sua organização será removida de quaisquer cálculos que envolvam comunicação, reuniões, trabalho em equipe, colaboração de conteúdo e mobilidade. Você precisa ser um administrador global para excluir sua organização dos relatórios de experiências de pessoas.

Para optar por:

1. No centro de administração, vá para **Configurações**   >   **Da Organização Configurações**  >  **Pontuação de Produtividade**.
2. Descon marque a caixa que diz Permitir que os dados de uso do  **Microsoft 365** sejam usados para informações de experiências de pessoas. Para entender como modificar as configurações de compartilhamento de dados para o Endpoint Analytics no gerenciador de configuração do Intune, selecione **Saiba mais**.
3. Selecione  **Salvar**.

:::image type="content" source="../../media/orgsettingspageoptout.png" alt-text="Página de configurações da organização onde você pode optar por não ter experiências de pessoas.":::
