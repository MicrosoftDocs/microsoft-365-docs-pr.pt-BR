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
description: Encontre informações e recursos para atualizar do SharePoint 2010 e do SharePoint Server 2010. Suporte para ambas as extremidades de 13 de abril de 2021.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fba095a15164f8a09ce1e0a1cbd5ee9cd298aa74
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519758"
---
# <a name="upgrading-from-sharepoint-2010"></a>Atualizando do SharePoint 2010

*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*

O Microsoft SharePoint 2010 e o SharePoint Server 2010 atingirão o fim do suporte em **13 de abril de 2021**. Este artigo fornece recursos para ajudá-lo a migrar seus dados existentes do SharePoint Server 2010 para o SharePoint Online no Microsoft 365 ou atualizar seu ambiente local do SharePoint Server 2010.

## <a name="what-is-end-of-support"></a>O que é o *fim do suporte*?

A maioria dos produtos da Microsoft tem um ciclo de vida de suporte, durante o qual eles obtêm novos recursos, correções de erros, correções de segurança e assim por diante. Após a data de término do suporte, o produto não deixa de funcionar, mas a Microsoft não fornece mais:

- Suporte técnico para problemas que podem ocorrer.

- Correções de erros que podem afetar a estabilidade e a usabilidade do servidor.

- Correções de segurança para vulnerabilidades que podem tornar o servidor vulnerável a brechas de segurança.

- Atualizações de fuso horário.

Isso significa que não haverá mais atualizações, patches ou correções para o produto (incluindo patches/correções de segurança). O suporte da Microsoft terá deslocado completamente seus esforços de suporte para versões mais recentes.

Como o fim do suporte das abordagens do SharePoint Server 2010, exclua os dados que não são mais necessários antes de atualizar o produto e migrar seus dados importantes.

