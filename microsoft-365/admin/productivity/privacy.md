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
ms.openlocfilehash: 4978039d99704c0658fe22f3725167ac31276dcd
ms.sourcegitcommit: d578b28ed1886abd083b01b93f01b354067e6d47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/30/2020
ms.locfileid: "48804742"
---
# <a name="privacy-controls-for-productivity-score"></a>Controles de privacidade para Pontuação de produtividade

Pontuação de produtividade ajuda as organizações a transformar como o trabalho é feito com métricas que ajudam você a medir e aprimorar experiências de pessoas e tecnologias. Ele ajuda você a obter visibilidade de como sua organização funciona, fornece métricas que ajudam você a se concentrar em Habilitar experiências aprimoradas.  Você também pode conectar as métricas a ações para ajudá-lo a atualizar as habilidades e os sistemas para que todos possam realizar o melhor trabalho. A pontuação reflete o desempenho da organização e também permite que você compare sua pontuação com segurança com outras organizações como a sua.  Para obter mais detalhes, confira [visão geral da Pontuação de produtividade](productivity-score.md).

Sua privacidade é importante para nós. Para saber como protegemos sua privacidade, consulte a [declaração de privacidade da Microsoft](https://privacy.microsoft.com/privacystatement). Pontuação de produtividade fornece informações essenciais sobre como as pessoas em suas organizações trabalham junto com os controles para garantir que as informações sejam acionáveis enquanto não comprometem a confiança que você coloca na Microsoft.

Na área experiências de pessoas, as métricas estão disponíveis no nível organizacional e inclui todos os usuários em seu locatário do Microsoft 365. Esta área examina como as pessoas usam o Microsoft 365 examinando as categorias de colaboração de conteúdo, mobilidade, reuniões, trabalho em equipe e comunicação. Para ajudá-lo a conduzir o treinamento e a conscientização para o conjunto certo de pessoas que podem precisar de suporte com nossos produtos, também fornecemos informações sobre o nível individual. Embora forneçamos esse nível de transparência, também vamos permitir que você tenha vários níveis de controles para ajudá-lo a atender às suas necessidades de política de privacidade interna.
Os seguintes controles fornecem:

- Funções de administrador flexíveis para controlar quem pode ver as informações na pontuação de produtividade.
- A capacidade de cancelar a identificação de métricas de nível de usuário.
- Capacidade de recusar experiências de pessoas.
- A capacidade de recusar a área de experiências de pessoas

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>Funções de administrador flexíveis para controlar quem pode ver as informações na pontuação de produtividade

Para exibir toda a pontuação de produtividade, incluindo métricas de nível de locatário e detalhes por usuário, sua função deve ser uma das seguintes funções de administrador:

- Administrador global
- Administradores do Exchange
- Administrador do SharePoint
- Administrador do Skype for Business
- Administrador de equipes
- Leitor global
- Leitor de relatórios

Atribua a função leitor de relatórios a qualquer pessoa responsável pelo gerenciamento de alterações e pela adoção. Essa função dá acesso à experiência completa, incluindo métricas de nível de locatário e detalhes de nível de usuário.

O relatório de experiências de pessoas contém detalhes de atividade por usuário para cada página de detalhes de categoria. Atribuir uma função personalizada chamada leitor de relatórios de Resumo de uso (disponível Iniciando em 29 de outubro de 2020) para permitir o acesso apenas às métricas de agregação das experiências de pessoas. Essa função terá que ser atribuída por meio dos cmdlets do PowerShell até que se torne atribuível do centro de administração da Microsoft em 11/15/2020.

Para atribuir a função leitor de relatórios de Resumo de uso com o PowerShell:

- Execute o seguinte PowerShell:

```powershell
Connect-AzureAD
$role=Get-AzureADDirectoryRole -Filter "roleTemplateId eq '75934031-6c7e-415a-99d7-48dbd49e875e'"
Get-AzureADDirectoryRoleMember -ObjectId $role.ObjectId
$u=Get-AzureADUser -ObjectId <user upn>
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId $u.ObjectId
```

</br>

:::image type="content" source="../../media/communicationspage.jpg" alt-text="Página de comunicações em relatórios de produtividade.":::

## <a name="de-identification-of-user-level-metrics"></a>Desidentificação de métricas de nível de usuário

Para tornar anônimos os dados coletados para todos os relatórios, você deve ser um administrador global. Esta ação ocultará as informações de identificação, como o usuário, o grupo e os nomes de site em todos os relatórios, incluindo a pontuação de produtividade e o uso do Microsoft 365.

1. No centro de administração, vá para as **Settings** configurações da   >   **organização** configurações e, na guia **Serviços** , escolha **relatórios** .
2. Selecione  **relatórios** e, em seguida, escolha para  **Exibir identificadores anônimos para nomes de usuários, grupos e sites em Pontuação de produtividade e relatórios de uso** . Essa configuração é aplicada aos relatórios de uso e ao aplicativo de modelo.
3. Selecione  **salvar alterações** .

:::image type="content" source="../../media/orgsettings_anonymous.jpg" alt-text="Página de comunicações em relatórios de produtividade.":::

## <a name="capability-to-opt-out-of-people-experiences"></a>Capacidade de recusar experiências de pessoas

Quando a pontuação da produtividade estiver disponível, você também poderá recusar a área de experiência de pessoas da Pontuação de produtividade. Se você recusar, ninguém da organização poderá exibir essas métricas e sua organização será removida de qualquer cálculo que envolve comunicação, reuniões, trabalho em equipe, colaboração de conteúdo e mobilidade.

1. No centro de administração, vá para as **Settings** configurações da   >   **organização** configurações e, na guia **Serviços** , escolha **relatórios** .
2. Selecione  **relatórios** e, em seguida, desmarque a caixa que diz  **permitir que os dados de uso do Microsoft 365 sejam usados para pessoas com informações de experiência.** . Para entender como modificar as configurações de compartilhamento de dados para o Endpoint Analytics no Intune Configuration Manager, clique em **saiba mais** .
3. Selecione  **salvar alterações** .

:::image type="content" source="../../media/orgsettingspageoptout.jpg" alt-text="Página de comunicações em relatórios de produtividade.":::