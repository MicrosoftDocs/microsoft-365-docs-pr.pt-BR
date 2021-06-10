---
title: Aplicativos integrados e Azure AD para Microsoft 365 administradores
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection: M365-subscription-management
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: cb2250e3-451e-416f-bf4e-363549652c2a
description: Saiba como registrar e administrar Office 365 aplicativos integrados no Azure AD, permitindo autorizações de aplicativo no nível de administrador global.
ms.openlocfilehash: 0b7392984b77b01abb0992fea5db62b80ed9fb6c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909769"
---
# <a name="integrated-apps-and-azure-ad-for-microsoft-365-administrators"></a>Aplicativos integrados e Azure AD para Microsoft 365 administradores

Há mais para gerenciar aplicativos integrados do que apenas gerenciar [o consentimento do usuário para aplicativos.](../admin/misc/user-consent.md) Com o advento das MICROSOFT 365 REST, os usuários podem conceder aos aplicativos acesso aos seus dados Microsoft 365, como emails, calendários, contatos, usuários, grupos, arquivos e pastas. Por padrão, os usuários precisam conceder permissões individualmente a cada aplicativo. 

Mas isso não será dimensionado bem se você quiser autorizar um aplicativo uma vez no nível de administrador global e reajustá-lo para toda a sua organização por meio do launcher de aplicativos. Para fazer isso, você deve registrar o aplicativo no Azure Active Directory (Azure AD). Existem algumas etapas que você precisa seguir para poder registrar um aplicativo no Azure AD e algumas informações em segundo plano que você deve saber que podem ajudá-lo a gerenciar aplicativos em sua Microsoft 365 organização.
  
## <a name="azure-ad-resources-for-microsoft-365-admins"></a>Recursos do Azure AD para Microsoft 365 administradores

Você precisa realizar essas duas tarefas antes de gerenciar seus aplicativos Microsoft 365 no Azure AD.
  
|Pré-requisitos|Comentários|
|:-----|:-----|
|[Usar sua assinatura gratuita do Azure AD](../compliance/use-your-free-azure-ad-subscription-in-office-365.md) <br/> |Cada assinatura paga Microsoft 365 vem com uma assinatura gratuita do Azure AD. Você pode usar o Azure AD para gerenciar seus aplicativos e para criar e gerenciar contas de usuário e grupo. Para usar o Azure AD, basta ir para o portal do Azure em e entrar [https://portal.azure.com](https://portal.azure.com) usando sua Microsoft 365 de usuário.  <br/> |
|[Gerenciar o consentimento do usuário para aplicativos](../admin/misc/user-consent.md) <br/> |Você deve gerenciar o consentimento do usuário para aplicativos para permitir que aplicativos de terceiros acessem informações Microsoft 365 usuários e registrem aplicativos no Azure AD. Por exemplo, quando alguém usa um aplicativo de terceiros, esse aplicativo pode solicitar permissão para acessar o calendário e editar arquivos que estão em uma pasta do OneDrive.  <br/> |
   
Gerenciar Microsoft 365 aplicativos exige que você tenha conhecimento de aplicativos no Azure AD. Use estes artigos para lhe dar o plano de fundo que você precisa.
  
|Artigo|Comentários|
|:-----|:-----|
|[Conheça o Microsoft 365 de aplicativos](https://support.microsoft.com/office/meet-the-microsoft-365-app-launcher-79f12104-6fed-442f-96a0-eb089a3f476a) <br/> |Se você é novo no launcher de aplicativos, pode estar se perguntando o que é e como usá-lo. O launcher de aplicativos foi projetado para ajudá-lo a chegar aos seus aplicativos de qualquer lugar Microsoft 365.  <br/> |
|[Office 365 visão geral das APIs de gerenciamento](/office/office-365-management-api/office-365-management-apis-overview) <br/> |As APIs de gerenciamento Microsoft 365 permitem que você forneça acesso aos seus dados de Microsoft 365, incluindo as coisas com as quais eles se preocupam mais, seus emails, calendários, contatos, usuários e grupos, arquivos e pastas. <br/> |
|[Integrando aplicativos no Azure AD](/azure/active-directory/develop/quickstart-v1-add-azure-ad-app) <br/> | Saiba mais sobre aplicativos integrados ao Azure AD e como registrar seu aplicativo, entender conceitos por trás de um aplicativo registrado e aprender sobre diretrizes de identidade visual para aplicativos de vários locatários.  <br/> |
|[Adicionar blocos personalizados ao launcher de aplicativos](/office365/admin/manage/customize-the-app-launcher)  <br/> |O launcher de aplicativos no Microsoft 365 torna mais fácil para os usuários encontrar e acessar seus aplicativos. Este artigo descreve as maneiras como um desenvolvedor pode fazer com que seus aplicativos apareçam nos iniciadores de aplicativos dos usuários e também dê a eles uma experiência de logom único (SSO) usando suas credenciais Microsoft 365 de usuário.  <br/> |
|[Tutoriais de integração do Azure AD](/azure/active-directory/saas-apps/tutorial-list) <br/> |O objetivo desses tutoriais é mostrar como configurar o SSO do Azure AD para aplicativos SaaS de terceiros.  <br/> |
|[Cenários de autenticação do Azure AD](/azure/active-directory/develop/authentication-vs-authorization) <br/> |O Azure AD simplifica a autenticação para desenvolvedores fornecendo identidade como serviço, com suporte para protocolos padrão do setor, como OAuth 2.0 e OpenID Conexão, bem como bibliotecas de código aberto para diferentes plataformas para ajudá-lo a começar rapidamente a codificar. Este documento ajuda você a entender os vários cenários que o Azure AD oferece suporte e mostra como começar.  <br/> |
|[Acesso a aplicativos](/azure/active-directory/manage-apps/what-is-access-management) <br/> |O Azure AD permite fácil integração com muitos dos aplicativos saaS (software popular) atuais. Ele fornece gerenciamento de identidade e acesso e fornece um Painel de Acesso para usuários onde eles podem descobrir qual acesso de aplicativo eles têm e onde eles podem usar o SSO para acessar seus aplicativos. Este artigo fornece links para os recursos relacionados que permitem saber mais sobre os aprimoramentos de acesso a aplicativos para o Azure AD e como você pode contribuir para eles.  <br/> |
|[Personalizar sua experiência Office 365 pessoal](https://support.microsoft.com/office/personalize-your-office-365-experience-eb34a21b-52fa-4fbf-a8d5-146132242985) <br/> |Você pode obter acesso rápido aos aplicativos que você usa todos os dias adicionando ou removendo aplicativos no Microsoft 365 de aplicativos.  <br/> |