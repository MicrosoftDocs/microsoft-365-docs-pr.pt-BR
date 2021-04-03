---
title: Fixar aplicativos no launcher de aplicativos de seus usuários
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- M365-subscription-management
ms.service: o365-administration
localization_priority: Normal
description: Como administrador global, você pode fixar até três aplicativos no launcher de aplicativos dos usuários.
ms.openlocfilehash: 786368f1236c7a86a6fbd0dd863ad0296cb65fac
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579261"
---
# <a name="pin-apps-to-your-users-app-launcher"></a>Fixar aplicativos no launcher de aplicativos de seus usuários

Você pode usar controles no portal do Azure Active Directory para fixar até três aplicativos Office.com e o launcher de aplicativos para todos os usuários em sua organização. Você também pode organizar grupos de aplicativos. Qualquer aplicativo que você adicionar poderá ser desempapado pelo usuário a qualquer momento. Para fixar um aplicativo para seus usuários, você deve ser um administrador de aplicativos em nuvem ou administrador de aplicativos no Azure Active Directory ou um administrador global no Office 365. Para obter mais informações sobre funções de administrador, consulte [funções de administrador no Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) e funções de administrador no Microsoft [365](../add-users/about-admin-roles.md). 

Para obter mais informações sobre o Office.com de aplicativos, consulte meet [the app launcher](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) and updates to office.com and [the-Office 365 app launcher](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503) blog article.

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a>Usar o portal do Azure Active Directory para fixar aplicativos

1. Vá para o Centro de administração do Microsoft 365 em <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .
2. Na nav esquerda, escolha **Mostrar tudo** e, em Centros **de administração,** escolha **Azure Active Directory**.
3. No **Azure Active Directory,** escolha **Aplicativos**  >  **Empresariais Configurações do usuário**.
4. Na seção **Configurações do Office 365,** escolha **Adicionar aplicativo**.
5. Escolha os aplicativos que você deseja fixar no launcher de aplicativo dos usuários e escolha **Adicionar**.

:::image type="content" source="../../media/add-apps.png" alt-text="Configurações do Microsoft 365 para fixar aplicativos.":::

### <a name="pin-a-custom-app"></a>Fixar um aplicativo personalizado

> [!NOTE]
> A interface do usuário indicará se você precisa comprar licenças adicionais do Azure AD para usar esse recurso. Para obter mais informações, [consulte Preço do Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).

1. No **Azure Active Directory,** escolha **Aplicativos Empresariais**  >  **Novo aplicativo** na parte superior da página Todos os **aplicativos.**
2. Na página **Adicionar um aplicativo,** escolha **Aplicativo** não galeria ou **Crie** seu próprio aplicativo se você estiver na versão de visualização do Azure Active Directory. 
3. Digite um nome para o aplicativo e atribua o usuário na **guia Usuários e grupos.**
4. Use a **guia Propriedades** para carregar um ícone para o aplicativo.
5. Para atribuir uma URL ao aplicativo, na guia **Logom** único, escolha **Vinculado** e insira uma URL.
6. Escolha **Salvar**.

## <a name="create-application-collections"></a>Criar coleções de aplicativos

Você também pode criar coleções de aplicativos para os usuários em sua organização. Para obter instruções, [consulte create collections on the My Apps portal in the Azure portal](/azure/active-directory/manage-apps/access-panel-collections).