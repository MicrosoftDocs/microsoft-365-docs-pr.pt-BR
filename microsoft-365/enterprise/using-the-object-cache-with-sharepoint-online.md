---
title: Usando o cache de objetos com o SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/20/2015
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: 38bc9c14-3826-449c-beb6-b1003bcbeaaf
description: Este artigo explica a diferença entre o uso do cache de objetos no SharePoint Server 2013 local e no SharePoint Online.
ms.openlocfilehash: 279d156a941aad6fbe7adbcf052c57f5b58c652f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695385"
---
# <a name="using-the-object-cache-with-sharepoint-online"></a>Usando o cache de objetos com o SharePoint Online

Este artigo explica a diferença entre o uso do cache de objetos no SharePoint Server 2013 local e no SharePoint Online.
  
Há um impacto negativo significativo de confiar no cache de objetos na implantação do SharePoint Online. Qualquer dependência no cache de objetos no SharePoint Online reduzirá a confiabilidade da sua página. 
  
## <a name="how-the-sharepoint-online-and-sharepoint-server-2013-object-cache-works"></a>Como funciona o cache de objetos do SharePoint Online e do SharePoint Server 2013

Quando o SharePoint Server 2013 está hospedado no local, o cliente tem servidores Web front-end privados que hospedam o cache de objetos. Isso significa que o cache é dedicado a um cliente e só é limitado pela quantidade de memória disponível e alocada no cache de objetos. Como apenas um cliente é servido no cenário local, os servidores Web front-end geralmente têm usuários fazendo solicitações para os mesmos sites repetidamente. Isso significa que o cache fica completo rapidamente e permanece completo dos resultados da consulta de lista e dos objetos do SharePoint que seus usuários estão solicitando regularmente.
  
![Mostra o tráfego e a carga para servidores front-end da Web locais](../media/a0d38b36-4909-4abb-8d4e-4930814bb3de.png)
  
Como resultado, a segunda vez que um usuário visita uma página, o tempo de carregamento da página melhora. Após um mínimo de quatro carregamentos da mesma página, a página é armazenada em cache em todos os servidores Web front-end.
  
Por outro lado, no SharePoint Online há muito mais servidores, mas também muitos outros sites. Cada usuário pode se conectar a um servidor Web front-end diferente que não tenha o cache preenchido. Ou, talvez o cache seja preenchido para um servidor, mas o próximo usuário desse servidor Web front-end solicita uma página de um site diferente. Ou, mesmo que o próximo usuário solicite a mesma página que em sua visita anterior, eles são balanceados por carga para um servidor Web front-end diferente que não tenha essa página em seu cache. Neste último caso, o cache não ajudará os usuários.
  
Na figura a seguir, cada ponto representa uma página que um usuário está solicitando e onde ele está armazenado em cache. Cores diferentes representam diferentes clientes que fazem uso compartilhado da infraestrutura SaaS.
  
![Mostra os resultados do cache de objeto no SharePoint Online](../media/25d04011-ef83-4cb7-9e04-a6ed490f63c3.png)
  
Como você pode ver no diagrama, as chances de qualquer usuário que esteja atingindo um servidor com a versão armazenada em cache da página sejam reduzidas. Além disso, devido à grande produtividade e ao fato de que os servidores são compartilhados entre muitos sites, o cache não dura por último, pois há muito espaço para armazenamento em cache disponível.
  
Por todos esses motivos, confiar em usuários que estão recebendo objetos em cache não é uma maneira eficaz de garantir uma experiência de usuário de qualidade e tempos de carregamento de página no SharePoint Online.
  
## <a name="if-we-cant-rely-on-the-object-cache-to-improve-performance-in-sharepoint-online-what-do-we-use-instead"></a>Se não pudermos confiar no cache de objetos para melhorar o desempenho no SharePoint Online, o que usamos em vez disso?

Como você não deve confiar no cache do SharePoint Online, avalie as abordagens de design alternativas para personalizações do SharePoint que usam o cache de objetos. Isso significa usar abordagens para problemas de desempenho que não dependem do cache de objetos para produzir bons resultados para os usuários. Isso é descrito em alguns dos outros artigos desta série e incluem:
  
- [Opções de navegação para o SharePoint Online](navigation-options-for-sharepoint-online.md)
    
- [Minificação e agrupamento no SharePoint Online](minification-and-bundling-in-sharepoint-online.md)
    
- [Usar a Rede de Distribuição de Conteúdo (CDN) do Office 365 com o SharePoint Online](use-microsoft-365-cdn-with-spo.md)
    
- [Atraso no carregamento de imagens e JavaScript no SharePoint Online](delay-loading-images-and-javascript-in-sharepoint-online.md)
    

