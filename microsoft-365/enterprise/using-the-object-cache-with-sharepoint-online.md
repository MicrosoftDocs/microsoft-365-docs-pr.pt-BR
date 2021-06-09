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
description: Este artigo explica a diferença entre o uso do cache de objeto no SharePoint Server 2013 local e SharePoint Online.
ms.openlocfilehash: 279d156a941aad6fbe7adbcf052c57f5b58c652f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695385"
---
# <a name="using-the-object-cache-with-sharepoint-online"></a>Usando o cache de objetos com o SharePoint Online

Este artigo explica a diferença entre o uso do cache de objeto no SharePoint Server 2013 local e SharePoint Online.
  
Há um impacto negativo significativo da confiança no cache do objeto na implantação SharePoint Online. Qualquer dependência do cache de objeto no SharePoint Online reduzirá a confiabilidade da sua página. 
  
## <a name="how-the-sharepoint-online-and-sharepoint-server-2013-object-cache-works"></a>Como o cache de objeto SharePoint Online e SharePoint Server 2013 funciona

Quando SharePoint Server 2013 é hospedado no local, o cliente tem servidores Web front-end privados que hospedam o cache do objeto. Isso significa que o cache é dedicado a um cliente e é limitado apenas pela quantidade de memória disponível e alocada ao cache do objeto. Como apenas um cliente é atendido no cenário local, os servidores Web front-end normalmente têm usuários fazendo solicitações para os mesmos sites uma e outra vez. Isso significa que o cache fica cheio rapidamente e permanece cheio dos resultados da consulta de lista e SharePoint objetos que seus usuários estão solicitando regularmente.
  
![Mostra o tráfego e a carga para servidores front-end da Web locais](../media/a0d38b36-4909-4abb-8d4e-4930814bb3de.png)
  
Como resultado, na segunda vez que um usuário visita uma página, o tempo de carregamento da página melhora. Após um mínimo de quatro cargas da mesma página, a página é armazenada em cache em todos os servidores Web front-end.
  
Por outro lado, no SharePoint Online, há muito mais servidores, mas também muitos outros sites. Cada usuário pode se conectar a um servidor Web front-end diferente que não tenha o cache preenchido. Ou, talvez o cache seja preenchido para um servidor, mas o próximo usuário desse servidor Web front-end solicita uma página de um site diferente. Ou, mesmo se o próximo usuário solicitar a mesma página da visita anterior, ele será balanceado com carga para um servidor Web front-end diferente que não tenha essa página em seu cache. Nesse último caso, o cache não ajuda os usuários.
  
Na figura a seguir, cada ponto representa uma página que um usuário está solicitando e onde ele armazena em cache. Cores diferentes representam clientes diferentes fazendo uso compartilhado da infraestrutura SaaS.
  
![Mostra os resultados do cache de objeto no SharePoint Online](../media/25d04011-ef83-4cb7-9e04-a6ed490f63c3.png)
  
Como você pode ver no diagrama, as chances de qualquer usuário atingir um servidor com a versão em cache de sua página são mínimas. Além disso, devido à grande produtividade e ao fato de que os servidores são compartilhados entre muitos sites, o cache não dura muito, já que há muito espaço para cache disponível.
  
Por todos esses motivos, confiar nos usuários que estão recebendo objetos armazenados em cache não é uma maneira eficaz de garantir uma experiência de usuário de qualidade e tempos de carregamento de página no SharePoint Online.
  
## <a name="if-we-cant-rely-on-the-object-cache-to-improve-performance-in-sharepoint-online-what-do-we-use-instead"></a>Se não podemos contar com o cache de objeto para melhorar o desempenho no SharePoint Online, o que usamos em vez disso?

Como você não deve depender do cache no SharePoint Online, você deve avaliar abordagens de design alternativas para SharePoint personalizações que usam o cache de objeto. Isso significa usar abordagens para problemas de desempenho que não dependem do cache do objeto para produzir bons resultados para os usuários. Isso é descrito em alguns dos outros artigos desta série e inclui:
  
- [Opções de navegação para o SharePoint Online](navigation-options-for-sharepoint-online.md)
    
- [Minificação e agrupamento no SharePoint Online](minification-and-bundling-in-sharepoint-online.md)
    
- [Usar a Rede de Distribuição de Conteúdo (CDN) do Office 365 com o SharePoint Online](use-microsoft-365-cdn-with-spo.md)
    
- [Atraso no carregamento de imagens e JavaScript no SharePoint Online](delay-loading-images-and-javascript-in-sharepoint-online.md)
    

