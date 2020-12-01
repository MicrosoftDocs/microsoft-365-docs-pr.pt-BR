---
title: Roteiro de fim do suporte do PerformancePoint Server 2007
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
search.appverid:
- PSV120
- PDD140
- MET150
ms.assetid: 89d9feee-2285-419c-8c14-0f7f583536e0
f1.keywords:
- NOCSH
description: O PerformancePoint Server 2007, o ProClarity e o SharePoint Server 2007 chegaram ao fim do suporte. Leia este artigo para ajudar a planejar a atualização da solução de BI.
ms.openlocfilehash: 4a13e6f8a40de78c0d98b03369b52a78899fc7a9
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519592"
---
# <a name="performancepoint-server-2007-end-of-support-roadmap"></a>Roteiro de fim do suporte do PerformancePoint Server 2007

*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*

Os servidores e aplicativos do Office 2007 atingiram o fim do suporte, incluindo servidores e aplicativos que você pode estar usando como parte de suas soluções de Business Intelligence (BI). A tabela a seguir lista os aplicativos de BI afetados:
  
|**Aplicativos Microsoft BI**|**Data de término do suporte**|
|:-----|:-----|
|ProClarity Analytics Server 6,3 Service Pack 3  <br/> ProClarity Desktop Professional 6,3  <br/> ProClarity SharePoint Viewer 6,3  <br/> |11 de julho de 2017  <br/> |
|SharePoint Server 2007 Service Pack 3  <br/> |10 de outubro de 2017  <br/> |
|PerformancePoint Server 2007 Service Pack 3  <br/> |9 de janeiro de 2018  <br/> |
   
Para obter mais informações, consulte [recursos para ajudá-lo a atualizar de clientes e servidores do Office 2007](upgrade-from-office-2007-servers-and-products.md).
  
## <a name="what-does-end-of-support-mean"></a>O que significa o *fim do suporte* ?

Como a maioria dos produtos da Microsoft, o PerformancePoint Server 2007 SP3, o software ProClarity e o SharePoint Server 2007 SP3, têm um ciclo de vida de suporte, durante o qual a Microsoft oferece novos recursos, correções de erros e atualizações de segurança. O ciclo de vida de um produto normalmente dura 10 anos da versão inicial do produto. O final desse ciclo de vida é conhecido como o fim do suporte do produto. Como ProClarity, PerformancePoint Server e SharePoint Server 2007 chegaram ao fim do suporte, a Microsoft não fornece mais:
  
- Suporte técnico para problemas que podem ocorrer.
    
- Correções de erros descobertas e que podem afetar a estabilidade e a usabilidade de servidores.
    
- Correções de segurança para vulnerabilidades descobertas e que podem tornar os servidores ou aplicativos vulneráveis a brechas de segurança.
    
- Atualizações de fuso horário.
    
Sua instalação do ProClarity, SharePoint Server 2007 SP3 e PerformancePoint Server 2007 SP3 continuarão a ser executadas, mesmo que o suporte tenha sido concluído. No entanto, é altamente recomendável migrar desses aplicativos o mais rápido possível.
  
## <a name="what-are-my-options"></a>Quais são as minhas opções?

Há muitas alterações nos aplicativos Microsoft BI desde 2007, e você tem várias opções a serem consideradas, conforme resumido na tabela a seguir.
  
