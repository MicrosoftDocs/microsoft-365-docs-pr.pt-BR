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
ms.openlocfilehash: 2cf18c5e91c095c92230a33f1b8a19fa26840777
ms.sourcegitcommit: bcb88a6171f9e7bdb5b2d8c03cd628d11c5e7bbf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/14/2020
ms.locfileid: "48464319"
---
# <a name="project-server-2010-end-of-support-roadmap"></a>Roteiro de encerramento de suporte do Project Server 2010

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

O Project Server 2010 atingirá o fim do suporte em **13 de abril de 2021**. Essa data foi estendida do fim da data de suporte anterior de 13 de outubro de 2020. Se você estiver usando o Project Server 2010 no momento, observe que esses outros produtos relacionados têm as seguintes datas de suporte:

|Produto |Data do fim da suporte|
|---|---|
|Padrão do Project 2010|13 de outubro de 2020|
|Project 2010 Professional|13 de outubro de 2020|

Para obter mais informações sobre os servidores do Office 2010 que atinjam o fim do suporte, consulte [Upgrade from Office 2010 Servers and Client Products](plan-upgrade-previous-versions-office.md).

## <a name="what-does-end-of-support-mean"></a>O que significa o fim do suporte?

O Project Server, como quase todos os produtos da Microsoft, tem um ciclo de vida de suporte durante o qual fornecemos novos recursos, correções de erros e atualizações de segurança. Esse ciclo de vida normalmente dura 10 anos a partir da data da versão inicial do produto, e o final desse ciclo de vida é conhecido como o fim do suporte do produto. Quando o Project Server 2010 atingir o fim do suporte em 13 de abril de 2021, a Microsoft não fornecerá mais:

- Suporte técnico para problemas que podem ocorrer.

- Correções de erros descobertas e que podem afetar a estabilidade e a usabilidade do servidor.

- Correções de segurança para vulnerabilidades descobertas e que podem tornar o servidor vulnerável a brechas de segurança.

- Atualizações de fuso horário.

Sua instalação do Project Server 2010 continuará a ser executada após essa data. No entanto, devido às alterações listadas acima, é altamente recomendável migrar do Project Server 2010 o mais rápido possível.

## <a name="what-are-my-options"></a>Quais são as minhas opções?

Se você estiver usando o Project Server 2010, precisará explorar as opções de migração, que são:

- Migrar para o Project online

- Migre para uma versão local mais recente do Project Server (preferivelmente o Project Server 2019).

Estes são os dois caminhos que você pode executar para evitar o fim do suporte para o Project Server 2010.

![Caminhos de atualização do Project Server 2010](../media/project-server-2010-end-of-support/project-server-2010-end-of-support-timeline.png)

|Por que eu prefiro migrar para o Project Server 2019?|Por que eu prefiro migrar para o Project online?|
|---|---|
|Regras de negócios restringe a operar minha empresa na nuvem.  <br/>  Preciso de controle das atualizações no meu ambiente.|Tenho usuários móveis ou remotos.  <br/>  Os custos para migrar servidores locais são uma grande preocupação (hardware, software, horas e esforço para implementar, etc.).  <br/>  Após a migração, os custos de manutenção do meu ambiente são uma grande preocupação (por exemplo, atualizações automáticas, tempo de atividade garantido, etc.).|

> [!NOTE]
> Para obter mais informações sobre as opções de migração de seus servidores do Office 2010, consulte [recursos para ajudá-lo a atualizar de clientes e servidores do office 2010](upgrade-from-office-2010-servers-and-products.md). Observe que o Project Server não oferece suporte a uma configuração híbrida, já que o Project Server e o Project online não podem compartilhar o mesmo pool de recursos.

### <a name="what-are-my-options-for-project-client"></a>Quais são as opções do Project Client?

Se você estiver usando o Project Professional 2010 ou o Project Standard 2010 e quiser explorar suas opções de migração, você tem a opção de:

- Mover para uma versão mais recente do Project Professional ou do Project Standard.
- Mudar para uma solução online como o Project online ou o Project para a Web.

#### <a name="moving-to-a-newer-version-of-project-client"></a>Movendo para uma versão mais recente do cliente do Project

Se você estiver migrando do Project Standard 2010, poderá migrar para uma versão mais recente do Project Standard (Project Standard 2016 ou Project Standard 2019).  Recomendamos mover para a versão mais recente para aproveitar os recursos e a funcionalidade mais recentes. Além disso, a migração para uma versão menos recente (Project Standard 2016) significa que você precisará migrar dessa versão mais cedo à medida que o final da data de suporte surgir.

