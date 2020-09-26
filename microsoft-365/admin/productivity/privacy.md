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
ROBOTS: NOINDEX, NOFOLLOW
description: Como a privacidade é protegida com a pontuação de produtividade.
ms.openlocfilehash: 799d532ca1f0abd5fa6234052d4875a79d629601
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48287206"
---
# <a name="privacy-controls-for-productivity-score"></a>Controles de privacidade para Pontuação de produtividade

Pontuação de produtividade ajuda as organizações a transformar como o trabalho é feito com ideias sobre como as pessoas usam o Microsoft 365 e as experiências tecnológicas que dão suporte a eles. A pontuação reflete a sua organização&#39;o desempenho contra medidas de experiência de funcionários e tecnologias e compara sua pontuação com organizações como a sua. Para obter mais detalhes, confira o tópico [visão geral da Pontuação de produtividade](productivity-score.md) .

Sua privacidade é importante para nós e você pode exibir a declaração de privacidade da Microsoft [aqui](https://privacy.microsoft.com/privacystatement). Na pontuação de produtividade, há informações essenciais que fornecemos sobre como as pessoas em suas organizações trabalham. Dessa forma, também Visaremos fornecer controles para garantir que as informações sejam acionáveis de forma significativa, sem comprometer a confiança que você coloca nos EUA.

Fornecemos os seguintes controles para permitir a manipulação mais segura dos dados:

- Funções de administrador flexíveis para controlar quem pode ver as informações na pontuação de produtividade.
- Anonimato de métricas de nível do usuário.
- Capacidade de recusar a experiência do funcionário.

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>Funções de administrador flexíveis para controlar quem pode ver as informações na pontuação de produtividade

Para exibir toda a experiência de produtividade com uma função de administrador, incluindo informações de nível de locatário e detalhes de nível de usuário, a função deve ser uma das seguintes:

- Administrador global
- Administradores do Exchange
- Administrador do SharePoint
- Administrador do Skype for Business
- Administrador de equipes
- Leitor global
- Leitor de relatórios

Para convidar pessoas responsáveis pelo gerenciamento de alterações e pela adoção, mas que não são administradores de ti na experiência, ao mesmo tempo em que dão acesso à experiência completa, incluindo insights de nível de locatário e detalhes de nível de usuário, você pode dar a eles a função leitor de relatórios.

Na experiência do funcionário, fornecemos detalhes de atividade de nível por usuário no formato de grade para cada página de detalhes de categoria. Como esse nível de detalhe não é adequado para todos os possíveis visitantes da Pontuação de produtividade, criamos uma função personalizada na função leitor de relatórios resumidos do Azure AD – para habilitar o acesso a um conjunto mais amplo de visitantes dentro da sua organização apenas para as métricas agregadas e nenhum detalhe por nível na experiência.

:::image type="content" source="../../media/communicationspage.jpg" alt-text="Página de comunicações em relatórios de produtividade.":::

## <a name="anonymization-of-user-level-metrics"></a>Anonimato de métricas de nível de usuário

Para tornar anônimos os dados coletados para todos os relatórios, você deve ser um administrador global. Isso ocultará as informações de identificação, como os nomes de usuários, grupos e sites em todos os relatórios, incluindo a pontuação de produtividade e o uso do Microsoft 365.

1. No centro de administração, vá para as **Settings**configurações da   >   **organização** configurações e, na guia **Serviços** , escolha **relatórios**.
2. Selecione  **relatórios** e, em seguida, escolha para  **Exibir identificadores anônimos para nomes de usuários, grupos e sites em Pontuação de produtividade e relatórios de uso**. Essa configuração é aplicada tanto para os relatórios de uso quanto para o aplicativo de modelo.
3. Selecione  **salvar alterações**.

:::image type="content" source="../../media/orgsettings_anonymous.jpg" alt-text="Tornar as informações do usuário anônimas para relatórios.":::

## <a name="capability-to-opt-out-of-employee-experience"></a>Capacidade de recusar a experiência de funcionários

Também forneceremos a capacidade de recusar a área de experiência de funcionários da Pontuação de produtividade na disponibilidade geral. A ativação dessa configuração impedirá que qualquer pessoa da sua organização possa exibir essas métricas e remover sua organização de quaisquer cálculos envolvendo categorias de comunicação, reuniões, trabalho em equipe, colaboração e mobilidade de conteúdo.

1. No centro de administração, vá para as **Settings**configurações da   >   **organização** configurações e, na guia **Serviços** , escolha **relatórios**.
2. Selecione  **relatórios** e, em seguida, desmarque a caixa que diz  **compartilhar seus dados de org&#39;s com pontuação de produtividade informações de experiência do funcionário**. Para entender como modificar as configurações de compartilhamento de dados para o Endpoint Analytics no Intune Configuration Manager, clique em **saiba mais**.
3. Selecione  **salvar alterações**.

:::image type="content" source="../../media/orgsettingspageoptout.jpg" alt-text="Página de configurações da organização onde você pode sair da experiência do funcionário.":::