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
description: Este artigo explica quais aspectos específicos você precisa considerar ao criar páginas para obter um melhor desempenho no SharePoint Online.
ms.openlocfilehash: d3a9dedbd5812774b81494af0f8defa5568f7dac
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687419"
---
# <a name="introduction-to-performance-tuning-for-sharepoint-online"></a>Introdução ao ajuste de desempenho para o SharePoint Online

Este artigo explica quais aspectos específicos você precisa considerar ao criar páginas para obter um melhor desempenho no SharePoint Online.
     
## <a name="sharepoint-online-metrics"></a>Métricas do SharePoint Online

As seguintes métricas amplas para o SharePoint Online fornecem dados reais do mundo sobre o desempenho:
  
- Como carregar páginas rápidas
    
- Quantas viagens de ida e segundo são exigidas por página
    
- Problemas com o serviço
    
- Outras coisas que causam degradação de desempenho
    
### <a name="conclusions-reached-because-of-the-data"></a>Conclusões atingidas por causa dos dados

Os dados nos dizem:
  
- A maioria das páginas tem um bom desempenho no SharePoint Online.
    
- Páginas não personalizadas carregam muito rapidamente.
    
- O OneDrive for Business, sites de equipe e páginas de sistema, como _layouts, etc., são todos rápidos para carregar.
    
- O 1% mais lento de páginas do SharePoint Online demora mais de 5.000 milissegundos para carregar.
    
Um teste de benchmark simples que você pode usar seria medir o desempenho comparando o tempo de carregamento do seu portal com o tempo de carregamento da home page do OneDrive for Business, pois usa alguns recursos personalizados. Em geral, este será o suporte a primeira etapa solicitará a conclusão da solução de problemas de desempenho da rede.
  
## <a name="use-a-standard-user-account-when-checking-performance"></a>Usar uma conta de usuário padrão ao verificar o desempenho

Um administrador do conjunto de sites, proprietário do site, editor ou colaborador pertence a grupos de segurança adicionais, têm permissões adicionais e, portanto, têm elementos adicionais que o SharePoint carrega em uma página.
  
Isso se aplica ao SharePoint local e ao SharePoint Online, mas em um cenário local as diferenças não serão tão facilmente percebidas quanto no SharePoint Online.
  
Para avaliar corretamente como uma página será executada para os usuários, você deve usar uma conta de usuário padrão para evitar o carregamento de controles de criação e tráfego adicional relacionado a grupos de segurança.
  
## <a name="connection-categories-for-performance-tuning"></a>Categorias de conexão para ajuste de desempenho

Você pode categorizar as conexões entre o servidor e o usuário em três componentes principais. Considere estes ao projetar páginas do SharePoint Online para obter informações sobre o tempo de carregamento.
  
- **Servidor do** Os servidores que a Microsoft hospeda nos data centers.
    
- **Rede** A rede da Microsoft, a Internet e sua rede local entre o datacenter e seus usuários.
    
- **Navegador** Onde a página é carregada.
    
Dentro dessas três conexões, geralmente há cinco razões que causam 95% de páginas lentas. Cada um desses motivos é discutido neste artigo:
  
- Problemas de navegação
    
- Distribuição de conteúdo
    
- Arquivos grandes
    
- Muitas solicitações para o servidor
    
- Processamento de Web Part
    
### <a name="server-connection"></a>Conexão do servidor

Muitos dos problemas que afetam o desempenho com o SharePoint local também se aplicam ao SharePoint Online.
  
Como esperado, você tem muito mais controle sobre como os servidores são executados com o SharePoint local. Com o SharePoint Online, as coisas são um pouco diferentes. Quanto mais trabalho fizer um servidor, mais demorará para renderizar uma página. Com o SharePoint, o maior culpado nesse respeito é páginas complexas com várias Web Parts.
  
SharePoint Server local
  
![Captura de tela do servidor local](../media/a8e9b646-cdff-4131-976a-b5f891da44ac.png)
  
SharePoint Online
  
![Captura de tela do servidor online](../media/46b27ded-d8a4-4287-b3e0-2603a764b8f8.png)
  
Com o SharePoint Online, determinadas solicitações de página podem realmente acabar chamando vários servidores. Você pode acabar com uma matriz de solicitações entre servidores para uma solicitação individual. Essas interações são caras de uma perspectiva de carregamento de página e tornarão as coisas lentas.
  
