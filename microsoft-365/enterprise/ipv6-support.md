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

O Office 365 oferece suporte a IPv6 e IPv4; no entanto, nem todos os recursos do Office 365 estão totalmente habilitados com IPv6. Isso significa que você deve usar IPv4 e IPv6 para se conectar ao Office 365. Se estiver filtrando o tráfego de saída para o Office 365, a lista completa de endereços IPv6 compatíveis com o Office 365 pode ser encontrada no artigo [office 365 URLs and IP address Ranges](urls-and-ip-address-ranges.md). Depois que a rede estiver configurada e os endereços IPv6 apropriados forem permitidos, você poderá baixar o [plano de teste do IPv6 do Office 365](https://go.microsoft.com/fwlink/?LinkId=293447) no centro de download da Microsoft.
  
## <a name="ipv6-support-in-office-365-subscription-service"></a>Suporte a IPv6 no serviço de assinatura do Office 365

### <a name="exchange-online-and-ipv6"></a>Exchange Online e IPv6

Se o programa que você usa para se conectar ao Exchange Online oferecer suporte a IPv6, ele usará IPv6 por padrão em redes com e sem fio. Se você quiser controlar as comunicações com o Exchange Online, use os intervalos de endereços IP nas [URLs e intervalos de endereços IP do Office 365](urls-and-ip-address-ranges.md).
  
### <a name="sharepoint-online-and-ipv6"></a>SharePoint Online e IPv6

 **Office 365 governo G1/G3/G4/K1** Se o programa que você usa para se conectar ao SharePoint Online oferece suporte a IPv6, ele tentará usar IPv6 por padrão.
  
 **Nuvem de vários locatários públicos** A Microsoft habilita o SharePoint Online IPv6 na sua solicitação. Você precisa fornecer os endereços IP de CIDR intated para a infraestrutura de DNS da sua organização. Tenha em mente que esta infraestrutura de DNS não pode ser compartilhada por outras organizações para que o IPv6 seja habilitado para seu locatário. Após a habilitação do IPv6, se o programa que você usa para se conectar ao SharePoint Online oferece suporte a IPv6, ele usa IPv6 por padrão.
  
Se o programa que você usa para se conectar ao SharePoint Online oferece suporte a IPv6, ele usará IPv6 por padrão em redes com e sem fio. Se você quiser controlar as comunicações com o SharePoint Online, use os intervalos de endereços IP nas [URLs e intervalos de endereços IP do Office 365](urls-and-ip-address-ranges.md).
  
 **Office 365 governo G1/G3/G4/K1** Se o programa que você usa para se conectar ao SharePoint Online oferece suporte a IPv6, ele tentará usar IPv6 por padrão.
  
### <a name="skype-for-business-and-ipv6"></a>Skype for Business e IPv6

Não há suporte para o IPv6 no Skype for Business e ele não pode mais ser habilitado.

### <a name="microsoft-teams-and-ipv6"></a>Microsoft Teams e IPV6

O Microsoft Teams Direct Routing só oferece suporte a IPv4. O Microsoft Teams Service e o cliente dão suporte a IPv4 e IPv6. Se você quiser controlar as comunicações com o Microsoft Teams, use os intervalos de endereços IP nas [URLs e intervalos de endereços IP do Office 365](urls-and-ip-address-ranges.md).
  
### <a name="exchange-online-protection-and-ipv6"></a>Proteção do Exchange Online e IPv6

O proteção do Exchange Online (EOP) oferece suporte ao IPv6 se a transmissão ocorrer no protocolo de segurança da camada de transporte. Para o intervalo EOP, use as [URLs e intervalos de endereços IP do Office 365](urls-and-ip-address-ranges.md).
  
### <a name="ipv6-support-for-office-365-government-offerings"></a>Suporte a IPv6 para ofertas governamentais do Office 365

O Office 365 IPv6 support para ofertas governamentais está em conformidade com o Office of Management and Budget (OMB) Memorandum para os principais gerentes de informações de departamentos e agências de executivos, bem como a adoção governamental do governo federal do Internet Protocol version 6 (IPv6) Memorandum. [O Microsoft Office 365 para o governo](https://go.microsoft.com/fwlink/p/?LinkId=325414) é um serviço de vários locatários que armazena dados do governo dos EUA em uma nuvem de comunidade segregada. Como outras ofertas do Office 365, ele fornece serviços de produtividade e colaboração, incluindo o Exchange Online, o Skype for Business, o SharePoint Online e os aplicativos do Microsoft 365 para empresas. 

As ofertas do governo do Microsoft Office 365 aplicam-se apenas aos 2013 e posteriores. Para obter mais informações sobre as ofertas governamentais do Office 365, consulte [anunciando o Office 365 para o governo: uma nuvem da Comunidade do governo dos EUA](https://go.microsoft.com/fwlink/p/?LinkId=325414). O tráfego internacional em normas de braços (ITAR) é um conjunto de regulamentações governamentais dos EUA que controlam a exportação e a importação de artigos e serviços relacionados à defesa na [lista de munitions (USML) dos Estados Unidos](https://go.microsoft.com/fwlink/p/?LinkId=325415). 

O Microsoft Office 365 para empresas fornece serviços de hospedagem dedicados para soluções de produtividade da Microsoft que oferecem suporte a segurança, privacidade e requisitos de conformidade normativa para agências federais dos EUA que exigem a certificação do Federal Information Security Management (FISMA) e entidades comerciais sujeitas ao ITAR.
  
## <a name="things-to-consider-when-using-ipv6-and-office-365"></a>Considerações a serem consideradas ao usar o IPv6 e o Office 365

Recomendamos que você não desative o IPv6. Para obter mais informações, consulte este [artigo de diretrizes](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users). Para determinar quais versões IP estão sendo usadas em sua rede, considere o seguinte:
  
- Se a exibição do comando **ipconfig** no prompt de comando contiver linhas chamadas "endereço IPv6" ou "endereço IPv6 temporário", você tem IPv6 em seu ambiente.

- Se todos os endereços IPv6 começam com "FE80" e correspondem a linhas chamadas "endereço IPv6 link-local", você não tem IPv6 em seu ambiente.

Essas considerações podem se aplicar à sua rede:
  
- O serviço de assinatura pública não dá suporte a compra por cartão de crédito sobre IPv6. Isso não se aplica à GCC (nuvem da Comunidade governamental) porque os governos têm licenciamento do Enterprise Agreement (EA).

- O IPv6 não oferece suporte a alguns cenários de serviços de gerenciamento de direitos (RMS).

- O IPv6 não oferece suporte a BlackBerry® Enterprise Server (BES) porque o BlackBerry não dá suporte a IPv6.

- Se você usar o AD FS (serviços de Federação do Active Directory) com o Office 365, não será possível anunciar o ponto de extremidade de rede do AD FS para o Office 365 usando IPv6. Você não deve incluir registros AAAA na entrada DNS do AD FS ao usar o Exchange Online. 

Aqui está um link curto que você pode usar para voltar: [https://aka.ms/o365ip6](https://aka.ms/o365ip6)
  
## <a name="see-also"></a>Confira também

[Roteiro de aprendizado IPv6](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))
  
[Guia de sobrevivência do IPv6](https://social.technet.microsoft.com/wiki/contents/articles/1728.ipv6-survival-guide.aspx)