> [!NOTE]
> Um ciclo de vida de software normalmente dura dez anos da versão inicial. Os [Microsoft Solution Providers](https://go.microsoft.com/fwlink/?linkid=841249) podem ajudá-lo a atualizar para a próxima versão do software ou migrar para a migração do Microsoft 365 (ou ambos). Certifique-se de que você está ciente das datas de fim de suporte para tecnologias básicas fundamentais também, particularmente para a versão do Microsoft SQL Server que você está usando com o SharePoint. Para obter mais informações, consulte [política de ciclo de vida fixo](https://support.microsoft.com/help/14085).

## <a name="plan-ahead"></a>Planejar para o futuro

Verifique as datas em que o suporte termina no [site do ciclo de vida do produto](https://support.microsoft.com/lifecycle/search?alpha=SharePoint%20Server%202010). Planeje suas atualizações ou migrações com essas datas em mente. Lembre-se de que seu produto *não vai parar de funcionar* na data listada. No entanto, como a instalação não será mais corrigida após essa data, você deverá planejar uma transição suave para a próxima versão do produto.

Esta matriz ajuda a plotar um curso entre as opções de migração:

|Produto do fim do suporte|Good |Melhor|
|---|---|---|
|SharePoint Server 2010|SharePoint Server 2013 (local)|SharePoint Online|
||SharePoint Server 2013 híbrido com o SharePoint Online|SharePoint Server 2016 (local)|
|||Pesquisa híbrida do SharePoint Cloud|

Se você escolher uma opção no final da escala (bom), será necessário começar a planejar outra atualização logo após a migração do SharePoint Server 2010.

Estes são os três caminhos que você pode seguir para evitar o fim do suporte para o SharePoint Server 2010.

![Caminhos de atualização do SharePoint Server 2010](../media/upgrade-from-sharepoint-2010/upgrade-from-sharepoint-2010-paths.png)

> [!NOTE]
> O fim do suporte para o SharePoint Server 2010 e o SharePoint Foundation 2010 está agendado para 13 de abril de 2021. Mas certifique-se de verificar o [site de ciclo de vida do produto](https://support.microsoft.com/lifecycle) para obter as datas mais atuais.

## <a name="whats-next"></a>O que vem a seguir?

O SharePoint Server 2013 e o SharePoint Foundation 2013 podem ser instalados no local em seus próprios servidores. Ou você pode usar o SharePoint Online, que é um serviço online que faz parte do Microsoft 365. Você pode optar por:

- Migrar para o SharePoint Online.

- Atualize o SharePoint Server ou o SharePoint Foundation local.

- Execute ambas as opções acima.

- Implementar uma solução [híbrida do SharePoint](https://docs.microsoft.com/sharepoint/hybrid/hybrid) .

Considere os custos ocultos de manutenção de um farm de servidores, incluindo manutenção ou migração de personalizações e atualização de hardware. Se você tiver contado nesses fatores, será mais fácil atualizar no local. Se você executar o farm em servidores herdados do SharePoint sem muita personalização, poderá se beneficiar de uma migração planejada para o SharePoint Online. Para um ambiente local do SharePoint Server, você também pode considerar mover alguns dados no SharePoint Online para reduzir a sobrecarga de gerenciamento de hardware.

> [!NOTE]
> Os administradores do SharePoint podem criar uma assinatura do Microsoft 365, configurar novos sites do SharePoint Online e, em seguida, cortar o SharePoint Server 2010 de forma limpa, levando apenas documentos essenciais para os sites novos. Em seguida, os dados remanescentes podem ser exauridos do site do SharePoint Server 2010 para arquivos mortos locais.

|SharePoint Online|SharePoint Server local|
|---|---|
|Alto custo no tempo (planejamento/execução/verificação)|Alto custo no tempo (planejamento/execução/verificação)|
|Menor custo em fundos (sem compras de hardware)|Custo maior em fundos (aquisições de hardware)|
|Custo único em migração|Custo de um único tempo repetido por migração futura|
|Baixo custo total de propriedade/manutenção|Alto custo total de propriedade/manutenção|

Uma passagem única para o Microsoft 365 terá um custo maior enquanto você organiza os dados e decide o que deve ser adotado na nuvem e o que deixar atrás. Mas depois que os dados forem migrados, as futuras atualizações serão automáticas, já que você não precisará mais gerenciar atualizações de hardware e software. E o tempo de backup do farm será feito por um contrato de [nível de serviço (SLA) da Microsoft](https://go.microsoft.com/fwlink/?linkid=843153).

### <a name="migrate-to-sharepoint-online"></a>Migrar para o SharePoint Online

Certifique-se de que o SharePoint Online oferece todos os recursos de que você precisa. Consulte [Descrição do serviço do SharePoint](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-service-description).

Não é possível migrar diretamente do SharePoint Server 2010 (ou do SharePoint Foundation 2010) para o SharePoint Online. Tanto o trabalho de migração é manual. Mas esse estágio oferece a oportunidade de remover dados e sites que não são mais necessários antes da movimentação. Você pode arquivar outros dados no armazenamento. 

Lembre-se de que o SharePoint Server 2010 e o SharePoint Foundation 2010 não deixarão de funcionar no final do suporte. Assim, os administradores podem ter um período em que o SharePoint ainda esteja em execução se seus clientes esquecerem de mover alguns de seus dados.

Se você atualizar para o SharePoint Server 2013 ou o SharePoint Server 2016 e decidir colocar dados no SharePoint Online, você pode usar a [API de migração do SharePoint](https://support.office.com/article/Upload-on-premises-content-to-SharePoint-Online-using-PowerShell-cmdlets-555049c6-15ef-45a6-9a1f-a1ef673b867c?ui=en-US&amp;rs=en-US&amp;ad=US) para migrar informações para o onedrive for Business.

|Vantagem do SharePoint Online|Desvantagem do SharePoint Online|
|---|---|
|A Microsoft fornece hardware SPO e toda a administração de hardware.|Os recursos disponíveis podem diferir entre o SharePoint Server local e o SPO.|
|Você é o administrador global da sua assinatura e pode atribuir administradores a sites do SPO.|Algumas ações disponíveis para um administrador de farm no SharePoint Server local não existem (ou não são necessárias) na função de administrador do SharePoint no Microsoft 365. Mas a administração do SharePoint, a administração do conjunto de sites e a propriedade do site são locais para sua organização.|
|A Microsoft aplica patches, correções e atualizações para o hardware e software subjacentes, incluindo os SQL Servers nos quais o SharePoint Online é executado.|Como não há acesso ao sistema de arquivos subjacente no serviço, a personalização é limitada.|
|A Microsoft publica [contratos de nível de serviço](https://go.microsoft.com/fwlink/?linkid=843153) e se move rapidamente para resolver incidentes de nível de serviço.|O backup e a restauração e outras opções de recuperação são automatizados pelo serviço no SharePoint Online. Os backups são substituídos se não forem usados.|
|O teste de segurança e o ajuste de desempenho do servidor são realizados continuamente no serviço pela Microsoft.|As alterações na interface do usuário e em outros recursos do SharePoint são instaladas pelo serviço e podem precisar ser ativadas ou desativadas.|
|A Microsoft 365 atende a vários padrões da indústria: [ofertas de conformidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=843165).|A assistência do [FastTrack](https://go.microsoft.com/fwlink/?linkid=518597) para migração é limitada.  <br/> Grande parte da atualização será manual ou por meio da API de migração do SPO descrita no [mapa de conteúdo de migração do SharePoint Online e do onedrive](https://go.microsoft.com/fwlink/?linkid=843184).|
|Os engenheiros de suporte da Microsoft e os funcionários de datacenter não têm acesso administrativo irrestrito à sua assinatura.|Poderá haver custos adicionais se a infraestrutura de hardware precisar ser atualizada para suportar a versão mais recente do SharePoint ou se um farm secundário for necessário para a atualização.|
|Os provedores de soluções podem ajudar no trabalho único de migrar seus dados para o SharePoint Online.|Nem todas as alterações no SharePoint Online estão dentro do seu controle. Após a migração, as diferenças de design nos menus, bibliotecas e outros recursos podem afetar temporariamente a usabilidade.|
|Os produtos online são atualizados automaticamente no serviço. Os recursos podem ser substituídos, mas não há um verdadeiro ciclo de vida de suporte.|Há um ciclo de vida de fim de suporte para o SharePoint Server ou o SharePoint Foundation, bem como servidores SQL subjacentes.|

Se você optou por criar um novo site do Microsoft 365 e migrar manualmente os dados necessários para ele, verifique suas [Opções do Microsoft 365](https://www.microsoft.com/microsoft-365/).

### <a name="upgrade-sharepoint-server-on-premises"></a>Atualizar o SharePoint Server no local

A partir do SharePoint Server 2019, as atualizações devem ir em  *série*. Não há como atualizar do SharePoint Server 2010 para o SharePoint Server 2016 ou para o SharePoint 2019 diretamente. Caminho de atualização serial:

- SharePoint Server 2010 \> SharePoint server 2013 \> sharepoint Server 2016

Levará tempo e planejando seguir o caminho completo do SharePoint 2010 para o SharePoint Server 2016. As atualizações envolvem custos de hardware (os SQL Servers também devem ser atualizados), de software e de administração. Além disso, as personalizações talvez precisem ser atualizadas ou até abandonadas. Certifique-se de documentar personalizações críticas antes de atualizar seu farm do SharePoint Server.

> [!NOTE]
> É possível manter o farm de fim de suporte do SharePoint 2010, instalar um farm do SharePoint Server 2016 no novo hardware (para que os farms separados sejam executados lado a lado) e, em seguida, planejar e executar uma migração manual de conteúdo (para baixar e recarregar o conteúdo, por exemplo). Mas há possíveis armadilhas para essas movimentações manuais, como documentos vindos de 2010 com uma conta de última modificação atual com o alias da conta que faz a movimentação manual. E algum trabalho deve ser feito com antecedência, como recriação de sites, subsites, permissões e estruturas de lista. Certifique-se de limpar o ambiente antes da atualização. Considere quais dados você pode mover para o armazenamento ou que não são mais necessários. Isso pode reduzir o impacto da migração. Certifique-se de que seu farm existente é funcional antes da atualização e (certamente) antes de encerrar!

Lembre-se de revisar os *caminhos de atualização com e sem suporte*:

- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)

- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)

Se você tiver *personalizações*, é fundamental planejar cada etapa no caminho de migração:

- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)

- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)

|Vantagem local|Desvantagem no local|
|---|---|
|Controle total de todos os aspectos do farm do SharePoint (e seu SQL), do hardware do servidor.|Todas as interrupções e correções são responsabilidade de sua empresa. Mas você pode entrar em contato com o suporte da Microsoft se o seu produto não ultrapassar o fim do suporte.|
|Conjunto de recursos completo do SharePoint Server no local com a opção para conectar seu farm local a uma assinatura do SharePoint Online via híbrido.|Atualização, patches, correções de segurança, atualizações de hardware e todas as manutenções do SharePoint Server e do farm SQL são gerenciadas no local.|
|Acesso completo para mais opções de personalização do que com o SharePoint Online.|As [ofertas de conformidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=843165) devem ser configuradas manualmente no local.|
|O teste de segurança e o ajuste de desempenho do servidor são realizados em seu local sob o seu controle.|O Microsoft 365 pode disponibilizar recursos para o SharePoint Online que não interoperem com o SharePoint Server local.|
|Os provedores de soluções podem ajudar a migrar dados para a próxima versão do SharePoint Server (e além disso).|Seus sites do SharePoint Server não usarão automaticamente certificados [SSL/TLS](https://go.microsoft.com/fwlink/?linkid=843167) como é visto no SharePoint Online.|
|Controle total de convenções de nomenclatura e backup e restauração e outras opções de recuperação no SharePoint Server local.|O SharePoint Server local é sensível aos ciclos de vida do produto.|

### <a name="upgrade-resources"></a>Recursos de atualização

Comece comparando os requisitos de hardware e software. Se seu ambiente atual não atender aos requisitos básicos, talvez seja necessário atualizar primeiro o hardware no farm ou nos servidores SQL. 

Você pode decidir mover alguns dos seus sites para o hardware "verde" do SharePoint Online. Depois de fazer a avaliação, siga os caminhos e os métodos de atualização com suporte.

- *Requisitos de hardware/software para:*

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)

- *Limites e limites de software para:*

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)

- *A visão geral do processo de atualização para:*

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)

### <a name="create-a-hybrid-solution-with-sharepoint-online-and-sharepoint-server-on-premises"></a>Criar uma solução híbrida com o SharePoint Online e o SharePoint Server no local

Uma configuração híbrida oferece o melhor do local e do online para algumas necessidades de migração. Você pode conectar farms do SharePoint Server 2013, 2016 ou 2019 ao SharePoint Online para criar um SharePoint híbrido: [saiba mais sobre as soluções híbridas do SharePoint](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx).

Se um farm do SharePoint Server híbrido for sua meta de migração, configure os sites e usuários a serem movidos online e que precisam permanecer no local. Classificar o conteúdo do seu farm do SharePoint Server como alto, médio ou baixo o impacto em sua empresa pode ajudar nessa decisão. Talvez você só precise compartilhar contas de usuário para logon e o índice de pesquisa do SharePoint Server com o SharePoint Online. Mas esse fator pode não ficar claro até que você veja como seus sites são usados. Se sua empresa mais tarde decidir migrar todo o conteúdo para o SharePoint Online, você poderá mover todas as contas e dados restantes online e encerrar o farm local. O gerenciamento/administração do farm do SharePoint será feito através dos consoles do Microsoft 365 a partir desse ponto em diante.

Familiarize-se com os tipos existentes de híbridos e como configurar a conexão entre seu farm local do SharePoint e sua assinatura do Microsoft 365.

|Opção|Descrição|
|---|---|
|[Ofertas de conformidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=843165).|A assistência do [FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) para migração é limitada.<br/><br/> Grande parte da atualização será manual ou por meio da API de migração do SPO descrita no [mapa de conteúdo de migração do SharePoint Online e do onedrive](https://go.microsoft.com/fwlink/?linkid=843184).|
|Os engenheiros de suporte da Microsoft e os funcionários de datacenter não têm acesso administrativo irrestrito à sua assinatura.|Poderá haver custos adicionais se a infraestrutura de hardware precisar ser atualizada para oferecer suporte à versão mais recente do SharePoint ou se um farm secundário for necessário.|
|Os parceiros podem ajudar no trabalho único de migrar seus dados para o SharePoint Online.||
|Os produtos online são atualizados automaticamente no serviço. Os recursos podem ser substituídos, mas não há um verdadeiro fim de suporte.||

Se você optou por criar um novo site do Microsoft 365 e migrar manualmente os dados para ele, conforme necessário, verifique as [Opções do Microsoft 365](https://www.microsoft.com/microsoft-365/).

### <a name="upgrade-sharepoint-server-on-premises"></a>Atualizar o SharePoint Server no local

Não há uma maneira de ignorar versões em atualizações do SharePoint. Isso significa que as atualizações entram em série:

- SharePoint 2007 SharePoint \> server 2010 \> sharepoint Server 2013 \> SharePoint Server 2016

Para obter todo o caminho do SharePoint 2007 para o SharePoint Server 2016 significa um investimento significativo de tempo e envolverá o hardware (os servidores SQL também devem ser atualizados), de software e de administração. As personalizações deverão ser atualizadas ou abandonadas, de acordo com a criticalidade do recurso.

> [!NOTE]
> É possível manter seu farm do SharePoint 2007 de fim de vida, instalar um farm do SharePoint Server 2016 no novo hardware (para que os farms separados sejam executados lado a lado) e, em seguida, planejar e executar uma migração manual de conteúdo (para baixar e recarregar o conteúdo, por exemplo). Mas há algumas desvantagens para essas movimentações manuais, como movimentações de documentos que substituem a última conta modificada pelo alias da conta que faz a movimentação manual. E muito trabalho deve ser feito com antecedência, como recriação de sites, subsites, permissões e estruturas de lista. Em qualquer caso, considere quais dados você pode mover para o armazenamento ou não precisa mais reduzir o impacto da migração.

Certifique-se de limpar o ambiente antes da atualização. Certifique-se de que seu farm existente é funcional antes da atualização e certamente antes de encerrar!

Lembre-se de revisar os *caminhos de atualização com e sem suporte*:

- 
  [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843156)

- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)

- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)

Se você tiver *personalizações*, é fundamental planejar a atualização de cada etapa no caminho de migração:

- [SharePoint 2007](https://go.microsoft.com/fwlink/?linkid=843158)

- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)

- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)

|Pro local|Con on-premises|
|---|---|
|Controle total de todos os aspectos do farm do SharePoint, do hardware do servidor.|Todas as interrupções e correções são responsabilidade de sua empresa. (Mas você pode se deparar com o suporte da Microsoft pago se o seu produto não ultrapassar o fim do suporte.)|
|Conjunto de recursos completo do SharePoint Server no local com a opção para conectar seu farm local a uma assinatura do SharePoint Online via híbrido.|Atualização, patches, correções de segurança e toda a manutenção do SharePoint Server gerenciado no local.|
|Acesso total para maior personalização.|As [ofertas de conformidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=843165) devem ser configuradas manualmente no local.|
|O teste de segurança e o ajuste de desempenho do servidor são realizados em seu local sob o seu controle.|O Microsoft 365 pode disponibilizar recursos para o SharePoint Online que não interoperem com o SharePoint Server local.|
|Os parceiros podem ajudar a migrar dados para a próxima versão do SharePoint Server (e posteriores).|Seus sites do SharePoint Server não usarão automaticamente certificados [SSL/TLS](https://go.microsoft.com/fwlink/?linkid=843167) como é visto no SharePoint Online.|
|Controle total de convenções de nomenclatura e backup e restauração e outras opções de recuperação no SharePoint Server local.|O SharePoint Server local é sensível aos ciclos de vida do produto.|

### <a name="upgrade-resources"></a>Recursos de atualização

Comece sabendo que você atende aos requisitos de hardware e software e siga os métodos de atualização com suporte.

- *Requisitos de hardware/software para*:

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)

- Limites *e limites de software para*:

    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843245)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)

