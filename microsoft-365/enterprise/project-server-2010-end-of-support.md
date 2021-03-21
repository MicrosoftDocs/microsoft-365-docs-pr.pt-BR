---
title: Roteiro de fim de suporte do Project Server 2010
ms.author: efrene
author: efrene
manager: pamg
ms.date: 04/14/2020
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
description: O suporte termina no Project Server 2010 em 13 de abril de 2021. Use este artigo como um guia para atualizar para o Project Online ou uma versão mais recente do Project Server local.
ms.openlocfilehash: 807c09bff0cb6331b872474acc22f8d2c622a6c6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927367"
---
# <a name="project-server-2010-end-of-support-roadmap"></a>Roteiro de encerramento de suporte do Project Server 2010

*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*

O Project Server 2010 chegará ao fim do suporte em 13 de abril de **2021**. Essa data foi estendida a partir da data anterior de término do suporte de 13 de outubro de 2020. Se você estiver usando o Project Server 2010 no momento, observe que esses produtos relacionados têm as seguintes datas de fim de suporte:

|Produto |Data de término do suporte|
|---|---|
|Project 2010 Standard|13 de outubro de 2020|
|Project 2010 Professional|13 de outubro de 2020|

Para obter mais informações sobre como chegar ao fim do suporte, consulte [Upgrade from Office 2010 servers and client products](plan-upgrade-previous-versions-office.md).

## <a name="what-does-end-of-support-mean"></a>O que *significa o fim do suporte?*

Quase todos os produtos Microsoft têm um ciclo de vida de suporte, durante o qual eles têm novos recursos, correções de bugs e atualizações de segurança. Esse ciclo de vida geralmente dura 10 anos a partir da versão inicial do produto. O final desse ciclo de vida é conhecido como o fim do suporte do produto. Depois que o Project Server 2010 atingir o fim do suporte em 13 de abril de 2021, a Microsoft não fornecerá mais:

- Suporte técnico para problemas que podem ocorrer.

- Correções de bugs para problemas descobertos e que podem afetar a estabilidade e a usabilidade do servidor.

- Correções de segurança para vulnerabilidades descobertas e que podem tornar o servidor vulnerável a violações de segurança.

- Atualizações de fuso horário.

Sua instalação do Project Server 2010 continuará sendo executado após essa data. Porém, devido às alterações listadas anteriormente, recomendamos que você migre do Project Server 2010 assim que possível.

## <a name="what-are-my-options"></a>Quais são minhas opções?

Suas opções de migração são:

- Migrar para o Project Online

- Migrar para uma versão local mais recente do Project Server (preferencialmente Project Server 2019)

Aqui estão os dois caminhos que você pode seguir para evitar o fim do suporte para o Project Server 2010.

![Caminhos de atualização do Project Server 2010](../media/project-server-2010-end-of-support/project-server-2010-end-of-support-timeline.png)

|Por que eu gostaria de migrar para o Project Server 2019?|Por que eu gostaria de migrar para o Project Online?|
|---|---|
|As regras de negócios me restringem a operar meus negócios na nuvem.  <br/><br/>  Preciso de controle de atualizações para meu ambiente.|Tenho usuários móveis ou remotos.<br/><br/>  Os custos para migrar servidores locais são uma preocupação significativa (hardware, software, tempo e esforço para implementar e assim por diante). <br/><br/>  Após a migração, os custos para manter meu ambiente são uma preocupação (por exemplo, atualizações automáticas, tempo de atividade garantido e assim por diante).|

> [!NOTE]
> Para obter mais informações sobre suas opções de migração, consulte Recursos para ajudá-lo a atualizar dos servidores e clientes [do Office 2010.](upgrade-from-office-2010-servers-and-products.md) Observe que o Project Server não dá suporte à configuração híbrida porque o Project Server e o Project Online não podem compartilhar o mesmo pool de recursos.

### <a name="what-are-my-options-for-project-client"></a>Quais são as minhas opções para cliente do Project?

Se você estiver usando o Project Professional 2010 ou o Project Standard 2010, suas opções são:

- Mover para uma versão mais recente do Project Professional ou Project Standard
- Mover para uma solução online, como o Project Online ou o Project para a Web

#### <a name="move-to-a-newer-version-of-project-client"></a>Mover para uma versão mais recente do cliente do Project

