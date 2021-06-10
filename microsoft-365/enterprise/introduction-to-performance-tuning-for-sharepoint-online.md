---
title: Introdução ao ajuste de desempenho para o SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/22/2018
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid: SPO160
ms.assetid: 81c4be5f-327e-435d-a568-526d68cffef0
description: Este artigo explica quais aspectos específicos você precisa considerar ao projetar páginas para melhor desempenho no SharePoint Online.
ms.openlocfilehash: 6f40243c9d6a1657b6716a071288f5b4fb018164
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909733"
---
# <a name="introduction-to-performance-tuning-for-sharepoint-online"></a>Introdução ao ajuste de desempenho para o SharePoint Online

Este artigo explica quais aspectos específicos você precisa considerar ao projetar páginas para melhor desempenho no SharePoint Online.
     
## <a name="sharepoint-online-metrics"></a>SharePoint Métricas online

As seguintes métricas amplas para o SharePoint Online fornecem dados reais sobre o desempenho:
  
- Como as páginas são carregadas rapidamente
    
- Quantas viagens de ida e volta são necessárias por página
    
- Problemas com o serviço
    
- Outras coisas que causam degradação de desempenho
    
### <a name="conclusions-reached-because-of-the-data"></a>Conclusões atingidas por causa dos dados

Os dados nos informam:
  
- A maioria das páginas tem um bom desempenho no SharePoint Online.
    
- Páginas não personalizadas são carregadas muito rapidamente.
    
- OneDrive for Business, sites de equipe e páginas do sistema, como _layouts, etc., são todos rápidos de carregar.
    
- Os 1% mais lentos SharePoint online levam mais de 5.000 milissegundos para carregar.
    
Um teste de referência simples que você pode usar seria medir o desempenho comparando o tempo de carga do seu próprio portal com o tempo de carregamento da home page do OneDrive for Business, pois ele usa poucos recursos personalizados. Geralmente, essa será a primeira etapa que o Suporte solicitará que você conclua ao solucionar problemas de desempenho da rede.
  
## <a name="use-a-standard-user-account-when-checking-performance"></a>Usar uma conta de usuário padrão ao verificar o desempenho

Um Administrador do Conjunto de Sites, Proprietário do Site, Editor ou Colaborador pertence a grupos de segurança adicionais, têm permissões adicionais e, portanto, têm elementos adicionais que SharePoint carregam em uma página.
  
Isso é aplicável ao SharePoint local e ao SharePoint Online, mas em um cenário local, as diferenças não serão notáveis tão facilmente quanto no SharePoint Online.
  
Para avaliar corretamente como uma página será usada para usuários, você deve usar uma conta de usuário padrão para evitar carregar os controles de autoria e o tráfego adicional relacionado a grupos de segurança.
  
## <a name="connection-categories-for-performance-tuning"></a>Categorias de conexão para ajuste de desempenho

Você pode categorizar as conexões entre o servidor e o usuário em três componentes principais. Considere-os ao projetar SharePoint online para informações sobre os tempos de carregamento.
  
- **Servidor** Os servidores que a Microsoft hospeda em datacenters.
    
- **Rede** A rede da Microsoft, a Internet e sua rede local entre o datacenter e seus usuários.
    
- **Navegador** Onde a página é carregada.
    
Dentro dessas três conexões, há normalmente cinco motivos que causam 95% de páginas lentas. Cada um desses motivos é discutido neste artigo:
  
- Problemas de navegação
    
- Roll up de conteúdo
    
- Arquivos grandes
    
- Muitas solicitações para o servidor
    
- Processamento de Web Part
    
### <a name="server-connection"></a>Conexão de servidor

Muitos dos problemas que afetam o desempenho SharePoint local também se aplicam ao SharePoint Online.
  
Como você poderia esperar, você tem muito mais controle sobre como os servidores se executam com os SharePoint. Com SharePoint online as coisas são um pouco diferentes. Quanto mais trabalho você faz um servidor, mais tempo leva para renderizar uma página. Com SharePoint, o maior responsável por esse aspecto são páginas complexas com várias Web Parts.
  
SharePoint Servidor local
  
![Captura de tela do servidor local](../media/a8e9b646-cdff-4131-976a-b5f891da44ac.png)
  
SharePoint Online
  
![Captura de tela do servidor online](../media/46b27ded-d8a4-4287-b3e0-2603a764b8f8.png)
  