- *A visão geral do processo de atualização para*:

    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843250)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)

### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Criar uma solução híbrida do SharePoint entre o SharePoint Online e o local

Se a resposta para suas necessidades de migração estiver em algum lugar entre o controle oferecido pelo local e o menor custo de propriedade oferecido pelo SharePoint Online, você poderá conectar farms do SharePoint Server 2013 ou 2016 ao SharePoint Online por meio de híbridos. [Saiba mais sobre as soluções híbridas do SharePoint](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)

Se você decidir que um farm híbrido do SharePoint Server beneficiará sua empresa, familiarize-se com os tipos existentes de híbridos e como configurar a conexão entre seu farm do SharePoint local e sua assinatura do Microsoft 365.

Convém criar um ambiente de desenvolvimento/teste da Microsoft 365, que pode ser configurado com os [guias de laboratório de teste](m365-enterprise-test-lab-guides.md). Após obter uma assinatura de avaliação ou comprada da Microsoft 365, você pode criar os conjuntos de sites, Webs e bibliotecas de documentos no SharePoint Online para os quais você pode migrar dados. Você pode migrar manualmente, usando a API de migração ou, se quiser migrar o conteúdo do meu site para o OneDrive for Business, por meio do assistente híbrido.

> [!NOTE]
> Para usar a opção híbrida, seu farm do SharePoint Server 2010 deve primeiro ser atualizado no local para o SharePoint Server 2013 ou 2016. O SharePoint Foundation 2010 e o SharePoint Foundation 2013 não dão suporte a conexões híbridas com o SharePoint Online.

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Resumo das opções de cliente e servidores do Office 2010 e do Windows 7

