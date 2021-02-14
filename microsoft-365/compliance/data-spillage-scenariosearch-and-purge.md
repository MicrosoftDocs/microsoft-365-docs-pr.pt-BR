---
title: Cenário de vazamento de dados da série de soluções de Descoberta eDiscovery - Pesquisa e limpeza
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MET150
ms.assetid: d945f7dd-f62f-4ca7-b3e7-469824cfd493
description: Use eDiscovery e ferramentas de pesquisa para gerenciar e responder a um incidente de vazamento de dados em sua organização.
ms.openlocfilehash: bb342eef057fefafe98de274851ad14e9c588dbe
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357561"
---
# <a name="ediscovery-solution-series-data-spillage-scenario---search-and-purge"></a>Série de soluções de Descoberta eDiscovery: Cenário de derramamento de dados - Pesquisa e limpeza

 **O que é vazamento de dados e por que você deve se preocupar?** O vazamento de dados é quando um documento confidencial é liberado em um ambiente não seguro. Quando um incidente de derramamento de dados é detectado, é importante avaliar rapidamente o tamanho e os locais do derramamento, examinar as atividades do usuário em torno dele e, em seguida, limpar permanentemente os dados eliminados do sistema. 
  
## <a name="data-spillage-scenario"></a>Cenário de derramamento de dados

Você é um líder de segurança de informações da Contoso. Você é informado de uma situação de vazamento de dados em que um funcionário compartilhou, sem saber, um documento altamente confidencial com várias pessoas por email. Você deseja avaliar rapidamente quem recebeu este documento interna e externamente. Uma vez identificado, você gostaria de compartilhar as descobertas de caso com outros investigadores para revisar e, em seguida, remover permanentemente os dados do Office 365. Após a conclusão da investigação, você deseja gerar um relatório com a evidência de remoção permanente e outros detalhes do caso para qualquer referência futura.
  
### <a name="scope-of-this-article"></a>Escopo deste artigo

Este documento fornece uma lista de instruções sobre como remover permanentemente uma mensagem do Microsoft 365 para que não seja acessível ou recuperável. Para excluir uma mensagem e torná-la recuperável até que o período de retenção do item excluído expire, consulte Pesquisar e excluir mensagens [de email em sua organização.](search-for-and-delete-messages-in-your-organization.md)
  
## <a name="workflow-for-managing-data-spillage-incidents"></a>Fluxo de trabalho para gerenciar incidentes de vazamento de dados

Veja aqui um como gerenciar um incidente de derramamento de dados:

![O fluxo de trabalho de 8 etapas para gerenciar incidentes de derramamento de dados](../media/O365-eDiscoverySolutions-DataSpillage-workflow.png)
  
