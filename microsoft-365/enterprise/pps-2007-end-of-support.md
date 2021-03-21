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
description: PerformancePoint Server 2007, ProClarity e SharePoint Server 2007 chegaram ao fim do suporte. Leia este artigo para ajudar a planejar a atualização da solução de BI.
ms.openlocfilehash: aa6adae24d78b6be72f17fd56c272b1293e6fcdc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927331"
---
# <a name="performancepoint-server-2007-end-of-support-roadmap"></a>Roteiro de fim do suporte do PerformancePoint Server 2007

*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*

Os servidores e aplicativos do Office 2007 chegaram ao fim do suporte, incluindo servidores e aplicativos que você pode estar usando como parte de suas soluções de business intelligence (BI). A tabela a seguir lista os aplicativos de BI afetados:
  
|**Aplicativos Microsoft BI**|**Suporte de data encerrada**|
|:-----|:-----|
|Service Pack 3 do ProClarity Analytics Server 6.3  <br/> ProClarity Desktop Professional 6.3  <br/> Visualizador do SharePoint ProClarity 6.3  <br/> |11 de julho de 2017  <br/> |
|SharePoint Server 2007 Service Pack 3  <br/> |10 de outubro de 2017  <br/> |
|PerformancePoint Server 2007 Service Pack 3  <br/> |9 de janeiro de 2018  <br/> |
   
Para obter mais informações, consulte Recursos para ajudá-lo a atualizar dos servidores e clientes [do Office 2007.](upgrade-from-office-2007-servers-and-products.md)
  
## <a name="what-does-end-of-support-mean"></a>O que *significa o fim do suporte?*

Como a maioria dos produtos Microsoft, PerformancePoint Server 2007 SP3, software ProClarity e SharePoint Server 2007 SP3 têm um ciclo de vida de suporte, durante o qual a Microsoft fornece novos recursos, correções de bugs e atualizações de segurança. O ciclo de vida de um produto geralmente dura 10 anos a partir da versão inicial do produto. O final desse ciclo de vida é conhecido como o fim do suporte do produto. Como o ProClarity, PerformancePoint Server e o SharePoint Server 2007 chegaram ao fim do suporte, a Microsoft não fornece mais:
  
- Suporte técnico para problemas que podem ocorrer.
    
- Correções de bugs para problemas descobertos e que podem afetar a estabilidade e a usabilidade dos servidores.
    
- Correções de segurança para vulnerabilidades descobertas e que podem tornar servidores ou aplicativos vulneráveis a violações de segurança.
    
- Atualizações de fuso horário.
    
Sua instalação do ProClarity, do SharePoint Server 2007 SP3 e do PerformancePoint Server 2007 SP3 continuará sendo executado mesmo que o suporte tenha terminado. No entanto, recomendamos que você migre desses aplicativos assim que possível.
  
## <a name="what-are-my-options"></a>Quais são minhas opções?

Houve muitas alterações nos aplicativos do Microsoft BI desde 2007 e você tem várias opções a considerar, conforme resumido na tabela a seguir.
  
