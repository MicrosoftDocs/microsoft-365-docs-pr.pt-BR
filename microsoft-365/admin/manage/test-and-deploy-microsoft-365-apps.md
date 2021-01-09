---
title: Testar e implantar aplicativos do Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
ms.custom: AdminSurgePortfolio
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Encontre, teste e implante aplicativos de parceiros da Microsoft e da Microsoft para usuários e grupos em sua organização no portal de aplicativos integrados no centro de administração do Microsoft 365.
ms.openlocfilehash: b0dc6277461ff03e8aae2e820543f8e5d9e2303c
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790185"
---
# <a name="test-and-deploy-microsoft-365-apps-in-the-microsoft-365-admin-center"></a>Testar e implantar o Microsoft 365 Apps no Centro de administração do Microsoft 365

O Centro de administração do Microsoft 365 oferece flexibilidade para implantar aplicativos de parceiros da Microsoft e da Microsoft em um único local. A capacidade de encontrar, testar e implantar totalmente aplicativos adquiridos e licenciados por parceiros da Microsoft e do portal de aplicativos integrados proporciona a conveniência e os benefícios que sua organização requer para manter os serviços de negócios atualizados regularmente e funcionando com eficiência.  

Para saber mais sobre como comprar e licenciar aplicativos do Microsoft 365 para sua organização, confira a postagem de blog chamada Gerenciar e implantar o Microsoft 365 Apps no centro de administração do [Microsoft 365.](https://techcommunity.microsoft.com/t5/microsoft-365-blog/manage-and-deploy-microsoft-365-apps-from-the-microsoft-365/ba-p/1194324)
  
## <a name="manage-apps-in-the-integrated-apps-portal"></a>Gerenciar aplicativos no portal de aplicativos integrados

Escolhendo aplicativos integrados no centro de administração do Microsoft 365, você pode gerenciar o teste e a implantação de aplicativos de parceiros adquiridos e licenciados da Microsoft e da Microsoft. 

1. In the admin center, in the left nav, choose **Settings**, and then choose **Integrated apps**. 

2. Escolha um aplicativo **com o Status** de Mais **aplicativos disponíveis.**

3. Selecione **Implantar** na parte superior da página ao lado da mensagem que se refere à espera de implantação.

    Alguns aplicativos exigem que você adicione usuários antes de selecionar **Implantar.**

    a. Selecione **Adicionar usuários,** escolha **Implantação completa** e escolha Toda a **organização** ou **usuários/grupos específicos.**

    Usuários/grupos específicos podem ser um grupo do Microsoft 365, um grupo de segurança ou um grupo distribuído.

    Você também pode escolher **Testar implantação** se preferir aguardar para implantar o aplicativo em toda a organização.

    b. Selecione **Atualizar**, **Feito** e agora você pode selecionar **Implantar** na guia **Visão** Geral.  

4. Revise as informações do aplicativo e selecione **Implantar.** 

5. Selecione **Concluído na** página **Implantação** concluída. 

    Revise os detalhes do teste ou da implantação completa na guia **Visão** geral.

## <a name="find-published-apps-for-testing-and-full-deployment"></a>Encontre aplicativos publicados para teste e implantação completa 

Você pode encontrar, testar e implantar totalmente aplicativos publicados que ainda não aparecem na lista na página Aplicativos integrados. Ao comprar e licenciar os aplicativos no centro de administração, você pode adicionar aplicativos de parceiros da Microsoft e da Microsoft à sua lista em um único local.

1. In the admin center, in the left nav, choose **Settings**, and then choose **Integrated apps**. 

2. Selecione **Obter aplicativos** acima da lista de aplicativos.

3. Na página **aplicativos publicados do Microsoft 365 Apps,** selecione o aplicativo que você deseja implantar escolhendo **Obter agora.**

4. Aceite as permissões e selecione **Continuar.**

5. Selecione **Implantar** na parte superior da página ao lado da mensagem que se refere à espera de implantação.

    Alguns aplicativos exigem que você adicione usuários antes de selecionar **Implantar.**

    a. Selecione **Adicionar usuários,** escolha **Implantação completa** e escolha Toda a **organização** ou **usuários/grupos específicos.**

    Usuários/grupos específicos podem ser um grupo do Microsoft 365, um grupo de segurança ou um grupo distribuído.

    Você também pode escolher **Testar implantação** se preferir aguardar para implantar o aplicativo em toda a organização.

    b. Selecione **Atualizar**, **Feito** e agora você pode selecionar **Implantar** na guia **Visão** Geral.  

6. Revise as informações do aplicativo e selecione **Implantar.** 

7. Selecione **Concluído na** página **Implantação** concluída. 

    Revise os detalhes do teste ou da implantação completa na guia **Visão** geral.

No Centro de administração do Microsoft 365, o **Status** de cada aplicativo implantado é **OK** com uma implantação de Tipo de Implantação de **Teste,** Implantação completa ou **Personalizado** e **a** data em que você implantou o aplicativo.

> [!NOTE]
> Se um aplicativo tiver sido implantado anteriormente em outro lugar que não seja o Portal de Aplicativos Integrados, o **Tipo de Implantação** será **Personalizado.**

## <a name="unsupported-scenarios"></a>Cenários sem suporte

Os cenários a seguir não têm suporte para implantação no portal de Aplicativos Integrados:

- O aplicativo ou o complemento está vinculado a mais de um software como uma oferta de serviço (SaaS).
- O aplicativo SaaS está vinculado a aplicativos e complementos, mas não tem um AADid associado.
- Dois aplicativos SaaS compartilham o mesmo AADid e ambos estão vinculados a aplicativos ou complementos.
  