[(Opcional) Etapa 1: Gerenciar quem pode acessar o caso e definir limites de conformidade](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries)<br/>
[Etapa 2: Criar um caso de Descoberta eDiscovery](#step-2-create-an-ediscovery-case)<br/>
[Etapa 3: procurar os dados de insupoção](#step-3-search-for-the-spilled-data)<br/>
[Etapa 4: Revisar e validar descobertas de caso](#step-4-review-and-validate-case-findings)<br/>
[Etapa 5: Usar o log de rastreamento de mensagens para verificar como os dados foram compartilhados](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared)<br/>
[Etapa 6: Preparar as caixas de correio](#step-6-prepare-the-mailboxes)<br/>
[Etapa 7: excluir permanentemente os dados de exclusão](#step-7-permanently-delete-the-spilled-data)<br/>
[Etapa 8: Verificar, fornecer uma prova de exclusão e auditoria](#step-8-verify-provide-a-proof-of-deletion-and-audit)<br/>

## <a name="things-to-know-before-you-start"></a>Coisas a saber antes de começar

- Quando uma caixa de correio está em espera, uma mensagem excluída permanece na pasta Itens Recuperáveis até que o período de retenção expire ou a retenção seja liberada. [A Etapa 6](#step-6-prepare-the-mailboxes) descreve como remover a espera das caixas de correio. Consulte o gerenciamento de registros ou os departamentos jurídicos antes de remover a espera. Sua organização pode ter uma política que define se uma caixa de correio em espera ou um incidente de vazamento de dados tem prioridade. 
    
- Para controlar quais caixas de correio de usuário um investigador de vazamento de dados pode pesquisar e gerenciar quem pode acessar o caso, você pode configurar limites de conformidade e criar um grupo de função personalizado, descrito na Etapa [1.](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries) Para fazer isso, você precisa ser membro do grupo de função Gerenciamento da Organização ou ter a função de gerenciamento de função atribuída. Se você ou o administrador em sua organização já tiver definido limites de conformidade, ignore a Etapa 1.
    
- Para criar uma ocorrência, você deve ser membro do grupo de funções Gerente de Descobertas e Ou ser membro de um grupo de função personalizado que tenha a função de Gerenciamento de Ocorrências atribuída. Se você não for um membro, peça a um administrador do Microsoft 365 para adicioná-lo ao grupo de funções do gerente [de Descobertas.](assign-ediscovery-permissions.md)
    
- Para criar e executar uma pesquisa de conteúdo, você precisa ser membro do grupo de funções Gerente de Descoberta Eletrônica ou receber a função de gerenciamento de Pesquisa de Conformidade. Para excluir mensagens, você precisa ser membro do grupo de funções Gerenciamento da Organização ou receber a função de gerenciamento Pesquisa e Limpar. Para saber mais sobre como adicionar usuários a um grupo de função, confira [Atribuir permissões de Descoberta Eletrônica no Centro de Segurança e Conformidade](https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions).
    
- Para pesquisar as atividades de Descoberta eDiscovery do log de auditoria na Etapa 8, a auditoria deve estar responsabilidade em sua organização. Você pode pesquisar atividades que foram executadas nos últimos 90 dias. Para saber mais sobre como habilitar e usar a auditoria, consulte a seção [Auditoria](#auditing-the-data-spillage-investigation-process) do processo de investigação de vazamento de dados na Etapa 8. 
    
## <a name="optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries"></a>(Opcional) Etapa 1: Gerenciar quem pode acessar o caso e definir limites de conformidade

Dependendo da prática organizacional, você precisa controlar quem pode acessar o caso de Descoberta eDiscovery usado para investigar um incidente de vazamento de dados e configurar limites de conformidade. A & maneira mais fácil de fazer isso é adicionar investigadores como membros de um grupo de função existente no Centro de Conformidade e Segurança e, em seguida, adicionar o grupo de função como membro do caso de Descoberta eDiscovery. Para obter informações sobre os grupos de função de Descoberta eDiscovery integrados e como adicionar membros a um caso de Descoberta [eDiscovery, consulte Assign eDiscovery permissions](assign-ediscovery-permissions.md).
  
Você também pode criar um novo grupo de funções que se alinhe às suas necessidades organizacionais. Por exemplo, você pode querer que um grupo de investigadores de vazamento de dados na organização acesse e colabore em todos os casos de vazamento de dados. Você pode fazer isso criando um grupo de funções "Investigador de Vazamento de Dados", atribuindo as funções apropriadas (Exportar, Descriptografar RMS, Revisão, Visualização, Pesquisa de Conformidade e Gerenciamento de Caso), adicionando os investigadores de vazamento de dados ao grupo de funções e, em seguida, adicionando o grupo de função como um membro do caso de vazamento de dados eDiscovery. Confira Configurar limites de conformidade para investigações de [Descobertas No Office 365](tagging-and-assessment-in-advanced-ediscovery.md) para obter instruções detalhadas sobre como fazer isso. 
  
## <a name="step-2-create-an-ediscovery-case"></a>Etapa 2: Criar um caso de Descoberta eDiscovery

Um caso de Descoberta e fornece uma maneira eficaz de gerenciar a investigação de vazamento de dados. Você pode adicionar membros ao grupo de funções criado na Etapa 1, adicionar o grupo de função como membro de um novo caso de Descoberta eDiscovery, realizar pesquisas iterativas para localizar os dados de vazamento, exportar um relatório para compartilhar, controlar o status da ocorrência e, em seguida, consultar novamente os detalhes do caso, se necessário. Considere estabelecer uma convenção de nomen por ocorrências de Descobertas e Descobertas Usadas para incidentes de vazamento de dados e forneça o máximo de informações possível no nome e na descrição do caso, para que você possa localizar e consultar no futuro, se necessário.
  
Para criar um novo caso, você pode usar o eDiscovery no centro de conformidade e segurança. Consulte "Criar um novo caso" em [casos de Descoberta e.](ediscovery-cases.md#step-2-create-a-new-case)
  
## <a name="step-3-search-for-the-spilled-data"></a>Etapa 3: procurar os dados de insupoção

Agora que você criou uma ocorrência e acesso gerenciado, pode usar o caso para pesquisar iterativamente para encontrar os dados que estão sendo procurados e identificar as caixas de correio que contêm os dados de inativos. Você usará a mesma consulta de pesquisa que usou para encontrar as mensagens de email para excluir essas mesmas mensagens na [Etapa 7.](#step-7-permanently-delete-the-spilled-data)
  
Para criar uma pesquisa de conteúdo associada a uma ocorrência de Descoberta eDiscovery, consulte "Criar e executar uma Pesquisa de Conteúdo associada a uma ocorrência" em casos de Descoberta [e.](ediscovery-cases.md#step-5-create-and-run-a-content-search-associated-with-a-case)
  
 **Importante:** As palavras-chave que você usa na consulta de pesquisa podem conter os dados reais que você está procurando. Por exemplo, se você pesquisar documentos que contenham um número de seguro social e usá-lo como palavra-chave de pesquisa, deverá excluir a consulta posteriormente para evitar mais vazamentos. Consulte [Excluir a consulta de pesquisa](#deleting-the-search-query) na Etapa 8. 
  
## <a name="step-4-review-and-validate-case-findings"></a>Etapa 4: Revisar e validar descobertas de caso

Depois de criar uma pesquisa de conteúdo, você precisa revisar e validar os resultados da pesquisa e verificar se eles consistem apenas nas mensagens de email que devem ser excluídas. Em uma pesquisa de conteúdo, você pode visualizar uma amostragem aleatória de 1.000 mensagens de email sem exportar os resultados da pesquisa para evitar mais vazamento de dados. Você pode ler mais sobre as limitações de visualização em [Limites para Pesquisa de Conteúdo.](limits-for-content-search.md)
  
Se você tiver mais de 1.000 caixas de correio ou mais de 100 mensagens de email por caixa de correio para revisar, poderá dividir a pesquisa inicial em várias pesquisas usando palavras-chave ou condições adicionais, como intervalo de datas ou remetente/destinatário, e analisar os resultados de cada pesquisa individualmente. Certifique-se de anotar todas as consultas de pesquisa a ser usadas ao excluir mensagens na [Etapa 7.](#step-7-permanently-delete-the-spilled-data)

Se um custodiante ou usuário final recebe uma licença do Office 365 E5, você pode examinar até 10.000 resultados de pesquisa de uma só vez usando a Descoberta Avançada. Se houver mais de 10.000 mensagens de email para revisar, você poderá dividir a consulta de pesquisa por intervalo de datas e revisar cada resultado individualmente à medida que os resultados da pesquisa são organizados por data. Na Descoberta Avançada, você pode marcar os  resultados da pesquisa usando o Rótulo como recurso no painel de visualização e filtrar o resultado da pesquisa pela marca que você rotulou. Isso é útil quando você colabora com um revistor secundário. Usando ferramentas de análise adicionais na Descoberta Eletrônico Avançada, como reconhecimento óptico de caracteres, threading de email e codificação preditiva, você pode processar e analisar rapidamente milhares de mensagens e marca-las para revisão adicional. Consulte [Configuração rápida para Descoberta Avançada de eDiscovery](quick-setup-for-advanced-ediscovery.md).

Quando você encontrar uma mensagem de email que contenha dados de recipiente, verifique os destinatários da mensagem para determinar se ela foi compartilhada externamente. Para rastrear ainda mais uma mensagem, você pode coletar informações do remetente e intervalo de datas para poder usar os logs de rastreamento de mensagens, descritos na [Etapa 5.](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared)

Depois de verificar os resultados da pesquisa, talvez você queira compartilhar suas descobertas com outras pessoas para uma análise secundária. As pessoas que você atribuiu ao caso na Etapa 1 podem revisar o conteúdo da ocorrência na Descoberta e na Descoberta Avançada e aprovar descobertas de caso. Você também pode gerar um relatório sem exportar o conteúdo real. Você também pode usar esse mesmo relatório como prova de exclusão, descrito na [Etapa 8.](#step-8-verify-provide-a-proof-of-deletion-and-audit)
  
 **Para gerar um relatório estatístico:**
  
1. Vá para a **página pesquisa** no caso de Descoberta e clique na pesquisa para a que você deseja gerar um relatório. 
    
2. Na página do flyout, clique em **Mais > Exportar relatório.**
 
      A página Exportar relatório é exibida.

    ![Selecione a pesquisa e clique em Mais > Exportar na página do flyout](../media/O365-eDiscoverySolutions-DataSpillage-ExportReport1.png)
    
3. Selecione **Todos os itens, incluindo** aqueles que não têm formato não reconhecedo, são criptografados ou não foram indexados por outros motivos e clique em Gerar **relatório.**

4. No caso de Descoberta eDiscovery, clique **em Exportar** para exibir a lista de trabalhos de exportação. Talvez seja preciso clicar em **Atualizar** para atualizar a lista para exibir o trabalho de exportação que você acabou de criar.

5. Clique no trabalho de exportação e clique em **Baixar** relatório na página do flyout.
 
    ![Na página Exportar, clique na exportação e em "Baixar relatório"](../media/O365-eDiscoverySolutions-DataSpillage-ExportReport2.png)

O **relatório Resumo de** Exportação contém o número de locais encontrados com os resultados e o tamanho dos resultados da pesquisa. Você pode usar isso para comparar com o relatório gerado após a exclusão e fornecer como prova de exclusão. O **relatório** de resultados contém um resumo mais detalhado dos resultados da pesquisa, incluindo o assunto, remetente, destinatários, se o email foi lido, datas e tamanho de cada mensagem. Se qualquer um dos detalhes neste relatório contiver os dados desastdos reais, certifique-se de excluir permanentemente o arquivo Results.csv de dados quando a investigação for concluída.

Para obter mais informações sobre como exportar relatórios, consulte [Exportar um relatório de Pesquisa de Conteúdo.](export-a-content-search-report.md)
    
## <a name="step-5-use-message-trace-log-to-check-how-spilled-data-was-shared"></a>Etapa 5: Usar o log de rastreamento de mensagens para verificar como os dados foram compartilhados

Para investigar ainda mais se os emails com dados de reação foram compartilhados, opcionalmente, você pode consultar os logs de rastreamento de mensagens com as informações do remetente e as informações do intervalo de datas coletadas na Etapa 4. Observe que o período de retenção para rastreamento de mensagens é de 30 dias para dados em tempo real e de 90 dias para dados históricos.
  
Você pode usar o rastreamento de mensagens no centro de conformidade e segurança ou usar os cmdlets correspondentes no PowerShell do Exchange Online. É importante observar que o rastreamento de mensagens não oferece garantias completas sobre a conclusão dos dados retornados. Para obter mais informações sobre como usar o rastreamento de mensagens, consulte: 
  
- [Rastreamento de mensagens no Centro de Conformidade e Segurança](https://docs.microsoft.com/microsoft-365/security/office-365-security/message-trace-scc)
    
- [Novo rastreamento de mensagens no Centro de Conformidade & segurança](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)
    
## <a name="step-6-prepare-the-mailboxes"></a>Etapa 6: Preparar as caixas de correio

Depois de analisar e validar se os resultados da pesquisa contêm apenas as mensagens que devem ser excluídas, você precisará coletar uma lista dos endereços de email das caixas de correio impactadas para usar na Etapa 7, quando excluir os dados excluídos. Você também pode ter que preparar as caixas de correio antes de excluir permanentemente as mensagens de email, dependendo se a recuperação de item individual está habilitada nas caixas de correio que contêm os dados pendentes ou se qualquer uma dessas caixas de correio está em espera.
  
### <a name="get-a-list-of-addresses-of-mailboxes-with-spilled-data"></a>Obter uma lista de endereços de caixas de correio com dados de vazamento

Há duas maneiras de coletar uma lista de endereços de email de caixas de correio com dados de envio.

**Opção 1: Obter uma lista de endereços de caixas de correio com dados de indados**

1. Abra a ocorrência de Descoberta e, em seguida, vá para a página **Pesquisa** e selecione a pesquisa de conteúdo apropriada. 
    
2. Na página do flyout, clique em **Exibir resultados.**
    
3. Na lista suspensa **Resultados individuais**, clique em **Estatísticas de pesquisa**.
    
4. Na lista **lista de** tipos, clique em **Locais principais.**
    
    ![Obter uma lista de caixas de correio que contêm resultados de pesquisa na página Principais locais nas estatísticas de pesquisa](../media/O365-eDiscoverySolutions-DataSpillage-TopLocations.png)

    Uma lista de caixas de correio que contêm resultados de pesquisa é exibida. O número de itens em cada caixa de correio que corresponderem à consulta de pesquisa também é exibido.
    
5. Copie as informações na lista e salve-as em um arquivo ou clique em **Baixar** para baixar as informações para um arquivo CSV. 
    
**Opção 2: Obter locais de caixa de correio do relatório de exportação**

Abra o relatório de Resumo de Exportação que você baixou na [Etapa 4.](#step-4-review-and-validate-case-findings) Na primeira coluna do relatório, o endereço de email de cada caixa de correio é listado em **Locais.**
  
### <a name="prepare-the-mailboxes-so-you-can-delete-the-spilled-data"></a>Preparar as caixas de correio para que você possa excluir os dados excluídos

Se a recuperação de item único estiver habilitada ou se uma caixa de correio for colocada em espera, uma mensagem excluída permanentemente (eliminada) será mantida na pasta Itens Recuperáveis. Portanto, antes de limpar os dados removidos, você precisa verificar as configurações de caixa de correio existentes e desabilitar a recuperação de item único e remover qualquer política de retenção ou retenção. Lembre-se de que você pode preparar uma caixa de correio por vez e, em seguida, executar o mesmo comando em caixas de correio diferentes ou criar um script do PowerShell para preparar várias caixas de correio ao mesmo tempo.

- Consulte "Etapa 1: Coletar informações [](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-1-collect-information-about-the-mailbox) sobre a caixa de correio" em Excluir itens na pasta Itens Recuperáveis de caixas de correio baseadas em nuvem em espera para obter instruções sobre como verificar se a recuperação de item único está habilitada ou se a caixa de correio é colocada em espera ou está atribuída a uma política de retenção. 

- Consulte "Etapa 2: Preparar [](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-2-prepare-the-mailbox) a caixa de correio" em Excluir itens na pasta Itens Recuperáveis de caixas de correio baseadas em nuvem em espera para obter instruções sobre como desabilitar a recuperação de item único. 

- Consulte a "Etapa 3: Remover todas [](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-3-remove-all-holds-from-the-mailbox) as retenções da caixa de correio" em Excluir itens na pasta Itens Recuperáveis de caixas de correio em espera baseadas em nuvem para obter instruções sobre como remover uma política de retenção ou retenção de uma caixa de correio. 

- Consulte "Etapa 4: Remover o atraso [](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-4-remove-the-delay-hold-from-the-mailbox) de espera da caixa de correio" em Excluir itens na pasta Itens Recuperáveis de caixas de correio baseadas em nuvem em espera para obter instruções sobre como remover o atraso que é colocado na caixa de correio após qualquer tipo de espera ser removido.

> [!IMPORTANT]
> Consulte o gerenciamento de registros ou os departamentos jurídicos antes de remover uma política de retenção ou retenção. Sua organização pode ter uma política que define se uma caixa de correio em espera ou um incidente de vazamento de dados tem prioridade. 
  
Certifique-se de reverter a caixa de correio para as configurações anteriores depois de verificar se os dados excluídos foram permanentemente excluídos. Veja os detalhes na [Etapa 7.](#step-7-permanently-delete-the-spilled-data)

## <a name="step-7-permanently-delete-the-spilled-data"></a>Etapa 7: excluir permanentemente os dados de exclusão

Usando os locais de caixa de correio coletados e preparados na Etapa 6 e a consulta de pesquisa que foi criada e refinada na Etapa 3 para encontrar mensagens de email que contenham os dados excluídos, agora você pode excluir permanentemente os dados excluídos.  Conforme explicado anteriormente, para excluir mensagens, você precisa ser membro do grupo de função Gerenciamento da Organização ou receber a função de gerenciamento Pesquisar e Limpar. Para saber mais sobre como adicionar usuários a um grupo de função, confira [Atribuir permissões de Descoberta Eletrônica no Centro de Segurança e Conformidade](https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions).

Para excluir as mensagens enviadas, consulte as etapas 2 & 3 na Pesquisa [e excluir mensagens de email](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization)

> [!IMPORTANT]
> Os itens de e-mail em um conjunto de revisões em um caso de Descoberta eletrônica avançada não podem ser excluídos usando os procedimentos deste artigo. Isso porque os itens em um conjunto de revisão são cópias de itens no serviço ao vivo que são copiados e armazenados em um local de armazenamento do Azure. Isso significa que eles não serão retornados por uma pesquisa de conteúdo que você criar na Etapa 3. Para excluir itens em um conjunto de revisões, é necessário excluir o caso de Descoberta eletrônica avançada que contém o conjunto de revisões. Para obter mais informações, consulte [Fechar ou excluir um caso de descoberta eletrônica avançado](close-or-delete-case.md).
  
## <a name="step-8-verify-provide-a-proof-of-deletion-and-audit"></a>Etapa 8: Verificar, fornecer uma prova de exclusão e auditoria

A etapa final no fluxo de trabalho para gerenciar um incidente de vazamento de dados é verificar se os dados de vazamento foram removidos permanentemente da caixa de correio indo para o caso de Descoberta e executando a mesma consulta de pesquisa que foi usada para excluir esses dados e confirmar se nenhum resultado foi retornado. Depois de confirmar que os dados foram removidos permanentemente, você pode exportar um relatório e incluí-lo (juntamente com o relatório original) como prova de exclusão. Em [seguida, você pode fechar o caso,](ediscovery-cases.md#optional-step-9-close-a-case)o que permitirá rea abri-lo se você tiver se referir a ele no futuro. Além disso, você também pode reverter as caixas de correio para seu estado anterior, excluir a consulta de pesquisa usada para encontrar os dados isolados e procurar registros de auditoria de tarefas executadas ao gerenciar o incidente de vazamento de dados. 
  
### <a name="reverting-the-mailboxes-to-their-previous-state"></a>Revertendo as caixas de correio para seu estado anterior

Se você alterou qualquer configuração de caixa de correio na Etapa 6 para preparar as caixas de correio antes que os dados de exclusão foram excluídos, você precisará reverte-los para seu estado anterior. Consulte "Etapa 6: Reverter a caixa de correio para seu estado anterior" em Excluir itens na pasta Itens Recuperáveis de caixas de correio baseadas em nuvem [em espera.](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-6-revert-the-mailbox-to-its-previous-state)
  
### <a name="deleting-the-search-query"></a>Excluir a consulta de pesquisa

Se as palavras-chave na consulta de pesquisa que você criou e usou na Etapa 3 contiver alguns de todos os dados gerados, exclua a consulta de pesquisa para evitar mais vazamento de dados.
  
1. No centro de conformidade e segurança, abra o caso  de Descoberta e, em seguida, vá para a página Pesquisa e selecione a pesquisa de conteúdo apropriada.
    
2. Na página do flyout, clique em **Excluir**.

    ![Selecione a pesquisa e clique em Excluir na página do flyout](../media/O365-eDiscoverySolutions-DataSpillage-DeleteSearch.png)
    
### <a name="auditing-the-data-spillage-investigation-process"></a>Auditoria do processo de investigação de vazamento de dados

Você pode pesquisar o log de auditoria para as atividades de Descoberta eDiscovery que foram executadas durante a investigação. Você também pode pesquisar o log de auditoria para retornar os registros de auditoria para o comando **New-ComplianceSearchAction -Purge** que você realizou na Etapa 7 para excluir os dados excluídos. Para saber mais, confira:

- [Pesquisas o log de auditoria](search-the-audit-log-in-security-and-compliance.md)

- [Procurar atividades de Descoberta Eletrônica no log de auditoria](search-for-ediscovery-activities-in-the-audit-log.md)
  
