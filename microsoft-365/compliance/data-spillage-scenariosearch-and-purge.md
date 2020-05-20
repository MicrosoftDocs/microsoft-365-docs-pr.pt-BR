---
title: cenário derramamento de dados da série de soluções de descoberta eletrônica-pesquisa e limpeza
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MET150
ms.assetid: d945f7dd-f62f-4ca7-b3e7-469824cfd493
description: Use as ferramentas de descoberta eletrônica e de pesquisa para gerenciar e responder a um incidente de derramamento de dados em sua organização.
ms.openlocfilehash: 4246460f2f7d7fdc41754fc2acd3125601bb5f79
ms.sourcegitcommit: 261d51b90a9ad53a6a42348c414b1b1e1230c37f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "44292447"
---
# <a name="ediscovery-solution-series-data-spillage-scenario---search-and-purge"></a>série de soluções de descoberta eletrônica: cenário de derramamento de dados-pesquisa e limpeza

 **O que é derramamento de dados e por que você deve cuidar?** Data derramamento é quando um documento confidencial é liberado em um ambiente não confiável. Quando um incidente de derramamento de dados é detectado, é importante avaliar rapidamente o tamanho e os locais do derramamento, examinar as atividades do usuário em torno dele e, em seguida, limpar permanentemente os dados derramados do sistema. 
  
## <a name="data-spillage-scenario"></a>Cenário de derramamento de dados

Você é diretor de segurança de informações de líder da contoso. Você é informado de uma situação de derramamento de dados em que um funcionário compartilhou inadvertidamente um documento altamente confidencial com várias pessoas por email. Você deseja avaliar rapidamente quem recebeu este documento interna e externamente. Depois de identificado, você gostaria de compartilhar resultados de caso com outros investigadores para revisão e, em seguida, remover permanentemente os dados do Office 365. Após a conclusão da investigação, você deseja gerar um relatório com a evidência de remoção permanente e outros detalhes de caso para qualquer referência futura.
  
### <a name="scope-of-this-article"></a>Escopo deste artigo

Este documento fornece uma lista de instruções sobre como remover permanentemente uma mensagem do Microsoft 365, de modo que ela não fique acessível ou recuperável. Para excluir uma mensagem e torná-la recuperável até que o período de retenção do item excluído expire, confira [Pesquisar e excluir mensagens de email em sua organização](search-for-and-delete-messages-in-your-organization.md).
  
## <a name="workflow-for-managing-data-spillage-incidents"></a>Fluxo de trabalho para gerenciamento de incidentes de derramamento de dados

Veja como gerenciar um incidente de derramamento de dados:

![O fluxo de trabalho de 8 etapas para gerenciar incidentes de derramamento de dados](../media/O365-eDiscoverySolutions-DataSpillage-workflow.png)
  
