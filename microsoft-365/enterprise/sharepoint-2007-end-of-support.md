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
ms.openlocfilehash: 224b0af90d6a314aa15a2c0dab7b60626e5abde8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924863"
---
# <a name="sharepoint-server-2007-end-of-support-roadmap"></a>Roteiro de fim do suporte do SharePoint Server 2007

*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*

Em **10 de outubro de 2017,** Microsoft Office SharePoint Server 2007 atingiu o fim do suporte. Se você não tiver migrado do SharePoint Server 2007 para o Microsoft 365 ou uma versão mais recente do SharePoint Server local, agora é a hora de começar a planejar. Este artigo fornece recursos para ajudá-lo a migrar dados para o SharePoint Online ou atualizar seu SharePoint Server local.
  
## <a name="what-does-end-of-support-mean"></a>O que *significa o fim do suporte?*

O SharePoint Server, como a maioria dos produtos Microsoft, tem um ciclo de vida de suporte, durante o qual a Microsoft fornece novos recursos, correções de bugs, correções de segurança e assim por diante. Esse ciclo de vida geralmente dura 10 anos a partir da versão inicial do produto. O final desse ciclo de vida é conhecido como o fim do suporte do produto. Após o fim do suporte, a Microsoft não fornece mais:
  
- Suporte técnico para problemas que podem ocorrer.
    
- Correções de bugs para problemas que podem afetar a estabilidade e a usabilidade do servidor.
    
- Correções de segurança para vulnerabilidades que podem tornar o servidor vulnerável a violações de segurança.
    
- Atualizações de fuso horário.
    
Seu farm do SharePoint Server 2007 ainda estará operacional após 10 de outubro de 2017, mas nenhuma nova atualização, patches ou correções será lançada para o produto, incluindo correções/correções de segurança. O Suporte da Microsoft mudou totalmente seus esforços de suporte para versões mais recentes do produto. Como sua instalação não é mais suportada ou corrigida, você deve atualizar o produto ou migrar dados importantes.
  
