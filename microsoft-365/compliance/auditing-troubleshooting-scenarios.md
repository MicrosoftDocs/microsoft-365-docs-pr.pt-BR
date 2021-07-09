---
title: Pesquisar o log de auditoria para solucionar problemas de cenários comuns
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.custom:
- seo-marvel-apr2020
description: Saiba como usar a ferramenta de pesquisa Microsoft 365 log de auditoria para ajudar a solucionar problemas comuns de suporte para contas de email.
ms.openlocfilehash: 22d511fa2ad538c4ec9729fb051caefad6c3e974
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341040"
---
# <a name="search-the-audit-log-to-investigate-common-support-issues"></a>Pesquise o log de auditoria para investigar problemas comuns de suporte

Este artigo descreve como usar a ferramenta de pesquisa de log de auditoria para ajudá-lo a investigar problemas comuns de suporte. Isso inclui o uso do log de auditoria para:

- Encontre o endereço IP do computador usado para acessar uma conta comprometida
- Determinar quem configura o encaminhamento de email para uma caixa de correio
- Determinar se um usuário excluiu itens de email em sua caixa de correio
- Determinar se um usuário criou uma regra de caixa de entrada
- Investigar por que houve um logon bem-sucedido por um usuário fora da sua organização
- Pesquisar atividades de caixa de correio executadas por usuários com licenças que não são do E5
- Pesquisar atividades de caixa de correio executadas por usuários delegados

## <a name="using-the-audit-log-search-tool"></a>Usando a ferramenta de pesquisa de log de auditoria

Cada um dos cenários de solução de problemas descritos neste artigo baseia-se no uso da ferramenta de pesquisa de log de auditoria no Centro de Conformidade & Segurança. Esta seção lista as permissões necessárias para pesquisar o log de auditoria e descreve as etapas para acessar e executar pesquisas de log de auditoria. Cada seção de cenário explica como configurar uma consulta de pesquisa de log de auditoria e o que procurar nas informações detalhadas nos registros de auditoria que corresponderem aos critérios de pesquisa.

### <a name="permissions-required-to-use-the-audit-log-search-tool"></a>Permissões necessárias para usar a ferramenta de pesquisa de log de auditoria

Você deve ter a função View-Only Logs de Auditoria ou Logs de Auditoria Exchange Online pesquisar o log de auditoria. Por padrão, essas funções são atribuídas aos grupos de funções Gerenciamento de Conformidade e Gerenciamento de Organização na página **Permissões** do centro de administração do Exchange. Os administradores globais no Office 365 e Microsoft 365 são adicionados automaticamente como membros do grupo de funções Gerenciamento da Organização no Exchange Online. Para saber mais, confira [Gerenciar Grupos de Funções do Exchange Online](/Exchange/permissions-exo/role-groups).

### <a name="running-audit-log-searches"></a>Executando pesquisas de log de auditoria

