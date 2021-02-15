---
title: Modelos de arquitetura para SharePoint, Exchange, Skype for Business e Lync
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/16/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Ent_Architecture
ms.assetid: 5b49fa68-f8f2-4705-af96-5f5475e8539a
search.appverid:
- MET150
description: Receba cartazes de TI que descrevem os modelos de arquitetura, implantação e opções de plataforma para SharePoint, Exchange, Skype for Business e Lync.
ms.openlocfilehash: 6d5cda89fb67f5c41dcf161abe7258c4600ee8ce
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48919815"
---
# <a name="architectural-models-for-sharepoint-exchange-skype-for-business-and-lync"></a>Modelos de arquitetura para SharePoint, Exchange, Skype for Business e Lync

Os cartazes de IT neste artigo descrevem os modelos de arquitetura e as opções de implantação para o SharePoint, o Exchange, o Skype for Business e o Lync. Eles também fornecem informações de design para implantar o SharePoint no Microsoft Azure.
  
Usando o Microsoft 365, você pode fornecer serviços familiares de colaboração e comunicação por meio da nuvem. Com algumas exceções, a experiência do usuário permanece a mesma, quer você esteja mantendo uma implantação local ou usando o Microsoft 365. 

Essa experiência unificada do usuário complica a decisão de onde colocar cada carga de trabalho. Ele também gera perguntas:
  
- Como escolher uma plataforma para cargas de trabalho individuais?
    
- Faz sentido manter algum serviço local?
    
- Em qual cenário uma implantação híbrida é apropriada?
    
- Como o Azure se encaixa na imagem?
    
- Quais configurações de cargas de trabalho de servidor do Office são suportadas pelo Azure?
    
> [!TIP]
> A maioria dos cartazes deste artigo está disponível em vários idiomas. Os idiomas disponíveis incluem chinês, inglês, francês, alemão, italiano, japonês, coreano, português, russo e espanhol. Para baixar um cartaz em um desses idiomas, na imagem em miniatura do cartaz, selecione **Mais idiomas.**
  
Envie-nos suas sugestões! Envie um email para [cloudadopt@microsoft.com](mailto:cloudadopt@microsoft.com). 
  
Use os links a seguir para obter os cartazes necessários:
  
- **Modelos** arquitetônicos: use esses recursos para determinar a plataforma e a configuração ideais para o SharePoint 2016 e o Skype for Business 2015.
    
  - [Modelos de arquitetura do Microsoft SharePoint 2016](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2016_ArchModel)
    
  - [Bancos de dados do SharePoint Server 2016](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2016_Databases)
    
  - [Modelos de arquitetura do Microsoft Skype for Business 2015](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SfB2015_ArchModel)
    
- **Plataforma:** use estes recursos para determinar a plataforma e a configuração ideais para o SharePoint 2013, o Exchange 2013 e o Lync 2013.
    
  - [Opções de plataforma do SharePoint 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2013_Options)
    
  - [Opções de plataforma do Exchange 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Exch2013_options)
    
  - [Opções de plataforma do Lync 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Lync2013_Options)
    
