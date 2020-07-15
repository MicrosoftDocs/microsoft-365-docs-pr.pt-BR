---
title: Baixa das ferramentas de Descoberta Eletrônica herdadas
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: A descoberta eletrônica in-loco e o bloqueio in-loco (e os cmdlets do PowerShell correspondentes) no Exchange Online serão removidos no primeiro semestre de 2020. O cmdlet Search-Mailbox e o eDiscovery avançado v 1.0 também estão sendo desativados no mesmo período de tempo.
ms.openlocfilehash: 12de88fe3c9de7806b12bd610e0dbeeb404524ca
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126938"
---
# <a name="retirement-of-legacy-ediscovery-tools"></a>Baixa das ferramentas de Descoberta Eletrônica herdadas

> [!IMPORTANT]
> A Microsoft está avaliando a situação de integridade pública e entendemos o impacto que isso ocorre em nossos clientes. Queremos ser fortes parceiros e cidadãos globais responsáveis. Para facilitar uma das muitas sobrecargas que você está enfrentando, vamos atrasar o aposentadoria programado para as ferramentas de descoberta eletrônica herdadas descritas neste artigo em três meses. **As datas de aposentadoria atualizadas estão refletidas abaixo.**

Nos anos, a Microsoft forneceu ferramentas de descoberta eletrônica que permitem pesquisar, Visualizar e exportar conteúdo de email do Exchange Online. No entanto, essas ferramentas não oferecem mais uma maneira eficaz de pesquisar conteúdo não-Exchange em outros serviços do Microsoft 365, como o SharePoint Online e os grupos do Microsoft 365. Para resolver isso, a Microsoft oferece outras ferramentas de descoberta eletrônica que ajudam você a pesquisar uma ampla variedade de conteúdo da Microsoft 365. E trabalhamos muito para incorporar as funcionalidades mais atuais e poderosas de eDiscovery no [centro de conformidade da Microsoft 365](https://compliance.microsoft.com). Isso permite que as organizações respondam a solicitações legais, internas e de documentos para conteúdo em muitos serviços da Microsoft 365, incluindo o Exchange Online.

Como resultado dessa nova e aprimorada funcionalidade de descoberta eletrônica no centro de conformidade da Microsoft 365, estamos desativando os seguintes recursos e funcionalidades relacionados à descoberta eletrônica relacionados à pesquisa de conteúdo de email no Exchange Online e no Microsoft 365:

- [Descoberta eletrônica in-loco](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) e [bloqueios in-loco](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds) no centro de administração do Exchange.

- Os cmdlets do PowerShell do Exchange Online que dão suporte a descoberta eletrônica in-loco e bloqueios in-loco (estes cmdlets são identificados coletivamente como cmdlets **-MailboxSearch* ). Isso inclui os seguintes cmdlets:

  - [New-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/new-mailboxsearch)

  - [Start-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/start-mailboxsearch)

  - [Stop-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/stop-mailboxsearch)

  - [Set-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/set-mailboxsearch)

   > [!NOTE]
   > Os cmdlets [Get-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/get-mailboxsearch) e [Remove-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/remove-mailboxsearch) estarão disponíveis após os outros * * * *-MailboxSearch * * * cmdlets serem desativados para que você possa usá-los para ajudar na transição para outras ferramentas de descoberta eletrônica e de bloqueio. No entanto, após uma determinada data (citada abaixo) o suporte da Microsoft não dará mais suporte a esses dois cmdlets.

- O cmdlet [Search-Mailbox](https://docs.microsoft.com/powershell/module/exchange/search-mailbox?view=exchange-ps) no PowerShell do Exchange Online.

- As operações a seguir na API de serviços Web do Exchange:

   - [GetSearchableMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getsearchablemailboxes-operation)

   - [SearchMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/searchmailboxes-operation)
   
   - [SetHoldOnMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/setholdonmailboxes-operation)

   - [GetHoldOnMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getholdonmailboxes-operation)

- [Office 365 Advanced eDiscovery v 1.0](office-365-advanced-ediscovery.md), que é a primeira versão da descoberta eletrônica avançada que é acessada por meio de um principal caso de descoberta eletrônica no centro de conformidade & segurança do Office 365. A aposentadoria do Advanced eDiscovery v 1.0 não afeta sua capacidade de criar e gerenciar casos de descoberta eletrônica principais.

> [!NOTE]
> A funcionalidade de descoberta eletrônica que está sendo desativada só se aplica às versões baseadas em nuvem do Microsoft 365 e do Office 365. a funcionalidade de descoberta eletrônica em versões locais do Exchange e do SharePoint ainda será suportada até um aviso adicional.

As seções a seguir neste artigo fornecem orientações sobre cada recurso que está sendo desativado. Essas informações incluem linhas do cronograma e ferramentas alternativas que podem ser usadas em vez da ferramenta desativada.

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a>Descoberta eletrônica in-loco e bloqueios in-loco no centro de administração do Exchange 

De acordo com o lançamento original em 1º de julho de 2017, a funcionalidade de bloqueio e descoberta & eletrônica in-loco no centro de administração do Exchange (Eat) está sendo desativada. A página de descoberta eletrônica in-loco & contém na Eat permissão para pesquisar, reter e exportar conteúdo do Exchange Online. A descoberta eletrônica in-loco também permite que você copie os resultados da pesquisa para uma caixa de correio de descoberta para que você ou outros gerentes de descoberta eletrônica possam revisar o conteúdo e disponibilizá-lo para solicitações legais, normativas e públicas.

Como todos esses recursos (exceto para copiar os resultados da pesquisa para uma caixa de correio de descoberta) estão disponíveis na pesquisa de conteúdo, no eDiscovery e nas ferramentas de descoberta eletrônica avançada no [centro de conformidade da microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) (com funcionalidade, confiabilidade e suporte aprimorados para uma ampla variedade de serviços da Microsoft 365), recomendamos que você comece a usar essas ferramentas o mais rápido possível. Para ajudá-lo na transição para essas outras ferramentas de descoberta eletrônica, a tabela abaixo lista as ferramentas que você pode usar em vez de descoberta eletrônica in-loco e bloqueio in-loco.

### <a name="scope-of-affected-organizations"></a>Escopo de organizações afetadas

- Organizações do Office 365 e do Microsoft 365 Enterprise

- Organizações do Office 365 e Microsoft 365 Education

- Organizações do Office 365 e do Microsoft 365 governamentais; Isso inclui GCC, GCC alta e DoD

- Office 365 Alemanha

### <a name="timeline-for-retirement"></a>Linha do tempo para aposentadoria

- 1º de julho de 2020: você não poderá criar novas pesquisas e isenções, mas ainda poderá executar, editar e excluir pesquisas existentes de sua responsabilidade. O suporte da Microsoft não será mais & de descoberta eletrônica in-loco no Eat.

- 1 de outubro de 2020: a & de descoberta eletrônica in-loco tem funcionalidade no Eat será colocada em um modo somente leitura. Isso significa que você só poderá remover pesquisas e isenções existentes.

### <a name="alternative-tools"></a>Ferramentas alternativas

A tabela a seguir descreve outras ferramentas que você pode usar para substituir a funcionalidade existente que está sendo desativada.

<table>
<thead>
<tr class="header">
<th><strong>Funcionalidade</strong></th>
<th><strong>Ferramenta alternativa</strong></th>
<th><strong>Comments</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Pesquisa, exportação e retenção para fins legais</td>
<td>Principais casos de descoberta eletrônica no centro de conformidade da Microsoft 365 </td>
<td><p>O uso dos recursos dos principais casos de descoberta eletrônica fornece a paridade funcional para descoberta eletrônica in-loco e bloqueios in-loco. Isso inclui:</p>
<ul>
<li>
<p>A pesquisa é dimensionada para milhões de locais</p>
</li>
<li>
<p>Maior confiabilidade para pesquisar, exportar e colocar conteúdo em retenção</p>
</li>
<li>
<p>Pesquisa de conteúdo para o Exchange Online, o SharePoint Online, o OneDrive for Business, o Skype for Business, o Microsoft Teams, os grupos do Yammer, os grupos do Microsoft 365 e outros conteúdos armazenados em aplicativos do Office 365</p></li></ul>
<p>Para obter mais informações, consulte <a href="https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations">gerenciar investigações legais no Office 365</a>.</td>
</tr>
<tr class="even">
<td>Bloqueio para fins de retenção</td>
<td>Políticas de retenção no centro de conformidade da Microsoft 365</td>
<td><p>Você pode usar as políticas de retenção para manter o conteúdo e, se desejado, excluí-lo após a expiração do período de retenção. Outros recursos incluem:</p>
<ul>
<li>
<p>Aplicando políticas para toda a organização </p>
</li><li>
<p>Aplicar políticas a locais de conteúdo específicos, como Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, Microsoft Teams e grupos do Office 365</p></li>
<li>
<p>Aplicando políticas a usuários específicos</p></li></ul>
<p>Para obter mais informações, consulte <a href="https://docs.microsoft.com/microsoft-365/compliance/retention-policies">saiba mais sobre políticas de retenção e rótulos de retenção</a>.</td>
</tr>
<tr class="odd">
<td>Copiar os resultados da pesquisa de email para uma caixa de correio de descoberta para revisão</td><td>Revisar conjuntos no eDiscovery v 2.0 avançado</td>
<td><p>A revisão do conteúdo no Microsoft 365 nunca foi tão fácil. Os conjuntos de revisão têm vários ótimos recursos para ajudar a reduzir a quantidade de tempo e dados necessários para a revisão, incluindo:</p>
<ul>
<li><p>Executar consultas de pesquisa rápida e filtrar conteúdo em um conjunto de revisão</p></li>
<li><p>Analisar conteúdo em um conjunto de revisão; Isso inclui a segmentação de email, a detecção de duplicidades, a análise de temas e a codificação de previsão</p></li>
<li><p>Marcar documentos em um conjunto de revisão</p></li>
<li><p>Sugestões de marcação para ajudar a identificar o conteúdo de privilégio de cliente do advogado</p></li></ul>
<p>Para obter mais informações, confira <a href="https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20">Visão geral da solução de Descoberta Eletrônica Avançada no Microsoft 365</a>.</p>
<p>
<p>Como alternativa, você pode exportar os resultados da pesquisa para arquivos PST e usar o serviço de importação do Microsoft 365 para importar os PSTs para uma caixa de correio de descoberta. Para instruções passo a passo, consulte usar o <a href="https://docs.microsoft.com/microsoft-365/compliance/use-network-upload-to-import-pst-files">carregamento de rede para importar arquivos pst para o Office 365</a>.
</tr>
<tr class=even>
  <td>Copiar mensagens de uma caixa de correio para uma caixa de correio diferente</td>
  <td><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Atribuir permissões a uma caixa de correio</a></td>
  <td>Para dar a uma pessoa acesso ao email de outro usuário (como quando um funcionário deixa sua organização e você precisa conceder acesso a outra pessoa para o email do usuário anterior), recomendamos que você atribua a essa pessoa permissões para acessar a caixa de correio do funcionário anterior. Portanto, em vez de copiar itens de caixa de correio para outra caixa de correio de usuário ou para uma caixa de correio compartilhada, basta atribuir uma permissão de usuário para acessar a caixa de correio</td>
  
  </tr>
<tr class="odd">
<td>Restaurar itens da pasta itens recuperáveis</td>
  <td><a href="https://docs.microsoft.com/powershell/module/exchange/Restore-RecoverableItems">Restore-RecoverableItems</td>
  <td>Você pode restaurar itens excluídos permanentemente (também conhecidos como itens <i>excluídos por software</i> ) em caixas de correio, desde que o período de retenção do item excluído de um item não tenha expirado. Para obter mais informações, consulte <a href="https://docs.microsoft.com/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">pasta itens recuperáveis no Exchange Online</a>.</td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a>Perguntas frequentes sobre a descoberta eletrônica in-loco e bloqueios in-loco

**Uso a funcionalidade copiar resultados de pesquisa de descoberta eletrônica in-loco & mantém no Eat para copiar os resultados da pesquisa para uma caixa de correio de descoberta para análise por advogados. Quais opções eu tenho agora?**

Existem duas maneiras de replicar essa funcionalidade hoje. O primeiro é usar os [conjuntos de revisão no eDiscovery v 2.0 avançado](https://docs.microsoft.com/microsoft-365/compliance/view-documents-in-review-set). Os conjuntos de revisão têm muitos dos mesmos recursos que você vê em uma ferramenta de revisão tradicional como pesquisa rápida de documentos, marcação, encadeamento de emails, agrupamentos próximos duplicados, análise de temas e codificação de previsão. Se você ainda quiser usar caixas de correio de descoberta para revisão, a segunda opção é exportar os resultados da pesquisa para arquivos PST e, em seguida, importar os arquivos PST para uma caixa de correio de descoberta usando o [recurso de importação de PST](use-network-upload-to-import-pst-files.md) no centro de conformidade da Microsoft.

**Como controlar quais locais de conteúdo (como caixas de correio ou sites) podem ser pesquisados por um gerente de descoberta eletrônica usando as novas ferramentas?**

O centro de conformidade da Microsoft 365 também usa [limites de conformidade](set-up-compliance-boundaries.md) para controlar quais locais de conteúdo um gerente de descoberta pode pesquisar. Os limites de conformidade são úteis em entidades governamentais que precisam permanecer dentro dos limites da agência ou de corporações multinacionais necessárias para respeitar os inboards geográficas.

**Como posso migrar minhas pesquisas atuais e se retenções para o centro de conformidade da Microsoft 365?**

É possível migrar pesquisas de descoberta eletrônica in-loco e isenções do Eat usando o PowerShell. Para obter instruções, consulte [migrar pesquisas e isenções da Eat para o centro de conformidade da Microsoft 365](https://go.microsoft.com/fwlink/?linkid=2114224).

## <a name="-mailboxsearch-cmdlets"></a>\*-Cmdlets do MailboxSearch

De acordo com o aviso original anunciado no dia 1º de julho de 2017 no centro de administração do Exchange, a & de descoberta eletrônica in-loco e os cmdlets correspondentes ** \* -MailboxSearch** estão sendo desativados. Esses cmdlets fornecem aos usuários a capacidade de Pesquisar, reter e exportar o conteúdo da caixa de correio para solicitações legais, normativas e públicas.

Como esses recursos agora estão disponíveis no [<span class="underline">centro de conformidade da Microsoft 365</span>](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) e no centro de segurança & conformidade do Office 365 com desempenho e escalabilidade aprimorados, você deve usar esses cmdlets aprimorados. Estes cmdlets incluem [<span class="underline"> \* -ComplianceCase</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase), [<span class="underline"> \* -ComplianceSearch</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch), [<span class="underline"> \* -CaseHoldPolicy</span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy), [<span class="underline"> \* -CaseHoldRule</span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdrule)e [<span class="underline"> \* -ComplianceSearchAction</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction).

### <a name="scope-of-affected-organizations"></a>Escopo de organizações afetadas

- Organizações do Office 365 e do Microsoft 365 Enterprise

- Organizações do Office 365 e Microsoft 365 Education

- Organizações do Office 365 e do Microsoft 365 governamentais; Isso inclui GCC, GCC alta e DoD

- Office 365 Alemanha

### <a name="timeline"></a>Linha do tempo

- 1º de julho de 2020: você não poderá usar o **New-MailboxSearch** para criar novas pesquisas de descoberta eletrônica in-loco e bloqueios in-loco, mas ainda poderá usar cmdlets para executar, editar e excluir pesquisas existentes e manter por sua conta e risco. O suporte da Microsoft não fornecerá mais assistência para esses tipos de pesquisas e isenções.

- 1 de outubro de 2020: como mencionado anteriormente, o & de descoberta eletrônica in-loco tem funcionalidade no Eat será colocado em um modo somente leitura. Isso também significa que você não poderá usar os cmdlets **New-MailboxSearch**, **Start-MailboxSearch**ou **Set-MailboxSearch** . Você só poderá obter e remover pesquisas e isenções existentes.

### <a name="alternative-tools"></a>Ferramentas alternativas

A tabela a seguir descreve outras ferramentas que você pode usar para substituir a funcionalidade existente que está sendo desativada.

<table>
<thead>
<tr class="header">
<th><strong>Funcionalidade</strong></th>
<th><strong>Ferramentas alternativas</strong></th>
<th><strong>Comments</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Pesquisa e exportação</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>Os cmdlets do ComplianceSearch e do ComplianceSearchAction funcionam juntos para ajudá-lo a Pesquisar e exportar conteúdo. Você pode criar uma nova pesquisa e exibir a estimativa de pesquisa usando os cmdlets <strong>New-</strong>, <strong>Get-</strong>e <strong>Start-ComplianceSearch</strong> . Em seguida, você pode usar o cmdlet <strong>New-ComplianceSearchAction</strong> para exportar os resultados da pesquisa. Você ainda terá que usar a ferramenta de descoberta eletrônica principal no centro de conformidade do Microsoft 365 para baixar os resultados da pesquisa para o seu computador local.</p>
<p>
<p><strong>Observação:</strong> Se você usar esses cmdlets para criar pesquisas que não estão associadas a um caso de descoberta eletrônica principal, essas pesquisas serão localizadas na página de <strong>pesquisa de conteúdo</strong> no centro de conformidade da Microsoft 365.</p></td>
</tr>
<tr class="even">
<td>Armazenar conteúdo em uma caixa de correio</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy"><span class="underline">*-CaseHoldPolicy</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdrule"><span class="underline">*-CaseHoldRule</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>As isenções no centro de conformidade da Microsoft 365 devem estar associadas a um ComplianceCase. Primeiro, crie o caso de conformidade e, em seguida, crie um CaseHoldPolicy e um CaseHoldRule.</p>
<p><strong>Observação:</strong> A criação de um CaseHoldPolicy sem um CaseHoldRule de criação tornará a retenção inoperante até que o CaseHoldRule seja criado e associado ao CaseHoldPolicy. Consulte a documentação do cmdlet para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td>Copiar os resultados da pesquisa para uma caixa de correio de descoberta</td>
<td>Nenhuma</td>
<td>Não há substituição direta para essa funcionalidade, pois ela não fornece acesso a todos os serviços do Microsoft 365. Consulte as seguintes perguntas frequentes abaixo para obter soluções alternativas.</td>
</tr>
  <tr class=even>
  <td>Copiar mensagens de uma caixa de correio para uma caixa de correio diferente</td>
  <td><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Atribuir permissões a uma caixa de correio</a></td>
  <td>Para dar a uma pessoa acesso ao email de outro usuário (como quando um funcionário deixa sua organização e você precisa conceder acesso a outra pessoa para o email do usuário anterior), recomendamos que você atribua a essa pessoa permissões para acessar a caixa de correio do funcionário anterior. Portanto, em vez de copiar itens de caixa de correio para outra caixa de correio de usuário ou para uma caixa de correio compartilhada, basta atribuir uma permissão de usuário para acessar a caixa de correio</td>
  
  </tr>

</tbody>
</table>

### <a name="faqs-about--mailboxsearch-cmdlets"></a>Perguntas frequentes sobre os cmdlets ***-MailboxSearch**

**Usamos a pesquisa de cópia para exportar mensagens de email ou mensagens instantâneas para fins de outras investigações jurídicas e de descoberta eletrônica. Que outras opções temos após a retirada desses cmdlets?**

As [<span class="underline">APIs do Microsoft Graph</span>](https://developer.microsoft.com/en-us/graph) fornecem vários métodos para extrair dados para análise e outros fins muito mais resistentes e escalonáveis do que os cmdlets usando o ** \* -MailboxSearch** .

**Como posso migrar minhas pesquisas e se o centro de conformidade da Microsoft 365?**

É possível migrar pesquisas de descoberta eletrônica in-loco e bloqueios do centro de administração do Exchange usando um script do PowerShell. Para obter mais informações, consulte [migrar pesquisas de descoberta eletrônica herdadas e isenções para o centro de conformidade da Microsoft 365](migrate-legacy-eDiscovery-searches-and-holds.md).

**Após a desativação dos cmdlets, ainda poderei remover ou recuperar pesquisas?**

Sim, embora estejamos removendo a capacidade de criar e modificar pesquisas, você ainda poderá usar **Get-MailboxSearch** e **Remove-MailboxSearch** até um aviso adicional. No entanto, o uso desses cmdlets será por seu próprio risco depois que as datas de aposentadoria e o suporte da Microsoft não poderão mais fornecer assistência.

## <a name="search-mailbox-cmdlet"></a>Cmdlet Search-Mailbox

O cmdlet **Search-Mailbox** no Exchange Online PowerShell está sendo desativado como anunciado originalmente em um aviso na saída do cmdlet a partir de volta no 2018. O cmdlet **Search-Mailbox** foi usado originalmente para pesquisar a caixa de correio de um usuário e limpar o conteúdo mal-intencionado. Recomendamos que você comece a usar os cmdlets **New-ComplianceSearch** e **New-ComplianceSearchAction** no Office 365 Security & o PowerShell do centro de conformidade para pesquisar e limpar o conteúdo. Para uma experiência de segurança interna, os [<span class="underline">recursos de segurança do Microsoft 365</span>](https://docs.microsoft.com/microsoft-365/security/) oferecem proteção robusta contra ameaças para email e muitos outros serviços da Microsoft.

### <a name="scope-of-affected-organizations"></a>Escopo de organizações afetadas

- Organizações do Office 365 e do Microsoft 365 Enterprise

- Organizações do Office 365 e Microsoft 365 Education

- Organizações do Office 365 e do Microsoft 365 governamentais; Isso inclui GCC, GCC alta e DoD

- Office 365 Alemanha

### <a name="timeline"></a>Linha do tempo

-  1º de julho de 2020: o cmdlet **Search-Mailbox** não estará mais disponível e o suporte da Microsoft não fornecerá mais assistência.

### <a name="alternative-tools"></a>Ferramentas alternativas

A tabela a seguir descreve outras ferramentas que você pode usar para substituir a funcionalidade existente que está sendo desativada.

<table>
<thead>
<tr class="header">
<th><strong>Funcionalidade</strong></th>
<th><strong>Ferramentas alternativas</strong></th>
<th><strong>Comments</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Pesquisar uma caixa de correio</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch?view=exchange-ps"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction?view=exchange-ps"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></a></p></td>
<td><p>Os cmdlets do ComplianceSearch e do ComplianceSearchAction funcionam juntos para ajudá-lo a Pesquisar e exportar conteúdo. Você pode criar uma nova pesquisa e exibir a estimativa de pesquisa usando os cmdlets <strong>New-</strong>, <strong>Get-</strong>e <strong>Start-ComplianceSearch</strong> . Em seguida, você pode usar o comando <strong>New-ComplianceSearchAction-Export</strong> para exportar os resultados da pesquisa. Você ainda terá que usar a ferramenta de descoberta eletrônica principal no centro de conformidade do Microsoft 365 para baixar os resultados da pesquisa para o seu computador local.</p></p>
</td>
</tr>
<tr class="even">
<td>Excluir email em massa de uma caixa de correio</td>
<td><p><a href="https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes?view=o365-worldwide"><span class="underline">Configurar uma política de arquivamento e exclusão para caixas de correio</span></a></p>
<p></p></td>
<td><p>Os administradores podem criar uma política de arquivamento e exclusão que move automaticamente os itens para a caixa de correio de arquivo morto de um usuário e exclui automaticamente os itens da caixa de correio.</p>
</td>
</tr>
<tr class="even">
<td>Copiar os resultados da pesquisa para uma caixa de correio de descoberta</td>
<td> </td>
<td>Não há substituição direta para essa funcionalidade, pois ela não fornece acesso a todos os serviços do Microsoft 365. Consulte as perguntas frequentes na seção <strong>cmdlets *-MailboxSearch</strong> para obter soluções alternativas. </td>
</tr>
<tr class=odd>
  <td>Copiar mensagens de uma caixa de correio para uma caixa de correio diferente</td>
  <td><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Atribuir permissões a uma caixa de correio</a></td>
  <td>Para dar a uma pessoa acesso ao email de outro usuário (como quando um funcionário deixa sua organização e você precisa conceder acesso a outra pessoa para o email do usuário anterior), recomendamos que você atribua a essa pessoa permissões para acessar a caixa de correio do funcionário anterior. Portanto, em vez de copiar itens de caixa de correio para outra caixa de correio de usuário ou para uma caixa de correio compartilhada, basta atribuir uma permissão de usuário para acessar a caixa de correio</td>
</tr>
<tr class=even>
  <td>Limpar mensagens de uma caixa de correio</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch?view=exchange-ps"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction?view=exchange-ps"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></p></td>
<td><p>Os cmdlets do ComplianceSearch e do ComplianceSearchAction funcionam juntos para ajudá-lo a Pesquisar e limpar o conteúdo. Você pode criar e executar uma pesquisa com os cmdlets <strong>New-ComplianceSearch</strong> e <strong>New-ComplianceSearch</strong> e, em seguida, pode limpar o conteúdo usando o comando <strong>New-ComplianceSearchAction-purga-PurgeType</strong> . Para obter mais informações, consulte <a href="https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">Search for and Delete messages</span></a>.</p>
</td>
</tr>
<tr class="odd"> 
<td>Limpar mensagens de uma caixa de correio</td>
<td><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Atribuir permissões a uma caixa de correio</a></td>
<td>Para limpar mensagens de uma caixa de correio, atribua permissões de administrador para acessar a caixa de correio do funcionário. As mensagens podem ser excluídas e recicladas conforme necessário aproveitando as funcionalidades internas de pesquisa e visualização no Outlook.</td>
</tr>
</tbody>
</table>

## <a name="exchange-web-services-api-operations"></a>Operações da API de serviços Web do Exchange

Essas operações na API de serviços Web do Exchange são usadas pelo recurso de bloqueio de descoberta & eletrônica in-loco no centro de administração do Exchange e pelos cmdlets ** \* MailboxSearch** correspondentes no PowerShell do Exchange Online. Eles também serão desativados como parte da remoção de outras ferramentas de descoberta eletrônica herdadas.

### <a name="scope-of-affected-organizations"></a>Escopo de organizações afetadas

- Organizações do Office 365 e do Microsoft 365 Enterprise

- Organizações do Office 365 e Microsoft 365 Education

- Organizações do Office 365 e do Microsoft 365 governamentais; Isso inclui GCC, GCC alta e DoD

- Office 365 Alemanha

### <a name="timeline"></a>Linha do tempo

- 1 de julho de 2020: as operações GetSearchableMailboxes, SearchMailboxes, SetHoldOnMailboxes e GetHoldOnMailboxes não estarão mais disponíveis e o suporte da Microsoft não fornecerá mais assistência.

## <a name="advanced-ediscovery-v10"></a>Descoberta eletrônica avançada v 1.0

O eDiscovery v 1.0 avançado, que é a versão da descoberta eletrônica avançada disponível em um caso de descoberta eletrônica principal clicando em **alternar para descoberta eletrônica avançada**, está sendo desativado. Sua funcionalidade foi substituída pela nova [solução de descoberta eletrônica avançada](https://aka.ms/edisco) no centro de conformidade da Microsoft 365.

Para determinar se sua organização está usando o eDiscovery v 1.0 avançado:

1. Vá para o [centro de conformidade & segurança do Office 365](https://protection.office.com).

2. No painel de navegação esquerdo do centro de conformidade & segurança, clique em **descoberta eletrônica > eDiscovery**e abra um caso de descoberta eletrônica principal.

3. Se você vir o botão **alternar para descoberta eletrônica avançada** e, em seguida, clicar nele para obter a versão 1,0 da descoberta eletrônica avançada, que está sendo desativada. A capacidade de criar e gerenciar ocorrências na descoberta eletrônica principal não será afetada. Somente a capacidade de adicionar e analisar dados de caso no eDiscovery v 1.0 avançado (clicando em **alternar para descoberta eletrônica avançada**) está sendo desativada.

A nova solução de descoberta eletrônica avançada no Microsoft 365 (também conhecida como *AutoDiscovery v 2.0*) fornece todos os recursos da solução original, mas agora inclui uma abordagem baseada em responsáveis de identificar conteúdo em outros serviços do Microsoft 365, coletar esse conteúdo e, em seguida, adicioná-lo a um conjunto de revisão em que os revisores podem aproveitar consultas de pesquisa rápida, marcação e recursos de análise para ajudar a analisar documentos relevantes. A descoberta eletrônica avançada agora inclui o processamento melhorado e os visualizadores nativos para tipos de arquivo da Microsoft e de terceiros, uma lista completa de tipos de arquivo é [aqui](https://docs.microsoft.com/microsoft-365/compliance/supported-filetypes-ediscovery20) e os campos de metadados suportados estão [aqui](https://docs.microsoft.com/microsoft-365/compliance/document-metadata-fields-in-advanced-ediscovery). Além disso, a nova solução de descoberta eletrônica avançada fornece um recurso de gerenciamento poderoso que permite que você aplique isenções ao conteúdo em diferentes serviços, notifique os usuários das isenções e rastreie as respostas dos responsáveis, tudo em um caso de descoberta eletrônica avançada.

Para acessar o eDiscovery v 2.0 avançado:

1. Vá para o [centro de conformidade da Microsoft 365](https://compliance.microsoft.com).

2. No painel de navegação esquerdo do centro de conformidade da Microsoft 365, clique em **Mostrar tudo**e, em seguida, clique em **descoberta eletrônica > avançado**.

No momento, recomendamos que você comece a migrar seu fluxo de trabalho de descoberta eletrônica para a nova funcionalidade avançada de descoberta eletrônica. Embora você ainda consiga acessar o eDiscovery v 1.0 avançado nos casos existentes, o suporte da Microsoft não fornecerá suporte após 1º de outubro de 2020. Confira mais detalhes na linha do tempo a seguir.

### <a name="scope-of-affected-organizations"></a>Escopo de organizações afetadas

- Organizações do Office 365 e do Microsoft 365 Enterprise

- Organizações do Office 365 e Microsoft 365 Education

- Office 365 Alemanha

### <a name="timeline"></a>Linha do tempo

- 1º de julho de 2020: você não poderá criar novos casos avançados de descoberta eletrônica v 1.0.

- 1 de outubro de 2020: você não poderá adicionar novos dados (preparar resultados de pesquisa para descoberta eletrônica avançada) para qualquer caso. Você poderá continuar a trabalhar com dados em casos existentes por sua conta e risco. O suporte da Microsoft não fornecerá mais assistência. 

### <a name="alternative-tools"></a>Ferramentas alternativas

A [solução de descoberta eletrônica avançada](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20) no centro de conformidade da Microsoft 365.
