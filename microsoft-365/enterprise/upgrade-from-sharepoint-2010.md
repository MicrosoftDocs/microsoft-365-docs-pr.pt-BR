---
title: Atualizando do SharePoint 2010
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 04/13/2020
audience: ITPro
ms.topic: conceptual
ms.prod: office-online-server
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- WSU140
- OSU140
ms.assetid: 985a357f-6db7-401f-bf7a-1bafdf1f312c
f1.keywords:
- NOCSH
description: Encontre informações e recursos para atualizar do SharePoint 2010 e sharepoint Server 2010. O suporte para ambos termina em 13 de abril de 2021.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fba095a15164f8a09ce1e0a1cbd5ee9cd298aa74
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519758"
---
# <a name="upgrading-from-sharepoint-2010"></a>Atualizando do SharePoint 2010

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

O Microsoft SharePoint 2010 e o SharePoint Server 2010 chegarão ao fim do suporte em 13 de abril de **2021.** Este artigo fornece recursos para ajudá-lo a migrar seus dados existentes do SharePoint Server 2010 para o SharePoint Online no Microsoft 365 ou atualizar seu ambiente local do SharePoint Server 2010.

## <a name="what-is-end-of-support"></a>O que *é o fim do suporte?*

A maioria dos produtos da Microsoft tem um ciclo de vida de suporte, durante o qual eles têm novos recursos, correções de bugs, correções de segurança e assim por diante. Após a data de fim do suporte, o produto não para de funcionar, mas a Microsoft não fornece mais:

- Suporte técnico para problemas que podem ocorrer.

- Correções de bugs para problemas que podem afetar a estabilidade e a usabilidade do servidor.

- Correções de segurança para vulnerabilidades que podem tornar o servidor vulnerável a violações de segurança.

- Atualizações de fuso horário.

Isso significa que não haverá mais atualizações, patches ou correções para o produto (incluindo correções/correções de segurança). O Suporte da Microsoft terá deslocado totalmente seus esforços de suporte para versões mais recentes.

Conforme o fim do suporte do SharePoint Server 2010 se aproxima, exclua os dados de que você não precisa mais antes de atualizar o produto e migrar seus dados importantes.

