---
title: Monitorar a conectividade do Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 8/4/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 53cdb60c-a6b2-4848-b3ff-e7b75dc3fd1f
description: Neste artigo, você aprenderá sobre as ferramentas e técnicas que você pode usar para monitorar e manter a conectividade do Microsoft 365.
ms.openlocfilehash: db3811b70f91efb9fd1e9f023df12d0852ce0189
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920771"
---
# <a name="monitor-microsoft-365-connectivity"></a>Monitorar a conectividade do Microsoft 365

Depois de ter implantado o Microsoft 365, você pode manter a conectividade do Microsoft 365 usando algumas das ferramentas e técnicas abaixo. Você vai querer entender as diretrizes oficiais de Continuidade e [Saúde](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) do Serviço, bem como nossas Práticas Recomendadas para usar [o Microsoft 365 em uma rede lenta.](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166) Você também vai querer pegar o aplicativo de administração do [Microsoft 365](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) e marcar nosso [Microsoft 365 para](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791)empresas - Ajuda do administrador .
  
## <a name="monitoring-microsoft-365-connectivity"></a>Monitorando a conectividade do Microsoft 365

|||
|:-----|:-----|
|**Recebendo notificado dos novos pontos de extremidade do Microsoft 365** <br/> |Se você estiver gerenciando pontos de extremidade do [Microsoft 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), receberá notificações quando publicarmos novos pontos de extremidade, você pode assinar nosso feed RSS usando seu leitor RSS favorito. Veja como se inscrever [por meio do Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) ou você pode enviar as atualizações de feed [RSS por email para você.](https://go.microsoft.com/fwlink/p/?LinkId=532417)  <br/> |
|**Usar o System Center para monitorar o Microsoft 365** <br/> |Se você estiver usando o Microsoft System Center, poderá baixar o [System Center Management Pack para Office 365](https://www.microsoft.com/download/details.aspx?id=43708) para começar a monitorar o Microsoft 365 hoje. Para obter orientações mais detalhadas, consulte o guia de operações do pacote de gerenciamento ou este blog poste Monitoramento [do Office365 usando o System Center Operations Manager](https://blogs.msdn.com/b/mvpawardprogram/archive/2015/07/08/office365-monitoring-using-system-centre-operations-manager.aspx) <br/> |
|**Monitorar a integridade do Azure ExpressRoute** <br/> |Se você estiver se conectando ao Microsoft 365 usando o Azure ExpressRoute para o Microsoft 365, você vai querer garantir que esteja usando o Painel de Saúde do Serviço do Microsoft 365, bem como o Azure [Reducing troubleshooting time with Azure Resource health](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/) <br/> |
|**Usar o Azure AD Connect Health com o AD FS** <br/> |Se você estiver usando o AD FS para um único Sign-On com o Microsoft 365, você vai querer começar a usar o [Azure AD Connect Health](/azure/active-directory/hybrid/how-to-connect-health-adfs)para monitorar sua infraestrutura do AD FS.  <br/> |
|**Monitorar programaticamente o Microsoft 365** <br/> |Consulte nossas diretrizes sobre a API de Gerenciamento [do Microsoft 365.](/office/office-365-management-api/office-365-management-apis-overview)  <br/> |

Aqui está um link curto que você pode usar para voltar: [https://aka.ms/monitorconnectivity365]()
  
## <a name="related-topics"></a>Tópicos relacionados

[Configurar serviços e aplicativos do Microsoft 365 Enterprise](configure-services-and-applications.md)
  
[Preparar sua organização para o Microsoft 365 Enterprise](get-your-organization-ready-for-office-365.md)
  
[Planejamento de rede e ajuste de desempenho para o Microsoft 365](network-planning-and-performance.md)
  
[Integração do Microsoft 365 com ambientes locais](microsoft-365-integration.md)
  
[Gerenciando pontos de extremidade do Microsoft 365](managing-office-365-endpoints.md)