---
title: Perguntas frequentes sobre o sistema de rede de vídeo do Office 365
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
description: Encontre respostas para algumas das perguntas mais frequentes sobre planejamento de largura de banda, criptografia & como o serviço aproveita as redes de distribuição de conteúdo (CDNs).
ms.openlocfilehash: e08a67988290e7ead87ff30a5ebdf9c8560f4825
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695312"
---
# <a name="office-365-video-networking-frequently-asked-questions"></a>Perguntas frequentes sobre o sistema de rede de vídeo do Office 365

O repositório de vídeo do Office 365 e os serviços de streaming facilitam o armazenamento e o fluxo de vídeo em sua organização. Há muitas informações importantes sobre o [vídeo do Office 365](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50); essas perguntas frequentes de rede são projetadas para responder às perguntas mais comuns sobre planejamento de largura de banda, criptografia e como o serviço aproveita as [redes de distribuição de conteúdo](content-delivery-networks.md) (CDNs).
  
Se você ainda não tem uma compreensão completa do que acontece quando um vídeo é carregado ou reproduzido, examine este vídeo que incluímos, [o que acontece com um arquivo de vídeo quando carregado no vídeo do Office 365](https://www.youtube.com/watch?v=HXSZ0jYBKlM).
  
## <a name="what-are-the-office-365-video-bandwidth-requirements"></a>Quais são os requisitos de largura de banda de vídeo do Office 365?

Há vários formatos de [vídeo com suporte](https://support.office.com/article/dd1af01c-fd8e-4640-b17b-93ee02b9b817) que podem ser carregados no Office 365. Cada arquivo de vídeo é então codificado para um formato padrão com várias qualidades de vídeo diferentes para reprodução. O vídeo do Office 365 usa o fluxo de taxa de bits adaptável para selecionar a melhor qualidade de reprodução de vídeo com base na largura de banda de rede disponível e no tamanho do player de vídeo. Para fazer isso, o Player inicialmente solicita a qualidade de reprodução mais baixa. O serviço começa a enviar segmentos de vídeo de 2 segundos para o player de vídeo. O player pode solicitar uma qualidade de reprodução superior ou inferior com base em quão rapidamente cada segmento é entregue.
  
O streaming de taxa de bits adaptável faz tudo isso em segundo plano enquanto o vídeo é reproduzido com a menor quantidade de interrupções ou buffering. Durante a reprodução de vídeo, o player de vídeo permite que o visualizador substitua manualmente a qualidade de reprodução automática, para selecionar uma qualidade de reprodução de vídeo específica.
  
Aqui está uma tabela rápida que descreve os requisitos de rede para cada uma das qualidades de reprodução de vídeo. A largura de banda mínima por pessoa necessária para reproduzir um vídeo é o 802Kbps.
  
| Qualidade de reprodução | Velocidade da rede |
|:-----|:-----|
|288p  <br/> |802Kbps  <br/> |
|360p  <br/> |1,2 Mbps  <br/> |
|576p  <br/> |2,5 Mbps  <br/> |
|720p  <br/> |3,8 Mbps  <br/> |

([Voltar ao início](office-365-video-networking-faq.md))
  
## <a name="how-do-content-delivery-networks-cdns-help-video-playback"></a>Como as redes de distribuição de conteúdo (CDNs) ajudam a reprodução de vídeo?

Se várias pessoas da mesma organização dentro da mesma localização geográfica estiverem transmitindo o mesmo (s) vídeo (s), o CDNs armazenará uma cópia desses vídeos em um local mais próximo da região geográfica. Com o vídeo armazenado ou armazenado em cache no local mais próximo, cada pessoa transmite o vídeo do local mais próximo a eles, em vez de um local mais distante. O vídeo do Office 365 usa os serviços de mídia do Azure para gerenciar o que é armazenado em cache no CDNs do Azure e por quanto tempo. Os serviços de mídia do Azure podem usar qualquer um dos [locais de CDN do Azure](https://azure.microsoft.com/documentation/articles/cdn-pop-locations/) para armazenar em cache fragmentos de vídeo e manifestos por alguns dias. Se as pessoas em sua organização continuarem a assistir aos vídeos em cache, elas permanecerão no cache. Se ninguém acessar o vídeo por vários dias, o vídeo eventualmente será removido do cache. Na próxima vez que alguém tentar assistir ao vídeo, ele será novamente armazenado em cache no local da CDN mais próximo.
  
Todos que tentarem assistir ao vídeo enquanto o conteúdo é armazenado em cache em uma CDN próxima, os benefícios do vídeo estão mais próximos e, na maioria dos casos, menos saltos. Isso melhora a velocidade de reprodução de vídeo; no entanto, ele não altera o requisito de rede para reproduzir o vídeo.
  
> [!NOTE]
> Há algumas circunstâncias, como o limite de capacidade sendo alcançado, onde o vídeo pode ser removido antes que os três dias tenham sido alcançados.
  
([Voltar ao início](office-365-video-networking-faq.md))
  
## <a name="can-i-cache-the-videos-locally-for-faster-playback"></a>Posso armazenar em cache os vídeos localmente para uma reprodução mais rápida?

Sim. O Office 365 não impede que você use uma CDN local ou um proxy de cache para trazer vídeo ou outro conteúdo do Office 365 para sua rede local para acesso mais rápido. Há várias maneiras de implementar uma solução de cache local em sua rede, o método mais comum é usar uma solução de proxy que armazena o conteúdo em cache localmente. Depois que um proxy ou CDN privada armazenar em cache os fragmentos e manifestos de vídeo, solicitações futuras para os arquivos que roteiam o proxy ou CDN privada serão extraídas do cache local e não obtidas de um local da Internet. Considere a largura de banda da rede, a capacidade e a simultaneidade de reprodução de vídeo durante o planejamento de uma solução como esta.
  
([Voltar ao início](office-365-video-networking-faq.md))
  
## <a name="how-videos-are-encrypted-and-secured"></a>Como os vídeos são criptografados e protegidos?

O vídeo do Office 365 sabe como é importante manter seus dados seguros e privados. A [central de confiabilidade da Microsoft](https://products.office.com/business/office-365-trust-center-welcome) descreve nosso compromisso com a privacidade e a segurança do conteúdo. Com a reprodução de vídeo, a velocidade é importante para uma boa experiência; no entanto, não comprometemos sua segurança ou privacidade na velocidade do Exchange. Veja como acomodamos velocidade, segurança e privacidade.
  
Quando você ou alguém de sua organização carrega um novo vídeo, esse vídeo é transcodificado, criptografado com a criptografia AES-128 e armazenado nos serviços de mídia do Azure. Isso significa que os vídeos são criptografados em trânsito e em repouso.
  
Quando alguém em sua organização tentar assistir a um novo vídeo, ele seguirá estas etapas:
  
1. Pergunte ao SharePoint Online se ele tem permissão para exibir o vídeo.

2. O SharePoint Online usa as permissões de arquivo para determinar se a pessoa pode assistir ao vídeo.

3. Se eles forem permitidos, o SharePoint Online recuperará um token do Azure para fornecer ao Player de vídeo.

4. O player de vídeo usa o token para solicitar a chave de descriptografia do Azure.

5. Com a chave de descriptografia em mãos, o player de vídeo é capaz de transmitir o vídeo.

![Reprodução de vídeo do O365](../media/9d3c6e76-151d-48a3-a30e-ba8dd07db0b7.png)
  
([Voltar ao início](office-365-video-networking-faq.md))
  
## <a name="what-are-the-requirements-to-playback-office-365-video"></a>Quais são os requisitos para reproduzir vídeo do Office 365?

Os sistemas operacionais e navegadores da Web com suporte para vídeo do Office 365 são os mesmos que os requisitos do SharePoint Online nos [requisitos de sistema do Office 365](https://support.office.com/article/Office-365-system-requirements-719254c0-2671-4648-9c84-c6a3d4f3be45). Dependendo do sistema operacional e da configuração do navegador da Web, você determinará as necessidades específicas do player de vídeo. Veja mais informações sobre [os requisitos de reprodução de vídeo](https://support.office.com/article/ca1cc1a9-a615-46e1-b6a3-40dbd99939a6).
  
([Voltar ao início](office-365-video-networking-faq.md))
  
## <a name="i-cant-get-office-365-video-to-work-where-should-i-start"></a>Não consigo obter o vídeo do Office 365 para funcionar, onde devo começar?

Solucionando problemas de conectividade com o vídeo do Office 365 envolve a solução de problemas de sua rede, seus provedores e a configuração do Office 365. O primeiro lugar a ser iniciado é o painel de integridade do serviço. Isso informará que o vídeo do Office 365 está com problema ou não. Se tudo parece ótimo, veja a seguir alguns recursos adicionais para ajudá-lo.
  
- Certifique-se de que você pode se conectar aos [pontos de extremidade da rede necessários para o vídeo do Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2).

- Verifique a conectividade de rede usando o [Guia de solução de problemas de rede do Office 365](https://support.office.com/article/Office-365-performance-tuning-and-troubleshooting-Admin-and-IT-Pro-1492cb94-bd62-43e6-b8d0-2a61ed88ebae).

- Consulte nossas [práticas recomendadas para usar o Office 365 em uma rede lenta](https://support.office.com/article/Best-practices-for-using-Office-365-on-a-slow-network-fd16c8d2-4799-4c39-8fd7-045f06640166).

- [Encontre ajuda sobre a configuração de vídeo do Office 365](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50).

([Voltar ao início](office-365-video-networking-faq.md))
  
## <a name="office-365-video-resources"></a>Recursos de vídeo do Office 365

Veja alguns outros recursos para ajudá-lo a implantar e usar com êxito o vídeo do Office 365:
  
[Encontre ajuda sobre a configuração de vídeo do Office 365](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50)
  
[Conheça o Vídeo do Office 365](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6)
  
[Criar e gerenciar um canal no Office 365 vídeo](https://support.office.com/article/Create-and-manage-a-channel-in-Office-365-Video-1fede4cc-13c0-435a-b585-e7fbf1c83bb2)
  
[Gerenciar portal de Vídeo do Office 365](https://support.office.com/article/Manage-your-Office-365-Video-portal-c059465b-eba9-44e1-b8c7-8ff7793ff5da)
  
[Formatos de vídeo que funcionam no Office 365 vídeo](https://support.office.com/article/Video-formats-that-work-in-Office-365-Video-dd1af01c-fd8e-4640-b17b-93ee02b9b817)
  
([Voltar ao início](office-365-video-networking-faq.md))
  
Aqui está um link curto que você pode usar para voltar: [https://aka.ms/video365networkfaq](https://aka.ms/video365networkfaq)
