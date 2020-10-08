---
title: Integração do Azure com o Microsoft 365
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
description: Integre o Microsoft 365 com o Azure AD se você quiser sincronização de senha ou logon único com seu ambiente local.
ms.openlocfilehash: b1f20ebc692421ed6df0d6f7c31a4d80347133e3
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384743"
---
# <a name="azure-integration-with-microsoft-365"></a>Integração do Azure com o Microsoft 365

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

O Microsoft 365 usa o Azure Active Directory (Azure AD) para gerenciar as identidades de usuário nos bastidores. Sua assinatura do Microsoft 365 inclui uma assinatura gratuita do Azure AD para que você possa integrar seus serviços de domínio do Active Directory (AD DS) local para sincronizar contas de usuário e senhas ou configurar o logon único. Você também pode adquirir recursos avançados para gerenciar melhor suas contas.
  
O Azure AD também oferece outras funcionalidades, como gerenciar aplicativos integrados, que você pode usar para estender e personalizar suas assinaturas do Microsoft 365.
  
Você pode usar os consultores de implantação do Azure AD para uma experiência de instalação e configuração orientada no centro de administração do Microsoft 365 (você deve estar conectado ao Microsoft 365):

 - [Supervisor de conexão do Azure AD](https://aka.ms/aadconnectpwsync)
 - [Supervisor de implantação do AD FS](https://aka.ms/adfsguidance)
 - [Guia de instalação do Azure AD](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a>Edições do Azure Active Directory e gerenciamento de identidade do Microsoft 365

Se você tiver uma assinatura paga do Microsoft 365, também terá uma assinatura gratuita do Azure AD. Você pode usar o Azure AD para criar e gerenciar contas de usuário e de grupo. Para ativar essa assinatura, você deve concluir um registro de uma única vez. Depois disso, você pode acessar o Azure AD do seu centro de administração do Microsoft 365. 

Para obter instruções para registrar sua assinatura gratuita do Azure AD, confira [usar sua assinatura gratuita do Azure ad](../compliance/use-your-free-azure-ad-subscription-in-office-365.md). Não vá diretamente para o azure.microsoft.com para se inscrever ou você terminará com uma assinatura de avaliação ou paga para o Microsoft Azure separada da sua assinatura gratuita do Azure AD com o Microsoft 365. 
  
Com a assinatura gratuita, você pode sincronizar com os diretórios locais, configurar o logon único e sincronizar com vários softwares como aplicativos de serviço, como Salesforce, DropBox e muito mais.
  
Se quiser uma funcionalidade avançada do AD DS, uma sincronização bidirecional e outros recursos de gerenciamento, você poderá atualizar sua assinatura gratuita para uma assinatura premium paga. Para obter detalhes, consulte [Azure Active Directory Editions](https://azure.microsoft.com/pricing/details/active-directory/).
  
Para obter mais informações sobre o Microsoft 365 e o Azure AD, consulte [microsoft 365 Identity Models](about-microsoft-365-identity.md).
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a>Estenda os recursos do seu locatário do Microsoft 365

|**Recurso**|**Descrição**|
|:-----|:-----|
|Aplicativos integrados  <br/> |Você pode conceder acesso a aplicativos individuais a seus dados do Microsoft 365, como emails, calendários, contatos, usuários, grupos, arquivos e pastas. Você também pode autorizar esses aplicativos no nível de administração global e disponibilizá-los para toda a empresa registrando os aplicativos no Azure AD. Formore informações, consulte [aplicativos integrados e o Azure ad para administradores do Microsoft 365](integrated-apps-and-azure-ads.md).  <br/> Confira também o [logon único](https://go.microsoft.com/fwlink/p/?LinkId=698604).  <br/> |
|PowerApps  <br/> | Os aplicativos de energia são aplicativos focados para dispositivos móveis que podem se conectar às fontes de dados existentes, como listas do SharePoint e outros aplicativos de dados. Confira [criar um PowerApp para uma lista no SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) e na [página do PowerApps](https://powerapps.microsoft.com/) para obter detalhes.  <br/> |
   
## <a name="see-also"></a>Confira também

[Visão geral do Microsoft 365 Enterprise](microsoft-365-overview.md)
