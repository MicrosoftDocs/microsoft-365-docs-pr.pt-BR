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

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Os servidores e aplicativos do Office 2007 chegaram ao fim do suporte, incluindo servidores e aplicativos que você pode estar usando como parte de suas soluções de business intelligence (BI). A tabela a seguir lista os aplicativos de BI afetados:
  
|**Aplicativos de BI da Microsoft**|**Suporte a data final**|
|:-----|:-----|
|ProClarity Analytics Server 6.3 Service Pack 3  <br/> ProClarity Desktop Professional 6.3  <br/> ProClarity SharePoint Viewer 6.3  <br/> |11 de julho de 2017  <br/> |
|SharePoint Server 2007 Service Pack 3  <br/> |10 de outubro de 2017  <br/> |
|PerformancePoint Server 2007 Service Pack 3  <br/> |9 de janeiro de 2018  <br/> |
   
Para obter mais informações, consulte Recursos para ajudá-lo a atualizar de clientes e servidores do [Office 2007.](upgrade-from-office-2007-servers-and-products.md)
  
## <a name="what-does-end-of-support-mean"></a>O que *significa o fim do suporte?*

Como a maioria dos produtos da Microsoft, o PerformancePoint Server 2007 SP3, o software ProClarity e o SharePoint Server 2007 SP3 têm um ciclo de vida de suporte, durante o qual a Microsoft fornece novos recursos, correções de bugs e atualizações de segurança. O ciclo de vida de um produto geralmente dura 10 anos a partir do lançamento inicial do produto. O fim desse ciclo de vida é conhecido como o fim do suporte do produto. Como o ProClarity, o PerformancePoint Server e o SharePoint Server 2007 chegaram ao fim do suporte, a Microsoft não oferece mais:
  
- Suporte técnico para problemas que podem ocorrer.
    
- Correções de bugs para problemas descobertos e que podem afetar a estabilidade e a usabilidade dos servidores.
    
- Correções de segurança para vulnerabilidades descobertas e que podem tornar servidores ou aplicativos vulneráveis a violações de segurança.
    
- Atualizações de fuso horário.
    
Sua instalação do ProClarity, do SharePoint Server 2007 SP3 e do PerformancePoint Server 2007 SP3 continuará a ser executado mesmo que o suporte tenha terminado. No entanto, recomendamos que você migre desses aplicativos assim que possível.
  
## <a name="what-are-my-options"></a>Quais são as minhas opções?

Houve muitas alterações nos aplicativos de BI da Microsoft desde 2007, e você tem várias opções a considerar, conforme resumido na tabela a seguir.
  
