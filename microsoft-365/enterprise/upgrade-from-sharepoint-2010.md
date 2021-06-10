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
description: Encontre informações e recursos para atualizar do SharePoint 2010 e do Sharepoint Server 2010. O suporte para ambos termina em 13 de abril de 2021.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4fa82fb0e382a244cdc126609ac62d17280b9702
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925327"
---
# <a name="upgrading-from-sharepoint-2010"></a>Atualizando do SharePoint 2010

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

O Microsoft SharePoint 2010 e o SharePoint Server 2010 chegarão ao fim do suporte em 13 de abril de **2021**. Este artigo fornece recursos para ajudá-lo a migrar seus dados existentes do SharePoint Server 2010 para o SharePoint Online no Microsoft 365 ou atualizar seu ambiente local do SharePoint Server 2010.

## <a name="what-is-end-of-support"></a>O que *é o fim do suporte?*

A maioria dos produtos Microsoft tem um ciclo de vida de suporte, durante o qual eles têm novos recursos, correções de bugs, correções de segurança e assim por diante. Após a data de término do suporte, o produto não para de funcionar, mas a Microsoft não fornece mais:

- Suporte técnico para problemas que podem ocorrer.

- Correções de bugs para problemas que podem afetar a estabilidade e a usabilidade do servidor.

- Correções de segurança para vulnerabilidades que podem tornar o servidor vulnerável a violações de segurança.

- Atualizações de fuso horário.

Isso significa que não haverá mais atualizações, patches ou correções para o produto (incluindo patches/correções de segurança). O Suporte da Microsoft terá deslocado totalmente seus esforços de suporte para versões mais recentes.

À medida que o fim do suporte do SharePoint Server 2010 se aproxima, exclua os dados que você não precisa mais antes de atualizar o produto e migrar seus dados importantes.

