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
description: Encontre informações e recursos para atualizar do SharePoint 2010 e do SharePoint Server 2010, como suporte para ambas as extremidades em 13 de outubro de 2020.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 57e44cf14a74f6a5a2098512e0a2339037d70655
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686911"
---
# <a name="upgrading-from-sharepoint-2010"></a>Atualizando do SharePoint 2010

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

O Microsoft SharePoint 2010 e o SharePoint Server 2010 atingirão o fim do suporte em **13 de abril de 2021**. Este artigo detalha os recursos para ajudá-lo a migrar seus dados existentes do SharePoint Server 2010 para o SharePoint Online no Microsoft 365 ou a atualizar seu ambiente local do SharePoint Server 2010.
  
## <a name="what-is-end-of-support"></a>O que é o fim do suporte?

Quando o software do SharePoint Server 2010 e do SharePoint Foundation 2010 atinge o final do seu ciclo de vida de suporte (o tempo durante o qual a Microsoft fornece novos recursos, correções de erros, correções de segurança e assim por diante), isso é chamado de ' fim de suporte ' do software ou, às vezes, de ' aposentadoria '. Após o fim do suporte (ou EOS) de um produto, nada é realmente desligado ou pára de funcionar; no entanto, no final do suporte ao software, a Microsoft não fornece mais:
  
- Suporte técnico para problemas que podem ocorrer;
    
- Correções de erros descobertas e que podem afetar a estabilidade e a usabilidade do servidor;
    
- Correções de segurança para vulnerabilidades descobertas e que podem tornar o servidor vulnerável a falhas de segurança;
    
- Atualizações de fuso horário.
    
Isso significa que não haverá mais atualizações, patches ou correções que serão remetidas para o produto (incluindo patches de segurança/correções) e o suporte da Microsoft terá alterado completamente seus esforços de suporte para versões mais recentes. Como o fim do suporte do SharePoint Server 2010 abordagens, você deve aproveitar as oportunidades de cortar dados que não são mais necessários antes de atualizar o produto e/ou migrar seus dados importantes.
  
