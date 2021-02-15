---
title: Aplicativos integrados e o Azure AD para administradores do Microsoft 365
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
description: Saiba como registrar e administrar os Aplicativos integrados do Office 365 no Azure AD, permitindo autorizações de aplicativos no nível de administrador global.
ms.openlocfilehash: 1e84b5e6f82848bf1d100004bcd2711ad2e9ed39
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384897"
---
# <a name="integrated-apps-and-azure-ad-for-microsoft-365-administrators"></a>Aplicativos integrados e o Azure AD para administradores do Microsoft 365

Há muito mais para gerenciar aplicativos integrados do que apenas gerenciar [o consentimento do usuário para aplicativos.](https://docs.microsoft.com/microsoft-365/admin/misc/integrated-apps) Com o advento das APIs REST do Microsoft 365, os usuários podem conceder aos aplicativos acesso aos seus dados do Microsoft 365, como email, calendários, contatos, usuários, grupos, arquivos e pastas. Por padrão, os usuários precisam conceder permissões individualmente a cada aplicativo. 

Mas isso não será bem dimensionado se você quiser autorizar um aplicativo uma vez no nível de administrador global e roll-out para toda a organização por meio do iniciador de aplicativos. Para fazer isso, você deve registrar o aplicativo no Azure Active Directory (Azure AD). Existem algumas etapas que você precisa seguir antes de registrar um aplicativo no Azure AD e algumas informações em segundo plano que você deve saber que podem ajudá-lo a gerenciar aplicativos em sua organização do Microsoft 365.
  
## <a name="azure-ad-resources-for-microsoft-365-admins"></a>Recursos do Azure AD para administradores do Microsoft 365

Você precisa realizar essas duas tarefas antes de gerenciar seus aplicativos do Microsoft 365 no Azure AD.
  
|Pré-requisitos|Comentários|
|:-----|:-----|
|[Usar sua assinatura gratuita do Azure AD](https://docs.microsoft.com/microsoft-365/compliance/use-your-free-azure-ad-subscription-in-office-365) <br/> |Cada assinatura paga do Microsoft 365 vem com uma assinatura gratuita do Azure AD. Você pode usar o Azure AD para gerenciar seus aplicativos e criar e gerenciar contas de usuários e grupos. Para usar o Azure AD, basta ir para o portal do Azure em e entrar [https://portal.azure.com](https://portal.azure.com) usando sua conta do Microsoft 365.  <br/> |
|[Gerenciar o consentimento do usuário para aplicativos](https://docs.microsoft.com/microsoft-365/admin/misc/integrated-apps) <br/> |Você deve gerenciar o consentimento do usuário para aplicativos para permitir que aplicativos de terceiros acessem as informações do Microsoft 365 do usuário e registrem aplicativos no Azure AD. Por exemplo, quando alguém usa um aplicativo de terceiros, esse aplicativo pode solicitar permissão para acessar o calendário e editar arquivos que estão em uma pasta do OneDrive.  <br/> |
   
Gerenciar aplicativos do Microsoft 365 requer que você tenha conhecimento de aplicativos no Azure AD. Use estes artigos para dar a você a experiência de que precisa.
  
|Artigo|Comentários|
|:-----|:-----|
|[Conheça o iniciador de aplicativos do Microsoft 365](https://support.microsoft.com/office/meet-the-microsoft-365-app-launcher-79f12104-6fed-442f-96a0-eb089a3f476a) <br/> |Se você é novo no iniciador de aplicativos, deve estar se perguntando o que é e como usá-lo. O iniciador de aplicativos foi projetado para ajudá-lo a chegar aos seus aplicativos de qualquer lugar no Microsoft 365.  <br/> |
|[Visão geral das APIs de gerenciamento do Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview) <br/> |As APIs de gerenciamento do Microsoft 365 permitem que você forneça acesso aos seus dados do Microsoft 365, incluindo o que eles mais importam: seus emails, calendários, contatos, usuários e grupos, arquivos e pastas. <br/> |
|[Integrando aplicativos no Azure AD](https://docs.microsoft.com/azure/active-directory/develop/quickstart-v1-add-azure-ad-app) <br/> | Saiba mais sobre os aplicativos integrados ao Azure AD e como registrar seu aplicativo, entender os conceitos por trás de um aplicativo registrado e aprender sobre diretrizes de identidade visual para aplicativos multi-locatário.  <br/> |
|[Adicionar blocos personalizados ao iniciador de aplicativos](https://docs.microsoft.com/office365/admin/manage/customize-the-app-launcher)  <br/> |O iniciador de aplicativos no Microsoft 365 torna mais fácil para os usuários encontrar e acessar seus aplicativos. Este artigo descreve como você, como desenvolvedor, pode fazer com que seus aplicativos apareçam nos iniciadores de aplicativos dos usuários e também dá a eles uma experiência de SSO (logo único) usando suas credenciais do Microsoft 365.  <br/> |
|[Tutoriais de integração do Azure AD](https://docs.microsoft.com/azure/active-directory/saas-apps/tutorial-list) <br/> |O objetivo desses tutoriais é mostrar como configurar o SSO do Azure AD para aplicativos SaaS de terceiros.  <br/> |
|[Cenários de autenticação do Azure AD](https://go.microsoft.com/fwlink/?LinkId=617145) <br/> |O Azure AD simplifica a autenticação para desenvolvedores fornecendo identidade como um serviço, com suporte para protocolos padrão do setor, como OAuth 2.0 e OpenID Connect, bem como bibliotecas de código aberto para diferentes plataformas para ajudá-lo a começar rapidamente a codificar. Este documento ajuda você a entender os vários cenários que o Azure AD oferece suporte e mostra como começar.  <br/> |
|[Acesso a aplicativos](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-access-management) <br/> |O Azure AD permite fácil integração com muitos dos aplicativos de software como serviço (SaaS) populares de hoje. Ele fornece gerenciamento de identidade e acesso e fornece um Painel de Acesso para os usuários onde eles podem descobrir qual acesso de aplicativo eles têm e onde eles podem usar o SSO para acessar seus aplicativos. Este artigo fornece links para os recursos relacionados que permitem que você saiba mais sobre os aprimoramentos de acesso ao aplicativo para o Azure AD e como você pode contribuir com eles.  <br/> |
|[Personalizar sua experiência do Office 365](https://support.microsoft.com/office/personalize-your-office-365-experience-eb34a21b-52fa-4fbf-a8d5-146132242985) <br/> |Você pode obter acesso rápido aos aplicativos usados todos os dias adicionando ou removendo aplicativos no iniciador de aplicativos do Microsoft 365.  <br/> |

