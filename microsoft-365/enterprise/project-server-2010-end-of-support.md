---
title: Roteiro de fim do suporte do Project Server 2010
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
description: O suporte para ends para o Project Server 2010 termina em 13 de abril de 2021. Use este artigo como um guia para atualizar para o Project online ou uma versão mais recente do Project Server no local.
ms.openlocfilehash: 239b3d93cfa6a1184ea21225fa97732712b8eb14
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519697"
---
# <a name="project-server-2010-end-of-support-roadmap"></a>Roteiro de encerramento de suporte do Project Server 2010

*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*

O Project Server 2010 atingirá o fim do suporte em **13 de abril de 2021**. Essa data foi estendida a partir da data de fim de suporte anterior de 13 de outubro de 2020. Se você estiver usando o Project Server 2010 no momento, observe que esses produtos relacionados possuem as seguintes datas de fim de suporte:

|Produto |Data do fim da suporte|
|---|---|
|Padrão do Project 2010|13 de outubro de 2020|
|Project 2010 Professional|13 de outubro de 2020|

Para obter mais informações sobre como atingir o fim do suporte, consulte [Upgrade from Office 2010 Servers and Client Products](plan-upgrade-previous-versions-office.md).

## <a name="what-does-end-of-support-mean"></a>O que significa o *fim do suporte* ?

Quase todos os produtos da Microsoft têm um ciclo de vida de suporte, durante o qual eles obtêm novos recursos, correções de erros e atualizações de segurança. Esse ciclo de vida normalmente dura 10 anos da versão inicial do produto. O final desse ciclo de vida é conhecido como o fim do suporte do produto. Depois que o Project Server 2010 atingir o fim do suporte em 13 de abril de 2021, a Microsoft não fornecerá mais:

- Suporte técnico para problemas que podem ocorrer.

- Correções de erros descobertas e que podem afetar a estabilidade e a usabilidade do servidor.

- Correções de segurança para vulnerabilidades descobertas e que podem tornar o servidor vulnerável a brechas de segurança.

- Atualizações de fuso horário.

Sua instalação do Project Server 2010 continuará a ser executada após essa data. Mas, por causa das alterações listadas anteriormente, é altamente recomendável migrar do Project Server 2010 o mais rápido possível.

## <a name="what-are-my-options"></a>Quais são as minhas opções?

Suas opções de migração são:

- Migrar para o Project online

- Migrar para uma versão local mais recente do Project Server (preferivelmente o Project Server 2019)

Estes são os dois caminhos que você pode executar para evitar o fim do suporte para o Project Server 2010.

![Caminhos de atualização do Project Server 2010](../media/project-server-2010-end-of-support/project-server-2010-end-of-support-timeline.png)

|Por que eu prefiro migrar para o Project Server 2019?|Por que eu prefiro migrar para o Project online?|
|---|---|
|Regras de negócios restringe a operar minha empresa na nuvem.  <br/><br/>  Preciso de controle das atualizações no meu ambiente.|Tenho usuários móveis ou remotos.<br/><br/>  Os custos para migrar servidores locais são uma preocupação considerável (hardware, software, tempo e esforço para implementar e assim por diante). <br/><br/>  Após a migração, os custos de manutenção do meu ambiente são uma preocupação (por exemplo, atualizações automáticas, tempo de atividade garantido e assim por diante).|

> [!NOTE]
> Para obter mais informações sobre suas opções de migração, consulte [recursos para ajudá-lo a atualizar de clientes e servidores do Office 2010](upgrade-from-office-2010-servers-and-products.md). Observe que o Project Server não oferece suporte à configuração híbrida porque o Project Server e o Project online não podem compartilhar o mesmo pool de recursos.

### <a name="what-are-my-options-for-project-client"></a>Quais são as opções do Project Client?

Se você estiver usando o Project Professional 2010 ou o Project Standard 2010, suas opções serão:

- Mover para uma versão mais recente do Project Professional ou do Project Standard
- Mover para uma solução online, como o Project online ou o Project para a Web

#### <a name="move-to-a-newer-version-of-project-client"></a>Mover para uma versão mais recente do cliente do Project

Se você estiver migrando do Project Standard 2010, poderá mover para uma versão mais recente do Project Standard (Project Standard 2016 ou Project Standard 2019). Recomendamos que você vá para a versão mais recente para aproveitar os recursos mais recentes. A migração para uma versão menos recente (Project Standard 2016) também significa que você precisará migrar novamente mais cedo.

