---
title: Fixar aplicativos no iniciador de aplicativos dos usuários
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- M365-subscription-management
ms.service: o365-administration
localization_priority: Normal
description: Como administrador global, você pode fixar até três aplicativos no iniciador de aplicativos dos usuários.
ms.openlocfilehash: d9b95a20f332a9b1f2f6b0ebba28a70c58677b58
ms.sourcegitcommit: 87449335d9a1124ee82fa2e95e4745155a95a62f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/29/2020
ms.locfileid: "47310870"
---
# <a name="pin-apps-to-your-users-app-launcher"></a>Fixar aplicativos no iniciador de aplicativos dos usuários

Você pode usar controles no portal do Azure Active Directory para fixar até três aplicativos no Office.com e no iniciador de aplicativos para todos os usuários em sua organização. Você também pode organizar grupos de aplicativos. Qualquer aplicativo que você adicionar poderá ser desempapado pelo usuário a qualquer momento. Para fixar um aplicativo para seus usuários, você deve ser um administrador de aplicativos na nuvem, um administrador de aplicativos no Azure Active Directory ou um administrador global no Office 365. Para obter mais informações sobre funções de administrador, consulte funções de administrador no [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) e funções [de administrador no Microsoft 365.](../add-users/about-admin-roles.md) 

Para obter mais informações sobre o Office.com de [](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) aplicativos, consulte o iniciador de aplicativos e as atualizações do office.com e do artigo do blog do iniciador de aplicativos do [Office 365.](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503)

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a>Usar o portal do Azure Active Directory para fixar aplicativos

1. Vá para o Centro de administração do Microsoft 365 em <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .
2. In the left nav, choose **Show all**, and under **Admin centers**, choose **Azure Active Directory**.
3. No **Azure Active Directory,** escolha **aplicativos empresariais**  >  **Configurações do usuário.**
4. Na seção **Configurações do Office 365,** escolha **Adicionar aplicativo.**
5. Escolha os aplicativos que você deseja fixar no iniciador de aplicativos dos usuários e escolha **Adicionar**.

:::image type="content" source="../../media/add-apps.png" alt-text="Configurações do Microsoft 365 para fixar aplicativos.":::

### <a name="pin-a-custom-app"></a>Fixar um aplicativo personalizado

> [!NOTE]
> A interface do usuário indicará se você precisa comprar licenças adicionais do Azure AD para usar esse recurso. Para saber mais, confira [os preços do Azure Active Directory.](https://azure.microsoft.com/pricing/details/active-directory/)

1. No **Azure Active Directory,** escolha **Aplicativos**  >  **Empresariais Novo** aplicativo na parte superior da página Todos os **aplicativos.**
2. Na página **Adicionar um**  aplicativo, escolha  Aplicativo não galeria ou Crie seu próprio aplicativo se estiver na versão de visualização do Azure Active Directory. 
3. Digite um nome para o aplicativo e atribua o usuário na **guia Usuários e** grupos.
4. Use a **guia** Propriedades para carregar um ícone para o aplicativo.
5. Para atribuir uma URL ao aplicativo, na **guia Logom** único, escolha **Vinculado** e insira uma URL.
6. Escolha **Salvar**.

## <a name="create-application-collections"></a>Criar coleções de aplicativos

Você também pode criar coleções de aplicativos para os usuários em sua organização. Para obter instruções, [confira criar coleções no portal Meus Aplicativos no portal do Azure.](https://docs.microsoft.com/azure/active-directory/manage-apps/access-panel-collections)