Com SharePoint Online, determinadas solicitações de página podem realmente acabar chamando vários servidores. Você pode acabar com uma matriz de solicitações entre servidores para uma solicitação individual. Essas interações são caras de uma perspectiva de carga de página e tornarão as coisas lentas.
  
Exemplos dessas interações de servidor para servidor são:
  
- Web para SQL Servidores
    
- Servidores web para aplicativos
    
A outra coisa que pode diminuir a velocidade das interações do servidor são erros de cache. Ao contrário do SharePoint local, há uma chance muito pequena de você atingir o mesmo servidor para uma página que você visitou anteriormente; isso torna o cache de objeto obsoleto.
  
### <a name="network-connection"></a>Conexão de rede

Com um SharePoint local que não usa uma WAN, você pode usar uma conexão de alta velocidade entre o datacenter e os usuários finais. Geralmente, as coisas são fáceis de gerenciar de uma perspectiva de rede.
  
Com SharePoint Online, há mais alguns fatores a considerar; por exemplo:
  
- A rede da Microsoft
    
- A Internet
    
- O ISP
    
Independentemente de qual versão do SharePoint (e qual rede) você está usando, as coisas que normalmente fazem com que a rede seja ocupada incluem:
  
- Carga grande
    
- Muitos arquivos
    
- Distância física grande para o servidor
    
Um recurso que você pode aproveitar no SharePoint Online é o Microsoft CDN (Rede de Distribuição de Conteúdo). Um CDN é basicamente uma coleção distribuída de servidores implantados em vários datacenters. Com uma CDN, o conteúdo em páginas pode ser hospedado em um servidor próximo ao cliente, mesmo se o cliente estiver longe do servidor SharePoint server. A Microsoft estará usando isso mais no futuro para armazenar instâncias locais de páginas que não podem ser personalizadas, por exemplo, a home page do administrador SharePoint Online. Para obter mais informações sobre CDNs, consulte [Redes de entrega de conteúdo.](content-delivery-networks.md)
  
Algo que você precisa estar ciente, mas pode não ser capaz de fazer muito sobre a velocidade de conexão de seu ISP. Uma ferramenta de teste de velocidade simples dirá a velocidade da conexão.
  
### <a name="browser-connection"></a>Conexão do navegador

Há alguns fatores a considerar com navegadores da Web de uma perspectiva de desempenho.
  
Visitar páginas complexas afetará o desempenho. A maioria dos navegadores tem apenas um pequeno cache (cerca de 90 MB), enquanto a página da Web média normalmente é de cerca de 1,6 MB. Isso não leva muito tempo para ser usado.
  
A largura de banda também pode ser um problema. Por exemplo, se um usuário estiver assistindo a vídeos em outra sessão, isso afetará o desempenho da SharePoint página. Embora você não possa impedir os usuários de transmitir mídia, você pode controlar a maneira como uma página será carregada para os usuários.
  
Confira os artigos a seguir para diferentes técnicas SharePoint de personalização de página online e outras práticas recomendadas para ajudá-lo a obter o desempenho ideal.
  
- [Opções de navegação para o SharePoint Online](navigation-options-for-sharepoint-online.md)
    
- [Use a ferramenta Diagnóstico de Página para SharePoint Online](page-diagnostics-for-spo.md)
    
- [Otimização de imagem para o SharePoint Online](image-optimization-for-sharepoint-online.md)
    
- [Atraso no carregamento de imagens e JavaScript no SharePoint Online](delay-loading-images-and-javascript-in-sharepoint-online.md)
    
- [Minificação e agrupamento no SharePoint Online](minification-and-bundling-in-sharepoint-online.md)
    
- [Usar a Rede de Distribuição de Conteúdo (CDN) do Office 365 com o SharePoint Online](use-microsoft-365-cdn-with-spo.md)
    
- [Usar a Web Part de Pesquisa de Conteúdo em vez de Web Part de Consulta de Conteúdo para melhorar o desempenho no SharePoint Online](using-content-search-web-part-instead-of-content-query-web-part-to-improve-perfo.md)
    
- [Planejamento de capacidade e teste de carregamento do SharePoint Online](capacity-planning-and-load-testing-sharepoint-online.md)
    
- [Diagnóstico de problemas de desempenho no SharePoint Online](diagnosing-performance-issues-with-sharepoint-online.md)
    
- [Usando o cache de objetos com o SharePoint Online](using-the-object-cache-with-sharepoint-online.md)
    
- [Como evitar ficar limitado ou bloqueado no SharePoint Online](/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online)
