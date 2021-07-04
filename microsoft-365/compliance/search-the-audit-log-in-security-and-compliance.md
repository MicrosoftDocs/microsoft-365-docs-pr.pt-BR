---
title: Pesquisar o log de auditoria no Centro de Conformidade e Segurança
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: 0d4d0f35-390b-4518-800e-0c7ec95e946c
description: Use o Centro de conformidade do Microsoft 365 para pesquisar o log de auditoria unificado para visualizar a atividade do usuário e administrador em sua organização.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a6989d8f57123a35e64b89cfe9148cae33c5758e
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287498"
---
# <a name="search-the-audit-log-in-the-compliance-center"></a>Pesquisar o log de auditoria no centro de conformidade

Precisa descobrir se um usuário visualizou um documento específico ou apagou um item de sua caixa de correio? Nesse caso, você pode usar o Centro de conformidade do Microsoft 365 para pesquisar o log de auditoria unificado para visualizar a atividade do usuário e administrador em sua organização. Por que usar um log de auditoria unificada? Como você pode procurar os seguintes tipos de [Atividade de usuários e administradores](#audited-activities) no Microsoft 365:

- Atividade do usuário do SharePoint Online e do OneDrive for Business
- Atividade do usuário do Exchange Online (log de auditoria da caixa de correio do Exchange)
- Atividade de administração do SharePoint Online
- Atividade de administração do Azure Active Directory (o serviço de diretório para o Microsoft 365)
- Atividade de administradores do Exchange Online (log de auditoria de administradores do Exchange)
- atividades de descoberta eletrônica no centro de conformidade e segurança
- Atividade de usuários e administradores do Power BI
- Atividade de usuários e administradores do Microsoft Teams
- Atividade de usuários e administradores do Dynamics 365
- Atividade de usuários e administradores do Yammer
- Atividade de usuários e administradores do Microsoft Power Automate
- Atividade de usuários e administradores do Microsoft Stream
- Atividade de administradores e analistas do Microsoft Workplace Analytics
- Atividade de usuários e administradores do Microsoft Power Apps
- Atividade de usuários e administradores do Microsoft Forms
- Atividade de usuários e administradores dos rótulos de sensibilidade de sites que usam o SharePoint Online ou o Microsoft Teams
- Atividade administrativa em email de Resumo e MyAnalytics

## <a name="requirements-to-search-the-audit-log"></a>Requisitos para pesquisar o log de auditoria

Leia os seguintes itens antes de começar a pesquisar o log de auditoria.

- A pesquisa de log de auditoria é ativada por padrão para organizações usando o Microsoft 365 e o Microsoft Office 365 corporativo. Isto inclui organizações com assinaturas E3/G3 ou E5/G5. Para verificar se a pesquisa de log de auditoria está ativada, você pode executar o seguinte comando em Exchange Online PowerShell:

  ```powershell
  Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
  ```

  O valor de `True` para a propriedade *UnifiedAuditLogIngestionEnabled* indica que a pesquisa de log de auditoria está ativada. Para saber mais, confira [Ativar ou desativar a pesquisa de log de auditoria](turn-audit-log-search-on-or-off.md).

- É preciso atribuir a função Logs de Auditoria Somente para Exibição ou Logs de Auditoria do Exchange Online para pesquisar o log de auditoria. Por padrão, essas funções são atribuídas aos grupos de funções Gerenciamento de Conformidade e Gerenciamento de Organização na página **Permissões** do centro de administração do Exchange. Note que os administradores globais do Office 365 e do Microsoft 365 são automaticamente adicionados como membros do grupo de função Gerenciamento da Organização no Exchange Online. Para que um usuário tenha a capacidade de pesquisar o log de auditoria com o nível mínimo de privilégios, você pode criar um grupo de funções personalizado no Exchange Online, adicionar a função Logs de Auditoria Somente para Exibição ou Logs de Auditoria e, em seguida, adicionar o usuário como um membro do novo grupo de funções. Para saber mais, confira [Gerenciar Grupos de Funções do Exchange Online](/Exchange/permissions-exo/role-groups).

  > [!IMPORTANT]
  > Se você atribuir a um usuário a função Logs de Auditoria Somente para Exibição ou Logs de Auditoria na página **Permissões** do Centro de Conformidade e Segurança, eles não poderão pesquisar o log de auditoria. Você deve atribuir as permissões no Exchange Online. Isso ocorre porque o cmdlet subjacente usado para pesquisar o log de auditoria é um cmdlet Exchange Online.

- Quando uma atividade auditada é realizada por um usuário ou administrador, um registro de auditoria é gerado e armazenado no log de auditoria para a sua organização. O período de tempo em que um registro de auditoria é mantido (e pesquisável no log de auditoria) depende da sua assinatura do Office 365 ou do Microsoft 365 Enterprise e, especificamente, o tipo de licença atribuída a usuários específicos.

  - Para os usuários que receberam uma licença do Office 365 E5 ou do Microsoft 365 E5 (ou usuários com uma licença complementar da Conformidade do Microsoft 365 E5 ou da Auditoria e Descoberta Eletrônica do Microsoft 365 E5), registros de auditoria do Azure Active Directory, Exchange e das atividades do SharePoint são mantidos por um ano, por padrão. As organizações também podem criar políticas de retenção de log de auditoria para manter os registros de auditoria para atividades em outros serviços por até um ano. Para saber mais, confira [Gerenciar políticas de retenção de log de auditoria](audit-log-retention-policies.md).

    > [!NOTE]
    > Se a sua organização participou do programa de visualização particular para a retenção de registros de auditoria por um ano, a duração da retenção para registros de auditoria gerados antes da data da implantação da disponibilidade geral não será redefinida.

  - Para os usuários que receberam qualquer outra licença (não E5) do Office 365 ou do Microsoft 365, os registros de auditoria serão mantidos por 90 dias. Para obter uma lista de assinaturas do Office 365 e do Microsoft 365 que oferecem suporte ao log de auditoria unificado, confira [descrição do serviço do centro de conformidade e segurança](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).

    > [!NOTE]
    > Mesmo quando a auditoria da caixa de correio está ativada por padrão, pode-se notar que os eventos de auditoria de caixa de correio de alguns usuários não são encontrados nas pesquisas de log de auditoria no Centro de Conformidade & Segurança ou por meio da API de Atividade de Gerenciamento do Office 365. Para saber mais, confira [Mais informações sobre o log de auditoria de caixa de correio](enable-mailbox-auditing.md#more-information).

- Caso pretenda desativar a pesquisa de log de auditoria da sua organização, execute o comando a seguir no PowerShell remoto conectado à sua organização do Exchange Online:

  ```powershell
  Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
  ```

    Para ativar a pesquisa de auditoria novamente, execute o seguinte comando no PowerShell do Exchange Online:

  ```powershell
  Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
  ```

  Para saber mais, confira [Desativar a pesquisa de log de auditoria](turn-audit-log-search-on-or-off.md).

- Como mencionado anteriormente, o cmdlet subjacente usado para pesquisar o log de auditoria é um cmdlet Exchange Online, que é **Search-UnifiedAuditLog**. Isso significa que você pode usar esse cmdlet para pesquisar o log de auditoria, em vez de usar a página **pesquisa de log de Auditoria** no Centro de Conformidade e Segurança. Você precisa executar esse cmdlet no PowerShell remoto conectado à sua organização do Exchange Online. Para saber mais, confira [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog).

  Para obter informações sobre como exportar os resultados da pesquisa retornados pelo cmdlet **Search-UnifiedAuditLog** para um arquivo CSV, confira a seção "Dicas para exportar e exibir o log de auditoria" em [Exportar, configurar e exibir registros de log de auditoria](export-view-audit-log-records.md#tips-for-exporting-and-viewing-the-audit-log).

- Se quiser baixar dados programaticamente do log de auditoria, recomendamos que você use a API da Atividade de Gestão do Office 365 em vez de usar um script do PowerShell. A API de Atividades de Gerenciamento do Office 365 é um serviço Web REST que você pode usar para desenvolver soluções de monitoramento de operações, segurança e conformidade para sua organização. Para mais informações, confira [referência da API de Atividade de Gerenciamento do Office 365](/office/office-365-management-api/office-365-management-activity-api-reference).

- Pode levar de 30 minutos a 24 horas após a ocorrência de um evento para que o registro do log de auditoria seja retornado nos resultados de uma pesquisa de log de auditoria. A tabela a seguir mostra o tempo necessário para os vários serviços do Office 365.

  <br>

  ****

  |Serviço ou recurso do Microsoft 365|30 minutos|24 horas|
  |---|:---:|:---:|
  |Defender para Office 365 e Inteligência Contra Ameaças|![Marca de seleção](../media/checkmark.png)||
  |Azure Active Directory (eventos de logon do usuário)||![Marca de seleção](../media/checkmark.png)|
  |Azure Active Directory (eventos de administração)||![Marca de seleção](../media/checkmark.png)|
  |Prevenção contra Perda de Dados|![Marca de seleção](../media/checkmark.png)||
  |Dynamics 365 CRM||![Marca de seleção](../media/checkmark.png)|
  |Descoberta eletrônica|![Marca de seleção](../media/checkmark.png)||
  |Exchange Online|![Marca de seleção](../media/checkmark.png)||
  |Microsoft Power Automate||![Marca de seleção](../media/checkmark.png)|
  |Microsoft Project|![Marca de seleção](../media/checkmark.png)||
  |Microsoft Stream|![Marca de seleção](../media/checkmark.png)||
  |Microsoft Teams|![Marca de seleção](../media/checkmark.png)||
  |Aplicativos de energia||![Marca de seleção](../media/checkmark.png)|
  |Power BI|![Marca de seleção](../media/checkmark.png)||
  |Centro de Conformidade e Segurança|![Marca de seleção](../media/checkmark.png)||
  |Rótulos de confidencialidade||![Marca de seleção](../media/checkmark.png)|
  |SharePoint Online e OneDrive for Business|![Marca de seleção](../media/checkmark.png)||
  |Workplace Analytics|![Marca de seleção](../media/checkmark.png)||
  |Yammer||![Marca de seleção](../media/checkmark.png)|
  |Microsoft Forms|![Marca de seleção](../media/checkmark.png)||
  |

- O Azure Active Directory (Azure AD) é o serviço de diretório do Office 365. O log de auditoria unificado contém atividades de usuários, grupos, aplicativos, domínios e atividades de diretórios realizadas no Microsoft 365 ou no portal de gerenciamento do Azure. Para obter uma lista completa de eventos do Azure AD, confira [Eventos de Relatório de Auditoria do Azure Active Directory](/azure/active-directory/reports-monitoring/concept-audit-logs).

- O log de auditoria do Power BI não está habilitado por padrão. Para pesquisar as atividades do Power BI no log de auditoria, habilite o recurso de auditoria no Portal de Administração do Power BI. Para obter instruções, confira a seção "logs de auditoria" no [portal de administração do Power bi](/power-bi/service-admin-portal#audit-logs).

## <a name="search-the-audit-log"></a>Pesquisar o log de auditoria

A seguir, veja o processo para pesquisar o log de auditoria do Office 365. 

[Etapa 1: Executar uma pesquisa de log de auditoria](#step-1-run-an-audit-log-search)

[Etapa 2: Exibir os resultados da pesquisa](#step-2-view-the-search-results)

[Etapa 3: Filtrar os resultados da pesquisa](#step-3-filter-the-search-results)

[Etapa 4: Exportar os resultados da pesquisa para um arquivo](#step-4-export-the-search-results-to-a-file)

### <a name="step-1-run-an-audit-log-search"></a>Etapa 1: Executar uma pesquisa de log de auditoria

1. Acesse [https://protection.office.com](https://protection.office.com).

    > [!TIP]
    > Use uma sessão de navegação particular (não uma sessão regular) para acessar o centro de conformidade & de segurança, pois isso impedirá que a credencial com a qual você está conectado no momento seja usada. Para abrir uma sessão de Navegação InPrivate no Internet Explorer ou no Microsoft Edge, basta pressionar CTRL+SHIFT+P. Para abrir uma sessão de navegação privada no Google Chrome (chamado de janela incógnita), pressione CTRL+SHIFT+N.

2. Entre usando sua conta de trabalho ou da escola.

3. No painel esquerdo do Centro de Conformidade e Segurança, clique em **Pesquisar** e, em seguida, clique em **Pesquisa de Log de Auditoria**.

    É exibida a página **Pesquisa de log de auditoria**.

    ![Configure os critérios e clique em Pesquisar para executar o relatório](../media/8639d09c-2843-44e4-8b4b-9f45974ff7f1.png)

    > [!NOTE]
    > Você primeiro precisa ativar o log de auditoria para poder executar uma pesquisa de log de auditoria. Se o link **Iniciar gravação de atividade de usuários e administradores** for exibido, clique nele para ativar a auditoria. Se você não vir esse link, significa que a auditoria já está ativada na sua organização.

4. Configure os seguintes critérios de pesquisa: 

   1. **Atividades**: Clique na lista suspensa para exibir as atividades que você pode procurar. As atividades de usuário e administrador são organizadas em grupos de atividades relacionadas. Você pode selecionar atividades específicas ou pode clicar no nome do grupo de atividades para selecionar todas as atividades que ele contém. Você também pode clicar em uma atividade selecionada para limpar a seleção. Após a execução da pesquisa, apenas as entradas do log de auditoria das atividades selecionadas serão exibidas. Ao selecionar **Mostrar resultados para todas as atividades** os resultados para todas as atividades executadas pelo usuário ou grupo de usuários selecionado será exibido.

      Mais de 100 atividades de usuários e administradores são registradas no log de auditoria. Clique na guia **Atividades auditadas**, no tópico deste artigo, para ver as descrições de cada atividade em cada um dos diferentes serviços.

   1. **Data de início** e **Data de término**: Os últimos sete dias são selecionados por padrão. Selecione um intervalo de datas e horas para exibir os eventos ocorridos durante esse período. A data e hora são apresentadas na horário local. O intervalo de datas máximo que você pode especificar é de 90 dias. Um erro será exibido se o período selecionado for superior a 90 dias.

      > [!TIP]
      > Se você estiver usando o intervalo máximo de datas de 90 dias, selecione a hora atual para a **Data de início**. Caso contrário, você receberá um erro afirmando que a data de início é anterior à data de término. Se você tiver ativado a auditoria nos últimos 90 dias, o intervalo máximo de datas não poderá começar antes da data em que a auditoria foi ativada.

   1. **Usuários**: Clique nessa caixa e selecione um ou mais usuários para os quais deseja exibir resultados. As entradas do log de auditoria para a atividade selecionada realizada pelos usuários que você seleciona nessa caixa são exibidas na lista de resultados. Deixe essa caixa em branco para retornar entradas para todos os usuários (e contas de serviço) na sua organização.

   1. **Arquivo, pasta ou site**: Digite alguns ou todos os nome de arquivo ou pasta para pesquisar atividades relacionadas ao arquivo de pasta que contenha a palavra-chave especificada. Você também pode especificar uma URL de um arquivo ou pasta. Se você usar uma URL, certifique-se, ao digitar o caminho completo ou apenas uma parte da URL, não incluir espaços ou caracteres especiais.

      Deixe essa caixa em branco para retornar entradas para todos os arquivos e pastas em sua organização.

      > [!TIP]
      >
      > - Se você estiver procurando por todas as atividades relacionadas a um **site**, adicione o símbolo curinga (\*) após a URL para retornar todas as entradas para esse site. Por exemplo, `"https://contoso-my.sharepoint.com/personal*"`.
      >
      > - Se você estiver procurando por todas as atividades relacionadas a um **arquivo**, adicione o símbolo curinga (\*) antes do nome do arquivo para retornar todas as entradas desse arquivo, por exemplo, `"*Customer_Profitability_Sample.csv"`.

5. Clique em **Pesquisar** para executar a pesquisa usando seus critérios de pesquisa. 

   Os resultados da pesquisa são carregados e, depois de alguns momentos, são exibidos em **Resultados**. Quando a pesquisa estiver concluída, o número de resultados encontrados será exibido. Um máximo de 5.000 eventos serão exibidos no painel **Resultados** em incrementos de 150 eventos. Se mais de 5.000 eventos atenderem aos critérios de pesquisa, os 5.000 mais recentes serão exibidos.

   ![O número de resultados é exibido após a conclusão da pesquisa](../media/986216f1-ca2f-4747-9480-e232b5bf094c.png)

#### <a name="tips-for-searching-the-audit-log"></a>Dicas para pesquisar o log de auditoria

- É possível selecionar atividades específicas para procurar clicando no nome da atividade. Também é possível procurar todas as atividades em um grupo (como **Atividades de arquivos e pastas**) clicando no nome do grupo. Se uma atividade estiver selecionada, você poderá clicar nela para cancelar a seleção. Você também pode usar a caixa de pesquisa para exibir as atividades que contêm a palavra-chave digitada.

  ![Clique no nome do grupo de atividade para selecionar todas as atividades](../media/3cde97cb-6f35-47c0-8612-ecd9c6ac36a3.png)

- É necessário selecionar **Mostrar resultados para todas as atividades**, na lista **Atividades** para exibir eventos do log de auditoria de administradores do Exchange. Os eventos desse log de auditoria exibem um nome de cmdlet (por exemplo, **Set-Mailbox**) na coluna **Atividade** dos resultados. Para obter mais informações, clique na guia **Atividades auditadas** neste tópico e, em seguida, clique em **Atividades de administração do Exchange**.

  Da mesma forma, existem algumas atividades de auditoria que não possuem um item correspondente na lista **Atividades**. Se souber o nome da operação dessas atividades, você poderá procurar todas as atividades e, em seguida, filtrar os resultados, digitando o nome da operação na caixa da coluna **Atividade**. Confira a [Etapa 3: filtrar os resultados da pesquisa](#step-3-filter-the-search-results) para saber mais sobre como filtrar os resultados.

- Clique em **Limpar** para limpar os critérios de pesquisa atuais. O intervalo de datas retorna para os últimos sete dias padrão. Você também pode clicar em **Limpar tudo para mostrar resultados de todas as atividades** para cancelar todas as atividades selecionadas.

- Se 5.000 resultados forem encontrados, você poderá supor que existam provavelmente mais de 5.000 eventos que corresponderam aos critérios de pesquisa. É possível restringir os critérios de pesquisa e executar a pesquisa novamente para retornar menos resultados ou exportar todos os resultados da pesquisa selecionando **Exportar resultados** \> **Baixar todos os resultados**.

### <a name="step-2-view-the-search-results"></a>Etapa 2: Exibir os resultados da pesquisa

Os resultados de uma pesquisa de log de auditoria são exibidos em **Resultados**, na página **Pesquisa de log de auditoria**. Conforme mencionado anteriormente, um máximo de 5.000 eventos (mais recentes) é exibido em incrementos de 150 eventos. Para exibir mais eventos, use a barra de rolagem no painel **Resultados** ou pressione **Shift+End** para exibir os próximos 150 eventos.

Os resultados contêm as seguintes informações sobre cada evento retornado pela pesquisa:

- **Data:**: A data e a hora (no seu horário local) de ocorrência do evento.

- **Endereço IP**: O endereço IP do dispositivo que foi usado quando a atividade foi registrada. O endereço IP é exibido em um formato de endereço IPv4 ou IPv6.

   > [!NOTE]
  > Para alguns serviços, o valor exibido nesse campo pode ser o endereço IP de um aplicativo confiável (por exemplo, Office em aplicativos Web) chamando o serviço em nome de um usuário e não o endereço IP do dispositivo usado por quem realizou a atividade. Além disso, em atividades de administrador (ou atividade realizada por uma conta do sistema) para os eventos relacionados ao Active Directory do Azure, o endereço IP não é registrado e o valor exibido neste campo é `null`.

- **Usuário**: O usuário (ou a conta de serviço) que realizou a ação que disparou o evento.

- **Atividade**: A atividade realizada pelo usuário. Esse valor corresponde às atividades que você selecionou na lista suspensa **Atividades**. Para um evento do log de auditoria de administradores do Exchange, o valor nessa coluna é um cmdlet do Exchange.

- **Item**: O objeto que foi criado ou modificado como resultado da atividade correspondente. Por exemplo, o arquivo que foi exibido ou modificado ou a conta do usuário que foi atualizada. Nem todas as atividades têm um valor nesta coluna.

- **Detalhe**: Informações adicionais sobre uma atividade. Novamente, nem todas as atividades têm um valor.

> [!TIP]
> Clique em um cabeçalho de coluna em **Resultados** para classificar os resultados. Você pode classificar os resultados da A até Z ou de Z até A. Clique no cabeçalho **Data** para classificar os resultados do mais antigo para o mais recente, ou vice-versa.

#### <a name="view-the-details-for-a-specific-event"></a>Exibir os detalhes de um evento específico

É possível visualizar mais detalhes sobre o evento clicando no registro de evento na lista de resultados da pesquisa. É exibida uma página **Detalhes** que contém as propriedades detalhadas do registro do evento. As propriedades exibidas dependem do serviço em que o evento ocorre. Para exibir esses detalhes, clique em **Mais informações**. Para obter descrições, confira [Propriedades detalhadas no log de auditoria](detailed-properties-in-the-office-365-audit-log.md).

![Clique em Mais informações para exibir as propriedades detalhadas do registro de eventos do log de auditoria](../media/6df582ae-d339-4735-b1a6-80914fb77a08.png)

### <a name="step-3-filter-the-search-results"></a>Etapa 3: Filtrar os resultados da pesquisa

Além de classificar, você também pode filtrar os resultados de uma pesquisa de log de auditoria. Este é um ótimo recurso que pode ajudá-lo a filtrar rapidamente os resultados para um usuário ou atividade específica. Você pode criar inicialmente uma pesquisa ampla e depois filtrar rapidamente os resultados para ver eventos específicos. Em seguida, você pode restringir os critérios de pesquisa e executar a pesquisa novamente para retornar um conjunto de resultados menor e mais conciso.

Para filtrar os resultados:

1. Execute uma pesquisa de logs de auditoria.

2. Quando os resultados forem exibidos, clique em **Filtrar resultados**.

   Caixas de palavras-chave são exibidas em cada cabeçalho de coluna.

3. Clique em uma das caixas sob um cabeçalho de coluna e digite uma palavra ou frase, dependendo da coluna na qual você está filtrando. Os resultados serão reajustados dinamicamente para exibir os eventos que correspondem ao seu filtro.

   ![Digite uma palavra no filtro para exibir os eventos que correspondam ao filtro](../media/542dc323-a997-402c-934b-cc5e218e50bc.png)

4. Para limpar um filtro, clique em **X** na caixa de filtro ou clique em **Ocultar filtragem**.

> [!TIP]
> Para exibir eventos do log de auditoria de administradores do Exchange, digite um **-** (traço) na caixa de filtro **Atividade**. Isto exibirá nomes de cmdlets, que aparecem na coluna **Atividade** para eventos de administradores do Exchange. Em seguida, você pode classificar os nomes de cmdlets em ordem alfabética.

### <a name="step-4-export-the-search-results-to-a-file"></a>Etapa 4: Exportar os resultados da pesquisa para um arquivo

É possível exportar os resultados de uma pesquisa de logs de auditoria para um arquivo CSV (valores separados por vírgula) no seu computador local. Você pode abrir esse arquivo no Microsoft Excel e usar recursos como pesquisa, classificação, filtragem e divisão de uma única coluna (que contém várias propriedades) em várias colunas.

1. Execute uma pesquisa de logs de auditoria e, em seguida, reveja os critérios de pesquisa até ter os resultados desejados.

2. Clique em **Exportar resultados** e selecione uma das seguintes opções:

   - **Salvar resultados carregados**: Escolha essa opção para exportar somente as entradas exibidas em **Resultados**, na página **Pesquisa de log de auditoria**. O arquivo CSV baixado contém as mesmas colunas (e dados) exibidos na página (Data, Usuário, Atividade, Item e Detalhes). Uma coluna extra (chamado **Mais**) é incluída no arquivo CSV que contém mais informações da entrada do log de auditoria. Como você está exportando os mesmos resultados que estão carregados (e visíveis) na página **Pesquisa de log de auditoria**, no máximo 5.000 entradas são exportadas.

   - **Baixar todos os resultados** Escolha essa opção para exportar todas as entradas do log de auditoria que correspondem aos critérios de pesquisa. Para um grande conjunto de resultados de pesquisa, escolha essa opção para baixar todas as entradas do log de auditoria, além das 5.000 registros de auditoria que podem ser exibidos na página de **Pesquisa de log de auditoria**. Essa opção baixa os dados brutos do log de auditoria para um arquivo CSV e contém informações adicionais da entrada do log de auditoria em uma coluna chamada **AuditData**. O download do arquivo poderá ser mais demorado se você escolher essa opção de exportação, pois o arquivo pode ser muito maior do que o baixado com a outra opção.

     > [!IMPORTANT]
     > É possível baixar no máximo 50 mil entradas para um arquivo CSV de uma única pesquisa de logs de auditoria. Se 50 mil entradas forem baixadas para o arquivo CSV, você poderá supor que existem provavelmente mais de 50 mil eventos que corresponderam aos critérios de pesquisa. Para exportar mais do que esse limite, tente usar um intervalo de datas para reduzir o número de entradas do log de auditoria. Talvez seja necessário executar várias pesquisas com intervalos de datas menores para exportar mais de 50 mil entradas.

3. Após a seleção de uma opção de exportação, é exibida uma mensagem na parte inferior da janela solicitando que você abra o arquivo CSV, salve-o na pasta Downloads ou salve-o em uma pasta específica.

#### <a name="more-information-about-exporting-and-viewing-audit-log-search-results"></a>Informações adicionais sobre como exportar e exibir resultados de pesquisa de log de auditoria

- Se você baixar todos os resultados da pesquisa, o arquivo CSV incluirá uma coluna chamada **AuditData**, que contém informações adicionais sobre cada evento. Os dados dessa coluna consistem em um objeto JSON contendo várias propriedades do registro de log de auditoria. Cada par *propriedade: valor* no objeto JSON é separado por uma vírgula. Você pode usar a ferramenta transformação JSON no editor do Power Query do Excel para dividir a coluna **AuditData** em várias colunas, de modo que cada propriedade no objeto JSON tenha sua própria coluna. Isso permitirá que você classifique e filtre uma ou mais dessas propriedades. Para obter instruções passo a passo sobre como usar o editor do Power Query para transformar o objeto JSON, confira [Exportar, configurar e exibir registros de log de auditoria](export-view-audit-log-records.md).

  Depois de dividir a coluna **AuditData**, você pode filtrar a coluna **Operações** para exibir as propriedades detalhadas de um tipo específico de atividade.

- A opção **Baixar todos os resultados** baixa os dados brutos do log de auditoria em um arquivo CSV. Esse arquivo contém nomes de coluna diferentes (CreationDate, userIds, Operação, AuditData) que o arquivo que será baixado se você selecionar a opção **Salvar resultados carregados**. Os valores nos dois arquivos CSV diferentes para a mesma atividade também podem ser diferentes. Por exemplo, a atividade da coluna **Ação** no arquivo CSV e pode ter um valor diferente do nome "amigável" que é exibido na coluna **Atividade** da página **Pesquisa de log de auditoria**. Por exemplo, MailboxLogin vs. Usuário conectado à caixa de correio.

- Quando você baixa todos os resultados de uma consulta de pesquisa que contém eventos de diferentes serviços, a coluna **AuditData** do arquivo CSV contém propriedades diferentes, dependendo do serviço no qual a ação foi realizada. Por exemplo, as entradas do Exchange e os logs de auditoria do Azure AD incluem uma propriedade chamada **ResultStatus** que indica se a ação teve êxito ou não. Essa propriedade não está incluída para eventos do SharePoint. Da mesma forma, os eventos do SharePoint têm uma propriedade que identifica a URL do site para atividades relacionadas a arquivos pastas. Para atenuar esse comportamento, considere usar diferentes pesquisas para exportar os resultados de atividades de um único serviço.

  Para obter uma descrição das propriedades listadas na coluna **AuditData** do arquivo CSV quando você baixa todos os resultados e o serviço ao qual cada uma se aplica, veja [Propriedades detalhadas no log de auditoria](detailed-properties-in-the-office-365-audit-log.md).

## <a name="audited-activities"></a>Atividades auditadas

As tabelas nesta seção descrevem as atividades que são auditadas no Office 365. Você pode procurar esses eventos pesquisando o log de auditoria no centro de segurança e conformidade.

Essas tabelas agrupam atividades relacionadas ou as atividades de um serviço específico. As tabelas incluem o nome amigável que é exibido na lista suspensa **Atividades** e o nome da operação correspondente exibida nas informações detalhadas de um registro de auditoria e no arquivo CSV quando você exporta o resultados da pesquisa. Para obter descrições das informações detalhadas, confira [Propriedades detalhadas no log de auditoria](detailed-properties-in-the-office-365-audit-log.md).

Clique em um dos links a seguir para ir até uma tabela específica.

:::row:::
    :::column:::
        [Atividades de arquivo e página](#file-and-page-activities)
    :::column-end:::
    :::column:::
        [Atividades de pasta](#folder-activities)
    :::column-end:::
    :::column:::
        [Atividades de lista do SharePoint](#sharepoint-list-activities)
    :::column-end:::
:::row-end:::

:::row:::
    :::column:::
        [Atividades de compartilhamento e solicitação de acesso](#sharing-and-access-request-activities)
    :::column-end:::
    :::column:::
        [Atividades de sincronização](#synchronization-activities)
    :::column-end:::
    :::column:::
        [Atividades de permissões de site](#site-permissions-activities)
    :::column-end:::
:::row-end:::

:::row:::
    :::column:::
        [Atividades de administração de site](#site-administration-activities)
    :::column-end:::
    :::column:::
        [Atividades de caixa de correio do Exchange](#exchange-mailbox-activities)
    :::column-end:::
    :::column:::
        [Atividades de administração de usuários](#user-administration-activities)
    :::column-end:::
:::row-end:::

:::row:::
    :::column:::
        [Atividades de administração de grupos do Azure AD](#azure-ad-group-administration-activities)
    :::column-end:::
    :::column:::
        [Atividades de administração de aplicativos](#application-administration-activities)
    :::column-end:::
    :::column:::
        [Atividades de administração de funções](#role-administration-activities)
    :::column-end:::
:::row-end:::

:::row:::
    :::column:::
        [Atividades de administração de diretórios](#directory-administration-activities)
    :::column-end:::
    :::column:::
        [Atividades de Descoberta Eletrônica](#ediscovery-activities)
    :::column-end:::
    :::column:::
        [Atividades de Descoberta Eletrônica Avançada](#advanced-ediscovery-activities)
    :::column-end:::
:::row-end:::

:::row:::
    :::column:::
        [Atividades do Power BI](#power-bi-activities)
    :::column-end:::
    :::column:::
        [Microsoft Workplace Analytics](#workplace-analytics-activities)
    :::column-end:::
    :::column:::
        [Atividades do Microsoft Teams](#microsoft-teams-activities)
    :::column-end:::
:::row-end:::

:::row:::
    :::column:::
        [Atividades do Microsoft Teams Healthcare](#microsoft-teams-healthcare-activities)
    :::column-end:::
    :::column:::
        [Atividades de Turnos do Microsoft Teams](#microsoft-teams-shifts-activities)
    :::column-end:::
    :::column:::
        [Atividades do Yammer](#yammer-activities)
    :::column-end:::
:::row-end:::

:::row:::
    :::column:::
        [Atividades do Microsoft Power Automate](#microsoft-power-automate-activities)
    :::column-end:::
    :::column:::
        [Atividades do Microsoft Power Apps](#microsoft-power-apps-activities)
    :::column-end:::
    :::column:::
        [Atividades do Microsoft Stream](#microsoft-stream-activities)
    :::column-end:::
:::row-end:::

:::row:::
    :::column:::
        [Atividades do explorador de conteúdo](#content-explorer-activities)
    :::column-end:::
    :::column:::
        [Atividades de quarentena](#quarantine-activities)
    :::column-end:::
    :::column:::
        [Atividades do Microsoft Forms](#microsoft-forms-activities)
    :::column-end:::
:::row-end:::

:::row:::
    :::column:::
        [Atividades de rótulo de sensibilidade](#sensitivity-label-activities)
    :::column-end:::
    :::column:::
        [Política de retenção e rótulo de retenção de atividades](#retention-policy-and-retention-label-activities)
    :::column-end:::
    :::column:::
        [Atividades do email de resumo](#briefing-email-activities)
    :::column-end:::
:::row-end:::

:::row:::
    :::column:::
        [Atividades do MyAnalytics](#myanalytics-activities)
    :::column-end:::
    :::column:::
        [Atividades das barreiras de informação](#information-barriers-activities)
    :::column-end:::
    :::column:::
        [Atividades de administradores do Exchange](#exchange-admin-audit-log)
    :::column-end:::
:::row-end:::

### <a name="file-and-page-activities"></a>Atividades de arquivo e página

A tabela a seguir descreve as atividades de arquivo e página do SharePoint Online e do OneDrive for Business.

|Nome amigável|Operação|Descrição|
|:-----|:-----|:-----|
|Arquivo acessado|FileAccessed|O usuário ou a conta do sistema acessa um arquivo.|
|(nenhuma)|FileAccessedExtended|Isso está relacionado à atividade "Arquivo acessado" (FileAccessed). Um evento FileAccessedExtended é registrado em log quando a mesma pessoa acessa continuamente um arquivo por um longo período (até 3 horas). <br/><br/> O propósito de registrar eventos FileAccessedExtended em log é reduzir o número de eventos FileAccessed registrados quando um arquivo é acessado continuamente. Isso ajuda a reduzir o ruído de vários registros de FileAccessed para, basicamente, a mesma atividade do usuário e permite que você se concentre no evento FileAccessed inicial (e mais importante).|
|Mudança no rótulo de retenção de um arquivo|ComplianceSettingChanged|Um rótulo de retenção foi aplicado ou removido de um documento. Este evento é acionado quando uma etiqueta de retenção é aplicada manualmente ou automaticamente a uma mensagem.|
|Status de registro alterado para bloqueado|LockRecord|O status do registro de um rótulo de retenção que classifica um documento como um registro foi bloqueado. Isso significa que o documento não pode ser modificado ou excluído. Somente os usuários que possuem pelo menos a permissão de colaborador de um site podem alterar o status do registro de um documento.|
|Status de registro alterado para desbloqueado|UnlockRecord|O status do registro de um rótulo de retenção que classifica um documento como um registro foi debloqueado. Isso significa que o documento pode ser modificado ou excluído. Somente os usuários que possuem pelo menos a permissão de colaborador de um site podem alterar o status do registro de um documento.|
|Arquivo com check-in|FileCheckedIn|O usuário faz check-in de um documento que estava em check-out em uma biblioteca de documentos.|
|Arquivo em check-out|FileCheckedOut|O usuário faz check-out de um documento localizado em uma biblioteca de documentos. Os usuários podem fazer check-out e efetuar alterações em documentos que foram compartilhados com eles.|
|Arquivo copiado|FileCopied|O usuário copia um documento de um site. O arquivo copiado pode ser salvo em outra pasta no site.|
|Arquivo excluído|FileDeleted|O usuário exclui um documento de um site.|
|Arquivo excluído da Lixeira|FileDeletedFirstStageRecycleBin|O usuário exclui um arquivo da lixeira de um site.|
|Arquivo excluído da Lixeira de segundo estágio|FileDeletedSecondStageRecycleBin|O usuário exclui um arquivo da lixeira de segundo estágio de um site.|
|Arquivo excluído marcado como um registro|RecordDelete|Um documento marcado como um registro foi excluído. Um documento é considerado um registro quando o rótulo de retenção, que marca itens como um registro, é aplicado ao conteúdo.|
|Incompatibilidade de confidencialidade em documento detectada|DocumentSensitivityMismatchDetected|O usuário carrega um documento em um site protegido com um rótulo de sensibilidade e o documento possui um rótulo de sensibilidade de prioridade mais alta que o rótulo de sensibilidade aplicado ao site. Por exemplo, um documento chamado Confidencial é carregado em um site chamado Geral. <br/><br/> Esse evento não é acionado se o documento tiver um rótulo de sensibilidade de prioridade mais baixo que o rótulo de sensibilidade aplicado ao site. Por exemplo, um documento chamado Geral é carregado em um site chamado Confidencial. Para obter mais informações sobre a prioridade dos rótulos de sensibilidade, consulte [Prioridade de rótulo (questões do pedido)](sensitivity-labels.md#label-priority-order-matters).|
|Malware detectado no arquivo|FileMalwareDetected|O mecanismo de antivírus do SharePoint detecta malwares em um arquivo.|
|Check-out de arquivo descartado|FileCheckOutDiscarded|O usuário descarta (ou desfaz) um arquivo de check-out. Isso significa que todas as alterações feitas nesse arquivo durante o check-out serão descartadas, e não serão salvas na versão do documento localizada na biblioteca de documentos.|
|Arquivo baixado|FileDownloaded|O usuário baixa um documento de um site.|
|Arquivo modificado|FileModified|O usuário ou a conta do sistema modifica o conteúdo ou as propriedades de um documento em um site.|
|(nenhum)|FileModifiedExtended|Isso está relacionado à atividade "Arquivo modificado" (FileModified). Um evento FileModifiedExtended é registrado em log quando a mesma pessoa altera continuamente um arquivo por um longo período (até 3 horas). <br/><br/> O propósito de registrar eventos FileModifiedExtended em log é reduzir o número de eventos FileModified registrados quando um arquivo é modificado continuamente. Isso ajuda a reduzir o ruído de vários registros de FileModified para o que é essencialmente a mesma atividade do usuário e permite que você se concentre no evento FileModified inicial (e mais importante).|
|Arquivo movido|FileMoved|O usuário move um documento de sua localização atual em um site até uma nova localização.|
|(nenhum)|FilePreviewed|O usuário visualiza documentos em um site do SharePoint ou OneDrive for Business. Esses eventos geralmente ocorrem em grandes volumes com base em uma única atividade, como a exibição de uma galeria de imagens.|
|Consulta de pesquisa realizada|SearchQueryPerformed|O usuário ou a conta do sistema realiza uma pesquisa no SharePoint ou OneDrive for Business. Alguns cenários comuns em que uma conta de serviço executa uma consulta de pesquisa incluem a aplicação de retenção de Descoberta Eletrônica e uma política de retenção a sites e contas do OneDrive, bem como a aplicação automática de rótulos de retenção ou confidencialidade ao conteúdo do site.|
|Todas as versões secundárias do arquivo foram recicladas|FileVersionsAllMinorsRecycled|O usuário exclui todas as versões secundárias do histórico de versões de um arquivo. As versões excluídas são movidas para a lixeira do site.|
|Todas as versões do arquivo foram recicladas|FileVersionsAllRecycled|O usuário exclui todas as versões do histórico de versões de um arquivo. As versões excluídas são movidas para a lixeira do site.|
|Versão do arquivo reciclada|FileVersionRecycled|O usuário exclui uma versão do histórico de versões de um arquivo. A versão excluída é movida para a lixeira do site.|
|Arquivo renomeado|FileRenamed|O usuário renomeia um documento em um site.|
|Arquivo restaurado|FileRestored|O usuário restaura um documento da lixeira de um site. |
|Arquivo carregado|FileUploaded|O usuário carrega um documento em uma pasta em um site.|
|Página exibida|PageViewed|O usuário exibe uma página no site. Isso não inclui usar um navegador da Web para exibir arquivos localizados em uma biblioteca de documentos.|
|(nenhum)|PageViewedExtended|Isso está relacionado à atividade "Página exibida" (PageViewed). Um evento PageViewedExtended é registrado em log quando a mesma pessoa vê continuamente uma página da Web por um longo período (até 3 horas). <br/><br/> O propósito de registrar eventos PageViewedExtended em log é reduzir o número de eventos PageViewed registrados quando uma página é exibida continuamente. Isso ajuda a reduzir o ruído de vários registros de PageViewed para o que é essencialmente a mesma atividade do usuário e permite que você se concentre no evento PageViewed inicial (e mais importante).|
|Exibição sinalizada pelo cliente|ClientViewSignaled|Um cliente do usuário (por exemplo, site ou aplicativo móvel) sinalizou que a página indicada foi exibida pelo usuário. Essa atividade geralmente é registrada após um evento PagePrefetched para uma página. <br/><br/>**OBSERVAÇÃO**: Como os eventos ClientViewSignaled são sinalizados pelo cliente, em vez do servidor, é possível que ele não seja registrado pelo servidor e, portanto, pode não aparecer no log de auditoria. Também é possível que as informações do registro de auditoria não sejam confiáveis. No entanto, como a identidade do usuário é validada por um token usado para criar o sinal, a identidade do usuário listada no registro de auditoria correspondente é precisa. |
|(nenhum)|PagePrefetched|O cliente do usuário (por exemplo, site ou aplicativo móvel) solicitou a página indicada para ajudar a melhorar o desempenho se o usuário navegar por ela. Este evento é registrado para indicar que o conteúdo da página foi servido ao cliente do usuário. Esse evento não é um indício definitivo de que o usuário navegou pela página. <br/><br/> Quando o conteúdo da página é renderizado pelo cliente (conforme a solicitação do usuário), um evento ClientViewSignaled deve ser gerado. Nem todos os clientes oferecem suporte para indicar uma pré-busca e, portanto, algumas atividades pré-buscadas podem ser registradas como eventos PageViewed.|
||||

#### <a name="frequently-asked-questions-about-fileaccessed-and-filepreviewed-events"></a>Perguntas frequentes sobre eventos do FileAccessed e FilePreviewed

**Alguma atividade de não usuário pode acionar registros de auditoria FilePreviewed que contêm um agente de usuário como "OneDriveMpc-Transform_Thumbnail"?**

Não temos conhecimento de cenários em que ações de não usuários gerem eventos como esses. As ações do usuário, como abrir um cartão de perfil do usuário (clicando em seu nome ou endereço de email em uma mensagem no Outlook na Web), gerariam eventos semelhantes.

**As chamadas para o OneDriveMpc-Transform_Thumbnail são sempre acionadas intencionalmente pelo usuário?**

Não. Mas eventos semelhantes podem ser registrados como resultado da pré-busca do navegador.

**Se virmos um evento FilePreviewed vindo de um endereço IP registrado pela Microsoft, isso significa que a visualização foi exibida na tela do dispositivo do usuário?**

Não. O evento pode ter sido registrado como resultado da pré-busca do navegador.

**Existem cenários em que um usuário visualizando um documento gera eventos FileAccessed?**

Ambos eventos FilePreviewed e FileAccessed indicam que a chamada de um usuário levou à leitura do arquivo (ou leitura de uma renderização em miniatura do arquivo). Embora esses eventos tenham a intenção de se alinhar com a intenção de visualização vs. intenção de acesso, a distinção do evento não é uma garantia da intenção do usuário.

#### <a name="the-appsharepoint-user-in-audit-records"></a>O usuário app\@sharepoint em registros de auditoria

Nos registros de auditoria para algumas atividades de arquivo (e outras atividades relacionadas ao SharePoint), você pode perceber que o usuário que executou a atividade (identificado nos campos Usuário e ID do usuário) é app@sharepoint. Isso indica que o "usuário" que executou a atividade é um aplicativo. Nesse caso, o aplicativo recebeu permissões no SharePoint para executar ações em toda a organização (como pesquisar em um site do SharePoint ou em uma conta do OneDrive) em nome de um usuário, administrador ou serviço. Esse processo de conceder permissões a um aplicativo é chamado de acesso *Somente Aplicativo do SharePoint*. Isso indica que a autenticação apresentada ao SharePoint para executar uma ação foi realizada por um aplicativo, em vez de um usuário. É por isso que o usuário app@sharepoint é identificado em determinados registros de auditoria. Para obter mais informações, confira [Conceder acesso usando Somente Aplicativo do SharePoint](/sharepoint/dev/solution-guidance/security-apponly-azureacs).

Por exemplo, app@sharepoint é frequentemente identificado como o usuário dos eventos "Consulta de pesquisa realizada" e "Arquivo acessado". Isso ocorre porque um aplicativo com acesso Somente Aplicativo do SharePoint em sua organização realiza consultas de pesquisa e acessa arquivos ao aplicar políticas de retenção a sites e contas do OneDrive.

Aqui estão alguns outros cenários em que app@sharepoint pode ser identificado em um registro de auditoria como o usuário que executou uma atividade:

- Grupos do Microsoft 365. Quando um usuário ou administrador cria um novo grupo, os registros de auditoria são gerados para criar um conjunto de sites, atualizar listas e adicionar membros a um grupo do SharePoint. Essas tarefas são executadas em nome do usuário que criou o grupo.

- Microsoft Teams. Semelhante aos grupos do Microsoft 365, os registros de auditoria são gerados para criar um conjunto de sites, atualizar listas e adicionar membros a um grupo do SharePoint quando uma equipe é criada.

- Recursos de conformidade. Quando um administrador implementa recursos de conformidade, como políticas de retenção, bloqueios de Descoberta Eletrônica e aplicação automática de rótulos de confidencialidade.

Neste e em outros cenários, você também notará que vários registros de auditoria com o usuário especificado como app@sharepoint foram criados dentro de um período de tempo muito curto, geralmente dentro de alguns segundos. Isso também indica que provavelmente eles foram disparados pela mesma tarefa iniciada pelo usuário. Além disso, os campos ApplicationDisplayName e EventData no registro de auditoria podem ajudar a identificar o cenário ou aplicativo que acionou o evento.

### <a name="folder-activities"></a>Atividades de pasta

A tabela a seguir descreve as atividades de pasta do SharePoint Online e do OneDrive for Business. Conforme explicado anteriormente, os registros de auditoria para algumas atividades do SharePoint indicarão que o usuário app@sharepoint executou a atividade em nome do usuário ou administrador que iniciou a ação. Para saber mais, confira o usuário [app\@sharepoint em registros de auditoria](#the-appsharepoint-user-in-audit-records).

|Nome amigável|Operação|Descrição|
|:-----|:-----|:-----|
|Pasta copiada|FolderCopied|O usuário copia uma pasta de um site para outro local do SharePoint ou do OneDrive for Business.|
|Pasta criada|FolderCreated|O usuário cria uma pasta no site.|
|Pasta excluída|FolderDeleted|O usuário exclui uma pasta do site.|
|Pasta excluída da Lixeira|FolderDeletedFirstStageRecycleBin|O usuário exclui uma pasta da Lixeira no site.|
|Pasta excluída da Lixeira de segundo estágio|FolderDeletedSecondStageRecycleBin|O usuário exclui uma pasta da Lixeira de segundo estágio no site.|
|Pasta modificada|FolderModified|O usuário modifica uma pasta no site. Isso inclui alterar os metadados da pasta, como propriedades e marcas.|
|Pasta movida|FolderMoved|O usuário move uma pasta para um local diferente no site.|
|Pasta renomeada|FolderRenamed|O usuário renomeia uma pasta no site.|
|Pasta restaurada|FolderRestored|O usuário restaura uma pasta da lixeira de um site.|
||||

### <a name="sharepoint-list-activities"></a>Atividades de lista do SharePoint

A tabela a seguir descreve as atividades relacionadas quando os usuários interagem com listas e itens de lista do SharePoint Online. Conforme explicado anteriormente, os registros de auditoria para algumas atividades do SharePoint indicarão que o usuário app@sharepoint executou a atividade em nome do usuário ou administrador que iniciou a ação. Para saber mais, confira o usuário [app\@sharepoint em registros de auditoria](#the-appsharepoint-user-in-audit-records).

|Nome amigável|Operação|Descrição|
|:-----|:-----|:-----|
|Lista criada|ListCreated|Um usuário criou uma lista do SharePoint.|
|Coluna de lista criada|ListColumnCreated|Um usuário criou uma coluna de lista do SharePoint. Uma coluna de lista é uma coluna anexada a uma ou mais listas do SharePoint.|
|Tipo de conteúdo de lista criado|ListContentTypeCreated|Um usuário criou um tipo de conteúdo de lista. Um tipo de conteúdo de lista é um tipo de conteúdo anexado a uma ou mais listas do SharePoint.|
|Item de lista criado|ListItemCreated|Um usuário criou um item em uma lista do SharePoint existente.|
|Coluna de site criada|SiteColumnCreated|Um usuário criou uma coluna de site do SharePoint. Uma coluna de site é uma coluna que não está anexada a uma lista. Uma coluna de site é também uma estrutura de metadados que pode ser usada por qualquer lista em uma determinada Web.|
|Tipo de conteúdo de site criado|ContentType do site criado|Um usuário criou um tipo de conteúdo de site. Um tipo de conteúdo de site é um tipo de conteúdo anexado ao site primário.|
|Lista excluída|ListDeleted|Um usuário excluiu uma lista do SharePoint.|
|Coluna de lista excluída|Coluna de Lista Excluída|Um usuário excluiu uma coluna de lista do SharePoint.|
|Tipo de conteúdo de lista excluído|ListContentTypeDeleted|Um usuário excluiu um tipo de conteúdo de lista.|
|Item de lista excluído|Item de Lista Excluído|Um usuário excluiu um item de lista do SharePoint.|
|Coluna de site excluída|SiteColumnDeleted|Um usuário excluiu uma coluna de site do SharePoint.|
|Tipo de conteúdo de site excluído|SiteContentTypeDeleted|Um usuário excluiu um tipo de conteúdo de site.|
|Item de lista reciclado|ListItemRecycled|Um usuário moveu um item de lista do SharePoint para a Lixeira.|
|Lista restaurada|ListRestored|Um usuário restaurou uma lista do SharePoint da Lixeira.|
|Item de lista restaurado|ListItemRestored|Um usuário restaurou um item de lista do SharePoint da Lixeira.|
|Lista atualizada|ListUpdated|Um usuário atualizou uma lista do SharePoint modificando uma ou mais propriedades.|
|Coluna da lista atualizada|ListColumnUpdated|Um usuário atualizou uma coluna de lista do SharePoint modificando uma ou mais propriedades.|
|Tipo de conteúdo de lista atualizado|ListContentTypeUpdated|Um usuário atualizou um tipo de conteúdo de lista modificando uma ou mais propriedades.|
|Item de lista atualizado|ListItemUpdated|Um usuário atualizou um item de lista do SharePoint modificando uma ou mais propriedades.|
|Coluna de site atualizada|SiteColumnUpdated|Um usuário atualizou uma coluna de site do SharePoint modificando uma ou mais propriedades.|
|Tipo de conteúdo de site atualizado|SiteContentTypeUpdated|Um usuário atualizou um tipo de conteúdo de site modificando uma ou mais propriedades.|
||||

### <a name="sharing-and-access-request-activities"></a>Atividades de compartilhamento e solicitação de acesso

A tabela a seguir descreve as atividades de compartilhamento e solicitação de acesso do usuário no SharePoint Online e no OneDrive for Business. Para eventos de compartilhamento, a coluna **Detalhes** em **Resultados** identifica o nome do usuário ou do grupo com o qual o item foi compartilhado e se esse usuário ou grupo é um membro ou convidado na sua organização. Para saber mais, veja [Usar a auditoria de compartilhamento no log de auditoria](use-sharing-auditing.md).

> [!NOTE]
> Os usuários podem ser *membros* ou *convidados* com base na propriedade UserType do objeto de usuário. Um membro é geralmente um funcionário, enquanto um convidado é geralmente um colaborador fora da sua organização. Quando um usuário aceita um convite de compartilhamento (e ainda não faz parte da sua organização), uma conta de convidado é criada para ele no diretório da sua organização. Quando esse usuário convidado tem uma conta no seu diretório, recursos podem ser compartilhados diretamente com ele (sem a necessidade de um convite).

|Nome amigável|Operação|Descrição|
|:-----|:-----|:-----|
|Nível de permissão adicionado ao conjunto de sites|PermissionLevelAdded|Um nível de permissão foi adicionado a um conjunto de sites.|
|Solicitação de acesso aceita|AccessRequestAccepted|Uma solicitação de acesso a um site, pasta ou documento foi aceita, e o usuário solicitante recebeu acesso.|
|Convite de compartilhamento aceito|SharingInvitationAccepted|O usuário (membro ou convidado) aceitou um convite de compartilhamento e recebeu acesso a um recurso. Esse evento inclui informações sobre o usuário que foi convidado e sobre o endereço de email que foi usado para aceitar o convite (eles podem ser diferentes). Com frequência, essa atividade é acompanhada por um segundo evento que descreve como o usuário obteve acesso ao recurso; por exemplo, a adição do usuário a um grupo com acesso ao recurso.|
|Convite de compartilhamento bloqueado|SharingInvitationBlocked|Um convite de compartilhamento enviado por um usuário em sua organização é bloqueado devido a uma política de compartilhamento externo que permite ou nega o compartilhamento externo com base no domínio do usuário de destino. Nesse caso, o convite de compartilhamento foi bloqueado porque: <br/> O domínio do usuário de destino não está incluído na lista de domínios permitidos. <br/> Ou <br/> O domínio do usuário de destino está incluído na lista de domínios bloqueados. <br/> Confira mais informações sobre como permitir ou bloquear o compartilhamento externo com base em domínios em [Compartilhamento de domínios restritos no SharePoint Online e no OneDrive for Business](/sharepoint/restricted-domains-sharing).|
|Solicitação de acesso criada|AccessRequestCreated|O usuário solicita acesso a um site, pasta ou documento que ele não tem permissões para acessar.|
|Link compartilhável da empresa criado |CompanyLinkCreated|O usuário criou um link de toda a empresa para um recurso. os links de toda a empresa só podem ser usados pelos membros da sua organização. Eles não podem ser usados por convidados.|
|Um link anônimo criado|AnonymousLinkCreated|O usuário criou um link anônimo para um recurso. Qualquer pessoa com esse link pode acessar o recurso sem ter que se autenticar.|
|Link seguro criado|SecureLinkCreated|Um link de compartilhamento seguro foi criado para esse item.|
|Convite de compartilhamento criado|SharingInvitationCreated|O usuário compartilhou um recurso do SharePoint Online ou do OneDrive for Business com um usuário que não está no diretório da sua organização.|
|Link seguro excluído|SecureLinkDeleted|Um link de compartilhamento seguro foi excluído.|
|Solicitação de acesso negada |AccessRequestDenied|Uma solicitação de acesso a um site, pasta ou documento foi negada.|
|Link compartilhável da empresa removido|CompanyLinkRemoved|O usuário removeu um link de empresa para um recurso. O link não pode mais ser usado para acessar o recurso.|
|Link anônimo removido|AnonymousLinkRemoved|O usuário removeu um link anônimo para um recurso. O link não pode mais ser usado para acessar o recurso.|
|Arquivo, pasta ou site compartilhado|SharingSet|O usuário (membro ou convidado) compartilhou um arquivo, uma pasta ou um site no SharePoint ou no OneDrive for Business com um usuário no diretório da sua organização. O valor na coluna **Detalhes** dessa atividade identifica o nome do usuário com o qual o recurso foi compartilhado e se esse usuário é um membro ou convidado. <br/><br/> Com frequência, essa atividade é acompanhada por um segundo evento que descreve como o usuário obteve acesso ao recurso; por exemplo, a adição do usuário a um grupo com acesso ao recurso.|
|Solicitação de acesso atualizado|AccessRequestUpdated|Uma solicitação de acesso a um item foi atualizada.|
|Link anônimo atualizado |AnonymousLinkUpdated|O usuário atualizou um link anônimo para um recurso. O campo atualizado é incluído na propriedade EventData quando você exporta os resultados da pesquisa.|
|Convite de compartilhamento atualizado|SharingInvitationUpdated|Um convite de compartilhamento externo foi atualizado.|
|Link anônimo usado|AnonymousLinkUsed|Um usuário anônimo acessou um recurso usando um link anônimo. A identidade do usuário pode ser desconhecida, mas você pode obter outros detalhes, como seu endereço IP.|
|Arquivo, pasta ou site não compartilhado|SharingRevoked|O usuário (membro ou convidado) cancelou o compartilhamento de um arquivo, pasta ou site que havia sido compartilhado com outro usuário.|
|Link compartilhável da empresa usado|CompanyLinkUsed|O usuário acessou um recurso usando um link de empresa.|
|Link seguro usado|SecureLinkUsed|Um usuário usou um link seguro.|
|Usuário adicionado a um link seguro|AddedToSecureLink|Um usuário foi adicionado à lista de entidades que podem usar um link de compartilhamento seguro.|
|Usuário removido do link seguro|RemovedFromSecureLink|Um usuário foi removido da lista de entidades que podem usar um link de compartilhamento seguro.|
|Convite de compartilhamento retirado|SharingInvitationRevoked|O usuário retirou um convite de compartilhamento para um recurso. |
||||

### <a name="synchronization-activities"></a>Atividades de sincronização

A tabela a seguir lista as atividades de sincronização de arquivos no SharePoint Online e no OneDrive for Business.

|Nome amigável|Operação|Descrição|
|:-----|:-----|:-----|
|Computador com permissão para sincronizar arquivos|ManagedSyncClientAllowed|O usuário estabelece com êxito uma relação de sincronização com um site. A relação de sincronização é bem-sucedida porque o computador do usuário é membro de um domínio que foi adicionado à lista de domínios (chamada de *lista de lista de destinatários seguros*) que podem acessar bibliotecas de documentos em sua organização. <br/><br/> Para obter mais informações sobre esse recurso, confira [Usar os cmdlets do Windows PowerShell para habilitar a sincronização do OneDrive para domínios que estão na Lista de Destinatários Confiáveis](/powershell/module/sharepoint-online/).|
|Computador impedido de sincronizar arquivos|UnmanagedSyncClientBlocked|O usuário tenta estabelecer uma relação de sincronização com um site em um computador que não é membro do domínio da sua organização ou que é membro de um domínio que não foi adicionado à lista de domínios (chamada de *lista de destinatários seguros*) que podem acessar bibliotecas de documentos na sua organização. A relação de sincronização não é permitida e o computador do usuário é impedido de sincronizar, fazer download ou fazer upload de arquivos em uma biblioteca de documentos. <br/><br/> Para obter informações sobre esse recurso, confira [Usar os cmdlets do Windows PowerShell para habilitar a sincronização do OneDrive para domínios que estão na Lista de Destinatários Confiáveis](/powershell/module/sharepoint-online/).|
|Arquivos baixados no computador|FileSyncDownloadedFull|O usuário estabelece uma relação de sincronização e baixa arquivos de uma biblioteca de documentos com êxito pela primeira vez em seu computador.|
|Alterações de arquivo baixadas no computador|FileSyncDownloadedPartial|O usuário baixa com êxito quaisquer alterações nos arquivos de uma biblioteca de documentos. Essa atividade indica que todas as alterações que foram feitas nos arquivos da biblioteca de documentos foram baixadas no computador do usuário. Apenas as alterações foram baixadas porque a biblioteca de documentos já foi baixada pelo usuário (conforme indicado pela atividade **Arquivos baixados no computador**).|
|Arquivos carregados na biblioteca de documentos|FileSyncUploadedFull|O usuário estabelece uma relação de sincronização e carrega arquivos em uma biblioteca de documentos com êxito pela primeira vez em seu computador.|
|Alterações de arquivo carregadas na biblioteca de documentos|FileSyncUploadedPartial|O usuário carrega com êxito em uma biblioteca de documentos as alterações feitas em arquivos. Esse evento indica que quaisquer alterações feitas na versão local de um arquivo de uma biblioteca de documentos foram carregadas com êxito para a biblioteca de documentos. Apenas alterações são carregadas porque esses arquivos já foram carregados pelo usuário (conforme indicado pela atividade **Arquivos carregados na biblioteca de documentos**).|
||||

### <a name="site-permissions-activities"></a>Atividades de permissões de site

A tabela a seguir lista os eventos relacionados para atribuir permissões no SharePoint e usar grupos para conceder (e revogar) acesso aos sites. Conforme explicado anteriormente, os registros de auditoria para algumas atividades do SharePoint indicarão que o usuário app@sharepoint executou a atividade em nome do usuário ou administrador que iniciou a ação. Para saber mais, confira o usuário [app\@sharepoint em registros de auditoria](#the-appsharepoint-user-in-audit-records).

|Nome amigável|Operação|Descrição|
|:-----|:-----|:-----|
|Administrador de conjunto de sites adicionado|SiteCollectionAdminAdded|O proprietário ou administrador do conjunto de sites adiciona uma pessoa como administrador de conjunto de sites para um site. Os administradores do conjunto de sites têm permissões de controle total para o conjunto de sites e todos os subsites. Essa atividade também será registrada quando um administrador conceder acesso a uma conta do usuário do Onedrive (editando o perfil do usuário no centro de administração do SharePoint ou [usando o centro de administração do Microsoft 365](/office365/admin/add-users/get-access-to-and-back-up-a-former-user-s-data)).|
|Usuário ou grupo adicionado ao grupo do SharePoint|AddedToGroup|O usuário adicionou um membro ou convidado a um grupo do SharePoint. Esta pode ter sido uma ação intencional ou o resultado de outra atividade, como um evento de compartilhamento.|
|Herança de nível de permissão interrompida|PermissionLevelsInheritanceBroken|Um item foi alterado para que ele não mais herde os níveis de permissão de seu pai.|
|Compartilhamento de herança interrompido|SharingInheritanceBroken|Um item foi alterado para que não herde mais as permissões de compartilhamento de seu pai.|
|Grupo criado|GroupAdded|O proprietário ou administrador do site cria um grupo para um site ou realiza uma tarefa que resulta na criação de um grupo. Por exemplo, quando um usuário cria um link para compartilhar um arquivo pela primeira vez, um grupo do sistema é adicionado ao site do OneDrive for Business do usuário. Esse evento também pode ser um resultado de um usuário que está criando um link com permissões de edição em um arquivo compartilhado.|
|Grupo excluído|GroupRemoved|O usuário exclui um grupo de um site.|
|Configuração da solicitação de acesso modificada|WebRequestAccessModified|As configurações de solicitação de acesso foram modificadas em um site.|
|Configuração “Membros Podem Compartilhar" modificado|WebMembersCanShareModified|A configuração **Membros Podem Compartilhar** foi modificada em um site.|
|Nível de permissão modificado em um conjunto de sites|PermissionLevelModified|Um nível de permissão foi alterado em um conjunto de sites.|
|Permissões de site modificadas|SitePermissionsModified|O administrador ou proprietário do site (ou conta do sistema) altera o nível de permissão atribuído a um grupo em um site. Esta atividade também é registrada se todas as permissões forem removidas de um grupo.<br/><br/> **OBSERVAÇÃO**: Esta operação foi preterida no SharePoint Online. Para localizar os eventos relacionados, você pode procurar outras atividades relacionadas à permissão, como **Administrador do conjunto de sites adicionado**, **Usuário ou grupo adicionado ao grupo do SharePoint**, **Usuário permitido para criar grupo**, **Grupo criado**, e **Grupo excluído.**|
|Nível de permissão removido do conjunto de sites|PermissionLevelRemoved|Um nível de permissão foi removido de um conjunto de sites.|
|Administrador de conjunto de sites removido|SiteCollectionAdminRemoved|O proprietário ou administrador do conjunto de sites remove uma pessoa como administrador de conjunto de sites para um site. Essa atividade também será registrada quando um administrador remover a si mesmo da lista de administradores de conjunto de sites para a conta do usuário do OneDrive (editando o perfil de usuário no centro de administração do SharePoint).  Para retornar essa atividade nos resultados de pesquisa do log de auditoria, é preciso procurar todas as atividades.|
|Usuário ou grupo removido do grupo do SharePoint|RemovedFromGroup|O usuário removeu um membro ou convidado de um grupo do SharePoint. Essa pode ter sido uma ação intencional ou o resultado de outra atividade, como um evento de cancelamento de compartilhamento.|
|Permissões de administrador de site solicitadas|SiteAdminChangeRequest|O usuário solicita ser adicionado como administrador de conjunto de sites para um conjunto de sites. Administradores de conjunto de sites têm permissões de controle total para o conjunto de sites e todos os subsites.|
|Herança de compartilhamento restaurada|SharingInheritanceReset|Uma alteração foi feita para que um item herde permissões de compartilhamento de seu pai.|
|Grupo atualizado|GroupUpdated|O proprietário ou administrador do site altera as configurações de um grupo para um site. Isso pode incluir alterar o nome do grupo, quem pode visualizar ou editar a participação no grupo e como as solicitações de associação são manipuladas.|
||||

### <a name="site-administration-activities"></a>Atividades de administração do site

A tabela a seguir lista os eventos decorrentes de tarefas de administração de sites no SharePoint Online. Conforme explicado anteriormente, os registros de auditoria para algumas atividades do SharePoint indicarão que o usuário app@sharepoint executou a atividade em nome do usuário ou administrador que iniciou a ação. Para saber mais, confira o usuário [app\@sharepoint em registros de auditoria](#the-appsharepoint-user-in-audit-records).

|Nome amigável|Operação|Descrição|
|:-----|:-----|:-----|
|Local de dados permitido adicionado|AllowedDataLocationAdded|Um administrador global ou do SharePoint adicionou um local de dados permitido em um ambiente multigeográfico.|
|Agente de usuário isento adicionado|ExemptUserAgentSet|Um administrador global ou do SharePoint adicionou um agente de usuário à lista de agentes de usuário isentos no centro de administração do SharePoint.|
|Administrador de localização geográfica adicionado|GeoAdminAdded|Um administrador global ou do SharePoint adicionou um usuário como um administrador geográfico de um local.|
|Usuário com permissão para criar grupos|AllowGroupCreationSet|O proprietário ou administrador do site adiciona um nível de permissão a um site, que permite que um usuário com essa permissão crie um grupo para esse site.|
|Movimentação geográfica do site cancelada|SiteGeoMoveCancelled|Um administrador global ou do SharePoint cancela com êxito uma movimentação geográfica do site do SharePoint ou do OneDrive. O recurso do Modelo Multigeográfico permite que uma organização abranja várias áreas geográficas do datacenter da Microsoft, chamadas geos. Para obter mais informações, confira [Funcionalidades multigeográficas do Onedrive e do SharePoint Online](../enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md).|
|Política de compartilhamento alterada|SharingPolicyChanged|Um administrador global ou do SharePoint alterou uma política de compartilhamento do SharePoint usando o portal de administração do Microsoft 365, o portal de administração do SharePoint ou o Shell de Gerenciamento do SharePoint Online. Qualquer alteração nas configurações da política de compartilhamento na sua organização será registrada. A política que foi alterada é identificada no campo **ModifiedProperties** nas propriedades detalhadas do registro de evento.|
|Política de acesso a dispositivo alterada|DeviceAccessPolicyChanged|Um administrador global ou do SharePoint alterou a política de dispositivos não gerenciados para sua organização. Esta política controla o acesso ao SharePoint, OneDrive e ao Microsoft 365 de dispositivos que não estão associados à sua organização. Configurar esta política requer uma assinatura do Enterprise Mobility + Security. Para obter informações, consulte [Controlar o acesso de dispositivos gerenciados](/sharepoint/control-access-from-unmanaged-devices).|
|Agentes de usuário isentos alterados|CustomizeExemptUsers|Um administrador global ou do Microsoft Office SharePoint Online personalizou a lista de agentes de usuário isentos no Centro de administração do SharePoint. Você pode especificar quais agentes de usuário deseja se isenta do recebimento de uma página da Web inteira para o índice. Isso significa que, quando um agente de usuário especificado como isento encontra um formulário do InfoPath, o formulário retorna como um arquivo XML, em vez de uma página da Web inteira. Isso torna a indexação de formulários do InfoPath mais rápida.|
|Política de acesso à rede alterada|NetworkAccessPolicyChanged|Um administrador global do ou do SharePoint alterou a política de acesso baseado no local (também chamada de limite de rede confiável) no centro de administração do SharePoint ou usando o PowerShell do SharePoint Online. Esse tipo de política controla quem pode acessar os recursos do SharePoint e do OneDrive em sua organização com base em intervalos de endereços IP autorizados, especificados por você. Para saber mais, confira [Controlar o acesso aos dados do SharePoint Online e do Onedrive com base no local de rede](/sharepoint/control-access-based-on-network-location).|
|Movimentação geográfica do site concluída|SiteGeoMoveCompleted|Uma movimentação geográfica do site que foi agendada por um administrador global em sua organização foi concluído com sucesso.  O recurso do Modelo Multigeográfico permite que uma organização abranja várias áreas geográficas do datacenter da Microsoft, chamadas geos. Para obter mais informações, confira [Funcionalidades multigeográficas do Onedrive e do SharePoint Online no Office 365](../enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md).|
|Conexão Enviar Para criada|SendToConnectionAdded|Um administrador global ou do Microsoft Office SharePoint Online cria uma nova conexão enviar para na página de gerenciamento de registros no Centro de administração do SharePoint. Uma conexão enviar para Especifica configurações para um repositório de documentos ou um centro de registros. Quando você cria uma conexão enviar para, um organizador de conteúdo pode enviar documentos para o local especificado.|
|Conjunto de sites criado|SiteCollectionCreated|Um administrador global ou do SharePoint cria um conjunto de sites na sua organização do SharePoint Online ou um usuário provisiona seu site do OneDrive for Business.|
|Site do hub órfão excluído|HubSiteOrphanHubDeleted|Um administrador global ou do SharePoint excluiu um site do hub órfão, que é um site do hub que não tem sites associados a ele. Um hub órfão provavelmente é causado pela exclusão do site do hub original.|
|Conexão Enviar Para excluída|SendToConnectionRemoved|Um administrador global ou do SharePoint exclui uma conexão Enviar Para na página de gerenciamento de Registros no centro de administração do SharePoint.|
|Site excluído|SiteDeleted|O administrador do site exclui um arquivo.|
|Visualização de documentos habilitada|PreviewModeEnabledSet|O administrador do site habilita a visualização de documentos para um site.|
|Fluxo de trabalho legado habilitado|LegacyWorkflowEnabledSet|O administrador ou proprietário do site adiciona o tipo de conteúdo Tarefa de fluxo de trabalho do SharePoint 2013 ao site. Os administradores globais também podem ativar fluxos de trabalho para toda a organização no Centro de Administração do SharePoint.|
|Office on Demand habilitado|OfficeOnDemandSet|O administrador do site habilita o Office on Demand, que permite aos usuários acessar a versão mais recente dos aplicativos da área de trabalho do Office. O Office on Demand está habilitado no Centro de administração do SharePoint e requer uma assinatura do Microsoft 365, que inclui os aplicativos completos do Office instalados.|
|Fonte de resultados habilitada para Pesquisas de Pessoas|PeopleResultsScopeSet|O administrador do site cria a fonte de resultado para Pesquisas de Pessoas em um site.|
|RSS feeds habilitados|NewsFeedEnabledSet|O proprietário ou administrador do site habilita RSS feeds para um site. Os administradores globais podem habilitar RSS feeds para toda a organização no Centro de administração do SharePoint.|
|Site associado ao site do hub|HubSiteJoined|Um proprietário de site associa seus sites a um site do hub.|
|Site do hub registrado|HubSiteRegistered|Um administrador global ou do SharePoint cria um site do hub. Os resultados são que o site é registrado para ser um site do hub.|
|Local de dados permitido removido|AllowedDataLocationDeleted|Um administrador global ou do SharePoint removeu um local de dados permitido em um ambiente multigeográfico.|
|Administrador de localização geográfica removido|GeoAdminDeleted|Um administrador global ou do SharePoint removeu um usuário como um administrador geográfico de um local.|
|Site renomeado|SiteRenamed|O proprietário ou administrador do site renomeia um site|
|Movimentação geográfica do site agendada|SiteGeoMoveScheduled|Um administrador global ou do SharePoint agenda com êxito uma movimentação geográfica do site do SharePoint ou do OneDrive. O recurso do Modelo Multigeográfico permite que uma organização abranja várias áreas geográficas do datacenter da Microsoft, chamadas geos. Para obter mais informações, confira [Funcionalidades multigeográficas do Onedrive e do SharePoint Online no Office 365](../enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md).|
|Definir site do host|HostSiteSet|Um administrador global ou do SharePoint altera o site designado para hospedar sites pessoais ou do OneDrive for Business.|
|Definir a cota de armazenamento para uma localização geográfica|GeoQuotaAllocated|Um administrador global ou do SharePoint configurou a cota de armazenamento para uma localização geográfica em um ambiente multigeográfico.|
|Site desvinculado do site do hub|HubSiteUnjoined|Um proprietário de site dissocia o site de um site do hub.|
|Site do hub não registrado|HubSiteUnregistered|Um administrador global ou do SharePoint cancela registro de um site como um site do hub. Quando o registro de um site do hub é cancelado, ele não funciona mais como um site do hub.|
||||

### <a name="exchange-mailbox-activities"></a>Atividades de caixa de correio do Exchange

A tabela a seguir lista as atividades que podem ser registradas pelo log de auditoria da caixa de correio. As atividades de caixa de correio executadas pelo proprietário da caixa de correio, por um usuário delegado ou por um administrador do são automaticamente registradas no log de auditoria por até 90 dias. É possível que um administrador desabilite o registro em log de auditoria da caixa de correio para todos os usuários em sua organização. Nesse caso, nenhuma ação da caixa de correio do usuário será registrada. Para saber mais, consulte [Gerenciar a auditoria da caixa de correio](enable-mailbox-auditing.md).

 Você também pode procurar atividades de caixa de correio usando o cmdlet [Search-MailboxAuditLog](/powershell/module/exchange/search-mailboxauditlog) no PowerShell do Exchange Online.

|Nome amigável|Operação|Descrição|
|:-----|:-----|:-----|
|Itens de caixa de correio acessados|MailItemsAccessed|As mensagens foram lidas ou acessadas na caixa de correio. Os registros de auditoria dessa atividade são disparados de duas maneiras: quando um cliente de e-mail (como o Outlook) executa uma operação de vinculação em mensagens ou quando os protocolos de e-mail (como o Exchange ActiveSync ou IMAP) sincronizam em uma pasta de e-mail. Essa atividade é registrada apenas aos usuários com uma licença do Office 365 ou do Microsoft 365 E5. A análise de registros de auditoria dessa atividade é útil ao investigar uma conta de e-mail comprometida. Para obter mais informações, consulte a seção "Acesso aos eventos cruciais de investigações" em [Auditoria avançada](advanced-audit.md#access-to-crucial-events-for-investigations). |
|Permissões de caixa de correio delegada adicionadas|Add-MailboxPermission|Um administrador atribuiu a um usuário (conhecido como um representante) a permissão da caixa de correio FullAccess para a caixa de correio de outra pessoa. A permissão FullAccess permite que o representante abra a caixa de correio de outra pessoa e leia e gerencie o conteúdo da caixa de correio.|
|Adicionado ou removido usuário com acesso delegado à pasta de calendário|UpdateCalendarDelegation|Um usuário foi adicionado ou removido como um representante para o calendário da caixa de correio de outro usuário. A delegação de calendário concede a outra pessoa na mesma organização permissões para gerenciar o calendário do proprietário da caixa de correio.|
|Permissões adicionadas à pasta|AddFolderPermissions|Uma permissão da pasta foi adicionada. As permissões de pasta controlam quais usuários da sua organização podem acessar as pastas em uma caixa de correio e as mensagens localizadas nessas pastas.|
|Mensagens copiadas para outra pasta|Copiar|Uma mensagem foi copiada para outra pasta.|
|Criação de item de caixa de correio|Criar|Um item é criado nas pastas Calendário, Contatos, Anotações ou Tarefas da caixa de correio. Por exemplo, uma nova solicitação de reunião é criada. Criar, enviar ou receber uma mensagem não é auditada. Criar pastas de caixa de correio também não é uma ação auditada.|
|Criada nova regra da caixa de entrada do Outlook Web App|New-InboxRule|Um proprietário da caixa de correio ou outro usuário com acesso à caixa de correio criou uma regra da caixa de entrada do Outlook Web App.|
|Mensagens excluídas da pasta Itens Excluídos|SoftDelete|Uma mensagem foi permanentemente excluída ou foi excluída da pasta Itens Excluídos. Esses itens são movidos para a pasta Itens Recuperáveis. As mensagens também são movidas para a pasta Itens Recuperáveis quando um usuário as seleciona e pressiona **Shift+Delete**.|
|Mensagem rotulada como um registro|ApplyRecordLabel|Uma mensagem foi classificada como um registro. Isso ocorre quando um rótulo de retenção que classifica o conteúdo como um registro é automaticamente aplicado a uma mensagem.|
|Mensagens movidas para outra pasta|Mover|Uma mensagem foi movida para outra pasta.|
|Mensagens movidas para a pasta Itens Excluídos|MoveToDeletedItems|Uma mensagem foi excluída e movida para a pasta Itens Excluídos.|
|Permissão de pasta modificada|UpdateFolderPermissions|Uma permissão da pasta foi alterada. As permissões de pasta controlam quais usuários da organização podem acessar as pastas de uma caixa de correio e as mensagens incluídas nessas pastas.|
|Modificada regra de caixa de entrada do Outlook Web App|Set-InboxRule|Um proprietário da caixa de correio ou outro usuário com acesso à caixa de correio modificou uma regra da caixa de entrada usando o Outlook Web App.|
|Mensagens limpas da caixa de correio|HardDelete|Uma mensagem foi limpa da pasta Itens Recuperáveis (permanentemente excluída da caixa de correio).|
|Permissões de caixa de correio do representante removidas|Remove-MailboxPermission|Um administrador removeu a permissão FullAccess (que foi atribuída a um representante) da caixa de correio de uma pessoa. Depois que a permissão FullAccess for removida, o representante não pode abrir a caixa de correio de outra pessoa ou acessar nenhum conteúdo dela.|
|Permissões removidas da pasta|RemoveFolderPermissions|Uma permissão da pasta foi removida. As permissões de pasta controlam quais usuários da sua organização podem acessar as pastas em uma caixa de correio e as mensagens localizadas nessas pastas.|
|Mensagem enviada|Enviar|Uma mensagem foi enviada, respondida ou encaminhada. Essa atividade é registrada apenas aos usuários com uma licença do Office 365 ou do Microsoft 365 E5. Para obter mais informações, consulte a seção "Acesso aos eventos cruciais de investigações" em [Auditoria Avançada](advanced-audit.md#access-to-crucial-events-for-investigations).|
|Mensagem enviada com permissões Enviar Como|SendAs|Uma mensagem foi enviada usando a permissão SendAs. Isso significa que outro usuário enviou a mensagem como se fosse proveniente do proprietário da caixa de correio.|
|Mensagem enviada com permissões Enviar em Nome de|SendOnBehalf|Uma mensagem foi enviada usando a permissão SendOnBehalf. Isso significa que outro usuário enviou a mensagem em nome do proprietário da caixa de correio. A mensagem indica ao destinatário para quem a mensagem foi enviada e quem realmente a enviou.|
|Regras atualizadas da caixa de entrada do cliente do Outlook|UpdateInboxRules|Um proprietário da caixa de correio ou outro usuário com acesso à caixa de correio modificou uma regra da caixa de entrada no cliente do Outlook.|
|Mensagem atualizada|Atualizar|Uma mensagem ou suas propriedades foram alteradas.|
|Usuário entrou na caixa de correio|MailboxLogin|O usuário entrou em sua caixa de correio.|
|Etiquetar a mensagem como um registro||Um usuário aplicou um rótulo de retenção a uma mensagem de e-mail, e essa etiqueta é configurada para marcar o item como um registro. |
||||

### <a name="user-administration-activities"></a>Atividades de administração de usuários

A tabela a seguir lista as atividades de administração de usuários que são registradas quando um administrador adiciona ou altera uma conta de usuário usando o Microsoft 365 ou o portal de gerenciamento do Azure.

> [!NOTE]
> Os nomes de operação listados na coluna **Operação** na tabela a seguir contêm um ponto ( `.` ). Você deve incluir o período no nome da operação se especificar a operação em um comando do Windows PowerShell ao pesquisar o log de auditoria, criar políticas de retenção de auditoria, criar políticas de alerta ou criar alertas de atividade. Além disso, certifique-se de usar aspas duplas (`" "`) para conter o nome da operação.

|Atividade|Operação|Descrição|
|:-----|:-----|:-----|
|Usuário adicionado|Adicionar usuário.|Uma conta de usuário foi criada.|
|Licença de usuário alterada|Altere a licença do usuário.|A licença atribuída a um usuário foi alterada. Para ver quais licenças foram alteradas, veja a atividade **Usuário atualizado** correspondente.|
|Senha do usuário alterada|Altere a senha de usuário.|Um usuário altera sua senha. A redefinição de senha de autoatendimento deve estar ativada (para todos ou usuários selecionados) na sua organização para permitir que os usuários redefinam suas senhas. Você também pode acompanhar a atividade de redefinição de senha de autoatendimento no Azure Active Directory. Para obter mais informações, consulte [Opções de relatório do gerenciamento de senhas do Azure AD](/azure/active-directory/authentication/howto-sspr-reporting).
|Usuário excluído|Excluir usuário.|Uma conta de usuário foi excluída.|
|Redefinir senha do usuário|Redefina a senha do usuário.|O administrador redefine a senha de um usuário.|
|Propriedade definida que força o usuário a alterar a senha|Defina forçar a alteração da senha do usuário.|O administrador definiu a propriedade que força o usuário a redefinir a senha da próxima vez que esse usuário entrar no Office 365.|
|Definir propriedades de licenças|Defina as propriedades de licenças.|O administrador modifica as propriedades de uma licença atribuída a um usuário.|
|Usuário atualizado|Atualize o usuário.|O administrador altera uma ou mais propriedades de uma conta de usuário. Para obter uma lista de propriedades do usuário que podem ser atualizadas, veja a seção "Atualizar atributos do usuário" em [Eventos de relatório de auditoria do Azure Active Directory](/azure/active-directory/reports-monitoring/concept-audit-logs).|
||||

### <a name="azure-ad-group-administration-activities"></a>Atividades de administração de grupos do Azure AD

A tabela a seguir lista as atividades de administração de grupos que são registradas quando um administrador ou um usuário cria ou altera um grupo do Microsoft 365 ou quando um administrador cria um grupo de segurança usando o Centro de Administração do Microsoft 365 ou o portal de gerenciamento do Azure. Para saber mais sobre grupos no Office 365, confira [Exibir, criar e excluir Grupos no centro de administração do Microsoft 365](../admin/create-groups/create-groups.md).

> [!NOTE]
> Os nomes de operação listados na coluna **Operação** na tabela a seguir contêm um ponto ( `.` ). Você deve incluir o período no nome da operação se especificar a operação em um comando do Windows PowerShell ao pesquisar o log de auditoria, criar políticas de retenção de auditoria, criar políticas de alerta ou criar alertas de atividade. Além disso, certifique-se de usar aspas duplas (`" "`) para conter o nome da operação.

|Nome amigável|Operação|Descrição|
|:-----|:-----|:-----|
|Grupo adicionado|Adicione grupo.|Um grupo foi criado.|
|Membro adicionado ao grupo|Adicione membro ao grupo.|Um membro foi adicionado a um grupo.|
|Grupo excluído|Exclua o grupo.|Um grupo foi excluído.|
|Membro removido do grupo|Remova membro do grupo.|Um membro foi removido de um grupo.|
|Grupo atualizado|Atualize o grupo.|Uma propriedade de um grupo foi alterada.|
||||

### <a name="application-administration-activities"></a>Atividades de administração de aplicativos

A tabela a seguir lista atividades de administração de aplicativos que são registradas quando um administrador adiciona ou altera um aplicativo que está registrado no Azure AD. Qualquer aplicativo que depende do Azure AD para autenticação deve ser registrado no diretório.

> [!NOTE]
> Os nomes de operação listados na coluna **Operação** na tabela a seguir contêm um ponto ( `.` ). Você deve incluir o período no nome da operação se especificar a operação em um comando do Windows PowerShell ao pesquisar o log de auditoria, criar políticas de retenção de auditoria, criar políticas de alerta ou criar alertas de atividade. Além disso, certifique-se de usar aspas duplas (`" "`) para conter o nome da operação.

|Nome amigável|Operação|Descrição|
|:-----|:-----|:-----|
|Entrada da delegação adicionada|Adicione entrada de delegação.|Uma permissão de autenticação foi criada/concedida a um aplicativo no Azure AD.|
|Entidade de serviço adicionada|Adicione entidade de serviço.|Um aplicativo foi registrado no Azure AD. Um aplicativo é representado por uma entidade de serviço no diretório.|
|Credenciais adicionadas a uma entidade de serviço |Adicione credenciais da entidade de serviço.|Credenciais foram adicionadas a uma entidade de serviço no Azure AD. Uma entidade de serviço representa um aplicativo no diretório.|
|Entrada de delegação removida|Remova a entrada de delegação.|Uma permissão de autenticação foi removida de um aplicativo no Azure AD.|
|Entidade de serviço removida do diretório|Remova a entidade de serviço.|Um aplicativo foi excluído/teve o registro cancelado do Azure AD. Um aplicativo é representado por uma entidade de serviço no diretório.|
|Credenciais removidas de uma entidade de serviço |Remova as credenciais da entidade de serviço.|Credenciais foram removidas de uma entidade de serviço no Azure AD. Uma entidade de serviço representa um aplicativo no diretório.|
|Definir entrada de delegação|Defina a entrada de delegação.|Uma permissão de autenticação foi atualizada para um aplicativo no Azure AD.|
||||

### <a name="role-administration-activities"></a>Atividades de administração de funções

A tabela a seguir lista as atividades de administração de funções do Azure AD registradas quando um administrador gerencia funções de administração no Microsoft 365 ou no portal de gerenciamento do Azure.

> [!NOTE]
> Os nomes de operação listados na coluna **Operação** na tabela a seguir contêm um ponto ( `.` ). Você deve incluir o período no nome da operação se especificar a operação em um comando do Windows PowerShell ao pesquisar o log de auditoria, criar políticas de retenção de auditoria, criar políticas de alerta ou criar alertas de atividade. Além disso, certifique-se de usar aspas duplas (`" "`) para conter o nome da operação.

|Nome amigável|Operação|Descrição|
|:-----|:-----|:-----|
|Adicionar membro à função|Adicione o membro à função.|Usuário adicionado a uma função de administração no Microsoft 365.|
|Usuário removido de uma função de diretório|Remova membro da função.|Usuário removido de uma função de administração no Microsoft 365.|
|Definir informações de contato da empresa|Defina as informações de contato da empresa.|Preferências de contato no nível da empresa atualizadas para a sua organização. Isso inclui endereços de email para emails relacionados a assinaturas enviados pelo Microsoft 365 e notificações técnicas sobre serviços.|
||||

### <a name="directory-administration-activities"></a>Atividades de administração de diretórios

A tabela a seguir lista as atividades relacionadas a diretórios e domínios do Azure AD que são registradas quando um administrador gerencia sua organização no Centro de administração do Microsoft 365 ou no portal de gerenciamento do Azure.

> [!NOTE]
> Os nomes de operação listados na coluna **Operação** na tabela a seguir contêm um ponto ( `.` ). Você deve incluir o período no nome da operação se especificar a operação em um comando do Windows PowerShell ao pesquisar o log de auditoria, criar políticas de retenção de auditoria, criar políticas de alerta ou criar alertas de atividade. Além disso, certifique-se de usar aspas duplas (`" "`) para conter o nome da operação.

|Nome amigável|Operação|Descrição|
|:-----|:-----|:-----|
|Domínio adicionado à empresa|Adicione o domínio à empresa.|Domínio adicionado à sua organização.|
|Parceiro adicionado ao diretório|Adicione parceiro à empresa.|Parceiro (administrador delegado) adicionado à sua organização.|
|Domínio removido da empresa|Remova o domínio da empresa.|Domínio removido da sua organização.|
|Parceiro removido do diretório|Remova o parceiro da empresa.|Parceiro (administrador delegado) removido da sua organização.|
|Definir informações da empresa|Defina a informações da empresa.|Informações da empresa atualizadas para a sua organização. Isso inclui endereços de email para emails relacionados a assinaturas enviados pelo Office 365 e notificações técnicas sobre os serviços do Microsoft 365.|
|Definir autenticação de domínio|Defina a autenticação de domínio.|Configuração de autenticação de domínio alterada para a sua organização.|
|Configurações de federação atualizadas para um domínio|Defina a configurações de federação no domínio.|Configurações de federação (compartilhamento externo) alteradas para a sua organização.|
|Definir política de senha|Defina a política de senha.|Restrições de comprimento e caracteres alteradas para senhas de usuário na sua organização.|
|Sincronização do Azure AD ativada|Defina o sinalizador DirSyncEnabled.|Definir a propriedade que habilita um diretório para sincronização do Azure AD.|
|Domínio atualizado|Atualize o domínio.|Configurações de um domínio atualizadas na sua organização.|
|Domínio verificado|Verifique o domínio.|Foi verificado que a sua organização é a proprietária de um domínio.|
|Domínio confirmado de email verificado|Verifique o domínio confirmado de email.|Verificação de email usada para confirmar que a sua organização é proprietária de um domínio.|
||||

### <a name="ediscovery-activities"></a>Atividades de Descoberta Eletrônica

Atividades relacionadas a Pesquisa de Conteúdo e Descoberta Eletrônica que são realizadas no centro de segurança e conformidade ou ao executar os cmdlets do PowerShell correspondentes são registradas no log de auditoria. Isso inclui as seguintes atividades:

- Criar e gerenciar casos de Descoberta Eletrônica

- Criar, iniciar e editar pesquisas de conteúdo

- Executar ações de pesquisa de conteúdo, como visualização, exportação e exclusão de resultados de pesquisa

- Configurar a filtragem de permissões para pesquisa de conteúdo

- Gerenciar a função de administrador de Descoberta Eletrônica

Para obter uma lista e uma descrição detalhada das atividades de Descoberta Eletrônica que são registradas, veja [Procurar atividades de Descoberta Eletrônica no log de auditoria](search-for-ediscovery-activities-in-the-audit-log.md).

> [!NOTE]
> Demora até 30 minutos para os eventos resultantes das atividades listadas em **Atividades de Descoberta Eletrônica** e **Atividades de Descoberta Eletrônica Avançada** na lista suspensa das **Atividades** serem exibidos nos resultados da pesquisa. Por outro lado, leva até 24 horas para que os eventos correspondentes das atividades de cmdlet de Descoberta Eletrônica apareçam nos resultados da pesquisa.

### <a name="advanced-ediscovery-activities"></a>Atividades de Descoberta Eletrônica Avançada

Você também pode pesquisar o log de auditoria das atividades na Descoberta Eletrônica Avançada. Para obter uma descrição dessas atividades, confira a seção "Atividades da Descoberta Eletrônica Avançada" em [Pesquisar atividades de Descoberta Eletrônica no log de auditoria](search-for-ediscovery-activities-in-the-audit-log.md#advanced-ediscovery-activities).

### <a name="power-bi-activities"></a>Atividades do Power BI

Você pode pesquisar o log de auditoria das atividades do Power BI. Para saber mais sobre as atividades do Power bi, confira a seção "Atividades auditadas pelo Power bi" em [Usando a auditoria dentro da sua organização](/power-bi/service-admin-auditing#activities-audited-by-power-bi).

O log de auditoria do Power BI não está habilitado por padrão. Para pesquisar as atividades do Power BI no log de auditoria, habilite o recurso de auditoria no Portal de Administração do Power BI. Para obter instruções, confira a seção "logs de auditoria" no [portal de administração do Power bi](/power-bi/service-admin-portal#audit-logs).

### <a name="workplace-analytics-activities"></a>Atividades do Workplace Analytics

O Workplace Analytics fornece informação de como os grupos colaboram em sua organização. A tabela a seguir lista as atividades executadas pelos usuários que recebem a função de Administrador ou as funções de Analista no Workplace Analytics. Os usuários que receberam a função de Analista têm acesso total a todos os recursos de serviço e usam o produto para fazer análise. Os usuários que receberam a função de Administrador podem definir as configurações de privacidade e os padrões do sistema, além de poder preparar, carregar e verificar dados organizacionais no Workplace Analytics. Para saber mais, confira [Workplace Analytics](/workplace-analytics/index-orig).

|Nome amigável|Operação|Descrição|
|:-----|:-----|:-----|
|Link OData acessado|AccessedOdataLink|O analista acessou o link OData para uma consulta.|
|Consulta cancelada|CanceledQuery|O analista cancelou uma consulta em execução.|
|Exclusão de reunião criada|MeetingExclusionCreated|O analista criou uma regra de exclusão de reunião.|
|Resultado excluído|DeletedResult|O analista excluiu um resultado de consulta.|
|Relatório baixado|DownloadedReport|O analista baixou um arquivo de resultado da consulta.|
|Consulta executada|ExecutedQuery|O analista executou uma consulta.|
|Configuração do acesso a dados atualizada|UpdatedDataAccessSetting|O administrador atualizou as configurações de acesso a dados.|
|Configuração de privacidade atualizada|UpdatedPrivacySetting|O administrador atualizou as configurações de privacidade; por exemplo, tamanho mínimo do grupo.|
|Dados da organização carregados|UploadedOrgData|O administrador carregou um arquivo de dados organizacional.|
|Exploração Exibida|ViewedExplore|O analista exibiu as visualizações em uma ou mais guias da página de Exploração.|
||||

### <a name="microsoft-teams-activities"></a>Atividades do Microsoft Teams

Você pode pesquisar o log de auditoria das atividades de usuários e de administradores no Microsoft Teams. O Teams é um espaço de trabalho centralizado em chat no Office 365. Ele reúne as conversas, reuniões, arquivos e anotações da equipe em um único lugar. Para obter descrições das atividades do Teams, confira [Pesquisar o log de auditoria de eventos no Microsoft Teams](/microsoftteams/audit-log-events#teams-activities).

### <a name="microsoft-teams-healthcare-activities"></a>Atividades do Microsoft Teams Healthcare

Se a sua organização estiver usando o [aplicativo Patients ](/MicrosoftTeams/expand-teams-across-your-org/healthcare/patients-app-overview) do Microsoft Teams, você poderá pesquisar o log de auditoria para atividades relacionadas ao uso do aplicativo Patients. Se o seu ambiente estiver configurado para oferecer suporte ao aplicativo Patients, um grupo de atividades adicionais para essas atividades estará disponível na lista seletora **Atividades**.

![Atividades do Microsoft Teams Healthcare na lista seletora Atividades](../media/TeamsHealthcareAuditActivities.png)

Para obter uma descrição das atividades do aplicativos Patients, confira [Logs de auditoria para aplicativo Patients](/MicrosoftTeams/expand-teams-across-your-org/healthcare/patients-audit).

### <a name="microsoft-teams-shifts-activities"></a>Atividades de Turnos do Microsoft Teams

Se sua organização estiver usando o aplicativo Turnos no Microsoft Teams, você poderá pesquisar o log de auditoria por atividades relacionadas ao uso do aplicativo Turnos. Se o seu ambiente estiver configurado para oferecer suporte ao aplicativo Turnos, um grupo de atividades adicionais para essas atividades estará disponível na lista de seleção **Atividades**.

Para obter uma descrição das atividades do aplicativo Turnos, confira [Pesquisar eventos no log de auditoria no Microsoft Teams](/microsoftteams/audit-log-events#shifts-in-teams-activities).

### <a name="yammer-activities"></a>Atividades do Yammer

A tabela a seguir lista as atividades de usuários e de administradores no Yammer que estejam conectados ao log de auditoria. Para retornar atividades relacionadas ao Yammer no log de auditoria, escolha **Mostrar resultados para todas as atividades** na lista **Atividades**. Use as caixas de intervalo de datas e a lista de **Usuários** para restringir os resultados da pesquisa.

|Nome amigável|Operação|Descrição|
|:-----|:-----|:-----|
|Política de retenção de dados alterada|SoftDeleteSettingsUpdated|O administrador verificado atualiza a configuração da política de retenção de dados da rede para Exclusão Irreversível ou Exclusão Temporária. Somente administradores verificados podem realizar essa operação.|
|Configuração de rede alterada|NetworkConfigurationUpdated|O administrador de rede ou administrador verificado altera as configurações da rede do Yammer. Isso inclui a definição do intervalo de exportação de dados e de habilitação do chat.|
|Configurações de perfil de rede alteradas|ProcessProfileFields|O administrador de rede ou verificado altera as informações que aparecem em perfis de membro para a rede de usuários da rede.|
|Modo de Conteúdo Particular modificado|SupervisorAdminToggled|O administrador verificado ativa ou desativa o *Modo de Conteúdo Particular*. Esse modo permite que um administrador visualize postagens em grupos particulares e visualize mensagens particulares entre usuários individuais (ou grupos de usuários). Somente administradores verificados podem realizar essa operação.|
|Configurações de segurança alteradas|NetworkSecurityConfigurationUpdated|O administrador verificado atualiza as configurações de segurança da rede do Yammer. Isso inclui a definição de políticas de expiração de senha e restrições de endereços IP. Somente administradores verificados podem realizar essa operação.|
|Arquivo criado|FileCreated|O usuário carrega um arquivo.|
|Grupo criado|GroupCreation|O usuário cria um grupo.|
|Grupo excluído|GroupDeletion|Um grupo é excluído do Yammer.|
|Mensagem excluída|MessageDeleted|O usuário exclui uma mensagem.|
|Arquivo baixado|FileDownloaded|O usuário baixa um arquivo.|
|Dados exportados|DataExport|O administrador verificado exporta dados de rede do Yammer. Somente administradores verificados podem realizar essa operação.|
|Arquivo compartilhado|FileShared|O usuário compartilha um arquivo com outros usuários.|
|Usuário de rede suspenso|NetworkUserSuspended|O administrador de rede ou verificado suspende ou desativa um usuário no Yammer.|
|Usuário suspenso|UserSuspension|A conta de usuário é suspensa ou desativada.|
|Descrição de arquivo atualizada|FileUpdateDescription|O usuário modifica a descrição de um arquivo.|
|Nome de arquivo atualizado|FileUpdateName|O usuário modifica o nome de um arquivo.|
|Arquivo exibido|FileVisited|O usuário exibe um arquivo.|
||||

### <a name="microsoft-power-automate-activities"></a>Atividades do Microsoft Power Automate

Você pode pesquisar o log de auditoria para atividades no Power Automate (anteriormente chamado Microsoft Flow). Essas atividades incluem criar, editar e excluir fluxos, e alterar as permissões de fluxo. Para obter informações sobre auditoria de atividades do Power Automate, confira o blog [eventos de auditoria do Microsoft Flow já estão disponíveis no Centro de Conformidade e Segurança](https://flow.microsoft.com/blog/security-and-compliance-center).

### <a name="microsoft-power-apps-activities"></a>Atividades do Microsoft Power Apps

Você pode pesquisar o log de auditoria de atividades relacionadas a aplicativos no Power Apps. Essas atividades incluem criar, iniciar e publicar um aplicativo. Atribuir permissões a aplicativos também é auditado. Para obter uma descrição de todas as atividades do Power Apps, confira [Log de atividades do Power Apps](/power-platform/admin/logging-powerapps#what-events-are-audited).

### <a name="microsoft-stream-activities"></a>Atividades do Microsoft Stream

Você pode pesquisar o log de auditoria para atividades no Microsoft Stream. Essas atividades incluem atividades de vídeo executadas por usuários, atividades de canal de grupo e atividades de administração, como gerenciar usuários, gerenciar as configurações da organização e exportar relatórios. Para obter uma descrição dessas atividades, consulte a seção "Atividades registradas no Microsoft Stream em [Logs de auditoria do Microsoft Stream](/stream/audit-logs#actions-logged-in-stream).

### <a name="content-explorer-activities"></a>Atividades do explorador de conteúdo

A tabela a seguir lista as atividades no explorador de conteúdo registradas no log de auditoria. Explorador de conteúdo, que é acessado na ferramenta Classificações de dados no centro de conformidade do Microsoft 365. Para obter mais informações, consulte [Usar o conteúdo de classificação de dados do Explorer](data-classification-content-explorer.md).

|Nome amigável|Operação|Descrição|
|:-----|:-----|:-----|
|Item acessado|LabelContentExplorerAccessedItem|Um administrador (ou um usuário que seja membro do grupo de funções do Visualizador de conteúdo do explorador de conteúdo) usa o explorador de conteúdo para exibir uma mensagem de e-mail ou documento do SharePoint/OneDrive.|
||||

### <a name="quarantine-activities"></a>Atividades de quarentena

A tabela a seguir lista as atividades de quarentena que podem ser pesquisadas no log de auditoria. Para saber mais sobre a quarentena, confira [Mensagens de e-mail em quarentena no Office 365](../security/office-365-security/quarantine-email-messages.md).

|Nome amigável|Operação|Descrição|
|:-----|:-----|:-----|
|Mensagem de quarentena excluída|QuarantineDelete|Um usuário excluiu uma mensagem de e-mail considerada nociva.|
|Mensagem de quarentena exportada|QuarantineExport|Um usuário exportou uma mensagem de e-mail considerada nociva.|
|Mensagem de quarentena exibida|QuarantinePreview|Um usuário visualizou uma mensagem de e-mail que foi considerada nociva.|
|Mensagem de quarentena liberada|QuarantineRelease|Um usuário liberou uma mensagem de e-mail da quarentena que foi considerada prejudicial.|
|Cabeçalho de mensagem de quarentena exibida|QuarantineViewHeader|Um usuário exibiu o cabeçalho uma mensagem de e-mail considerada nociva.|
||||

### <a name="microsoft-forms-activities"></a>Atividades do Microsoft Forms

A tabela a seguir lista as atividades de usuários e administradores no Microsoft Forms que estejam conectados ao log de auditoria. O Microsoft Forms é uma ferramenta de formulários/testes/pesquisa usada para coletar dados para análise. 

Onde indicado abaixo nas descrições, algumas operações contêm parâmetros adicionais de atividade.

> [!NOTE]
> Se uma atividade do Forms for realizada por um coautor ou um respondente anônimo, ela será registrada um pouco diferente. Para saber mais, confira a seção [Atividades do Forms realizadas por coautores e respondentes anônimos](#forms-activities-performed-by-coauthors-and-anonymous-responders).

|Nome amigável|Operação|Descrição|
|:-----|:-----|:-----|
|Comentário criado|CreateComment|O proprietário do formulário adiciona um comentário ou pontuação a um teste.|
|Formulário criado|CreateForm|O proprietário do formulário cria um novo formulário.|
|Formulário editado|EditForm|O proprietário do formulário edita um formulário criando, removendo ou editando uma pergunta. A propriedade *EditOperation: cadeia de caracteres* indica o nome da operação de edição. As operações possíveis são:<br/>- CreateQuestion<br/>- CreateQuestionChoice <br/>- DeleteQuestion <br/>- DeleteQuestionChoice <br/>- DeleteFormImage <br/>- DeleteQuestionImage <br/>- UpdateQuestion <br/>- UpdateQuestionChoice <br/>- UploadFormImage/Bing/Onedrive <br/>- UploadQuestionImage <br/>- ChangeTheme <br><br>FormImage inclui qualquer lugar dentro do Forms que o usuário pode carregar uma imagem, como em uma consulta ou como um tema de plano de fundo.|
|Formulário movido|MoveForm|O proprietário do formulário move um formulário. <br><br>A propriedade DestinationUserId:string indica a ID de usuário da pessoa que moveu o formulário. A propriedade NewFormId:string é a nova ID do formulário copiado recentemente.|
|Formulário excluído |DeleteForm|O proprietário do formulário exclui um formulário. Isso inclui SoftDelete (opção de exclusão usada e formulário movido para a lixeira) e HardDelete (lixeira esvaziada).|
|Formulário exibido (tempo de design)|ViewForm|O proprietário do formulário abre um formulário existente para edição.|
|Formulário visualizado|PreviewForm|O proprietário do formulário visualiza um formulário usando a função Visualização.|
|Formulário exportado|ExportForm|O proprietário do formulário exporta os resultados para o Excel. <br><br>A propriedade ExportFormat:string indica se o arquivo do Excel foi baixado ou está online.|
|Formulário de compartilhamento permitido para cópia|AllowShareFormForCopy|O proprietário do formulário cria um link de modelo para compartilhar o formulário com outros usuários. Esse evento é registrado quando o proprietário do formulário clica para gerar uma URL de modelo.|
|Formulário de compartilhamento não permitido para cópia|DisallowShareFormForCopy|O proprietário do formulário exclui o link do modelo.|
|Coautor do formulário adicionado|AddFormCoauthor|Um usuário usa um link de colaboração para criar e exibir respostas. Esse evento é registrado em log quando um usuário usa uma URL de colaboração (não quando a URL de colaboração é gerada primeiro).|
|Coautor do formulário removido|RemoveFormCoauthor|O proprietário do formulário exclui um link de colaboração.|
|Página de resposta exibida|ViewRuntimeForm|O usuário abriu uma página de resposta para exibição. Esse evento é registrado independentemente de o usuário enviar uma resposta ou não.|
|Resposta criada|CreateResponse|Semelhante a receber uma nova resposta.  Um usuário enviou uma resposta a um formulário. <br><br>A propriedade ResponseId:string e a propriedade ResponderId:string indicam qual resultado está sendo visualizado. <br><br>Para um respondente anônimo, a propriedade ResponderId será nula.|
|Resposta atualizada|UpdateResponse|O proprietário do formulário atualizou um comentário ou uma pontuação em um teste. <br><br>A propriedade ResponseId:string e a propriedade ResponderId:string indicam qual resultado está sendo visualizado. <br><br>Para um respondente anônimo, a propriedade ResponderId será nula.|
|Todas as respostas excluídas|DeleteAllResponses|O proprietário exclui todos os dados de resposta.|
|Resposta excluída|DeleteResponse|O proprietário do formulário exclui uma resposta. <br><br>A propriedade ResponseId:string indica qual resposta está sendo excluída.|
|Respostas exibidas|ViewResponses|O proprietário do formulário exibe a lista agregada de respostas. <br><br>A propriedade ViewType:string indica se o proprietário do formulário está exibindo Detalhes ou Agregação|
|Resposta exibida|ViewResponse|O proprietário do formulário exibe uma resposta específica. <br><br>A propriedade ResponseId:string e a propriedade ResponderId:string indicam qual resultado está sendo visualizado. <br><br>Para um respondente anônimo, a propriedade ResponderId será nula.|
|Link de resumo criado|GetSummaryLink|O proprietário do formulário cria links de resumo para compartilhar resultados.|
|Link de resumo excluído|DeleteSummaryLink|O proprietário do formulário exclui o link de resultados de resumo.|
|Formulário de status de phishing atualizado|UpdatePhishingStatus|Este evento é registrado sempre que o valor detalhado para o status de segurança interna for alterado, independentemente de isso ter alterado o estado de segurança final (por exemplo, o formulário agora está Fechado ou Aberto). Isso significa que você pode ver eventos duplicados sem uma alteração final do estado de segurança. Os valores de status possíveis para este evento são:<br/>- Derrubar <br/>- Retirado por Administrador <br/>- Administrador Desbloqueado <br/>- Auto Bloqueado <br/>- Auto Desbloqueado <br/>- Relatado pelo Cliente <br/>-Redefinir Cliente Relatado|
|Status de phishing do usuário atualizado|UpdateUserPhishingStatus|Este evento é registrado sempre que o valor do status de segurança do usuário é alterado. O valor do status do usuário no registro de auditoria é **Confirmado como Phisher** quando o usuário criou um formulário de phishing que foi removido pela equipe de segurança do Microsoft Online. Se um administrador desbloquear o usuário, o valor do status do usuário é definido como **Redefinir como Usuário Normal**.|
|Convite do Forms Pro enviado|ProInvitation|O usuário clica para ativar uma avaliação do Pro.|
|Configuração do formulário atualizado|UpdateFormSetting|O proprietário do formulário atualiza a configuração de um formulário. <br><br>A propriedade FormSettingName:string indica o nome e o novo valor da configuração.|
|Configuração de usuário atualizada|UpdateUserSetting|O proprietário do formulário atualiza a configuração de um usuário. <br><br>A propriedade UserSettingName:string indica o nome e o novo valor da configuração|
|Formulários listados|ListForms|O proprietário do formulário está exibindo uma lista de formulários. <br><br>A propriedade ViewType:string indica qual exibição o proprietário do formulário está olhando: Todos os Formulários, Compartilhado Comigo ou Formulários de Grupo|
|Resposta enviada |SubmitResponse|Um usuário envia uma resposta a um formulário. <br><br>A propriedade IsInternalForm:boolean indica se o respondente é da mesma organização que o proprietário do formulário.|
||||

#### <a name="forms-activities-performed-by-coauthors-and-anonymous-responders"></a>Atividades do Forms realizadas por coautores e respondentes anônimos

Os formulários oferecem suporte à colaboração quando os formulários são projetados e ao analisar as respostas. Um colaborador de formulário é conhecido como um *coautor*. Os coautores podem fazer tudo o que um proprietário de formulário pode fazer, exceto excluir ou mover um formulário. O Forms também permite criar um formulário que pode ser respondido anonimamente. Isso significa que o respondente não precisa estar conectado à sua organização para responder a um formulário.

A tabela a seguir descreve as atividades e informações de auditoria no registro de auditoria para atividades executadas por coautores e respondentes anônimos.

|Tipo de atividade|Usuário interno ou externo|Identificação do usuário que está conectado|Organização conectada a|Tipo de usuário de formulários|
|:-----|:-----|:-----|:-----|:-----|
|Atividades de coautoria|Interno|UPN|Organização do proprietário do formulário|Coautor|
|Atividades de coautoria|Externo|UPN<br>|Organização da coautoria<br>|Coautor|
|Atividades de coautoria|Externo|`urn:forms:coauthor#a0b1c2d3@forms.office.com`<br>(A segunda parte do ID é um hash, que será diferente para cada usuários)|Organização do proprietário do formulário<br>|Coautor|
|Atividades de resposta|Externo|UPN<br>|Organização do respondente<br>|Respondente|
|Atividades de resposta|Externo|`urn:forms:external#a0b1c2d3@forms.office.com`<br>(A segunda parte do ID do usuário é um hash, que será diferente para cada usuário)|Organização do proprietário do formulário|Respondente|
|Atividades de resposta|Anônimo|`urn:forms:anonymous#a0b1c2d3@forms.office.com`<br>(A segunda parte do ID do usuário é um hash, que será diferente para cada usuário)|Organização do proprietário do formulário|Respondente|
||||

### <a name="sensitivity-label-activities"></a>Atividades de rótulo de sensibilidade

A tabela abaixo lista os eventos que resultam das atividades de rotulamento dos sites do SharePoint Online e do Teams.

|Nome amigável|Operação|Descrição|
|:-----|:-----|:-----|
|Rótulo de sensibilidade aplicado ao site|SensitivityLabelApplied|Um rótulo de sensibilidade foi aplicado a um site do SharePoint ou do Teams.|
|Rótulo de sensibilidade removido do site|SensitivityLabelRemoved|Um rótulo de sensibilidade foi removido de um site do SharePoint ou do Teams.|
|Rótulo de sensibilidade aplicado ao site|FileSensitivityLabelApplied|Um rótulo de confidencialidade foi aplicado a um documento usando o Office na Web ou uma política de rotulação automática.|
|Rótulo de sensibilidade alterado aplicado ao arquivo|FileSensitivityLabelChanged|Um rótulo de confidencialidade diferente foi aplicado a um documento usando o Office na Web ou uma política de rotulação automática.|
|Rótulo de sensibilidade removido do site|FileSensitivityLabelRemoved|Um rótulo de sensibilidade foi removido de um documento usando o Office na Web, uma política de rotulamento automático ou usando o cmdlet [Unlock-SPOSensitivityLabelEncryptedFile](/powershell/module/sharepoint-online/unlock-sposensitivitylabelencryptedFile).|
||||

### <a name="retention-policy-and-retention-label-activities"></a>Política de retenção e atividades do rótulo de retenção

|Nome amigável|Operação|Descrição|
|:-----|:-----|:-----|
| Configurações definidas para uma política de retenção |NewRetentionComplianceRule |As configurações de retenção para uma nova política de retenção foram definidas pelo administrador. As configurações de retenção incluem por quanto tempo os itens são retidos e o que acontece com os itens quando o período de retenção expira (como excluir itens, reter itens ou retê-los e excluí-los). Essa atividade também corresponde à execução do cmdlet [New-RetentionComplianceRule](/powershell/module/exchange/new-retentioncompliancerule).|
| Criado o rótulo de retenção |NewComplianceTag |Um novo rótulo de retenção foi criado pelo administrador.|
| Criada a política de retenção  |NewRetentionCompliancePolicy|Uma nova política de retenção foi criada pelo administrador.|
| As configurações de uma política de retenção foram excluídas| RemoveRetentionComplianceRule<br/>| As definições de configuração de uma política de retenção foram excluídas pelo administrador. Provavelmente, essa atividade é registrada quando um administrador exclui uma política de retenção ou executa o cmdlet [Remove-RetentionComplianceRule](/powershell/module/exchange/Remove-RetentionComplianceRule).|
| Rótulo de retenção excluído |RemoveComplianceTag | Um rótulo de retenção foi excluído pelo administrador.|
| Excluída a política de retenção |RemoveRetentionCompliancePolicy<br/> |Uma política de retenção foi excluída pelo administrador. |
| A opção de registro regulatório foi habilitada para etiquetas de retenção<br/> |SetRestrictiveRetentionUI |O administrador executou o cmdlet [Set-RegulatoryComplianceUI](/powershell/module/exchange/set-regulatorycomplianceui) para que um administrador possa selecionar a opção de configuração da IU para que um rótulo de retenção marque o conteúdo como um registro regulamentar.|
| Configurações atualizadas para uma política de retenção | SetRetentionComplianceRule | As configurações de retenção para uma política de retenção existente foram alteradas pelo administrador. As configurações de retenção incluem por quanto tempo os itens são retidos e o que acontece com os itens quando o período de retenção expira (como excluir itens, reter itens ou retê-los e excluí-los). Essa atividade também corresponde à execução do cmdlet [Set-RetentionComplianceRule](/powershell/module/exchange/set-retentioncompliancerule). |
| Rótulo de retenção atualizado |SetComplianceTag  | Um rótulo de retenção existente foi atualizado pelo administrador.|
| Política de retenção atualizada |SetRetentionCompliancePolicy |Uma política de retenção existente foi atualizada pelo administrador. As atualizações que acionam este evento incluem adicionar ou excluir locais de conteúdo aos quais a política de retenção é aplicada.|
||||

### <a name="briefing-email-activities"></a>Atividades do email de resumo

A tabela a seguir lista as atividades em Emails de resumo registrados no log de auditoria do Office 365. Para obter mais informações sobre o Email de resumo, consulte:

- [Visão geral do email de Resumo](/Briefing/be-overview)

- [Configurar email de Resumo](/Briefing/be-admin)

|**Nome amigável**|**Operação**|**Descrição**|
|:-----|:-----|:-----|
|Configurações de privacidade da organização atualizadas|UpdatedOrganizationBriefingSettings|O administrador atualiza as configurações de privacidade da organização para email de Resumo. |
|Configurações de privacidade do usuário atualizadas|UpdatedUserBriefingSettings|O administrador atualiza as configurações de privacidade do usuário para email de Resumo.
||||

### <a name="myanalytics-activities"></a>Atividades do MyAnalytics

A tabela a seguir lista as atividades no MyAnalytics registradas no log de auditoria do Office 365. Para obter mais informações sobre o MyAnalytics, consulte [MyAnalytics para administradores](/workplace-analytics/myanalytics/overview/mya-for-admins).

|**Nome amigável**|**Operação**|**Descrição**|
|:-----|:-----|:-----|
|Configurações atualizadas do MyAnalytics da organização|UpdatedOrganizationMyAnalyticsSettings|O administrador atualiza as configurações no nível da organização para o MyAnalytics. |
|Configurações atualizadas do usuário do MyAnalytics|UpdatedUserMyAnalyticsSettings|O administrador atualiza as configurações do usuário para o MyAnalytics.|
||||

### <a name="information-barriers-activities"></a>Atividades das barreiras de informação

A tabela a seguir lista as atividades das barreiras de informação registradas no log de auditoria do Office 365. Para obter mais informações sobre as barreiras de informação, consulte [Saiba mais sobre as barreiras de informação no Microsoft 365](information-barriers.md).

|**Nome amigável**|**Operação**|**Descrição**|
|:----------------|:------------|:--------------|
| Adicionados segmentos a um site | SegmentsAdded | Um administrador global, do SharePoint ou proprietário de site adicionou um ou mais segmentos de barreiras de informação a um site. |
| Segmentos alterados de um site | SegmentsChanged | Um administrador global ou do SharePoint alterou um ou mais segmentos de barreiras de informação para um site. |
| Segmentos removidos de um site | SegmentsRemoved | Um administrador global ou do SharePoint removeu um ou mais segmentos de barreiras de informação de um site. |
||||

### <a name="exchange-admin-audit-log"></a>Log de auditoria de administradores do Exchange

O log de auditoria de administradores do Exchange (que está habilitado por padrão no Office 365) registra um evento no log de auditoria quando um administrador (ou um usuário que recebeu permissões administrativas) faz uma alteração na sua organização do Exchange Online. As alterações feitas usando o centro de administração do Exchange ou executando um cmdlet no PowerShell do Exchange Online são registradas no log de auditoria de administradores do Exchange. Os cmdlets que começam com os verbos **Obter-**, **Pesquisar**, ou **Testar –** não estão registrados no log de auditoria. Para obter informações mais detalhadas sobre o log de auditoria de administradores do Exchange, confira [Log de auditoria de administradores](/exchange/administrator-audit-logging-exchange-2013-help).

> [!IMPORTANT]
> Alguns cmdlets do Exchange Online que não estão registrados no log de auditoria de administradores do Exchange (ou no log de auditoria). Muitos desses cmdlets estão relacionados à manutenção do serviço do Exchange Online e são executados pela equipe do datacenter da Microsoft ou por contas de serviços. Esses cmdlets não são registrados porque resultariam em um grande número de eventos de auditoria "ruidosa". Se houver um cmdlet do Exchange Online que não está sendo auditado, envie uma sugestão para o [fórum de Voz do Usuário de Conformidade e Segurança](https://office365.uservoice.com/forums/289138-office-365-security-compliance) e solicite que ele seja habilitado para auditoria. Você também pode enviar uma solicitação de alteração de design (DCR) para o suporte da Microsoft.

Aqui estão algumas dicas para pesquisar atividades de administração do Exchange ao pesquisar o log de auditoria:

- Para retornar entradas do log de auditoria de administradores do Exchange, você precisa selecionar **Mostrar resultados para todas as atividades** na lista de **Atividades**. Use as caixas de intervalo de datas e a lista de **Usuários** para restringir os resultados da pesquisa para cmdlets executados por um administrador específico do Exchange dentro de um intervalo de datas específico.

- Para exibir eventos do log de auditoria de administradores do Exchange, filtre os resultados da pesquisa e digite um **-** (traço) na caixa de filtro **Atividade**. São mostrados os nomes de cmdlets, que são exibidos na coluna **Atividade** para eventos de administradores do Exchange. Em seguida, você pode classificar os nomes de cmdlets em ordem alfabética.

  ![Digite um traço na caixa Atividades para filtrar os eventos de administração do Exchange](../media/7628e7aa-6263-474a-a28b-2dcf5694bb27.png)

- Para obter informações sobre qual cmdlet foi executado, quais parâmetros e valores de parâmetros foram usados e quais objetos foram afetados, você pode exportar os resultados da pesquisa selecionando a opção **Baixar todos os resultados**. Para saber mais, confira [Exportar, configurar e exibir registros de log de auditoria](export-view-audit-log-records.md).

- Você também pode usar o comando `Search-UnifiedAuditLog -RecordType ExchangeAdmin` no PowerShell do Exchange Online para retornar somente registros de auditoria do log de auditoria de administradores do Exchange. Pode levar até 30 minutos após a execução de um cmdlet do Exchange para que a entrada do log de auditoria correspondente seja retornada nos resultados da pesquisa. Para saber mais, confira [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog). Para obter informações sobre como exportar os resultados da pesquisa retornados pelo cmdlet **Search-UnifiedAuditLog** para um arquivo CSV, confira a seção "Dicas para exportar e exibir o log de auditoria" em [Exportar, configurar e exibir registros de log de auditoria](export-view-audit-log-records.md#tips-for-exporting-and-viewing-the-audit-log).

- Você também pode exibir os eventos no log de auditoria de administradores do Exchange usando o centro de administração do Exchange ou executando o **Search-AdminAuditLog** no PowerShell do Exchange Online. Esta é uma ótima maneira de procurar especificamente atividades executadas por administradores do Exchange Online. Para obter instruções, veja:

  - [Exibir o log de auditoria do administrador](/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log)

  - [Search-AdminAuditLog](/powershell/module/exchange/search-adminauditlog)

   Lembre-se de que as mesmas atividades do administrador do Exchange estão registradas no log de auditoria do administrador do Exchange e no log de auditoria.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

**Quais são os diferentes serviços do Microsoft 365 que atualmente são auditados?**

Os serviços mais usados ​​como Exchange Online, Microsoft Office SharePoint Online, Microsoft OneDrive for Business, Azure Active Directory, Microsoft Teams, Dynamics 365, Defender para Office 365 e Power BI são auditados. Confira o [Início deste artigo](search-the-audit-log-in-security-and-compliance.md) para obter uma lista de serviços que são auditados.

**Quais atividades são auditadas por serviço de auditoria no Office 365?**

Consulte a seção [Atividades auditadas](#audited-activities) neste artigo para obter uma lista e uma descrição das atividades que são auditadas.

**Quanto tempo leva para um registro de auditoria estar disponível após um evento ter ocorrido?**

A maioria dos dados de auditoria está disponível em 30 minutos, mas pode levar até 24 horas após a ocorrência de um evento para que a entrada do log de auditoria correspondente seja exibida nos resultados da pesquisa. Consulte a tabela na seção [Requisitos para pesquisar o log de auditoria](#requirements-to-search-the-audit-log) deste artigo que exibe o tempo necessário dos eventos em diferentes serviços disponíveis.

**Por quanto tempo os registros de auditoria são mantidos?**

Como explicado anteriormente, os registros de auditoria para atividades realizadas por usuários que receberam uma licença do Office 365 E5 ou do Microsoft E5 (ou usuários com uma licença complementar do Microsoft 365 E5) são mantidos por um ano. Para todas as outras assinaturas que oferecem suporte ao log de auditoria unificado, os registros de auditoria são mantidos por 90 dias.

**Posso acessar os dados de auditoria de forma programática?**

Sim. A API de atividade de gerenciamento do Office 365 é usada para buscar os logs de auditoria por programação.  Para saber mais, confira [Introdução às APIs de Gerenciamento do Office 365](/office/office-365-management-api/get-started-with-office-365-management-apis).

**Existem outras maneiras de obter logs de auditoria além de usar o centro de segurança e conformidade ou a API da Atividade de Gerenciamento do Office 365?**

Não. Estas são as duas únicas maneiras de obter dados do serviço de auditoria.

**Preciso habilitar individualmente a auditoria em cada serviço para o qual quero capturar os logs de auditoria?**

Na maioria dos serviços, a auditoria é habilitada por padrão depois que você ativa a auditoria pela sua organização, (conforme descrito na seção [Requisitos para pesquisar o log de auditoria](#requirements-to-search-the-audit-log) neste artigo).

**O serviço de auditoria oferece suporte para a duplicação de registros?**

Não. O pipeline do serviço de auditoria está quase em tempo real, portanto não é compatível com a duplicação.

**O dados de auditoria fluem entre regiões geográficas?**

Não. Atualmente, temos implantações de pipeline de auditoria nas regiões da América do Norte, Europa, Oriente Médio, África e Pacífico Asiático. No entanto, podemos transmitir os dados entre essas regiões para balancear a carga e apenas durante problemas no site ao vivo. Quando realizamos essas atividades, os dados em trânsito são criptografados.

**Os dados de auditoria são criptografados?**

Os dados de auditoria são armazenados nas caixas de correio do Exchange (dados em repouso) na mesma região em que o pipeline de auditoria é implantado. Os dados da caixa de correio em repouso não são criptografados pelo Exchange. No entanto, a criptografia no nível de serviço criptografa todos os dados da caixa de correio, pois os servidores do Exchange nos datacenters da Microsoft são criptografados via BitLocker. Para saber mais, confira [Criptografia do Office 365 para Skype for Business, OneDrive for Business, SharePoint Online e Exchange Online](/compliance/assurance/assurance-encryption-for-microsoft-365-services).

Os dados de email em trânsito sempre são criptografados.