|**Se você estava usando este ...**|**Explore estas opções...**|**E lembre-se disso...**|
|:-----|:-----|:-----|
| Recursos do PerformancePoint Server 2007 Monitoring &amp; Analytics, incluindo:<br/>- PerformancePoint Monitoring Server <br/>- PerformancePoint Dashboard Designer<br/>- Dashboard Viewer para SharePoint Services (usado para renderizar painéis, scorecards e relatórios do PerformancePoint)<br/> |**Excel com Excel em um navegador** (na nuvem ou no local). Para ter uma visão geral, confira [os recursos de BI no Excel e no Microsoft 365.](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx)<br/><br/> **Power BI** (na nuvem ou no local). Para uma visão geral, confira [O que é o Power BI?](https://go.microsoft.com/fwlink/?linkid=841341) <br/><br/> **SQL Server Reporting Services** (local). Para uma visão geral, consulte [SQL Server Reporting Services (SSRS): criar,](https://go.microsoft.com/fwlink/?linkid=841342)implantar e gerenciar relatórios móveis e paginados. <br/><br/> **PerformancePoint Services** (local). Para uma visão geral, [consulte Novidades dos Serviços PerformancePoint (SharePoint Server 2010).](https://go.microsoft.com/fwlink/?linkid=841343) <br/> |O Excel está disponível como uma solução online (baseada em nuvem) ou local. Muitas necessidades de relatórios e painéis podem ser atendidas com o Excel.  <br/><br/> O Power BI está disponível como uma solução online ou local. O Power BI não está incluído no Microsoft 365. Mas você pode começar a usar o Power BI gratuitamente. Mais tarde, dependendo de seu uso de dados e necessidades comerciais, você pode atualizar para o Power BI Pro com o Microsoft 365 E5.<br/> <br/> Reporting Services e PerformancePoint Services são soluções locais. <br/><br/> O PerformancePoint Services está disponível no SharePoint Server 2010, SharePoint Server 2013 e SharePoint Server 2016. <br/> <br/> Alguns recursos e tipos de relatório que estavam disponíveis no PerformancePoint Server 2007 não estão disponíveis no Excel, Power BI, Reporting Services ou PerformancePoint Services. Revise os recursos disponíveis para determinar a melhor solução para suas necessidades de negócios. <br/> |
| Software ProClarity, incluindo:<br/>- ProClarity Desktop Professional<br/> - ProClarity Analytics Server<br/>- ProClarity SharePoint Viewer<br/> |**Trabalhe com um parceiro da Microsoft** para identificar uma solução que melhor atenda às suas necessidades. Visite o [Microsoft Partner Center.](https://go.microsoft.com/fwlink/?linkid=841249) <br/><br/> Você também pode considerar o uso do Excel com o Excel em um navegador, Power BI, SQL Server Reporting Services ou PerformancePoint Services.  <br/> |Vários, mas nem todos os recursos do software ProClarity estão disponíveis em outras ofertas da Microsoft, incluindo Excel, Power BI, Reporting Services e PerformancePoint Services.  <br/> |
|KPIs do SharePoint Server 2007 (também chamados de KPIs moss)  <br/> |**Excel com Excel Services**. Para uma visão geral, [consulte Business intelligence no Excel e nos Serviços do Excel (SharePoint Server 2013).](https://support.office.com/article/2740f10c-579d-4b40-a1d9-7beb5d38547c.aspx) <br/> |Os KPIs do MOSS criados usando o SharePoint Server 2007 podem ser usados no SharePoint Server 2010, no SharePoint Server 2013 e no SharePoint Server 2016. Mas você não pode criar novos KPIs do MOSS.  <br/> |
|Excel 2007  <br/> |**Excel** (na nuvem ou no local). Para ter uma visão geral, confira [os recursos de BI no Excel e no Office 365.](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx) <br/><br/> **Power BI** (na nuvem ou no local). Para uma visão geral, confira [O que é o Power BI?](https://go.microsoft.com/fwlink/?linkid=841341) <br/> |Tanto o Excel quanto o Power BI oferecem soluções locais e baseadas em nuvem da sua organização, com suporte para uma ampla variedade de fontes de dados.  <br/> |
   
### <a name="help-selecting-a-solution"></a>Ajudar a selecionar uma solução

Com tantas opções de BI disponíveis, pode ser difícil determinar qual opção é a melhor. Temos um guia online disponível para ajudar. Consulte [Escolhendo ferramentas do Microsoft Business Intelligence (BI) para análise e relatórios.](https://go.microsoft.com/fwlink/?linkid=839877)
  
### <a name="what-if-i-dont-upgrade-now"></a>E se eu não atualizar agora?

Você pode optar por não atualizar imediatamente. Seus servidores e aplicativos existentes continuarão a ser executados. Mas você não receberá mais atualizações, incluindo atualizações de segurança, desde que o suporte foi encerrado. E se algo der errado com seus aplicativos de servidor, você não poderá obter ajuda do suporte técnico da Microsoft.
  
## <a name="how-do-i-plan-my-upgrade"></a>Como faço para planejar minha atualização?

Depois de explorar suas opções de atualização, a próxima etapa é preparar um plano de atualização. As seções a seguir incluem informações e recursos adicionais para ajudar. Você tem quatro opções principais, incluindo duas que funcionam na nuvem ou no local e duas que são apenas locais:
  
|**Opção**|**Na nuvem ou no local?**|
|:-----|:-----|
|[Excel com SharePoint Server (local)](#excel-with-sharepoint-server-on-premises) <br/> |Ambos  <br/> |
|[Power BI](#use-power-bi-in-the-cloud-or-on-premises)<br/> |Ambos  <br/> |
|[Serviços de relatório](#use-reporting-services-on-premises) <br/> |Somente no local  <br/> |
|[Serviços do PerformancePoint](#use-performancepoint-services-on-premises) <br/> |Somente no local  <br/> |
   
### <a name="use-excel-in-the-cloud-or-on-premises"></a>Usar o Excel (na nuvem ou no local)

Com o Excel, que também é conhecido como Serviços do *Excel* no SharePoint Server, você pode exibir e usar as planilhas em uma janela do navegador, mesmo se o Excel não estiver instalado no computador. Você pode usar o Excel para criar relatórios, scorecards e painéis. Em seguida, compartilhe suas planilhas com outras pessoas, que podem usar o Excel em um navegador, se eles estão usando o SharePoint Online como parte do Microsoft 365 ou SharePoint Server local. Você pode usar dados armazenados no local ou na nuvem, o que permite usar uma ampla variedade de fontes de dados.
  
A tabela a seguir compara as principais vantagens de usar o Excel com o Microsoft 365 para usar o Excel com o SharePoint Server. Mais informações a seguir.
  
|**Excel com o Microsoft 365 (na nuvem)**|**Excel com SharePoint Server (local)**|
|:-----|:-----|
|**Você pode obter a melhor e mais recente versão do Excel.** Com o Microsoft 365, você recebe a versão mais recente do Excel, que inclui novos tipos de gráfico poderosos, a capacidade de criar gráficos e tabelas de forma rápida e fácil e o suporte para mais fontes de dados. <br/> <br/> **A instalação é muito mais simples.** O Excel está incluído no Microsoft 365 para empresas, portanto, não há trabalho pesado de sua parte. Inscreva-se e entre, e você estará em execução de forma mais rápida e eficiente do que se atualizasse seus servidores locais. <br/> <br/> **As pessoas têm em todos os lugares acesso às suas guias de trabalho.** As pessoas podem exibir com segurança as workbooks de onde quer que estejam, usando seu computador, smartphone e tablet. <br/> <br/> **Há mais!** Confira [os recursos de BI no Excel e no Office 365.](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx) <br/> |**Você gerencia suas configurações globais.** Como administrador do SharePoint, você pode especificar configurações globais, como segurança, balanceamento de carga, gerenciamento de sessão, cache de livro de trabalho e conexões de dados externos. <br/> <br/> **Você pode usar os Serviços do Excel com os Serviços PerformancePoint.** Você pode configurar os Serviços do Excel e o PerformancePoint Services como parte da instalação do SharePoint Server e incluir relatórios dos Serviços do Excel em seus painéis do PerformancePoint. <br/> <br/> **Há mais!** Consulte [Business intelligence no Excel e nos Serviços do Excel (SharePoint Server 2013).](https://support.office.com/article/2740f10c-579d-4b40-a1d9-7beb5d38547c.aspx) <br/> |
   
#### <a name="excel-with-microsoft-365-in-the-cloud"></a>Excel com o Microsoft 365 (na nuvem)

Se você mudar para o Microsoft 365, terá os serviços e aplicativos mais atualizados, incluindo o Excel 2016. O PerformancePoint Services não está disponível no Microsoft 365, portanto, você substituirá o conteúdo do painel do PerformancePoint por planilhas do Excel ou outros relatórios. A boa notícia é que o Excel 2016 tem muitos tipos de gráficos novos e está mais fácil do que nunca criar painéis atraentes no Excel. E novos recursos são adicionados regularmente. Para saber mais, confira [Novidades no Excel 2016 para Windows.](https://support.office.com/article/5fdb9208-ff33-45b6-9e08-1f5cdb3a6c73.aspx)
  
Além disso, se você comprar 50 assentos ou mais do Microsoft 365, a equipe do Microsoft FastTrack poderá ajudá-lo a se configurar. Para saber mais, visite [o FastTrack.](https://www.microsoft.com/fasttrack/microsoft-365)
  
#### <a name="excel-with-sharepoint-server-on-premises"></a>Excel com SharePoint Server (local)

Se você atualizar para uma versão mais recente do SharePoint, poderá usar o Excel com os Serviços do Excel ou em um navegador, da seguinte forma:
  
- Serviços do Excel no SharePoint Server 2010
    
- Serviços do Excel no SharePoint Server 2013
    
- O Excel, que faz parte do Servidor do Office Online, instalado separadamente do SharePoint Server 2016
    
Você também pode configurar o PerformancePoint Services em sua nova versão do SharePoint Server e usá-lo junto com o Excel.
  
Para saber mais sobre suas opções de atualização do SharePoint, consulte [SharePoint Server 2007 end of support Roadmap](sharepoint-2007-end-of-support.md).
  
Para saber mais sobre os Serviços do Excel, consulte [Excel Services overview (SharePoint Server 2010).](https://go.microsoft.com/fwlink/?linkid=841362)
  
### <a name="use-power-bi-in-the-cloud-or-on-premises"></a>Usar o Power BI (na nuvem ou no local)

O Power BI é um pacote de ferramentas de análise de negócios para analisar dados e compartilhar ideias. Com o Power BI, você pode usar fontes de dados locais ou online para criar relatórios e painéis interativos. As pessoas podem exibir e usar seus relatórios e painéis em seus computadores ou dispositivos móveis.
  
O Power BI não faz parte do Microsoft 365 ou do SharePoint Server. É uma oferta separada que inclui a Área de Trabalho do Power BI, gateways do Power BI e o serviço do Power BI. O Power BI também se integra ao SharePoint Online. Você pode começar a usar o Power BI gratuitamente. Com base em suas necessidades comerciais e de uso de dados, você pode atualizar posteriormente para o Power BI Pro com o Microsoft 365 E5. Para saber mais, veja [O que é o Power BI?](https://go.microsoft.com/fwlink/?linkid=841341)
  
### <a name="use-reporting-services-on-premises"></a>Usar o Reporting Services (local)

O SQL Server Reporting Services fornece uma solução robusta de relatórios. Você pode configurar o Reporting Services no modo nativo ou no modo integrado do SharePoint. Você pode usar várias ferramentas diferentes para criar relatórios, incluindo o Designer de Relatórios, o Construtor de Relatórios e o Power View. Com a versão mais recente do SQL Server, você também pode usar o SQL Server Mobile Report Publisher para fornecer relatórios que dimensionam para qualquer tamanho de tela. Isso permite que os visualizadores consumam relatórios em seus dispositivos móveis. Para saber mais, consulte [SQL Server Reporting Services (SSRS): criar,](https://go.microsoft.com/fwlink/?linkid=841342)implantar e gerenciar relatórios móveis e paginados.
  
### <a name="use-performancepoint-services-on-premises"></a>Usar os Serviços PerformancePoint (no local)

O PerformancePoint Server 2007 foi vendido separadamente do SharePoint Server 2007. A partir do SharePoint Server 2010, o PerformancePoint Services é um aplicativo de serviço no SharePoint Server. Portanto, você não precisa comprar licenças de servidor ou hardware separados para usar o PerformancePoint Services.
  
Para mover do PerformancePoint Server 2007 para o PerformancePoint Services, você move para uma versão mais recente do SharePoint Server e configura o PerformancePoint Services. A versão do SharePoint Server para a qual você move determina se é possível importar o conteúdo do painel existente do PerformancePoint Server 2007 para o PerformancePoint Services.
  
- Se você atualizar para o SharePoint Server 2010, poderá importar o conteúdo do painel do PerformancePoint do PerformancePoint Server 2007 para o PerformancePoint Services no SharePoint Server 2010. Para saber mais, consulte [Assistente de Importação: conteúdo do PerformancePoint Server 2007 para o SharePoint Server 2010.](https://go.microsoft.com/fwlink/?linkid=838873)
    
- Se você mudar para o SharePoint Server 2013 ou SharePoint Server 2016, provavelmente precisará criar novo conteúdo de painel (fontes de dados, relatórios, scorecards e páginas de painel).
    
Para começar a trabalhar em seu plano de atualização do PerformancePoint Services, consulte os seguintes recursos:
  
- [Roteiro de fim do suporte do SharePoint Server 2007](sharepoint-2007-end-of-support.md)
    
- Quando você sabe para qual versão do SharePoint você está mudando, consulte o artigo correspondente do PerformancePoint Services:
    
  - [Planejar os Serviços do PerformancePoint (SharePoint Server 2010)](https://go.microsoft.com/fwlink/?linkid=841363)
    
  - [Visão geral do PerformancePoint Services no SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=841551)
    
  - [Visão geral dos Serviços PerformancePoint no SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=874704)
    
Ao atualizar para o PerformancePoint Services, você recebe vários novos recursos e aprimoramentos. Os Serviços PerformancePoint oferecem scorecards aprimorados; novas visualizações, como a Árvore de Decomposição e o relatório de Detalhes de KPI; mais tipos de gráfico; melhores recursos de filtragem de inteligência de dados temporização; e conformidade de acessibilidade aprimorada. Para saber mais, consulte [Novidades do PerformancePoint Services (SharePoint Server 2010).](https://go.microsoft.com/fwlink/?linkid=841343)
  
## <a name="where-can-i-get-help-with-my-upgrade"></a>Onde posso obter ajuda com a atualização?

Se você atualizar no local ou mudar para o Microsoft 365, recomendamos que você trabalhe com um parceiro da Microsoft. Um parceiro qualificado pode ajudá-lo a identificar a solução que melhor atenda às suas necessidades de negócios e ajuda com sua implantação. Visite o [Microsoft Partner Center](https://go.microsoft.com/fwlink/?linkid=841249)e use os filtros de pesquisa para encontrar um provedor de soluções.
  
## <a name="related-topics"></a>Tópicos relacionados

[Recursos para ajudá-lo a atualizar de servidores e clientes do Office 2007](upgrade-from-office-2007-servers-and-products.md)