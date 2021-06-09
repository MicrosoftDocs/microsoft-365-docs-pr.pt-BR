---
title: Integração do Azure com Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: a5efce5d-9c9c-4190-b61b-fd273c1d425f
description: Integre Microsoft 365 com o Azure AD se você quiser sincronização de senha ou um único login com seu ambiente local.
ms.openlocfilehash: f977969634401d59d7598136f9323cb0e37f9ece
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905327"
---
# <a name="azure-integration-with-microsoft-365"></a>Integração do Azure com Microsoft 365

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Microsoft 365 usa Azure Active Directory (Azure AD) para gerenciar identidades de usuários nos bastidores. Sua assinatura Microsoft 365 inclui uma assinatura gratuita do Azure AD para que você possa integrar seus Serviços de Domínio do Active Directory (AD DS) local para sincronizar contas de usuário e senhas ou configurar o logom único. Você também pode comprar recursos avançados para gerenciar melhor suas contas.
  
O Azure AD também oferece outras funcionalidades, como o gerenciamento de aplicativos integrados, que você pode usar para estender e personalizar suas Microsoft 365 assinaturas.
  
Você pode usar os consultores de implantação do Azure AD para uma experiência de configuração e configuração guiada no centro de administração do Microsoft 365 (você deve estar Microsoft 365):

 - [Consultor de Conexão do Azure AD](https://aka.ms/aadconnectpwsync)
 - [Consultor de implantação do AD FS](https://aka.ms/adfsguidance)
 - [Guia de configuração do Azure AD](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a>Edições do Azure AD e gerenciamento Microsoft 365 identidade

Se você tiver uma assinatura paga para Microsoft 365, também terá uma assinatura gratuita do Azure AD. Você pode usar o Azure AD para criar e gerenciar contas de usuário e grupo. Para ativar essa assinatura, você precisa concluir um registro único. Depois, você pode acessar o Azure AD a partir do seu Microsoft 365 de administração. 

Para obter instruções para registrar sua assinatura gratuita do Azure AD, consulte use sua assinatura gratuita [do Azure AD](../compliance/use-your-free-azure-ad-subscription-in-office-365.md). Não vá diretamente para azure.microsoft.com para se inscrever ou você terminará com uma assinatura de avaliação ou paga para Microsoft Azure que está separada da sua assinatura gratuita do Azure AD com Microsoft 365. 
  
Com a assinatura gratuita, você pode sincronizar com diretórios locais, configurar o logor único e sincronizar com muitos softwares como aplicativos de serviço, como Salesforce, DropBox e muito mais.
  
Se você quiser funcionalidade aprimorada do AD DS, sincronização bi-direcional e outros recursos de gerenciamento, você pode atualizar sua assinatura gratuita para uma assinatura premium paga. Para obter os detalhes, [consulte Azure Active Directory edições](https://azure.microsoft.com/pricing/details/active-directory/).
  
Para obter mais informações sobre Microsoft 365 e do Azure AD, [consulte Microsoft 365 de identidade.](about-microsoft-365-identity.md)
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a>Estender os recursos do seu Microsoft 365 locatário

|**Recurso**|**Descrição**|
|:-----|:-----|
|Aplicativos integrados  <br/> |Você pode conceder acesso a aplicativos individuais aos seus dados de Microsoft 365, como emails, calendários, contatos, usuários, grupos, arquivos e pastas. Você também pode autorizar esses aplicativos no nível de administrador global e torná-los disponíveis para toda a sua empresa registrando os aplicativos no Azure AD. Para obter mais informações, consulte [Integrated Apps and Azure AD for Microsoft 365 administrators](integrated-apps-and-azure-ads.md).  <br/> Consulte [Também Sign-on único](/azure/active-directory/manage-apps/what-is-single-sign-on).  <br/> |
|PowerApps  <br/> | Os aplicativos de energia são aplicativos voltados para dispositivos móveis que podem se conectar às fontes de dados existentes, como SharePoint listas e outros aplicativos de dados. Consulte [Create a PowerApp for a list in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) and the [PowerApps page for](https://powerapps.microsoft.com/) details.  <br/> |
   
## <a name="see-also"></a>Confira também

[Visão geral do Microsoft 365 Enterprise](microsoft-365-overview.md)