Para obter um resumo visual das opções de atualização, migração e mover para nuvem para clientes e servidores do Office 2010 e Windows 7, confira o [pôster sobre o fim do suporte](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Fim do suporte para clientes e servidores do Office 2010 e pôster do Windows 7](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Este cartaz ilustra os vários caminhos que você pode seguir para evitar os produtos de servidor e cliente do Office 2010 e o fim de suporte do Windows 7, com caminhos e opções preferenciais no Microsoft 365 Enterprise realçados.

Você também pode [baixar](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) este cartaz e imprimi-lo no formato carta, legal ou tablóide (11 x 17).

## <a name="related-articles"></a>Artigos relacionados

[Recursos para ajudá-lo a atualizar do Office 2007 ou 2010 servidores e clientes](upgrade-from-office-2010-servers-and-products.md)

[Overview of the upgrade process from SharePoint 2010 to SharePoint 2013](https://technet.microsoft.com/library/mt493301%28v=office.16%29.aspx)

[Práticas recomendadas para atualização do SharePoint 2010 para o SharePoint 2013](https://technet.microsoft.com/library/mt493305%28v=office.16%29.aspx)

[Resolver problemas de atualização do banco de dados no SharePoint 2013](https://go.microsoft.com/fwlink/?linkid=843195)

[Procurar provedores de solução da Microsoft para ajudá-lo com a atualização](https://go.microsoft.com/fwlink/?linkid=841249)

[Política atualizada de manutenção do produto para SharePoint Server 2013](https://technet.microsoft.com/library/mt493253%28v=office.16%29.aspx)

[Política atualizada de manutenção do produto para SharePoint Server 2016](https://technet.microsoft.com/library/mt782882%28v=office.16%29.aspx)
