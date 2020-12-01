---
title: Roteiro de fim do suporte do SharePoint Server 2007
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 01/28/2019
audience: ITPro
ms.topic: conceptual
f1.keywords:
- CSH
ms.custom:
- vsemail
- MS_WSS_DirectoryManagement
- MS_WSS_ConfigEmail
- globalemailconfig
- configssc
- AppDefToBDC
- seo-marvel-apr2020
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- OFU120
- SPS150
- OSU140
- WSU120
- OSR120
- SPO160
- PJW120
- SPB160
- OSI150
- OSI160
- BSA160
- OSU160
ms.assetid: ba124775-d5c0-4d68-b88d-8458ad4c3717
description: O suporte para o SharePoint Server 2007 terminou em outubro de 2017. Neste artigo, saiba mais sobre suas opções de atualização, migração e suporte.
ms.openlocfilehash: aa09669d1c7b90f70e6c136a85d06ef2a516e4b5
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519629"
---
# <a name="sharepoint-server-2007-end-of-support-roadmap"></a>Roteiro de fim do suporte do SharePoint Server 2007

*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*

Em **10 de outubro de 2017**, o Microsoft Office SharePoint Server 2007 atingiu o fim do suporte. Se você não tiver migrado do SharePoint Server 2007 para a Microsoft 365 ou uma versão mais recente do SharePoint Server local, agora é hora de começar a planejar. Este artigo fornece recursos para ajudá-lo a migrar dados para o SharePoint Online ou atualizar seu SharePoint Server local.
  
## <a name="what-does-end-of-support-mean"></a>O que significa o *fim do suporte* ?

O SharePoint Server, como a maioria dos produtos da Microsoft, tem um ciclo de vida de suporte, durante o qual a Microsoft oferece novos recursos, correções de erros, correções de segurança e assim por diante. Esse ciclo de vida normalmente dura 10 anos da versão inicial do produto. O final desse ciclo de vida é conhecido como o fim do suporte do produto. Após o fim do suporte, a Microsoft não fornece mais:
  
- Suporte técnico para problemas que podem ocorrer.
    
- Correções de erros que podem afetar a estabilidade e a usabilidade do servidor.
    
- Correções de segurança para vulnerabilidades que podem tornar o servidor vulnerável a brechas de segurança.
    
- Atualizações de fuso horário.
    
Seu farm do SharePoint Server 2007 ainda estará operacional após 10 de outubro de 2017, mas nenhuma outra atualização, patch ou correção será lançada para o produto, incluindo patches de segurança/correções. O suporte da Microsoft intermoveu completamente seus esforços de suporte para versões mais recentes do produto. Como sua instalação não é mais suportada ou corrigida, você deve atualizar o produto ou migrar dados importantes.
  