[Opcion Etapa 1: gerenciar quem pode acessar o caso e definir limites de conformidade](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries)<br/>
[Etapa 2: criar uma ocorrência de descoberta eletrônica](#step-2-create-an-ediscovery-case)<br/>
[Etapa 3: Pesquisar os dados derramados](#step-3-search-for-the-spilled-data)<br/>
[Etapa 4: analisar e validar as descobertas de caso](#step-4-review-and-validate-case-findings)<br/>
[Etapa 5: usar o log de rastreamento de mensagem para verificar como os dados de despejo foram compartilhados](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared)<br/>
[Etapa 6: preparar as caixas de correio](#step-6-prepare-the-mailboxes)<br/>
[Etapa 7: excluir permanentemente os dados derramados](#step-7-permanently-delete-the-spilled-data)<br/>
[Etapa 8: verificar, fornecer uma prova de exclusão e auditoria](#step-8-verify-provide-a-proof-of-deletion-and-audit)<br/>

## <a name="things-to-know-before-you-start"></a>Coisas que você precisa saber antes de começar

- Quando uma caixa de correio estiver em espera, uma mensagem excluída permanecerá na pasta itens recuperáveis até que o período de retenção expire ou a retenção seja liberada. A [etapa 6](#step-6-prepare-the-mailboxes) descreve como remover a retenção das caixas de correio. Verifique com seus departamentos jurídicos ou de gerenciamento de registros antes de remover a isenção. Sua organização pode ter uma política que define se uma caixa de correio em espera ou um incidente de derramamento de dados tem prioridade. 
    
- Para controlar quais caixas de correio de usuários um derramamento investigador de dados pode pesquisar e gerenciar quem pode acessar o caso, você pode configurar os limites de conformidade e criar um grupo de funções personalizado, descrito na [etapa 1](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries). Para fazer isso, você precisa ser membro do grupo de função gerenciamento da organização ou receber a função de gerenciamento de função. Se você ou o administrador da sua organização já tiver definido limites de conformidade, você poderá ignorar a etapa 1.
    
- Para criar uma ocorrência, você deve ser membro do grupo de função Gerenciador de descoberta eletrônica ou ser membro de um grupo de funções personalizado atribuído à função de gerenciamento de casos. Se você não for um membro, peça a um administrador do Microsoft 365 para [adicioná-lo ao grupo de funções Gerenciador de descoberta eletrônica](assign-ediscovery-permissions.md).
    
- Para criar e executar uma pesquisa de conteúdo, você precisa ser membro do grupo de funções Gerente de Descoberta Eletrônica ou receber a função de gerenciamento de Pesquisa de Conformidade. Para excluir mensagens, você precisa ser membro do grupo de funções Gerenciamento da Organização ou receber a função de gerenciamento Pesquisa e Limpar. Para saber mais sobre como adicionar usuários a um grupo de função, confira [Atribuir permissões de Descoberta Eletrônica no Centro de Segurança e Conformidade](https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions).
    
- Para pesquisar as atividades de descoberta eletrônica de log de auditoria na etapa 8, a auditoria deve estar ativada para sua organização. Você pode pesquisar atividades que foram realizadas nos últimos 90 dias. Para saber mais sobre como habilitar e usar a auditoria, confira a seção [Auditing The data derramamento Investigation Process](#auditing-the-data-spillage-investigation-process) na etapa 8. 
    
## <a name="optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries"></a>Opcion Etapa 1: gerenciar quem pode acessar o caso e definir limites de conformidade

Dependendo da sua prática organizacional, você precisará controlar quem pode acessar a ocorrência de descoberta eletrônica usada para investigar um incidente de derramamento de dados e configurar os limites de conformidade. A maneira mais fácil de fazer isso é adicionar investigadores como membros de um grupo de função existente no centro de conformidade & segurança e, em seguida, adicionar o grupo de função como membro da ocorrência de descoberta eletrônica. Para obter informações sobre os grupos de função de descoberta eletrônica interna e como adicionar membros a uma ocorrência de descoberta eletrônica, consulte [atribuir permissões de descoberta eletrônica](assign-ediscovery-permissions.md).
  
Você também pode criar um novo grupo de função que se alinhe às suas necessidades organizacionais. Por exemplo, você pode querer um grupo de dados derramamento investigadores na organização para acessar e colaborar em todas as ocorrências de derramamento de dados. Você pode fazer isso criando um grupo de função "investigador de dados derramamento", atribuindo as funções apropriadas (exportar, descriptografar, revisar, Visualizar, pesquisa de conformidade e gerenciamento de casos), adicionando os derramamento de dados de investigadores ao grupo de função e, em seguida, adicionando o grupo de função como um membro da ocorrência de descoberta eletrônica de dados derramamento. Confira [configurar limites de conformidade para investigações de descoberta eletrônica no Office 365](tagging-and-assessment-in-advanced-ediscovery.md) para obter instruções detalhadas sobre como fazer isso. 
  
## <a name="step-2-create-an-ediscovery-case"></a>Etapa 2: criar uma ocorrência de descoberta eletrônica

Um caso de descoberta eletrônica oferece uma maneira eficaz de gerenciar sua investigação de derramamento de dados. Você pode adicionar membros ao grupo de função que você criou na etapa 1, adicionar o grupo de função como um membro de um novo caso de descoberta eletrônica, realizar pesquisas iterativas para localizar os dados derramados, exportar um relatório para compartilhar, rastrear o status da ocorrência e, em seguida, consultar os detalhes do caso necessário. Considere o estabelecimento de uma Convenção de nomenclatura para casos de descoberta eletrônica usados para incidentes de derramamento de dados e forneça tantas informações quantas forem necessárias no nome e na descrição do caso, para que você possa localizar e consultar no futuro, se necessário.
  
Para criar um novo caso, você pode usar a descoberta eletrônica no centro de segurança e conformidade. Consulte "criar um novo caso" em [casos de descoberta eletrônica](ediscovery-cases.md#step-2-create-a-new-case).
  
## <a name="step-3-search-for-the-spilled-data"></a>Etapa 3: Pesquisar os dados derramados

Agora que você criou um caso e acesso gerenciado, você pode usar o caso para pesquisa iterativamente para localizar os dados derramados e identificar as caixas de correio que contêm os dados derramados. Você usará a mesma consulta de pesquisa que usou para localizar as mensagens de email para excluir essas mesmas mensagens na [etapa 7](#step-7-permanently-delete-the-spilled-data).
  
Para criar uma pesquisa de conteúdo associada a uma ocorrência de descoberta eletrônica, consulte "criar e executar uma pesquisa de conteúdo associada a um caso" em [casos de descoberta eletrônica](ediscovery-cases.md#step-5-create-and-run-a-content-search-associated-with-a-case).
  
 **Importante:** As palavras-chave que você usa na consulta de pesquisa podem conter os dados reais derramados que você está pesquisando. Por exemplo, se você estiver procurando documentos que contenham um número de seguridade social e usar a palavra-chave ti como pesquisa, deverá excluir a consulta posteriormente para evitar mais derramamento. Consulte [excluindo a consulta de pesquisa](#deleting-the-search-query) na etapa 8. 
  
## <a name="step-4-review-and-validate-case-findings"></a>Etapa 4: analisar e validar as descobertas de caso

Após criar uma pesquisa de conteúdo, você precisará rever e validar que os resultados da pesquisa e verificar se eles consistam apenas das mensagens de email que devem ser excluídas. Em uma pesquisa de conteúdo, você pode visualizar uma amostra aleatória de 1.000 mensagens de email sem exportar os resultados da pesquisa para evitar outros dados de derramamento. Você pode ler mais sobre as limitações de visualização em [limites de pesquisa de conteúdo](limits-for-content-search.md).
  
Se você tiver mais de 1.000 caixas de correio ou mais de 100 mensagens de email por caixa de correio para revisão, você pode dividir a pesquisa inicial em várias pesquisas usando palavras-chave ou condições adicionais, como o intervalo de datas ou remetente/destinatário, e revisar os resultados de cada pesquisa individualmente. Certifique-se de anotar todas as consultas de pesquisa para usar quando excluir mensagens na [etapa 7](#step-7-permanently-delete-the-spilled-data).

Se uma licença do Office 365 E5 for atribuída a um ou usuário final, você poderá examinar até 10.000 resultados de pesquisa ao usar a descoberta eletrônica avançada. Se houver mais de 10.000 mensagens de email a serem revisadas, você pode dividir a consulta de pesquisa por intervalo de datas e revisar cada resultado individualmente à medida que os resultados da pesquisa são classificados por data. Na descoberta eletrônica avançada, você pode marcar os resultados da pesquisa usando o **rótulo como** recurso no painel Visualizar e filtrar o resultado da pesquisa pela marca rotulada. Isso é útil quando você colabora com um revisor secundário. Usando ferramentas de análise adicionais em uma descoberta eletrônica avançada, como reconhecimento óptico de caracteres, encadeamento de emails e codificação de previsão, você pode processar e revisar rapidamente milhares de mensagens e marcá-las para análise adicional. Consulte [configuração rápida para descoberta eletrônica avançada](quick-setup-for-advanced-ediscovery.md).

Quando encontrar uma mensagem de email que contenha dados derramados, verifique os destinatários da mensagem para determinar se ele foi compartilhado externamente. Para rastrear mais uma mensagem, você pode coletar informações do remetente e o intervalo de datas para que possa usar os logs de rastreamento de mensagens, que é descrito na [etapa 5](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared).

Depois de verificar os resultados da pesquisa, talvez você queira compartilhar suas descobertas com outras pessoas para uma revisão secundária. As pessoas que você atribuiu à caixa de entrada da etapa 1 podem revisar o conteúdo do caso em descoberta eletrônica avançada e descoberta eletrônica avançada e aprovar descobertas de caso. Também é possível gerar um relatório sem exportar o conteúdo real. Você também pode usar esse mesmo relatório como prova de exclusão, que é descrito na [etapa 8](#step-8-verify-provide-a-proof-of-deletion-and-audit).
  
 **Para gerar um relatório estatístico:**
  
1. Vá para a página de **pesquisa** na ocorrência de descoberta eletrônica e clique na pesquisa para a qual você deseja gerar um relatório. 
    
2. Na página do menu, clique em **mais > relatório de exportação**.
 
      A página Exportar relatório é exibida.

    ![Selecione a pesquisa e clique em mais > relatório de exportação na página do menu suspenso](../media/O365-eDiscoverySolutions-DataSpillage-ExportReport1.png)
    
3. Selecione **todos os itens, incluindo aqueles que têm formato não reconhecido, estão criptografados ou não foram indexados por outros motivos** e clique em **gerar relatório**.

4. No caso de descoberta eletrônica, clique em **Exportar** para exibir a lista de trabalhos de exportação. Talvez seja necessário clicar em **Atualizar** para atualizar a lista para exibir o trabalho de exportação que você acabou de criar.

5. Clique no trabalho de exportação e, em seguida, clique em **baixar** relatório na página do menu suspenso.
 
    ![Na página Exportar, clique em exportar e em "baixar relatório"](../media/O365-eDiscoverySolutions-DataSpillage-ExportReport2.png)

O relatório de **Resumo de exportação** contém o número de locais encontrados com resultados e o tamanho dos resultados da pesquisa. Você pode usá-lo para comparar com o relatório gerado após a exclusão e fornecer uma prova de exclusão. O relatório de **resultados** contém um resumo mais detalhado dos resultados da pesquisa, incluindo o assunto, o remetente, os destinatários, se o email foi lido, as datas e o tamanho de cada mensagem. Se qualquer um dos detalhes neste relatório contiver os dados reais derramados, certifique-se de excluir permanentemente o arquivo Results. csv quando a investigação estiver concluída.

Para obter mais informações sobre como exportar relatórios, consulte [exportar um relatório de pesquisa de conteúdo](export-a-content-search-report.md).
    
## <a name="step-5-use-message-trace-log-to-check-how-spilled-data-was-shared"></a>Etapa 5: usar o log de rastreamento de mensagem para verificar como os dados de despejo foram compartilhados

Para investigar melhor se um email com dados derramados foi compartilhado, você pode opcionalmente consultar os logs de rastreamento de mensagens com as informações do remetente e as informações do intervalo de datas que você coletou na etapa 4. Observe que o período de retenção para rastreamento de mensagens é de 30 dias para dados em tempo real e 90 dias para dados históricos.
  
Você pode usar o rastreamento de mensagens no centro de segurança e conformidade ou usar os cmdlets correspondentes no PowerShell do Exchange Online. É importante observar que o rastreamento de mensagens não oferece garantias completas sobre a integridade dos dados retornados. Para obter mais informações sobre como usar o rastreamento de mensagens, consulte: 
  
- [Rastreamento de mensagens no Centro de Conformidade e Segurança](https://docs.microsoft.com/microsoft-365/security/office-365-security/message-trace-scc)
    
- [Novo rastreamento de mensagens no centro de conformidade e segurança &](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)
    
## <a name="step-6-prepare-the-mailboxes"></a>Etapa 6: preparar as caixas de correio

Depois de revisar e validar que os resultados da pesquisa contenham apenas as mensagens que devem ser excluídas, você precisará coletar uma lista dos endereços de email das caixas de correio afetadas a serem usadas na etapa 7 ao excluir os dados derramados. Você também pode ter que preparar as caixas de correio antes de excluir permanentemente mensagens de email dependendo se a recuperação de item único está habilitada nas caixas de correio que contêm os dados derramados ou se alguma dessas caixas de correio está em espera.
  
### <a name="get-a-list-of-addresses-of-mailboxes-with-spilled-data"></a>Obter uma lista de endereços de caixas de correio com dados derramados

Há duas maneiras de coletar uma lista de endereços de email de caixas de correio com dados derramados.

**Opção 1: obter uma lista de endereços de caixas de correio com dados derramados**

1. Abra o caso de descoberta eletrônica, vá para a página de **pesquisa** e selecione a pesquisa de conteúdo apropriada. 
    
2. Na página do menu suspenso, clique em **exibir resultados**.
    
3. Na lista suspensa **Resultados individuais**, clique em **Estatísticas de pesquisa**.
    
4. Na lista suspensa **tipo** , clique em **locais principais**.
    
    ![Obter uma lista de caixas de correio que contenham resultados de pesquisa na página locais principais nas estatísticas de pesquisa](../media/O365-eDiscoverySolutions-DataSpillage-TopLocations.png)

    Uma lista de caixas de correio que contêm resultados de pesquisa é exibida. O número de itens em cada caixa de correio que corresponde à consulta de pesquisa também é exibido.
    
5. Copie as informações na lista e salve-as em um arquivo ou clique em **baixar** para baixar as informações para um arquivo CSV. 
    
**Opção 2: obter locais de caixa de correio do relatório de exportação**

Abra o relatório de Resumo de exportação que você baixou na [etapa 4](#step-4-review-and-validate-case-findings). Na primeira coluna no relatório, o endereço de email de cada caixa de correio é listado em **locais**.
  
### <a name="prepare-the-mailboxes-so-you-can-delete-the-spilled-data"></a>Preparar as caixas de correio para que você possa excluir os dados derramados

Se a recuperação de item único estiver habilitada ou se uma caixa de correio for colocada em espera, uma mensagem permanentemente excluída (limpad) será mantida na pasta itens recuperáveis. Portanto, antes de poder limpar dados derramados, você precisa verificar as configurações de caixa de correio existentes e desabilitar a recuperação de item único e remover qualquer política de retenção ou bloqueio. Tenha em mente que você pode preparar uma caixa de correio de cada vez e, em seguida, executar o mesmo comando em caixas de correio diferentes ou criar um script do PowerShell para preparar várias caixas de correio ao mesmo tempo.

- Consulte "etapa 1: coletar informações sobre a caixa de correio" em [excluir itens da pasta itens recuperáveis das caixas de correio baseadas em nuvem em espera](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-1-collect-information-about-the-mailbox) para obter instruções sobre como verificar se a recuperação de item único está habilitada ou se a caixa de correio está colocada em espera ou se ela está atribuída a uma política de retenção. 

- Consulte "etapa 2: preparar a caixa de correio" em [excluir itens da pasta itens recuperáveis das caixas de correio baseadas em nuvem em espera](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-2-prepare-the-mailbox) para obter instruções sobre como desabilitar a recuperação de item único. 

- Consulte "etapa 3: remover todas as isenções da caixa de correio" em [excluir itens da pasta itens recuperáveis das caixas de correio baseadas em nuvem em espera](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-3-remove-all-holds-from-the-mailbox) para obter instruções sobre como remover uma política de retenção ou bloqueio de uma caixa de correio. 

- Consulte "etapa 4: remover o atraso na retenção da caixa de correio" em [excluir itens na pasta itens recuperáveis das caixas de correio baseadas em nuvem em espera](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-4-remove-the-delay-hold-from-the-mailbox) para obter instruções sobre como remover a espera de atraso que é colocada na caixa de correio após a remoção de qualquer tipo de retenção.

> [!IMPORTANT]
> Consulte o gerenciamento de registros ou os departamentos legais antes de remover uma política de retenção ou bloqueio. Sua organização pode ter uma política que define se uma caixa de correio em espera ou um incidente de derramamento de dados tem prioridade. 
  
Certifique-se de reverter a caixa de correio para as configurações anteriores depois de verificar se os dados derramados foram excluídos permanentemente. Consulte os detalhes na [etapa 7](#step-7-permanently-delete-the-spilled-data).

## <a name="step-7-permanently-delete-the-spilled-data"></a>Etapa 7: excluir permanentemente os dados derramados

Usando os locais da caixa de correio que você coletou e preparou na etapa 6 e a consulta de pesquisa que foi criada e refinada na etapa 3 para localizar mensagens de email que contêm os dados derramados, você pode excluir permanentemente os dados derramados.  Conforme explicado anteriormente, para excluir mensagens, você precisa ser membro do grupo de função gerenciamento da organização ou ter a função de gerenciamento de pesquisa e limpeza atribuída. Para saber mais sobre como adicionar usuários a um grupo de função, confira [Atribuir permissões de Descoberta Eletrônica no Centro de Segurança e Conformidade](https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions).

Para excluir as mensagens derramadas, Confira as etapas 2 & 3 em [Pesquisar e excluir mensagens de email](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization)

> [!IMPORTANT]
> Os itens de email em um conjunto de revisão em um caso de descoberta eletrônica avançada não podem ser excluídos usando os procedimentos deste artigo. Isso ocorre porque os itens em um conjunto de revisão são cópias dos itens no serviço em tempo real que são copiados e armazenados em um local de armazenamento do Azure. Isso significa que eles não serão retornados por uma pesquisa de conteúdo criada na etapa 3. Para excluir itens em um conjunto de revisão, você deve excluir a ocorrência de descoberta eletrônica avançada que contém o conjunto de revisão. Para obter mais informações, consulte [fechar ou excluir uma ocorrência de descoberta eletrônica avançada](close-or-delete-case.md).
  
## <a name="step-8-verify-provide-a-proof-of-deletion-and-audit"></a>Etapa 8: verificar, fornecer uma prova de exclusão e auditoria

A etapa final do fluxo de trabalho para gerenciar um incidente de derramamento de dados é verificar se os dados derramados foram removidos permanentemente da caixa de correio, acessando o caso de descoberta eletrônica e executando novamente a mesma consulta de pesquisa que foi usada para excluir esses dados para confirmar que nenhum resultado seja retornado. Após confirmar que os dados derramados foram removidos permanentemente, você pode exportar um relatório e incluí-lo (juntamente com o relatório original) como prova de exclusão. Em seguida, você pode [fechar o caso, o](ediscovery-cases.md#optional-step-9-close-a-case)que permitirá reabri-lo se você fizer referência a ele no futuro. Além disso, você também pode reverter caixas de correio para o estado anterior, excluir a consulta de pesquisa usada para localizar os dados derramados e pesquisar registros de auditoria de tarefas executadas ao gerenciar o incidente de derramamento de dados. 
  
### <a name="reverting-the-mailboxes-to-their-previous-state"></a>Revertendo as caixas de correio para o estado anterior

Se você alterou qualquer configuração de caixa de correio na etapa 6 para preparar as caixas de correio antes da exclusão dos dados derramados, será necessário revertê-los ao estado anterior. Consulte "etapa 6: reverter a caixa de correio para o estado anterior" em [excluir itens na pasta itens recuperáveis das caixas de correio baseadas em nuvem em espera](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-6-revert-the-mailbox-to-its-previous-state).
  
### <a name="deleting-the-search-query"></a>Excluindo a consulta de pesquisa

Se as palavras-chave na consulta de pesquisa que você criou e usou na etapa 3 contiverem alguns de todos os dados líquidos, você deverá excluir a consulta de pesquisa para evitar mais dados derramamento.
  
1. No centro de segurança e conformidade, abra o caso de descoberta eletrônica, vá para a página de **pesquisa** e selecione a pesquisa de conteúdo apropriada.
    
2. Na página do menu suspenso, clique em **excluir**.

    ![Selecione a pesquisa e clique em excluir na página do menu suspenso](../media/O365-eDiscoverySolutions-DataSpillage-DeleteSearch.png)
    
### <a name="auditing-the-data-spillage-investigation-process"></a>Auditar o processo de investigação de derramamento de dados

Você pode pesquisar o log de auditoria das atividades de descoberta eletrônica que foram realizadas durante a investigação. Você também pode pesquisar o log de auditoria para retornar os registros de auditoria para o comando **New-ComplianceSearchAction-Purge** executado na etapa 7 para excluir os dados derramados. Para saber mais, confira:

- [Pesquisas o log de auditoria](search-the-audit-log-in-security-and-compliance.md)

- [Procurar atividades de Descoberta Eletrônica no log de auditoria](search-for-ediscovery-activities-in-the-audit-log.md)
  