> [!NOTE]
> Um ciclo de vida de software geralmente dura dez anos a partir da versão inicial. [Os provedores de soluções](https://go.microsoft.com/fwlink/?linkid=841249) da Microsoft podem ajudá-lo a atualizar para a próxima versão do software ou migrar para Microsoft 365 migração (ou ambos). Certifique-se de estar ciente das datas de fim de suporte para tecnologias subjacentes críticas também, especialmente para a versão do Microsoft SQL Server que você está usando com SharePoint. Para obter mais informações, consulte [Política de Ciclo de Vida Fixa](https://support.microsoft.com/help/14085).

## <a name="plan-ahead"></a>Planejar com antecedência

Verifique as datas em que o suporte termina no [site ciclo de vida do produto.](https://support.microsoft.com/lifecycle/search?alpha=SharePoint%20Server%202010) Planeje suas atualizações ou migrações com essas datas em mente. Lembre-se de *que seu produto não para de funcionar* na data listada. Mas como sua instalação não será mais corrigida após essa data, você vai querer planejar uma transição suave para a próxima versão do produto.

Essa matriz ajuda a plotar um curso entre opções de migração:

|Fim do produto de suporte|Good |Melhor|
|---|---|---|
|SharePoint Server 2010|SharePoint Server 2013 (local)|SharePoint Online|
||SharePoint Server 2013 híbrido com SharePoint Online|SharePoint Server 2016 (local)|
|||SharePoint Pesquisa Híbrida na Nuvem|

Se você escolher uma opção na parte baixa da escala (boa), você precisará começar a planejar outra atualização logo após a migração do SharePoint Server 2010.

Aqui estão os três caminhos que você pode seguir para evitar o fim do suporte para SharePoint Server 2010.

![SharePoint Caminhos de atualização do Server 2010](../media/upgrade-from-sharepoint-2010/upgrade-from-sharepoint-2010-paths.png)

> [!NOTE]
> O fim do suporte para o SharePoint Server 2010 e o SharePoint Foundation 2010 está agendado para 13 de abril de 2021. Mas verifique o [site](https://support.microsoft.com/lifecycle) do Ciclo de Vida do Produto para as datas mais atuais.

## <a name="whats-next"></a>O que vem a seguir?

SharePoint O Server 2013 e o SharePoint Foundation 2013 podem ser instalados no local em seus próprios servidores. Ou você pode usar SharePoint Online, que é um serviço online que faz parte do Microsoft 365. Você pode optar por:

- Migre para o SharePoint Online.

- Atualize SharePoint Server ou SharePoint Foundation no local.

- Faça as duas coisas acima.

- Implemente uma [SharePoint híbrida.](/sharepoint/hybrid/hybrid)

Considere os custos ocultos de manutenção de um farm de servidores, incluindo manutenção ou migração de personalizações e atualização de hardware. Se você tiver conta desses fatores, será mais fácil atualizar no local. Se você executar seu farm em servidores SharePoint herdados sem personalização pesada, poderá se beneficiar de uma migração planejada para o SharePoint Online. Para um ambiente de servidor SharePoint local, você também pode considerar mover alguns dados no SharePoint Online para reduzir a sobrecarga de gerenciamento de hardware.

> [!NOTE]
> SharePoint administradores podem criar uma Assinatura Microsoft 365, configurar novos sites do SharePoint Online e, em seguida, recortar do SharePoint Server 2010 de forma limpa, levando apenas documentos essenciais para os sites novos. Em seguida, qualquer dado restante pode ser drenado do site SharePoint Server 2010 para arquivos locais.

|SharePoint Online|SharePoint Servidor local|
|---|---|
|Alto custo no tempo (plano/execução/verificação)|Alto custo no tempo (plano/execução/verificação)|
|Menor custo em fundos (sem compras de hardware)|Custo mais alto em fundos (compras de hardware)|
|Custo único na migração|Custo único repetido por migração futura|
|Baixo custo total de propriedade/manutenção|Alto custo total de propriedade/manutenção|

Uma movimentação única para Microsoft 365 terá um custo mais alto enquanto você organiza os dados e decide o que levar para a nuvem e o que deixar para trás. Mas depois que seus dados são migrados, as atualizações futuras serão automáticas, pois você não precisará mais gerenciar atualizações de hardware e software. E o tempo de atualização do seu farm será respaldado por um contrato de nível de serviço [da Microsoft (SLA)](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement).

### <a name="migrate-to-sharepoint-online"></a>Migrar para o SharePoint Online

Certifique-se SharePoint Online oferece todos os recursos necessários. Consulte [SharePoint descrição do serviço](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-service-description).

Não é possível migrar diretamente do SharePoint Server 2010 (ou SharePoint Foundation 2010) para SharePoint Online. Muito do trabalho de migração é manual. Mas esse estágio oferece a oportunidade de podar dados e sites que não são mais necessários antes da movimentação. Você pode arquivar outros dados no armazenamento. 

Lembre-se de SharePoint Server 2010 e SharePoint Foundation 2010 não param de funcionar no final do suporte. Portanto, os administradores podem ter um período em que SharePoint ainda estiver em execução se seus clientes esquecerem de mover alguns de seus dados.

Se você atualizar para o SharePoint Server 2013 ou o SharePoint Server 2016 e decidir colocar dados no SharePoint Online, poderá usar [a API](https://support.office.com/article/Upload-on-premises-content-to-SharePoint-Online-using-PowerShell-cmdlets-555049c6-15ef-45a6-9a1f-a1ef673b867c?ui=en-US&amp;rs=en-US&amp;ad=US) de Migração do SharePoint para migrar informações para o OneDrive for Business.

|SharePoint Vantagem online|SharePoint Desvantagem online|
|---|---|
|A Microsoft fornece hardware SPO e toda a administração de hardware.|Os recursos disponíveis podem diferir entre SharePoint Server local e SPO.|
|Você é o administrador global da sua assinatura e pode atribuir administradores a sites SPO.|Algumas ações disponíveis para um administrador de farm no SharePoint Server local não existem (ou não são necessárias) na função de administrador do SharePoint no Microsoft 365. Mas SharePoint Administração, Administração do Conjunto de Sites e Propriedade do Site são locais para sua organização.|
|A Microsoft aplica patches, correções e atualizações a hardware e software subjacentes, incluindo SQL servidores nos quais o SharePoint Online é executado.|Como não há acesso ao sistema de arquivos subjacente no serviço, a personalização é limitada.|
|A Microsoft [publica contratos de nível de serviço](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement) e se move rapidamente para resolver incidentes de nível de serviço.|Backup e restauração e outras opções de recuperação são automatizadas pelo serviço no SharePoint Online. Os backups são substituídos se não usados.|
|Os testes de segurança e o ajuste de desempenho do servidor são executados continuamente no serviço pela Microsoft.|Alterações na interface do usuário e outros recursos SharePoint são instalados pelo serviço e podem precisar ser alternados ou desligados.|
|Microsoft 365 atende a muitos padrões do setor: [ofertas de conformidade da Microsoft.](/compliance/regulatory/offering-home)|[A assistência do FastTrack](https://go.microsoft.com/fwlink/?linkid=518597) para migração é limitada.  <br/> Grande parte da atualização será manual ou por meio da API de Migração de SPO descrita no roteiro SharePoint Online e OneDrive Conteúdo de [Migração.](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets)|
|Os engenheiros de suporte da Microsoft e funcionários do datacenter não têm acesso de administrador irrestrito à sua assinatura.|Pode haver custos adicionais se a infraestrutura de hardware precisar ser atualizada para dar suporte à versão mais recente do SharePoint ou se um farm secundário for necessário para atualização.|
|Os provedores de soluções podem ajudar com o trabalho único de migrar seus dados para SharePoint Online.|Nem todas as alterações no SharePoint Online estão sob seu controle. Após a migração, as diferenças de design em menus, bibliotecas e outros recursos podem afetar temporariamente a usabilidade.|
|Os produtos online são atualizados automaticamente em todo o serviço. Os recursos podem ser preteridores, mas não há um final verdadeiro do ciclo de vida do suporte.|Há um ciclo de vida de fim de suporte para o SharePoint Server ou SharePoint Foundation, bem como servidores SQL subjacentes.|

Se você decidiu criar um novo site de Microsoft 365 e migrar manualmente os dados para ele conforme necessário, verifique suas opções de Microsoft 365 [.](https://www.microsoft.com/microsoft-365/)

### <a name="upgrade-sharepoint-server-on-premises"></a>Atualizar SharePoint servidor local

A partir SharePoint Server 2019, as atualizações devem ser *em série*. Não há como atualizar do SharePoint Server 2010 para o SharePoint Server 2016 ou para SharePoint 2019 diretamente. Caminho de atualização serial:

- SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016

Levará tempo e planejamento para seguir todo o caminho do SharePoint 2010 para o SharePoint Server 2016. As atualizações envolvem custos para hardware (SQL servidores também devem ser atualizados), software e administração. Além disso, as personalizações podem precisar ser atualizadas ou até mesmo abandonadas. Certifique-se de documentar personalizações críticas antes de atualizar seu farm SharePoint Server.

> [!NOTE]
> É possível manter seu farm de fim de suporte do SharePoint 2010, instalar um farm do SharePoint Server 2016 em novo hardware (para que os farms separados executem lado a lado) e, em seguida, planeje e execute uma migração manual de conteúdo (para baixar e carregar conteúdo, por exemplo). Mas há possíveis armadilhas para essas movimentações manuais, como documentos provenientes de 2010 que têm uma conta de última modificação atual com o alias da conta que faz a movimentação manual. E alguns trabalhos devem ser feitos com antecedência, como recriar sites, subsites, permissões e estruturas de lista. Certifique-se de limpar seu ambiente antes da atualização. Considere quais dados você pode mover para o armazenamento ou não precisa mais. Isso pode reduzir o impacto da migração. Não se desfaça de que seu farm existente está funcional antes de atualizar e (certamente) antes da desativação!

Lembre-se de revisar os caminhos de atualização com suporte *e sem suporte:*

- [SharePoint Server 2010](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))

- [SharePoint Server 2013](/SharePoint/upgrade-and-update/review-supported-editions-and-products-for-upgrading-to-sharepoint-2013)

Se você tiver *personalizações,* é fundamental planejar cada etapa no caminho de migração:

- [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc263203(v=office.14))

- [SharePoint Server 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)

|Vantagem local|Desvantagem local|
|---|---|
|Controle total de todos os aspectos do farm SharePoint (e sua SQL), do hardware do servidor para cima.|Todas as quebras e correções são de responsabilidade da sua empresa. Mas você pode envolver o Suporte Pago da Microsoft se seu produto não estiver no final do suporte.|
|Conjunto de recursos completo do SharePoint Server local com a opção de conectar seu farm local a uma assinatura SharePoint Online via híbrido.|Atualização, patches, correções de segurança, atualizações de hardware e toda a manutenção do SharePoint Server e seu farm SQL são gerenciados no local.|
|Acesso total para opções de personalização maiores do que com SharePoint Online.|[As ofertas de](/compliance/regulatory/offering-home) conformidade da Microsoft devem ser configuradas manualmente no local.|
|Testes de segurança e ajuste de desempenho do servidor são realizados em seu local sob seu controle.|Microsoft 365 disponibilizar recursos para o SharePoint Online que não interoperam com o SharePoint Server local.|
|Os provedores de soluções podem ajudar a migrar dados para a próxima versão do SharePoint Server (e além).|Seus sites SharePoint Server não usarão automaticamente [certificados SSL/TLS,](/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016) como é visto no SharePoint Online.|
|Controle total das convenções de nomenis e backup e restauração e outras opções de recuperação no SharePoint Server local.|SharePoint O servidor local é sensível aos ciclos de vida do produto.|

### <a name="upgrade-resources"></a>Atualizar recursos

Comece comparando requisitos de hardware e software. Se o ambiente atual não atender aos requisitos básicos, talvez seja necessário atualizar o hardware no farm ou nos servidores SQL primeiro. 

Você pode decidir mover alguns de seus sites para o hardware "evergreen" do SharePoint Online. Depois de fazer sua avaliação, siga os métodos e caminhos de atualização suportados.

- *Requisitos de hardware/software para:*

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/hardware-and-software-requirements-0)  |  [SharePoint Server 2016](/SharePoint/install/hardware-and-software-requirements)

- *Limites e limites de software para:*

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262787(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/software-boundaries-and-limits)  |  [SharePoint Server 2016](/SharePoint/install/software-boundaries-and-limits-0)

- *A visão geral do processo de atualização para:*

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc303420(v=office.14))  |  [SharePoint Server 2013](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)  |  [SharePoint Server 2016](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)

### <a name="create-a-hybrid-solution-with-sharepoint-online-and-sharepoint-server-on-premises"></a>Criar uma solução híbrida com SharePoint Online e SharePoint Servidor local

Uma instalação híbrida fornece o melhor local e online para algumas necessidades de migração. Você pode conectar farms do SharePoint Server 2013, 2016 ou 2019 ao SharePoint Online para criar um SharePoint híbrido: saiba mais sobre SharePoint [soluções](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)híbridas.

Se um farm SharePoint Server híbrido for sua meta de migração, descubra quais sites e usuários devem se mover online e quais precisam permanecer no local. A classificação SharePoint conteúdo do farm do servidor como alto, médio ou baixo impacto para sua empresa pode ajudar nessa decisão. Talvez você só precise compartilhar contas de usuário para logon e o índice de pesquisa SharePoint Server com SharePoint Online. Mas esse fator pode não estar claro até que você veja como seus sites são usados. Se a sua empresa decidir migrar todo o conteúdo para o SharePoint Online, você poderá mover todas as contas e dados restantes online e desmantelar seu farm local. O gerenciamento/administração do SharePoint farm será feito Microsoft 365 consoles a partir desse ponto.

Certifique-se de se familiarizar com os tipos de híbridos existentes e como configurar a conexão entre seu farm SharePoint local e sua assinatura Microsoft 365 local.

|Opção|Descrição|
|---|---|
|[Ofertas de conformidade da Microsoft](/compliance/regulatory/offering-home).|[A assistência do FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) para migração é limitada.<br/><br/> Grande parte da atualização será manual ou por meio da API de Migração de SPO descrita no roteiro SharePoint Online e OneDrive Conteúdo de [Migração.](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets)|
|Os engenheiros de suporte da Microsoft e funcionários do datacenter não têm acesso de administrador irrestrito à sua assinatura.|Pode haver custos adicionais se a infraestrutura de hardware precisar ser atualizada para dar suporte à versão mais recente do SharePoint ou se um farm secundário for necessário.|
|Os parceiros podem ajudar com o trabalho único de migrar seus dados para SharePoint Online.||
|Os produtos online são atualizados automaticamente em todo o serviço. Os recursos podem ser preteridores, mas não há um fim verdadeiro do suporte.||

Se você decidiu criar um novo site Microsoft 365 e migrar manualmente os dados para ele conforme necessário, verifique suas opções [Microsoft 365 .](https://www.microsoft.com/microsoft-365/)

### <a name="upgrade-sharepoint-server-on-premises"></a>Atualizar SharePoint servidor local

Não há como ignorar versões em SharePoint Atualizações. Isso significa que as atualizações são em série:

- SharePoint 2007 \> SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016

Para seguir todo o caminho do SharePoint 2007 para o SharePoint Server 2016 significará um investimento significativo de tempo e envolverá hardware (os servidores SQL também devem ser atualizados), software e custos de administração. As personalizações precisarão ser atualizadas ou abandonadas, de acordo com a criticidade do recurso.

> [!NOTE]
> É possível manter seu farm de fim de vida SharePoint 2007, instalar um farm do SharePoint Server 2016 em um novo hardware (para que os farms separados executem lado a lado) e planeje e execute uma migração manual de conteúdo (para baixar e carregar conteúdo, por exemplo). Mas há algumas desvantagens para essas movimentações manuais, como movimentações de documentos substituindo a última conta modificada pelo alias da conta que faz a movimentação manual. E muito trabalho deve ser feito com antecedência, como recriar sites, subsites, permissões e estruturas de lista. Em qualquer caso, considere quais dados você pode mover para o armazenamento ou não precisa mais reduzir o impacto da migração.

Certifique-se de limpar seu ambiente antes da atualização. Não se desfaça de que seu farm existente está funcional antes de atualizar e, certamente, antes de desmantelá-lo!

Lembre-se de revisar os caminhos de atualização com suporte *e sem suporte:*

- 
  [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))

- [SharePoint Server 2010](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))

- [SharePoint Server 2013](/SharePoint/upgrade-and-update/review-supported-editions-and-products-for-upgrading-to-sharepoint-2013)

Se você tiver *personalizações,* é fundamental planejar sua atualização para cada etapa no caminho de migração:

- [SharePoint 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc263203(v=office.12))

- [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc263203(v=office.14))

- [SharePoint Server 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)

|Profissional local|Con local|
|---|---|
|Controle total de todos os aspectos do SharePoint Farm, do hardware do servidor para cima.|Todas as quebras e correções são de responsabilidade da sua empresa. (Mas você pode envolver o Suporte Pago da Microsoft se seu produto não estiver no final do suporte.)|
|Conjunto de recursos completo do SharePoint Server local com a opção de conectar seu farm local a uma assinatura SharePoint Online via híbrido.|Atualização, patches, correções de segurança e toda a manutenção do servidor SharePoint gerenciado no local.|
|Acesso total para maior personalização.|[As ofertas de](/compliance/regulatory/offering-home) conformidade da Microsoft devem ser configuradas manualmente no local.|
|Testes de segurança e ajuste de desempenho do servidor são realizados em seu local sob seu controle.|Microsoft 365 disponibilizar recursos para o SharePoint Online que não interoperam com o SharePoint Server local.|
|Os parceiros podem ajudar a migrar dados para a próxima versão do SharePoint Server (e além).|Seus sites SharePoint Server não usarão automaticamente [certificados SSL/TLS,](/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016) como é visto no SharePoint Online.|
|Controle total das convenções de nomenis e backup e restauração e outras opções de recuperação no SharePoint Server local.|SharePoint O servidor local é sensível aos ciclos de vida do produto.|

### <a name="upgrade-resources"></a>Atualizar recursos

Comece sabendo que você atenderá aos requisitos de hardware e software e siga os métodos de atualização com suporte.

- *Requisitos de hardware/software para*:

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/hardware-and-software-requirements-0)  |  [SharePoint Server 2016](/SharePoint/install/hardware-and-software-requirements)

- *Limites e limites de software para*:

    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262787(v=office.12))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262787(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/software-boundaries-and-limits)  |  [SharePoint Server 2016](/SharePoint/install/software-boundaries-and-limits-0)

