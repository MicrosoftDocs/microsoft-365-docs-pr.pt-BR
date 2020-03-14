---
title: Usar sua assinatura gratuita do Azure Active Directory no Office 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: d104fb44-1c42-4541-89a6-1f67be22e4ad
description: Saiba como acessar o Azure Active Directory, que vem incluído na assinatura paga da sua organização ao Office 365.
ms.openlocfilehash: 40ed5808f6e921a3649af408ee078dba64167bb3
ms.sourcegitcommit: dcea75af89f5f80ec6670346ee176407e043de54
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2020
ms.locfileid: "42610588"
---
# <a name="use-your-free-azure-active-directory-subscription-in-office-365"></a>Usar sua assinatura gratuita do Azure Active Directory no Office 365

Se sua organização tiver uma assinatura paga do Office 365, do Microsoft Dynamics CRM Online, do Enterprise Mobility Suite ou de outros serviços da Microsoft, você terá uma assinatura gratuita do Microsoft Azure Active Directory. Você e outros administradores podem usar o Azure AD para criar e gerenciar contas de usuário e grupo. Para usar o Azure AD, basta ir ao portal do Azure e entrar usando sua conta do Office 365.

## <a name="before-you-begin"></a>Antes de começar

Use uma sessão de navegação privada (não uma sessão normal) para acessar o portal do Azure (na etapa 1 abaixo) porque isso impedirá que a credencial com a qual você efetuou logon passe para o Azure. Para abrir uma sessão de navegação privada:

- No Microsoft Edge (versão herdada), no Internet Explorer ou no Mozilla FireFox, pressione `CTRL+SHIFT+P`.

- No Microsoft Edge (versão mais recente) ou no Google Chrome, pressione `CTRL+SHIFT+N`.

## <a name="access-azure-active-directory"></a>Acessar o Azure Active Directory

1. Vá para [portal.azure.com](https://portal.azure.com) e entre com sua conta corporativa ou de estudante do Office 365.

2. No painel de navegação à esquerda no portal do Azure, clique em **Azure Active Directory**.

    ![Clique em Azure Active Directory no painel de navegação à esquerda no portal do Azure.](../media/97d2d72f-ac20-46ab-898c-851f6009b453.png)

    O Centro de administração do **Azure Active Directory** aparece.

## <a name="more-information"></a>Mais informações

- Uma assinatura gratuita do Azure Active Directory não inclui o relatório de atividade de entrada. Para registrar a atividade de entrada (que pode ser útil no caso de um vazamento de dados), você precisa de uma assinatura do Azure Active Directory Premium. Para saber mais, consulte [Por quanto tempo o Azure AD armazena os dados?](https://docs.microsoft.com/azure/active-directory/reports-monitoring/reference-reports-data-retention#how-long-does-azure-ad-store-the-data).

- Você também pode acessar o centro de administração do **Azure Active Directory** do centro de administração do Microsoft 365. No painel de navegação à esquerda do centro de administração do Microsoft 365, clique em **Centros de administração do** \> **Azure Active Directory**.

- Confira informações sobre como gerenciar usuários e grupos e realizar outras tarefas de gerenciamento do diretório em [Gerenciar seu diretório do Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-administer).
