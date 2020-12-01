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
description: Em 10 de outubro de 2017, o suporte terminou para o Project Server 2007, Project Portfolio Server e Project 2007. Use este artigo para planejar sua atualização agora.
ms.openlocfilehash: f59b319ec39c6b2d1df0876c916332491f1bb0f6
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519794"
---
# <a name="project-server-2007-end-of-support-roadmap"></a>Roteiro de fim do suporte do Project Server 2007

*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*

O suporte terminou para os servidores e aplicativos do Office 2007 no 2017 e você precisa considerar os planos de migração. Se você estiver usando o Project Server 2007 e produtos relacionados, observe as seguintes datas de fim de suporte:
  
|**Produto**|**Data do fim da suporte**|
|:-----|:-----|
|Project Server 2007  <br/> |10 de outubro de 2017  <br/> |
|Project Portfolio Server 2007  <br/> |10 de outubro de 2017  <br/> |
|Padrão do Project 2007  <br/> |10 de outubro de 2017  <br/> |
|Project 2007 Professional  <br/> |10 de outubro de 2017  <br/> |
   
Para obter mais informações sobre os servidores do Office 2007 que estão chegando à aposentadoria, confira [Upgrade from Office 2007 Servers and Client Products](upgrade-from-office-2007-servers-and-products.md).
  
## <a name="what-does-end-of-support-mean"></a>O que significa o *fim do suporte* ?

A maioria dos produtos da Microsoft tem um ciclo de vida de suporte durante o qual eles obtêm novos recursos, correções de erros, correções de segurança e assim por diante. Esse ciclo de vida normalmente dura 10 anos da versão inicial do produto. O final desse ciclo de vida é conhecido como o fim do suporte do produto. Como o Project Server 2007 atingiu o fim do suporte em 10 de outubro de 2017, a Microsoft não fornece mais:
  
- Suporte técnico para problemas que podem ocorrer.
    
- Correções de erros que podem afetar a estabilidade e a usabilidade do servidor.
    
- Correções de segurança para vulnerabilidades que podem tornar o servidor vulnerável a brechas de segurança.
    
- Atualizações de fuso horário.
    
Sua instalação do Project Server 2007 continuará a ser executada após essa data. Mas devido às alterações listadas anteriormente, é altamente recomendável migrar do Project Server 2007 assim que for prático.
  
## <a name="what-are-my-options"></a>Quais são as minhas opções?

Se você estiver usando o Project Server 2007, precisará explorar as opções de migração, que são:
  
- Migrar para o Project online
    
- Migrar para uma versão local mais recente do Project Server (preferivelmente o Project Server 2016)
    
|**Por que eu prefiro migrar para o Project online**|**Por que eu prefiro migrar para o Project Server 2016**|
|:-----|:-----|
| Eu tenho usuários móveis.  <br/> <br/>Os custos de migração são uma preocupação considerável (hardware, software, horas e esforço para implementar). <br/><br/>  Após a migração, os custos de manutenção do meu ambiente são uma preocupação importante (por exemplo, atualizações automáticas, tempo de atividade garantido e assim por diante).  <br/> | Regras de negócios restringe a operar minha empresa na nuvem.<br/><br/>  Preciso de controle das atualizações no meu ambiente.  |
   
> [!NOTE]
> Para obter mais informações sobre as opções de migração de seus servidores do Office 2007, consulte [recursos para ajudá-lo a atualizar de clientes e servidores do office 2007](upgrade-from-office-2007-servers-and-products.md). Observe que o Project Server não oferece suporte a uma configuração híbrida, pois o Project Server e o Project online não podem compartilhar o mesmo pool de recursos. 
  
## <a name="important-considerations-when-you-migrate-from-project-server-2007"></a>Considerações importantes ao migrar do Project Server 2007

Considere o seguinte quando você planeja migrar do Project Server 2007:
  