- *A visão geral do processo de atualização para*:

    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc303420(v=office.12))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc303420(v=office.14))  |  [SharePoint Server 2013](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)  |  [SharePoint Server 2016](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)

### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Criar uma SharePoint híbrida entre SharePoint Online e local

Se a resposta às suas necessidades de migração estiver em algum lugar entre o controle oferecido pelo local e o menor custo de propriedade oferecido pelo SharePoint Online, você poderá conectar farms do SharePoint Server 2013 ou 2016 ao SharePoint Online por meio de híbridos. [Saiba mais sobre SharePoint soluções híbridas](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)

Se você decidir que um farm de servidores SharePoint híbrido beneficiará sua empresa, familiarize-se com os tipos de híbridos existentes e como configurar a conexão entre seu farm SharePoint local e sua assinatura Microsoft 365 local.

Talvez você queira criar um ambiente Microsoft 365 dev/test, que você pode configurar com Guias [de Laboratório de Teste.](m365-enterprise-test-lab-guides.md) Depois de obter uma assinatura de avaliação ou Microsoft 365, você pode criar os conjunto de sites, webs e bibliotecas de documentos no SharePoint Online para o qual você pode migrar dados. Você pode migrar manualmente, por meio da API de Migração, ou, se quiser migrar o conteúdo de Meu Site para OneDrive for Business, por meio do assistente híbrido.