Esta seção descreve as noções básicas para criar e executar pesquisas de log de auditoria. Use essas instruções como ponto de partida para cada cenário de solução de problemas neste artigo. Para obter instruções passo a passo mais detalhadas, consulte [Pesquisar o log de auditoria](search-the-audit-log-in-security-and-compliance.md#step-1-run-an-audit-log-search).

1. Vá até <https://compliance.microsoft.com/auditlogsearch> e entre usando uma conta corporativa ou de estudante.
    
    A página **Auditoria** é exibida. 
    
    ![Configure criteria e selecione Pesquisar para executar a pesquisa](../media/AuditLogSearchPage1.png)
  
4. Você pode configurar os critérios de pesquisa a seguir. Cada cenário de solução de problemas neste artigo recomenda orientações específicas para configurar esses campos.
    
   a. **Data de** início **e data de término:** selecione uma data e um intervalo de tempo para exibir os eventos que ocorreram nesse período. Os últimos sete dias são selecionados por padrão. A data e a hora são apresentadas no formato UTC (Tempo Universal Coordenado). O intervalo de datas máximo que você pode especificar é de 90 dias.    

   b. **Atividades:** Selecione a lista lista listada para exibir as atividades que você pode pesquisar. Depois de executar a pesquisa, somente os registros de Auditoria das atividades selecionadas serão exibidos. Selecionar **Mostrar resultados para todas as atividades** exibe resultados para todas as atividades que atendem aos outros critérios de pesquisa. Você também terá que deixar esse campo em branco em alguns dos cenários de solução de problemas.
    
    c. **Usuários:** Clique nesta caixa e selecione um ou mais usuários para exibir os resultados da pesquisa. Os registros de auditoria para a atividade selecionada realizada pelos usuários selecionados nesta caixa são exibidos na lista de resultados. Deixe essa caixa em branco para retornar entradas para todos os usuários (e contas de serviço) na sua organização.
    
    d. **Arquivo, pasta ou site:** Digite alguns ou todos os nomes de arquivo ou pasta para pesquisar atividades relacionadas ao arquivo de pasta que contém a palavra-chave especificada. Você também pode especificar uma URL de um arquivo ou pasta. Se você usar uma URL, certifique-se de digitar o caminho de URL completo ou se você digitar apenas uma parte da URL, não inclua caracteres ou espaços especiais. Deixe essa caixa em branco para retornar entradas para todos os arquivos e pastas em sua organização. Este campo é deixado em branco em todos os cenários de solução de problemas neste artigo.
    
5. Selecione **Pesquisar** para executar a pesquisa usando seus critérios de pesquisa. 
    
    Os resultados da pesquisa são carregados e, após alguns instantes, eles são exibidos em **Resultados** na página de pesquisa **de log de** auditoria. Cada uma das seções deste artigo fornece orientações sobre o que procurar no contexto do cenário de solução de problemas específico.

    Para obter mais informações sobre como exibir, filtrar ou exportar resultados de pesquisa de log de auditoria, consulte:

    - [Exibir resultados da pesquisa](search-the-audit-log-in-security-and-compliance.md#step-2-view-the-search-results)
    - [Filtrar resultados da pesquisa](search-the-audit-log-in-security-and-compliance.md#step-3-filter-the-search-results)
    - [Exportar resultados de pesquisa](search-the-audit-log-in-security-and-compliance.md#step-4-export-the-search-results-to-a-file)

## <a name="find-the-ip-address-of-the-computer-used-to-access-a-compromised-account"></a>Encontre o endereço IP do computador usado para acessar uma conta comprometida

O endereço IP correspondente a uma atividade executada por qualquer usuário está incluído na maioria dos registros de auditoria. As informações sobre o cliente usado também estão incluídas no registro de auditoria.

Veja como configurar uma consulta de pesquisa de log de auditoria para este cenário:

**Atividades:** Se for relevante para seu caso, selecione uma atividade específica a ser pesquisada. Para solucionar problemas de contas comprometidas, considere selecionar a atividade de usuário **que se inscreveu** na caixa de correio em Exchange **de caixa de correio.** Isso retorna registros de auditoria mostrando o endereço IP que foi usado ao entrar na caixa de correio. Caso contrário, deixe esse campo em branco para retornar registros de auditoria para todas as atividades. 

> [!TIP]
> Deixar esse campo em branco retornará atividades **UserLoggedIn,** que é uma atividade Azure Active Directory que indica que alguém entrou em uma conta de usuário. Use a filtragem nos resultados da pesquisa para exibir os registros **de auditoria UserLoggedIn.**

**Data de** início **e data de término:** selecione um intervalo de datas aplicável à investigação.

**Usuários:** Se você estiver investigando uma conta comprometida, selecione o usuário cuja conta foi comprometida. Isso retorna registros de auditoria para atividades executadas por essa conta de usuário.

**Arquivo, pasta ou site:** Deixe esse campo em branco.

Depois de executar a pesquisa, o endereço IP de cada atividade é exibido na coluna endereço **IP** nos resultados da pesquisa. Selecione o registro nos resultados da pesquisa para exibir informações mais detalhadas na página de sobremenu.

## <a name="determine-who-set-up-email-forwarding-for-a-mailbox"></a>Determinar quem configura o encaminhamento de email para uma caixa de correio

Quando o encaminhamento de email é configurado para uma caixa de correio, as mensagens de email enviadas para a caixa de correio são encaminhadas para outra caixa de correio. As mensagens podem ser encaminhadas para usuários dentro ou fora da sua organização. Quando o encaminhamento de email é definido em uma caixa de correio, o cmdlet Exchange Online subjacente usado é **Set-Mailbox**.

Veja como configurar uma consulta de pesquisa de log de auditoria para este cenário:

**Atividades:** Deixe esse campo em branco para que a pesquisa retorne registros de auditoria para todas as atividades. Isso é necessário para retornar quaisquer registros de auditoria relacionados ao cmdlet **Set-Mailbox.**

**Data de** início **e data de término:** selecione um intervalo de datas aplicável à investigação.

**Usuários:** A menos que você esteja investigando um problema de encaminhamento de email para um usuário específico, deixe este campo em branco. Isso ajuda a identificar se o encaminhamento de email foi definido para qualquer usuário.

**Arquivo, pasta ou site:** Deixe esse campo em branco.

Depois de executar a pesquisa, selecione **Filtrar resultados** na página de resultados da pesquisa. Na caixa em **Header da** coluna Atividade, digite **Set-Mailbox** para que apenas os registros de auditoria relacionados ao cmdlet **Set-Mailbox** sejam exibidos.

![Filtrando os resultados de uma pesquisa de log de auditoria](../media/emailforwarding1.png)

Neste ponto, você precisa olhar para os detalhes de cada registro de auditoria para determinar se a atividade está relacionada ao encaminhamento de email. Selecione o registro de auditoria para exibir a página **detalhes** do sobressalto e selecione **Mais informações**. As descrições e capturas de tela a seguir realçam as informações que indicam que o encaminhamento de email foi definido na caixa de correio.

![Informações detalhadas do registro de auditoria](../media/emailforwarding2.png)

a. No campo **ObjectId,** o alias da caixa de correio em que o encaminhamento de email foi definido é exibido. Essa caixa de correio também é exibida na coluna **Item** na página de resultados da pesquisa.

b. No campo **Parâmetros,** O valor *ForwardingSmtpAddress* indica que o encaminhamento de email foi definido na caixa de correio. Neste exemplo, o email está sendo encaminhado para o endereço de email mike@contoso.com, que está fora da alpinehouse.onmicrosoft.com organização.

c. O valor *True* para o parâmetro *DeliverToMailboxAndForward* indica que uma cópia  da mensagem é entregue ao sarad@alpinehouse.onmicrosoft.com e é encaminhada para o endereço de email especificado pelo parâmetro *ForwardingSmtpAddress,* que neste exemplo é mike@contoso.com. Se o valor do parâmetro *DeliverToMailboxAndForward* for definido como *False*, o email será encaminhado apenas para o endereço especificado pelo parâmetro *ForwardingSmtpAddress.* Ele não é entregue à caixa de correio especificada no **campo ObjectId.**

d. O **campo UserId** indica o usuário que definiu o encaminhamento de email na caixa de correio especificada no **campo ObjectId.** Esse usuário também é exibido na coluna **Usuário** na página de resultados da pesquisa. Nesse caso, parece que o proprietário da caixa de correio definiu o encaminhamento de email em sua caixa de correio.

Se você determinar que o encaminhamento de email não deve ser definido na caixa de correio, poderá removê-lo executando o seguinte comando no Exchange Online PowerShell:

```powershell
Set-Mailbox <mailbox alias> -ForwardingSmtpAddress $null 
```

Para obter mais informações sobre os parâmetros relacionados ao encaminhamento de email, consulte o [artigo Set-Mailbox.](/powershell/module/exchange/set-mailbox)

## <a name="determine-if-a-user-deleted-email-items"></a>Determinar se um usuário excluiu itens de email

A partir de janeiro de 2019, a Microsoft está aprindo o log de auditoria de caixa de correio por padrão para todas as Office 365 e organizações da Microsoft. Isso significa que determinadas ações executadas pelos proprietários de caixa de correio são registradas automaticamente e os registros de auditoria de caixa de correio correspondentes estão disponíveis quando você procura por eles no log de auditoria de caixa de correio. Antes de a auditoria de caixa de correio ser ativada por padrão, você precisava habilita-la manualmente para cada caixa de correio de usuário em sua organização. 

As ações de caixa de correio registradas por padrão incluem as ações de caixa de correio SoftDelete e HardDelete executadas pelos proprietários da caixa de correio. Isso significa que você pode usar as etapas a seguir para pesquisar no log de auditoria eventos relacionados a itens de email excluídos. Para obter mais informações sobre a auditoria de caixa de correio por padrão, consulte [Manage mailbox auditing](enable-mailbox-auditing.md).

Veja como configurar uma consulta de pesquisa de log de auditoria para este cenário:

**Atividades:** Em **Exchange de caixa de correio,** selecione uma ou ambas as seguintes atividades:

- **Mensagens excluídas da pasta Itens Excluídos:** Essa atividade corresponde à ação de auditoria **de caixa de correio SoftDelete.** Essa atividade também é registrada quando um usuário exclui permanentemente um item selecionando-o e pressionando **Shift+Delete.** Depois que um item for excluído permanentemente, o usuário poderá recuperá-lo até que o período de retenção de item excluído expire.

- **Mensagens limpas da caixa de correio:** Essa atividade corresponde à ação de auditoria de caixa de correio **HardDelete.** Isso é registrado quando um usuário limpa um item da pasta Itens Recuperáveis. Os administradores podem usar a ferramenta pesquisa de conteúdo no centro de segurança e conformidade para pesquisar e recuperar itens limpos até que o período de retenção de item excluído expire ou mais se a caixa de correio do usuário estiver em espera.

**Data de** início **e data de término:** selecione um intervalo de datas aplicável à investigação.

**Usuários:** Se você selecionar um usuário nesse campo, a ferramenta de pesquisa de log de auditoria retornará registros de auditoria para itens de email excluídos (SoftDeleted ou HardDeleted) pelo usuário especificado. Às vezes, o usuário que exclui um email pode não ser o proprietário da caixa de correio.

**Arquivo, pasta ou site:** Deixe esse campo em branco.

Depois de executar a pesquisa, você pode filtrar os resultados da pesquisa para exibir os registros de auditoria para itens excluídos de forma suave ou para itens excluídos com dificuldade. Selecione o registro de auditoria para exibir a página **detalhes** do sobressalto e selecione **Mais informações**. Informações adicionais sobre o item excluído, como a linha de assunto e o local do item quando ele foi excluído, são exibidas no campo **AffectedItems.** As capturas de tela a seguir mostram um exemplo do campo **AffectedItems** de um item excluído de forma suave e um item excluído com dificuldade.

**Exemplo do campo AffectedItems para item excluído de forma suave**

![Registro de auditoria para item excluído de forma suave](../media/softdeleteditem.png)

**Exemplo do campo AffectedItems para item excluído com dificuldade**

![Registro de auditoria para item de email excluído com exclusão](../media/harddeleteditem.png)

### <a name="recover-deleted-email-items"></a>Recuperar itens de email excluídos

Os usuários podem recuperar itens excluídos de forma suave se o período de retenção de itens excluídos não tiver expirado. No Exchange Online, o período de retenção de itens excluídos padrão é de 14 dias, mas os administradores podem aumentar essa configuração para um máximo de 30 dias. Aponte os usuários para [o artigo Recuperar itens excluídos](https://support.office.com/article/Recover-deleted-items-or-email-in-Outlook-Web-App-C3D8FC15-EEEF-4F1C-81DF-E27964B7EDD4) ou emails Outlook na Web instruções sobre como recuperar itens excluídos.

Conforme explicado anteriormente, os administradores poderão recuperar itens excluídos com dificuldade se o período de retenção do item excluído não tiver expirado ou se a caixa de correio estiver em espera, nesse caso, os itens serão mantidos até que a duração da retenção expire. Quando você executar uma pesquisa de conteúdo, os itens excluídos e excluídos de forma fácil na pasta Itens Recuperáveis são retornados nos resultados da pesquisa se eles corresponderem à consulta de pesquisa. Para obter mais informações sobre como executar pesquisas de conteúdo, consulte [Pesquisa de conteúdo em Office 365](content-search.md).

> [!TIP]
> Para pesquisar itens de email excluídos, pesquise por todo ou parte da linha de assunto exibida no campo **AffectedItems** no registro de auditoria.

## <a name="determine-if-a-user-created-an-inbox-rule"></a>Determinar se um usuário criou uma regra de caixa de entrada

Quando os usuários criam uma regra de caixa de entrada para Exchange Online caixa de correio, um registro de auditoria correspondente é salvo no log de auditoria. Para obter mais informações sobre regras de caixa de entrada, consulte:

- [Usar regras de caixa de entrada Outlook na Web](https://support.office.com/article/use-inbox-rules-in-outlook-on-the-web-8400435c-f14e-4272-9004-1548bb1848f2)
- [Gerenciar mensagens de email Outlook usando regras](https://support.office.com/article/Manage-email-messages-by-using-rules-C24F5DEA-9465-4DF4-AD17-A50704D66C59)

Veja como configurar uma consulta de pesquisa de log de auditoria para este cenário:

**Atividades:** Em **Exchange de caixa de** correio, selecione **New-InboxRule Create/modify/enable/disable inbox rule**.

**Data de** início **e data de término:** selecione um intervalo de datas aplicável à investigação.

**Usuários:** A menos que você esteja investigando um usuário específico, deixe este campo em branco. Isso ajuda a identificar novas regras de caixa de entrada configuradas por qualquer usuário.

**Arquivo, pasta ou site:** Deixe esse campo em branco.

Depois de executar a pesquisa, todos os registros de auditoria para essa atividade são exibidos nos resultados da pesquisa. Selecione um registro de auditoria para exibir a página **detalhes** do sobressalto e selecione **Mais informações**. As informações sobre as configurações de regra de caixa de entrada são exibidas no **campo Parâmetros.** As descrições e capturas de tela a seguir realçam as informações sobre regras de caixa de entrada.

![Registro de auditoria para nova regra de caixa de entrada](../media/NewInboxRuleRecord.png)

a. No campo **ObjectId,** o nome completo da regra de caixa de entrada é exibido. Esse nome inclui o alias da caixa de correio do usuário (por exemplo, SaraD) e o nome da regra de caixa de entrada (por exemplo, "Mover mensagens do administrador").

b. No campo **Parâmetros,** a condição da regra de caixa de entrada é exibida. Neste exemplo, a condição é especificada pelo *parâmetro From.* O valor definido para o *parâmetro From* indica que a regra de caixa de entrada age em emails enviados por admin@alpinehouse.onmicrosoft.com. Para uma lista completa dos parâmetros que podem ser usados para definir condições de regras de caixa de entrada, consulte o [artigo New-InboxRule.](/powershell/module/exchange/new-inboxrule)

c. O *parâmetro MoveToFolder* especifica a ação da regra de caixa de entrada. Neste exemplo, as mensagens recebidas admin@alpinehouse.onmicrosoft.com são movidas para a pasta denominada *AdminSearch*. Consulte também o [artigo New-InboxRule](/powershell/module/exchange/new-inboxrule) para uma lista completa de parâmetros que podem ser usados para definir a ação de uma regra de caixa de entrada.

d. O **campo UserId** indica o usuário que criou a regra de caixa de entrada especificada no **campo ObjectId.** Esse usuário também é exibido na coluna **Usuário** na página de resultados da pesquisa.

## <a name="investigate-why-there-was-a-successful-login-by-a-user-outside-your-organization"></a>Investigar por que houve um logon bem-sucedido por um usuário fora da sua organização

Ao revisar os registros de auditoria no log de auditoria, você pode ver registros que indicam que um usuário externo foi autenticado pelo Azure Active Directory e conectado com êxito à sua organização. Por exemplo, um administrador no contoso.onmicrosoft.com pode ver um registro de auditoria mostrando que um usuário de uma organização diferente (por exemplo, fabrikam.onmicrosoft.com) fez logor com êxito no contoso.onmicrosoft.com. Da mesma forma, você pode ver registros de auditoria que indicam usuários com uma conta da Microsoft (MSA), como um Outlook.com ou Live.com, conectados com êxito à sua organização. Nessas situações, a atividade auditada é **Usuário conectado**. 

Este é o comportamento padrão. Azure Active Directory (Azure AD), o serviço de diretório,  permite algo chamado autenticação de passagem quando um usuário externo tenta acessar um site SharePoint ou um local OneDrive em sua organização. Quando o usuário externo tenta fazer isso, ele é solicitado a inserir suas credenciais. O Azure AD usa as credenciais para autenticar o usuário, ou seja, somente o Azure AD verifica se o usuário é quem diz ser. A indicação do logon bem-sucedido no registro de auditoria é o resultado da autenticação do usuário pelo Azure AD. O logon bem-sucedido não significa que o usuário foi capaz de acessar qualquer recurso ou executar qualquer outra ação em sua organização. Ele só indica que o usuário foi autenticado pelo Azure AD. Para que um usuário de passagem acesse recursos SharePoint ou OneDrive, um usuário em sua organização teria que compartilhar explicitamente um recurso com o usuário externo enviando um convite de compartilhamento ou um link de compartilhamento anônimo. 

> [!NOTE]
> O Azure AD permite a autenticação de passagem somente para aplicativos de primeira, como SharePoint Online e OneDrive for Business. Não é permitido para outros aplicativos de terceiros.

Veja um exemplo e descrições de propriedades relevantes em um registro de auditoria para um evento User **logged In** que é resultado da autenticação de passagem. Selecione o registro de auditoria para exibir a página **detalhes** do sobressalto e selecione **Mais informações**.

![Exemplo de registro de auditoria para autenticação de passagem bem-sucedida](../media/PassThroughAuth1.png)

   a. Este campo indica que o usuário que tentou acessar um recurso em sua organização não foi encontrado no Azure AD da sua organização.

   b. Este campo exibe o UPN do usuário externo que tentou acessar um recurso em sua organização. Essa ID de usuário também é identificada nas **propriedades User** e **UserId** no registro de auditoria.

   c. A **propriedade ApplicationId** identifica o aplicativo que disparou a solicitação de logon. O valor de 000000003-0000-0ff1-ce00-000000000000 exibido na propriedade ApplicationId neste registro de auditoria indica SharePoint Online. OneDrive for Business também tem esse mesmo ApplicationId.

   d. Isso indica que a autenticação de passagem foi bem-sucedida. Em outras palavras, o usuário foi autenticado com êxito pelo Azure AD. 

   e. O **valor RecordType** de **15** indica que a atividade auditada (UserLoggedIn) é um evento de logon do Serviço de Token Seguro (STS) no Azure AD.

Para obter mais informações sobre as outras propriedades exibidas em um registro de auditoria UserLoggedIn, consulte as informações de esquema relacionadas ao Azure AD no esquema da API de Atividade de Gerenciamento [do Office 365](/office/office-365-management-api/office-365-management-activity-api-schema#azure-active-directory-base-schema).

Aqui estão dois exemplos de cenários que resultariam em uma atividade de auditoria bem-sucedida do Usuário **conectado** devido à autenticação de passagem: 

  - Um usuário com uma conta da Microsoft (como SaraD@outlook.com) tentou acessar um documento em uma conta OneDrive for Business no fourthcoffee.onmicrosoft.com e não há uma conta de usuário convidado correspondente para SaraD@outlook.com no fourthcoffee.onmicrosoft.com.

  - Um usuário com uma conta Work ou School em uma organização (como pilarp@fabrikam.onmicrosoft.com) tentou acessar um site do SharePoint no contoso.onmicrosoft.com e não há uma conta de usuário convidado correspondente para pilarp@fabrikam.com em contoso.onmicrosoft.com.

### <a name="tips-for-investigating-successful-logins-resulting-from-pass-through-authentication"></a>Dicas para investigar logons bem-sucedidos resultantes da autenticação de passagem

- Pesquise no log de auditoria as atividades realizadas pelo usuário externo identificado no registro de **auditoria do** Usuário conectado. Digite o UPN para o usuário externo na caixa **Usuários** e use um intervalo de datas, se relevante para seu cenário. Por exemplo, você pode criar uma pesquisa usando os seguintes critérios de pesquisa:

   ![Pesquisar todas as atividades realizadas pelo usuário externo](../media/PassThroughAuth2.png)

    Além das  atividades do Usuário conectado, outros registros de auditoria podem ser retornados, como aqueles que indicam que um usuário em sua organização compartilhou recursos com o usuário externo e se o usuário externo acessou, modificou ou baixou um documento que foi compartilhado com ele.

- Pesquise SharePoint atividades de compartilhamento que indiquem que um arquivo foi compartilhado com o usuário externo identificado por um **usuário conectado ao** registro de auditoria. Para saber mais, veja [Usar a auditoria de compartilhamento no log de auditoria](use-sharing-auditing.md).

- Exporte os resultados da pesquisa de log de auditoria que contenham registros relevantes para sua investigação para que você possa usar o Excel para pesquisar outras atividades relacionadas ao usuário externo. Para obter mais informações, [consulte Exportar, configurar e exibir registros de log de auditoria.](export-view-audit-log-records.md)

## <a name="search-for-mailbox-activities-performed-by-users-with-non-e5-licenses"></a>Pesquisar atividades de caixa de correio executadas por usuários com licenças que não são do E5

Mesmo [](enable-mailbox-auditing.md) quando a auditoria de caixa de correio por padrão está íntequeada para sua organização, você pode notar que os eventos de auditoria de caixa de correio para alguns usuários não são encontrados em pesquisas de log de auditoria usando o centro de conformidade, o cmdlet **Search-UnifiedAuditLog** ou a API de Atividade de Gerenciamento Office 365. O motivo disso é que os eventos de auditoria de caixa de correio serão retornados somente para usuários com licenças E5 quando você um dos métodos anteriores pesquisar o log de auditoria unificado.

Para recuperar registros de log de auditoria de caixa de correio para usuários que não são do E5, você pode executar uma das seguintes soluções alternativas:

- Habilitar manualmente a auditoria de caixa de correio em caixas de correio individuais (execute o `Set-Mailbox -Identity <MailboxIdentity> -AuditEnabled $true` comando no Exchange Online PowerShell). Depois de fazer isso, pesquise as atividades de auditoria de caixa de correio usando o centro de conformidade, o cmdlet **Search-UnifiedAuditLog** ou a API Office 365 Management Activity.
  
  > [!NOTE]
  > Se a auditoria de caixa de correio já estiver habilitada na caixa de correio, mas suas pesquisas não retornarem resultados, altere o valor do parâmetro _AuditEnabled_ para e volte `$false` para `$true` .
  
- Use os seguintes cmdlets no Exchange Online PowerShell:

  - [Search-MailboxAuditLog](/powershell/module/exchange/search-mailboxauditlog) para pesquisar o log de auditoria de caixa de correio para usuários específicos.

  - [New-MailboxAuditLogSearch](/powershell/module/exchange/new-mailboxauditlogsearch) para pesquisar o log de auditoria de caixa de correio para usuários específicos e para ter os resultados enviados por email para destinatários especificados.

## <a name="search-for-mailbox-activities-performed-in-a-specific-mailbox-including-shared-mailboxes"></a>Pesquisar atividades de caixa de correio executadas em uma caixa de correio específica (incluindo caixas de correio compartilhadas)

Quando você  usa a lista suspenso Usuários na ferramenta de pesquisa de log de auditoria no centro de conformidade ou no comando **Search-UnifiedAuditLog -UserIds** no Exchange Online PowerShell, você pode pesquisar atividades executadas por um usuário específico. Para atividades de auditoria de caixa de correio, esse tipo de pesquisa procurará atividades executadas pelo usuário especificado. Ele não garante que todas as atividades realizadas na mesma caixa de correio sejam retornadas nos resultados da pesquisa. Por exemplo, uma pesquisa de log de auditoria não retornará registros de auditoria para atividades executadas por um usuário delegado porque pesquisar atividades de caixa de correio executadas por um usuário específico não retornará atividades executadas por um usuário delegado que tenha sido atribuída permissões para acessar a caixa de correio de outro usuário. (Um usuário representante é alguém que foi atribuído a permissão de caixa de correio SendAs, SendOnBehalf ou FullAccess para a caixa de correio de outro usuário.)

Além disso, o uso da lista **suspenso** Usuário na ferramenta de pesquisa de log de auditoria ou o **Search-UnifiedAuditLog -UserIds** não retornará os resultados das atividades realizadas em uma caixa de correio compartilhada.

Para pesquisar as atividades realizadas em uma caixa de correio específica ou para pesquisar atividades executadas em uma caixa de correio compartilhada, use a seguinte sintaxe ao executar o cmdlet **Search-UnifiedAuditLog:**

```powershell
Search-UnifiedAuditLog  -StartDate <date> -EndDate <date> -FreeText (Get-Mailbox <mailbox identity).ExchangeGuid
```

Por exemplo, o comando a seguir retorna registros de auditoria para atividades realizadas na caixa de correio compartilhada da Equipe de Conformidade da Contoso entre agosto de 2020 e outubro de 2020:

```powershell
Search-UnifiedAuditLog  -StartDate 08/01/2020 -EndDate 10/31/2020 -FreeText (Get-Mailbox complianceteam@contoso.onmicrosoft.com).ExchangeGuid
```

Como alternativa, você pode usar o cmdlet **Search-MailboxAuditLog** para pesquisar registros de auditoria para atividades executadas em uma caixa de correio específica. Isso inclui a pesquisa de atividades executadas em uma caixa de correio compartilhada.

O exemplo a seguir retorna registros de log de auditoria de caixa de correio para atividades realizadas na caixa de correio compartilhada da Equipe de Conformidade da Contoso:

```powershell
Search-MailboxAuditLog -Identity complianceteam@contoso.onmicrosoft.com -StartDate 08/01/2020 -EndDate 10/31/2020 -ShowDetails
```

O exemplo a seguir retorna registros de log de auditoria de caixa de correio para atividades realizadas na caixa de correio especificada por usuários representantes:

```powershell
Search-MailboxAuditLog -Identity <mailbox identity> -StartDate <date> -EndDate <date> -LogonTypes Delegate -ShowDetails
```

Você também pode usar o cmdlet **New-MailboxAuditLogSearch** para pesquisar no log de auditoria uma caixa de correio específica e enviar os resultados por email para destinatários especificados.