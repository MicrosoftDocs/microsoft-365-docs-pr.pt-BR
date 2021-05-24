---
title: Configurar o Microsoft Viva Learning (Visualização) no Teams de administração
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 05/24/2021
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
ms.openlocfilehash: a96a2f3ecf7d4e1ee0c136ae155868218f08aaf4
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636129"
---
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a>Configurar o Microsoft Viva Learning (Visualização) no Teams de administração

> [!NOTE]
> As informações neste artigo se relacionam a um produto de visualização que pode ser substancialmente modificado antes de ser lançado comercialmente. 

O Teams administrador instala o Viva Learning (Visualização) e aplica políticas de permissão por meio do Teams de administração.

1. Para o Viva Learning (Visualização), você deve primeiro definir a política De atualização em Teams. Para obter mais informações, [consulte Microsoft Teams Visualização Pública](/MicrosoftTeams/public-preview-doc-updates).

    1. Entre no centro de Teams de administração.

    2. Selecione **Teams**  >  **Políticas de atualização.**

    3. Selecione **Adicionar**. 

    4. Nomeia a política de atualização, adicione uma política e acione **Mostrar recursos de visualização**.

2. O administrador deve notificar os usuários sobre a atualização de política para que eles movam sua com build para a Visualização Pública para Teams. 

    1. Os usuários devem selecionar suas imagens de perfil > **Sobre**  >  **Visualização Pública.**
   
        ![Navegação superior no aplicativo Teams mostrando o perfil do usuário](../media/learning/learning-app-select-profile-teams.png)
    
    2. Os usuários devem aceitar os termos e condições **de visualização** pública.

        ![Alternar para a com build de visualização pública](../media/learning/learning-app-switch-to-public-preview.png)
 
3. Para organizações que têm políticas restritivas e precisam habilitar o Viva Learning (Visualização), siga o processo na próxima seção.

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