> [!TIP]
> Se você ainda não tiver planejado a atualização ou a migração, confira: [Opções de migração do SharePoint 2007 para considerar](sharepoint-2007-migration-options.md) alguns exemplos de onde começar. Você também pode procurar [parceiros da Microsoft](https://go.microsoft.com/fwlink/?linkid=841249) que podem ajudar com a atualização ou com a migração do Microsoft 365 (ou ambos).
  
Para obter mais informações sobre os servidores do Office 2007 e o fim do suporte, consulte [recursos para ajudá-lo a atualizar de clientes e servidores do office 2007](upgrade-from-office-2007-servers-and-products.md).
  
## <a name="what-are-my-options"></a>Quais são as minhas opções?

Sua primeira parada deve ser o [site de ciclo de vida do produto](https://go.microsoft.com/fwlink/?linkid=843148). Se você tiver um produto da Microsoft local de duração, verifique o fim da data de suporte para ter um ano ou para agendar uma atualização ou migração. Ao escolher a próxima etapa, considere quais recursos do produto seriam bons o suficiente, melhor e melhor. Exemplo: 
  
|**Good**|**Melhor**|**Melhor**|
|:-----|:-----|:-----|
|SharePoint Server 2010  <br/> |SharePoint Server 2013  <br/> |SharePoint Online  <br/> |
||SharePoint Híbrido  <br/> |SharePoint Server 2016  <br/> |
| | |SharePoint Híbrido  <br/> |
   
Se você escolher uma opção "boa o suficiente", logo precisará começar a planejar outra atualização após a conclusão da migração do SharePoint Server 2007. 

>[!NOTE] 
>As datas de fim de suporte estão sujeitas a alterações. Verifique o [site do ciclo de vida do produto](https://support.microsoft.com/lifecycle).
  
## <a name="where-can-i-go-next"></a>O que devo fazer em seguida?

O SharePoint Server pode ser instalado no local em seus próprios servidores. Ou você pode usar o SharePoint Online, que é um serviço online que faz parte do Microsoft 365. Suas opções são:
  
- Migrar para o SharePoint Online.
    
- Atualize o SharePoint Server no local.
    
- Execute ambas as opções acima.
    
- Implementar uma solução [híbrida do SharePoint](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx) .
    
Esteja ciente dos custos ocultos associados à manutenção de um farm de servidores, manutenção ou migração de personalizações e atualização do hardware que o SharePoint Server precisa. Ter um farm do SharePoint Server local é gratificante, se necessário. Mas se você executar o farm em servidores herdados do SharePoint sem muita personalização, poderá se beneficiar da migração para o SharePoint Online.
  
> [!IMPORTANT]
> Há outra opção se o conteúdo no SharePoint 2007 é usado com frequência. Alguns administradores do SharePoint optam por criar uma assinatura do Microsoft 365, configurar um novo site do SharePoint Online e, em seguida, cortar do SharePoint 2007 de forma limpa, levando apenas documentos essenciais aos novos sites do SharePoint Online. Os dados podem ser descarregados do site do SharePoint 2007 para arquivos mortos. Considere como seus usuários trabalham com dados da sua instalação do SharePoint 2007. Pode haver maneiras criativas de gerenciar suas necessidades.
  
|**SharePoint Online (SPO)**|**SharePoint Server local**|
|:-----|:-----|
|Alto custo no tempo (planejamento/execução/verificação)  <br/> |Alto custo no tempo (planejamento/execução/verificação)  <br/> |
|Menor custo em fundos (sem compras de hardware)  <br/> |Custo maior em fundos (hardware + desenvolvedores/administradores)  <br/> |
|Custo único em migração  <br/> |Custo de um único tempo repetido por migração futura  <br/> |
|Baixo custo total de propriedade/manutenção  <br/> |Alto custo total de propriedade/manutenção  <br/> |
   
Quando você migrar para o Microsoft 365, a movimentação única terá um custo mais pesado em frente, enquanto você organiza os dados e decide o que levar para a nuvem e o que deixar atrás. Mas futuras atualizações serão automáticas, e você não precisará mais gerenciar atualizações de hardware e de software. Além disso, o tempo de backup do farm será feito por um contrato de nível de serviço ([SLA](https://go.microsoft.com/fwlink/?linkid=843153)) da Microsoft.
  
### <a name="migrate-to-sharepoint-online"></a>Migrar para o SharePoint Online

Verifique se o SharePoint Online tem todos os recursos necessários. Confira as [descrições de serviço do Microsoft 365 e do Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library).
  
Não é possível migrar diretamente do SharePoint 2007 para o SharePoint Online. A mudança para o SharePoint Online seria feita manualmente. Se você atualizar para o SharePoint Server 2013 ou o SharePoint Server 2016, você poderá usar a API de migração do SharePoint (para migrar informações para o OneDrive for Business, por exemplo).
  
|**Pro online**|**Con online**|
|:-----|:-----|
|A Microsoft fornece hardware SPO e toda a administração de hardware.  <br/> |Os recursos disponíveis podem diferir entre o SharePoint Server local e o SPO.  <br/> |
|Você é o administrador global da sua assinatura e pode atribuir administradores a sites do SPO.  <br/> |Algumas ações disponíveis para um administrador de farm no SharePoint Server local não existem ou não estão necessariamente incluídas na função de administrador do SharePoint no Microsoft 365.  <br/> |
|A Microsoft aplica patches, correções e atualizações para o hardware e software subjacentes. <br/> |Como não há acesso ao sistema de arquivos subjacente no serviço, a personalização é limitada.  <br/> |
|A Microsoft publica [contratos de nível de serviço](https://go.microsoft.com/fwlink/?linkid=843153) e se move rapidamente para resolver incidentes de nível de serviço. <br/> |O backup e a restauração e outras opções de recuperação são automatizados pelo serviço no SharePoint Online. Os backups são substituídos se não forem usados. <br/> |
|O teste de segurança e o ajuste de desempenho do servidor são realizados continuamente no serviço da Microsoft. <br/> |As alterações na interface do usuário e em outros recursos do SharePoint são instaladas pelo serviço e podem precisar ser ativadas ou desativadas. <br/> |
|A Microsoft 365 atende a vários padrões da indústria: [ofertas de conformidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=843165).  <br/> |A assistência do [FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) para migração é limitada.  <br/> Grande parte da atualização será manual ou por meio da API de migração do SPO descrita no [mapa de conteúdo de migração do SharePoint Online e do onedrive](https://go.microsoft.com/fwlink/?linkid=843184).  <br/> |
|Os engenheiros de suporte da Microsoft e os funcionários de datacenter não têm acesso administrativo irrestrito à sua assinatura. <br/> |Poderá haver custos adicionais se o hardware precisar ser atualizado para suportar a versão mais recente do SharePoint ou se um farm secundário for necessário para a atualização.  <br/> |
|Os parceiros podem ajudar no trabalho único de migrar seus dados para o SharePoint Online.  <br/> ||
|Os produtos online são atualizados automaticamente. Embora os recursos possam ser substituídos, não há um verdadeiro fim de suporte. <br/> ||
   
Se você optou por criar um novo site do Microsoft 365 e migrar manualmente os dados necessários para ele, verifique suas [Opções do Microsoft 365](https://www.microsoft.com/microsoft-365/).
  
### <a name="upgrade-sharepoint-server-on-premises"></a>Atualizar o SharePoint Server no local

Não há uma maneira de ignorar versões em atualizações do SharePoint. As atualizações entram em série:
  
- SharePoint 2007 SharePoint \> server 2010 \> sharepoint Server 2013 \> SharePoint Server 2016
   
Para ir do SharePoint 2007 para o SharePoint Server 2016 significa um investimento significativo de tempo e envolverá custos no hardware (os servidores SQL também devem ser atualizados), software e administração. As personalizações deverão ser atualizadas ou abandonadas.
  
> [!NOTE]
> É possível manter seu farm do SharePoint 2007 de fim de vida, instalar um farm do SharePoint Server 2016 no novo hardware (para que os farms separados sejam executados lado a lado) e, em seguida, planejar e executar uma migração manual de conteúdo (para baixar e recarregar o conteúdo, por exemplo). Mas cuidado com algumas das armadilhas de movimentações manuais, como movimentações de documentos que substituem a conta de última modificação pelo alias da conta que está fazendo a movimentação manual. Considere também o trabalho que deve ser feito antes do tempo, como recriação de sites, subsites, permissões e estruturas de lista. Considere antecipadamente quais dados você pode mover para o armazenamento ou excluir para reduzir o impacto da migração.
  
É importante limpar o ambiente antes de atualizar. Certifique-se de que seu farm existente é funcional antes da atualização e certamente antes de encerrar!
  
Lembre-se de revisar os *caminhos de atualização com e sem suporte*: 
  
- 
  [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)
    
Se você tiver personalizações, é fundamental ter um plano para cada etapa no caminho de migração: 
  
- [SharePoint 2007](https://go.microsoft.com/fwlink/?linkid=843158)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)
    
|**Pro local**|**Con on-premises**|
|:-----|:-----|
|Controle total de todos os aspectos do farm do SharePoint, do hardware do servidor.  <br/> |Todas as interrupções e correções são de responsabilidade da sua empresa (você pode entrar em contato com o suporte da Microsoft, caso o seu produto não tenha passado para o fim do suporte).  <br/> |
|Conjunto de recursos completo do SharePoint Server no local com a opção para conectar seu farm local a uma assinatura do SharePoint Online via híbrido.  <br/> |Atualização, patches, correções de segurança e toda a manutenção do SharePoint Server gerenciado no local.  <br/> |
|Acesso total para maior personalização.  <br/> |As [ofertas de conformidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=843165) devem ser configuradas manualmente no local.  <br/> |
|O teste de segurança e o ajuste de desempenho do servidor são realizados em seu local (sob seu controle).  <br/> |O Microsoft 365 pode disponibilizar recursos para o SharePoint Online que não interoperem com o SharePoint Server local.  <br/> |
|Os parceiros podem ajudar na migração de dados para a próxima versão do SharePoint Server (e posteriores).  <br/> |Seus sites do SharePoint Server não usarão automaticamente certificados [SSL/TLS](https://go.microsoft.com/fwlink/?linkid=843167) como é visto no SharePoint Online.  <br/> |
|Controle total de convenções de nomenclatura, backup e restauração e outras opções de recuperação no SharePoint Server local.  <br/> |O SharePoint Server local é sensível aos ciclos de vida do produto.  <br/> |
   
### <a name="upgrade-resources"></a>Recursos de atualização

Verifique se o ambiente atende aos requisitos de hardware e software e siga os métodos de atualização com suporte.
  
- **Requisitos de hardware/software para**: 
    
    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)
    
- Limites **e limites de software para**: 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843245)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)
    
- **A visão geral do processo de atualização para**: 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843250)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Criar uma solução híbrida do SharePoint entre o SharePoint Online e o local

Se a resposta para suas necessidades de migração estiver em algum lugar entre o autocontrole oferecido pelo local e o menor custo de propriedade oferecido pelo SharePoint Online, você poderá conectar farms do SharePoint Server 2013 ou 2016 ao SharePoint Online por meio de híbridos. [Saiba mais sobre as soluções híbridas do SharePoint](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx).
  
Se você decidir que um farm híbrido do SharePoint Server beneficiará sua empresa, familiarize-se com os tipos existentes de híbridos e como configurar a conexão entre seu farm do SharePoint local e sua assinatura do Microsoft 365.
  
| Opção | Descrição |
|:-----|:-----|
[Ofertas de conformidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=843165)  <br/> |A assistência do [FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) para migração é limitada.  <br/> Grande parte da atualização será manual ou por meio da API de migração do SPO descrita no [mapa de conteúdo de migração do SharePoint Online e do onedrive](https://go.microsoft.com/fwlink/?linkid=843184).  <br/> |
|Os engenheiros de suporte da Microsoft e os funcionários do Data Center não têm acesso administrativo irrestrito à sua assinatura.<br/> |Poderá haver custos adicionais se a infraestrutura de hardware precisar ser atualizada para oferecer suporte à versão mais recente do SharePoint ou se um farm secundário for necessário para a atualização.  <br/> |
|Os parceiros podem ajudar no trabalho único de migrar seus dados para o SharePoint Online.  <br/> ||
|Os produtos online são atualizados automaticamente no serviço. Embora os recursos possam ser substituídos, não há um verdadeiro fim de suporte.<br/> ||
   
Se você optou por criar um novo site do Microsoft 365 e migrar manualmente os dados necessários para ele, verifique suas [Opções do Microsoft 365](https://www.microsoft.com/microsoft-365/).
  
### <a name="upgrade-sharepoint-server-on-premises"></a>Atualizar o SharePoint Server no local

Não há uma maneira de ignorar versões em atualizações do SharePoint. As atualizações entram em série:
  
- SharePoint 2007 SharePoint \> server 2010 \> sharepoint Server 2013 \> SharePoint Server 2016
   
Para ir do SharePoint 2007 para o SharePoint Server 2016 significa um investimento significativo de tempo e envolverá os custos de hardware (os servidores SQL também devem ser atualizados), de software e de administração. As personalizações deverão ser atualizadas ou abandonadas.
  
> [!NOTE]
> É possível manter seu farm do SharePoint 2007 de fim de vida, instalar um farm do SharePoint Server 2016 no novo hardware (para que os farms separados sejam executados lado a lado) e, em seguida, planejar e executar uma migração manual de conteúdo (para baixar e recarregar o conteúdo, por exemplo). Mas cuidado com possíveis armadilhas de movimentações manuais, como movimentações de documentos que substituem a conta de última modificação pelo alias da conta que está fazendo a movimentação manual e o trabalho que deve ser feito com antecedência, como recriação de sites, subsites, permissões e estruturas de lista. Considere quais dados você pode mover para o armazenamento ou excluir para reduzir o impacto da migração.
  
Limpe o ambiente antes da atualização. Certifique-se de que seu farm existente é funcional antes de atualizar e certamente antes de encerrar! 
  
Lembre-se de revisar os *caminhos de atualização com e sem suporte*: 
  
- 
  [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)
    
Se você tiver *personalizações*, é fundamental que você tenha um plano de atualização para cada etapa no caminho de migração: 
  
- [SharePoint 2007](https://go.microsoft.com/fwlink/?linkid=843158)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)
    
|**Pro local**|**Con on-premises**|
|:-----|:-----|
|Controle total de todos os aspectos do farm do SharePoint, do hardware do servidor.  <br/> |Todas as interrupções e correções são responsabilidade de sua empresa. (Você pode entrar em contato com o suporte da Microsoft se o seu produto não ultrapassar o fim do suporte.)  <br/> |
|Conjunto de recursos completo do SharePoint Server no local com a opção para conectar seu farm local a uma assinatura do SharePoint Online via híbrido.  <br/> |Atualização, patches, correções de segurança e toda a manutenção do SharePoint Server gerenciado no local.  <br/> |
|Acesso total para maior personalização.  <br/> |As [ofertas de conformidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=843165) devem ser configuradas manualmente no local.  <br/> |
|O teste de segurança e o ajuste de desempenho do servidor são realizados em seu local sob o seu controle.  <br/> |O Microsoft 365 pode tornar recursos disponíveis para o SharePoint Online que não interoperem com o SharePoint Server local  <br/> |
|Os parceiros podem ajudar a migrar dados para a próxima versão do SharePoint Server (e posteriores).  <br/> |Seus sites do SharePoint Server não usarão automaticamente certificados [SSL/TLS](https://go.microsoft.com/fwlink/?linkid=843167) como é visto no SharePoint Online.  <br/> |
|Controle total de convenções de nomenclatura, backup e restauração e outras opções de recuperação no SharePoint Server local.  <br/> |O SharePoint Server local é sensível aos ciclos de vida do produto.  <br/> |
   
### <a name="upgrade-resources"></a>Recursos de atualização

Verifique se o ambiente atende aos requisitos de hardware e software. Siga os métodos de atualização com suporte.
  
- **Requisitos de hardware/software para:** 
    
    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)
    
- **Limites e limites de software para:** 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843245)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)
    
- **A visão geral do processo de atualização para:** 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843250)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Criar uma solução híbrida do SharePoint entre o SharePoint Online e o local

Se a resposta para suas necessidades de migração estiver em algum lugar entre o autocontrole oferecido pelo local e o menor custo de propriedade oferecido pelo SharePoint Online, você poderá conectar farms do SharePoint Server 2013 ou 2016 ao SharePoint Online por meio de híbridos. [Saiba mais sobre as soluções híbridas do SharePoint](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
  
Se você decidir que um farm híbrido do SharePoint Server beneficiará sua empresa, familiarize-se com os tipos existentes de híbridos e como configurar a conexão entre seu farm do SharePoint local e sua assinatura do Microsoft 365.
  
Uma boa maneira de ver como isso funciona é criar um ambiente de desenvolvimento/teste do Microsoft 365, que pode ser configurado com os [guias de laboratório de teste](m365-enterprise-test-lab-guides.md). Após obter uma assinatura de avaliação ou comprada da Microsoft 365, você pode criar os conjuntos de sites, Webs e bibliotecas de documentos no SharePoint Online para os quais você pode migrar dados. Você pode migrar manualmente, usando a API de migração ou, se quiser migrar o conteúdo do meu site para o OneDrive for Business, por meio do assistente híbrido.
  
> [!NOTE]
> Lembre-se de que para usar a opção híbrida, seu farm do SharePoint 2007 precisará ser atualizado, no local, para o SharePoint Server 2013 ou o SharePoint Server 2016.
  
## <a name="related-topics"></a>Tópicos relacionados

[Solução de problemas e retomar a atualização (Office SharePoint Server 2007)](https://go.microsoft.com/fwlink/?linkid=843192)
  
[Solucionar problemas de atualização (SharePoint Server 2010)](https://go.microsoft.com/fwlink/?linkid=843194)
  
[Resolver problemas de atualização do banco de dados no SharePoint 2013](https://go.microsoft.com/fwlink/?linkid=843195)
  
[Procurar parceiros da Microsoft para ajudar com a atualização](https://go.microsoft.com/fwlink/?linkid=841249)
  
[Recursos para ajudá-lo a atualizar de clientes e servidores do Office 2007](upgrade-from-office-2007-servers-and-products.md)
  