|**Se você estivesse usando este ...**|**Explore essas opções...**|**E tenha isso em mente...**|
|:-----|:-----|:-----|
| PerformancePoint Server de Análise de Monitoramento 2007, &amp; incluindo:<br/>- PerformancePoint Monitoring Server <br/>- PerformancePoint Dashboard Designer<br/>- Visualizador de painel para SharePoint Services (usado para renderizar painéis, scorecards e relatórios do PerformancePoint)<br/> |**Excel com Excel em um navegador** (na nuvem ou local). Para uma visão geral, consulte [Recursos de BI no Excel e no Microsoft 365](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx).<br/><br/> **Power BI** (na nuvem ou local). Para uma visão geral, consulte [O que é o Power BI?](https://go.microsoft.com/fwlink/?linkid=841341) <br/><br/> **SQL Server Reporting Services** (local). Para uma visão geral, [consulte SQL Server Reporting Services (SSRS): Criar,](/sql/reporting-services/create-deploy-and-manage-mobile-and-paginated-reports)implantar e gerenciar relatórios móveis e paginados. <br/><br/> **Serviços PerformancePoint** (local). Para uma visão geral, consulte Novidades para [Serviços PerformancePoint (SharePoint Server 2010)](/previous-versions/office/sharepoint-server-2010/ee661741(v=office.14)). <br/> |O Excel está disponível como uma solução online (baseada em nuvem) ou local. Muitas necessidades de relatório e painel podem ser atendidas com o Excel.  <br/><br/> O Power BI está disponível como uma solução online ou local. O Power BI não está incluído no Microsoft 365. Mas você pode começar a usar o Power BI gratuitamente. Mais tarde, dependendo do uso de dados e das necessidades de negócios, você pode atualizar para o Power BI Pro com o Microsoft 365 E5.<br/> <br/> Os Serviços de Relatório e Serviços PerformancePoint são soluções locais. <br/><br/> Serviços PerformancePoint está disponível no SharePoint Server 2010, no SharePoint Server 2013 e no SharePoint Server 2016. <br/> <br/> Alguns recursos e tipos de relatório que estavam disponíveis no PerformancePoint Server 2007 não estão disponíveis no Excel, Power BI, Reporting Services ou Serviços PerformancePoint. Revise os recursos disponíveis para determinar a melhor solução para suas necessidades de negócios. <br/> |
| Software ProClarity, incluindo:<br/>- ProClarity Desktop Professional<br/> - ProClarity Analytics Server<br/>- Visualizador do SharePoint ProClarity<br/> |**Trabalhe com um parceiro da Microsoft** para identificar uma solução que atenda melhor às suas necessidades. Visite o [Microsoft Partner Center](https://go.microsoft.com/fwlink/?linkid=841249). <br/><br/> Você também pode considerar usar o Excel com o Excel em um navegador, Power BI, SQL Server Reporting Services ou Serviços PerformancePoint.  <br/> |Vários, mas nem todos os recursos do software ProClarity estão disponíveis em outras ofertas da Microsoft, incluindo Excel, Power BI, Reporting Services e Serviços PerformancePoint.  <br/> |
|KPIs do SharePoint Server 2007 (também chamados de KPIs moss)  <br/> |**Excel com Serviços do Excel**. Para uma visão geral, consulte [Business intelligence in Excel and Serviços do Excel (SharePoint Server 2013)](https://support.office.com/article/2740f10c-579d-4b40-a1d9-7beb5d38547c.aspx). <br/> |Os KPIs do MOSS criados usando o SharePoint Server 2007 podem ser usados no SharePoint Server 2010, no SharePoint Server 2013 e no SharePoint Server 2016. Mas você não pode criar novos KPIs do MOSS.  <br/> |
|Excel 2007  <br/> |**Excel** (na nuvem ou local). Para uma visão geral, consulte [Recursos de BI no Excel e no Office 365](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx). <br/><br/> **Power BI** (na nuvem ou local). Para uma visão geral, consulte [O que é o Power BI?](https://go.microsoft.com/fwlink/?linkid=841341) <br/> |O Excel e o Power BI oferecem à sua organização soluções baseadas em nuvem e locais, com suporte para uma ampla variedade de fontes de dados.  <br/> |
   
### <a name="help-selecting-a-solution"></a>Ajudar a selecionar uma solução

Com tantas opções de BI disponíveis, pode parecer avassalador determinar qual opção é a melhor. Temos um guia online disponível para ajudar. Consulte [Escolhendo ferramentas do Microsoft Business Intelligence (BI) para análise e relatórios.](/sql/reporting-services/choosing-microsoft-business-intelligence-bi-tools-for-analysis-and-reporting)
  
### <a name="what-if-i-dont-upgrade-now"></a>E se eu não atualizar agora?

Você pode optar por não atualizar imediatamente. Seus servidores e aplicativos existentes continuarão sendo executados. Mas você não receberá mais atualizações, incluindo atualizações de segurança, já que o suporte terminou. E se algo der errado com seus aplicativos de servidor, você não poderá obter ajuda do suporte técnico da Microsoft.
  
## <a name="how-do-i-plan-my-upgrade"></a>Como faço para planejar minha atualização?

Depois de explorar suas opções de atualização, a próxima etapa é preparar um plano de atualização. As seções a seguir incluem informações e recursos adicionais para ajudar. Você tem quatro opções principais, incluindo duas que funcionam na nuvem ou no local, e duas que são somente locais:
  
|**Opção**|**Na nuvem ou no local?**|
|:-----|:-----|
|[Excel com SharePoint Server (local)](#excel-with-sharepoint-server-on-premises) <br/> |Ambos  <br/> |
|[Power BI](#use-power-bi-in-the-cloud-or-on-premises)<br/> |Ambos  <br/> |
|[Serviços de relatório](#use-reporting-services-on-premises) <br/> |Somente no local  <br/> |
|[Serviços do PerformancePoint](#use-performancepoint-services-on-premises) <br/> |Somente no local  <br/> |
   
### <a name="use-excel-in-the-cloud-or-on-premises"></a>Usar o Excel (na nuvem ou no local)

Com o Excel, que também é conhecido como *Serviços do Excel* no SharePoint Server, você pode exibir e usar as planilhas em uma janela do navegador, mesmo que o Excel não seja instalado no computador. Você pode usar o Excel para criar relatórios, scorecards e painéis. Em seguida, compartilhe suas planilhas com outras pessoas, que podem usar o Excel em um navegador, se estão usando o SharePoint Online como parte do Microsoft 365 ou do SharePoint Server local. Você pode usar dados armazenados no local ou na nuvem, o que permite usar uma ampla variedade de fontes de dados.
  
A tabela a seguir compara as principais vantagens de usar o Excel com o Microsoft 365 para usar o Excel com o SharePoint Server. Mais informações a seguir.
  
|**Excel com o Microsoft 365 (na nuvem)**|**Excel com SharePoint Server (local)**|
|:-----|:-----|
|**Você tem a versão mais recente e melhor do Excel.** Com o Microsoft 365, você recebe a versão mais recente do Excel, que inclui novos tipos de gráficos poderosos, a capacidade de criar gráficos e tabelas de forma rápida e fácil e suporte para mais fontes de dados. <br/> <br/> **A instalação é muito mais simples**. O Excel está incluído no Microsoft 365 para empresas, portanto, não há nenhum levantamento pesado de sua parte. Inscreva-se e entre, e você estará funcionando de forma mais rápida e eficiente do que se atualizar seus servidores locais. <br/> <br/> **As pessoas têm acesso em todos os lugares às suas guias de trabalho.** As pessoas podem exibir com segurança as guias de trabalho de onde quer que estejam, usando o computador, o smartphone e o tablet. <br/> <br/> **Há mais!** Consulte [Recursos de BI no Excel e no Office 365](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx). <br/> |**Você gerencia suas configurações globais.** Como administrador do SharePoint, você pode especificar configurações globais, como segurança, balanceamento de carga, gerenciamento de sessão, cache de livros de trabalho e conexões de dados externos. <br/> <br/> **Você pode usar Serviços do Excel com Serviços PerformancePoint**. Você pode configurar Serviços do Excel e Serviços PerformancePoint como parte da instalação do SharePoint Server e incluir Serviços do Excel relatórios em seus painéis do PerformancePoint. <br/> <br/> **Há mais!** Consulte [Business intelligence no Excel e Serviços do Excel (SharePoint Server 2013)](https://support.office.com/article/2740f10c-579d-4b40-a1d9-7beb5d38547c.aspx). <br/> |
   
#### <a name="excel-with-microsoft-365-in-the-cloud"></a>Excel com o Microsoft 365 (na nuvem)

Se você mudar para o Microsoft 365, terá os serviços e aplicativos mais atualizados, incluindo o Excel 2016. Serviços PerformancePoint não está disponível no Microsoft 365, portanto, você substituirá o conteúdo do painel do PerformancePoint por planilhas do Excel ou outros relatórios. A boa notícia é que o Excel 2016 tem muitos tipos de gráfico novos e é mais fácil do que nunca criar painéis impressionantes no Excel. E novos recursos são adicionados regularmente. Para saber mais, confira [Novidades no Excel 2016 para Windows](https://support.office.com/article/5fdb9208-ff33-45b6-9e08-1f5cdb3a6c73.aspx).
  
Além disso, se você comprar 50 assentos ou mais do Microsoft 365, a equipe do Microsoft FastTrack poderá ajudá-lo a se configurar. Para saber mais, visite [FastTrack](https://www.microsoft.com/fasttrack/microsoft-365).
  
#### <a name="excel-with-sharepoint-server-on-premises"></a>Excel com SharePoint Server (local)

Se você atualizar para uma versão mais recente do SharePoint, poderá usar o Excel com Serviços do Excel ou em um navegador, da seguinte forma:
  
- Serviços do Excel sharepoint server 2010
    
- Serviços do Excel no SharePoint Server 2013
    
- O Excel, que faz parte do Servidor do Office Online, instalado separadamente do SharePoint Server 2016
    
Você também pode Serviços PerformancePoint em sua nova versão do SharePoint Server e usá-lo junto com o Excel.
  
Para saber mais sobre suas opções de atualização do SharePoint, consulte [SharePoint Server 2007 end of support Roadmap](sharepoint-2007-end-of-support.md).
  
Para saber mais sobre Serviços do Excel, [consulte Serviços do Excel visão geral (SharePoint Server 2010)](/previous-versions/office/sharepoint-server-2010/ee424405(v=office.14)).
  
### <a name="use-power-bi-in-the-cloud-or-on-premises"></a>Usar o Power BI (na nuvem ou no local)

O Power BI é um pacote de ferramentas de análise de negócios para analisar dados e compartilhar informações. Com o Power BI, você pode usar fontes de dados locais ou online para criar relatórios interativos e painéis. As pessoas podem exibir e usar seus relatórios e painéis em seus computadores ou dispositivos móveis.
  
O Power BI não faz parte do Microsoft 365 ou do SharePoint Server. É uma oferta separada que inclui a Área de Trabalho do Power BI, gateways do Power BI e o serviço Power BI. O Power BI também se integra ao SharePoint Online. Você pode começar com o Power BI gratuitamente. Com base no uso de dados e nas necessidades de negócios, você pode atualizar para o Power BI Pro com o Microsoft 365 E5. Para saber mais, confira [O que é o Power BI?](https://go.microsoft.com/fwlink/?linkid=841341)
  
### <a name="use-reporting-services-on-premises"></a>Usar o Reporting Services (local)

SQL Server Reporting Services fornece uma solução robusta de relatórios. Você pode configurar o Reporting Services no modo nativo ou no modo integrado ao SharePoint. Você pode usar várias ferramentas diferentes para criar relatórios, incluindo Report Designer, Construtor de Relatórios e Power View. Com a versão mais recente do SQL Server, você também pode usar SQL Server Mobile Report Publisher para fornecer relatórios que dimensionam para qualquer tamanho de tela. Isso permite que os visualizadores consumam relatórios em seus dispositivos móveis. Para saber mais, consulte SQL Server Serviços de Relatórios [(SSRS): Criar,](/sql/reporting-services/create-deploy-and-manage-mobile-and-paginated-reports)implantar e gerenciar relatórios móveis e paginados.
  
### <a name="use-performancepoint-services-on-premises"></a>Usar Serviços PerformancePoint (local)

PerformancePoint Server 2007 foi vendido separadamente do SharePoint Server 2007. A partir do SharePoint Server 2010, Serviços PerformancePoint é um aplicativo de serviço no SharePoint Server. Portanto, você não precisa comprar licenças de servidor ou hardware separados para usar Serviços PerformancePoint.
  
Para mudar de PerformancePoint Server 2007 para Serviços PerformancePoint, você move para uma versão mais recente do SharePoint Server e configura Serviços PerformancePoint. A versão do SharePoint Server que você move para determinar se você pode importar o conteúdo do painel existente do PerformancePoint Server 2007 para Serviços PerformancePoint.
  
- Se você atualizar para o SharePoint Server 2010, poderá importar o conteúdo do painel do PerformancePoint do PerformancePoint Server 2007 para o Serviços PerformancePoint no SharePoint Server 2010. Para saber mais, consulte [Import Wizard: PerformancePoint Server conteúdo 2007 para SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/ee681485(v=office.14)).
    
- Se você mudar para SharePoint Server 2013 ou SharePoint Server 2016, provavelmente precisará criar novo conteúdo de painel (fontes de dados, relatórios, scorecards e páginas de painel).
    
Para começar a trabalhar no seu Serviços PerformancePoint de atualização, consulte os seguintes recursos:
  
- [Roteiro de fim de suporte do SharePoint Server 2007](sharepoint-2007-end-of-support.md)
    
- Quando você sabe para qual versão do SharePoint você está mudando, consulte o artigo correspondente para Serviços PerformancePoint:
    
  - [Planejar os Serviços do PerformancePoint (SharePoint Server 2010)](/previous-versions/office/sharepoint-server-2010/ee681486(v=office.14))
    
  - [Visão geral do PerformancePoint Services no SharePoint Server 2013](/sharepoint/administration/performancepoint-services-overview)
    
  - [Visão geral dos Serviços PerformancePoint no SharePoint Server 2016](/sharepoint/administration/performancepoint-services-overview)
    
Quando você atualiza para Serviços PerformancePoint, você recebe vários novos recursos e aprimoramentos. Serviços PerformancePoint oferece scorecards aprimorados; novas visualizações, como o relatório Decomposition Tree e KPI Details; mais tipos de gráfico; melhores recursos de filtragem de Inteligência de Tempo; e conformidade de acessibilidade aprimorada. Para saber mais, confira [Novidades para Serviços PerformancePoint (SharePoint Server 2010)](/previous-versions/office/sharepoint-server-2010/ee661741(v=office.14)).
  
## <a name="where-can-i-get-help-with-my-upgrade"></a>Onde posso obter ajuda com minha atualização?

Se você atualiza no local ou se move para o Microsoft 365, recomendamos que você trabalhe com um parceiro da Microsoft. Um parceiro qualificado pode ajudá-lo a identificar a solução que melhor atende às suas necessidades de negócios e ajuda com sua implantação. Visite o [Microsoft Partner Center](https://go.microsoft.com/fwlink/?linkid=841249)e use os filtros de pesquisa para encontrar um provedor de soluções.
  
## <a name="related-topics"></a>Tópicos relacionados

[Recursos para ajudá-lo a atualizar de servidores e clientes do Office 2007](upgrade-from-office-2007-servers-and-products.md)