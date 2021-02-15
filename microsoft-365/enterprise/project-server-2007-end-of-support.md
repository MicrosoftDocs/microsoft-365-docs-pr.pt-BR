---
title: Roteiro de fim do suporte do Project Server 2007
ms.author: efrene
author: efrene
manager: laurawi
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: IT_ProjectAdmin
search.appverid:
- MET150
- ZPJ120
- PJU120
- PJW120
ms.assetid: d379018f-72b7-4284-b40a-6c23c8ae38fe
description: Em 10 de outubro de 2017, o suporte terminou para o Project Server 2007, o Project Portfolio Server e o Project 2007. Use este artigo para planejar sua atualização agora.
ms.openlocfilehash: f59b319ec39c6b2d1df0876c916332491f1bb0f6
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519794"
---
# <a name="project-server-2007-end-of-support-roadmap"></a>Roteiro de fim do suporte do Project Server 2007

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

O suporte terminou para servidores e aplicativos do Office 2007 em 2017, e você precisa considerar os planos de migração. Se você estiver usando o Project Server 2007 e produtos relacionados no momento, anote as seguintes datas de fim de suporte:
  
|**Product**|**Data de término do suporte**|
|:-----|:-----|
|Project Server 2007  <br/> |10 de outubro de 2017  <br/> |
|Project Portfolio Server 2007  <br/> |10 de outubro de 2017  <br/> |
|Project 2007 Standard  <br/> |10 de outubro de 2017  <br/> |
|Project 2007 Professional  <br/> |10 de outubro de 2017  <br/> |
   
Para obter mais informações sobre os servidores do Office 2007 que estão chegando à baixa, consulte Atualização dos servidores e produtos de cliente do [Office 2007.](upgrade-from-office-2007-servers-and-products.md)
  
## <a name="what-does-end-of-support-mean"></a>O que *significa o fim do suporte?*

A maioria dos produtos da Microsoft tem um ciclo de vida de suporte durante o qual eles têm novos recursos, correções de bugs, correções de segurança e assim por diante. Esse ciclo de vida geralmente dura 10 anos a partir do lançamento inicial do produto. O fim desse ciclo de vida é conhecido como o fim do suporte do produto. Como o Project Server 2007 atingiu o fim do suporte em 10 de outubro de 2017, a Microsoft não oferece mais:
  
- Suporte técnico para problemas que podem ocorrer.
    
- Correções de bugs para problemas que podem afetar a estabilidade e a usabilidade do servidor.
    
- Correções de segurança para vulnerabilidades que podem tornar o servidor vulnerável a violações de segurança.
    
- Atualizações de fuso horário.
    
Sua instalação do Project Server 2007 continuará a ser executado após essa data. Porém, devido às alterações listadas anteriormente, recomendamos que você migre do Project Server 2007 assim que possível.
  
## <a name="what-are-my-options"></a>Quais são as minhas opções?

Se você estiver usando o Project Server 2007, precisará explorar suas opções de migração, que são:
  
- Migrar para o Project Online
    
- Migrar para uma versão local mais recente do Project Server (preferencialmente o Project Server 2016)
    
|**Por que eu prefere migrar para o Project Online**|**Por que eu prefere migrar para o Project Server 2016**|
|:-----|:-----|
| Eu tenho usuários móveis.  <br/> <br/>Os custos para migrar são uma preocupação significativa (hardware, software, horas e esforço para implementar). <br/><br/>  Após a migração, os custos para manter meu ambiente são uma preocupação importante (por exemplo, atualizações automáticas, tempo de atividade garantido e assim por diante).  <br/> | As regras de negócios me restringem a operar meus negócios na nuvem.<br/><br/>  Preciso controlar as atualizações do meu ambiente.  |
   
> [!NOTE]
> Para obter mais informações sobre opções para mover de seus servidores do Office 2007, consulte Recursos para ajudá-lo a atualizar de servidores e clientes do [Office 2007.](upgrade-from-office-2007-servers-and-products.md) Observe que o Project Server não dá suporte a uma configuração híbrida, pois o Project Server e o Project Online não podem compartilhar o mesmo pool de recursos. 
  
## <a name="important-considerations-when-you-migrate-from-project-server-2007"></a>Considerações importantes ao migrar do Project Server 2007