> [!TIP]
> Se você ainda não planejou a atualização ou a migração, consulte: Opções de migração do [SharePoint 2007](sharepoint-2007-migration-options.md) a considerar para alguns exemplos de por onde começar. Você também pode pesquisar parceiros [da Microsoft que](https://go.microsoft.com/fwlink/?linkid=841249) podem ajudar na atualização ou na migração do Microsoft 365 (ou ambos).
  
Para obter mais informações sobre servidores do Office 2007 e o final do suporte, consulte Recursos para ajudá-lo a atualizar dos servidores e clientes [do Office 2007.](upgrade-from-office-2007-servers-and-products.md)
  
## <a name="what-are-my-options"></a>Quais são minhas opções?

Sua primeira parada deve ser o [site ciclo de vida do produto.](/lifecycle/products/?alpha=Microsoft+Office+SharePoint+Server+2007) Se você tiver um produto da Microsoft local que está envelhando, verifique a data de término do suporte para que você tenha um ano ou mais para agendar uma atualização ou migração. Ao escolher a próxima etapa, considere quais recursos do produto seriam bons o suficiente, melhores e melhores. Exemplo: 
  
|**Good**|**Melhor**|**Melhor**|
|:-----|:-----|:-----|
|SharePoint Server 2010  <br/> |SharePoint Server 2013  <br/> |SharePoint Online  <br/> |
||Microsoft Office SharePoint Online Híbrido  <br/> |SharePoint Server 2016  <br/> |
| | |Microsoft Office SharePoint Online Híbrido  <br/> |
   
Se você escolher uma opção "boa o suficiente", em breve precisará começar a planejar outra atualização após a migração do SharePoint Server 2007 ser concluída. 

>[!NOTE] 
>As datas de fim de suporte estão sujeitas a alterações. Verifique o [site ciclo de vida do produto](https://support.microsoft.com/lifecycle).
  
## <a name="where-can-i-go-next"></a>O que devo fazer em seguida?

O SharePoint Server pode ser instalado no local em seus próprios servidores. Ou você pode usar o SharePoint Online, que é um serviço online que faz parte do Microsoft 365. Suas opções são:
  
- Migrar para o SharePoint Online.
    
- Atualize o SharePoint Server local.
    
- Faça as duas coisas acima.
    
- Implementar uma [solução híbrida do SharePoint.](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
    
Esteja ciente dos custos ocultos associados à manutenção de um farm de servidores, manutenção ou migração de personalizações e atualização do hardware que o SharePoint Server precisa. Ter um farm local do SharePoint Server é recompensador, se necessário. Mas se você executar seu farm em Servidores do SharePoint herdados sem personalização pesada, poderá se beneficiar da migração para o SharePoint Online.
  
> [!IMPORTANT]
> Há outra opção se o conteúdo no SharePoint 2007 for usado com pouca freqüência. Alguns administradores do SharePoint optam por criar uma assinatura do Microsoft 365, configurar um novo site do SharePoint Online e, em seguida, cortar do SharePoint 2007 de forma limpa, levando apenas documentos essenciais para os novos sites do SharePoint Online. Em seguida, os dados podem ser drenados do site do SharePoint 2007 para arquivos. Considere como seus usuários trabalham com dados da instalação do SharePoint 2007. Pode haver maneiras criativas de gerenciar suas necessidades.
  
|**SharePoint Online (SPO)**|**SharePoint Server local**|
|:-----|:-----|
|Alto custo no tempo (plano/execução/verificação)  <br/> |Alto custo no tempo (plano/execução/verificação)  <br/> |
|Menor custo em fundos (sem compras de hardware)  <br/> |Maior custo em fundos (hardware + devs/administradores)  <br/> |
|Custo único na migração  <br/> |Custo único repetido por migração futura  <br/> |
|Baixo custo total de propriedade/manutenção  <br/> |Alto custo total de propriedade/manutenção  <br/> |
   
Ao migrar para o Microsoft 365, a movimentação única terá um custo mais alto antes, enquanto você organiza os dados e decide o que levar para a nuvem e o que deixar para trás. Mas as atualizações futuras serão automáticas e você não precisará mais gerenciar atualizações de hardware e software. Além disso, o tempo de atualização do seu farm será respaldado por um Contrato de Nível de Serviço da Microsoft ([SLA](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement)).
  
### <a name="migrate-to-sharepoint-online"></a>Migrar para o SharePoint Online

Certifique-se de que o SharePoint Online tenha todos os recursos necessários. Consulte Descrições de serviço do [Microsoft 365 e do Office 365.](/office365/servicedescriptions/office-365-service-descriptions-technet-library)
  
Não é possível migrar diretamente do SharePoint 2007 para o SharePoint Online. Sua mudança para o SharePoint Online seria feita manualmente. Se você atualizar para SharePoint Server 2013 ou SharePoint Server 2016, poderá usar a API de Migração do SharePoint (para migrar informações para o OneDrive for Business, por exemplo).
  
|**Profissional online**|**Con online**|
|:-----|:-----|
|A Microsoft fornece hardware SPO e toda a administração de hardware.  <br/> |Os recursos disponíveis podem diferir entre o SharePoint Server local e o SPO.  <br/> |
|Você é o administrador global da sua assinatura e pode atribuir administradores a sites SPO.  <br/> |Algumas ações disponíveis para um administrador de farm no SharePoint Server local não existem ou não são necessariamente incluídas na função administrador do SharePoint no Microsoft 365.  <br/> |
|A Microsoft aplica patches, correções e atualizações a hardware e software subjacentes. <br/> |Como não há acesso ao sistema de arquivos subjacente no serviço, a personalização é limitada.  <br/> |
|A Microsoft [publica contratos de nível de serviço](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement) e se move rapidamente para resolver incidentes de nível de serviço. <br/> |Backup e restauração e outras opções de recuperação são automatizadas pelo serviço no SharePoint Online. Os backups são substituídos se não usados. <br/> |
|Os testes de segurança e o ajuste de desempenho do servidor são executados continuamente no serviço pela Microsoft. <br/> |As alterações na interface do usuário e outros recursos do SharePoint são instaladas pelo serviço e podem precisar ser alternadas ou desligadas. <br/> |
|O Microsoft 365 atende a vários padrões do setor: [ofertas de conformidade da Microsoft.](/compliance/regulatory/offering-home)  <br/> |[A assistência do FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) para migração é limitada.  <br/> Grande parte da atualização será manual ou por meio da API de Migração de SPO descrita no Roteiro de Conteúdo de Migração do SharePoint Online e [do OneDrive.](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets)  <br/> |
|Os engenheiros de suporte da Microsoft e funcionários do datacenter não terão acesso de administrador irrestrito à sua assinatura. <br/> |Pode haver custos adicionais se o hardware precisar ser atualizado para dar suporte à versão mais recente do SharePoint ou se um farm secundário for necessário para atualização.  <br/> |
|Os parceiros podem ajudar com o trabalho único de migrar seus dados para o SharePoint Online.  <br/> ||
|Os produtos online são atualizados automaticamente. Embora os recursos possam ser preteridores, não há um verdadeiro fim do suporte. <br/> ||
   
Se você decidiu criar um novo site do Microsoft 365 e migrar manualmente dados para ele conforme necessário, verifique suas opções do [Microsoft 365](https://www.microsoft.com/microsoft-365/).
  
### <a name="upgrade-sharepoint-server-on-premises"></a>Atualizar o SharePoint Server local

Não há como ignorar versões em Atualizações do SharePoint. As atualizações são em série:
  
- SharePoint 2007 \> SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016
   
Ir do SharePoint 2007 para o SharePoint Server 2016 significa um investimento significativo de tempo e envolverá custos em hardware (os servidores SQL também devem ser atualizados), software e administração. As personalizações precisarão ser atualizadas ou abandonadas.
  
> [!NOTE]
> É possível manter seu farm do SharePoint 2007 de fim de vida, instalar um farm do SharePoint Server 2016 em um novo hardware (para que os farms separados executem lado a lado) e, em seguida, planeje e execute uma migração manual de conteúdo (para baixar e carregar conteúdo, por exemplo). Mas tenha cuidado com algumas das armadilhas de movimentações manuais, como movimentações de documentos substituindo a última conta modificada pelo alias da conta que está fazendo a movimentação manual. Considere também o trabalho que deve ser feito com antecedência, como recriar sites, subsites, permissões e estruturas de lista. Considere antecipadamente quais dados você pode mover para o armazenamento ou excluir para reduzir o impacto da migração.
  
É importante limpar seu ambiente antes de atualizar. Não se desfaça de que seu farm existente está funcional antes de atualizar e, certamente, antes de desmantelá-lo!
  
Lembre-se de revisar os caminhos de atualização com suporte *e sem suporte:* 
  
- 
  [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))
    
- [SharePoint Server 2010](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))
    
- [SharePoint Server 2013](/SharePoint/upgrade-and-update/review-supported-editions-and-products-for-upgrading-to-sharepoint-2013)
    
Se você tiver personalizações, é fundamental ter um plano para cada etapa no caminho de migração: 
  
- [SharePoint 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc263203(v=office.12))
    
- [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc263203(v=office.14))
    
- [SharePoint Server 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)
    
|**Profissional local**|**Con local**|
|:-----|:-----|
|Controle total de todos os aspectos do farm do SharePoint, do hardware do servidor para cima.  <br/> |Todas as quebras e correções são de responsabilidade da sua empresa (você pode envolver o Suporte pago da Microsoft se seu produto não for passado do fim do suporte).  <br/> |
|Conjunto de recursos completo do SharePoint Server local com a opção de conectar seu farm local a uma assinatura do SharePoint Online por meio de híbrido.  <br/> |Atualização, patches, correções de segurança e toda a manutenção do SharePoint Server gerenciada no local.  <br/> |
|Acesso total para maior personalização.  <br/> |[As ofertas de](/compliance/regulatory/offering-home) conformidade da Microsoft devem ser configuradas manualmente no local.  <br/> |
|Testes de segurança e ajuste de desempenho do servidor são realizados em seu local (sob seu controle).  <br/> |O Microsoft 365 pode disponibilizar recursos para o SharePoint Online que não interoperam com o SharePoint Server local.  <br/> |
|Os parceiros podem ajudar na migração de dados para a próxima versão do SharePoint Server (e além).  <br/> |Seus sites do SharePoint Server não usarão automaticamente [certificados SSL/TLS,](/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016) como é visto no SharePoint Online.  <br/> |
|Controle total das convenções de nomenização, backup e restauração e outras opções de recuperação no SharePoint Server local.  <br/> |O SharePoint Server local é sensível aos ciclos de vida do produto.  <br/> |
   
### <a name="upgrade-resources"></a>Atualizar recursos

Certifique-se de que seu ambiente atenda aos requisitos de hardware e software e siga os métodos de atualização suportados.
  
- **Requisitos de hardware/software para**: 
    
    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/hardware-and-software-requirements-0)  |  [SharePoint Server 2016](/SharePoint/install/hardware-and-software-requirements)
    
- **Limites e limites de software para**: 
    
    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262787(v=office.12))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262787(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/software-boundaries-and-limits)  |  [SharePoint Server 2016](/SharePoint/install/software-boundaries-and-limits-0)
    
