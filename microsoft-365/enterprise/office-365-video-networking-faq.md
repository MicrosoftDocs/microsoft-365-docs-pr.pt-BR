---
title: Redes de vídeo do Office 365 perguntas frequentes
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 3/14/2019
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 2bed67a1-4052-49ff-a4ce-b7e6530eb98e
ms.custom:
- Adm_O365
- seo-marvel-apr2020
description: Encontre respostas para algumas das perguntas mais frequentes sobre planejamento de largura de banda, criptografia, & como o serviço aproveita as CDNs (Redes de Entrega de Conteúdo).
ms.openlocfilehash: 8bc0a69ff744967d24aa7d21ed6daee1a839f159
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921565"
---
# <a name="office-365-video-networking-frequently-asked-questions"></a>Redes de vídeo do Office 365 perguntas frequentes

O repositório de vídeo e serviços de streaming do Office 365 torna simples o armazenamento e a transmissão de vídeos em sua organização. Há muitas informações excelentes [sobre o Vídeo do Office 365;](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50) essa perguntas [frequentes](content-delivery-networks.md) de rede foi projetada para responder às perguntas mais comuns sobre planejamento de largura de banda, criptografia e como o serviço aproveita as CDNs (Redes de Entrega de Conteúdo).
  
Se você ainda não tiver uma compreensão completa do que acontece quando um vídeo é carregado ou tocado de volta, confira este vídeo que juntamos, o que acontece com um arquivo de vídeo quando carregado no [Vídeo do Office 365](https://www.youtube.com/watch?v=HXSZ0jYBKlM).
  
## <a name="what-are-the-office-365-video-bandwidth-requirements"></a>Quais são os requisitos de largura de banda do Office 365 Video?

Há vários formatos de vídeo com suporte que podem ser [carregados](https://support.office.com/article/dd1af01c-fd8e-4640-b17b-93ee02b9b817) no Office 365. Cada arquivo de vídeo é codificado em um formato padrão com várias qualidades de vídeo diferentes para reprodução. O Vídeo do Office 365 usa streaming de taxa de bits adaptável para selecionar a melhor qualidade de reprodução de vídeo com base na largura de banda de rede disponível e no tamanho do player de vídeo. Para fazer isso, o jogador solicita inicialmente a menor qualidade de reprodução. Em seguida, o serviço começa a enviar segmentos de vídeo de 2 segundos para o player de vídeo. Em seguida, o jogador pode solicitar uma qualidade de reprodução maior ou menor com base na rapidez com que cada segmento é entregue.
  
O streaming de bitrate adaptável faz tudo isso em segundo plano enquanto o vídeo é reproduzindo com a menor quantidade de interrupção ou buffer. Durante a reprodução de vídeo, o player de vídeo permite que o visualizador substitua manualmente a qualidade de reprodução automática, para selecionar uma qualidade específica de reprodução de vídeo.
  
Aqui está uma tabela rápida que descreve os requisitos de rede para cada uma das qualidades de reprodução de vídeo. A largura de banda mínima por pessoa necessária para reproduzir um vídeo é de 802 Kbps.
  
| Qualidade de reprodução | Velocidade da rede |
|:-----|:-----|
|288p  <br/> |802Kbps  <br/> |
|360p  <br/> |1,2 Mbps  <br/> |
|576p  <br/> |2,5 Mbps  <br/> |
|720p  <br/> |3,8 Mbps  <br/> |

([Voltar para cima](office-365-video-networking-faq.md))
  
## <a name="how-do-content-delivery-networks-cdns-help-video-playback"></a>Como as CDNs (Redes de Entrega de Conteúdo) ajudam a reprodução de vídeo?

Se várias pessoas da mesma organização dentro da mesma localização geográfica estão transmitindo os mesmos vídeos, as CDNs armazenarão uma cópia desses vídeos em um local mais próximo dessa região geográfica. Com o vídeo armazenado ou armazenado em cache no local mais próximo, cada pessoa transmite o vídeo do local mais próximo a eles, em vez de um local mais distante. O Vídeo do Office 365 usa os Serviços de Mídia do Azure para gerenciar o que é armazenado em cache nas CDNs do Azure e por quanto tempo. Os Serviços de Mídia do Azure podem usar qualquer um dos locais da CDN do [Azure](/azure/cdn/cdn-pop-locations) para armazenar em cache fragmentos de vídeo e manifestos por alguns dias. Se as pessoas em sua organização continuarem a assistir aos vídeos armazenados em cache, elas permanecerão no cache. Se ninguém acessar o vídeo por vários dias, o vídeo será descartado do cache. Na próxima vez que alguém tentar assistir ao vídeo, ele será novamente armazenado em cache no local da CDN mais próximo.
  
Todos os que tentarem assistir ao vídeo enquanto o conteúdo é armazenado em cache em uma CDN próxima se beneficiam de o vídeo estar mais próximo e, na maioria dos casos, menos saltos, de distância. Isso melhora a velocidade de reprodução de vídeo; no entanto, ele não altera o requisito de rede para reproduzir o vídeo.
  
> [!NOTE]
> Há algumas circunstâncias, como o limite de capacidade que está sendo atingido, em que o vídeo pode ser removido antes que os três dias sejam atingidos.
  
([Voltar para cima](office-365-video-networking-faq.md))
  
## <a name="can-i-cache-the-videos-locally-for-faster-playback"></a>Posso armazenar em cache os vídeos localmente para reprodução mais rápida?

Sim. O Office 365 não impedirá que você use uma CDN local ou um proxy de cache para trazer vídeo ou outro conteúdo do Office 365 para sua rede local para acesso mais rápido. Há várias maneiras de implementar uma solução de cache local em sua rede, o método mais comum é usar uma solução proxy que armazena em cache o conteúdo localmente. Depois que um proxy ou CDN privado armazena em cache os fragmentos e manifestos de vídeo, as solicitações futuras para os arquivos que roteiam pelo proxy ou pela CDN privada são retiradas do cache local e não são retiradas de um local da Internet. Considere a simultância de largura de banda, capacidade e reprodução de vídeo durante o planejamento de uma solução como esta.
  
([Voltar para cima](office-365-video-networking-faq.md))
  
## <a name="how-videos-are-encrypted-and-secured"></a>Como os vídeos são criptografados e protegidos?

O Vídeo do Office 365 sabe o quanto é importante manter seus dados seguros e privados. [A Central de Confiações da Microsoft](https://products.office.com/business/office-365-trust-center-welcome) descreve nosso compromisso com a privacidade e a segurança de seu conteúdo. Com a reprodução de vídeo, a velocidade é importante para uma boa experiência; no entanto, não comprometemos sua segurança ou privacidade em troca da velocidade. Veja como acomodamos velocidade, segurança e privacidade.
  
Quando você ou alguém em sua organização carrega um novo vídeo, esse vídeo é transcodificado, criptografado com criptografia do AES-128 e armazenado no Azure Media Services. Isso significa que os vídeos são criptografados em trânsito e em repouso.
  
Quando alguém em sua organização tenta assistir a um novo vídeo, ele segue estas etapas:
  
1. Pergunte ao SharePoint Online se eles têm permissão para exibir o vídeo.

2. O SharePoint Online usa as permissões de arquivo para determinar se a pessoa pode assistir ao vídeo.

3. Se eles são permitidos, o SharePoint Online recupera um token do Azure para dar ao player de vídeo.

4. Em seguida, o player de vídeo usa o token para solicitar a chave de descriptografia do Azure.

5. Com a chave de descriptografia na mão, o player de vídeo é capaz de transmitir o vídeo.

![Reprodução de vídeo do O365](../media/9d3c6e76-151d-48a3-a30e-ba8dd07db0b7.png)
  
([Voltar para cima](office-365-video-networking-faq.md))
  
## <a name="what-are-the-requirements-to-playback-office-365-video"></a>Quais são os requisitos para reproduzir o Vídeo do Office 365?

Os sistemas operacionais e navegadores da Web com suporte do Office 365 Video são os mesmos dos requisitos do SharePoint Online nos requisitos do sistema [do Office 365.](https://support.office.com/article/Office-365-system-requirements-719254c0-2671-4648-9c84-c6a3d4f3be45) Dependendo da configuração do sistema operacional e do navegador da Web, você determinará as necessidades específicas do player de vídeo. Veja mais informações sobre os [requisitos de reprodução de vídeo.](https://support.office.com/article/ca1cc1a9-a615-46e1-b6a3-40dbd99939a6)
  
([Voltar para cima](office-365-video-networking-faq.md))
  
## <a name="i-cant-get-office-365-video-to-work-where-should-i-start"></a>Não consigo fazer com que o vídeo do Office 365 funcione, por onde devo começar?

A solução de problemas de conectividade com o Vídeo do Office 365 envolve a solução de problemas de sua rede, seus ISP(s) e sua configuração do Office 365. O primeiro lugar para iniciar é o painel de saúde do serviço. Isso dirá que o Vídeo do Office 365 está com um problema ou não. Se tudo estiver ótimo lá, aqui estão alguns recursos adicionais para ajudá-lo.
  
- Certifique-se de que você pode se conectar aos pontos de extremidade de [rede necessários para o Vídeo do Office 365.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)

- Verifique a conectividade de rede usando nosso guia de solução de problemas de rede do [Office 365.](https://support.office.com/article/Office-365-performance-tuning-and-troubleshooting-Admin-and-IT-Pro-1492cb94-bd62-43e6-b8d0-2a61ed88ebae)

- Consulte nossas [práticas recomendadas para usar o Office 365 em uma rede lenta.](https://support.office.com/article/Best-practices-for-using-Office-365-on-a-slow-network-fd16c8d2-4799-4c39-8fd7-045f06640166)

- Encontre ajuda sobre a configuração de vídeo do [Office 365.](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50)

([Voltar para cima](office-365-video-networking-faq.md))
  
## <a name="office-365-video-resources"></a>Recursos de vídeo do Office 365

Aqui estão alguns outros recursos para ajudá-lo a implantar e usar o Vídeo do Office 365 com êxito:
  
[Encontre ajuda sobre a configuração de vídeo do Office 365](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50)
  
[Conheça o Vídeo do Office 365](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6)
  
[Criar e gerenciar um canal no Vídeo do Office 365](https://support.office.com/article/Create-and-manage-a-channel-in-Office-365-Video-1fede4cc-13c0-435a-b585-e7fbf1c83bb2)
  
[Gerenciar portal de Vídeo do Office 365](https://support.office.com/article/Manage-your-Office-365-Video-portal-c059465b-eba9-44e1-b8c7-8ff7793ff5da)
  
[Formatos de vídeo que funcionam no Vídeo do Office 365](https://support.office.com/article/Video-formats-that-work-in-Office-365-Video-dd1af01c-fd8e-4640-b17b-93ee02b9b817)
  
([Voltar para cima](office-365-video-networking-faq.md))
  
Aqui está um link curto que você pode usar para voltar: [https://aka.ms/video365networkfaq]()