- **Obter ajuda de um Microsoft Partner** -upgrading from Project Server 2007 pode ser desafiador e exige muito plano e planejamento. Pode ser especialmente desafiador se você não for a pessoa que configurou o Project Server 2007 originalmente. Felizmente, há parceiros da Microsoft que podem ajudar, se você planeja migrar para o Project Server 2016 ou para o Project online. Procure um parceiro da Microsoft para ajudá-lo com sua migração no [centro de parceiros da Microsoft](https://go.microsoft.com/fwlink/p/?linkid=841249). Pesquise o termo  *projeto ouro e gerenciamento de portfólio* para exibir uma lista de todos os parceiros da Microsoft que têm experiência no Project. 
    
- **Planejar suas personalizações** -muitas das personalizações feitas no ambiente do project Server 2007 podem não funcionar quando você migrar para o project Server 2016 ou o Project online. Há diferenças significativas na arquitetura do Project Server entre as versões. Os sistemas operacionais, servidores de banco de dados e navegadores da Web do cliente necessários também são diferentes. Planejar como testar ou reconstruir suas personalizações para o novo ambiente. O planejamento também oferece uma boa oportunidade de considerar se cada personalização ainda é necessária. Para saber mais, confira [Create a plan for current customizations during upgrade to SharePoint 2013](https://go.microsoft.com/fwlink/p/?linkid=842061). 
    
- O planejamento, a execução e o teste de atualização de **tempo e paciência** terão tempo e esforço, especialmente se você atualizar para o Project Server 2016. Por exemplo, se você migrar do Project Server 2007 para o Project Server 2016, primeiro você precisa migrar para o Project Server 2010, verificar seus dados e fazer o mesmo quando migrar para cada versão sucessiva. Você pode querer consultar um parceiro da Microsoft para obter estimativas de quanto tempo levará e o que ele custará.
    
## <a name="migrate-to-project-online"></a>Migrar para o Project online

Se você optar por migrar do Project Server 2007 para o Project online, poderá fazer o seguinte para migrar manualmente os dados do plano de projeto:
  
1. Salve seus planos de projeto do Project Server 2003 para o formato. mpp.
    
2. No Project Professional 2013, no Project Professional 2016 ou no cliente da área de trabalho do Project online, abra cada arquivo. mpp e, em seguida, salve e publique-o no Project online.
    
Você pode criar manualmente a configuração do Microsoft Project Web App (PWA) no Project online. Por exemplo, recrie todos os campos personalizados ou calendários da empresa necessários. Os parceiros da Microsoft também podem ajudar com esse processo.
  
Principais recursos:
  
|**Recurso**|**Descrição**|
|:-----|:-----|
|[Introdução ao Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11) <br/> |Como configurar e usar o Project online <br/> |
|[Descrições do serviço do Project online](https://go.microsoft.com/fwlink/p/?linkid=829088) <br/> |Informações sobre os diferentes planos do Project online que estão disponíveis para você <br/> |
   
## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Migrar para uma versão local mais recente do Project Server

Acreditamos que você obtém o melhor valor e a experiência do usuário migrando para o Project online. Mas também entendemos que algumas organizações precisam manter os dados do projeto em um ambiente local. Se você optar por manter seus dados de projeto no local, poderá migrar seu ambiente do Project Server 2007 para o Project Server 2010, o Project Server 2013 ou o Project Server 2016.
  
Se você não conseguir migrar para o Project online, recomendamos migrar para o Project Server 2016. O Project Server 2016 inclui todos os recursos de versões anteriores do Project Server. Ele atende melhor à experiência disponível com o Project online, embora alguns recursos estejam disponíveis somente no Project online.
  
Após cada migração, você deve verificar se seus dados foram migrados com êxito.
  
> [!NOTE]
>
  
### <a name="how-do-i-migrate-to-project-server-2016"></a>Como faço para migrar para o Project Server 2016?

Diferenças arquitetônicas entre o Project Server 2007 e o Project Server 2016 impedem um caminho de migração direto. Portanto, você precisa migrar os dados do Project Server 2007 para cada versão sucessiva do Project Server até chegar ao Project Server 2016.
  
Siga estas etapas para o Project Server 2016:
  
1. Migre do Project Server 2007 para o Project Server 2010.
    
2. Migrar do Project serve 2010 para o Project Server 2013.
    
3. Migre do Project Server 2013 para o Project Server 2016.
    
Após cada migração, certifique-se de que seus dados foram migrados com êxito.
  
### <a name="step-1-migrate-from-project-server-2007-to-project-server-2010"></a>Etapa 1: migrar do Project Server 2007 para o Project Server 2010

Para obter uma descrição abrangente do que você precisa fazer para atualizar do Project Server 2007 para o Project Server 2010, consulte [upgrade to project server 2010](https://go.microsoft.com/fwlink/p/?linkid=841812).
  
Principais recursos:
  
|**Recurso**|**Descrição**|
|:-----|:-----|
|[Visão geral da atualização do Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841813) <br/> |Uma visão de alto nível do que você precisa fazer para atualizar do Project Server 2007 para o Project Server 2010 <br/> |
|[Planejar a atualização para o Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841815) <br/> |Considerações de planejamento ao atualizar do Project Server 2007 para o Project Server 2010, incluindo os requisitos do sistema  <br/> |
   
#### <a name="how-do-i-upgrade"></a>Como faço para atualizar?

Para obter detalhes, consulte [upgrade to Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841812). Mas é importante entender que há dois métodos distintos que você pode usar para atualizar:
  
- **Atualização de anexação de banco de dados:** Esse método atualiza apenas o conteúdo para o seu ambiente, não as definições de configuração. Será necessário se você estiver atualizando do Office Project Server 2007 implantado no hardware que suporta apenas um sistema operacional de servidor de 32 bits. Há dois tipos de métodos de atualização de anexação de banco de dados:
    
  - ***Atualização completa* de anexação de banco** de dados-migra os dados de projeto armazenados nos bancos de dados do Office Project Server 2007, além dos dados de site do Microsoft Project Web App armazenados em um banco de dados de conteúdo do SharePoint.
    
  - ***Atualização principal* de anexação de banco** de dados: migra somente os dados de projeto armazenados nos bancos de dados do Project Server.
    
- **Atualização** in-loco: os dados de configuração do farm e todo o conteúdo do farm são atualizados no hardware existente em uma ordem fixa. Quando você inicia o processo de atualização, a instalação leva todo o farm offline. Os sites da Web e do Microsoft Project Web App não estão disponíveis até que a atualização seja concluída e, em seguida, a instalação reinicia o servidor. Depois de começar uma atualização in-loco, você não pode pausar a atualização ou reverter para a versão anterior. É melhor criar uma imagem espelhada do ambiente de produção e fazer a atualização in-loco para esse ambiente, e não no ambiente de produção. 
    
Recursos adicionais:
  
- [Estouro para atualização do Microsoft Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841277)
    
- [Migração do Project Server 2007 para o Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841278)
    
- [Considerações sobre atualização das Web parts do Project Web App](https://go.microsoft.com/fwlink/p/?linkid=841276)
    
- [SDK (Software Development Kit) do Project](https://go.microsoft.com/fwlink/p/?linkid=841275)
    
### <a name="step-2-migrate-to-project-server-2013"></a>Etapa 2: migrar para o Project Server 2013

Depois de verificar se seus dados foram migrados com êxito, a próxima etapa é migrar para o Project Server 2013.
  
Para obter uma descrição abrangente do que você precisa fazer para atualizar do Project Server 2010 para o Project Server 2013, consulte [upgrade to project server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822). 
  
Principais recursos:
  
|**Recurso**|**Descrição**|
|:-----|:-----|
|[Visão geral do processo de atualização do Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822) <br/> |Visão geral do que você precisa fazer para atualizar do Project Server 2010 para o Project Server 2013  <br/> |
|[Planejar a atualização para o Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841823) <br/> |Considerações de planejamento ao atualizar do Project Server 2010 para o Project Server 2013, incluindo os requisitos do sistema <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>Coisas que você precisa saber sobre a atualização para esta versão

[O que há de novo no Project Server 2013 atualização](https://go.microsoft.com/fwlink/p/?linkid=841824) descreve as alterações importantes da atualização para esta versão. Os mais notáveis são: 
  
- Não há nenhuma atualização in-loco para o Project Server 2013. O método Database-Attach é o único método com suporte para atualização do Project Server 2010 para o Project Server 2013.
    
- O processo de atualização não só converterá os dados do Project Server 2010 no formato do Project Server 2013, mas também consolidará os quatro bancos de dados do Project Server 2010 em um único banco de dados do Project Web App.
    
- Nas versões 2013, o SharePoint Server e o Project Server mudaram para a autenticação baseada em declarações. Se você estiver usando a autenticação clássica, precisará considerar esse fator para a atualização. Para saber mais, confira [Migrar da autenticação de modo clássico para a autenticação baseada em declarações SharePoint 2013](https://go.microsoft.com/fwlink/p/?linkid=841825).
    
Recursos adicionais:
  
- [Visão geral do processo de atualização para o Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841274)
    
- [Atualizar seus bancos de dados e conjuntos de sites do Project Web App (Project Server 2013)](https://go.microsoft.com/fwlink/p/?linkid=841272)
    
- [Diagrama de processo de atualização do Microsoft Project Server](https://go.microsoft.com/fwlink/p/?linkid=841270)
    
- [A excelente consolidação do banco de dados, o Project Server 2010 para a migração 2013 em 8 etapas simples](https://go.microsoft.com/fwlink/p/?linkid=841271)
    
### <a name="step-3-migrate-to-project-server-2016"></a>Etapa 3: migrar para o Project Server 2016

Depois de verificar se seus dados foram migrados com êxito, a próxima etapa é migrar para o Project Server 2016.
  
Para obter uma descrição abrangente do que você precisa fazer para atualizar do Project Server 2013 para o Project Server 2016, consulte [upgrade to project server 2016](https://docs.microsoft.com//project/upgrading-to-project-server-2016).
  
Principais recursos:
  
|**Recurso**|**Descrição**|
|:-----|:-----|
|[Visão geral do processo de atualização do Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841260) <br/> |Visão geral do que você precisa fazer para atualizar do Project Server 2013 para o Project Server 2016 <br/> |
|[Planejar a atualização para o Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841826) <br/> |Considerações de planejamento você atualiza do Project Server 2013 para o Project Server 2016 <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>Coisas que você precisa saber sobre a atualização para esta versão

As [coisas que você precisa saber sobre a atualização do Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841827) mostra algumas alterações importantes para atualização para esta versão, que incluem:
  
- Ao criar seu ambiente do Project Server 2016 para o qual você migrará os dados do Project Server 2013, os arquivos de instalação do Project Server 2016 serão incluídos no SharePoint Server 2016. Para obter mais informações, consulte [Deploy Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841829).
    
- Os planos de recursos são preteridos no Project Server 2016. Seus planos de recursos do Project Server 2013 serão migrados para os compromissos de recursos no Project Server 2016 e no Project online. Consulte [visão geral: compromissos de recursos](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) para obter mais informações. 
    
## <a name="migrate-from-portfolio-server-2007"></a>Migrar do Portfolio Server 2007

O Project Portfolio Server 2007 foi usado com o Project Server 2007 para estratégia de portfólio, priorização e otimização. Não foram criadas versões adicionais do Project Portfolio Server após esta versão. No entanto, os recursos de gerenciamento de portfólio estão disponíveis no Project Server 2016 e na versão Premium do Project online. Mas os dados do Project Portfolio Server 2007 não podem ser migrados para o. Dados como drivers de negócios terão que ser recriados.
  
Outros recursos:
  
- [Descrições do serviço do Project online:](https://go.microsoft.com/fwlink/p/?linkid=841280) Consulte os recursos de gerenciamento de portfólio incluídos no Project Server 2016 e no Project Online Premium.
    
- [Guia de migração do Microsoft Office Project Portfolio Server 2007.](https://go.microsoft.com/fwlink/p/?linkid=841279)
    
## <a name="related-topics"></a>Tópicos relacionados

[Roteiro de fim do suporte do SharePoint Server 2007](sharepoint-2007-end-of-support.md)
  
[Recursos para ajudá-lo a atualizar de clientes e servidores do Office 2007](upgrade-from-office-2007-servers-and-products.md)
  