> [!NOTE]
> Um ciclo de vida de software geralmente dura dez anos a partir do lançamento inicial. [Os provedores de soluções](https://go.microsoft.com/fwlink/?linkid=841249) da Microsoft podem ajudá-lo a atualizar para a próxima versão do software ou migrar para a migração do Microsoft 365 (ou ambos). Certifique-se de que também conhece as datas de fim do suporte para tecnologias subjacentes críticas, especialmente para a versão do Microsoft SQL Server que você está usando com o SharePoint. Para obter mais informações, consulte Política [de Ciclo de Vida Fixa.](https://support.microsoft.com/help/14085)

## <a name="plan-ahead"></a>Planejar com antecedência

Verifique as datas em que o suporte termina no [site ciclo de vida do produto.](https://support.microsoft.com/lifecycle/search?alpha=SharePoint%20Server%202010) Planeje suas atualizações ou migrações com essas datas em mente. Lembre-se de que *seu produto não para de funcionar* na data listada. Porém, como sua instalação não será mais corrigida após essa data, você vai querer planejar uma transição suave para a próxima versão do produto.

Essa matriz ajuda a plotar um curso entre as opções de migração:

|Produto de fim do suporte|Good |Melhor|
|---|---|---|
|SharePoint Server 2010|SharePoint Server 2013 (local)|SharePoint Online|
||SharePoint Server 2013 híbrido com SharePoint Online|SharePoint Server 2016 (local)|
|||Pesquisa Híbrida na Nuvem do SharePoint|

Se você escolher uma opção na extremidade baixa da escala (boa), você precisará começar a planejar outra atualização logo após a migração do SharePoint Server 2010.

Aqui estão os três caminhos que você pode seguir para evitar o fim do suporte para o SharePoint Server 2010.

![Caminhos de atualização do SharePoint Server 2010](../media/upgrade-from-sharepoint-2010/upgrade-from-sharepoint-2010-paths.png)

> [!NOTE]
> O fim do suporte para o SharePoint Server 2010 e o SharePoint Foundation 2010 está agendado para 13 de abril de 2021. Mas certifique-se de verificar o [site do Ciclo de Vida do](https://support.microsoft.com/lifecycle) Produto para as datas mais atuais.

## <a name="whats-next"></a>O que vem a seguir?

O SharePoint Server 2013 e o SharePoint Foundation 2013 podem ser instalados no local em seus próprios servidores. Ou você pode usar o SharePoint Online, que é um serviço online que faz parte do Microsoft 365. Você pode optar por:

- Migrar para o SharePoint Online.

- Atualize o SharePoint Server ou o SharePoint Foundation local.

- Faça as duas coisas acima.

- Implementar uma solução [híbrida do SharePoint.](https://docs.microsoft.com/sharepoint/hybrid/hybrid)

Considere os custos ocultos de manutenção de um farm de servidores, incluindo manutenção ou migração de personalizações e atualização de hardware. Se você tiver contabilizou esses fatores, será mais fácil atualizar no local. Se você executar seu farm em Servidores Do SharePoint herdados sem personalização pesada, poderá se beneficiar de uma migração planejada para o SharePoint Online. Para um ambiente local do SharePoint Server, você também pode considerar mover alguns dados no SharePoint Online para reduzir a sobrecarga de gerenciamento de hardware.

> [!NOTE]
> Os administradores do SharePoint podem criar uma Assinatura do Microsoft 365, configurar novos sites do SharePoint Online e, em seguida, recortar do SharePoint Server 2010 corretamente, levando apenas documentos essenciais para os sites atualizados. Em seguida, quaisquer dados restantes podem ser esvaziados do site do SharePoint Server 2010 para arquivos locais.

|SharePoint Online|SharePoint Server local|
|---|---|
|Alto custo no tempo (plano/execução/verificação)|Alto custo no tempo (plano/execução/verificação)|
|Menor custo em fundos (sem compras de hardware)|Custo mais alto em fundos (compras de hardware)|
|Custo único na migração|Custo único repetido por migração futura|
|Baixo custo total de propriedade/manutenção|Alto custo total de propriedade/manutenção|

Uma mudança única para o Microsoft 365 terá um custo mais alto enquanto você organiza os dados e decide o que levar para a nuvem e o que deixar para trás. Mas depois que seus dados são migrados, futuras atualizações serão automáticas, pois você não precisará mais gerenciar atualizações de hardware e software. E o tempo de adoção do seu farm será respaldado por um contrato de nível de [serviço (SLA) da Microsoft.](https://go.microsoft.com/fwlink/?linkid=843153)

### <a name="migrate-to-sharepoint-online"></a>Migrar para o SharePoint Online

Certifique-se de que o SharePoint Online ofereça todos os recursos necessários. Confira a [descrição do serviço do SharePoint.](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-service-description)

Não é possível migrar diretamente do SharePoint Server 2010 (ou do SharePoint Foundation 2010) para o SharePoint Online. Muito do trabalho de migração é manual. Mas esse estágio oferece a oportunidade de remoção de dados e sites que não são mais necessários antes da mudança. Você pode arquivar outros dados no armazenamento. 

Lembre-se de que o SharePoint Server 2010 e o SharePoint Foundation 2010 não param de funcionar no fim do suporte. Portanto, os administradores podem ter um período em que o SharePoint ainda está em execução se seus clientes se esquecerem de mover alguns de seus dados.

Se você atualizar para o SharePoint Server 2013 ou o SharePoint Server 2016 e decidir colocar dados no SharePoint Online, poderá usar a API de Migração do [SharePoint](https://support.office.com/article/Upload-on-premises-content-to-SharePoint-Online-using-PowerShell-cmdlets-555049c6-15ef-45a6-9a1f-a1ef673b867c?ui=en-US&amp;rs=en-US&amp;ad=US) para migrar informações para o OneDrive for Business.

|Vantagem do SharePoint Online|Desvantagem do SharePoint Online|
|---|---|
|A Microsoft fornece hardware SPO e toda a administração de hardware.|Os recursos disponíveis podem diferir entre o SharePoint Server local e o SPO.|
|Você é o administrador global da sua assinatura e pode atribuir administradores a sites SPO.|Algumas ações disponíveis para um administrador de farm no SharePoint Server local não existem (ou não são necessárias) na função de Administrador do SharePoint no Microsoft 365. Mas a Administração do SharePoint, a Administração do Conjunto de Sites e a Propriedade do Site são locais para sua organização.|
|A Microsoft aplica patches, correções e atualizações a hardware e software subjacentes, incluindo servidores SQL nos quais o SharePoint Online é executado.|Como não há acesso ao sistema de arquivos subjacente no serviço, a personalização é limitada.|
|A Microsoft [publica contratos de nível de serviço](https://go.microsoft.com/fwlink/?linkid=843153) e se move rapidamente para resolver incidentes de nível de serviço.|O backup e a restauração e outras opções de recuperação são automatizados pelo serviço no SharePoint Online. Os backups serão substituídos se não usados.|
|Os testes de segurança e o ajuste de desempenho do servidor são executados continuamente no serviço pela Microsoft.|As alterações feitas na interface do usuário e em outros recursos do SharePoint são instaladas pelo serviço e talvez precisem ser 100%2 ou 5.000.|
|O Microsoft 365 atende a vários padrões do setor: [ofertas de conformidade da Microsoft.](https://go.microsoft.com/fwlink/?linkid=843165)|[A assistência do FastTrack](https://go.microsoft.com/fwlink/?linkid=518597) para migração é limitada.  <br/> Grande parte da atualização será manual ou por meio da API de Migração do SPO descrita no Mapa de Conteúdo de Migração do SharePoint Online e do [OneDrive.](https://go.microsoft.com/fwlink/?linkid=843184)|
|Os engenheiros de Suporte da Microsoft e os funcionários do datacenter não têm acesso irrestrito de administrador à sua assinatura.|Pode haver custos adicionais se a infraestrutura de hardware precisar ser atualizada para dar suporte à versão mais recente do SharePoint ou se um farm secundário for necessário para a atualização.|
|Os provedores de soluções podem ajudar com o trabalho único de migrar seus dados para o SharePoint Online.|Nem todas as alterações no SharePoint Online estão dentro de seu controle. Após a migração, as diferenças de design em menus, bibliotecas e outros recursos podem afetar temporariamente a usabilidade.|
|Os produtos online são atualizados automaticamente em todo o serviço. Os recursos podem ser preterdos, mas não há um final verdadeiro do ciclo de vida de suporte.|Há um ciclo de vida de fim de suporte para o SharePoint Server ou o SharePoint Foundation, bem como para servidores SQL subjacentes.|

Se você decidiu criar um novo site do Microsoft 365 e migrará manualmente os dados para ele conforme necessário, verifique as opções [do Microsoft 365.](https://www.microsoft.com/microsoft-365/)

### <a name="upgrade-sharepoint-server-on-premises"></a>Atualizar o SharePoint Server local

A partir do SharePoint Server 2019, as atualizações devem ser *em série.* Não é possível atualizar do SharePoint Server 2010 para o SharePoint Server 2016 ou para o SharePoint 2019 diretamente. Caminho de atualização em série:

- SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016

Levará tempo e planejar seguir todo o caminho do SharePoint 2010 para o SharePoint Server 2016. As atualizações envolvem custos de hardware (os servidores SQL também devem ser atualizados), software e administração. Além disso, as personalizações podem precisar ser atualizadas ou até mesmo abandonadas. Certifique-se de documentar as personalizações críticas antes de atualizar o farm do SharePoint Server.

> [!NOTE]
> É possível manter seu farm de fim de suporte do SharePoint 2010, instalar um farm do SharePoint Server 2016 em um novo hardware (para que os farms separados executem lado a lado) e, em seguida, planejar e executar uma migração manual de conteúdo (para baixar e carregar conteúdo, por exemplo). Mas há possíveis armadilhas para essas movimentações manuais, como documentos provenientes de 2010 que têm uma conta da última modificação atual com o alias da conta que faz a movimentação manual. E algum trabalho deve ser feito com antecedência, como recriar sites, subsites, permissões e estruturas de lista. Certifique-se de limpar seu ambiente antes da atualização. Considere quais dados você pode mover para o armazenamento ou não precisa mais. Isso pode reduzir o impacto da migração. Você deve ter certeza de que seu farm existente está funcionando antes de atualizar e (certamente) antes de descomissioná-lo!

Lembre-se de revisar os caminhos de atualização com e *sem suporte:*

- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)

- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)

Se você tiver *personalizações,* é fundamental planejar cada etapa no caminho de migração:

- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)

- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)

|Vantagem local|Desvantagem local|
|---|---|
|Controle total de todos os aspectos do farm do SharePoint (e seu SQL) do hardware do servidor para cima.|Todas as quebras e correções são de responsabilidade da sua empresa. Mas você pode envolver o Suporte pago da Microsoft se seu produto não tiver passado do fim do suporte.|
|Conjunto completo de recursos do SharePoint Server local com a opção de conectar seu farm local a uma assinatura do SharePoint Online via híbrido.|Atualização, patches, correções de segurança, atualizações de hardware e toda a manutenção do SharePoint Server e seu farm SQL são gerenciados no local.|
|Acesso total para mais opções de personalização do que com o SharePoint Online.|[As ofertas de conformidade](https://go.microsoft.com/fwlink/?linkid=843165) da Microsoft devem ser configuradas manualmente no local.|
|Os testes de segurança e o ajuste de desempenho do servidor são executados no local sob seu controle.|O Microsoft 365 pode disponibilizar recursos para o SharePoint Online que não interoperam com o SharePoint Server local.|
|Os provedores de soluções podem ajudar a migrar dados para a próxima versão do SharePoint Server (e além).|Seus sites do SharePoint Server não usarão automaticamente [certificados SSL/TLS,](https://go.microsoft.com/fwlink/?linkid=843167) como visto no SharePoint Online.|
|Controle total das convenções de nomen por nomeação e backup e restauração e outras opções de recuperação no SharePoint Server local.|O SharePoint Server local é sensível aos ciclos de vida do produto.|

### <a name="upgrade-resources"></a>Recursos de atualização

Comece comparando os requisitos de hardware e software. Se o seu ambiente atual não atender aos requisitos básicos, talvez seja necessário atualizar o hardware no farm ou nos servidores SQL primeiro. 

Você pode decidir mover alguns de seus sites para o hardware "evergreen" do SharePoint Online. Depois de fazer a avaliação, siga os métodos e caminhos de atualização com suporte.

- *Requisitos de hardware/software para:*

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)

- *Limites de software para:*

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)

- *A visão geral do processo de atualização para:*

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)

### <a name="create-a-hybrid-solution-with-sharepoint-online-and-sharepoint-server-on-premises"></a>Criar uma solução híbrida com o SharePoint Online e o SharePoint Server local

Uma configuração híbrida oferece o melhor local e online para algumas necessidades de migração. Você pode conectar farms do SharePoint Server 2013, 2016 ou 2019 ao SharePoint Online para criar um híbrido do SharePoint: saiba mais sobre soluções híbridas do [SharePoint.](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)

Se um farm híbrido do SharePoint Server for sua meta de migração, descubra quais sites e usuários mover online e quais precisam permanecer no local. Classificar o conteúdo do farm do SharePoint Server como alto, médio ou baixo impacto para sua empresa pode ajudar nessa decisão. Talvez seja necessário apenas compartilhar contas de usuário para logon e o índice de pesquisa do SharePoint Server com o SharePoint Online. Mas esse fator pode não ser claro até que você veja como seus sites são usados. Se posteriormente sua empresa decidir migrar todo o conteúdo para o SharePoint Online, você poderá mover todas as contas e dados restantes online e descomissionar seu farm local. O gerenciamento/administração do farm do SharePoint será feito por meio dos consoles do Microsoft 365 desse ponto em diante.

Familiarize-se com os tipos de híbridos existentes e como configurar a conexão entre seu farm do SharePoint local e sua assinatura do Microsoft 365.

|Opção|Descrição|
|---|---|
|[Ofertas de conformidade da Microsoft.](https://go.microsoft.com/fwlink/?linkid=843165)|[A assistência do FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) para migração é limitada.<br/><br/> Grande parte da atualização será manual ou por meio da API de Migração do SPO descrita no Mapa de Conteúdo de Migração do SharePoint Online e do [OneDrive.](https://go.microsoft.com/fwlink/?linkid=843184)|
|Os engenheiros de Suporte da Microsoft e os funcionários do datacenter não têm acesso irrestrito de administrador à sua assinatura.|Pode haver custos adicionais se a infraestrutura de hardware precisar ser atualizada para dar suporte à versão mais recente do SharePoint ou se um farm secundário for necessário.|
|Os parceiros podem ajudar no trabalho único de migrar seus dados para o SharePoint Online.||
|Os produtos online são atualizados automaticamente em todo o serviço. Os recursos podem ser preterdos, mas não há um fim de suporte verdadeiro.||

Se você decidiu criar um novo site do Microsoft 365 e migrar manualmente os dados para ele conforme necessário, verifique as opções [do Microsoft 365.](https://www.microsoft.com/microsoft-365/)

### <a name="upgrade-sharepoint-server-on-premises"></a>Atualizar o SharePoint Server local

Não é possível ignorar versões em Atualizações do SharePoint. Isso significa que as atualizações são em série:

- SharePoint 2007 \> SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016

Para tomar todo o caminho do SharePoint 2007 para o SharePoint Server 2016 significará um investimento significativo de tempo e envolverá hardware (os servidores SQL também devem ser atualizados), software e custos de administração. As personalizações precisarão ser atualizadas ou abandonadas, de acordo com a criticidade do recurso.

> [!NOTE]
> É possível manter seu farm de fim de vida do SharePoint 2007, instalar um farm do SharePoint Server 2016 em um novo hardware (para que os farms separados executem lado a lado) e, em seguida, planejar e executar uma migração manual de conteúdo (para baixar e carregar conteúdo, por exemplo). Mas há algumas desvantagens nessas movimentações manuais, como movimentações de documentos substituindo a última conta modificada pelo alias da conta que faz a movimentação manual. E muito trabalho deve ser feito com antecedência, como recriar sites, subsites, permissões e estruturas de lista. De qualquer forma, considere quais dados você pode mover para o armazenamento ou não precisa mais reduzir o impacto da migração.

Certifique-se de limpar seu ambiente antes da atualização. Você deve ter certeza de que seu farm existente está funcionando antes de atualizar e, certamente, antes de descomissioná-lo!

Lembre-se de revisar os caminhos de atualização com e *sem suporte:*

- 
  [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843156)

- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)

- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)

Se você tiver *personalizações,* é fundamental planejar sua atualização para cada etapa no caminho de migração:

- [SharePoint 2007](https://go.microsoft.com/fwlink/?linkid=843158)

- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)

- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)

|Profissional local|Contra no local|
|---|---|
|Controle total de todos os aspectos do farm do SharePoint, do hardware do servidor para cima.|Todas as quebras e correções são de responsabilidade da sua empresa. (Mas você pode envolver o Suporte pago da Microsoft se seu produto não tiver passado do fim do suporte.)|
|Conjunto completo de recursos do SharePoint Server local com a opção de conectar seu farm local a uma assinatura do SharePoint Online via híbrido.|Atualização, patches, correções de segurança e toda a manutenção do SharePoint Server gerenciada no local.|
|Acesso total para maior personalização.|[As ofertas de conformidade](https://go.microsoft.com/fwlink/?linkid=843165) da Microsoft devem ser configuradas manualmente no local.|
|O teste de segurança e o ajuste de desempenho do servidor são executados no local sob seu controle.|O Microsoft 365 pode disponibilizar recursos para o SharePoint Online que não interoperam com o SharePoint Server local.|
|Os parceiros podem ajudar a migrar dados para a próxima versão do SharePoint Server (e além).|Seus sites do SharePoint Server não usarão automaticamente [certificados SSL/TLS,](https://go.microsoft.com/fwlink/?linkid=843167) como visto no SharePoint Online.|
|Controle total das convenções de nomen por nomeação e backup e restauração e outras opções de recuperação no SharePoint Server local.|O SharePoint Server local é sensível aos ciclos de vida do produto.|

### <a name="upgrade-resources"></a>Recursos de atualização

Comece sabendo que você está de acordo com os requisitos de hardware e software e, em seguida, siga os métodos de atualização com suporte.

- *Requisitos de hardware/software para:*

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)

- *Limites de software para:*

    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843245)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)

- *A visão geral do processo de atualização para:*

    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843250)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)

### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Criar uma solução híbrida do SharePoint entre o SharePoint Online e o local

Se a resposta às suas necessidades de migração estiver entre o controle oferecido no local e o menor custo de propriedade oferecido pelo SharePoint Online, você poderá conectar farms do SharePoint Server 2013 ou 2016 ao SharePoint Online por meio de híbridos. [Saiba mais sobre as soluções híbridas do SharePoint](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)

Se você decidir que um farm híbrido do SharePoint Server beneficiará seus negócios, familiarize-se com os tipos de híbridos existentes e como configurar a conexão entre seu farm do SharePoint local e sua assinatura do Microsoft 365.

Talvez você queira criar um ambiente de dev/teste do Microsoft 365, que você pode configurar com guias [de laboratório de teste.](m365-enterprise-test-lab-guides.md) Depois de obter uma assinatura do Microsoft 365 de avaliação ou adquirida, você pode criar os conjunto de sites, webs e bibliotecas de documentos no SharePoint Online para o qual você pode migrar dados. Você pode migrar manualmente, por meio da API de Migração, ou, se quiser migrar o conteúdo de Meu Site para o OneDrive for Business, por meio do assistente híbrido.

> [!NOTE]
> Para usar a opção híbrida, seu farm do SharePoint Server 2010 deve primeiro ser atualizado localmente para o SharePoint Server 2013 ou 2016. O SharePoint Foundation 2010 e o SharePoint Foundation 2013 não suportam conexões híbridas com o SharePoint Online.

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Resumo das opções para cliente e servidores do Office 2010 e Windows 7