- **SharePoint Server 2013 no Azure:** use estes cartazes de TI para projetar e configurar cargas de trabalho do SharePoint Server 2013 nos serviços de infraestrutura do Azure.
    
  - [Sites da Internet no Azure usando o SharePoint Server 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Azure_sharepoint2013)
    
  - [Amostra de design: sites da Internet no Azure para SharePoint 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#DesignSampleInternetSites)
    
  - [Recuperação de desastre do SharePoint para o Azure](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#sharepoint_recovery_Azure)
    
## <a name="architectural-models-posters"></a>Cartazes com modelos de arquitetura

Os cartazes de IT para o SharePoint 2016 e o Skype for Business 2015 oferecem uma maneira de comparar métodos de implantação em um formato fácil de imprimir. Os cartazes listam todas as opções de configuração ou plataforma. Eles fornecem as seguintes informações para cada opção:
  
- **Visão** geral: um breve resumo da plataforma, incluindo um diagrama conceitual.
    
- **Melhor para:** cenários comuns que são ideais para a plataforma.
    
- **Requisitos de** licença: as licenças de que você precisa para a implantação.
    
- **Tarefas de** arquitetura: as decisões que você precisa tomar como arquiteto.
    
- **Tarefas ou responsabilidades dos** profissionais de IT: as responsabilidades diárias que sua equipe de IT precisa planejar.
    
<a name="SP2016_ArchModel"> </a>
### <a name="microsoft-sharepoint-server-2016-architectural-models"></a>Modelos de arquitetura do Microsoft SharePoint Server 2016

|Item|Descrição|
|---|---|
|[![Miniatura do cartaz modelos de arquitetura do SharePoint Server 2016.](../media/7d3e590c-1f3b-42cf-920d-9edac8fa3e04.png)          ](https://www.microsoft.com/download/details.aspx?id=52650) <br/> [PDF](https://download.microsoft.com/download/4/F/A/4FA0F94B-EE2F-41DB-A047-D9864FEF41E9/SharePoint2016ArchitecturalModels.pdf)  \| [Visio](https://download.microsoft.com/download/4/F/A/4FA0F94B-EE2F-41DB-A047-D9864FEF41E9/SharePoint2016ArchitecturalModels.vsdx)  \| [Mais idiomas](https://www.microsoft.com/download/details.aspx?id=52650)|Este cartaz de TI descreve as configurações locais do SharePoint Online, do Azure e do SharePoint que os tomadores de decisões de negócios e os arquitetos de soluções precisam saber. <br/><br/> - **SharePoint Online (SaaS)**: consome o SharePoint por meio de um modelo de assinatura de software como serviço (SaaS). <br/> - **SharePoint híbrido:** mova seus sites e aplicativos do SharePoint para a nuvem em seu próprio ritmo. <br/> - **SharePoint no Azure (IaaS)**: estenda seu ambiente local para o Azure e implante os servidores do SharePoint 2016 lá. (Esse modelo é recomendado para ambientes de alta disponibilidade ou recuperação de desastres e ambientes dev/teste.) <br/> - **SharePoint local:** planejar, implantar, manter e personalizar seu ambiente do SharePoint em um datacenter que você mantém.|
   
<a name="SP2016_Databases"> </a>
### <a name="sharepoint-server-2016-databases"></a>Bancos de dados do SharePoint Server 2016

|Item|Descrição|
|---|---|
|[![Miniatura do cartaz bancos de dados do SharePoint Server 2016.](../media/c53e9de7-3bf8-446d-8766-e6700c8dd8e1.png)](https://www.microsoft.com/download/details.aspx?id=55041) <br/> [PDF](https://download.microsoft.com/download/D/5/D/D5DC1121-8BC5-4953-834F-1B5BB03EB691/DBrefguideSPS2016_tabloid.pdf)  \| [Visio](https://download.microsoft.com/download/D/5/D/D5DC1121-8BC5-4953-834F-1B5BB03EB691/DBrefguideSPS2016_tabloid.vsdx)  \| [Mais idiomas](https://www.microsoft.com/download/details.aspx?id=55041)|Este cartaz de IT é uma referência rápida para bancos de dados do SharePoint Server 2016. Você verá detalhes de cada banco de dados: <br/><br/> - Tamanho <br/> - Diretrizes de escala <br/> - Padrões I/O <br/> - Requisitos <br/><br/>  A primeira página mostra os bancos de dados de sistema do SharePoint e os aplicativos de serviço que têm vários bancos de dados. A segunda página mostra todos os aplicativos de serviços que têm bancos de dados únicos. <br/><br/>  Para saber mais, confira [Tipos e descrições dos bancos de dados no SharePoint Server 2016.](https://docs.microsoft.com/SharePoint/technical-reference/database-types-and-descriptions)|
   
<a name="SfB2015_ArchModel"> </a>
### <a name="microsoft-skype-for-business-2015-architectural-models"></a>Modelos de arquitetura para o Microsoft Skype for Business 2015

|Item|Descrição|
|---|---|
|[![Miniatura do cartaz modelos de arquitetura do Skype for Business.](../media/132288c0-6ae4-4394-88ab-b57dae367714.png)](https://www.microsoft.com/download/details.aspx?id=55022) <br/> [PDF](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.pdf)  \| [Visio](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.vsd)  \| [Mais idiomas](https://www.microsoft.com/download/details.aspx?id=55022)|Este cartaz descreve o Skype for Business Online, pbx (central privada de com ramificação privada) no local, híbrida e na nuvem. Ele também descreve a integração com as configurações do Exchange e do SharePoint que os tomadores de decisões de negócios e os arquitetos de soluções precisam saber. <br/><br/> O cartaz destina-se aos profissionais de IT para aumentar a conscientização dos modelos de arquitetura fundamentais por meio dos quais o Skype for Business Online e o Skype for Business local podem ser consumidos. <br/><br/>Comece com a configuração mais adequada às necessidades e aos planos da sua organização. Considere e use outras configurações conforme necessário. Por exemplo, você pode considerar a integração com o Exchange e o SharePoint ou uma solução que tira proveito da oferta do Cloud PBX da Microsoft.|
   
## <a name="platform-options-posters"></a>Cartazes com opções de plataforma

Os cartazes de IT para SharePoint 2013, Exchange 2013 e Lync 2013 fornecem uma maneira de comparar os métodos de implantação rapidamente. Cada cartaz lista todas as configurações ou opções de plataforma. Ele fornece as seguintes informações para cada opção:
  
- **Visão** geral: um breve resumo da plataforma, incluindo um diagrama conceitual.
    
- **Melhor para:** cenários comuns que são ideais para a plataforma.
    
- **Requisitos de** licença: as licenças de que você precisa para a implantação.
    
- **Tarefas de** arquitetura: as decisões que você precisa tomar como arquiteto.
    
- **Tarefas ou responsabilidades dos** profissionais de IT: as responsabilidades diárias que sua equipe de IT precisa planejar.
    
<a name="SP2013_Options"> </a>
## <a name="sharepoint-2013-platform-options"></a>Opções de Plataforma para o SharePoint 2013

|Item|Descrição|
|---|---|
|[![Imagem em miniatura do cartaz Opções de Plataforma do SharePoint 2013.](../media/SP-PlatformOptions.jpg)](https://www.microsoft.com/download/details.aspx?id=40332) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=324594)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=324593)  \| [Mais idiomas](https://www.microsoft.com/download/details.aspx?id=40332)|Para tomadores de decisões de negócios e arquitetos, este cartaz mostra as opções de plataforma para o SharePoint 2013, o SharePoint no Microsoft 365, híbrido local com implantações do Microsoft 365, Azure e somente local. Ele inclui uma visão geral de cada arquitetura, recomendações, requisitos de licença e listas de tarefas de arquitetos e profissionais de TI para cada plataforma. O cartaz destaca várias soluções do SharePoint no Azure.|
   
<a name="Exch2013_options"> </a>
## <a name="exchange-2013-platform-options"></a>Opções de plataforma para o Exchange 2013

|Item|Descrição|
|---|---|
|[![Imagem em miniatura do cartaz Opções da Plataforma do Exchange.](../media/ITPro-Other-Exchange2013PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=42676) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkID=398740)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkID=398742)  \| [Mais idiomas](https://www.microsoft.com/download/details.aspx?id=42676)|Para arquitetos e tomadores de decisões de negócios, este cartaz descreve as opções de plataforma para o Exchange 2013. Os clientes podem escolher entre o Exchange Online com o Microsoft 365, Exchange híbrido, Exchange Server local e Exchange hospedado. O cartaz detalha cada opção de arquitetura, incluindo os cenários ideais para cada uma delas, os requisitos de licença e as responsabilidades dos profissionais de IT.|
   
<a name="Lync2013_Options"> </a>
## <a name="lync-2013-platform-options"></a>Opções de plataforma para o Lync 2013

|Item|Descrição|
|---|---|
|[![Imagem em miniatura do cartaz Opções de Plataforma do Lync 2013.](../media/Lync-PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41677) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkID=391837)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkID=391839)  \| [Mais idiomas](https://www.microsoft.com/download/details.aspx?id=41677)|Para arquitetos e tomadores de decisões de negócios, este cartaz descreve as opções de plataforma para o Lync 2013. Os clientes podem escolher entre o Lync Online com o Microsoft 365, o Lync híbrido, o Lync Server local e o Lync hospedado. O cartaz de IT detalha cada opção de arquitetura, incluindo os cenários ideais para cada uma delas, os requisitos de licença e as responsabilidades dos profissionais de IT.|
   
<a name="Lync2013_Options"> </a>
## <a name="sharepoint-in-azure-solutions-posters"></a>Cartazes com soluções do SharePoint no Azure

Os cartazes de TI do SharePoint no Azure mostram soluções baseadas no Azure que usam o SharePoint Server 2013.
  
<a name="Azure_sharepoint2013"> </a>
### <a name="internet-sites-in-microsoft-azure-using-sharepoint-server-2013"></a>Sites da Internet no Microsoft Azure usando o SharePoint Server 2013

|Item|Descrição|
|---|---|
|[![Imagem dos sites da Internet no Azure usando o cartaz do SharePoint Server 2013.](../media/MS-AZ-SPInternetSites.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41992) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392552)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392551)  \| [Mais idiomas](https://www.microsoft.com/download/details.aspx?id=41992)|Este cartaz descreve as principais atividades de design e a arquitetura recomendada para sites voltados para a Internet no Azure.  <br/><br/> Para saber mais, confira os seguintes artigos:  <br/><br/> - [Sites da Internet no Azure usando o SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md) <br/> - [Arquiteturas do Azure para SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
<a name="DesignSampleInternetSites"> </a>
### <a name="internet-sites-in-azure-for-sharepoint-2013"></a>Sites da Internet no Azure para SharePoint 2013

|Item|Descrição|
|---|---|
|[![Imagem dos sites da Internet no cartaz do Microsoft Azure para SharePoint Server 2013.](../media/MS-AZ-InternetSitesDesignSample.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41991) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392549)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392548)  \| [Mais idiomas](https://www.microsoft.com/download/details.aspx?id=41991)|Use este exemplo de design como ponto de partida para sua própria arquitetura de um site voltado para a Internet no Azure usando o SharePoint Server 2013. <br/><br/> Para saber mais, confira os seguintes artigos:  <br/><br/> - [Sites da Internet no Azure usando o SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md) <br/> - [Arquiteturas do Azure para SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
<a name="sharepoint_recovery_Azure"> </a>
### <a name="sharepoint-disaster-recovery-to-microsoft-azure"></a>Recuperação de desastres do SharePoint para o Microsoft Azure

|Item|Descrição|
|---|---|
|[![Imagem do cartaz do processo de recuperação de desastres do SharePoint para o Azure.](../media/SP-DR-Azure.png)          ](https://www.microsoft.com/download/details.aspx?id=41993) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392555)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392554)  \| [Mais idiomas](https://www.microsoft.com/download/details.aspx?id=41993)|Este cartaz de TI mostra os princípios de arquitetura de um ambiente de recuperação de desastre no Azure. <br/><br/> Para saber mais, confira os seguintes artigos:  <br/><br/> - [Recuperação de desastre do SharePoint Server 2013 no Azure](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md) <br/> - [Arquiteturas do Azure para SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
## <a name="see-also"></a>Confira também

- [Centro de soluções e arquitetura do Microsoft 365](../solutions/solution-architecture-center.md)
  
- [Modelos de arquitetura em nuvem da Microsoft](../solutions/cloud-architecture-models.md)
  
- [Guias do laboratório de teste do Microsoft 365](m365-enterprise-test-lab-guides.md)
  
- [Soluções híbridas](hybrid-solutions.md)