Considere o seguinte ao planejar a migração do Project Server 2007:
  
- **Obter ajuda de um microsoft partner** - a atualização do Project Server 2007 pode ser um desafio e requer muita preparação e planejamento. Pode ser especialmente desafiador se você não foi a pessoa que definiu o Project Server 2007 originalmente. Felizmente, há parceiros da Microsoft que podem ajudar, se você planeja migrar para o Project Server 2016 ou para o Project Online. Procure um Microsoft Partner para ajudar na migração no [Microsoft Partner Center.](https://go.microsoft.com/fwlink/p/?linkid=841249) Pesquise o  *termo Projeto Gold e Gerenciamento de Portfólio* para exibir uma lista de todos os parceiros da Microsoft que têm experiência no Project. 
    
- **Planeje** suas personalizações - Muitas das personalizações feitas em seu ambiente do Project Server 2007 podem não funcionar quando você migra para o Project Server 2016 ou o Project Online. Há diferenças significativas na arquitetura do Project Server entre versões. Os sistemas operacionais, servidores de banco de dados e navegadores da Web cliente suportados também são diferentes. Planeje como testar ou reconstruir suas personalizações para o novo ambiente. O planejamento também oferece uma boa oportunidade para considerar se cada personalização ainda é necessária. Para saber mais, confira [Create a plan for current customizations during upgrade to SharePoint 2013](https://go.microsoft.com/fwlink/p/?linkid=842061). 
    
- **Tempo e paciência** - O planejamento, a execução e os testes da atualização levarão tempo e esforço, especialmente se você atualizar para o Project Server 2016. Por exemplo, se você migrar do Project Server 2007 para o Project Server 2016, primeiro precisará migrar para o Project Server 2010, verificar seus dados e, em seguida, fazer o mesmo quando migrar para cada versão sucessiva. Talvez você queira verificar com um Microsoft Partner para obter estimativas de quanto tempo levará e o que vai custar.
    
## <a name="migrate-to-project-online"></a>Migrar para o Project Online

Se você optar por migrar do Project Server 2007 para o Project Online, poderá fazer o seguinte para migrar manualmente os dados do seu plano de projeto:
  
1. Salve seus planos de projeto do Project Server 2003 para o formato .mpp.
    
2. No Project Professional 2013, no Project Professional 2016 ou no Project Online Desktop Client, abra cada arquivo .mpp e salve e publique-o no Project Online.
    
Você pode criar manualmente sua configuração do Microsoft Project Web App (PWA) no Project Online. Por exemplo, recrie quaisquer campos personalizados ou calendários corporativos necessários. Os parceiros da Microsoft também podem ajudar nesse processo.
  
Principais recursos:
  
|**Recurso**|**Descrição**|
|:-----|:-----|
|[Introdução ao Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11) <br/> |Como configurar e usar o Project Online <br/> |
|[Descrições do serviço do Project Online](https://go.microsoft.com/fwlink/p/?linkid=829088) <br/> |Informações sobre os diferentes planos do Project Online que estão disponíveis para você <br/> |
   
## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Migrar para uma versão local mais recente do Project Server

Acreditamos que você tem o melhor valor e experiência do usuário migrando para o Project Online. Mas também entendemos que algumas organizações precisam manter os dados do projeto em um ambiente local. Se você optar por manter seus dados de projeto no local, poderá migrar seu ambiente do Project Server 2007 para o Project Server 2010, o Project Server 2013 ou o Project Server 2016.
  
Se não for possível migrar para o Project Online, recomendamos migrar para o Project Server 2016. O Project Server 2016 inclui todos os recursos de versões anteriores do Project Server. Ele corresponde mais de perto à experiência disponível com o Project Online, embora alguns recursos só estão disponíveis no Project Online.
  
Após cada migração, você deve verificar se os dados foram migrados com êxito.
  
> [!NOTE]
>
  
### <a name="how-do-i-migrate-to-project-server-2016"></a>Como migrar para o Project Server 2016?

As diferenças de arquitetura entre o Project Server 2007 e o Project Server 2016 impedem um caminho de migração direta. Portanto, você precisa migrar seus dados do Project Server 2007 para cada versão sucessiva do Project Server até chegar ao Project Server 2016.
  
Siga estas etapas para o Project Server 2016:
  
1. Migrar do Project Server 2007 para o Project Server 2010.
    
2. Migrar do Project Serve 2010 para o Project Server 2013.
    
3. Migrar do Project Server 2013 para o Project Server 2016.
    
Após cada migração, certifique-se de que seus dados foram migrados com êxito.
  
### <a name="step-1-migrate-from-project-server-2007-to-project-server-2010"></a>Etapa 1: Migrar do Project Server 2007 para o Project Server 2010

Para uma descrição abrangente do que você precisa fazer para atualizar do Project Server 2007 para o Project Server 2010, consulte Atualização para [o Project Server 2010.](https://go.microsoft.com/fwlink/p/?linkid=841812)
  
Principais recursos:
  
|**Recurso**|**Descrição**|
|:-----|:-----|
|[Visão geral da atualização do Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841813) <br/> |Uma visão de alto nível do que você precisa fazer para atualizar do Project Server 2007 para o Project Server 2010 <br/> |
|[Planejar a atualização para o Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841815) <br/> |Considerações de planejamento ao atualizar do Project Server 2007 para o Project Server 2010, incluindo requisitos do sistema  <br/> |
   
#### <a name="how-do-i-upgrade"></a>Como faço para atualizar?

Para obter detalhes, [consulte Upgrade to Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841812). Mas é importante entender que há dois métodos distintos que você pode usar para atualizar:
  
- **Atualização com anexação de banco de dados:** Esse método atualiza apenas o conteúdo do seu ambiente, não as definições de configuração. Ele será necessário se você estiver atualizando do Office Project Server 2007 implantado em um hardware que só dá suporte a um sistema operacional de servidor de 32 bits. Existem dois tipos de métodos de atualização com anexação de banco de dados:
    
  - **Atualização completa** com anexação de banco de dados - Migra os dados do projeto armazenados nos bancos de dados do Office Project Server 2007, além dos dados do site do Microsoft Project Web App armazenados em um banco de dados de conteúdo do SharePoint.
    
  - **Atualização de núcleo com *anexação de*** banco de dados - Migra somente os dados do projeto armazenados nos bancos de dados do Project Server.
    
- **Atualização local: os** dados de configuração para o farm e todo o conteúdo no farm são atualizados no hardware existente em uma ordem fixa. Quando você inicia o processo de atualização, a instalação leva todo o farm offline. Os sites e os sites do Microsoft Project Web App ficam indisponíveis até que a atualização seja concluída e, em seguida, a instalação reinicia o servidor. Depois de iniciar uma atualização in-locar, você não poderá pausar a atualização ou reverter para a versão anterior. É melhor fazer uma imagem espelhada do seu ambiente de produção e fazer a atualização local para esse ambiente, não em seu ambiente de produção. 
    
Recursos adicionais:
  
- [SuperFlow para Atualização do Microsoft Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841277)
    
- [Migração do Project Server 2007 para o Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841278)
    
- [Considerações sobre atualização das Web parts do Project Web App](https://go.microsoft.com/fwlink/p/?linkid=841276)
    
- [Project Software Development Kit (SDK)](https://go.microsoft.com/fwlink/p/?linkid=841275)
    
### <a name="step-2-migrate-to-project-server-2013"></a>Etapa 2: Migrar para o Project Server 2013

Depois de verificar se os dados foram migrados com êxito, a próxima etapa é migrar para o Project Server 2013.
  
Para uma descrição abrangente do que você precisa fazer para atualizar do Project Server 2010 para o Project Server 2013, consulte Atualização para [o Project Server 2013.](https://go.microsoft.com/fwlink/p/?linkid=841822) 
  
Principais recursos:
  
|**Recurso**|**Descrição**|
|:-----|:-----|
|[Visão geral do processo de atualização do Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822) <br/> |Visão geral do que você precisa fazer para atualizar do Project Server 2010 para o Project Server 2013  <br/> |
|[Planejar a atualização para o Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841823) <br/> |Considerações de planejamento ao atualizar do Project Server 2010 para o Project Server 2013, incluindo requisitos do sistema <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>Informações importantes sobre a atualização para esta versão

[O que há de novo na atualização do Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841824) descreve alterações importantes para a atualização para esta versão. Os mais notáveis são: 
  
- Não há atualização local para o Project Server 2013. O método de anexação de banco de dados é o único método com suporte para atualização do Project Server 2010 para o Project Server 2013.
    
- O processo de atualização não só converterá os dados do Project Server 2010 no formato do Project Server 2013, mas também consolidará os quatro bancos de dados do Project Server 2010 em um único banco de dados do Project Web App.
    
- Nas versões de 2013, o SharePoint Server e o Project Server foram alterados para autenticação baseada em declarações. Se você estiver usando a autenticação clássica, será necessário considerar esse fator para a atualização. Para saber mais, confira [Migrar da autenticação de modo clássico para a autenticação baseada em declarações SharePoint 2013](https://go.microsoft.com/fwlink/p/?linkid=841825).
    
Recursos adicionais:
  
- [Visão geral do processo de atualização para o Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841274)
    
- [Atualizar seus bancos de dados e conjuntos de sites do Project Web App (Project Server 2013)](https://go.microsoft.com/fwlink/p/?linkid=841272)
    
- [Diagrama do processo de atualização do Microsoft Project Server](https://go.microsoft.com/fwlink/p/?linkid=841270)
    
- [A grande consolidação de banco de dados, migração do Project Server 2010 para 2013 em 8 etapas fáceis](https://go.microsoft.com/fwlink/p/?linkid=841271)
    
### <a name="step-3-migrate-to-project-server-2016"></a>Etapa 3: Migrar para o Project Server 2016

Depois de verificar se os dados foram migrados com êxito, a próxima etapa é migrar para o Project Server 2016.
  
Para uma descrição abrangente do que você precisa fazer para atualizar do Project Server 2013 para o Project Server 2016, consulte Atualização para o [Project Server 2016.](https://docs.microsoft.com//project/upgrading-to-project-server-2016)
  
Principais recursos:
  
|**Recurso**|**Descrição**|
|:-----|:-----|
|[Visão geral do processo de atualização do Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841260) <br/> |Visão geral do que você precisa fazer para atualizar do Project Server 2013 para o Project Server 2016 <br/> |
|[Planejar a atualização para o Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841826) <br/> |Considerações de planejamento que você atualiza do Project Server 2013 para o Project Server 2016 <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>Informações importantes sobre a atualização para esta versão

O que você precisa saber sobre a atualização do [Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841827) informa algumas alterações importantes para a atualização desta versão, que incluem:
  
- Quando você cria seu ambiente do Project Server 2016 para o qual migrará os dados do Project Server 2013, os arquivos de instalação do Project Server 2016 são incluídos no SharePoint Server 2016. Para obter mais informações, [consulte Implantar o Project Server 2016.](https://go.microsoft.com/fwlink/p/?linkid=841829)
    
- Os planos de recursos foram preterido no Project Server 2016. Seus planos de recurso do Project Server 2013 serão migrados para Compromissos de Recurso no Project Server 2016 e no Project Online. Consulte [Visão geral: compromissos de recursos](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) para obter mais informações. 
    
## <a name="migrate-from-portfolio-server-2007"></a>Migrar do Portfolio Server 2007

O Project Portfolio Server 2007 foi usado com o Project Server 2007 para estratégia, priorização e otimização de portfólio. Nenhuma versão adicional do Project Portfolio Server foi criada após essa versão. No entanto, os recursos de gerenciamento de portfólio estão disponíveis no Project Server 2016 e na versão Premium do Project Online. Mas os dados do Project Portfolio Server 2007 não podem ser migrados para nenhum deles. Dados como drivers de negócios terão que ser recriados.
  
Outros recursos:
  
- [Descrições do serviço do Project Online:](https://go.microsoft.com/fwlink/p/?linkid=841280) Consulte os recursos de gerenciamento de portfólio incluídos no Project Server 2016 e no Project Online Premium.
    
- [Guia de migração do Microsoft Office Project Portfolio Server 2007.](https://go.microsoft.com/fwlink/p/?linkid=841279)
    
## <a name="related-topics"></a>Tópicos relacionados

[Roteiro de fim do suporte do SharePoint Server 2007](sharepoint-2007-end-of-support.md)
  
[Recursos para ajudá-lo a atualizar de servidores e clientes do Office 2007](upgrade-from-office-2007-servers-and-products.md)
  