Os exemplos dessas interações de servidor para servidor são:
  
- Web para SQL Servers
    
- Servidores da Web para aplicativos
    
A outra coisa que pode reduzir as interações com o servidor é erros de cache. Ao contrário do SharePoint local, há uma chance muito leve de que você acesse o mesmo servidor para uma página que visitou anteriormente; Isso torna o cache do objeto obsoleto.
  
### <a name="network-connection"></a>Conexão de rede

Com o SharePoint local que não faz uso de uma WAN, você pode usar uma conexão de alta velocidade entre o datacenter e os usuários finais. Geralmente, as coisas são fáceis de gerenciar a partir de uma perspectiva de rede.
  
Com o SharePoint Online, há alguns fatores que devem ser considerados; por exemplo:
  
- A rede da Microsoft
    
- A Internet
    
- O ISP
    
Independentemente da versão do SharePoint (e da rede) que você está usando, as coisas que normalmente farão com que a rede estejam ocupadas incluem:
  
- Carga grande
    
- Muitos arquivos
    
- Grande distância física para o servidor
    
Um recurso que você pode aproveitar no SharePoint Online é a CDN da Microsoft (rede de distribuição de conteúdo). Uma CDN é basicamente uma coleção distribuída de servidores implantados em vários datacenters. Com uma CDN, o conteúdo nas páginas pode ser hospedado em um servidor próximo ao cliente, mesmo que o cliente esteja longe do servidor do SharePoint de origem. A Microsoft usará isso mais no futuro para armazenar instâncias locais de páginas que não podem ser personalizadas, por exemplo, a Home Page de administração do SharePoint Online. Para obter mais informações sobre o CDNs, consulte [redes de distribuição de conteúdo](content-delivery-networks.md).
  
Algo que você precisa saber, mas talvez não seja possível fazer muito sobre a velocidade de conexão do seu provedor de Internet. Uma ferramenta de teste de velocidade simples informará a velocidade da conexão.
  
### <a name="browser-connection"></a>Conexão do navegador

Há alguns fatores que devem ser considerados nos navegadores da Web a partir de uma perspectiva de desempenho.
  
A visita a páginas complexas afetará o desempenho. A maioria dos navegadores tem um pequeno cache (em torno de 90MB), enquanto a página da Web média é geralmente cerca de 1,6 MB. Isso não demora muito para ser usado.
  
A largura de banda também pode ser um problema. Por exemplo, se um usuário estiver assistindo a vídeos em outra sessão, isso afetará o desempenho da página do SharePoint. Embora não seja possível impedir que os usuários enviem mídias, você pode controlar a forma como uma página será carregada para os usuários.
  
Confira os seguintes artigos para diferentes técnicas de personalização de páginas do SharePoint Online e outras práticas recomendadas para ajudá-lo a obter o desempenho ideal.
  
- [Opções de navegação para o SharePoint Online](navigation-options-for-sharepoint-online.md)
    
- [Usar a ferramenta diagnóstico de página para o SharePoint Online](page-diagnostics-for-spo.md)
    
- [Otimização de imagem para o SharePoint Online](image-optimization-for-sharepoint-online.md)
    
- [Atraso no carregamento de imagens e JavaScript no SharePoint Online](delay-loading-images-and-javascript-in-sharepoint-online.md)
    
- [Minificação e agrupamento no SharePoint Online](minification-and-bundling-in-sharepoint-online.md)
    
- [Usar a Rede de Distribuição de Conteúdo (CDN) do Office 365 com o SharePoint Online](use-microsoft-365-cdn-with-spo.md)
    
- [Usando a Web Part de pesquisa de conteúdo em vez da Web Part de consulta de conteúdo para melhorar o desempenho no SharePoint Online](using-content-search-web-part-instead-of-content-query-web-part-to-improve-perfo.md)
    
- [Planejamento de capacidade e teste de carregamento do SharePoint Online](capacity-planning-and-load-testing-sharepoint-online.md)
    
- [Diagnóstico de problemas de desempenho no SharePoint Online](diagnosing-performance-issues-with-sharepoint-online.md)
    
- [Usando o cache de objetos com o SharePoint Online](using-the-object-cache-with-sharepoint-online.md)
    
- [Como evitar ficar limitado ou bloqueado no SharePoint Online](https://msdn.microsoft.com/library/office/dn889829.aspx)
    