- **A visão geral do processo de atualização para**: 
    
    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc303420(v=office.12))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc303420(v=office.14))  |  [SharePoint Server 2013](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)  |  [SharePoint Server 2016](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Criar uma solução híbrida do SharePoint entre o SharePoint Online e o local

Se a resposta às suas necessidades de migração estiver em algum lugar entre o autocontrole oferecido pelo local e o menor custo de propriedade oferecido pelo SharePoint Online, você poderá conectar farms do SharePoint Server 2013 ou 2016 ao SharePoint Online por meio de híbridos. [Saiba mais sobre as soluções híbridas do SharePoint.](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
  
Se você decidir que um farm híbrido do SharePoint Server beneficiará sua empresa, familiarize-se com os tipos de híbridos existentes e como configurar a conexão entre o farm local do SharePoint e sua assinatura do Microsoft 365.
  
| Opção | Descrição |
|:-----|:-----|
[Ofertas de conformidade da Microsoft](/compliance/regulatory/offering-home)  <br/> |[A assistência do FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) para migração é limitada.  <br/> Grande parte da atualização será manual ou por meio da API de Migração de SPO descrita no Roteiro de Conteúdo de Migração do SharePoint Online e [do OneDrive.](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets)  <br/> |
|Os engenheiros de suporte da Microsoft e funcionários do data center não têm acesso de administrador irrestrito à sua assinatura.<br/> |Pode haver custos adicionais se a infraestrutura de hardware precisar ser atualizada para dar suporte à versão mais recente do SharePoint ou se um farm secundário for necessário para atualização.  <br/> |
|Os parceiros podem ajudar com o trabalho único de migrar seus dados para o SharePoint Online.  <br/> ||
|Os produtos online são atualizados automaticamente em todo o serviço. Embora os recursos possam ser preteridores, não há fim verdadeiro do suporte.<br/> ||
   
Se você decidiu criar um novo site do Microsoft 365 e migrar manualmente dados para ele conforme necessário, verifique suas opções do [Microsoft 365](https://www.microsoft.com/microsoft-365/).
  
### <a name="upgrade-sharepoint-server-on-premises"></a>Atualizar o SharePoint Server local

Não há como ignorar versões em Atualizações do SharePoint. As atualizações são em série:
  
- SharePoint 2007 \> SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016
   
Ir do SharePoint 2007 para o SharePoint Server 2016 significará um investimento significativo de tempo e envolverá custos para hardware (os servidores SQL também devem ser atualizados), software e administração. As personalizações precisarão ser atualizadas ou abandonadas.
  
> [!NOTE]
> É possível manter seu farm do SharePoint 2007 de fim de vida, instalar um farm do SharePoint Server 2016 em um novo hardware (para que os farms separados executem lado a lado) e, em seguida, planeje e execute uma migração manual de conteúdo (para baixar e carregar conteúdo, por exemplo). Mas cuidado com possíveis armadilhas de movimentações manuais, como movimentações de documentos substituindo a última conta modificada pelo alias da conta que está fazendo a movimentação manual e o trabalho que deve ser feito com antecedência, como recriar sites, subsites, permissões e estruturas de lista. Considere quais dados você pode mover para o armazenamento ou excluir para reduzir o impacto da migração.
  
Limpe seu ambiente antes da atualização. Não se desfaça de que seu farm existente está funcional antes de atualizar e, certamente, antes de descomissioná-lo! 
  
Lembre-se de revisar os caminhos de atualização com suporte *e sem suporte:* 
  
- 
  [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))
    
- [SharePoint Server 2010](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))
    
- [SharePoint Server 2013](/SharePoint/upgrade-and-update/review-supported-editions-and-products-for-upgrading-to-sharepoint-2013)
    
Se você tiver *personalizações,* é fundamental que você tenha um plano de atualização para cada etapa no caminho de migração: 
  
- [SharePoint 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc263203(v=office.12))
    
- [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc263203(v=office.14))
    
- [SharePoint Server 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)
    
|**Pro local**|**Con local**|
|:-----|:-----|
|Controle total de todos os aspectos do farm do SharePoint, do hardware do servidor para cima.  <br/> |Todas as quebras e correções são de responsabilidade da sua empresa. (Você pode envolver o Suporte Pago da Microsoft se seu produto não estiver no final do suporte.)  <br/> |
|Conjunto de recursos completo do SharePoint Server local com a opção de conectar seu farm local a uma assinatura do SharePoint Online por meio de híbrido.  <br/> |Atualização, patches, correções de segurança e toda a manutenção do SharePoint Server gerenciada no local.  <br/> |
|Acesso total para maior personalização.  <br/> |[As ofertas de](/compliance/regulatory/offering-home) conformidade da Microsoft devem ser configuradas manualmente no local.  <br/> |
|Testes de segurança e ajuste de desempenho do servidor são realizados em seu local sob seu controle.  <br/> |O Microsoft 365 pode disponibilizar recursos para o SharePoint Online que não interoperam com o SharePoint Server local  <br/> |
|Os parceiros podem ajudar a migrar dados para a próxima versão do SharePoint Server (e além).  <br/> |Seus sites do SharePoint Server não usarão automaticamente [certificados SSL/TLS,](/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016) como é visto no SharePoint Online.  <br/> |
|Controle total das convenções de nomenização, backup e restauração e outras opções de recuperação no SharePoint Server local.  <br/> |O SharePoint Server local é sensível aos ciclos de vida do produto.  <br/> |
   
### <a name="upgrade-resources"></a>Atualizar recursos

Certifique-se de que seu ambiente atenda aos requisitos de hardware e software. Em seguida, siga os métodos de atualização com suporte.
  
- **Requisitos de hardware/software para:** 
    
    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/hardware-and-software-requirements-0)  |  [SharePoint Server 2016](/SharePoint/install/hardware-and-software-requirements)
    