Da mesma forma, se você estiver migrando do Project Professional 2010, poderá optar por migrar para uma versão mais recente (Project Professional 2019 ou Project Professional 2016). Recomendamos mover para a versão mais recente, se possível.  Se você estiver usando o Project Professional para se conectar ao Project Server, certifique-se de migrar para uma versão do Project Professional que é compatível com a versão do Project Server que você está usando.

Os usuários do Project Professional 2010 também podem optar por migrar para o cliente da área de trabalho do Project online. É uma versão baseada em assinatura do Project Professional 2019 e está incluída nas assinaturas do plano de projeto 3 e do Project Plan 5.

#### <a name="moving-to-an-online-solution"></a>Movendo para uma solução online

Você também pode optar por migrar do Project Professional 2010 ou do Project Standard 2010 para as soluções online baseadas em assinatura do projeto. O plano de projeto 3 e o plano 5 incluem o Project online e a última oferta de nuvem, [projeto para a Web](https://support.office.com/article/what-can-you-do-with-project-for-the-web-b30f5442-be5f-43d2-9072-c95bff778ea1). Ambas oferecem vários novos recursos e benefícios que vale a pena explorar.

Para obter mais informações sobre os recursos incluídos em ambas, bem como as licenças do plano de projeto incluídas no, consulte a [Descrição do serviço do Microsoft Project](https://docs.microsoft.com/office365/servicedescriptions/project-online-service-description/project-online-service-description).

## <a name="important-considerations-you-need-to-make-when-planning-to-migrate-from-project-server-2010"></a>Considerações importantes que você precisa tomar ao planejar a migração do Project Server 2010

Você precisa considerar o seguinte ao planejar a migração do Project Server 2010:

- **Obter ajuda de um provedor de solução da Microsoft** – a atualização do Project Server 2010 pode ser um desafio e requer muito planejamento e preparação. Pode ser especialmente desafiador se você não fosse o para instalar e configurar o Project Server 2010 originalmente. 2019 no @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ Você pode pesquisar por um provedor de soluções da Microsoft para ajudá-lo com sua migração no [centro de provedores de soluções da Microsoft](https://go.microsoft.com/fwlink/p/?linkid=841249).

- **Planejar suas personalizações** – esteja ciente de que muitas das personalizações que você está trabalhando no seu ambiente do Project Server 2010 podem não funcionar ao migrar para o project Server 2019 ou para o Project online. Há grandes diferenças na arquitetura do Project Server entre as versões, bem como os sistemas operacionais necessários, os servidores de banco de dados e os navegadores da Web do cliente com suporte para trabalhar com a versão mais recente. Tenha um plano em vigor para testar ou reconstruir suas personalizações conforme necessário em seu novo ambiente. O planejamento da atualização também será uma boa oportunidade para verificar se uma personalização específica é realmente necessária à medida que você avança. [Criar um plano para personalizações atuais durante a atualização para o SharePoint 2013]( https://docs.microsoft.com/SharePoint/upgrade-and-update/create-a-plan-for-current-customizations-during-upgrade-to-sharepoint-2013) tem algumas informações gerais excelentes sobre a avaliação e o planejamento de suas personalizações atuais durante a atualização.

- O planejamento, a execução e o teste da atualização de **tempo e paciência** levarão muito tempo e esforço, especialmente se você estiver atualizando para o Project Server 2019. Por exemplo, se você estiver migrando do Project Server 2010 para o Project Server 2019, primeiro será necessário migrar do Project Server 2010 para o Project Server 2013 e, em seguida, verificar seus dados e, em seguida, fazer o mesmo quando migrar para cada versão sucessiva (para o Project Server 2016 e, em seguida, para o Project Server 2019). Você pode querer verificar com um provedor de soluções da Microsoft para comparar seus custos estimados com suas estimativas de quanto tempo levará para eles e em qual custo.

## <a name="migrate-to-project-online"></a>Migrar para o Project online

Se você optar por migrar do Project Server 2010 para o Project online, poderá fazer o seguinte para migrar manualmente os dados do plano de projeto:

1. Salve seus planos de projeto do Project Server 2010 para o. Formato MPP.

2. Usando o Project Professional 2016, o Project Professional 2019 ou o cliente da área de trabalho do Project online, abra cada arquivo. mpp e salve e publique-o no Project online.

Você pode criar manualmente a configuração do PWA no Project online (por exemplo, recrie os campos personalizados ou calendários da empresa necessários). Os Microsoft Solution Providers também podem ajudá-lo com isso.

Principais recursos:

|Recurso|Descrição|
|---|---|
|[Introdução ao Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11)|Como configurar e usar o Project online.|
|[Descrição do Serviço do Project Online](https://go.microsoft.com/fwlink/p/?linkid=829088)|Informações sobre os diferentes planos do Project online que estão disponíveis para você.|

## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Migrar para uma versão local mais recente do Project Server

Embora acreditemos que você possa obter o melhor valor e a experiência do usuário migrando para o Project online, também entendemos que algumas organizações precisam manter os dados do projeto em um ambiente local. Se você optar por manter seus dados de projeto no local, poderá migrar seu ambiente do Project Server 2010 para o Project Server 2013, o Project Server 2016 ou o Project Server 2019.

Recomendamos migrar para o Project Server 2019 se não for possível migrar para o Project online. O Project Server 2019 inclui a maior parte da chave dos recursos e avanços incluídos nas versões anteriores do Project Server e mais se compara à experiência disponível com o Project online (embora alguns recursos estejam disponíveis somente no Project online).

Após concluir cada migração, você deve verificar seus dados para certificar-se de que foram migrados com êxito.

> [!NOTE]
> Se você estiver pensando em migrar somente para o Project Server 2013 se estiver limitado a uma solução local, é importante observar que ela tem apenas mais alguns anos de suporte à esquerda. O Project Server 2013 com Service Pack 2 data de término de suporte é 10/13/2023. Para obter mais informações sobre o fim das datas de suporte, consulte [política de ciclo de vida do produto da Microsoft](https://go.microsoft.com/fwlink/p/?linkid=842066).

### <a name="how-do-i-migrate-to-project-server-2019"></a>Como faço para migrar para o Project Server 2019?

As diferenças arquitetônicas entre o Project Server 2010 e o Project Server 2019 evitam um caminho de migração direta. Isso significa que você precisará migrar os dados do Project Server 2010 para a próxima versão sucessiva do Project Server até atualizar para o Project Server 2019.

Será necessário executar as seguintes etapas para atualizar o Project Server 2010 para o Project Server 2019:

1. Migrar para o Project Server 2013.

2. Migrar do Project serve 2013 para o Project Server 2016.

3. Migre do Project Server 2016 para o Project Server 2019.

Após concluir cada migração, você deve verificar seus dados para certificar-se de que foram migrados com êxito.


### <a name="step-1-migrate-to-project-server-2013"></a>Etapa 1: migrar para o Project Server 2013

Sua primeira etapa na migração dos dados do Project Server 2010 para o Project Server 2019 é primeiro migrar para o Project Server 2013.

Para obter uma compreensão abrangente do que você precisa fazer para atualizar do Project Server 2010 para o Project Server 2013, consulte [upgrade to project server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822).

Principais recursos:

- [Visão geral do processo de atualização do Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822)

  Obtenha uma compreensão de alto nível do que você precisa fazer para atualizar do Project Server 2010 para o Project Server 2013.
- [Planejar a atualização para o Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841823)

  Observe as considerações de planejamento que você precisa fazer ao atualizar do Project Server 2010 para o Project Server 2013, incluindo os requisitos do sistema.

[O que há de novo na atualização do Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841824) mostra algumas alterações importantes para a atualização desta versão, o mais notável:

- Não há nenhuma atualização no local para o Project Server 2013. O método Database-Attach é o único método com suporte para atualização do Project Server 2010 para o Project Server 2013.

- O processo de atualização não só converterá os dados do Project Server 2010 no formato do Project Server 2013, mas também consolidará os quatro bancos de dados do Project Server 2010 em um único banco de dados do Project Web App.

- O SharePoint Server 2013 e o Project Server 2013 foram alterados para a autenticação baseada em declarações da versão anterior. Você precisará fazer considerações ao atualizar se estiver usando a autenticação clássica. Para saber mais, confira [Migrar da autenticação de modo clássico para a autenticação baseada em declarações SharePoint 2013]( https://docs.microsoft.com/sharepoint/upgrade-and-update/migrate-from-classic-mode-to-claims-based-authentication-in-sharepoint-2013).

Principais recursos:

- [Visão geral do processo de atualização para o Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841274)

- [Atualizar seus bancos de dados e conjuntos de sites do Project Web App (Project Server 2013)](https://go.microsoft.com/fwlink/p/?linkid=841272)

- [Diagrama de processo de atualização do Microsoft Project Server](https://go.microsoft.com/fwlink/p/?linkid=841270)

- [A excelente consolidação do banco de dados, o Project Server 2010 para a migração 2013 em 8 etapas simples](https://go.microsoft.com/fwlink/p/?linkid=841271)

### <a name="step-2-migrate-to-project-server-2016"></a>Etapa 2: migrar para o Project Server 2016

Após a migração para o Project Server 2013 e a verificação de que seus dados foram migrados com êxito, a próxima etapa é migrar seus dados para o Project Server 2016.

Para obter uma compreensão abrangente do que você precisa fazer para atualizar do Project Server 2013 para o Project Server 2016, consulte [upgrade to project server 2016](https://docs.microsoft.com/Project/upgrade-to-project-server-2016).

Principais recursos:

- [Visão geral do processo de atualização do Project Server 2016](https://docs.microsoft.com/Project/overview-of-the-project-server-2016-upgrade-process)

  Obtenha uma compreensão de alto nível do que você precisa fazer para atualizar do Project Server 2013 para o Project Server 2016.

- [Planejar a atualização para o Project Server 2016](https://docs.microsoft.com/Project/plan-for-upgrade-to-project-server-2016)

  Observe as considerações de planejamento que você precisa fazer ao atualizar do Project Server 2013 para o Project Server 2016.

As [coisas que você precisa saber sobre a atualização do Project Server 2016](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2016#thingknow) lhe dizem algumas alterações importantes para atualizar para esta versão, que incluem:

- Ao criar seu ambiente do Project Server 2016 para o qual você migrará os dados do Project Server 2013, observe que os arquivos de instalação do Project Server 2016 estão incluídos no SharePoint Server 2016. Para obter mais informações, consulte [Deploy Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841829).

- Os planos de recursos são preteridos no Project Server 2016. Seus planos de recursos do Project Server 2013 serão migrados para os compromissos de recursos no Project Server 2016 e no Project online. Consulte [visão geral: compromissos de recursos](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) para obter mais informações.

### <a name="step-3-migrate-to-project-server-2019"></a>Etapa 3: migrar para o Project Server 2019

Após a migração para o Project Server 2016 e a verificação de que seus dados foram migrados com êxito, a próxima etapa é migrar seus dados para o Project Server 2019.

Para obter uma compreensão abrangente do que você precisa fazer para atualizar do Project Server 2016 para o Project Server 2019, consulte [upgrade to project server 2019](https://docs.microsoft.com/Project/upgrade-to-project-server-2016).

Principais recursos:

- [Visão geral do processo de atualização do Project Server 2019](https://docs.microsoft.com/project/overview-of-the-project-server-2019-upgrade-process)

  Obtenha uma compreensão de alto nível do que você precisa fazer para atualizar do Project Server 2013 para o Project Server 2016.

- [Planejar a atualização para o Project Server 2019](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2019)

  Observe as considerações de planejamento que você precisa fazer ao atualizar do Project Server 2016 para o Project Server 2019.

As [coisas que você precisa saber sobre a atualização do Project Server 2019](https://go.microsoft.com/fwlink/p/?linkid=841827) lhe dizem algumas alterações importantes para atualizar para esta versão, que incluem:

- O processo de atualização migrará seus dados do banco de dados do Project Server 2016 para o banco de dados de conteúdo do SharePoint Server 2019.  O Project Server 2019 não criará mais seu próprio banco de dados do Project Server no farm do SharePoint Server.

- Após a atualização, esteja ciente de várias alterações no Project Web App.  Para obter uma descrição dessas, consulte [What ' s New in Project Server 2019](https://docs.microsoft.com/project/what-s-new-for-it-pros-in-project-server-2019#PWAChanges).

**Outros recursos**:

- [Descrições do serviço do Project online](https://go.microsoft.com/fwlink/p/?linkid=841280): consulte os recursos de gerenciamento de portfólio incluídos no project Server 2016 e no Project Online Premium.

- [Guia de migração do Microsoft Office Project Portfolio Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841279)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Resumo das opções de cliente e servidores do Office 2010 e do Windows 7

Para obter um resumo visual das opções de atualização, migração e mover para nuvem para clientes e servidores do Office 2010 e Windows 7, confira o [pôster sobre o fim do suporte](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Imagem do pôster sobre o fim do suporte para clientes e servidores do Office 2010 e do Windows 7](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Este pôster de uma página é uma maneira rápida de entender os vários caminhos que podem ser tomados para impedir que os produtos de cliente e servidor do Office 2010 e o Windows 7 cheguem ao final do suporte, com destaque para os caminhos preferenciais e o suporte de opções no Microsoft 365 Enterprise.

Você também pode [baixar](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf)esse pôster e imprimir em formatos de carta, oficial ou tablóide (11x17).

## <a name="related-topics"></a>Tópicos relacionados

[Atualizando do SharePoint 2010](upgrade-from-sharepoint-2010.md)

[Atualizar de servidores e clientes do Office 2010](upgrade-from-office-2010-servers-and-products.md)