Para obter um resumo visual das opções de atualização, migração e mover para nuvem para clientes e servidores do Office 2010 e Windows 7, confira o [pôster sobre o fim do suporte](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Fim do suporte para clientes e servidores do Office 2010 e cartaz do Windows 7](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Este cartaz ilustra os vários caminhos que você pode seguir para evitar o fim do suporte aos produtos de cliente e servidor do Office 2010 e do Windows 7, com opções e caminhos preferenciais com suporte no Microsoft 365 Enterprise realçada.

Você também pode [baixar esse](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) cartaz e imprimi-lo em formato de carta, oficial ou tabloide (11 x 17).

## <a name="related-articles"></a>Artigos relacionados

[Recursos para ajudá-lo a atualizar de servidores e clientes do Office 2007 ou 2010](upgrade-from-office-2010-servers-and-products.md)

[Overview of the upgrade process from SharePoint 2010 to SharePoint 2013](https://technet.microsoft.com/library/mt493301%28v=office.16%29.aspx)

[Práticas recomendadas para atualização do SharePoint 2010 para o SharePoint 2013](https://technet.microsoft.com/library/mt493305%28v=office.16%29.aspx)

[Resolver problemas de atualização do banco de dados no SharePoint 2013](https://go.microsoft.com/fwlink/?linkid=843195)

[Pesquise provedores de soluções da Microsoft para ajudar na atualização](https://go.microsoft.com/fwlink/?linkid=841249)

[Política atualizada de manutenção do produto para SharePoint Server 2013](https://technet.microsoft.com/library/mt493253%28v=office.16%29.aspx)

[Política atualizada de manutenção do produto para SharePoint Server 2016](https://technet.microsoft.com/library/mt782882%28v=office.16%29.aspx)