Da mesma forma, se você estiver migrando do Project Professional 2010, poderá mudar para uma versão mais recente (Project Professional 2019 ou Project Professional 2016). Novamente, mova para a versão mais recente, se possível. Se você usar o Project Professional para se conectar ao Project Server, certifique-se de migrar para uma versão do Project Professional que se conecta à versão do Project Server que você usa.

Os usuários do Project Professional 2010 também podem migrar para o cliente da área de trabalho do Project online, que é uma versão baseada em assinatura do Project Professional 2019. Ele está incluído no plano de projeto 3 e nas assinaturas do Project Plan 5.

#### <a name="move-to-an-online-solution"></a>Mover para uma solução online

Você também pode migrar do Project Professional 2010 ou do Project Standard 2010 para uma solução online baseada na assinatura do projeto. O plano de projeto 3 e o plano 5 incluem o Project online e a última oferta de nuvem, [projeto para a Web](https://support.office.com/article/what-can-you-do-with-project-for-the-web-b30f5442-be5f-43d2-9072-c95bff778ea1). Ambas oferecem novos recursos e benefícios que vale a pena explorar.

Para obter mais informações sobre recursos e licenças, consulte [Descrição do serviço do Microsoft Project](https://docs.microsoft.com/office365/servicedescriptions/project-online-service-description/project-online-service-description).

## <a name="important-considerations-for-migrating-from-project-server-2010"></a>Considerações importantes para a migração do Project Server 2010

Considere o seguinte quando você planeja migrar do Project Server 2010:

- **Obter ajuda de um provedor de soluções da Microsoft** -uma atualização do Project Server 2010 pode ser um desafio. Requer muita preparação e planejamento. Pode ser especialmente desafiador se você não for a pessoa que originalmente configurou o Project Server 2010. Os Microsoft Solution Providers estão disponíveis para ajudar, se você planeja migrar para o Project Server 2019 ou para o Project online. Procure um provedor de soluções no [centro de provedores de soluções da Microsoft](https://go.microsoft.com/fwlink/p/?linkid=841249).

- **Planejar suas personalizações-as** personalizações em seu ambiente do Project Server 2010 podem não funcionar quando você migrar para o project Server 2019 ou o Project online. Há diferenças significativas na arquitetura do Project Server entre as versões. Além disso, os sistemas operacionais, servidores de banco de dados e navegadores da Web necessários que funcionam com as versões são diferentes. Tenha um plano para testar ou reconstruir suas personalizações no novo ambiente. Aproveite esta oportunidade para determinar se as personalizações específicas ainda são necessárias. Para saber mais, confira [Create a plan for current customizations during upgrade to SharePoint 2013](https://docs.microsoft.com/SharePoint/upgrade-and-update/create-a-plan-for-current-customizations-during-upgrade-to-sharepoint-2013).

- O planejamento, a execução e o teste da atualização de **tempo e paciência** levarão muito tempo e esforço, especialmente para uma atualização para o Project Server 2019. Se você estiver migrando do Project Server 2010 para o Project Server 2019, primeiro você deve migrar para o Project Server 2013, verificar seus dados e migrar para o Project Server 2016 e, em seguida, para o Project Server 2019. Convém verificar com um provedor de soluções da Microsoft um período de tempo e o custo estimado para o auxílio.

## <a name="migrate-to-project-online"></a>Migrar para o Project online

Se optar por migrar do Project Server 2010 para o Project online, você pode seguir estas etapas para migrar manualmente os dados do plano de projeto:

1. Salve seus planos de projeto do Project Server 2010 para o formato. mpp.

2. Usando o Project Professional 2016, o Project Professional 2019 ou o cliente da área de trabalho do Project online, abra cada arquivo. mpp e salve e publique-o no Project online.

Você pode criar manualmente a configuração do PWA no Project online (por exemplo, recrie os campos personalizados ou calendários da empresa necessários). Os Microsoft Solution Providers também podem ajudar com esse processo.

Principais recursos:

|Recurso|Descrição|
|---|---|
|[Introdução ao Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11)|Como configurar e usar o Project online|
|[Descrição do Serviço do Project Online](https://go.microsoft.com/fwlink/p/?linkid=829088)|Informações sobre os diferentes planos do Project online disponíveis|

## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Migrar para uma versão local mais recente do Project Server

Acreditamos que você obtém o melhor valor e a experiência do usuário migrando para o Project online. Mas também entendemos algumas organizações necessárias para manter os dados do projeto no local. Se você optar por manter seus dados de projeto no local, poderá migrar seu ambiente do Project Server 2010 para o Project Server 2013, o Project Server 2016 ou o Project Server 2019.

Se você não conseguir migrar para o Project online, recomendamos migrar para o Project Server 2019. O Project Server 2019 inclui a maioria dos recursos principais nas versões anteriores do Project Server. E mais se compara à experiência disponível com o Project online, embora alguns recursos estejam disponíveis somente no Project online.

Após concluir cada migração, certifique-se de que seus dados foram migrados com êxito.

> [!NOTE]
> Se você estiver limitado a uma solução local e estiver tentando apenas migrar para o Project Server 2013, tome cuidado para que essa versão tenha apenas alguns anos de suporte à esquerda. O fim da data de suporte para o Project Server 2013 com Service Pack 2 13 de outubro de 2023. Para obter mais informações sobre datas de fim de suporte, consulte [política de ciclo de vida do produto da Microsoft](https://go.microsoft.com/fwlink/p/?linkid=842066).

### <a name="how-do-i-migrate-to-project-server-2019"></a>Como faço para migrar para o Project Server 2019?

As diferenças arquitetônicas entre o Project Server 2010 e o Project Server 2019 impedem um caminho de migração direta. Portanto, você precisará migrar os dados do Project Server 2010 para cada versão sucessiva do Project Server até alcançar o Project Server 2019. Etapas para atualizar o Project Server 2010 para o Project Server 2019:

1. Migrar para o Project Server 2013.

2. Migrar do Project serve 2013 para o Project Server 2016.

3. Migre do Project Server 2016 para o Project Server 2019.

Após concluir cada migração, certifique-se de que seus dados foram migrados com êxito.

### <a name="step-1-migrate-to-project-server-2013"></a>Etapa 1: migrar para o Project Server 2013

Para obter informações abrangentes sobre a atualização do Project Server 2010 para o Project Server 2013, consulte [upgrade to project server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822).

Principais recursos:

- [Visão geral do processo de atualização do Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822)

  Obtenha uma visão geral de alto nível de como atualizar do Project Server 2010 para o Project Server 2013.
- [Planejar a atualização para o Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841823)

  Veja considerações de planejamento ao atualizar do Project Server 2010 para o Project Server 2013, incluindo os requisitos do sistema.

- [O que há de novo no Project Server 2013 atualização](https://go.microsoft.com/fwlink/p/?linkid=841824) abrange as alterações importantes para esta versão, incluindo:

   - Não há nenhuma atualização in-loco para o Project Server 2013. O método de anexação de banco de dados é a única maneira suportada de atualizar do Project Server 2010 para o Project Server 2013.

   - O processo de atualização não só converterá os dados do Project Server 2010 no formato do Project Server 2013, mas também consolidará os quatro bancos de dados do Project Server 2010 em um único banco de dados do Project Web App.

   - O SharePoint Server 2013 e o Project Server 2013 foram alterados para a autenticação baseada em declarações da versão anterior. Se você estiver usando a autenticação clássica, precisará considerar isso ao atualizar. Para saber mais, confira [Migrar da autenticação de modo clássico para a autenticação baseada em declarações SharePoint 2013]( https://docs.microsoft.com/sharepoint/upgrade-and-update/migrate-from-classic-mode-to-claims-based-authentication-in-sharepoint-2013).

Principais recursos:

- [Visão geral do processo de atualização para o Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841274)

- [Atualizar seus bancos de dados e conjuntos de sites do Project Web App (Project Server 2013)](https://go.microsoft.com/fwlink/p/?linkid=841272)

- [Diagrama de processo de atualização do Microsoft Project Server](https://go.microsoft.com/fwlink/p/?linkid=841270)

- [A excelente consolidação do banco de dados, o Project Server 2010 para a migração 2013 em 8 etapas simples](https://go.microsoft.com/fwlink/p/?linkid=841271)

### <a name="step-2-migrate-to-project-server-2016"></a>Etapa 2: migrar para o Project Server 2016

Depois de mover para o Project Server 2013 e verificar se seus dados foram migrados com êxito, a próxima etapa é migrar para o Project Server 2016.

Para obter mais informações, consulte [upgrade to Project Server 2016](https://docs.microsoft.com/Project/upgrade-to-project-server-2016).

Principais recursos:

- [Visão geral do processo de atualização do Project Server 2016](https://docs.microsoft.com/Project/overview-of-the-project-server-2016-upgrade-process)

  Compreenda o que você precisa fazer para atualizar do Project Server 2013 para o Project Server 2016.

- [Planejar a atualização para o Project Server 2016](https://docs.microsoft.com/Project/plan-for-upgrade-to-project-server-2016)

  Observe as considerações de planejamento a fazer ao atualizar do Project Server 2013 para o Project Server 2016.

As [coisas que você precisa saber sobre a atualização do Project Server 2016](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2016#thingknow) abrangem alterações importantes para atualizar para esta versão, que incluem:

- Ao criar seu ambiente do Project Server 2016, observe que os arquivos de instalação do Project Server 2016 estão incluídos no SharePoint Server 2016. Para obter mais informações, consulte [Deploy Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841829).

- Os planos de recursos são preteridos no Project Server 2016. Seus planos de recursos do Project Server 2013 serão migrados para os compromissos de recursos no Project Server 2016 e no Project online. Consulte [visão geral: compromissos de recursos](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) para obter mais informações.

### <a name="step-3-migrate-to-project-server-2019"></a>Etapa 3: migrar para o Project Server 2019

Após migrar para o Project Server 2016 e verificar se seus dados foram migrados com êxito, a próxima etapa é migrar seus dados para o Project Server 2019.

Para saber o que você precisa fazer para atualizar do Project Server 2016 para o Project Server 2019, consulte [upgrade to project server 2019](https://docs.microsoft.com/Project/upgrade-to-project-server-2016).

Principais recursos:

- [Visão geral do processo de atualização do Project Server 2019](https://docs.microsoft.com/project/overview-of-the-project-server-2019-upgrade-process)

  Obtenha uma compreensão de alto nível do que você precisa fazer para atualizar do Project Server 2013 para o Project Server 2016.

- [Planejar a atualização para o Project Server 2019](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2019)

  Veja as considerações de planejamento para atualização do Project Server 2016 para o Project Server 2019.

- [Coisas que você precisa saber sobre a atualização do Project Server 2019](https://go.microsoft.com/fwlink/p/?linkid=841827)<br/><br/>Saiba mais sobre as alterações importantes para atualizar para esta versão, que incluem:

   - O processo de atualização migrará seus dados do banco de dados do Project Server 2016 para o banco de dados de conteúdo do SharePoint Server 2019.  O Project Server 2019 não criará mais seu próprio banco de dados do Project Server no farm do SharePoint Server.

   - Após a atualização, esteja ciente de várias alterações no Project Web App.  Para obter detalhes, consulte [What ' s New in Project Server 2019](https://docs.microsoft.com/project/what-s-new-for-it-pros-in-project-server-2019#PWAChanges).

**Outros recursos**:

- [Descrições do serviço do Project online](https://go.microsoft.com/fwlink/p/?linkid=841280): consulte os recursos de gerenciamento de portfólio incluídos no project Server 2016 e no Project Online Premium.

- [Guia de migração do Microsoft Office Project Portfolio Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841279)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Resumo das opções de cliente e servidores do Office 2010 e do Windows 7

Para obter um resumo visual das opções de atualização, migração e mover para nuvem para clientes e servidores do Office 2010 e Windows 7, confira o [pôster sobre o fim do suporte](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Fim do suporte para clientes e servidores do Office 2010 e pôster do Windows 7](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Este cartaz ilustra os vários caminhos que você pode executar para evitar o fim do suporte para os produtos de servidor e cliente do Office 2010 e o Windows 7, com caminhos preferidos e suporte a opções no Microsoft 365 Enterprise realçado.

Você também pode [baixar](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) este cartaz e imprimi-lo no formato carta, legal ou tablóide (11 x 17).

## <a name="related-topics"></a>Tópicos relacionados

[Atualizando do SharePoint 2010](upgrade-from-sharepoint-2010.md)

[Atualizar de servidores e clientes do Office 2010](upgrade-from-office-2010-servers-and-products.md)