> [!NOTE]
> Um ciclo de vida de software normalmente dura dez anos a partir da data da versão inicial do produto. Você pode pesquisar os [provedores de soluções da Microsoft](https://go.microsoft.com/fwlink/?linkid=841249) que podem ajudar na atualização para a próxima versão do software ou com a migração do Microsoft 365 (ou ambos). Certifique-se de que você está ciente do fim das datas de suporte em tecnologias básicas fundamentais, particularmente da versão do SQL Server que você está usando com o SharePoint. Consulte [política de ciclo de vida fixo](https://support.microsoft.com/help/14085) para entender o ciclo de vida do produto em detalhes.
  
## <a name="what-are-my-options"></a>Quais são as minhas opções?

Primeiro, verifique a data em que o suporte termina no [site de ciclo de vida do produto](https://support.microsoft.com/lifecycle/search?alpha=SharePoint%20Server%202010). Em seguida, certifique-se de planejar a atualização ou o tempo de migração com o conhecimento dessa data. Lembre-se de que seu produto  *não vai parar de funcionar*  na data listada e você pode continuar a usar, mas isso, pois a instalação não será mais corrigida após essa data, você vai querer uma estratégia que o ajudará a fazer uma transição mais tranqüila para a próxima versão do produto. 
  
Esta matriz ajuda a plotar um curso quando se trata da migração dos recursos do produto e dos dados do usuário:
  
| Produto do fim do suporte | Good | Melhor |
|:-----|:-----|:-----|
|SharePoint Server 2010  <br/> |SharePoint Server 2013 (local)  <br/> |SharePoint Online  <br/> |
||SharePoint Server 2013 híbrido com o SharePoint Online  <br/> |SharePoint Server 2016 (local)  <br/> |
| | |Pesquisa híbrida do SharePoint Cloud  <br/> |
   
Se você escolher opções no final da escala (opções boas), precisará começar a planejar outra atualização logo após a conclusão da migração do SharePoint Server 2010. 

Estes são os três caminhos que você pode seguir para evitar o fim do suporte para o SharePoint Server 2010.

![Caminhos de atualização do SharePoint Server 2010](../media/upgrade-from-sharepoint-2010/upgrade-from-sharepoint-2010-paths.png)

>[!Note]
>O fim do suporte para o SharePoint Server 2010 e o SharePoint Foundation 2010 estão agendados para 13 de abril de 2021, mas *lembre* -se de que você sempre deve verificar o [site de ciclo de vida do produto](https://support.microsoft.com/lifecycle) para obter as datas mais atuais.
>

  
## <a name="where-should-i-go-next"></a>Onde devo ir para a próxima?

O SharePoint Server 2013 e o SharePoint Foundation 2013 podem ser instalados no local em seus próprios servidores. Caso contrário, você pode usar o SharePoint Online, que é um serviço online que faz parte do Microsoft Microsoft 365. Você pode optar por:
  
- Migrar para o SharePoint Online
    
- Atualizar o SharePoint Server ou o SharePoint Foundation local
    
- Faça ambas as opções acima
    
- Implementar uma solução [híbrida do SharePoint](https://docs.microsoft.com/sharepoint/hybrid/hybrid) 
    
Esteja ciente dos custos ocultos associados à manutenção de um farm de servidores que está indo, mantendo ou migrando personalizações e atualizando o hardware no qual o SharePoint Server depende. Se você estiver ciente e tiver considerado tudo isso, será mais fácil continuar a atualizar no local. Caso contrário, se você executar o farm em servidores herdados do SharePoint sem muita personalização, poderá se beneficiar de uma migração planejada para o SharePoint Online. Também é possível que, para seu ambiente local do SharePoint Server, você possa optar por colocar alguns dados no SharePoint Online para reduzir a quantidade de gerenciamento de hardware que mantém todos os seus dados no local. Pode ser mais econômico mover alguns de seus dados para o SharePoint Online.
  
> [!NOTE]
> Os administradores do SharePoint podem criar uma assinatura do Microsoft 365, configurar um novo site do SharePoint Online de marca e, em seguida, cortar do SharePoint Server 2010, de forma limpa, levando apenas os documentos mais essenciais aos novos sites do SharePoint Online. A partir daí, todos os dados remanescentes podem ser exauridos do site do SharePoint Server 2010 para arquivos mortos locais. 
  
|**SharePoint Online**|**SharePoint Server local**|
|:-----|:-----|
|Alto custo no tempo (planejamento/execução/verificação)  <br/> |Alto custo no tempo (planejamento/execução/verificação)  <br/> |
|Menor custo em fundos (sem compras de hardware)  <br/> |Custo maior em fundos (aquisições de hardware)  <br/> |
|Custo único em migração  <br/> |Custo de um único tempo repetido por migração futura  <br/> |
|Baixo custo total de propriedade/manutenção  <br/> |Alto custo total de propriedade/manutenção  <br/> |
   
Quando você migrar para o Microsoft 365, a movimentação única terá um custo mais pesado em planejamento, em frente (enquanto você estiver organizando dados e decidindo o que deve ser usado para a nuvem e o que deixar atrás). No entanto, depois que os dados forem migrados, as atualizações serão automáticas desse ponto, visto que você não precisará mais gerenciar atualizações de hardware e de software, e o tempo de ingestão do farm será feito por um contrato de nível de serviço ([SLA](https://go.microsoft.com/fwlink/?linkid=843153)) da Microsoft.
  
### <a name="migrate-to-sharepoint-online"></a>Migrar para o SharePoint Online

Certifique-se de que o SharePoint Online oferece todos os recursos de que você precisa conferindo sua [Descrição de serviço](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-service-description).
  
No momento, não há um meio pelo qual você pode migrar diretamente do SharePoint Server 2010 (ou SharePoint Foundation 2010) para o SharePoint Online, portanto, grande parte do trabalho é manual. Isso lhe dá a oportunidade de arquivar e remover dados e sites que não são mais necessários, antes da movimentação. Você pode arquivar outros dados no armazenamento. Além disso, lembre-se de que nem o SharePoint Server 2010 nem o SharePoint Foundation 2010 deixarão de funcionar no final do suporte, para que os administradores possam ter um período durante o qual o SharePoint ainda esteja em execução se seus clientes esquecerem de mover alguns de seus dados.
  
Se você atualizar para o SharePoint Server 2013 ou o SharePoint Server 2016 e decidir colocar dados no SharePoint Online, sua movimentação também pode envolver o uso da [API de migração do SharePoint](https://support.office.com/article/Upload-on-premises-content-to-SharePoint-Online-using-PowerShell-cmdlets-555049c6-15ef-45a6-9a1f-a1ef673b867c?ui=en-US&amp;rs=en-US&amp;ad=US) (para migrar informações para o onedrive for Business). 
  
|**Vantagem do SharePoint Online**|**Desvantagem do SharePoint Online**|
|:-----|:-----|
|A Microsoft fornece hardware SPO e toda a administração de hardware.  <br/> |Os recursos disponíveis podem ser diferentes entre o SharePoint Server local e o SPO.  <br/> |
|Você é o administrador global da sua assinatura e pode atribuir administradores a sites do SPO.  <br/> |Algumas ações disponíveis para um administrador de farm no SharePoint Server local não existem (ou não são necessárias) na função de administrador do SharePoint no Microsoft 365, mas a administração do SharePoint, a administração do conjunto de sites e a propriedade do site são locais para sua organização.  <br/> |
|A Microsoft aplica patches, correções e atualizações para o hardware e software subjacentes (incluindo os SQL Servers nos quais o SharePoint Online é executado).  <br/> |Como não há acesso ao sistema de arquivos subjacente no serviço, algumas personalizações são limitadas.  <br/> |
|A Microsoft publica [contratos de nível de serviço](https://go.microsoft.com/fwlink/?linkid=843153) e se move rapidamente para resolver incidentes de nível de serviço.  <br/> |O backup e a restauração e outras opções de recuperação são automatizados pelo serviço no SharePoint Online-os backups são substituídos se não forem usados.  <br/> |
|O teste de segurança e o ajuste de desempenho do servidor são realizados continuamente no serviço da Microsoft.  <br/> |As alterações na interface do usuário e em outros recursos do SharePoint são instaladas pelo serviço e podem precisar ser ativadas ou desativadas.  <br/> |
|A Microsoft 365 atende a vários padrões da indústria: [ofertas de conformidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=843165).  <br/> |A assistência do [FastTrack](https://go.microsoft.com/fwlink/?linkid=518597) para migração é limitada.  <br/> Grande parte da atualização será manual ou por meio da API de migração do SPO descrita no [mapa de conteúdo de migração do SharePoint Online e do onedrive](https://go.microsoft.com/fwlink/?linkid=843184).  <br/> |
|Os engenheiros de suporte da Microsoft e os funcionários do datacenter têm acesso administrativo irrestrito à sua assinatura.  <br/> |Poderá haver custos adicionais se a infraestrutura de hardware precisar ser atualizada para oferecer suporte à versão mais recente do SharePoint ou se um farm secundário for necessário para a atualização.  <br/> |
|Os provedores de soluções podem ajudar no trabalho único de migrar seus dados para o SharePoint Online.  <br/> |Nem todas as alterações no SharePoint Online estão dentro do seu controle. Após a migração, as diferenças de design nos menus, bibliotecas e outros recursos podem afetar temporariamente a usabilidade.  <br/> |
|Os produtos online são atualizados automaticamente no sentido do serviço, embora os recursos possam ser substituídos, não há nenhum ciclo de vida de suporte real.  <br/> |Há um ciclo de vida de suporte para o SharePoint Server (ou SharePoint Foundation), bem como servidores SQL subjacentes.  <br/> |
   
Se você optou por criar um novo site do Microsoft 365 e migrar manualmente os dados para ele, conforme necessário, você pode examinar suas [Opções do Microsoft 365](https://www.microsoft.com/microsoft-365/).
  

  
### <a name="upgrade-sharepoint-server-on-premises"></a>Atualizar o SharePoint Server no local

A partir da versão mais recente do produto local do SharePoint (SharePoint Server 2019), as atualizações do SharePoint Server devem ir em  *série*, o que significa que não há nenhuma maneira de atualizar do sharepoint Server 2010 para o sharepoint Server 2016 ou para o SharePoint 2019, diretamente. 
  
Caminho de atualização serial: 

- SharePoint Server 2010 \> SharePoint server 2013 \> sharepoint Server 2016
   
Se você optar por seguir o caminho completo do SharePoint 2010 para o SharePoint Server 2016, isso levará tempo e planejamento. As atualizações envolvem um custo em termos de hardware atualizado (Lembre-se de que os SQL Servers também devem ser atualizados), software e administração. Além disso, as personalizações talvez precisem ser atualizadas ou até abandonadas. Verifique se você coleta anotações em todas as suas personalizações críticas antes de atualizar seu farm do SharePoint Server.
  
> [!NOTE]
> É possível manter seu farm de fim de suporte do SharePoint 2010, instalar um farm do SharePoint Server 2016 no novo hardware (para que os farms separados sejam executados lado a lado) e, em seguida, planejar e executar uma migração manual de conteúdo (para baixar e recarregar o conteúdo, por exemplo). Há possíveis armadilhas para essas movimentações manuais (como documentos vindos de 2010 com uma conta de última modificação atual com o alias da conta que está fazendo a movimentação manual) e algum trabalho deve ser feito com antecedência (recriando sites, subsites, permissões e estruturas de lista). É uma boa hora para considerar quais dados você pode mover para o armazenamento ou não são mais necessários. Isso pode reduzir o impacto da migração. De qualquer forma, limpe o ambiente antes da atualização. Certifique-se de que seu farm existente seja funcional antes da atualização e (tenha certeza) antes de encerrar! 
  
Lembre-se de revisar os **caminhos de atualização com e sem suporte**: 
  
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)
    
Se você tiver **personalizações**, é fundamental que você tenha um plano de atualização para cada etapa no caminho de migração: 
  
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)
    
|**Vantagem local**|**Desvantagem no local**|
|:-----|:-----|
|Controle total de todos os aspectos do farm do SharePoint (e do seu SQL), do hardware do servidor.  <br/> |Todas as interrupções e correções são responsabilidade de sua empresa (mas você pode entrar em contato com o suporte da Microsoft se o seu produto não estiver no fim do suporte):  <br/> |
|Conjunto de recursos completo do SharePoint Server no local com a opção para conectar seu farm local a uma assinatura do SharePoint Online via híbrido.  <br/> |Atualização, patches, correções de segurança, atualizações de hardware e todas as manutenções do SharePoint Server e do farm SQL são gerenciadas no local.  <br/> |
|Acesso completo para mais opções de personalização do que com o SharePoint Online.  <br/> |As [ofertas de conformidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=843165) devem ser configuradas manualmente no local.  <br/> |
|Teste de segurança e ajuste de desempenho do servidor, realizado em seu local (sob seu controle).  <br/> |O Microsoft 365 pode tornar recursos disponíveis para o SharePoint Online que não interoperem com o SharePoint Server local  <br/> |
|Os provedores de soluções podem ajudar na migração de dados para a próxima versão do SharePoint Server (e posteriores).  <br/> |Seus sites do SharePoint Server não usarão automaticamente certificados [SSL/TLS](https://go.microsoft.com/fwlink/?linkid=843167) como é visto no SharePoint Online.  <br/> |
|Controle total de convenções de nomenclatura, backup e restauração e outras opções de recuperação no SharePoint Server local.  <br/> |O SharePoint Server local é sensível aos ciclos de vida do produto.  <br/> |
   
### <a name="upgrade-resources"></a>Recursos de atualização

Comece comparando os requisitos de hardware e software. Se você não atender aos requisitos básicos da atualização no hardware atual, isso pode significar que você precisa atualizar o hardware no farm ou servidores SQL primeiro ou que você possa decidir mover algumas porcentagens dos seus sites para o hardware "verde" do SharePoint Online. Depois de fazer a avaliação, siga os caminhos e os métodos de atualização com suporte.
  
- **Requisitos de hardware/software para**: 
    
    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)
    
- Limites **e limites de software para**: 
    
    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)
    
- **A visão geral do processo de atualização para**: 
    
    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-sharepoint-server-on-premises"></a>Criar uma solução híbrida do SharePoint entre o SharePoint Online e o SharePoint Server no local

Outra opção (uma que pode ser a melhor dos mundos locais e online para algumas necessidades de migração) é híbrida, você pode conectar farms do SharePoint Server 2013 ou 2016 ou 2019 ao SharePoint Online para criar um SharePoint híbrido: [saiba mais sobre as soluções híbridas do SharePoint](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx).
  
Se você decidir que um farm híbrido do SharePoint Server é sua meta de migração, não deixe de planejar quais sites e usuários devem ser movidos para o online e quais precisam permanecer no local. Uma revisão e classificação do conteúdo do seu farm do SharePoint Server (determinando quais dados é alto, médio ou baixo impacto em sua empresa) pode ser útil para tomar essa decisão. Pode ser que a única coisa que você precisa compartilhar com o SharePoint Online seja (a) contas de usuário para logon e (b) o índice de pesquisa do SharePoint Server – isso pode não ser claro até que você veja como seus sites são usados. Se sua empresa mais tarde decidir migrar todo o conteúdo para o SharePoint Online, você poderá mover todas as contas e dados restantes online e descomissionar o farm local, e o gerenciamento/administração do farm do SharePoint será feito através dos consoles do Microsoft 365 a partir desse ponto em diante.
  
Familiarize-se com os tipos existentes de híbridos e como configurar a conexão entre seu farm local do SharePoint e sua assinatura do Microsoft 365.

| Opção | Descrição |
|:-----|:-----|
|[Ofertas de conformidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=843165).  <br/> |A assistência do [FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) para migração é limitada.  <br/> Grande parte da atualização será manual ou por meio da API de migração do SPO descrita no [mapa de conteúdo de migração do SharePoint Online e do onedrive](https://go.microsoft.com/fwlink/?linkid=843184).  <br/> |
|Os engenheiros de suporte da Microsoft e os funcionários do datacenter têm acesso administrativo irrestrito à sua assinatura.  <br/> |Poderá haver custos adicionais se a infraestrutura de hardware precisar ser atualizada para oferecer suporte à versão mais recente do SharePoint ou se um farm secundário for necessário para a atualização.  <br/> |
|Os parceiros podem ajudar no trabalho único de migrar seus dados para o SharePoint Online.  <br/> ||
|Os produtos online são atualizados automaticamente no sentido do serviço, embora os recursos possam ser substituídos, não há nenhum verdadeiro suporte.  <br/> ||
   
Se você optou por criar um novo site do Microsoft 365 e migrar manualmente os dados para ele, conforme necessário, você pode examinar suas [Opções do Microsoft 365](https://www.microsoft.com/microsoft-365/).
  
### <a name="upgrade-sharepoint-server-on-premises"></a>Atualizar o SharePoint Server no local

Há uma maneira histórica de ignorar versões em atualizações do SharePoint, pelo menos no lançamento do SharePoint Server 2016. Isso significa que as atualizações entram em série:
  
- SharePoint 2007 SharePoint \> server 2010 \> sharepoint Server 2013 \> SharePoint Server 2016
   
Para obter todo o caminho do SharePoint 2007 para o SharePoint Server 2016 significa um investimento significativo de tempo e envolverá um custo em termos de hardware atualizado (Lembre-se de que os SQL Servers também devem ser atualizados), software e administração. As personalizações deverão ser atualizadas ou abandonadas, de acordo com a criticalidade do recurso.
  
> [!NOTE]
> É possível manter seu farm do SharePoint 2007 de fim de vida, instalar um farm do SharePoint Server 2016 no novo hardware (para que os farms separados sejam executados lado a lado) e, em seguida, planejar e executar uma migração manual de conteúdo (para baixar e recarregar o conteúdo, por exemplo). Esteja ciente de algumas das armadilhas das movimentações manuais (como movimentações de documentos que substituem a última conta modificada pelo alias da conta que está fazendo a movimentação manual) e o trabalho que deve ser feito com antecedência (como recriação de sites, subsites, permissões e estruturas de lista). Novamente, esse é o momento para considerar quais dados você pode mover para o armazenamento ou não precisam mais de uma ação que possa reduzir o impacto da migração.
  
De qualquer forma, limpe o ambiente antes da atualização. Certifique-se de que seu farm existente seja funcional antes da atualização e (tenha certeza) antes de encerrar! 
  
Lembre-se de revisar os **caminhos de atualização com e sem suporte**: 
  
- 
  [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)
    
Se você tiver **personalizações**, é fundamental que você tenha um plano de atualização para cada etapa no caminho de migração: 
  
- [SharePoint 2007](https://go.microsoft.com/fwlink/?linkid=843158)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)
    
|**Pro local**|**Con on-premises**|
|:-----|:-----|
|Controle total de todos os aspectos do farm do SharePoint, do hardware do servidor.  <br/> |Todas as interrupções e correções são responsabilidade de sua empresa (pode envolver o suporte da Microsoft se o seu produto não estiver no fim do suporte):  <br/> |
|Conjunto de recursos completo do SharePoint Server no local com a opção para conectar seu farm local a uma assinatura do SharePoint Online via híbrido.  <br/> |Atualização, patches, correções de segurança e toda a manutenção do SharePoint Server gerenciado no local.  <br/> |
|Acesso total para maior personalização.  <br/> |As [ofertas de conformidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=843165) devem ser configuradas manualmente no local.  <br/> |
|Teste de segurança e ajuste de desempenho do servidor, realizado em seu local (está sob seu controle).  <br/> |O Microsoft 365 pode tornar recursos disponíveis para o SharePoint Online que não interoperem com o SharePoint Server local  <br/> |
|Os parceiros podem ajudar na migração de dados para a próxima versão do SharePoint Server (e posteriores).  <br/> |Seus sites do SharePoint Server não usarão automaticamente certificados [SSL/TLS](https://go.microsoft.com/fwlink/?linkid=843167) como é visto no SharePoint Online.  <br/> |
|Controle total de convenções de nomenclatura, backup e restauração e outras opções de recuperação no SharePoint Server local.  <br/> |O SharePoint Server local é sensível aos ciclos de vida do produto.  <br/> |
   
### <a name="upgrade-resources"></a>Recursos de atualização

Comece sabendo que você atende aos requisitos de hardware e software e siga os métodos de atualização com suporte.
  
- **Requisitos de hardware/software para**: 
    
    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)
    
- Limites **e limites de software para**: 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843245)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)
    
- **A visão geral do processo de atualização para**: 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843250)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Criar uma solução híbrida do SharePoint entre o SharePoint Online e o local

Se a resposta para suas necessidades de migração estiver em algum lugar entre o autocontrole oferecido pelo local e o menor custo de propriedade oferecido pelo SharePoint Online, você poderá conectar farms do SharePoint Server 2013 ou 2016 ao SharePoint Online, através de híbridos. [Saiba mais sobre as soluções híbridas do SharePoint](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
  
Se você decidir que um farm híbrido do SharePoint Server se beneficiará da sua empresa, familiarize-se com os tipos existentes de híbrido e como configurar a conexão entre seu farm do SharePoint local e sua assinatura do Microsoft 365.
  
Uma boa maneira de ver como isso funciona criando um ambiente de desenvolvimento/teste do Microsoft 365, que pode ser configurado com os [guias de laboratório de teste](m365-enterprise-test-lab-guides.md). Depois de fazer uma assinatura de avaliação ou comprada da Microsoft 365, você estará prestes a criar os conjuntos de sites, as Webs e as bibliotecas de documentos no SharePoint Online para os quais você pode migrar dados (seja manualmente, usando a API de migração ou-se quiser migrar o conteúdo do meu site para o OneDrive for Business por meio do assistente híbrido).
  
> [!NOTE]
> Lembre-se de que seu farm do SharePoint Server 2010 primeiro precisará ser atualizado, no local, para o SharePoint Server 2013 ou o SharePoint Server 2016 para usar a opção híbrida. O SharePoint Foundation 2010 e o SharePoint Foundation 2013 não podem criar conexões híbridas com o SharePoint Online. 

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Resumo das opções de cliente e servidores do Office 2010 e do Windows 7

Para obter um resumo visual das opções de atualização, migração e mover para nuvem para clientes e servidores do Office 2010 e Windows 7, confira o [pôster sobre o fim do suporte](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Imagem do pôster sobre o fim do suporte para clientes e servidores do Office 2010 e do Windows 7](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Este pôster de uma página é uma maneira rápida de entender os vários caminhos que podem ser tomados para impedir que os produtos de cliente e servidor do Office 2010 e o Windows 7 cheguem ao final do suporte, com destaque para os caminhos preferenciais e o suporte de opções no Microsoft 365 Enterprise.

Você também pode [baixar](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf)esse pôster e imprimir em formatos de carta, oficial ou tablóide (11x17).
        
## <a name="related-topics"></a>Tópicos relacionados

[Recursos para ajudá-lo a atualizar do Office 2007 ou 2010 servidores e clientes](upgrade-from-office-2010-servers-and-products.md)
  
[Overview of the upgrade process from SharePoint 2010 to SharePoint 2013](https://technet.microsoft.com/library/mt493301%28v=office.16%29.aspx)
  
[Práticas recomendadas para atualização do SharePoint 2010 para o SharePoint 2013](https://technet.microsoft.com/library/mt493305%28v=office.16%29.aspx)
  
[Resolver problemas de atualização do banco de dados no SharePoint 2013](https://go.microsoft.com/fwlink/?linkid=843195)
  
[Procurar provedores de solução da Microsoft para ajudá-lo com a atualização](https://go.microsoft.com/fwlink/?linkid=841249)
  
[Política atualizada de manutenção do produto para SharePoint Server 2013](https://technet.microsoft.com/library/mt493253%28v=office.16%29.aspx)
  
[Política atualizada de manutenção do produto para SharePoint Server 2016](https://technet.microsoft.com/library/mt782882%28v=office.16%29.aspx)
  

