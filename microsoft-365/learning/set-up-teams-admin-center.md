---
title: Configurar o Microsoft Viva Learning (Visualização) no Teams de administração
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 04/30/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: Saiba como configurar o Microsoft Viva Learning (Visualização) no Teams de administração.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: c1427ae9fceab38046b53b31540e08d726815bda
ms.sourcegitcommit: d3f8c69519c593b1580cfa7187ce085a99b8a846
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2021
ms.locfileid: "52100832"
---
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a>Configurar o Microsoft Viva Learning (Visualização) no Teams de administração

> [!NOTE]
> As informações neste artigo se relacionam a um produto de visualização que pode ser substancialmente modificado antes de ser lançado comercialmente. 

O Teams administrador instala o Viva Learning (Visualização) e aplica políticas de permissão por meio do Teams de administração.

## <a name="manage-settings-for-viva-learning-preview"></a>Gerenciar configurações para o Viva Learning (Visualização)

Você deve ser um administrador no centro de administração Teams para executar essas tarefas.

Para disponibilizar o Viva Learning (Visualização) para usuários em sua organização, siga estas etapas:

1. Na navegação à esquerda do centro de administração Teams, acesse **Teams**  >  **aplicativos Gerenciar aplicativos**.

   ![Navegação à esquerda no centro de Teams de administração mostrando Teams aplicativos e Gerenciar aplicativos.](../media/learning/learning-app-teams-manage-apps-nav.png)

2. Na página **Gerenciar aplicativos,** na caixa de pesquisa, digite *Viva learning* e selecione Viva **Learning (Visualização).**

   ![Gerenciar a página aplicativos no Teams de administração mostrando a caixa de pesquisa.](../media/learning/learning-app-teams-manage-apps-page.png)

3. Na página **Viva Aprendizagem (Visualização):**

   1. Em **Status**, selecione **Permitido** ativar o Viva Learning (Visualização).

   2. Na guia **Configurações,** em Configurações **do** aplicativo, vá para o centro de administração Microsoft 365 para configurar fontes de conteúdo [de aprendizagem.](content-sources-365-admin-center.md)

   ![Página de aprendizado no centro Teams de administração mostrando configurações de Status e Aplicativo.](../media/learning/learning-app-teams-learning-page.png)

4. Depois **de Gerenciar** configurações  do  aplicativo, acesse Políticas de permissão e políticas de Instalação para conceder permissão aos funcionários que devem ter acesso ao Viva Learning (Visualização) como parte da participação da sua organização na visualização.

> [!NOTE]
>  Se sua organização estiver no Ring 4.0 como parte do programa TAP100 do Teams, talvez seja necessário habilitar usuários aprovados no Ring 3.0 para acessar o Viva Learning (Visualização). <br><br>Como parte da visualização, o Viva Learning (Visualização) é lançado no Ring 3.0. Se sua organização estiver no Ring 4.0, você não verá o Viva Learning (Visualização) na página **Gerenciar aplicativos.** Para testar o aplicativo, você precisa criar uma política de permissão de aplicativos personalizados, defini-la como **Permitir** todos os aplicativos e atribuí-la aos usuários aprovados do Anel 3.0. <br><br>   ![Página TAP-AppsPermission-Plcy mostrando Permitir todos os aplicativos selecionados.](../media/learning/learning-app-tap-appspermission-plcy.png)

## <a name="next-step"></a>Próxima etapa

[Configurar fontes de conteúdo de aprendizagem para o Viva Learning (Visualização) no Microsoft 365 de administração](content-sources-365-admin-center.md)