|**Se você estava usando isso...**|**Explore estas opções...**|**E tenha isso em mente...**|
|:-----|:-----|:-----|
| Recursos de análise de monitoramento do PerformancePoint Server 2007 &amp; , incluindo:<br/>– PerformancePoint Monitoring Server <br/>– PerformancePoint Dashboard Designer<br/>-Dashboard Viewer para SharePoint Services (usado para renderizar painéis, scorecards e relatórios do PerformancePoint)<br/> |**Excel com o Excel em um navegador** (na nuvem ou no local). Para obter uma visão geral, consulte [recursos de BI no Excel e Microsoft 365](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx).<br/><br/> **Power bi** (na nuvem ou no local). Para obter uma visão geral, consulte [o que é Power bi?](https://go.microsoft.com/fwlink/?linkid=841341) <br/><br/> **SQL Server Reporting Services** (local). Para obter uma visão geral, consulte [SQL Server Reporting Services (SSRS): criar, implantar e gerenciar relatórios móveis e paginados](https://go.microsoft.com/fwlink/?linkid=841342). <br/><br/> **Serviços PerformancePoint** (local). Para obter uma visão geral, consulte [What ' s New for PerformancePoint Services (SharePoint Server 2010)](https://go.microsoft.com/fwlink/?linkid=841343). <br/> |O Excel está disponível como uma solução online (baseada na nuvem) ou local. Muitas necessidades de relatórios e painéis podem ser atendidas com o Excel.  <br/><br/> O Power BI está disponível como uma solução online ou local. O Power BI não está incluído no Microsoft 365. Mas você pode começar a usar o Power BI gratuitamente. Mais tarde, dependendo de suas necessidades de negócios e de uso de dados, você pode atualizar para o Power BI pro com o Microsoft 365 e5.<br/> <br/> O Reporting Services e o PerformancePoint Services são soluções locais. <br/><br/> Os Serviços PerformancePoint estão disponíveis no SharePoint Server 2010, no SharePoint Server 2013 e no SharePoint Server 2016. <br/> <br/> Alguns recursos e tipos de relatório que estavam disponíveis no PerformancePoint Server 2007 não estão disponíveis no Excel, no Power BI, no Reporting Services ou nos Serviços PerformancePoint. Revise os recursos disponíveis para determinar a melhor solução para suas necessidades de negócios. <br/> |
| Software ProClarity, incluindo:<br/>– ProClarity Desktop Professional<br/> -ProClarity Analytics Server<br/>– Visualizador do SharePoint do ProClarity<br/> |**Trabalhe com um parceiro da Microsoft** para identificar uma solução que melhor atenda às suas necessidades. Visite o [centro de parceiros da Microsoft](https://go.microsoft.com/fwlink/?linkid=841249). <br/><br/> Você também pode considerar usar o Excel com o Excel em um navegador, no Power BI, no SQL Server Reporting Services ou nos Serviços PerformancePoint.  <br/> |Vários, mas não todos os recursos do software ProClarity estão disponíveis em outras ofertas da Microsoft, incluindo Excel, Power BI, Reporting Services e serviços do PerformancePoint.  <br/> |
|KPIs do SharePoint Server 2007 (também chamados de KPIs do MOSS)  <br/> |**Excel com serviços do Excel**. Para obter uma visão geral, consulte [Business Intelligence no Excel e no Excel Services (SharePoint Server 2013)](https://support.office.com/article/2740f10c-579d-4b40-a1d9-7beb5d38547c.aspx). <br/> |KPIs MOSS que foram criados usando o SharePoint Server 2007 podem ser usados no SharePoint Server 2010, no SharePoint Server 2013 e no SharePoint Server 2016. Mas você não pode criar novos KPIs do MOSS.  <br/> |
|Excel 2007  <br/> |**Excel** (na nuvem ou no local). Para obter uma visão geral, consulte [recursos de BI no Excel e no Office 365](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx). <br/><br/> **Power bi** (na nuvem ou no local). Para obter uma visão geral, consulte [o que é Power bi?](https://go.microsoft.com/fwlink/?linkid=841341) <br/> |O Excel e o Power BI oferecem suas soluções locais e baseadas em nuvem da organização, com suporte para uma ampla variedade de fontes de dados.  <br/> |
   
### <a name="help-selecting-a-solution"></a>Ajuda para selecionar uma solução

Com tantas opções de BI disponíveis, pode parecer difícil determinar qual é a melhor opção. Temos um guia online disponível para ajudar. Consulte [escolhendo ferramentas de Business Intelligence (BI) da Microsoft para análise e relatórios](https://go.microsoft.com/fwlink/?linkid=839877).
  
### <a name="what-if-i-dont-upgrade-now"></a>E se eu não atualizar agora?

Você pode optar por não atualizar imediatamente. Os servidores e aplicativos existentes continuarão a ser executados. Mas você não receberá mais atualizações, incluindo atualizações de segurança, desde que o suporte foi concluído. E se algo der errado com seus aplicativos de servidor, você não conseguirá obter ajuda do suporte técnico da Microsoft.
  
## <a name="how-do-i-plan-my-upgrade"></a>Como planejar a atualização?

Após explorar as opções de atualização, a próxima etapa é preparar um plano de atualização. As seções a seguir incluem informações e recursos adicionais para ajudar. Você tem quatro opções principais, incluindo duas que funcionam tanto na nuvem quanto no local e duas que são somente no local:
  
|**Opção**|**Na nuvem ou no local?**|
|:-----|:-----|
|[Excel com o SharePoint Server (local)](#excel-with-sharepoint-server-on-premises) <br/> |Ambos  <br/> |
|[Power BI](#use-power-bi-in-the-cloud-or-on-premises)<br/> |Ambos  <br/> |
|[Serviços de relatório](#use-reporting-services-on-premises) <br/> |Somente local  <br/> |
|[Serviços do PerformancePoint](#use-performancepoint-services-on-premises) <br/> |Somente local  <br/> |
   
### <a name="use-excel-in-the-cloud-or-on-premises"></a>Usar o Excel (na nuvem ou local)

Com o Excel, que também é conhecido como *Serviços do Excel* no SharePoint Server, você pode exibir e usar pastas de trabalho em uma janela do navegador, mesmo que o Excel não esteja instalado no computador. Você pode usar o Excel para criar relatórios, scorecards e painéis. Em seguida, compartilhe suas pastas de trabalho com outras pessoas, que podem usar o Excel em um navegador, se estão usando o SharePoint Online como parte do Microsoft 365 ou SharePoint Server local. Você pode usar dados armazenados no local ou na nuvem, o que permite usar uma ampla variedade de fontes de dados.
  
A tabela a seguir compara as principais vantagens de usar o Excel com o Microsoft 365 para usar o Excel com o SharePoint Server. Mais informações a seguir.
  
|**Excel com Microsoft 365 (na nuvem)**|**Excel com o SharePoint Server (local)**|
|:-----|:-----|
|**Você obtém a maior e mais recente versão do Excel**. Com o Microsoft 365, você obtém a versão mais recente do Excel, que inclui novos tipos de gráfico avançados, a capacidade de criar gráficos e tabelas de forma rápida e fácil e dão suporte a mais fontes de dados. <br/> <br/> **A configuração é muito mais simples**. O Excel está incluído no Microsoft 365 for Business e, portanto, não há trabalho pesado em sua parte. Inscreva-se e entre, e você estará em funcionamento mais rápido e com mais eficiência do que se atualizar seus servidores locais. <br/> <br/> **As pessoas têm acesso às suas pastas de trabalho**. As pessoas podem exibir pastas de trabalho com segurança de qualquer lugar, usando o computador, o telefone inteligente e o Tablet. <br/> <br/> **Há mais!** Veja [recursos de BI no Excel e no Office 365](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx). <br/> |**Você gerencia as configurações globais**. Como administrador do SharePoint, você pode especificar configurações globais, como segurança, balanceamento de carga, gerenciamento de sessão, cache de pasta de trabalho e conexões de dados externos. <br/> <br/> **Você pode usar os serviços do Excel com o PerformancePoint Services**. Você pode configurar os serviços do Excel e os serviços do PerformancePoint como parte da sua instalação do SharePoint Server e incluir relatórios do Excel Services em seus painéis do PerformancePoint. <br/> <br/> **Há mais!** Veja [Business Intelligence no Excel e no Excel Services (SharePoint Server 2013)](https://support.office.com/article/2740f10c-579d-4b40-a1d9-7beb5d38547c.aspx). <br/> |
   
#### <a name="excel-with-microsoft-365-in-the-cloud"></a>Excel com Microsoft 365 (na nuvem)

Se você mudar para o Microsoft 365, terá os serviços e aplicativos mais recentes, incluindo o Excel 2016. Os serviços do PerformancePoint não estão disponíveis no Microsoft 365, portanto, você substituirá o conteúdo do seu painel do PerformancePoint com pastas de trabalho do Excel ou outros relatórios. A boa notícia é que o Excel 2016 tem vários novos tipos de gráfico e é mais fácil do que nunca criar painéis impressionantes no Excel. E novos recursos são adicionados regularmente. Para saber mais, confira [What ' s New in Excel 2016 for Windows](https://support.office.com/article/5fdb9208-ff33-45b6-9e08-1f5cdb3a6c73.aspx).
  
Além disso, se você adquirir 50 estações ou mais do Microsoft 365, a equipe do Microsoft FastTrack pode ajudá-lo a ser configurado. Para saber mais, visite o [FastTrack](https://www.microsoft.com/fasttrack/microsoft-365).
  
#### <a name="excel-with-sharepoint-server-on-premises"></a>Excel com o SharePoint Server (local)

Se você atualizar para uma versão mais recente do SharePoint, poderá usar o Excel com os serviços do Excel ou em um navegador, da seguinte maneira:
  
- Serviços do Excel no SharePoint Server 2010
    
- Serviços do Excel no SharePoint Server 2013
    
- Excel, que faz parte do servidor do Office Online, instalado separadamente do SharePoint Server 2016
    
Você também pode configurar os Serviços PerformancePoint na nova versão do SharePoint Server e usá-los junto com o Excel.
  
Para saber mais sobre suas opções de atualização do SharePoint, confira [roteiro de final de suporte do SharePoint Server 2007](sharepoint-2007-end-of-support.md).
  
Para saber mais sobre os serviços do Excel, confira [visão geral dos serviços do Excel (SharePoint Server 2010)](https://go.microsoft.com/fwlink/?linkid=841362).
  
### <a name="use-power-bi-in-the-cloud-or-on-premises"></a>Usar o Power BI (na nuvem ou no local)

O Power BI é um pacote de ferramentas de análise de negócios para analisar dados e compartilhar ideias. Com o Power BI, você pode usar fontes de dados locais ou online para criar relatórios e painéis interativos. As pessoas podem exibir e usar seus relatórios e painéis em seus computadores ou dispositivos móveis.
  
O Power BI não faz parte do Microsoft 365 ou do SharePoint Server. É uma oferta separada que inclui o Power BI desktop, os gateways do Power BI e o serviço do Power BI. O Power BI também se integra ao SharePoint Online. Você pode começar a usar o Power BI gratuitamente. Com base em suas necessidades de negócios e uso de dados, você pode atualizar mais tarde para o Power BI pro com o Microsoft 365 e5. Para saber mais, confira [o que é o Power bi?](https://go.microsoft.com/fwlink/?linkid=841341)
  
### <a name="use-reporting-services-on-premises"></a>Usar o Reporting Services (local)

O SQL Server Reporting Services oferece uma solução de relatórios robusta. Você pode configurar o Reporting Services no modo nativo ou no modo integrado do SharePoint. Você pode usar várias ferramentas diferentes para criar relatórios, incluindo o designer de relatórios, o construtor de relatórios e o Power View. Com a versão mais recente do SQL Server, você também pode usar o editor de relatório móvel do SQL Server para entregar relatórios que são dimensionados para qualquer tamanho de tela. Isso permite que os usuários consumam relatórios em seus dispositivos móveis. Para saber mais, consulte [SQL Server Reporting Services (SSRS): criar, implantar e gerenciar relatórios móveis e paginados](https://go.microsoft.com/fwlink/?linkid=841342).
  
### <a name="use-performancepoint-services-on-premises"></a>Usar os Serviços PerformancePoint (local)

O PerformancePoint Server 2007 foi vendido separadamente do SharePoint Server 2007. Começando com o SharePoint Server 2010, os Serviços PerformancePoint são um aplicativo de serviço no SharePoint Server. Portanto, não é necessário adquirir licenças ou hardware de servidor separado para usar os Serviços PerformancePoint.
  
Para migrar do PerformancePoint Server 2007 para os serviços do PerformancePoint, você vai para uma versão mais recente do SharePoint Server e configurar os Serviços PerformancePoint. A versão do SharePoint Server que você move para determinará se é possível importar seu conteúdo de painel existente do PerformancePoint Server 2007 para os Serviços PerformancePoint.
  
- Se você atualizar para o SharePoint Server 2010, poderá importar o conteúdo do seu painel do PerformancePoint do PerformancePoint Server 2007 para os Serviços PerformancePoint no SharePoint Server 2010. Para saber mais, confira [Assistente de importação: conteúdo do PerformancePoint server 2007 para o SharePoint server 2010](https://go.microsoft.com/fwlink/?linkid=838873).
    
- Se você migrar para o SharePoint Server 2013 ou o SharePoint Server 2016, provavelmente precisará criar novo conteúdo de painel (fontes de dados, relatórios, scorecards e páginas de painel).
    
Para começar a usar o plano de atualização do PerformancePoint Services, confira os seguintes recursos:
  
- [Roteiro de fim do suporte do SharePoint Server 2007](sharepoint-2007-end-of-support.md)
    
- Quando você souber de qual versão do SharePoint você está migrando, consulte o artigo correspondente para o PerformancePoint Services:
    
  - [Planejar os Serviços do PerformancePoint (SharePoint Server 2010)](https://go.microsoft.com/fwlink/?linkid=841363)
    
  - [Visão geral do PerformancePoint Services no SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=841551)
    
  - [Visão geral dos Serviços PerformancePoint no SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=874704)
    
Ao atualizar para os serviços do PerformancePoint, você obtém vários recursos e aprimoramentos novos. Os Serviços PerformancePoint oferecem scorecards aprimorados; novas visualizações, como a árvore de decomposição e o relatório de detalhes do KPI; mais tipos de gráfico; melhores recursos de filtragem de inteligência de tempo; e melhor conformidade de acessibilidade. Para saber mais, confira [What ' s New for PerformancePoint Services (SharePoint Server 2010)](https://go.microsoft.com/fwlink/?linkid=841343).
  
## <a name="where-can-i-get-help-with-my-upgrade"></a>Onde posso obter ajuda com a atualização?

Se você atualizar o local ou mudar para o Microsoft 365, recomendamos que você trabalhe com um parceiro da Microsoft. Um parceiro qualificado pode ajudá-lo a identificar a solução que melhor atenda às suas necessidades de negócios e ajuda com sua implantação. Visite o [centro de parceiros da Microsoft](https://go.microsoft.com/fwlink/?linkid=841249)e use os filtros de pesquisa para encontrar um provedor de soluções.
  
## <a name="related-topics"></a>Tópicos relacionados

[Recursos para ajudá-lo a atualizar de clientes e servidores do Office 2007](upgrade-from-office-2007-servers-and-products.md)