> [!NOTE]
> Para usar a opção híbrida, o farm do SharePoint Server 2010 deve primeiro ser atualizado no local para o SharePoint Server 2013 ou 2016. SharePoint O Foundation 2010 e o SharePoint Foundation 2013 não suportam conexões híbridas com SharePoint Online.

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Resumo das opções para Office 2010 clientes e servidores e Windows 7

Para obter um resumo visual das opções de atualização, migração e mover para nuvem para clientes e servidores do Office 2010 e Windows 7, confira o [pôster sobre o fim do suporte](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Fim do suporte para clientes e servidores Office 2010 e Windows cartaz 7](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Este cartaz ilustra os vários caminhos que você pode seguir para evitar os produtos de cliente e servidor do Office 2010 2010 e Windows fim de suporte 7, com caminhos preferenciais e suportes de opção em Microsoft 365 Enterprise realçadas.

Você também pode [baixar](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) esse cartaz e imprimi-lo em formato de carta, legal ou tablóide (11 x 17).

## <a name="related-articles"></a>Artigos relacionados

[Recursos para ajudá-lo a atualizar Office 2007 ou 2010 servidores e clientes](upgrade-from-office-2010-servers-and-products.md)

[Overview of the upgrade process from SharePoint 2010 to SharePoint 2013](/SharePoint/upgrade-and-update/overview-of-the-upgrade-process-from-sharepoint-2010-to-sharepoint-2013)

[Práticas recomendadas para atualização do SharePoint 2010 para o SharePoint 2013](/SharePoint/upgrade-and-update/best-practices-for-upgrading-from-sharepoint-2010-to-sharepoint-2013)

[Resolver problemas de atualização do banco de dados no SharePoint 2013](/SharePoint/upgrade-and-update/troubleshoot-database-upgrade-issues-in-sharepoint-2013)

[Pesquisar provedores de soluções da Microsoft para ajudar na atualização](https://go.microsoft.com/fwlink/?linkid=841249)

[Política atualizada de manutenção do produto para SharePoint Server 2013](/SharePoint/product-servicing-policy/updated-product-servicing-policy-for-sharepoint-2013)

[Política atualizada de manutenção do produto para SharePoint Server 2016](/SharePoint/product-servicing-policy/updated-product-servicing-policy-for-sharepoint-server-2016)