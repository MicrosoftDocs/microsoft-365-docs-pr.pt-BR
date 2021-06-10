---
title: Suporte a IPv6 nos serviços do Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 10/10/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: c08786fb-298e-437c-8222-dab7625fc815
description: 'Resumo: descreve o suporte a IPv6 em Microsoft Office 365 componentes e em Office 365 do governo.'
ms.openlocfilehash: 7f06ed6f8df2c6552ee0a331ad958bca289d0a09
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909677"
---
# <a name="ipv6-support-in-office-365-services"></a>Suporte a IPv6 nos serviços do Office 365

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Office 365 dá suporte a IPv6 e IPv4; no entanto, nem todos os Office 365 recursos estão totalmente habilitados com IPv6. Isso significa que você deve usar IPv4 e IPv6 para se conectar ao Office 365. Se você estiver filtrando seu tráfego de saída para Office 365, a lista completa de endereços IPv6 que são suportados pelo Office 365 pode ser encontrada no artigo [Office 365 URLs](urls-and-ip-address-ranges.md)e intervalos de endereços IP . Depois que sua rede estiver configurada e os endereços IPv6 apropriados são permitidos, você pode baixar o plano de teste [Office 365 IPv6](https://go.microsoft.com/fwlink/?LinkId=293447) do Centro de Download da Microsoft.
  
## <a name="ipv6-support-in-office-365-subscription-service"></a>Suporte A IPv6 no serviço Office 365 assinatura

### <a name="exchange-online-and-ipv6"></a>Exchange Online e IPv6

Se o programa que você usa para se conectar ao Exchange Online suporta IPv6, ele usará IPv6 por padrão em redes com fio e sem fio. Se você quiser controlar as comunicações Exchange Online, use os intervalos de endereços IP em Office 365 [URLs e intervalos de endereços IP.](urls-and-ip-address-ranges.md)
  
### <a name="sharepoint-online-and-ipv6"></a>SharePoint Online e IPv6

 **Office 365 Government G1/G3/G4/K1** Se o programa que você usa para se conectar ao SharePoint Online oferece suporte a IPv6, ele tentará usar IPv6 por padrão.
  
 **Nuvem pública com vários locatários** A Microsoft habilita SharePoint IPv6 Online à sua solicitação. Você precisa fornecer os endereços IP notados cidr para a infraestrutura DNS da sua organização. Lembre-se de que essa infraestrutura DNS não pode ser compartilhada por outras organizações para que o IPv6 seja habilitado para seu locatário. Depois que o IPv6 estiver habilitado, se o programa que você usa para se conectar ao SharePoint Online oferece suporte a IPv6, ele usa IPv6 por padrão.
  
Se o programa que você usa para se conectar ao SharePoint Online oferece suporte a IPv6, ele usará IPv6 por padrão em redes com fio e sem fio. Se você quiser controlar as comunicações SharePoint Online, use os intervalos de endereços IP em Office 365 [URLs e intervalos de endereços IP.](urls-and-ip-address-ranges.md)
  
 **Office 365 Government G1/G3/G4/K1** Se o programa que você usa para se conectar ao SharePoint Online oferece suporte a IPv6, ele tentará usar IPv6 por padrão.
  
### <a name="skype-for-business-and-ipv6"></a>Skype for Business e IPv6

Lembre-se de que o IPv6 não tem suporte no Skype for Business e não pode mais ser habilitado.

### <a name="microsoft-teams-and-ipv6"></a>Microsoft Teams e IPV6

Microsoft Teams O Roteamento Direto só dá suporte a IPv4. O Microsoft Teams e o cliente suportam IPv4 e IPv6. Se você quiser controlar as comunicações para Microsoft Teams, use os intervalos de endereços IP em Office 365 [URLs e intervalos de endereços IP.](urls-and-ip-address-ranges.md)
  
### <a name="exchange-online-protection-and-ipv6"></a>Proteção do Exchange Online e IPv6

Proteção do Exchange Online (EOP) dá suporte a IPv6 se a transmissão ocorrer por meio do Protocolo de Segurança da Camada de Transporte. Para o intervalo EOP, use [Office 365 URLs e intervalos de endereços IP.](urls-and-ip-address-ranges.md)
  
### <a name="ipv6-support-for-office-365-government-offerings"></a>Suporte para IPv6 para Office 365 do governo

Office 365 O suporte IPv6 para ofertas governamentais está em conformidade com o memorando Office de Gerenciamento e Orçamento (OMB) para Diretores de Informações de Departamentos e Agências Executivos, bem como o memorando Adoção do Protocolo IPv6 (IPv6) do Governo Federal. [Microsoft Office 365 para o Governo é](https://go.microsoft.com/fwlink/p/?LinkId=325414) um serviço de vários locatários que armazena dados do governo dos EUA em uma nuvem de comunidade segregada. Como outras Office 365, ela fornece serviços de produtividade e colaboração, incluindo Exchange Online, Skype for Business, SharePoint Online e Microsoft 365 Apps para Grandes Empresas. 

As Microsoft Office 365 do governo se aplicam somente a 2013 e posteriores. Para obter mais informações sobre as Office 365 do governo, consulte Anunciando Office 365 [para Governo: uma Nuvem da Comunidade Governamental](https://go.microsoft.com/fwlink/p/?LinkId=325414). O ITAR (International Traffic in Arms Regulations) é um conjunto de regulamentos do governo dos EUA que controlam a exportação e a importação de artigos e serviços relacionados à defesa na Lista de Munição dos Estados Unidos [(USML)](https://go.microsoft.com/fwlink/p/?LinkId=325415). 

O Microsoft Office 365 para Empresas fornece serviços de hospedagem dedicados para soluções de produtividade da Microsoft que suportam os requisitos de segurança, privacidade e conformidade regulamentar para as agências federais dos EUA que exigem a certificação FISMA (Gerenciamento Federal de Segurança de Informações) e entidades comerciais sujeitas ao ITAR.
  
## <a name="things-to-consider-when-using-ipv6-and-office-365"></a>Coisas a considerar ao usar IPv6 e Office 365

Recomendamos que você não desabilite IPv6. Para obter mais informações, consulte este [artigo de orientação](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users). Para determinar quais versões IP estão sendo usadas em sua rede, considere o seguinte:
  
- Se a exibição do **comando IPConfig** no prompt de comando contiver linhas chamadas "Endereço IPv6" ou "Endereço IPv6 Temporário", você terá IPv6 em seu ambiente.

- Se todos os endereços IPv6 começarem com "fe80" e corresponderem a linhas chamadas "Link-Local IPv6 Address", você não terá IPv6 em seu ambiente.

Essas considerações podem se aplicar à sua rede:
  
- O serviço de assinatura pública não dá suporte à compra por cartão de crédito por IPv6. Isso não se aplica ao Nuvem da Comunidade Governamental (GCC) porque os governos Enterprise Agreement licenciamento (EA).

- O IPv6 não dá suporte a alguns cenários do RMS (Rights Management Services).

- O IPv6 não dá suporte a BlackBerry® Enterprise Server (BES) porque BlackBerry não dá suporte a IPv6.

- Se você usar os Serviços de Federação do Active Directory (AD FS) com Office 365, não há suporte para anunciar seu ponto de extremidade de rede do AD FS para Office 365 usando IPv6. Você não deve incluir registros AAAA na entrada DNS do AD FS ao usar Exchange Online. 

Aqui está um link curto que você pode usar para voltar: [https://aka.ms/o365ip6]()
  
## <a name="see-also"></a>Confira também

[Roteiro de Aprendizagem IPv6](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))
  
[Guia de Sobrevivência IPv6](https://social.technet.microsoft.com/wiki/contents/articles/1728.ipv6-survival-guide.aspx)