- **Limites e limites de software para:** 
    
    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262787(v=office.12))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262787(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/software-boundaries-and-limits)  |  [SharePoint Server 2016](/SharePoint/install/software-boundaries-and-limits-0)
    
- **A visão geral do processo de atualização para:** 
    
    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc303420(v=office.12))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc303420(v=office.14))  |  [SharePoint Server 2013](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)  |  [SharePoint Server 2016](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Criar uma solução híbrida do SharePoint entre o SharePoint Online e o local

Se a resposta às suas necessidades de migração estiver em algum lugar entre o autocontrole oferecido pelo local e o menor custo de propriedade oferecido pelo SharePoint Online, você poderá conectar farms do SharePoint Server 2013 ou 2016 ao SharePoint Online por meio de híbridos. [Saiba mais sobre soluções híbridas do SharePoint](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
  
Se você decidir que um farm híbrido do SharePoint Server beneficiará sua empresa, familiarize-se com os tipos de híbridos existentes e como configurar a conexão entre o farm local do SharePoint e sua assinatura do Microsoft 365.
  
Uma boa maneira de ver como isso funciona é criar um ambiente de dev/test do Microsoft 365, que você pode configurar com Guias de Laboratório de [Teste.](m365-enterprise-test-lab-guides.md) Depois de obter uma avaliação ou adquirir a assinatura do Microsoft 365, você pode criar os conjunto de sites, webs e bibliotecas de documentos no SharePoint Online para os quais você pode migrar dados. Você pode migrar manualmente, por meio da API de Migração, ou, se quiser migrar o conteúdo de Meu Site para o OneDrive for Business, por meio do assistente híbrido.
  
> [!NOTE]
> Lembre-se de que, para usar a opção híbrida, seu farm do SharePoint 2007 precisará ser atualizado, no local, para o SharePoint Server 2013 ou o SharePoint Server 2016.
  
## <a name="related-topics"></a>Tópicos relacionados

[Solucionar problemas e retomar a atualização (Office SharePoint Server 2007)](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262967(v=office.12))
  
[Solucionar problemas de atualização (SharePoint Server 2010)](/previous-versions/office/sharepoint-server-2010/cc262967(v=office.14))
  
[Resolver problemas de atualização do banco de dados no SharePoint 2013](/SharePoint/upgrade-and-update/troubleshoot-database-upgrade-issues-in-sharepoint-2013)
  
[Pesquisar parceiros da Microsoft para ajudar na atualização](https://go.microsoft.com/fwlink/?linkid=841249)
  
[Recursos para ajudá-lo a atualizar de servidores e clientes do Office 2007](upgrade-from-office-2007-servers-and-products.md)
