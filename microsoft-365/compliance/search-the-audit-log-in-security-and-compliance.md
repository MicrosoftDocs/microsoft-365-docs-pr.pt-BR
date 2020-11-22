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
description: Use o Centro de Segurança e Conformidade do Office 365 ou o centro de conformidade da Microsoft 365 para pesquisar o log de auditoria unificado para ver as atividades do usuário e do administrador em sua organização.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: aa47cc0c460e77a6faadd5cb2ff7d46c62ed88ab
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376650"
---
# <a name="search-the-audit-log-in-the-compliance-center"></a>Pesquisar o log de auditoria no centro de conformidade

Precisa descobrir se um usuário visualizou um documento específico ou apagou um item de sua caixa de correio? Em caso afirmativo, você pode usar o Centro de conformidade do Microsoft 365 para pesquisar o log de auditoria unificado para ver as atividades do usuário e do administrador em sua organização. Por que um log de auditoria unificado? Como você pode procurar os seguintes tipos de [atividade de usuários e administradores](#audited-activities) no Microsoft 365:

- Atividade do usuário do Microsoft Office SharePoint Online e do OneDrive for Business

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

## <a name="requirements-to-search-the-audit-log"></a>Requisitos para pesquisar o log de auditoria

Leia os seguintes itens antes de começar a pesquisar o log de auditoria.

- É necessário primeiro ativar o registro em log de auditoria para poder começar a pesquisar o log de auditoria. Para ativá-la, clique em **Ativar a auditoria** na página **Pesquisa de logs de auditoria** no Centro de Conformidade e Segurança. (Se você não vir esse link, a auditoria já está ativada na sua organização). Depois de ativá-lo, será exibida uma mensagem informando que o log de auditoria está sendo preparado e que você pode executar uma pesquisa dentro de algumas horas após concluir a preparação. Você só precisa fazer isso uma vez. Para saber mais, confira [Ativar ou desativar a pesquisa de log de auditoria](turn-audit-log-search-on-or-off.md).

  > [!NOTE]
  > Estamos em processo de ativar a auditoria por padrão. Até lá, você poderá ativá-la conforme descrito anteriormente.

- É preciso atribuir a função logs de auditoria somente para exibição ou logs de auditoria no Exchange Online para pesquisar o log de auditoria. Por padrão, essas funções são atribuídas aos grupos de funções Gerenciamento de conformidade e gerenciamento de organização na página **Permissões** no centro de administração do Exchange. Observação: os administradores globais do Office 365 e Microsoft 365 são automaticamente adicionados como membros do grupo de função gerenciamento da organização no Exchange Online. Para permitir que um usuário pesquise o log de auditoria com o nível mínimo de privilégios, você pode criar um grupo de funções personalizado no Exchange Online, adicionar a função logs de auditoria somente para exibição ou logs de auditoria e, em seguida, adicionar o usuário como um membro do novo grupo de função. Para saber mais, confira [Gerenciar grupos de funções no Exchange Online](https://go.microsoft.com/fwlink/p/?LinkID=730688).

  > [!IMPORTANT]
  > Se você atribuir a um usuário a função logs de Auditoria somente para exibição ou logs de auditoria na página **Permissões** no Centro de conformidade e segurança, eles não conseguirão Pesquisar o log de auditoria. Você deve atribuir as permissões no Exchange Online. Isso ocorre porque o cmdlet subjacente usado para pesquisar o log de auditoria é um cmdlet do Exchange Online.

- Quando uma atividade auditada é realizada por um usuário ou administrador, um registro de auditoria é gerado e armazenado no log de auditoria da sua organização. O período de tempo em que um registro de auditoria é mantido (e ser pesquisado no log de auditoria) depende da sua assinatura do Office 365 ou do Microsoft 365 Enterprise e, especificamente, do tipo de licença atribuído a usuários específicos.

  - Para os usuários que receberam uma licença do Office 365 E5 ou do Microsoft 365 E5 (ou usuários com uma licença do Microsoft 365 E5 ou de descoberta eletrônica e auditoria do Microsoft 365 E5), os registros de auditoria do Azure Active Directory, do Exchange e das atividades do Microsoft Office SharePoint Online são mantidos por um ano por padrão. As organizações também podem criar políticas de retenção de logs de auditoria para manter registros de auditoria de atividades em outros serviços por até um ano. Para obter mais informações, confira [Gerenciar políticas de retenção de log de auditoria](audit-log-retention-policies.md).

    > [!NOTE]
    > Se a sua organização participou do programa de visualização particular para a retenção de registros de auditoria por um ano, a duração da retenção para registros de auditoria gerados antes da data da implantação da disponibilidade geral não será redefinida.

  - Para usuários que atribuiram qualquer outra licença (não E5) do Office 365 ou do Microsoft 365, os registros de auditoria serão mantidos por 90 dias. Para obter uma lista de assinaturas do Office 365 e do Microsoft 365 que oferecem suporte ao log de auditoria unificado, confira [Descrição do serviço do centro de segurança e conformidade](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).

    > [!NOTE]
    > Mesmo quando a auditoria de caixa de correio ativada por padrão, você pode notar que os eventos de auditoria de caixa de correio de alguns usuários não são encontrados nas pesquisas de log de auditoria no centro de conformidade & de segurança ou por meio da API da Atividade de Gestão do Office 365. Para obter mais informações, confira [Obter mais informações sobre o log de auditoria de caixa de correio](enable-mailbox-auditing.md#more-information).

- Caso pretenda desativar a pesquisa de log de auditoria da sua organização, execute o comando a seguir no Windows PowerShell remoto conectado à sua organização do Exchange Online:

  ```powershell
  Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
  ```

    Para ativar a pesquisa de auditoria novamente, execute o seguinte comando no PowerShell do Exchange Online:

  ```powershell
  Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
  ```

  Para saber mais, confira [Desativar a pesquisa de log de auditoria](turn-audit-log-search-on-or-off.md).

- Como mencionado anteriormente, o cmdlet subjacente usado para pesquisar o log de auditoria é um cmdlet do Exchange Online, que é o **Search-UnifiedAuditLog**. Isso significa que você pode usar esse cmdlet para pesquisar o log de auditoria, em vez de usar a página de **Pesquisa de log de auditoria** no Centro de Conformidade e Segurança. Você deve executar esse cmdlet no Windows PowerShell remoto conectado à sua organização do Exchange Online. Para obter mais informações, confira [Search-UnifiedAuditLog](https://go.microsoft.com/fwlink/p/?linkid=834776).

  Para obter informações sobre como exportar os resultados da pesquisa retornados pelo cmdlet **Search-UnifiedAuditLog** para um arquivo CSV, confira a seção "Dicas para exportar e exibir o log de auditoria" em [Exportar, configurar e exibir registros de log de auditoria](export-view-audit-log-records.md#tips-for-exporting-and-viewing-the-audit-log).

- Se quiser baixar dados programaticamente do log de auditoria, recomendamos que você use a API da Atividade de Gestão do Office 365, em vez de usar um script do Windows PowerShell. A API da Atividade de Gestão do Office 365 é um serviço Web REST que você pode usar para desenvolver soluções de monitoramento de operações, segurança e conformidade para a sua organização. Para obter mais informações, confira [Referência da API da Atividade de Gestão do Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).

- Pode levar até 30 minutos ou até 24 horas após a ocorrência de um evento para que o registro de log de auditoria correspondente seja retornado nos resultados de uma pesquisa de log de auditoria. A tabela a seguir mostra o tempo necessário para os diferentes serviços do Office 365.

  |Serviço ou recurso do Microsoft 365|30 minutos|24 horas|
  |:-----|:-----:|:-----:|
  |Defender para Office 365 e Inteligência Contra Ameaças|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Azure Active Directory (eventos de logon do usuário)||![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
  |Azure Active Directory (eventos de administração)||![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
  |Prevenção contra Perda de Dados|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Dynamics 365 CRM||![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
  |Descoberta eletrônica|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Exchange Online|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Microsoft Power Automate||![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
  |Microsoft Project|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Microsoft Stream|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Microsoft Teams|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Aplicativos de energia||![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
  |Power BI|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Centro de Conformidade e Segurança|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Rótulos de confidencialidade||![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
  |SharePoint Online e OneDrive for Business|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Workplace Analytics|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Yammer||![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Microsoft Forms|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
  ||||

- O Azure Active Directory (Azure AD) é o serviço de diretório para o Office 365. O log de Auditoria unificado contém atividades de usuários, grupos, aplicativos, domínios e diretórios realizadas no Centro de administração do Microsoft 365 ou no portal de gerenciamento do Azure. Para obter uma lista completa de eventos do Azure AD, confira [Eventos de relatório de auditoria do Azure Active Directory](https://go.microsoft.com/fwlink/p/?LinkID=616549).

- O log de Auditoria do Power BI não está habilitado por padrão. Para pesquisar atividades do Power BI no log de auditoria, é preciso habilitar a auditoria no portal de administração do Power BI. Para obter instruções, confira a seção "logs de auditoria" no [Portal de administração do Power BI](https://docs.microsoft.com/power-bi/service-admin-portal#audit-logs).

## <a name="search-the-audit-log"></a>Pesquisar o log de auditoria

> [!NOTE]
> Ocorreu um problema com as atividades do Azure AD indisponíveis na ferramenta de pesquisa de log de auditoria de 22 de outubro de 2020 a 6 de novembro de 2020. Essas atividades incluem as atividades de administração de usuários do Azure Active Directory, atividades de administração de grupos, atividades de administração de aplicativos, atividades de administração de funções e atividades de administração de diretórios. Os eventos ausentes para o período de impacto estarão disponíveis durante os próximos dias e o número esperado de 20 de novembro de 2020 a ser concluído. Em alguns casos, os clientes podem observar dados de eventos duplicados para eventos gerados entre 26 de outubro de 2020 e 5 de novembro de 2020.
    
Este é o processo para pesquisar o log de auditoria no Microsoft Office 365.

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
    > Primeiro você precisa ativar o registro em log de auditoria para poder executar uma pesquisa de logs de auditoria. Se o link **Iniciar gravação de atividade de usuários e administradores** for exibido, clique nele para ativar a auditoria. Se você não vir esse link, isso indicará que a auditoria já está ativada na sua organização.

4. Configure os seguintes critérios de pesquisa: 

   1. **Atividades**: Clique na lista suspensa para exibir as atividades que você pode procurar. As atividades de usuários e administradores são organizadas em grupos de atividades relacionadas. Você pode selecionar atividades específicas ou pode clicar no nome do grupo de atividades para selecionar todas as atividades que ele contém. Você também pode clicar em uma atividade selecionada para limpar a seleção. Após a execução da pesquisa, apenas as entradas do log de auditoria das atividades selecionadas são exibidas. Selecionar **Mostrar resultados para todas as atividades** exibirá resultados para todas as atividades realizadas pelo usuário ou grupo de usuários selecionado.

      Mais de 100 atividades de administração e usuário são registradas no log de auditoria. Clique na guia **Atividades auditadas** na parte superior deste artigo para ver as descrições de cada atividade em cada um dos diferentes serviços.

   1. **Data de início** e **Data de término**: Os últimos sete dias são selecionados por padrão. Selecione um intervalo de tempo para exibir os eventos ocorridos durante esse período. A data e a hora são apresentadas no formato UTC (Tempo Universal Coordenado). O intervalo de datas máximo que você pode especificar é de 90 dias. Um erro será exibido se o período selecionado for superior a 90 dias.

      > [!TIP]
      > Se você estiver usando o intervalo máximo de datas de 90 dias, selecione a hora atual para a **Data de início**. Caso contrário, você receberá um erro afirmando que a data de início é anterior à data de término. Se você tiver ativado a auditoria nos últimos 90 dias, o intervalo máximo de datas não poderá começar antes da data em que a auditoria foi ativada.

   1. **Usuários**: Clique nessa caixa e selecione um ou mais usuários para os quais exibir resultados. As entradas do log de auditoria para a atividade selecionada realizada pelos usuários que você seleciona nessa caixa são exibidas na lista de resultados. Deixe essa caixa em branco para retornar entradas para todos os usuários (e contas de serviço) na sua organização.

   1. **Arquivo, pasta ou site**: Digite algum ou todo o nome do arquivo ou da pasta para procurar atividades relacionadas ao arquivo de pasta que contém a palavra-chave especificada. Você também pode especificar uma URL de um arquivo ou pasta. Se você usar uma URL, certifique-se de que o caminho da URL completa ou se você digitou uma parte da URL, não inclua espaços ou caracteres especiais.

      Deixe essa caixa em branco para retornar entradas para todos os arquivos e pastas em sua organização.

      > [!TIP]
      >
      > - Se você estiver procurando por todas as atividades relacionadas a um **site**, adicione o símbolo curinga (\*) após a URL para retornar todas as entradas para esse site. Por exemplo, `"https://contoso-my.sharepoint.com/personal*"`.
      >
      > - Se você estiver procurando por todas as atividades relacionadas a um **arquivo**, adicione o símbolo curinga (\*) antes do nome do arquivo para retornar todas as entradas desse arquivo, por exemplo, `"*Customer_Profitability_Sample.csv"`.

5. Clique em **Pesquisar** para executar a pesquisa usando seus critérios de pesquisa. 

   Os resultados da pesquisa são carregados e, depois de alguns momentos, são exibidos em **Resultados**. Quando a pesquisa estiver concluída, o número de resultados encontrados será exibido. Um máximo de 5.000 eventos serão exibidos no painel **Resultados** em incrementos de 150 eventos. Se mais de 5.000 eventos atenderem aos critérios de pesquisa, os mais 5.000 recentes serão exibidos.

   ![O número de resultados é exibido após a conclusão da pesquisa](../media/986216f1-ca2f-4747-9480-e232b5bf094c.png)

#### <a name="tips-for-searching-the-audit-log"></a>Dicas para pesquisar o log de auditoria

- Você pode selecionar atividades específicas para procurar clicando no nome da atividade. Ou você pode procurar todas as atividades em um grupo (por exemplo **Atividades de arquivo e pasta**) clicando no nome do grupo. Se uma atividade estiver selecionada, você poderá clicar nela para cancelar a seleção. Você também pode usar a caixa de pesquisa para exibir as atividades que contêm a palavra-chave digitada.

  ![Clique no nome do grupo de atividade para selecionar todas as atividades](../media/3cde97cb-6f35-47c0-8612-ecd9c6ac36a3.png)

- É preciso selecionar **Mostrar resultados para todas as atividades** na lista **Atividades** para exibir eventos do log de auditoria de administradores do Exchange. Os eventos desse log de auditoria exibem um nome de cmdlet (por exemplo, **Set-Mailbox**) na coluna **Atividades** nos resultados. Para saber mais, clique na guia **Atividades auditadas**, neste tópico, e clique em **Atividades de administração do Exchange**.

  Da mesma forma, há algumas atividades de auditoria que não têm um item correspondente na lista **Atividades**. Se souber o nome da operação dessas atividades, você poderá procurar todas as atividades e, em seguida, filtrar os resultados digitando o nome da operação na caixa da coluna **Atividade**. Confira [Etapa 3: filtrar os resultados da pesquisa](#step-3-filter-the-search-results) para obter mais informações sobre como filtrar os resultados.

- Clique em **Limpar** para limpar os critérios de pesquisa atuais. O intervalo de datas retorna para os últimos sete dias padrão. Você também pode clicar em **Limpar tudo para mostrar resultados de todas as atividades** para cancelar todas as atividades selecionadas.

- Se 5.000 resultados forem encontrados, você poderá supor que existam mais de 5.000 eventos que atendem aos critérios de pesquisa. Você pode refinar os critérios de pesquisa e executar a pesquisa novamente para retornar menos resultados ou exportar todos os resultados da pesquisa selecionando **Exportar resultados** \> **Baixar todos os resultados**.

### <a name="step-2-view-the-search-results"></a>Etapa 2: Exibir os resultados da pesquisa

Os resultados de uma pesquisa de log de auditoria são exibidos em **Resultados**, na página **Pesquisa de log de Auditoria**. Conforme mencionado anteriormente, um máximo de 5.000 eventos (mais recentes) é exibido em incrementos de 150 eventos. Para exibir mais eventos, você pode usar a barra de rolagem no painel **Resultados** ou pode pressionar **Shift+End** para exibir os próximos 150 eventos.

Os resultados contêm as seguintes informações sobre cada evento retornado pela pesquisa:

- **Data:**: A data e a hora (no formato UTC) de ocorrência do evento.

- **Endereço IP**: O endereço IP do dispositivo que foi usado quando a atividade foi registrada. O endereço IP é exibido no formato de endereço IPv4 ou IPv6.

   > [!NOTE]
  > Para alguns serviços, o valor exibido neste campo pode ser o endereço IP de um aplicativo confiável (por exemplo, Office nos aplicativos Web) chamando o serviço em nome de um usuário e não o endereço IP do dispositivo usado por uma pessoa que executou a atividade. Além disso, para atividades de administrador (ou atividade realizada por uma conta do sistema) para os eventos relacionados ao Active Directory do Azure, o endereço IP não é registrado e o valor exibido neste campo é `null`.

- **Usuário**: O usuário (ou a conta de serviço) que realizou a ação que disparou o evento.

- **Atividade**: A atividade realizada pelo usuário. Esse valor corresponde às atividades que você selecionou na lista suspensa **Atividades**. Para um evento do log de auditoria de administradores do Exchange, o valor nessa coluna é um cmdlet do Exchange.

- **Item**: O objeto que foi criado ou modificado como resultado da atividade correspondente. Por exemplo, o arquivo que foi exibido ou modificado ou a conta de usuário que foi atualizada. Nem todas as atividades têm um valor nessa coluna.

- **Detalhes**: Informações adicionais sobre uma atividade. Novamente, nem todas as atividades têm um valor.

> [!TIP]
> Clique em um cabeçalho de coluna em **Resultados** para classificar os resultados. Você pode classificar os resultados da A até Z ou de Z até A. Clique no cabeçalho **Data** para classificar os resultados do mais antigo para o mais recente, ou vice-versa.

#### <a name="view-the-details-for-a-specific-event"></a>Exibir os detalhes de um evento específico

Você pode exibir mais detalhes sobre um evento clicando no registro de evento na lista de resultados da pesquisa. É exibida uma página de **Detalhes** que contém as propriedades detalhadas do registro de evento. As propriedades exibidas dependem do serviço do em que o evento ocorre. Para exibir esses detalhes, clique **Mais informações**. Para obter descrições, confira [Propriedades detalhadas no log de auditoria](detailed-properties-in-the-office-365-audit-log.md).

![Clique em Mais informações para exibir as propriedades detalhadas do registro de eventos do log de auditoria](../media/6df582ae-d339-4735-b1a6-80914fb77a08.png)

### <a name="step-3-filter-the-search-results"></a>Etapa 3: Filtrar os resultados da pesquisa

Além de classificar, você também pode filtrar os resultados de uma pesquisa de log de auditoria. Esse é um ótimo recurso que pode ajudá-lo a filtrar rapidamente os resultados para um usuário específico ou uma atividade. Você pode criar uma ampla pesquisa e filtrar rapidamente os resultados para ver eventos específicos. Em seguida, você pode restringir os critérios de pesquisa e executar a pesquisa novamente para retornar um conjunto menor e mais conciso de resultados.

Para filtrar os resultados:

1. Execute uma pesquisa de logs de auditoria.

2. Quando os resultados forem exibidos, clique em **Filtrar resultados**.

   Caixas de palavras-chave são exibidas em cada cabeçalho de coluna.

3. Clique em uma das caixas sob um cabeçalho de coluna e digite uma palavra ou frase, dependendo da coluna na qual você está filtrando. Os resultados serão reajustados dinamicamente para exibir os eventos que correspondem ao seu filtro.

   ![Digite uma palavra no filtro para exibir os eventos que correspondam ao filtro](../media/542dc323-a997-402c-934b-cc5e218e50bc.png)

4. Para limpar um filtro, clique em **X** na caixa de filtro ou clique em **Ocultar filtragem**.

> [!TIP]
> Para exibir eventos do log de auditoria de administradores do Exchange, digite um **-** (traço) na caixa de filtro **Atividade**. Isso exibirá nomes de cmdlets, que são exibidos na coluna **Atividade** para eventos de administrador do Exchange. Em seguida, você pode classificar os nomes de cmdlets em ordem alfabética.

### <a name="step-4-export-the-search-results-to-a-file"></a>Etapa 4: Exportar os resultados da pesquisa para um arquivo

Você pode exportar os resultados de uma pesquisa de logs de auditoria para um arquivo CSV (valores separados por vírgula) no computador local. Você pode abrir esse arquivo no Microsoft Excel e usar recursos como pesquisa, classificação, filtragem e divisão de uma única coluna (que contém várias propriedades) em várias colunas.

1. Execute uma pesquisa de logs de auditoria e, em seguida, reveja os critérios de pesquisa até ter os resultados desejados.

2. Clique em **Exportar resultados** e selecione uma das seguintes opções:

   - **Salvar resultados carregados**: Escolha esta opção para exportar somente as entradas que são exibidas em **Resultados** na página **Pesquisa de log de auditoria**. O arquivo CSV baixado contém as mesmas colunas (e dados) exibidas na página (data, User, Activity, item e detalhes). Uma coluna extra (chamada **Mais**) está incluída no arquivo CSV que contém mais informações da entrada do log de auditoria. Uma vez que você está exportando os mesmos resultados que são carregados (e exibíveis) na página **Pesquisa de log de auditoria**, é possível exportar um máximo de 5.000 entradas.

   - **Baixar todos os resultados**: Escolha esta opção para exportar todas as entradas do log de auditoria que atendem aos critérios de pesquisa. Para um grande conjunto de resultados de pesquisa, escolha essa opção para baixar todas as entradas do log de auditoria, além das 5.000 registros de auditoria que podem ser exibidos na página **Pesquisa de log de auditoria**. Essa opção baixa os dados brutos do log de auditoria para um arquivo CSV e contém informações adicionais da entrada do log de auditoria em uma coluna chamada **AuditData**. Pode ser mais demorado baixar o arquivo se você escolher essa opção de exportação porque o arquivo pode ser muito maior do que o baixado se você escolher a opção outra.

     > [!IMPORTANT]
     > É possível baixar no máximo 50 mil entradas para um arquivo CSV de uma única pesquisa de logs de auditoria. Se 50 mil entradas forem baixadas para o arquivo CSV, você poderá supor que existem provavelmente mais de 50 mil eventos que corresponderam aos critérios de pesquisa. Para exportar mais do que esse limite, tente usar um intervalo de datas para reduzir o número de entradas do log de auditoria. Talvez seja necessário executar várias pesquisas com intervalos de datas menores para exportar mais de 50 mil entradas.

3. Após a seleção de uma opção de exportação, é exibida uma mensagem na parte inferior da janela solicitando que você abra o arquivo CSV, salve-o na pasta Downloads ou salve-o em uma pasta específica.

#### <a name="more-information-about-exporting-and-viewing-audit-log-search-results"></a>Informações adicionais sobre como exportar e exibir resultados de pesquisa de log de auditoria

- Se você baixar todos os resultados da pesquisa, o arquivo CSV incluirá uma coluna chamada **AuditData**, que contém informações adicionais sobre cada evento. Os dados nessa coluna consistem em um objeto JSON contendo várias propriedades do registro de log de auditoria. Cada par *propriedade:valor* no objeto JSON é separado por uma vírgula. Você pode usar a ferramenta transformação JSON no editor do Power Query no Excel para dividir la coluna **AuditData** em várias colunas, de modo que cada propriedade no objeto JSON tenha sua própria coluna. Isso permite que você classifique e filtre em uma ou mais dessas propriedades. Para obter instruções passo a passo sobre como usar o editor do Power Query para transformar o objeto JSON, confira [Exportar, configurar e exibir registros de log de auditoria](export-view-audit-log-records.md).

  Depois de dividir a coluna **AuditData**, você pode filtrar a coluna **Operações** para exibir as propriedades detalhadas de um tipo específico de atividade.

- A opção **Baixar todos os resultados** baixa os dados brutos do log de auditoria para um arquivo CSV. Esse arquivo contém nomes de coluna diferentes (CreationDate, UserIds, Operation, AuditData) do que o arquivo que será baixado se você selecionar a opção **Salvar resultados carregados**. Os valores nos dois arquivos CSV diferentes para a mesma atividade também podem ser diferentes. Por exemplo, a atividade na coluna **Ação** no arquivo CSV e pode ter um valor diferente do nome "amigável" que é exibido na coluna **Atividade** na página **Pesquisa do log de auditoria**. Por exemplo, MailboxLogin x usuário conectado à caixa de correio.

- Quando você baixa todos os resultados de uma consulta de pesquisa que contém eventos de diferentes serviços, a coluna **AuditData** no arquivo CSV contém propriedades diferentes, dependendo de qual serviço foi executado na ação. Por exemplo, as entradas do Exchange e os logs de auditoria do Azure Active Directory incluem uma propriedade chamada **ResultStatus** que indica se a ação teve êxito ou não. Essa propriedade não está incluída para eventos no Microsoft Office SharePoint Online. Da mesma forma, os eventos do Microsoft Office SharePoint Online têm uma propriedade que identifica a URL do site para atividades relacionadas a arquivos e pastas. Para reduzir esse comportamento, considere o uso de pesquisas diferentes para exportar os resultados de atividades de um único serviço.

  Para obter uma descrição das propriedades listadas na coluna **AuditData** do arquivo CSV quando você baixa todos os resultados e o serviço ao qual cada uma se aplica, veja [Propriedades detalhadas no log de auditoria](detailed-properties-in-the-office-365-audit-log.md).

## <a name="audited-activities"></a>Atividades auditadas

As tabelas nesta seção descrevem as atividades que são auditadas no Office 365. Você pode procurar esses eventos pesquisando o log de auditoria no centro de segurança e conformidade.

Essas tabelas agrupam atividades relacionadas ou as atividades de um serviço específico. As tabelas incluem o nome amigável que é exibido na lista suspensa **Atividades** e o nome da operação correspondente exibida nas informações detalhadas de um registro de auditoria e no arquivo CSV quando você exporta os resultados da pesquisa. Para obter descrições das informações detalhadas, confira [Propriedades detalhadas no log de auditoria](detailed-properties-in-the-office-365-audit-log.md).

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
        [Microsoft Workplace Analytics](#microsoft-workplace-analytics-activities)
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
        [Atividades de administradores do Exchange](#exchange-admin-audit-log)
    :::column-end:::
:::row-end:::

### <a name="file-and-page-activities"></a>Atividades de arquivo e página

A tabela a seguir descreve as atividades de arquivo e página do SharePoint Online e do OneDrive for Business.

|Nome amigável|Operação|Descrição|
|:-----|:-----|:-----|
|Arquivo acessado|FileAccessed|O usuário ou a conta do sistema acessa um arquivo.|
|(nenhuma)|FileAccessedExtended|Isso está relacionado à atividade "arquivo acessado". Um evento FileAccessedExtended é registrado em log quando a mesma pessoa acessa continuamente um arquivo por um longo período (até 3 horas). <br/><br/> O propósito de fazer o logon de eventos do FileAccessedExtended é reduzir o número de eventos de arquivamento registrados quando um arquivo é acessado continuamente. Isso ajuda a reduzir o ruído de vários registros de FileAccessed para o que é essencialmente a mesma atividade do usuário e permite que você se concentre no evento inicial (e mais importante).|
|Mudança no rótulo de retenção de um arquivo|ComplianceSettingChanged|Um rótulo de retenção foi aplicado ou removido de um documento. Este evento é acionado quando uma etiqueta de retenção é aplicada manualmente ou automaticamente a uma mensagem.|
|Status de registro alterado para bloqueado|LockRecord|O status do registro de um rótulo de retenção que classifica um documento como um registro foi bloqueado. Isso significa que o documento não pode ser modificado ou excluído. Somente os usuários que atribuíram pelo menos a permissão de colaborador de um site podem alterar o status do registro de um documento.|
|Status de registro alterado para desbloqueado|UnlockRecord|O status do registro de um rótulo de retenção que classifica um documento como registro foi desbloqueado. Isso significa que o documento pode ser modificado ou excluído. Somente os usuários que atribuíram pelo menos a permissão de colaborador de um site podem alterar o status do registro de um documento.|
|Arquivo com check-in|FileCheckedIn|O usuário faz check-in de um documento que estava em check-out em uma biblioteca de documentos.|
|Arquivo em check-out|FileCheckedOut|O usuário faz check-out de um documento localizado em uma biblioteca de documentos. Os usuários podem fazer check-out e efetuar alterações em documentos que foram compartilhados com eles.|
|Arquivo copiado|FileCopied|O usuário copia um documento de um site. O arquivo copiado pode ser salvo em outra pasta no site.|
|Arquivo excluído|FileDeleted|O usuário exclui um documento de um site.|
|Arquivo excluído da Lixeira|FileDeletedFirstStageRecycleBin|O usuário exclui um arquivo da lixeira de um site.|
|Arquivo excluído da Lixeira de segundo estágio|FileDeletedSecondStageRecycleBin|O usuário exclui um arquivo da lixeira de segundo estágio de um site.|
|Arquivo excluído marcado como um registro|RecordDelete|Um documento marcado como registro foi excluído. Um documento é considerado um registro quando uma etiqueta de retenção que marca o conteúdo como um registro é aplicada ao documento.|
|Incompatibilidade de confidencialidade em documento detectada|DocumentSensitivityMismatchDetected|O usuário carrega um documento em um site protegido com um rótulo de sensibilidade e o documento tem um rótulo de sensibilidade de prioridade maior do que o rótulo de sensibilidade aplicado ao site. Por exemplo, um documento rotulado como Confidencial será carregado em um site rotulado como Geral. <br/><br/> Esse evento não será disparado se o documento tiver um rótulo de sensibilidade de prioridade mais baixa do que a etiqueta de sensibilidade aplicada ao site. Por exemplo, um documento rotulado como Geral é carregado para um site rotulado como Confidencial. Para obter mais informações sobre a prioridade de rótulos de sensibilidade, confira [Prioridade de rótulo (questões sobre o pedido)](sensitivity-labels.md#label-priority-order-matters).|
|Malware detectado no arquivo|FileMalwareDetected|O mecanismo de antivírus do SharePoint detecta malwares em um arquivo.|
|Check-out de arquivo descartado|FileCheckOutDiscarded|O usuário descarta (ou desfaz) um arquivo de check-out. Isso significa que todas as alterações feitas nesse arquivo durante o check-out serão descartadas, e não serão salvas na versão do documento localizada na biblioteca de documentos.|
|Arquivo baixado|FileDownloaded|O usuário baixa um documento de um site.|
|Arquivo modificado|FileModified|O usuário ou a conta do sistema modifica o conteúdo ou as propriedades de um documento em um site.|
|(nenhum)|FileModifiedExtended|Isso está relacionado à atividade "Arquivo modificado" (FileModified). Um evento FileModifiedExtended é registrado em log quando a mesma pessoa altera continuamente um arquivo por um longo período (até 3 horas). <br/><br/> O propósito do registro de eventos de FileModifiedExtended é reduzir o número de eventos FileModified que são registrados quando um arquivo é modificado continuamente. Isso ajuda a reduzir o ruído de vários registros de FileModified para o que é essencialmente a mesma atividade do usuário e permite que você se concentre no evento de FileModified inicial (e mais importante).|
|Arquivo movido|FileMoved|O usuário move um documento de sua localização atual em um site até uma nova localização.|
|(nenhum)|FilePreviewed|Os usuários visualizam arquivos em um site do Microsoft Office SharePoint Online ou do OneDrive for Business. Esses eventos geralmente ocorrem em grandes volumes com base em uma única atividade, como a exibição de uma galeria de imagens.|
|Consulta de pesquisa realizada|SearchQueryPerformed|A conta de usuário ou sistema executa uma pesquisa no Microsoft Office SharePoint Online ou no OneDrive for Business. Alguns cenários comuns onde uma conta de serviço executa uma consulta de pesquisa incluem a aplicação de uma política de retenção e bloqueios de descoberta eletrônica para sites e contas do OneDrive e a aplicação automática de rótulos de retenção ou sensibilidade no conteúdo do site.|
|Todas as versões secundárias do arquivo foram recicladas|FileVersionsAllMinorsRecycled|O usuário exclui todas as versões secundárias do histórico de versões de um arquivo. As versões excluídas são movidas para a lixeira do site.|
|Todas as versões do arquivo foram recicladas|FileVersionsAllRecycled|O usuário exclui todas as versões do histórico de versões de um arquivo. As versões excluídas são movidas para a lixeira do site.|
|Versão do arquivo reciclada|FileVersionRecycled|O usuário exclui uma versão do histórico de versões de um arquivo. A versão excluída é movida para a lixeira do site.|
|Arquivo renomeado|FileRenamed|O usuário renomeia um documento em um site.|
|Arquivo restaurado|FileRestored|O usuário restaura um documento da lixeira de um site. |
|Arquivo carregado|FileUploaded|O usuário carrega um documento em uma pasta em um site.|
|Página exibida|PageViewed|O usuário exibe uma página no site. Isso não inclui usar um navegador da Web para exibir arquivos localizados em uma biblioteca de documentos.|
|(nenhuma)|PageViewedExtended|Isso está relacionado à atividade "Página exibida" (PageViewed). Um evento PageViewedExtended é registrado em log quando a mesma pessoa vê continuamente uma página da Web por um longo período (até 3 horas). <br/><br/> O propósito de fazer o logon de eventos do PageViewedExtended é reduzir o número de eventos do PageViewed que serão registrados quando uma página for exibida continuamente. Isso ajuda a reduzir o ruído de vários registros de PageViewed para o que é essencialmente a mesma atividade do usuário e permite que você se concentre no evento PageViewed inicial (e mais importante).|
|Exibição sinalizada pelo cliente|ClientViewSignaled|O cliente do usuário (por exemplo, site ou aplicativo móvel) sinalizou que a página indicada foi exibida pelo usuário. Essa atividade geralmente é registrada após um evento PagePrefetched para uma página. <br/><br/>**Observação**: Como os eventos ClientViewSignaled são sinalizados pelo cliente, em vez do servidor, é possível que ele não seja registrado pelo servidor e, portanto, pode não aparecer no log de auditoria. Também é possível que as informações no registro de auditoria não sejam confiáveis. No entanto, como a identidade do usuário é validada por um token usado para criar o sinal, a identidade do usuário listada no registro de auditoria correspondente é precisa. |
|(nenhum)|PagePrefetched|O cliente do usuário (por exemplo, site ou aplicativo móvel) solicitou a página indicada para ajudar a melhorar o desempenho se o usuário navegar por ela. Este evento é registrado para indicar que o conteúdo da página foi servido no cliente do usuário. Esse evento não é um indício definitivo de que o usuário navegou para a página. <br/><br/> Quando o conteúdo da página é renderizado pelo cliente (conforme a solicitação do usuário), um evento ClientViewSignaled deve ser gerado. Nem todos os clientes oferecem suporte para indicar uma pré-busca prévia e, portanto, algumas atividades anteriores podem ser registradas como eventos PageViewed.|
||||

#### <a name="frequently-asked-questions-about-fileaccessed-and-filepreviewed-events"></a>Perguntas frequentes sobre eventos do FileAccessed e FilePreviewed

**Alguma atividade de não usuário pode acionar registros de auditoria FilePreviewed que contêm um agente de usuário como "OneDriveMpc-Transform_Thumbnail"?**

Não conhecemos as situações em que ações não de usuários geram eventos como essas. Ações do usuário, como abrir um cartão de perfil de usuário (clicando no nome ou no endereço de email em uma mensagem no Outlook na Web), gerariam eventos semelhantes.

**As chamadas para o OneDriveMpc-Transform_Thumbnail são sempre acionadas intencionalmente pelo usuário?**

Não. Mas é possível registrar eventos similares como resultado da pré-busca do navegador.

**Se virmos um evento FilePreviewed vindo de um endereço IP registrado pela Microsoft, isso significa que a visualização foi exibida na tela do dispositivo do usuário?**

Não. O evento pode ter sido registrado como resultado da pré-busca do navegador.

**Existem cenários em que um usuário visualizando um documento gera eventos FileAccessed?**

Os eventos FilePreviewed e FileAccess indicam que a chamada do usuário levou a uma leitura do arquivo (ou uma leitura em miniatura do arquivo). Enquanto esses eventos se destinam a se alinhar com as intenções prévias e de acesso, a distinção de eventos não é uma garantia de que o usuário tenha.

#### <a name="the-appsharepoint-user-in-audit-records"></a>O usuário app\@sharepoint em registros de auditoria

Em registros de auditoria para algumas atividades de arquivo (e outras atividades relacionadas ao SharePoint), você pode observar que o usuário que executou a atividade (identificado nos campos User e UserId) é app@sharepoint. Isso indica que o "usuário" que executou a atividade era um aplicativo. Nesse caso, o aplicativo recebeu permissões no SharePoint para executar ações em toda a organização (por exemplo, pesquisar um site do SharePoint ou uma conta do OneDrive) em nome de um usuário, administrador ou serviço. Esse processo de conceder permissões a um aplicativo é chamado acesso do *Somente Aplicativo SharePoint*. Isso indica que a autenticação apresentada ao SharePoint para executar uma ação foi realizada por um aplicativo, em vez de um usuário. Esse é o motivo pelo qual o usuário app@sharepoint está identificado em determinados registros de auditoria. Para saber mais, confira [Conceder acesso usando somente o aplicativo do SharePoint](https://docs.microsoft.com/sharepoint/dev/solution-guidance/security-apponly-azureacs).

Por exemplo, app@sharepoint geralmente é identificado como o usuário para os eventos "Consulta de pesquisa realizada" e "Arquivo acessado". Isso ocorre porque um aplicativo com acesso somente a aplicativos do Microsoft Office SharePoint Online em sua organização executa consultas de pesquisa e acessa arquivos ao aplicar políticas de retenção a sites e contas do OneDrive.

Aqui estão alguns outros cenários em que app@sharepoint pode ser identificado em um registro de auditoria como o usuário que executou uma atividade:

- Grupos do Microsoft 365. Quando um usuário ou administrador cria um novo grupo, os registros de auditoria são gerados para criar um conjunto de sites, atualizar listas e adicionar membros a um grupo do SharePoint. Essas tarefas são executadas em nome do usuário que criou o grupo.

- Microsoft Teams. Semelhante aos grupos do Microsoft 365, os registros de auditoria são gerados para criar um conjunto de sites, atualizar listas e adicionar membros a um grupo do SharePoint quando uma equipe é criada.

- Recursos de conformidade. Quando um administrador implementa recursos de conformidade, como políticas de retenção, bloqueios de descoberta eletrônica e aplicação automática de rótulos de sensibilidade.

Neste e em outros cenários, você também observará que vários registros de auditoria com app@sharepointdas quando o usuário especificado foram criados dentro de um curto período de tempo, geralmente dentro de alguns segundos. Isso também indica que provavelmente eram disparados pela mesma tarefa iniciada pelo usuário. Além disso, os campos ApplicationDisplayName e EventData no registro de auditoria podem ajudá-lo a identificar o cenário ou o aplicativo que disparou o evento.

### <a name="folder-activities"></a>Atividades de pasta

A tabela a seguir descreve as atividades de pasta do SharePoint Online e do OneDrive for Business. Como explicado anteriormente, os registros de auditoria de algumas atividades do SharePoint indicarão o app@sharepoint usuário realizou a atividade do nome do usuário ou do administrador que iniciou a ação. Para saber mais, confira o [Aplicativo\@do usuário do Microsoft Office SharePoint Online em registros de auditoria](#the-appsharepoint-user-in-audit-records).

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

### <a name="sharepoint-list-activities"></a>Atividades de lista do Microsoft Office SharePoint Online

A tabela a seguir descreve as atividades relacionadas ao quando os usuários interagem com listas e itens de lista no SharePoint Online. Como explicado anteriormente, os registros de auditoria de algumas atividades do SharePoint indicarão o app@sharepoint usuário realizou a atividade do nome do usuário ou do administrador que iniciou a ação. Para saber mais, confira o [Aplicativo\@do usuário do Microsoft Office SharePoint Online em registros de auditoria](#the-appsharepoint-user-in-audit-records).

|Nome amigável|Operação|Descrição|
|:-----|:-----|:-----|
|Lista criada|ListCreated|Um usuário criou uma lista do SharePoint.|
|Coluna de lista criada|ListColumnCreated|Um usuário criou uma coluna de lista do Microsoft Office SharePoint Online. Uma coluna de lista é uma coluna associada a uma ou mais listas do Microsoft Office SharePoint Online.|
|Tipo de conteúdo de lista criado|ListContentTypeCreated|Um usuário criou um tipo de conteúdo de lista. Um tipo de conteúdo de lista é um tipo de conteúdo anexado a uma ou mais listas do Microsoft Office SharePoint Online.|
|Item de lista criado|ListItemCreated|Um usuário criou um item em uma lista do SharePoint existente.|
|Coluna de site criada|SiteColumnCreated|Um usuário criou uma coluna de site do Microsoft Office SharePoint Online. Uma coluna de site é uma coluna que não está associada a uma lista. Uma coluna de site também é uma estrutura de metadados que pode ser usada por qualquer lista em uma determinada Web.|
|Tipo de conteúdo de site criado|ContentType do site criado|Um usuário criou um tipo de conteúdo de site. Um tipo de conteúdo de site é um tipo de conteúdo conectado ao site pai.|
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

A tabela a seguir descreve as atividades de compartilhamento e solicitação de acesso do usuário no SharePoint Online e no OneDrive for Business. Para compartilhar eventos, a coluna **Detalhes** em **Resultados** identifica o nome do usuário ou do grupo com o qual o item foi compartilhado e se esse usuário ou grupo é um membro ou convidado na sua organização. Para saber mais, confira [Usar a auditoria de compartilhamento no log de auditoria](use-sharing-auditing.md).

> [!NOTE]
> Os usuários podem ser *membros* ou *convidados* com base na propriedade UserType do objeto de usuário. Um membro é geralmente um funcionário, enquanto um convidado é geralmente um colaborador fora da sua organização. Quando um usuário aceita um convite de compartilhamento (e ainda não faz parte da sua organização), uma conta de convidado é criada para ele no diretório da sua organização. Quando esse usuário convidado tem uma conta no seu diretório, recursos podem ser compartilhados diretamente com ele (sem a necessidade de um convite).

|Nome amigável|Operação|Descrição|
|:-----|:-----|:-----|
|Nível de permissão adicionado ao conjunto de sites|PermissionLevelAdded|Um nível de permissão foi adicionado a um conjunto de sites.|
|Solicitação de acesso aceita|AccessRequestAccepted|Uma solicitação de acesso a um site, pasta ou documento foi aceita, e o usuário solicitante recebeu acesso.|
|Convite de compartilhamento aceito|SharingInvitationAccepted|O usuário (membro ou convidado) aceitou um convite de compartilhamento e recebeu acesso a um recurso. Esse evento inclui informações sobre o usuário que foi convidado e sobre o endereço de email que foi usado para aceitar o convite (eles podem ser diferentes). Com frequência, essa atividade é acompanhada por um segundo evento que descreve como o usuário obteve acesso ao recurso; por exemplo, a adição do usuário a um grupo com acesso ao recurso. |
|Convite de compartilhamento bloqueado|SharingInvitationBlocked|Um convite de compartilhamento enviado por um usuário em sua organização é bloqueado devido a uma política de compartilhamento externo que permite ou nega o compartilhamento externo com base no domínio do usuário de destino. Nesse caso, o convite de compartilhamento foi bloqueado porque: <br/> O domínio do usuário de destino não está incluído na lista de domínios permitidos. <br/> Ou <br/> O domínio do usuário de destino está incluído na lista de domínios bloqueados. <br/> Confira mais informações sobre como permitir ou bloquear o compartilhamento externo com base em domínios em [Compartilhamento de domínios restritos no SharePoint Online e no OneDrive for Business](https://docs.microsoft.com/sharepoint/restricted-domains-sharing).|
|Solicitação de acesso criada|AccessRequestCreated|O usuário solicita acesso a um site, pasta ou documento que ele não tem permissões para acessar.|
|Link compartilhável da empresa criado |CompanyLinkCreated|O usuário criou um link de empresa para um recurso. Links de empresa só podem ser usados pelos membros da sua organização. Eles não podem ser usados por convidados.|
|Um link anônimo criado|AnonymousLinkCreated|O usuário criou um link anônimo para um recurso. Qualquer pessoa com esse link pode acessar o recurso sem ter que se autenticar.|
|Link seguro criado|SecureLinkCreated|Um link de compartilhamento seguro foi criado para esse item.|
|Convite de compartilhamento criado|SharingInvitationCreated|O usuário compartilhou um recurso do SharePoint Online ou do OneDrive for Business com um usuário que não está no diretório da sua organização.|
|Link seguro excluído|SecureLinkDeleted|Um link de compartilhamento seguro foi excluído.|
|Solicitação de acesso negada |AccessRequestDenied|Uma solicitação de acesso a um site, pasta ou documento foi negada.|
|Link compartilhável da empresa removido|CompanyLinkRemoved|O usuário removeu um link de empresa para um recurso. O link não pode mais ser usado para acessar o recurso.|
|Link anônimo removido|AnonymousLinkRemoved|O usuário removeu um link anônimo para um recurso. O link não pode mais ser usado para acessar o recurso.|
|Arquivo, pasta ou site compartilhado|SharingSet|Usuário (membro ou convidado) compartilhou um arquivo, uma pasta ou um site no Microsoft Office SharePoint Online ou no OneDrive for Business com um usuário no diretório da sua organização. O valor na coluna **Detalhes** para esta atividade identifica o nome do usuário com o qual o recurso foi compartilhado e se esse usuário é membro ou convidado. <br/><br/> Com frequência, essa atividade é acompanhada por um segundo evento que descreve como o usuário obteve acesso ao recurso; por exemplo, a adição do usuário a um grupo com acesso ao recurso.|
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
|Computador com permissão para sincronizar arquivos|ManagedSyncClientAllowed|O usuário estabelece com êxito uma relação de sincronização com um site. A relação de sincronização é bem-sucedida porque o computador do usuário é membro de um domínio que foi adicionado à lista de domínios (chamada de *lista de destinatários seguros*) que podem acessar bibliotecas de documentos na sua organização. <br/><br/> Para obter mais informações sobre esse recurso, confira [Usar os cmdlets do Windows PowerShell para habilitar a Sincronização do Microsoft OneDrive para domínios que estão na Lista de Destinatários Confiáveis](https://go.microsoft.com/fwlink/p/?LinkID=534609).|
|Computador impedido de sincronizar arquivos|UnmanagedSyncClientBlocked|O usuário tenta estabelecer uma relação de sincronização com um site em um computador que não é membro do domínio da sua organização ou que é membro de um domínio que não foi adicionado à lista de domínios (chamada de *Lista de destinatários seguros)* que podem acessar bibliotecas de documentos na sua organização. A relação de sincronização não é permitida, e o computador do usuário é impedido de sincronizar, baixar ou carregar arquivos em uma biblioteca de documentos.<br/><br/> Para obter informações sobre esse recurso, confira [Usar os cmdlets do Windows PowerShell para habilitar a Sincronização do Microsoft OneDrive para domínios que estão na Lista de Destinatários Confiáveis](https://go.microsoft.com/fwlink/p/?LinkID=534609).|
|Arquivos baixados no computador|FileSyncDownloadedFull|O usuário estabelece uma relação de sincronização e baixa arquivos de uma biblioteca de documentos com êxito pela primeira vez em seu computador.|
|Alterações de arquivo baixadas no computador|FileSyncDownloadedPartial|O usuário baixa com êxito quaisquer alterações nos arquivos de uma biblioteca de documentos. Essa atividade indica que todas as alterações que foram feitas nos arquivos da biblioteca de documentos foram baixadas no computador do usuário. Apenas as alterações foram baixadas porque a biblioteca de documentos já foi baixada pelo usuário (conforme indicado pela atividade **Arquivos baixados no computador**).|
|Arquivos carregados na biblioteca de documentos|FileSyncUploadedFull|O usuário estabelece uma relação de sincronização e carrega arquivos em uma biblioteca de documentos com êxito pela primeira vez em seu computador.|
|Alterações de arquivo carregadas na biblioteca de documentos|FileSyncUploadedPartial|O usuário carrega com êxito as alterações nos arquivos de uma biblioteca de documentos do. Esse evento indica que todas as alterações feitas na versão local de um arquivo de uma biblioteca de documentos são carregadas com êxito na biblioteca de documentos. Apenas as alterações são carregadas porque esses arquivos já foram carregados pelo usuário (conforme indicado pela atividade dos **Arquivos carregados na biblioteca de documentos**).|
||||

### <a name="site-permissions-activities"></a>Atividades de permissões de site

A tabela a seguir lista os eventos relacionados para atribuir permissões no Microsoft Office SharePoint Online e usar grupos para conceder (e revogar) acesso aos sites. Como explicado anteriormente, os registros de auditoria de algumas atividades do Microsoft Office SharePoint Online indicarão o app@sharepoint usuário realizou a atividade do nome do usuário ou do administrador que iniciou a ação. Para saber mais, confira [O aplicativo\@de usuário do Microsoft Office SharePoint Online em registros de auditoria](#the-appsharepoint-user-in-audit-records).

|Nome amigável|Operação|Descrição|
|:-----|:-----|:-----|
|Administrador de conjunto de sites adicionado|SiteCollectionAdminAdded|O proprietário ou administrador do conjunto de sites adiciona uma pessoa como administrador de conjunto de sites para um site. Os administradores de conjunto de sites têm permissões de controle total para o conjunto de sites e todos os subsites. Essa atividade também será registrada quando um administrador conceder acesso a uma conta do OneDrive do usuário (editando o perfil do usuário no centro de administração do Microsoft Office SharePoint Online ou por [usando o Centro de administração do Microsoft 365](https://docs.microsoft.com/office365/admin/add-users/get-access-to-and-back-up-a-former-user-s-data)).|
|Usuário ou grupo adicionado ao grupo do Microsoft Office SharePoint Online|AddedToGroup|O usuário adicionou um membro ou convidado a um grupo do Microsoft Office SharePoint Online. Pode ter sido uma ação intencional ou o resultado de outra atividade, como um evento de compartilhamento.|
|Herança de nível de permissão interrompida|PermissionLevelsInheritanceBroken|Um item foi alterado para que ele não mais herde os níveis de permissão de seu pai.|
|Compartilhamento de herança interrompido|SharingInheritanceBroken|Um item foi alterado para que não herde mais as permissões de compartilhamento de seu pai.|
|Grupo criado|GroupAdded|O proprietário ou administrador do site cria um grupo para um site ou realiza uma tarefa que resulta na criação de um grupo. Por exemplo, quando um usuário cria um link para compartilhar um arquivo pela primeira vez, um grupo do sistema é adicionado ao site do OneDrive for Business do usuário. Esse evento também pode ser um resultado de um usuário que está criando um link com permissões de edição em um arquivo compartilhado.|
|Grupo excluído|GroupRemoved|O usuário exclui um grupo de um site.|
|Configuração da solicitação de acesso modificada|WebRequestAccessModified|As configurações de solicitação de acesso foram modificadas em um site.|
|Configuração “Membros Podem Compartilhar" modificado|WebMembersCanShareModified|A configuração **Membros Podem Compartilhar** foi modificada em um site.|
|Nível de permissão modificado em um conjunto de sites|PermissionLevelModified|Um nível de permissão foi alterado em um conjunto de sites.|
|Permissões de site modificadas|SitePermissionsModified|O proprietário ou administrador do site (ou a conta do sistema) altera o nível de permissão que é atribuído a um grupo em um site. Essa atividade também será registrada se todas as permissões forem removidas de um grupo. <br/><br/> **OBSERVAÇÃO**: Essa operação foi preterida no Microsoft Office SharePoint Online. Para localizar os eventos relacionados, você pode procurar outras atividades relacionadas à permissão, como **Administrador do conjunto de sites adicionado**, **Usuário ou grupo ao grupo do SharePoint adicionado**, **Usuário permitido para criar grupos**, **Criar grupo**, e **Grupo excluído.**|
|Nível de permissão removido do conjunto de sites|PermissionLevelRemoved|Um nível de permissão foi removido de um conjunto de sites.|
|Administrador de conjunto de sites removido|SiteCollectionAdminRemoved|O proprietário ou administrador do conjunto de sites remove uma pessoa como administrador de conjunto de sites para um site. Essa atividade também será registrada quando um administrador remover a própria lista de administradores de conjunto de sites para a conta do OneDrive de um usuário (editando o perfil de usuário no Centro de Administração do SharePoint Online). Para retornar essa atividade nos resultados de pesquisa do log de auditoria, é preciso procurar todas as atividades.|
|Usuário ou grupo removido do grupo do Microsoft Office SharePoint Online|RemovedFromGroup|O usuário removeu um membro ou convidado de um grupo do Microsoft Office SharePoint Online. Pode ter sido uma ação intencional ou o resultado de outra atividade, como um evento de cancelamento de compartilhamento.|
|Permissões de administrador de site solicitadas|SiteAdminChangeRequest|O usuário solicita ser adicionado como administrador de conjunto de sites para um conjunto de sites. Administradores de conjunto de sites têm permissões de controle total para o conjunto de sites e todos os subsites.|
|Herança de compartilhamento restaurada|SharingInheritanceReset|Uma alteração foi feita para que um item herde permissões de compartilhamento de seu pai.|
|Grupo atualizado|GroupUpdated|O proprietário ou administrador do site altera as configurações de um grupo para um site. Isso pode incluir alterar o nome do grupo, quem pode visualizar ou editar a participação no grupo e como as solicitações de associação são manipuladas.|
||||

### <a name="site-administration-activities"></a>Atividades de administração do site

A tabela a seguir lista os eventos decorrentes de tarefas de administração de sites no SharePoint Online. Como explicado anteriormente, os registros de auditoria de algumas atividades do SharePoint indicarão o app@sharepoint usuário realizou a atividade do nome do usuário ou do administrador que iniciou a ação. Para saber mais, confira [O aplicativo\@de usuário do SharePoint em registros de auditoria](#the-appsharepoint-user-in-audit-records).

|Nome amigável|Operação|Descrição|
|:-----|:-----|:-----|
|Local de dados permitido adicionado|AllowedDataLocationAdded|Um administrador global ou do SharePoint adicionou um local de dados permitido em um ambiente multigeográfico.|
|Agente de usuário isento adicionado|ExemptUserAgentSet|Um administrador global ou do SharePoint adicionou um agente de usuário à lista de agentes de usuário isentos no centro de administração do SharePoint.|
|Administrador de localização geográfica adicionado|GeoAdminAdded|Um administrador global ou do SharePoint adicionou um usuário como um administrador geográfico de um local.|
|Usuário com permissão para criar grupos|AllowGroupCreationSet|O proprietário ou administrador do site adiciona um nível de permissão a um site, que permite que um usuário com essa permissão crie um grupo para esse site.|
|Movimentação geográfica do site cancelada|SiteGeoMoveCancelled|Um administrador global do Microsoft Office SharePoint Online ou do Microsoft Office SharePoint Online cancelou um site do SharePoint ou do OneDrive. O recurso de várias regiões permite que uma organização se estenda por várias regiões do Microsoft datacenter, chamadas GEOS. Para saber mais, confira [Recurso multigeográfico no OneDrive e no SharePoint Online](https://go.microsoft.com/fwlink/?linkid=860840).|
|Política de compartilhamento alterada|SharingPolicyChanged|Um administrador do Microsoft Office SharePoint Online ou um administrador global alterou uma política de compartilhamento do Microsoft Office SharePoint Online usando o Portal de administração do Microsoft 365, o Portal de administração do Microsoft Office SharePoint Online ou o Shell de gerenciamento do SharePoint Online. Qualquer alteração nas configurações da política de compartilhamento na sua organização será registrada. A política que foi alterada é identificada no campo **ModificadoProperties** nas propriedades detalhadas do registro de evento.|
|Política de acesso a dispositivo alterada|DeviceAccessPolicyChanged|Um administrador global do ou do SharePoint alterou a política de dispositivos não gerenciados da sua organização. Esta política controla o acesso ao Microsoft Office SharePoint Online, OneDrive e Microsoft 365 de dispositivos que não fazem parte da sua organização. Configurar essa política exige uma assinatura Enterprise Mobility + Security. Para saber mais, confira [Controlar o acesso de dispositivos não gerenciados](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices).|
|Agentes de usuário isentos alterados|CustomizeExemptUsers|Um administrador global ou do Microsoft Office SharePoint Online personalizou a lista de agentes de usuário isentos no Centro de administração do SharePoint. Você pode especificar quais agentes de usuário deseja se isenta do recebimento de uma página da Web inteira para o índice. Isso significa que, quando um agente de usuário especificado como isento encontra um formulário do InfoPath, o formulário retorna como um arquivo XML, em vez de uma página da Web inteira. Isso torna a indexação de formulários do InfoPath mais rápida.|
|Política de acesso à rede alterada|NetworkAccessPolicyChanged|Um administrador global do ou do Microsoft Office SharePoint Online alterou a política de acesso baseado em local (também chamada de limite de rede confiável) no centro de administração do SharePoint ou usando o Windows PowerShell do Microsoft Office SharePoint Online. Esse tipo de política controla quem pode acessar os recursos do Microsoft Office SharePoint Online e do OneDrive em sua organização com base em intervalos de endereços IP autorizados especificados por você. Para obter mais informações, confira [Controlar o acesso aos dados doMicrosoft Office SharePoint Online e do OneDrive com base no local de rede](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location).|
|Movimentação geográfica do site concluída|SiteGeoMoveCompleted|Uma mudança geográfica do site que foi agendada por um administrador global em sua organização foi concluída com êxito. O recurso multigeográfico permite que uma organização se estenda por várias regiões do Microsoft datacenter, chamadas GEOS. Para saber mais, confira [Recursos multigeográficos no OneDrive e no Microsoft Office SharePoint Online no Office 365](https://go.microsoft.com/fwlink/?linkid=860840).|
|Conexão Enviar Para criada|SendToConnectionAdded|Um administrador global ou do Microsoft Office SharePoint Online cria uma nova conexão enviar para na página de gerenciamento de registros no Centro de administração do SharePoint. Uma conexão enviar para Especifica configurações para um repositório de documentos ou um centro de registros. Quando você cria uma conexão enviar para, um organizador de conteúdo pode enviar documentos para o local especificado.|
|Conjunto de sites criado|SiteCollectionCreated|Um administrador global ou do SharePoint cria um conjunto de sites na sua organização do SharePoint Online ou um usuário provisiona seu site do OneDrive for Business.|
|Site do hub órfão excluído|HubSiteOrphanHubDeleted|Um administrador global ou do Microsoft Office SharePoint Online excluiu um site de Hub órfão, que é um site do Hub que não tem sites associados a ele. Um hub órfão provavelmente é causado pela exclusão do site do Hub original.|
|Conexão Enviar Para excluída|SendToConnectionRemoved|Um administrador global ou do SharePoint exclui uma conexão Enviar Para na página de gerenciamento de Registros no centro de administração do SharePoint.|
|Site excluído|SiteDeleted|O administrador do site exclui um arquivo.|
|Visualização de documentos habilitada|PreviewModeEnabledSet|O administrador do site habilita a visualização de documentos para um site.|
|Fluxo de trabalho legado habilitado|LegacyWorkflowEnabledSet|O proprietário ou administrador do site adiciona o tipo de conteúdo tarefa de fluxo de trabalho do Microsoft Office SharePoint Online 2013 ao site. Os administradores globais também podem habilitar fluxos de trabalho para toda a organização no Centro de administração do SharePoint.|
|Office on Demand habilitado|OfficeOnDemandSet|O administrador do site habilita o Office on Demand, que permite aos usuários acessar a versão mais recente dos aplicativos da área de trabalho do Office. O Office on Demand está habilitado no Centro de administração do SharePoint e requer uma assinatura do Microsoft 365, que inclui os aplicativos completos do Office instalados.|
|Fonte de resultados habilitada para Pesquisas de Pessoas|PeopleResultsScopeSet|O administrador do site cria a fonte de resultado para Pesquisas de Pessoas em um site.|
|RSS feeds habilitados|NewsFeedEnabledSet|O proprietário ou administrador do site habilita RSS feeds para um site. Os administradores globais podem habilitar RSS feeds para toda a organização no Centro de administração do SharePoint.|
|Site associado ao site do hub|HubSiteJoined|Um proprietário de site associa seus sites a um site do hub.|
|Site do hub registrado|HubSiteRegistered|Um administrador global ou do Microsoft Office SharePoint Online cria um site do Hub. Os resultados são que o site está registrado para ser um site do Hub.|
|Local de dados permitido removido|AllowedDataLocationDeleted|Um administrador global ou do SharePoint removeu um local de dados permitido em um ambiente multigeográfico.|
|Administrador de localização geográfica removido|GeoAdminDeleted|Um administrador global ou do SharePoint removeu um usuário como um administrador geográfico de um local.|
|Site renomeado|SiteRenamed|O proprietário ou administrador do site renomeia um site|
|Movimentação geográfica do site agendada|SiteGeoMoveScheduled|Um administrador global do SharePoint agenda uma mudança geográfica de site do SharePoint ou do OneDrive. O recurso de várias regiões permite que uma organização se estenda por várias regiões do Microsoft datacenter, chamadas GEOS. Para saber mais, confira [Recursos multigeográficos no OneDrive e no SharePoint Online no Office 365](https://go.microsoft.com/fwlink/?linkid=860840).|
|Definir site do host|HostSiteSet|Um administrador global ou do SharePoint altera o site designado para hospedar sites pessoais ou do OneDrive for Business.|
|Definir a cota de armazenamento para uma localização geográfica|GeoQuotaAllocated|Um administrador global ou do SharePoint configurou a cota de armazenamento para uma localização geográfica em um ambiente multigeográfico.|
|Site desvinculado do site do hub|HubSiteUnjoined|Um proprietário de site dissocia o site de um site do hub.|
|Site do hub não registrado|HubSiteUnregistered|Um administrador do Microsoft Office SharePoint Online ou global não registra um site como um site do Hub. Quando um site do hub é cancelado, ele não funciona mais como um site do Hub.|
||||

### <a name="exchange-mailbox-activities"></a>Atividades de caixa de correio do Exchange

A tabela a seguir lista as atividades que podem ser registradas no log de auditoria de caixa de correio. As atividades de caixa de correio executadas pelo proprietário da caixa de correio, por um usuário delegado ou por um administrador do são automaticamente registradas no log de auditoria por até 90 dias. É possível que um administrador desabilite o registro em log de auditoria de caixa de correio para todos os usuários em sua organização. Nesse caso, nenhuma ação de caixa de correio do usuário será registrada. Para obter mais informações, consulte [Gerenciar a auditoria de caixa de correio](enable-mailbox-auditing.md).

 Você também pode procurar atividades de caixa de correio usando o cmdlet [Search-MailboxAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) no Windows PowerShell do Exchange Online.

|Nome amigável|Operação|Descrição|
|:-----|:-----|:-----|
|Itens de caixa de correio acessados|MailItemsAccessed|As mensagens foram lidas ou acessadas na caixa de correio. Os registros de auditoria para esta atividade são disparados de duas maneiras: quando um cliente de email (como o Outlook) executa uma operação de vinculação em mensagens ou quando os protocolos de email (como o Exchange ActiveSync ou IMAP) sincronizam em uma pasta de email. Essa atividade é registrada apenas para usuários com uma licença do Office 365 ou do Microsoft 365 e5. A análise de registros de auditoria para esta atividade é útil durante a investigação de uma conta de email comprometida. Para saber mais, confira a seção "acesso a eventos cruciais para investigações" na [Auditoria Avançada](advanced-audit.md#access-to-crucial-events-for-investigations). |
|Permissões de caixa de correio delegada adicionadas|AddMailboxPermissions|Um administrador atribuiu a permissão de caixa de correio do FullAccess a um usuário (conhecido como representante) à caixa de correio de outra pessoa. A permissão FullAccess permite ao representante abrir a caixa de correio de outra pessoa e ler e gerenciar o conteúdo da caixa de correio.|
|Adicionado ou removido usuário com acesso delegado à pasta de calendário|UpdateCalendarDelegation|Um usuário foi adicionado ou removido como um representante para o Calendário do Outlook da caixa de correio de outro usuário. A delegação de calendário concede a outra pessoa na mesma organização permissões para gerenciar o calendário do proprietário da caixa de correio.|
|Permissões adicionadas à pasta|AddFolderPermissions|Uma permissão de pasta foi adicionada. As permissões de pasta controlam quais usuários em sua organização podem acessar pastas em uma caixa de correio e as mensagens localizadas nelas.|
|Mensagens copiadas para outra pasta|Copiar|Uma mensagem foi copiada para outra pasta.|
|Criação de item de caixa de correio|Criar|Um item é criado na pasta Calendário do Outlook, contatos, anotações ou tarefas da caixa de correio. Por exemplo, uma nova solicitação de reunião é criada. Criar, enviar ou receber uma mensagem não é auditada. Além disso, criar uma pasta de caixa de correio não é auditada.|
|Criada nova regra da caixa de entrada do Outlook Web App|New-InboxRule|Um proprietário da caixa de correio ou outro usuário com acesso à caixa de correio criou uma regra da caixa de entrada do Outlook Web App.|
|Mensagens excluídas da pasta Itens Excluídos|SoftDelete|Uma mensagem foi permanentemente excluída ou foi excluída da pasta Itens Excluídos. Esses itens são movidos para a pasta Itens Recuperáveis. As mensagens também são movidas para a pasta Itens Recuperáveis quando um usuário as seleciona e pressiona **Shift+Delete**.|
|Mensagem rotulada como um registro|ApplyRecordLabel|Uma mensagem foi classificada como um registro. Isso ocorre quando um rótulo de retenção que classifica o conteúdo como um registro é automaticamente aplicado a uma mensagem.|
|Mensagens movidas para outra pasta|Mover|Uma mensagem foi movida para outra pasta.|
|Mensagens movidas para a pasta Itens Excluídos|MoveToDeletedItems|Uma mensagem foi excluída e movida para a pasta Itens Excluídos.|
|Permissão de pasta modificada|UpdateFolderPermissions|Uma permissão da pasta foi alterada. As permissões de pasta controlam quais usuários da organização podem acessar as pastas de uma caixa de correio e as mensagens incluídas nessas pastas.|
|Modificada regra de caixa de entrada do Outlook Web App|Set-InboxRule|Um proprietário da caixa de correio ou outro usuário com acesso à caixa de correio modificou uma regra da caixa de entrada usando o Outlook Web App.|
|Mensagens limpas da caixa de correio|HardDelete|Uma mensagem foi limpa da pasta Itens Recuperáveis (permanentemente excluída da caixa de correio).|
|Permissões de caixa de correio do representante removidas|Remove-MailboxPermission|Um administrador removeu a permissão FullAccess (que foi atribuída a um representante) da caixa de correio de uma pessoa. Depois que a permissão FullAccess for removida, o representante não pode abrir a caixa de correio de outra pessoa ou acessar nenhum conteúdo nela.|
|Permissões removidas da pasta|RemoveFolderPermissions|Foi removida uma permissão de pasta. As permissões de pasta controlam quais usuários em sua organização podem acessar pastas em uma caixa de correio e as mensagens localizadas nelas.|
|Mensagem enviada|Enviar|Uma mensagem foi enviada, respondida ou encaminhada. Essa atividade é registrada apenas para usuários com uma licença do Office 365 ou do Microsoft 365 E5. Para saber mais, confira a seção "Acesso a eventos cruciais para investigações" na [Auditoria Avançada](advanced-audit.md#access-to-crucial-events-for-investigations).|
|Mensagem enviada com permissões Enviar Como|SendAs|Uma mensagem foi enviada usando a permissão SendAs. Isso significa que outro usuário enviou a mensagem como se fosse proveniente do proprietário da caixa de correio.|
|Mensagem enviada com permissões Enviar em Nome de|SendOnBehalf|Uma mensagem foi enviada usando a permissão SendOnBehalf. Isso significa que outro usuário enviou a mensagem em nome do proprietário da caixa de correio. A mensagem indica ao destinatário quem a mensagem foi enviada em nome e quem a enviou.|
|Regras atualizadas da caixa de entrada do cliente do Outlook|UpdateInboxRules|Um proprietário da caixa de correio ou outro usuário com acesso à caixa de correio modificou uma regra da caixa de entrada no cliente do Outlook.|
|Mensagem atualizada|Atualizar|Uma mensagem ou suas propriedades foram alteradas.|
|Usuário entrou na caixa de correio|MailboxLogin|O usuário entrou em sua caixa de correio.|
|Etiquetar a mensagem como um registro||Um usuário aplicou um rótulo de retenção a uma mensagem de e-mail, e essa etiqueta é configurada para marcar o item como um registro. |
||||

### <a name="user-administration-activities"></a>Atividades de administração de usuários

A tabela a seguir lista as atividades de administração de usuários que são registradas quando um administrador adiciona ou altera uma conta de usuário usando o Microsoft 365 ou o portal de gerenciamento do Azure.

|Atividade|Operação|Descrição|
|:-----|:-----|:-----|
|Usuário adicionado|Adicionar usuário|Uma conta de usuário foi criada.|
|Licença de usuário alterada|Alterar licença de usuário|A licença atribuída a um usuário foi alterada. Para ver quais licenças foram alteradas, veja a atividade **Usuário atualizado** correspondente.|
|Senha do usuário alterada|Alterar senha do usuário|Um usuário altera a senha. A redefinição de senha de autoatendimento deve ser habilitada (para todos os usuários selecionados) em sua organização para permitir que os usuários redefinam a senha. Você também pode acompanhar a atividade de redefinição de senhas de autoatendimento no Azure Active Directory. Para obter mais informações, consulte [Opções de relatório para o gerenciamento de senhas do Azure AD](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-reporting).
|Usuário excluído|Excluir usuário|Uma conta de usuário foi excluída.|
|Redefinir senha do usuário|Redefinir senha do usuário|O administrador redefine a senha de um usuário.|
|Propriedade definida que força o usuário a alterar a senha|Definir alteração forçada de senha do usuário|O administrador definiu a propriedade que força o usuário a redefinir a senha da próxima vez que esse usuário entrar no Office 365.|
|Definir propriedades de licenças|Definir propriedades de licenças|O administrador modifica as propriedades de uma licença atribuída a um usuário.|
|Usuário atualizado|Atualizar usuário|O administrador altera uma ou mais propriedades de uma conta de usuário. Para obter uma lista das propriedades do usuário que podem ser atualizadas, confira a seção "Atualizar atributos do usuário" nos [Eventos de relatório de Auditoria do Azure Active Directory](https://go.microsoft.com/fwlink/p/?LinkID=616549).|
||||

### <a name="azure-ad-group-administration-activities"></a>Atividades de administração de grupos do Azure Active Directory

A tabela a seguir lista as atividades de administração de grupos que são registradas quando um administrador ou um usuário cria ou altera um grupo do Microsoft 365 ou quando um administrador cria um grupo de segurança usando o centro de administração do Microsoft 365 ou o portal de gerenciamento do Azure. Para saber mais sobre grupos no Office 365, confira [Exibir, criar e excluir grupos no Centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/create-groups).

|Nome amigável|Operação|Descrição|
|:-----|:-----|:-----|
|Grupo adicionado|Adicionar grupo|Um grupo foi criado.|
|Membro adicionado ao grupo|Adicionar membro ao grupo|Um membro foi adicionado a um grupo.|
|Grupo excluído|Excluir grupo|Um grupo foi excluído.|
|Membro removido do grupo|Remover membro do grupo|Um membro foi removido de um grupo.|
|Grupo atualizado|Atualizar grupo|Uma propriedade de um grupo foi alterada.|
||||

### <a name="application-administration-activities"></a>Atividades de administração de aplicativos

A tabela a seguir lista as atividades de administração de aplicativos que são registradas quando um administrador adiciona ou altera um aplicativo que está registrado no Azure Active Directory. Qualquer aplicativo que depende do Azure Active Directory para autenticação deve ser registrado no diretório.

|Nome amigável|Operação|Descrição|
|:-----|:-----|:-----|
|Entrada da delegação adicionada|Adicionar entrada de delegação|Uma permissão de autenticação foi criada/concedida a um aplicativo no Azure AD.|
|Entidade de serviço adicionada|Adicionar entidade de serviço|Um aplicativo foi registrado no Azure Active Directory. Um aplicativo é representado por uma entidade de serviço no diretório.|
|Credenciais adicionadas a uma entidade de serviço |Adicionar credenciais de entidade de serviço|Credenciais foram adicionadas a uma entidade de serviço no Azure Active Directory. Um princípio de serviço representa um aplicativo no diretório.|
|Entrada de delegação removida|Remover entrada de delegação|Uma permissão de autenticação foi removida de um aplicativo no Azure AD.|
|Entidade de serviço removida do diretório|Remover entidade de serviço|Um aplicativo foi excluído/cancelado no Azure Active Directory. Um aplicativo é representado por uma entidade de serviço no diretório.|
|Credenciais removidas de uma entidade de serviço |Remover credenciais da entidade de serviço|Credenciais foram removidas de uma entidade de serviço no Azure Active Directory. Um princípio de serviço representa um aplicativo no diretório.|
|Definir entrada de delegação|Definir entrada de delegação|Uma permissão de autenticação foi atualizada para um aplicativo no Azure AD.|
||||

### <a name="role-administration-activities"></a>Atividades de administração de funções

A tabela a seguir lista as atividades de administração de funções do Azure AD registradas quando um administrador gerencia funções de administração no Microsoft 365 ou no portal de gerenciamento do Azure.

|Nome amigável|Operação|Descrição|
|:-----|:-----|:-----|
|Adicionar membro à função|Adicionar membro de função à função|Usuário adicionado a uma função de administração no Microsoft 365.|
|Usuário removido de uma função de diretório|Remover membro de função da função|Usuário removido de uma função de administração no Microsoft 365.|
|Definir informações de contato da empresa|Definir informações de contato da empresa|Preferências de contato no nível da empresa atualizadas para a sua organização do. Isso inclui endereços de email para emails relacionados a assinaturas enviados pelo Microsoft 365 e notificações técnicas sobre serviços do.|
||||

### <a name="directory-administration-activities"></a>Atividades de administração de diretórios

A tabela a seguir lista as atividades relacionadas a diretórios e domínios do Azure AD que são registradas quando um administrador gerencia sua organização no Centro de administração do Microsoft 365 ou no portal de gerenciamento do Azure.

|Nome amigável|Operação|Descrição|
|:-----|:-----|:-----|
|Domínio adicionado à empresa|Adicionar domínio à empresa|Domínio adicionado à sua organização.|
|Parceiro adicionado ao diretório|Parceiro adicionado à empresa|Parceiro (administrador delegado) adicionado à sua organização.|
|Domínio removido da empresa|Remover domínio da empresa|Domínio removido da sua organização.|
|Parceiro removido do diretório|Remover parceiro da empresa|Parceiro (administrador delegado) removido da sua organização.|
|Definir informações da empresa|Definir informações da empresa|Informações da empresa atualizadas para a sua organização. Isso inclui endereços de email para emails relacionados a assinaturas enviados pelo Microsoft 365 e notificações técnicas sobre os serviços do Microsoft 365.|
|Definir autenticação de domínio|Definir autenticação de domínio|Configuração de autenticação de domínio alterada para a sua organização.|
|Configurações de federação atualizadas para um domínio|Definir configurações de federação no domínio|Configurações de federação (compartilhamento externo) alteradas para a sua organização.|
|Definir política de senha|Definir política de senha|Restrições de comprimento e caracteres alteradas para senhas de usuário na sua organização.|
|Sincronização do Azure AD ativada|Definir sinalizador DirSyncEnabled ativado na empresa|Definir a propriedade que habilita um diretório para sincronização do Azure AD.|
|Domínio atualizado|Atualizar domínio|Configurações de um domínio atualizadas na sua organização.|
|Domínio verificado|Verificar domínio|Foi verificado que a sua organização é a proprietária de um domínio.|
|Domínio confirmado de email verificado|Verificar domínio confirmado de email|Verificação de email usada para confirmar que a sua organização é proprietária de um domínio.|
||||

### <a name="ediscovery-activities"></a>Atividades de Descoberta Eletrônica

Atividades relacionadas a pesquisa de conteúdo e descoberta eletrônica que são executadas no centro de segurança e conformidade ou executando os cmdlets do Windows PowerShell correspondentes são registradas no log de auditoria. Isso inclui as seguintes atividades:

- Criar e gerenciar casos de Descoberta Eletrônica

- Criar, iniciar e editar pesquisas de conteúdo

- Executar ações de pesquisa de conteúdo, como visualização, exportação e exclusão de resultados de pesquisa

- Configurar a filtragem de permissões para pesquisa de conteúdo

- Gerenciar a função de administrador de Descoberta Eletrônica

Para obter uma lista e uma descrição detalhada das atividades de Descoberta Eletrônica que são registradas, veja [Procurar atividades de Descoberta Eletrônica no log de auditoria](search-for-ediscovery-activities-in-the-audit-log.md).

> [!NOTE]
> Leva até 30 minutos para os eventos que resultam das atividades listadas em **Atividades da descoberta eletrônica** e **Atividades da descoberta eletrônica avançada** na lista suspensa **Atividades** a ser exibida nos resultados da pesquisa. Inversamente, demora até 24 horas para que os eventos correspondentes das atividades de cmdlet da descoberta eletrônica apareçam nos resultados da pesquisa.

### <a name="advanced-ediscovery-activities"></a>Atividades de Descoberta Eletrônica Avançada

Você também pode pesquisar o log de auditoria para atividades na descoberta eletrônica avançada. Para obter uma descrição dessas atividades, confira a seção "Atividades da descoberta eletrônica avançada" no [Pesquisar atividades de descoberta eletrônica no de log de auditoria](search-for-ediscovery-activities-in-the-audit-log.md#advanced-ediscovery-activities).

### <a name="power-bi-activities"></a>Atividades do Power BI

Você pode pesquisar o log de auditoria das atividades do Power BI. Para saber mais sobre as atividades do Power BI, confira a seção "Atividades auditadas pelo Power BI" no [Usando a auditoria dentro da sua organização](https://docs.microsoft.com/power-bi/service-admin-auditing#activities-audited-by-power-bi).

O log de Auditoria do Power BI não está habilitado por padrão. Para pesquisar atividades do Power BI no log de auditoria, é preciso habilitar a auditoria no portal de administração do Power BI. Para obter instruções, confira a seção "logs de auditoria" no [Portal de administração do Power BI](https://docs.microsoft.com/power-bi/service-admin-portal#audit-logs).

### <a name="microsoft-workplace-analytics-activities"></a>Atividades do Microsoft Workplace Analytics

O Workplace Analytics fornece informações sobre como os grupos colaboram em toda a organização. A tabela a seguir lista as atividades executadas pelos usuários que recebem a função de administrador ou as funções de analista no workplace Analytics. Os usuários que atribuiram a função de analista têm acesso total a todos os recursos de serviço e usam a análise de produto para fazer. Os usuários que receberam a função de administrador podem definir as configurações de privacidade e os padrões do sistema, além de poder preparar, carregar e verificar dados organizacionais no workplace Analytics. Para saber mais, confira [Workplace Analytics](https://docs.microsoft.com/workplace-analytics/index-orig).

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

Você pode pesquisar o log de auditoria de atividades de usuários e administradores no Microsoft Teams. As equipes são um espaço de trabalho centralizado em chat no Office 365. Ele reúne as conversas, as reuniões, os arquivos e as anotações de uma equipe em um único lugar. Para obter descrições das atividades de equipe que são auditadas, confira [Pesquisar eventos no log de auditoria do Microsoft Teams](https://docs.microsoft.com/microsoftteams/audit-log-events#teams-activities).

### <a name="microsoft-teams-healthcare-activities"></a>Atividades do Microsoft Teams Healthcare

Se a sua organização estiver usando o [Aplicativo de Pacientes](https://docs.microsoft.com/MicrosoftTeams/expand-teams-across-your-org/healthcare/patients-app-overview) do Microsoft Teams, você poderá pesquisar o log de auditoria para atividades relacionadas ao usando o aplicativo pacientes. Se o seu ambiente estiver configurado para oferecer suporte a aplicativos do paciente, um grupo de atividades adicionais para essas atividades estará disponível na lista seletora **Atividades**.

![Atividades do Microsoft Teams Healthcare na lista seletora Atividades](../media/TeamsHealthcareAuditActivities.png)

Para obter uma descrição das atividades do aplicativos Patients, confira [Logs de auditoria para aplicativo Patients](https://docs.microsoft.com/MicrosoftTeams/expand-teams-across-your-org/healthcare/patients-audit).

### <a name="microsoft-teams-shifts-activities"></a>Atividades de Turnos do Microsoft Teams

Se a sua organização estiver usando o aplicativo turnos no Microsoft Teams, você poderá pesquisar o log de auditoria para atividades relacionadas ao usando o aplicativo turnos. Se o seu ambiente estiver configurado para dar suporte a aplicativos turnos, um grupo de atividades adicionais para essas atividades estará disponível na lista seletora **Atividades**.

Para obter uma descrição das atividades do aplicativo Turnos, confira [Pesquisar eventos no log de auditoria no Microsoft Teams](https://docs.microsoft.com/microsoftteams/audit-log-events#shifts-in-teams-activities).

### <a name="yammer-activities"></a>Atividades do Yammer

A tabela a seguir lista as atividades de usuários e de administradores no Yammer que estejam conectados ao log de auditoria. Para retornar atividades relacionadas ao Yammer no log de auditoria, escolha **Mostrar resultados para todas as atividades** na lista **Atividades**. Use as caixas de intervalo de datas e a lista de **Usuários** para restringir os resultados da pesquisa.

|Nome amigável|Operação|Descrição|
|:-----|:-----|:-----|
|Política de retenção de dados alterada|SoftDeleteSettingsUpdated|O administrador verificado atualiza a configuração da política de retenção de dados da rede para "exclusão irreversível" ou "exclusão temporária". Somente administradores verificados podem realizar essa operação.|
|Configuração de rede alterada|NetworkConfigurationUpdated|O administrador de rede ou administrador verificado altera as configurações da rede do Yammer. Isso inclui a definição do intervalo de exportação de dados e de habilitação do chat.|
|Configurações de perfil de rede alteradas|ProcessProfileFields|O administrador de rede ou verificado altera as informações que aparecem em perfis de membro para a rede de usuários da rede.|
|Modo de Conteúdo Particular modificado|SupervisorAdminToggled|O administrador verificado ativa ou desativa o *Modo de conteúdo particular*. Esse modo permite a um administrador exibir as postagens em grupos privados e exibir mensagens particulares entre usuários individuais (ou grupos de usuários). Somente administradores verificados podem realizar essa operação.|
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

Você pode pesquisar o log de auditoria para atividades em automatização de energia (conhecida anteriormente como Microsoft Flow). Essas atividades incluem criar, editar e excluir fluxos, além de alterar as permissões de fluxo. Para obter informações sobre auditoria de atividades de automação de energia, confira o blog [Eventos de auditoria de fluxo da Microsoft que estão disponíveis no Centro de Conformidade e Segurança](https://flow.microsoft.com/blog/security-and-compliance-center).

### <a name="microsoft-power-apps-activities"></a>Atividades do Microsoft Power Apps

Você pode pesquisar o log de auditoria para atividades relacionadas a aplicativos em aplicativos de poder. Essas atividades incluem criar, iniciar e publicar um aplicativo. Atribuir permissões a aplicativos também é auditado. Para obter uma descrição de todas as atividades de aplicativos de energia, confira o [Registro de atividades para aplicativos de energia](https://docs.microsoft.com/power-platform/admin/logging-powerapps#what-events-are-audited).

### <a name="microsoft-stream-activities"></a>Atividades do Microsoft Stream

Você pode pesquisar o log de auditoria para atividades no Microsoft Stream. Essas atividades incluem atividades de vídeo executadas por usuários, atividades de canal de grupo e atividades de administração, como gerenciar usuários, gerenciar as configurações da organização e exportar relatórios. Para obter uma descrição dessas atividades, confira a seção "Ações conectadas no fluxo" nos [Logs de Auditoria no Microsoft Stream](https://docs.microsoft.com/stream/audit-logs#actions-logged-in-stream).

### <a name="content-explorer-activities"></a>Atividades do explorador de conteúdo

A tabela a seguir lista as atividades no Gerenciador de conteúdo que estão conectadas no log de auditoria do. Gerenciador de conteúdo, que é acessado na ferramenta classificações de dados no Centro de conformidade do Microsoft 365. Para saber mais, confira [Usar o conteúdo de classificação de dados do Explorer](data-classification-content-explorer.md).

|Nome amigável|Operação|Descrição|
|:-----|:-----|:-----|
|Item acessado|LabelContentExplorerAccessedItem|Um administrador (ou um usuário que seja membro do grupo de funções do Visualizador de conteúdo do explorador de conteúdo) usa o explorador de conteúdo para exibir uma mensagem de e-mail ou documento do SharePoint/OneDrive.|
||||

### <a name="quarantine-activities"></a>Atividades de quarentena

A tabela a seguir lista as atividades de quarentena que podem ser pesquisadas no log de auditoria do. Para obter mais informações sobre quarentena, confira o artigo [Quarentena de mensagens de email no Office 365](../security/office-365-security/quarantine-email-messages.md).

|Nome amigável|Operação|Descrição|
|:-----|:-----|:-----|
|Mensagem de quarentena excluída|QuarantineDelete|Um usuário excluiu uma mensagem de e-mail considerada nociva.|
|Mensagem de quarentena exportada|QuarantineExport|Um usuário exportou uma mensagem de e-mail considerada nociva.|
|Mensagem de quarentena exibida|QuarantinePreview|Um usuário visualizou uma mensagem de e-mail que foi considerada nociva.|
|Mensagem de quarentena liberada|QuarantineRelease|Um usuário liberou uma mensagem de e-mail da quarentena que foi considerada prejudicial.|
|Cabeçalho de mensagem de quarentena exibida|QuarantineViewHeader|Um usuário exibiu o cabeçalho uma mensagem de e-mail considerada nociva.|
||||

### <a name="microsoft-forms-activities"></a>Atividades do Microsoft Forms

A tabela a seguir lista as atividades de usuários e administradores no Microsoft Forms que são registradas no log de auditoria. O Microsoft Forms é uma ferramenta de formulários/testes/pesquisa usada para coletar dados para análise. 

Onde indicado abaixo nas descrições, algumas operações contêm parâmetros adicionais de atividade.

> [!NOTE]
> Se uma atividade formulários for realizada por um coautor ou um respondedor anônimo, ela será registrada um pouco diferente. Para saber mais, confira a seção [Atividades de formulários executadas por coautores e respondentes anônimos](#forms-activities-performed-by-coauthors-and-anonymous-responders).

|Nome amigável|Operação|Descrição|
|:-----|:-----|:-----|
|Comentário criado|CreateComment|O proprietário do formulário adiciona um comentário ou pontuação a um teste.|
|Formulário criado|CreateForm|O proprietário do formulário cria um novo formulário.|
|Formulário editado|EditForm|O proprietário do formulário edita um formulário, como criar, remover ou editar uma pergunta. A propriedade *EditOperation:string* indica o nome da operação de edição. As possíveis operações são:<br/>- CreateQuestion<br/>- CreateQuestionChoice <br/>- DeleteQuestion <br/>- DeleteQuestionChoice <br/>- DeleteFormImage <br/>- DeleteQuestionImage <br/>- UpdateQuestion <br/>- UpdateQuestionChoice <br/>- UploadFormImage/Bing/Onedrive <br/>- UploadQuestionImage <br/>- ChangeTheme <br><br>FormImage inclui qualquer lugar dentro do Forms que o usuário pode carregar uma imagem, como em uma consulta ou como um tema de plano de fundo.|
|Formulário movido|MoveForm|O proprietário do formulário move um formulário. <br><br>Propriedade DestinationUserId:string indica o ID de usuário da pessoa que moveu o formulário. Propriedade NewFormId:string é o novo ID do formulário recentemente copiado.|
|Formulário excluído |DeleteForm|O proprietário do formulário exclui um formulário. Isso inclui SoftDelete (opção de exclusão usada e formulário movido para a lixeira) e HardDelete (lixeira esvaziada).|
|Formulário exibido (tempo de design)|ViewForm|O proprietário do formulário abre um formulário existente para edição.|
|Formulário visualizado|PreviewForm|O proprietário do formulário visualiza um formulário usando a função Visualização.|
|Formulário exportado|ExportForm|O proprietário do formulário exporta os resultados para o Excel. <br><br>A propriedade ExportFormat:string indica se o arquivo do Excel foi baixado ou está online.|
|Formulário de compartilhamento permitido para cópia|AllowShareFormForCopy|O proprietário do formulário cria um link de modelo para compartilhar o formulário com outros usuários. Esse evento é registrado quando o proprietário do formulário clica para gerar uma URL de modelo.|
|Formulário de compartilhamento não permitido para cópia|DisallowShareFormForCopy|O proprietário do formulário exclui o link do modelo.|
|Coautor do formulário adicionado|AddFormCoauthor|Um usuário usa um link de colaboração para criar e exibir respostas. Esse evento é registrado em log quando um usuário usa uma URL colaboração (não quando a URL do colaboração é gerada primeiro).|
|Coautor do formulário removido|RemoveFormCoauthor|O proprietário do formulário exclui um link de colaboração.|
|Página de resposta exibida|ViewRuntimeForm|O usuário abriu uma página de resposta para exibição. Esse evento é registrado independentemente de o usuário submeter ou não uma resposta.|
|Resposta criada|CreateResponse|Semelhante a receber uma nova resposta.  Um usuário enviou uma resposta a um formulário. <br><br>A propriedade ResponseId:string e a propriedade ResponderId:string indicam qual resultado está sendo visualizado. <br><br>Para um respondente anônimo, a propriedade ResponderId será nula.|
|Resposta atualizada|UpdateResponse|O proprietário do formulário atualizou um comentário ou uma pontuação em um teste. <br><br>A propriedade ResponseId:string e a propriedade ResponderId:string indicam qual resultado está sendo visualizado. <br><br>Para um respondente anônimo, a propriedade ResponderId será nula.|
|Todas as respostas excluídas|DeleteAllResponses|O proprietário exclui todos os dados de resposta.|
|Resposta excluída|DeleteResponse|O proprietário do formulário exclui uma resposta. <br><br>A propriedade ResponseId:string indica qual resposta está sendo excluída.|
|Respostas exibidas|ViewResponses|O proprietário do formulário exibe a lista agregada de respostas. <br><br>A propriedade ViewType:string indica se o proprietário do formulário está exibindo Detalhes ou Agregação|
|Resposta exibida|ViewResponse|O proprietário do formulário exibe uma resposta específica. <br><br>A propriedade ResponseId:string e a propriedade ResponderId:string indicam qual resultado está sendo visualizado. <br><br>Para um respondente anônimo, a propriedade ResponderId será nula.|
|Link de resumo criado|GetSummaryLink|O proprietário do formulário cria links de resumo para compartilhar resultados.|
|Link de resumo excluído|DeleteSummaryLink|O proprietário do formulário exclui o link de resultados de resumo.|
|Formulário de status de phishing atualizado|UpdatePhishingStatus|Esse evento é registrado sempre que o valor detalhado do status de segurança interna é alterado, independentemente de isso ter sido alterado o estado de segurança final (por exemplo, formulário agora é fechado ou aberto). Isso significa que você pode ver os eventos duplicados sem uma alteração de estado de segurança final. Os possíveis valores de status para este evento são:<br/>- Retirar <br/>- Retirado por Administrador <br/>- Administrador Desbloqueado <br/>- Auto Bloqueado <br/>- Auto Desbloqueado <br/>- Relatado pelo Cliente <br/>- Redefinir Relatado pelo Cliente|
|Status de phishing do usuário atualizado|UpdateUserPhishingStatus|Esse evento é registrado sempre que o valor do status de segurança do usuário foi alterado. O valor do status de usuário no registro de auditoria é **Confirmado como Phisher** quando o usuário criou um formulário de phishing que foi obtido pela equipe de segurança do Microsoft Online. Se um administrador desbloquear o usuário, o valor do status do usuário será definido como **Redefinir como usuário normal**.|
|Convite do Forms Pro enviado|ProInvitation|O usuário clica para ativar uma avaliação do Pro.|
|Configuração do formulário atualizado|UpdateFormSetting|O proprietário do formulário atualiza a configuração de um formulário. <br><br>A propriedade FormSettingName:string indica o nome e o novo valor da configuração.|
|Configuração de usuário atualizada|UpdateUserSetting|O proprietário do formulário atualiza a configuração de um usuário. <br><br>A propriedade UserSettingName:string indica o nome e o novo valor da configuração|
|Formulários listados|ListForms|O proprietário do formulário está exibindo uma lista de formulários. <br><br>A propriedade ViewType:string indica qual exibição o proprietário do formulário está olhando: Todos os Formulários, Compartilhado Comigo ou Formulários de Grupo|
|Resposta enviada |SubmitResponse|Um usuário envia uma resposta a um formulário. <br><br>A propriedade IsInternalForm:boolean indica se o respondente é da mesma organização que o proprietário do formulário.|
||||

#### <a name="forms-activities-performed-by-coauthors-and-anonymous-responders"></a>Atividades do Forms realizadas por coautores e respondentes anônimos

Os formulários do oferecem suporte à colaboração quando os formulários são projetados e durante a análise de respostas. Um colaborador de formulário é conhecido como um *coautor*. Os coautores podem fazer tudo o que o proprietário do formulário pode fazer, exceto excluir ou mover um formulário. Os formulários também permitem que você crie um formulário que pode ser respondido anonimamente. Isso significa que o respondedor não precisa estar conectado à sua organização para responder a um formulário.

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
|Rótulo de sensibilidade removido do site|FileSensitivityLabelRemoved|Um rótulo de sensibilidade foi removido de um documento usando o Office na Web, uma política de rotulamento automático ou usando o cmdlet [Unlock-SPOSensitivityLabelEncryptedFile](https://docs.microsoft.com/powershell/module/sharepoint-online/unlock-sposensitivitylabelencryptedFile).|
||||

### <a name="retention-policy-and-retention-label-activities"></a>Política de retenção e atividades do rótulo de retenção

|Nome amigável|Operação|Descrição|
|:-----|:-----|:-----|
| Configurações definidas para uma política de retenção |NewRetentionComplianceRule |O administrador configurou as configurações de retenção para uma nova política de retenção. As configurações de retenção incluem por quanto tempo os itens são mantidos e o que acontece com os itens quando o período de retenção expira (por exemplo, excluir itens, reter itens ou reter e, em seguida, excluí-los). Essa atividade também corresponde à execução do novo cmdlet [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule).|
| Criado o rótulo de retenção |NewComplianceTag |Um novo rótulo de retenção foi criado pelo administrador.|
| Criada a política de retenção  |NewRetentionCompliancePolicy|Uma nova política de retenção foi criada pelo administrador.|
| As configurações de uma política de retenção foram excluídas| RemoveRetentionComplianceRule<br/>| O administrador excluiu as configurações de uma política de retenção. Provavelmente, essa atividade será registrada quando um administrador excluir uma política de retenção ou executará o cmdlet [Remove-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/Remove-RetentionComplianceRule).|
| Rótulo de retenção excluído |RemoveComplianceTag | Um rótulo de retenção foi excluído pelo administrador.|
| Excluída a política de retenção |RemoveRetentionCompliancePolicy<br/> |Uma política de retenção foi excluída pelo administrador. |
| A opção de registro regulatório foi habilitada para etiquetas de retenção<br/> |SetRestrictiveRetentionUI |O administrador executou o cmdlet [Set-RegulatoryComplianceUI](https://docs.microsoft.com/powershell/module/exchange/set-regulatorycomplianceui) para que um administrador possa selecionar a opção de configuração da IU para que um rótulo de retenção marque o conteúdo como um registro regulamentar.|
| Configurações atualizadas para uma política de retenção | SetRetentionComplianceRule | O administrador alterou as configurações de retenção de uma política de retenção existente. As configurações de retenção incluem por quanto tempo os itens são mantidos e o que acontece com os itens quando o período de retenção expira (por exemplo, excluir itens, reter itens ou reter e, em seguida, excluí-los). Essa atividade também corresponde à execução do cmdlet [Set-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule). |
| Rótulo de retenção atualizado |SetComplianceTag  | Um rótulo de retenção existente foi atualizado pelo administrador.|
| Política de retenção atualizada |SetRetentionCompliancePolicy |O administrador atualizou uma política de retenção existente. As atualizações que disparam esse evento incluem adicionar ou excluir locais de conteúdo ao qual a política de retenção foi aplicada.|

### <a name="exchange-admin-audit-log"></a>Log de auditoria de administradores do Exchange

O log de auditoria de administradores do Exchange (que está habilitado por padrão no Office 365) registra um evento no log de auditoria quando um administrador (ou um usuário que recebeu permissões administrativas) faz uma alteração na sua organização do Exchange Online. As alterações feitas usando o centro de administração do Exchange ou executando um cmdlet no PowerShell do Exchange Online são registradas no log de auditoria de administradores do Exchange. Os cmdlets que começam com os verbos **Get-**, **Search-**, ou **Test-** não são registrados no log de auditoria. Para obter informações mais detalhadas sobre o log de auditoria de administradores no Exchange, confira [Log de auditoria de administradores](https://go.microsoft.com/fwlink/p/?LinkID=619225).

> [!IMPORTANT]
> Alguns cmdlets do Exchange Online que não estão registrados no log de auditoria de administradores do Exchange (ou no log de auditoria do). Muitos desses cmdlets estão relacionados à manutenção do serviço do Exchange Online e são executados pela equipe do Data Center da Microsoft ou por contas de serviços. Esses cmdlets não são registrados porque resultaram em um grande número de eventos de auditoria "ruidosa". Se houver um cmdlet do Exchange Online que não está sendo auditado, envie uma sugestão para o [Fórum de voz usuário de Conformidade e Segurança](https://office365.uservoice.com/forums/289138-office-365-security-compliance) e solicite que ele seja habilitado para a auditoria. Você também pode enviar uma solicitação de alteração de design (DCR) para o suporte da Microsoft.

Aqui estão algumas dicas para pesquisar atividades de administração do Exchange ao pesquisar o log de auditoria:

- Para retornar entradas do log de auditoria de administradores do Exchange, você precisa selecionar **Mostrar resultados para todas as atividades** na lista **Atividades**. Use as caixas de intervalo de datas e as **Usuários** para restringir os resultados da pesquisa para cmdlets executados por um administrador específico do Exchange dentro de um intervalo de datas específico.

- Para exibir eventos do log de auditoria de administradores do Exchange, filtre os resultados da pesquisa e digite um **-** (traço) na caixa de **Atividade** de filtro. Esse exibe nomes de cmdlets, que são exibidos na coluna **Atividade** de eventos de administração do Exchange. Em seguida, você pode classificar os nomes de cmdlets em ordem alfabética.

  ![Digite um traço na caixa Atividades para filtrar os eventos de administração do Exchange](../media/7628e7aa-6263-474a-a28b-2dcf5694bb27.png)

- Para obter informações sobre qual cmdlet foi executado, quais parâmetros e valores de parâmetros foram usados e quais objetos foram afetados, você pode exportar os resultados da pesquisa selecionando a opção **Baixar todos os resultados**. Para saber mais, confira [Exportar, configurar e exibir registros de log de auditoria](export-view-audit-log-records.md).

- Você também pode usar o comando `Search-UnifiedAuditLog -RecordType ExchangeAdmin` no PowerShell do Exchange Online para retornar somente registros de auditoria do log de auditoria de administradores do Exchange. Pode levar até 30 minutos após um cmdlet do Exchange ser executado para que a entrada do log de auditoria correspondente seja retornada nos resultados da pesquisa. Para obter mais informações, confira [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog). Para obter informações sobre como exportar os resultados da pesquisa retornados pelo cmdlet **Search-UnifiedAuditLog** para um arquivo CSV, confira a seção "dicas para exportar e exibir o log de auditoria" em [Exportar, configurar e exibir os registros de log de auditoria](export-view-audit-log-records.md#tips-for-exporting-and-viewing-the-audit-log).

- Você também pode exibir os eventos no log de auditoria de administradores do Exchange usando o centro de administração do Exchange ou executando o **Search-AdminAuditLog** no Windows PowerShell do Exchange Online. Esta é uma boa maneira de procurar especificamente atividades executadas por administradores do Exchange Online. Para obter instruções, confira:

  - [Exibir o log de auditoria do administrador](https://technet.microsoft.com/library/dn342832%28v=exchg.150%29.aspx)

  - [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog)

   Lembre-se de que as mesmas atividades do administrador do Exchange estão registradas no log de auditoria do administrador do Exchange e no log de auditoria.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

**Quais são os diferentes serviços do Microsoft 365 que atualmente são auditados?**

Os serviços mais usados, como o Exchange Online, o SharePoint Online, o OneDrive for Business e o Azure Active Directory, o Microsoft Teams, o Dynamics 365, o defender para Office 365 e o Power BI, têm auditoria. Confira o [começo deste artigo](search-the-audit-log-in-security-and-compliance.md) para obter uma lista de serviços que são auditados.

**Quais atividades são auditadas por serviço de auditoria no Office 365?**

Consulte a seção [Atividades auditadas](#audited-activities) neste artigo para obter uma lista e uma descrição das atividades que são auditadas.

**Quanto tempo leva para um registro de auditoria estar disponível após um evento ter ocorrido?**

A maioria dos dados de auditoria está disponível em 30 minutos, mas pode levar até 24 horas após a ocorrência de um evento para que a entrada do log de auditoria correspondente seja exibida nos resultados da pesquisa. Confira a tabela na seção [Requisitos para pesquisar o log de auditoria](#requirements-to-search-the-audit-log) deste artigo que mostra o tempo necessário para os eventos em diferentes serviços disponíveis.

**Por quanto tempo os registros de auditoria são mantidos?**

Como explicado anteriormente, os registros de auditoria para atividades executadas por usuários que receberam uma licença do Office 365 E5 ou Microsoft E5 (ou usuários com uma licença complementar da Microsoft 365 E5) são mantidos por um ano. Para todas as outras assinaturas que oferecem suporte a registro de auditoria unificado, os registros de auditoria são mantidos por 90 dias.

**Posso acessar os dados de auditoria de forma programática?**

Sim. A API da Atividade de Gestão do Office 365 é usada para buscar os logs de auditoria por programação.  Para começar, confira [Comece a usar as APIs de gerenciamento do Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).

**Existem outras maneiras de obter logs de auditoria além de usar o centro de segurança e conformidade ou a API da Atividade de Gestão do Office 365?**

Não. Estas são as duas únicas maneiras de obter dados do serviço de auditoria.

**Preciso habilitar individualmente a auditoria em cada serviço para o qual quero capturar os logs de auditoria?**

Na maioria dos serviços, a auditoria é habilitada por padrão depois que você ativa a auditoria pela sua organização, (conforme descrito na seção [Requisitos para pesquisar o log de auditoria](#requirements-to-search-the-audit-log) neste artigo).

**O serviço de auditoria oferece suporte para a duplicação de registros?**

Não. O pipeline do serviço de auditoria está quase em tempo real e, portanto, não é compatível com a duplicação.

**O dados de auditoria fluem entre regiões geográficas?**

Não. Atualmente, temos implantações de pipeline de auditoria nas regiões na América do Norte, EMEA (Europa, Oriente Médio e África) e No entanto, podemos transmitir os dados entre essas regiões para balancear a carga e apenas durante problemas no local. Quando fazemos essas atividades, os dados são criptografados.

**Os dados de auditoria são criptografados?**

Os dados de auditoria são armazenados nas caixas de correio do Exchange (dados em repouso) na mesma região em que o pipeline de auditoria unificado é implantado. Os dados de caixa de correio no REST não são criptografados pelo Exchange. No entanto, a criptografia no nível de serviço criptografa todos os dados da caixa de correio, pois os servidores do Exchange no Microsoft datacenters são criptografados via BitLocker. Para saber mais, confira [Criptografia do Office 365 para Skype for Business, OneDrive for Business, SharePoint Online e Exchange Online](office-365-encryption-for-skype-onedrive-sharepoint-and-exchange.md).

Os dados de Email do Outlook em trânsito sempre são criptografados.