Se você estiver migrando do Project Standard 2010, poderá migrar para uma versão mais recente do Project Standard (Project Standard 2016 ou Project Standard 2019). Recomendamos que você vá para a versão mais recente para aproveitar os recursos mais recentes. Migrar para uma versão menos atual (Project Standard 2016) também significa que você precisará migrar novamente mais cedo.

Da mesma forma, se você estiver migrando do Project Professional 2010, poderá migrar para uma versão mais recente (Project Professional 2019 ou Project Professional 2016). Novamente, mova para a versão mais recente, se possível. Se você usar o Project Professional para se conectar ao Project Server, certifique-se de migrar para uma versão do Project Professional que se conecta à versão do Project Server que você usa.

Os usuários do Project Professional 2010 também podem migrar para o cliente da Área de Trabalho do Project Online, que é uma versão baseada em assinatura do Project Professional 2019. Ele está incluído nas assinaturas do Project Plan 3 e do Project Plan 5.

#### <a name="move-to-an-online-solution"></a>Mover para uma solução online

Você também pode migrar do Project Professional 2010 ou do Project Standard 2010 para uma solução online baseada em assinatura do Project. Tanto o Project Plan 3 quanto o Plano 5 incluem o Project Online e a oferta de nuvem mais recente, [o Project para a Web.](https://support.office.com/article/what-can-you-do-with-project-for-the-web-b30f5442-be5f-43d2-9072-c95bff778ea1) Ambos oferecem novos recursos e benefícios que valem a pena explorar.

Para obter mais informações sobre recursos e licenças, consulte [Descrição do serviço do Microsoft Project.](/office365/servicedescriptions/project-online-service-description/project-online-service-description)

## <a name="important-considerations-for-migrating-from-project-server-2010"></a>Considerações importantes para migrar do Project Server 2010

Considere o seguinte quando você planeja migrar do Project Server 2010:

- **Obter ajuda de um provedor de soluções da Microsoft** - Uma atualização do Project Server 2010 pode ser um desafio. Exige muita preparação e planejamento. Pode ser especialmente desafiador se você não foi a pessoa que originalmente definiu o Project Server 2010. Os provedores de soluções da Microsoft estão disponíveis para ajudar, quer você planeje migrar para o Project Server 2019 ou para o Project Online. Procure um provedor de soluções no centro [de provedores de soluções da Microsoft.](https://go.microsoft.com/fwlink/p/?linkid=841249)

- **Planeje suas personalizações** - As personalizações em seu ambiente do Project Server 2010 podem não funcionar quando você migrar para o Project Server 2019 ou o Project Online. Há diferenças significativas na arquitetura do Project Server entre versões. Além disso, os sistemas operacionais, servidores de banco de dados e navegadores da Web necessários que trabalham com as versões diferem. Tenha um plano sobre como testar ou reconstruir suas personalizações no novo ambiente. Aproveite essa oportunidade para determinar se personalizações específicas ainda são necessárias. Para saber mais, confira [Create a plan for current customizations during upgrade to SharePoint 2013](/SharePoint/upgrade-and-update/create-a-plan-for-current-customizations-during-upgrade-to-sharepoint-2013).

- **Tempo e paciência** - O planejamento, a execução e o teste de atualização levarão tempo e esforço consideráveis, especialmente para uma atualização para o Project Server 2019. Se você estiver migrando do Project Server 2010 para o Project Server 2019, primeiro deve migrar para o Project Server 2013, verificar seus dados, depois migrar para o Project Server 2016 e, em seguida, para o Project Server 2019. Talvez você queira verificar com um provedor de soluções da Microsoft por um período de tempo e o custo estimado para que eles possam ajudar.

## <a name="migrate-to-project-online"></a>Migrar para o Project Online

Se você optar por migrar do Project Server 2010 para o Project Online, siga estas etapas para migrar manualmente os dados do plano de projeto:

1. Salve seus planos de projeto do Project Server 2010 para o formato .mpp.

2. Usando o Project Professional 2016, o Project Professional 2019 ou o Cliente de Área de Trabalho do Project Online, abra cada arquivo .mpp e salve e publique-o no Project Online.

Você pode criar manualmente sua configuração do PWA no Project Online (por exemplo, recriar todos os campos personalizados ou calendários corporativos necessários). Os provedores de soluções da Microsoft também podem ajudar nesse processo.

Principais recursos:

|Recurso|Descrição|
|---|---|
|[Introdução ao Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11)|Como configurar e usar o Project Online|
|[Descrição do Serviço do Project Online](/office365/servicedescriptions/project-online-service-description/project-online-service-description)|Informações sobre os diferentes planos do Project Online disponíveis|

## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Migrar para uma versão local mais recente do Project Server

Acreditamos fortemente que você tenha o melhor valor e experiência do usuário migrando para o Project Online. Mas também entendemos que algumas organizações precisam manter os dados do projeto no local. Se você optar por manter seus dados de projeto no local, poderá migrar seu ambiente do Project Server 2010 para o Project Server 2013, o Project Server 2016 ou o Project Server 2019.

Se você não puder migrar para o Project Online, recomendamos migrar para o Project Server 2019. O Project Server 2019 inclui a maioria dos principais recursos em versões anteriores do Project Server. E ele corresponde mais de perto à experiência disponível com o Project Online, embora alguns recursos só estão disponíveis no Project Online.

Depois de concluir cada migração, certifique-se de que seus dados migraram com êxito.

> [!NOTE]
> Se você estiver limitado a uma solução local e considerar apenas migrar para o Project Server 2013, tenha cuidado para que essa versão tenha apenas mais alguns anos de suporte. A data de término do suporte para o Project Server 2013 com Service Pack 2 13 de outubro de 2023. Para obter mais informações sobre datas de fim de suporte, consulte [Política de Ciclo de Vida do Produto da Microsoft](/lifecycle/).

### <a name="how-do-i-migrate-to-project-server-2019"></a>Como migrar para o Project Server 2019?

As diferenças de arquitetura entre o Project Server 2010 e o Project Server 2019 impedem um caminho de migração direta. Portanto, você precisará migrar seus dados do Project Server 2010 para cada versão sucessiva do Project Server até chegar ao Project Server 2019. Etapas para atualizar o Project Server 2010 para o Project Server 2019:

1. Migrar para o Project Server 2013.

2. Migrar do Project Serve 2013 para o Project Server 2016.

3. Migrar do Project Server 2016 para o Project Server 2019.

Depois de concluir cada migração, certifique-se de que seus dados migraram com êxito.

### <a name="step-1-migrate-to-project-server-2013"></a>Etapa 1: Migrar para o Project Server 2013

Para obter informações abrangentes sobre a atualização do Project Server 2010 para o Project Server 2013, consulte [Upgrade to Project Server 2013](/project/upgrade-to-project-server-2016).

Principais recursos:

- [Visão geral do processo de atualização do Project Server 2013](/project/upgrade-to-project-server-2016)

  Obter uma visão geral de alto nível de como atualizar do Project Server 2010 para o Project Server 2013.
- [Planejar a atualização para o Project Server 2013](/project/plan-for-upgrade-to-project-server-2016)

  Veja as considerações de planejamento ao atualizar do Project Server 2010 para o Project Server 2013, incluindo os requisitos do sistema.

- [Novidades na atualização do Project Server 2013](/project/what-s-new-in-project-server-2013-upgrade) abordam alterações importantes para esta versão, incluindo:

   - Não há atualização in-locar para o Project Server 2013. O método de anexação de banco de dados é a única maneira suportada de atualizar do Project Server 2010 para o Project Server 2013.

   - O processo de atualização não apenas converterá seus dados do Project Server 2010 no formato do Project Server 2013, mas também consolidará os quatro bancos de dados do Project Server 2010 em um único banco de dados do Project Web App.

   - Tanto o SharePoint Server 2013 quanto o Project Server 2013 foram alterados para autenticação baseada em declarações da versão anterior. Se você estiver usando a autenticação clássica, você precisará considerar isso ao atualizar. Para saber mais, confira [Migrar da autenticação de modo clássico para a autenticação baseada em declarações SharePoint 2013]( https://docs.microsoft.com/sharepoint/upgrade-and-update/migrate-from-classic-mode-to-claims-based-authentication-in-sharepoint-2013).

Principais recursos:

- [Visão geral do processo de atualização para o Project Server 2013](/project/overview-of-the-project-server-2016-upgrade-process)

- [Atualizar seus bancos de dados e conjuntos de sites do Project Web App (Project Server 2013)](/project/upgrading-to-project-server-2016)

- [Diagrama do processo de atualização do Microsoft Project Server](https://go.microsoft.com/fwlink/p/?linkid=841270)

- [A Grande Consolidação de Banco de Dados, Migração do Project Server 2010 a 2013 em 8 etapas fáceis](https://go.microsoft.com/fwlink/p/?linkid=841271)

### <a name="step-2-migrate-to-project-server-2016"></a>Etapa 2: Migrar para o Project Server 2016

Depois de migrar para o Project Server 2013 e verificar se seus dados migraram com êxito, a próxima etapa é migrar para o Project Server 2016.

Para obter mais informações, [consulte Upgrade to Project Server 2016](/Project/upgrade-to-project-server-2016).

Principais recursos:

- [Visão geral do processo de atualização do Project Server 2016](/Project/overview-of-the-project-server-2016-upgrade-process)

  Entenda o que você precisa fazer para atualizar do Project Server 2013 para o Project Server 2016.

- [Planejar a atualização para o Project Server 2016](/Project/plan-for-upgrade-to-project-server-2016)

  Veja as considerações de planejamento a ser consideradas ao atualizar do Project Server 2013 para o Project Server 2016.

As coisas que você precisa saber sobre a atualização do [Project Server 2016](/project/plan-for-upgrade-to-project-server-2016#thingknow) abordam alterações importantes para atualizar para esta versão, que incluem:

- Ao criar seu ambiente do Project Server 2016, observe que os arquivos de instalação do Project Server 2016 estão incluídos no SharePoint Server 2016. Para obter mais informações, [consulte Deploy Project Server 2016](/project/deploy-project-server-2016).

- Os planos de recursos são preterido no Project Server 2016. Seus planos de recursos do Project Server 2013 serão migrados para Compromissos de Recursos no Project Server 2016 e no Project Online. Consulte [Visão geral: Compromissos de recursos](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) para obter mais informações.

### <a name="step-3-migrate-to-project-server-2019"></a>Etapa 3: Migrar para o Project Server 2019

Depois de migrar para o Project Server 2016 e verificar se seus dados migraram com êxito, a próxima etapa é migrar seus dados para o Project Server 2019.

Para saber o que você precisa fazer para atualizar do Project Server 2016 para o Project Server 2019, consulte [Upgrade to Project Server 2019](/Project/upgrade-to-project-server-2016).

Principais recursos:

- [Visão geral do processo de atualização do Project Server 2019](/project/overview-of-the-project-server-2019-upgrade-process)

  Entenda de alto nível o que você precisa fazer para atualizar do Project Server 2013 para o Project Server 2016.

- [Planejar a atualização para o Project Server 2019](/project/plan-for-upgrade-to-project-server-2019)

  Veja as considerações de planejamento para atualizar do Project Server 2016 para o Project Server 2019.

- [Coisas que você precisa saber sobre a atualização do Project Server 2019](/project/plan-for-upgrade-to-project-server-2016)<br/><br/>Saiba mais sobre alterações importantes para atualizar para esta versão, que incluem:

   - O processo de atualização migrará seus dados do banco de dados do Project Server 2016 para o banco de dados de Conteúdo do SharePoint Server 2019.  O Project Server 2019 não criará mais seu próprio banco de dados do Project Server no farm do SharePoint Server.

   - Após a atualização, esteja ciente de várias alterações no Project Web App.  Para obter detalhes, [consulte Novidades no Project Server 2019](/project/what-s-new-for-it-pros-in-project-server-2019#PWAChanges).

**Outros recursos**:

- [Descrições de serviço do Project Online](/office365/servicedescriptions/project-online-service-description/project-online-service-description): consulte os recursos de gerenciamento de portfólio incluídos no Project Server 2016 e no Project Online Premium.

- [Microsoft Office guia de migração do Project Portfolio Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841279)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Resumo das opções para cliente e servidores do Office 2010 e Windows 7

Para obter um resumo visual das opções de atualização, migração e mover para nuvem para clientes e servidores do Office 2010 e Windows 7, confira o [pôster sobre o fim do suporte](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Fim do suporte para clientes e servidores do Office 2010 e cartaz do Windows 7](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Este cartaz ilustra os vários caminhos que você pode seguir para evitar o fim do suporte para produtos de cliente e servidor do Office 2010 e o Windows 7, com caminhos preferenciais e suporte a opções no Microsoft 365 Enterprise realçadas.

Você também pode [baixar](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) esse cartaz e imprimi-lo em formato de carta, legal ou tablóide (11 x 17).

## <a name="related-topics"></a>Tópicos relacionados

[Atualizando do SharePoint 2010](upgrade-from-sharepoint-2010.md)

[Atualizar de servidores e clientes do Office 2010](upgrade-from-office-2010-servers-and-products.md)