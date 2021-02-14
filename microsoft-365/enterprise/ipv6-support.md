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
description: 'Resumo: descreve o suporte a IPv6 nos componentes do Microsoft Office 365 e nas ofertas governamentais do Office 365.'
ms.openlocfilehash: f671e8caf868ebbed628a155b73ce6fe413949a9
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235601"
---
# <a name="ipv6-support-in-office-365-services"></a>Suporte a IPv6 nos serviços do Office 365

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

O Office 365 dá suporte a IPv6 e IPv4; No entanto, nem todos os recursos do Office 365 estão totalmente habilitados com IPv6. Isso significa que você deve usar IPv4 e IPv6 para se conectar ao Office 365. Se você estiver filtrando o tráfego de saída para o Office 365, a lista completa de endereços IPv6 suportados pelo Office 365 pode ser encontrada no artigo URLs e intervalos de endereços IP do [Office 365.](urls-and-ip-address-ranges.md) Depois que sua rede estiver configurada e os endereços IPv6 apropriados são permitidos, você poderá baixar o plano de teste [IPv6 do Office 365](https://go.microsoft.com/fwlink/?LinkId=293447) do Centro de Download da Microsoft.
  
## <a name="ipv6-support-in-office-365-subscription-service"></a>Suporte a IPv6 no serviço de assinatura do Office 365

### <a name="exchange-online-and-ipv6"></a>Exchange Online e IPv6

Se o programa que você usa para se conectar ao Exchange Online for compatível com IPv6, ele usará IPv6 por padrão em redes com e sem fio. Se você quiser controlar as comunicações com o Exchange Online, use os intervalos de endereços IP em URLs e intervalos de endereços IP do [Office 365.](urls-and-ip-address-ranges.md)
  
### <a name="sharepoint-online-and-ipv6"></a>SharePoint Online e IPv6

 **Office 365 Government G1/G3/G4/K1** Se o programa que você usa para se conectar ao SharePoint Online oferece suporte a IPv6, ele tentará usar IPv6 por padrão.
  
 **Nuvem pública multi-locatário** A Microsoft habilita o SharePoint Online IPv6 em sua solicitação. Você precisa fornecer os endereços IP notados CIDR para a infraestrutura DNS da sua organização. Lembre-se de que essa infraestrutura DNS não pode ser compartilhada por outras organizações para que o IPv6 seja habilitado para seu locatário. Depois que o IPv6 é habilitado, se o programa que você usa para se conectar ao SharePoint Online suporta IPv6, ele usa IPv6 por padrão.
  
Se o programa que você usa para se conectar ao SharePoint Online for compatível com IPv6, ele usará IPv6 por padrão em redes com e sem fio. Se você quiser controlar as comunicações com o SharePoint Online, use os intervalos de endereços IP nas URLs e intervalos de endereços IP do [Office 365.](urls-and-ip-address-ranges.md)
  
 **Office 365 Government G1/G3/G4/K1** Se o programa que você usa para se conectar ao SharePoint Online oferece suporte a IPv6, ele tentará usar IPv6 por padrão.
  
### <a name="skype-for-business-and-ipv6"></a>Skype for Business e IPv6

Lembre-se de que o IPv6 não é suportado no Skype for Business e não pode mais ser habilitado.

### <a name="microsoft-teams-and-ipv6"></a>Microsoft Teams e IPV6

O Roteamento Direto do Microsoft Teams é compatível apenas com IPv4. O serviço e o cliente do Microsoft Teams suportam IPv4 e IPv6. Se você quiser controlar as comunicações com o Microsoft Teams, use os intervalos de endereços IP nas URLs e intervalos de endereços IP do [Office 365.](urls-and-ip-address-ranges.md)
  
### <a name="exchange-online-protection-and-ipv6"></a>Proteção do Exchange Online e IPv6

O Exchange Online Protection (EOP) dá suporte a IPv6 se a transmissão ocorrer por meio do Protocolo de Segurança da Camada de Transporte. Para o intervalo de EOP, use URLs e intervalos de [endereços IP do Office 365.](urls-and-ip-address-ranges.md)
  
### <a name="ipv6-support-for-office-365-government-offerings"></a>Suporte a IPv6 para ofertas governamentais do Office 365

O suporte a IPv6 do Office 365 para ofertas governamentais está em conformidade com o Memorando do Office of Management and Budget (OMB) para Diretores de Informações de Departamentos e Agências Executivos, bem como o memorando Adoção do Protocolo IPv6 (Federal Government Adoption of Internet Protocol Version 6) (IPv6). [O Microsoft Office 365 para](https://go.microsoft.com/fwlink/p/?LinkId=325414) o Governo é um serviço multi-inquilino que armazena dados do governo dos EUA em uma nuvem de comunidade segregada. Como outras ofertas do Office 365, ela fornece serviços de colaboração e produtividade, incluindo o Exchange Online, o Skype for Business, o SharePoint Online e o Microsoft 365 Apps para empresas. 

As ofertas governamentais do Microsoft Office 365 se aplicam somente a 2013 e posteriores. Para saber mais sobre as ofertas governamentais do Office 365, confira Anúncio do [Office 365 para](https://go.microsoft.com/fwlink/p/?LinkId=325414)o Governo: Nuvem da Comunidade Governamental dos EUA. O ITAR (International Traffic in Arms Regulations) é um conjunto de regulamentações do governo dos EUA que controlam a exportação e a importação de artigos e serviços relacionados à defesa na [USML (Lista](https://go.microsoft.com/fwlink/p/?LinkId=325415)de Uniformes dos Estados Unidos). 

O Microsoft Office 365 para empresas fornece serviços de hospedagem dedicados para soluções de produtividade da Microsoft que suportam os requisitos de segurança, privacidade e conformidade regulamentar para agências federais dos EUA que exigem certificação FISMA (Federal Information Security Management) e entidades comerciais sujeitas ao ITAR.
  
## <a name="things-to-consider-when-using-ipv6-and-office-365"></a>Pontos a considerar ao usar o IPv6 e o Office 365

Recomendamos que você não desabilite o IPv6. Para obter mais informações, consulte [este artigo de orientação.](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users) Para determinar quais versões IP estão sendo usadas em sua rede, considere o seguinte:
  
- Se a exibição do comando **IPConfig** no prompt de comando contiver linhas chamadas "Endereço IPv6" ou "Endereço IPv6 Temporário", você terá IPv6 em seu ambiente.

- Se todos os endereços IPv6 começarem com "fe80" e corresponderem às linhas chamadas "Endereço IPv6 Link-Local", você não terá IPv6 em seu ambiente.

Estas considerações podem se aplicar à sua rede:
  
- O serviço de assinatura pública não dá suporte à compra por cartão de crédito por IPv6. Isso não se aplica à Nuvem da Comunidade Governamental (GCC) porque os governos têm licenciamento do Enterprise Agreement (EA).

- O IPv6 não dá suporte a alguns cenários do RMS (Rights Management Services).

- O IPv6 não dá suporte ao BlackBerry® Enterprise Server (BES) porque o BlackBerry não dá suporte a IPv6.

- Se você usar os Serviços de Federação do Active Directory (AD FS) com o Office 365, não será possível anunciar seu ponto de extremidade de rede do AD FS para o Office 365 usando IPv6. Você não deve incluir registros AAAA na entrada DNS do AD FS ao usar o Exchange Online. 

Aqui está um link curto que você pode usar para voltar: [https://aka.ms/o365ip6](https://aka.ms/o365ip6)
  
## <a name="see-also"></a>Confira também

[Roteiro de aprendizagem IPv6](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))
  
[Guia de sobrevivência do IPv6](https://social.technet.microsoft.com/wiki/contents/articles/1728.ipv6-survival-guide.aspx)
