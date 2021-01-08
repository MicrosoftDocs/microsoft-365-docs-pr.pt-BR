---
title: Configurar permissões de filtragem para a Pesquisa de Conteúdo
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: 1adffc35-38e5-4f7d-8495-8e0e8721f377
description: Use a filtragem de permissões de Pesquisa de Conteúdo para permitir que um gerente de Descoberta Eletrônico pesquise apenas um subconjunto de caixas de correio e sites em sua organização.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8ac09b35a4487ad836b48ba0cf7fee765e758ec4
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780469"
---
# <a name="configure-permissions-filtering-for-content-search"></a>Configurar permissões de filtragem para a Pesquisa de Conteúdo

Você pode usar a filtragem de permissões de pesquisa para permitir que um gerente de Descoberta Eletrônico pesquise apenas um subconjunto de caixas de correio e sites em sua organização. Você também pode usar permissões de filtragem para que esse mesmo gerente de Descoberta Eletrônica procure somente o conteúdo da caixa de correio ou site que atende aos critérios de pesquisa específicos. Por exemplo, você pode permitir que um gerente de Descoberta Eletrônica pesquise apenas as caixas de correio de usuários em um local ou departamento específico. Você pode fazer isso criando um filtro que usa um filtro de destinatário com suporte para limitar quais caixas de correio um usuário ou grupo de usuários específico pode pesquisar. Você também pode criar um filtro que especifica o conteúdo da caixa de correio que um usuário pode pesquisar. Isso é feito criando um filtro que usa uma propriedade de mensagem pesquisável. Da mesma forma, você pode permitir que um gerente de Descoberta eDiscovery pesquise apenas sites específicos do SharePoint em sua organização. Você pode fazer isso criando um filtro que limita qual site pode ser pesquisado. Você também pode criar um filtro que especifica qual conteúdo de site pode ser pesquisado. Isso é feito criando um filtro que usa uma propriedade de site pesquisável.

Você também pode usar a filtragem de permissões de pesquisa para criar limites lógicos (chamados de limites de *conformidade)* dentro de uma organização que controlam os locais de conteúdo do usuário (como caixas de correio, sites do SharePoint e contas do OneDrive) que gerentes de Descobertas Eletrônicos específicos podem pesquisar. Para saber mais, confira Configurar limites de conformidade para investigações de [Descobertas No Office 365.](tagging-and-assessment-in-advanced-ediscovery.md)
  
A filtragem de permissões de pesquisa é suportada pelo recurso Pesquisa de Conteúdo no Centro de Conformidade & Segurança. Esses quatro cmdlets permitem configurar e gerenciar filtros de permissões de pesquisa:
  
[New-ComplianceSecurityFilter](#new-compliancesecurityfilter)

[Get-ComplianceSecurityFilter](#get-compliancesecurityfilter)

[Set-ComplianceSecurityFilter](#set-compliancesecurityfilter)

[Remove-ComplianceSecurityFilter](#remove-compliancesecurityfilter)

## <a name="requirements-to-configure-permissions-filtering"></a>Requisitos para configurar a filtragem de permissões

- Para executar os cmdlets de filtro de segurança de conformidade, você precisa ser membro do grupo de funções Gerenciamento da Organização no Centro de Conformidade e Segurança & Segurança. Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).

- Você precisa se conectar ao PowerShell do Centro de Conformidade e Segurança do Exchange Online e & para usar os cmdlets de filtro de segurança de conformidade. Isso é necessário porque esses cmdlets exigem acesso às propriedades da caixa de correio e é por isso que você precisa se conectar ao PowerShell do Exchange Online. Veja as etapas na próxima seção.

- Consulte a seção [Mais informações](#more-information) para obter informações adicionais sobre os filtros de permissões de pesquisa.

- A filtragem de permissões de pesquisa é aplicável a caixas de correio inativas, o que significa que você pode usar a filtragem de conteúdo de caixa de correio e caixa de correio para limitar quem pode pesquisar uma caixa de correio inativa. Consulte a [seção Mais informações](#more-information) para obter informações adicionais sobre filtragem de permissões e caixas de correio inativas.

- A filtragem de permissões de pesquisa não pode ser usada para limitar quem pode pesquisar pastas públicas no Exchange.

- Não há limite para o número de filtros de permissões de pesquisa que podem ser criados em uma organização. Mas o desempenho da pesquisa será afetado quando houver mais de 100 filtros de permissões de pesquisa. Para manter o número de filtros de permissões de pesquisa em sua organização o menor possível, crie filtros que combinem regras para Exchange, SharePoint e OneDrive em um único filtro sempre que possível.

## <a name="connect-to-exchange-online-and-security--compliance-center-powershell-in-a-single-session"></a>Conectar-se ao PowerShell do Centro de Conformidade e Segurança & Exchange Online em uma única sessão

Antes de poder executar com êxito o script nesta seção, você precisa baixar e instalar o módulo do PowerShell do Exchange Online V2. Para obter informações, [consulte Sobre o módulo V2 do PowerShell do Exchange Online.](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)

1. Salve o texto a seguir em um arquivo de script do Windows PowerShell usando um sufixo de nome de arquivo **.ps1**. Por exemplo, você poderia salvá-lo em um arquivo **chamadoConnectEXO-SCC.ps1**.

    ```powershell
    Import-Module ExchangeOnlineManagement
    $UserCredential = Get-Credential
    Connect-ExchangeOnline -Credential $UserCredential -ShowBanner:$false
    Connect-IPPSSession -Credential $UserCredential
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. No computador local, abra o Windows PowerShell, vá para a pasta onde está localizado o script criado na etapa anterior e execute o script; por exemplo:

    ```powershell
    .\ConnectEXO-SCC.ps1
    ```

Como saber se funcionou? Depois de executar o script, os cmdlets do Exchange Online e do PowerShell de conformidade & segurança são importados para sua sessão local do Windows PowerShell. Se nenhum erro aparecer, a conexão terá sido estabelecida. Um teste rápido é executar um cmdlet do Centro de Conformidade e Segurança & Exchange Online. Por exemplo, você pode executar e **Get-Mailbox** e **Get-ComplianceSearch**.

Para solucionar problemas de erros de conexão do PowerShell, confira:

- [Conectar-se ao PowerShell do Exchange Online ](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell#how-do-you-know-this-worked)

- [Conectar-se ao PowerShell do Centro de Conformidade e Segurança](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell#how-do-you-know-this-worked)

## <a name="new-compliancesecurityfilter"></a>New-ComplianceSecurityFilter

O **New-ComplianceSecurityFilter** é usado para criar um filtro de permissões de pesquisa. A tabela a seguir descreve os parâmetros para este cmdlet. Todos os parâmetros são necessários para criar um filtro de segurança de conformidade.
  
|**Parâmetro**|**Descrição**|
|:-----|:-----|
| _Action_ <br/> | O  _parâmetro Action_ especifica o tipo de ação de pesquisa ao qual o filtro é aplicado. As ações de pesquisa de conteúdo possíveis são:  <br/><br/> **Exportar:** O filtro é aplicado ao exportar os resultados da pesquisa.  <br/> **Visualização:** O filtro é aplicado ao visualizar os resultados da pesquisa.  <br/> **Limpar:** O filtro é aplicado ao se purga os resultados da pesquisa.  <br/> **Pesquisa:** O filtro é aplicado ao executar uma pesquisa.  <br/> **Tudo:** O filtro é aplicado a todas as ações de pesquisa.  <br/> |
| _FilterName_ <br/> |O  _parâmetro FilterName_ especifica o nome do filtro de permissões. Esse nome é usado para identificar um filtro ao usar os cmdlets **Get-ComplianceSecurityFilter**, **Set-ComplianceSecurityFilter,** e **Remove-ComplianceSecurityFilter**.  <br/> |
| _Filtros_ <br/> | O  _parâmetro Filters_ especifica os critérios de pesquisa para o filtro de segurança de conformidade. Você pode criar três tipos diferentes de filtros:  <br/><br/> **Filtragem de caixa de correio:** Esse tipo de filtro especifica as caixas de correio que os usuários atribuídos (especificado pelo  _parâmetro Users)_ podem pesquisar. A sintaxe para esse tipo de filtro é **Mailbox_** _MailboxPropertyName_, onde  _MailboxPropertyName_ especifica uma propriedade de caixa de correio usada para escopo as caixas de correio que podem ser pesquisadas. Por exemplo, o filtro de caixa de correio permitiria que o usuário atribuído a esse filtro pesquisasse somente as caixas de correio com o valor  `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` "OttawaUsers" na propriedade CustomAttribute10.  <br/>  Qualquer propriedade de destinatário filtável com suporte pode ser usada para a _propriedade MailboxPropertyName._ Para uma lista de propriedades com suporte, consulte [Propriedades filtáveis para o parâmetro -RecipientFilter](https://go.microsoft.com/fwlink/p/?LinkId=784903).  <br/><br/> **Filtragem de conteúdo de caixa de correio:** Esse tipo de filtro é aplicado ao conteúdo que pode ser pesquisado. Ele especifica o conteúdo da caixa de correio que os usuários atribuídos podem pesquisar. A sintaxe para esse tipo de filtro é **MailboxContent_** _SearchablePropertyName: value_, onde  _SearchablePropertyName_ especifica uma propriedade KQL (Keyword Query Language) que pode ser especificada em uma Pesquisa de Conteúdo. Por exemplo, o filtro de conteúdo de caixa de correio permitiria que o usuário atribuído a esse filtro pesquisasse apenas mensagens enviadas a destinatários no contoso.com  `MailboxContent_recipients:contoso.com` domínio.  <br/>  Para uma lista de propriedades de mensagens pesquisáveis, consulte [Consultas de palavra-chave e condições de pesquisa para Pesquisa de Conteúdo.](keyword-queries-and-search-conditions.md) <br/> <br/> **Importante:**  Um único filtro de pesquisa não pode conter um filtro de caixa de correio e um filtro de conteúdo de caixa de correio. Para combiná-los em um único filtro, você precisa usar uma lista [de filtros.](#using-a-filters-list-to-combine-filter-types)  Mas um filtro pode conter uma consulta mais complexa do mesmo tipo. Por exemplo,  `"Mailbox_CustomAttribute10 -eq 'FTE' -and Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'"`  <br/><br/> **Filtragem de conteúdo de site e site:** Há dois filtros relacionados ao site do SharePoint e do OneDrive for Business que você pode usar para especificar qual site ou conteúdo de site os usuários atribuídos podem pesquisar:  <br/><br/> - **Site_** _SearchableSiteProperty_ <br/> - **SiteContent_** _SearchableSiteProperty_ <br/><br/>  Esses dois filtros são intercambiáveis. Por exemplo,  `"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` e retorne os mesmos  `"SiteContent_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` resultados. Mas para ajudá-lo a identificar o que um filtro faz, você pode usar para especificar propriedades relacionadas ao site (como uma URL do site) e para especificar propriedades relacionadas ao conteúdo (como tipos  `Site_`  `SiteContent_` de documento. Por exemplo, o filtro permitiria que o usuário atribuído a esse filtro pesquisasse  `"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` apenas o conteúdo no conjunto de https://contoso.sharepoint.com/sites/doctors sites. O filtro permitiria que o usuário atribuído a esse filtro procurasse apenas documentos do  `"SiteContent_FileExtension -eq 'docx'"` Word (Word 2007 e posterior).  <br/><br/>  Para uma lista de propriedades de site pesquisáveis, confira [Visão geral das propriedades rastreadas e gerenciadas no SharePoint.](https://go.microsoft.com/fwlink/p/?LinkId=331599) As propriedades marcadas com **Um** Sim **na coluna Queryable** podem ser usadas para criar um filtro de conteúdo de site ou site.  <br/><br/> **Importante:** Você precisa criar um filtro de permissões de pesquisa para impedir explicitamente que os usuários pesquisem locais de conteúdo em um serviço específico (como impedir que um usuário pesquise em qualquer caixa de correio do Exchange ou em qualquer site do SharePoint). Em outras palavras, criar um filtro de permissões de pesquisa que permita que um usuário pesquise todos os sites do SharePoint na organização não impede que esse usuário pesquise caixas de correio. Por exemplo, para permitir que os administradores do SharePoint pesquisem apenas sites do SharePoint, você precisa criar um filtro que os impeça de pesquisar caixas de correio. Da mesma forma, para permitir que os administradores do Exchange pesquisem apenas caixas de correio, você precisa criar um filtro que os impeça de pesquisar sites.           |
| _Usuários_ <br/> |O  _parâmetro Users_ especifica os usuários que têm esse filtro aplicado às suas Pesquisas de Conteúdo. Identifica os usuários por seus alias ou endereço SMTP principal. Você pode especificar vários valores separados por vírgulas ou pode atribuir o filtro a todos os usuários usando o valor **All**.  <br/> Você também pode usar o  _parâmetro Users_ para especificar um grupo de funções & Centro de Conformidade e Segurança. Isso permite que você crie um grupo de função personalizada e, em seguida, atribua esse grupo de função a um filtro de permissões de pesquisa. Por exemplo, digamos que você tenha um grupo de função personalizada para gerentes de Descoberta Eletrônica para a subsidiária americana de uma multinacional. Você pode usar o parâmetro  _Users_ para especificar esse grupo de função (usando a propriedade Name do grupo de função) e, em seguida, usar o parâmetro  _Filter_ para permitir que apenas caixas de correio nos EUA sejam pesquisadas.  <br/> Você não pode especificar um grupo de distribuição com esse parâmetro.  <br/> |
   
### <a name="using-a-filters-list-to-combine-filter-types"></a>Usando uma lista de filtros para combinar tipos de filtro

Uma *lista de filtros* é um filtro que inclui um filtro de caixa de correio e um filtro de site separados por vírgula. Usar uma lista de filtros é o único método com suporte para combinar diferentes tipos de filtros. No exemplo a seguir, observe que uma vírgula separa os filtros **Caixa** de Correio e **Site:**

```powershell
-Filters "Mailbox_CustomAttribute10 -eq 'OttawaUsers'", "Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"
```

Quando um filtro que contém uma lista de filtros é processado durante a execução de uma pesquisa de conteúdo, dois filtros de permissões de pesquisa são criados a partir da lista de filtros: um para cada filtro separado por vírgula. Portanto, no exemplo anterior, um filtro de permissões de pesquisa de caixa de correio e um filtro de permissões de pesquisa de site seriam criados. 

Uma alternativa ao uso de uma lista de filtros seria criar dois filtros de permissões de pesquisa separados. Portanto, no exemplo anterior, você criaria um filtro para o atributo de caixa de correio e um filtro para o atributo de site. Em ambos os casos, os resultados são os mesmos. Usar uma lista de filtros ou criar filtros de permissões de pesquisa separados é uma questão de preferência.

Lembre-se do seguinte sobre o uso de uma lista de filtros:

- Você precisa usar uma lista de filtros para criar um filtro que inclua um filtro **de** Caixa de Correio e um **filtro MailboxContent.** 

- Como sugerido anteriormente, você não precisa usar uma lista de filtros para incluir um **site** e um **filtro SiteContent** em um único filtro de permissões de pesquisa. Por exemplo, você pode combinar **filtros Site** e **SiteContent** usando **um operador -or.**

   ```powershell
   -Filters "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"
   ```

- Cada componente de uma lista de filtros pode conter uma sintaxe de filtro complexa. Por exemplo, os filtros de caixa de correio e de site podem conter vários filtros separados por **um operador ou -:**

   ```powershell
   -Filters "Mailbox_Department -eq 'CohoWinery' -or Mailbox_CustomAttribute10 -eq 'CohoUsers'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'"
   ```

## <a name="examples-of-creating-search-permissions-filters"></a>Exemplos de criação de filtros de permissões de pesquisa

Estes são exemplos de como usar o cmdlet **New-ComplianceSecurityFilter** para criar um filtro de permissões de pesquisa. 
  
Este exemplo permite que o usuário annb@contoso.com executar todas as ações de Pesquisa de Conteúdo somente para caixas de correio no Canadá. O filtro usa o código de país numérico de três dígitos para o Canadá da ISO 3166-1.

```powershell
New-ComplianceSecurityFilter -FilterName CountryFilter  -Users annb@contoso.com -Filters "Mailbox_CountryCode  -eq '124'" -Action All
```

Este exemplo permite que os usuários viniciusm e clarab pesquisem apenas as caixas de correio que têm o valor Marketing para a propriedade de caixa de correio CustomAttribute1.

```powershell
New-ComplianceSecurityFilter -FilterName MarketingFilter  -Users donh,suzanf -Filters "Mailbox_CustomAttribute1  -eq 'Marketing'" -Action Search
```

Este exemplo permite que os membros do grupo de função "Gerentes de Descoberta dos EUA" executem todas as ações de pesquisa de conteúdo apenas em caixas de correio nos Estados Unidos. O filtro usa o código de país numérico de três dígitos para os Estados Unidos da ISO 3166-1.
  
```powershell
New-ComplianceSecurityFilter -FilterName USDiscoveryManagers  -Users "US Discovery Managers" -Filters "Mailbox_CountryCode  -eq '840'" -Action All
```

Este exemplo permite que os membros do grupo de função Gerente de Descobertas Eletrônicos pesquisem apenas as caixas de correio de membros do grupo de distribuição Ottawa Users. O Get-DistributionGroup cmdlet no PowerShell do Exchange Online é usado para encontrar os membros do grupo Ottawa Users.
  
```powershell
$DG = Get-DistributionGroup "Ottawa Users"
```

```powershell
New-ComplianceSecurityFilter -FilterName DGFilter  -Users eDiscoveryManager -Filters "Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'" -Action Search
```

Este exemplo impede que qualquer usuário exclua o conteúdo de caixas de correio dos membros do grupo de distribuição Equipe Executiva. O Get-DistributionGroup cmdlet no PowerShell do Exchange Online é usado para encontrar os membros do grupo de equipe executiva.

```powershell
$DG = Get-DistributionGroup "Executive Team"
```

```powershell
New-ComplianceSecurityFilter -FilterName NoExecutivesPreview  -Users All -Filters "Mailbox_MemberOfGroup -ne '$($DG.DistinguishedName)'" -Action Purge
```

Este exemplo permite que os membros do grupo de função personalizado Gerentes de Descobertas Do OneDrive pesquisem apenas conteúdo em locais do OneDrive for Business na organização.

```powershell
New-ComplianceSecurityFilter -FilterName OneDriveOnly  -Users "OneDrive eDiscovery Managers" -Filters "Site_Path -like 'https://contoso-my.sharepoint.com/personal*'" -Action Search
```

> [!NOTE]
> Para restringir os usuários à pesquisa de sites específicos, use o  `Site_Path` filtro, conforme mostrado no exemplo anterior. O  `Site_Site` uso não funcionará. 
  
Este exemplo restringe o usuário a executar todas as ações de Pesquisa de Conteúdo somente em mensagens de email enviadas durante o ano de 2015.

```powershell
New-ComplianceSecurityFilter -FilterName EmailDateRestrictionFilter -Users donh@contoso.com -Filters "MailboxContent_Received -ge '01-01-2015' -and MailboxContent_Received -le '12-31-2015'" -Action All
```

Semelhante ao exemplo anterior, este exemplo restringe o usuário a executar todas as ações de pesquisa de conteúdo em documentos alterados pela última vez em algum ponto no ano de 2015.

```powershell
New-ComplianceSecurityFilter -FilterName DocumentDateRestrictionFilter -Users donh@contoso.com -Filters "SiteContent_LastModifiedTime -ge '01-01-2015' -and SiteContent_LastModifiedTime -le '12-31-2015'" -Action All
```

Este exemplo impede que os membros do grupo de funções "Gerentes de Descoberta do OneDrive" esgotam ações de pesquisa de conteúdo em qualquer caixa de correio na organização. 

```powershell
New-ComplianceSecurityFilter -FilterName NoEXO -Users "OneDrive Discovery Managers" -Filters "Mailbox_Alias -notlike '*'"  -Action All
```

Este exemplo impede que qualquer pessoa na organização procura mensagens de email enviadas ou recebidas por janets ou sarad.

```powershell
New-ComplianceSecurityFilter -FilterName NoSaraJanet -Users All -Filters "MailboxContent_Participants -notlike 'janets@contoso.onmicrosoft.com' -and MailboxContent_Participants -notlike 'sarad@contoso.onmicrosoft.com'" -Action Search
```

Este exemplo usa uma lista de filtros para combinar filtros de caixa de correio e de site.

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="get-compliancesecurityfilter"></a>Get-ComplianceSecurityFilter

O **Get-ComplianceSecurityFilter** é usado para retornar uma lista de filtros de permissões de pesquisa. Use o  _parâmetro FilterName_ para retornar informações para um filtro de pesquisa específico. 
  
## <a name="set-compliancesecurityfilter"></a>Set-ComplianceSecurityFilter

O **Set-ComplianceSecurityFilter** é usado para modificar um filtro de permissões de pesquisa existente. O único parâmetro necessário é  _FilterName_. 
  
|**Parâmetro**|**Descrição**|
|:-----|:-----|
| _Action_| O  _parâmetro Action_ especifica o tipo de ação de pesquisa ao qual o filtro é aplicado. As ações de pesquisa de conteúdo possíveis são: <br/><br/> **Exportar:** O filtro é aplicado ao exportar os resultados da pesquisa.  <br/> **Visualização:** O filtro é aplicado ao visualizar os resultados da pesquisa.  <br/> **Limpar:** O filtro é aplicado ao se purga os resultados da pesquisa.  <br/> **Pesquisa:** O filtro é aplicado ao executar uma pesquisa.  <br/> **Tudo:** O filtro é aplicado a todas as ações de pesquisa.  <br/> |
| _FilterName_|O  _parâmetro FilterName_ especifica o nome do filtro de permissões. |
| _Filtros_| O  _parâmetro Filters_ especifica os critérios de pesquisa para o filtro de segurança de conformidade. Você pode criar dois tipos diferentes de filtros: <br/><br/>**Filtragem de caixa de correio:** Esse tipo de filtro especifica as caixas de correio que os usuários atribuídos (especificado pelo  _parâmetro Users)_ podem pesquisar. A sintaxe para esse tipo de filtro é **Mailbox_** _MailboxPropertyName_, onde  _MailboxPropertyName_ especifica uma propriedade de caixa de correio usada para escopo as caixas de correio que podem ser pesquisadas. Por exemplo, o filtro de caixa de correio permitiria que o usuário atribuído a esse filtro pesquisasse somente as caixas de correio com o valor  `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` "OttawaUsers" na propriedade CustomAttribute10.  Qualquer propriedade de destinatário filtável com suporte pode ser usada para a _propriedade MailboxPropertyName._ Para uma lista de propriedades com suporte, consulte [Propriedades filtáveis para o parâmetro -RecipientFilter](https://go.microsoft.com/fwlink/p/?LinkId=784903). <br/><br/>**Filtragem de conteúdo de caixa de correio:** Esse tipo de filtro é aplicado ao conteúdo que pode ser pesquisado. Ele especifica o conteúdo da caixa de correio que os usuários atribuídos podem pesquisar. A sintaxe para esse tipo de filtro é **MailboxContent_** _SearchablePropertyName:value_, onde  _SearchablePropertyName_ especifica uma propriedade KQL (Keyword Query Language) que pode ser especificada em uma Pesquisa de Conteúdo. Por exemplo, o filtro de conteúdo de caixa de correio permitiria que o usuário atribuído a esse filtro pesquisasse apenas mensagens enviadas a destinatários no contoso.com  `MailboxContent_recipients:contoso.com` domínio.  Para uma lista de propriedades de mensagens pesquisáveis, consulte [Consultas de palavra-chave para Pesquisa de Conteúdo.](keyword-queries-and-search-conditions.md) <br/><br/>**Filtragem de conteúdo de site e site:** Há dois filtros relacionados ao site do SharePoint e do OneDrive for Business que você pode usar para especificar qual site ou conteúdo de site os usuários atribuídos podem pesquisar: <br/><br/>- **Site_** *SearchableSiteProperty* <br/>- **SiteContent** _ *SearchableSiteProperty*<br/><br/>Esses dois filtros são intercambiáveis. Por exemplo,  `"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` e retorna os mesmos  `"SiteContent_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` resultados. Mas para ajudá-lo a identificar o que um filtro faz, você pode usar para especificar propriedades relacionadas ao site (como uma URL do site) e para especificar propriedades relacionadas ao conteúdo (como tipos  `Site_`  `SiteContent_` de documento. Por exemplo, o filtro permitiria que o usuário atribuído a esse filtro pesquisasse  `"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` apenas o conteúdo no conjunto de https://contoso.spoppe.com/sites/doctors sites. O filtro permitiria que o usuário atribuído a esse filtro procurasse apenas documentos do  `"SiteContent_FileExtension -eq 'docx'"` Word (Word 2007 e posterior).  <br/><br/>Para uma lista de propriedades de site pesquisáveis, confira [Visão geral das propriedades rastreadas e gerenciadas no SharePoint.](https://go.microsoft.com/fwlink/p/?LinkId=331599) As propriedades marcadas com **Um** Sim **na coluna Queryable** podem ser usadas para criar um filtro de conteúdo de site ou site. <br/><br/>          |
| _Usuários_|O  _parâmetro Users_ especifica os usuários que têm esse filtro aplicado às suas Pesquisas de Conteúdo. Como esta é uma propriedade de vários valores, especificar um usuário ou grupo de usuários com esse parâmetro substitui a lista de usuários existente. Consulte os exemplos a seguir para a sintaxe para adicionar e remover usuários selecionados. <br/><br/>Você também pode usar o  _parâmetro Users_ para especificar um grupo de funções & Centro de Conformidade e Segurança. Isso permite que você crie um grupo de função personalizada e, em seguida, atribua esse grupo de função a um filtro de permissões de pesquisa. Por exemplo, digamos que você tenha um grupo de função personalizada para gerentes de Descoberta Eletrônica para a subsidiária americana de uma multinacional. Você pode usar o parâmetro  _Users_ para especificar esse grupo de função (usando a propriedade Name do grupo de função) e, em seguida, usar o parâmetro  _Filter_ para permitir que apenas caixas de correio nos EUA sejam pesquisadas. <br/><br/>Você não pode especificar um grupo de distribuição com esse parâmetro. |

## <a name="examples-of-changing-search-permissions-filters"></a>Exemplos de alteração de filtros de permissões de pesquisa

Estes exemplos mostram como usar os cmdlets **Get-ComplianceSecurityFilter** e **Set-ComplianceSecurityFilter** para adicionar ou remover um usuário à lista existente de usuários aos qual o filtro está atribuído. Quando você adiciona ou remove usuários de um filtro, especifique o usuário com o endereço SMTP correspondente. 
  
Este exemplo adiciona um usuário ao filtro.

```powershell
$filterusers = Get-ComplianceSecurityFilter -FilterName OttawaUsersFilter
```

```powershell
$filterusers.users.add("pilarp@contoso.com")
```

```powershell
Set-ComplianceSecurityFilter -FilterName OttawaUsersFilter -Users $filterusers.users
```

Este exemplo remove um usuário do filtro.

```powershell
$filterusers = Get-ComplianceSecurityFilter -FilterName OttawaUsersFilter
```

```powershell
$filterusers.users.remove("annb@contoso.com")
```

```powershell
Set-ComplianceSecurityFilter -FilterName OttawaUsersFilter -Users $filterusers.users
```

## <a name="remove-compliancesecurityfilter"></a>Remove-ComplianceSecurityFilter

O **Remove-ComplianceSecurityFilter** é usado para excluir um filtro de pesquisa. Use o  _parâmetro FilterName_ para especificar o filtro que você deseja excluir. 
  
## <a name="more-information"></a>Mais informações

- **Como funciona a filtragem de permissões de pesquisa?** O filtro de permissões é adicionado à consulta de pesquisa quando uma pesquisa de conteúdo é executada. O filtro de permissões é ingressado na consulta de pesquisa pelo **operador AND** Boolean. Por exemplo, você tem um filtro de permissões que permite que Bob execute todas as ações de pesquisa nas caixas de correio dos membros do grupo de distribuição Funcionários. Em seguida, Bob executa uma Pesquisa de Conteúdo em todas as caixas de correio na organização com a consulta de  `sender:jerry@adatum.com` pesquisa. Como o filtro de permissões e a consulta de pesquisa são logicamente combinados por um operador **AND,** a pesquisa retorna qualquer mensagem enviada por jerry@adatum.com a qualquer membro do grupo de distribuição Funcionários. 
    
- **O que acontece se você tiver vários filtros de permissões de pesquisa?** Em uma consulta de pesquisa de conteúdo, vários filtros de permissões são combinados por operadores boolianos **OU**. Dessa forma, os resultados serão retornados se qualquer um dos filtros for verdadeiro. Em uma pesquisa de conteúdo, todos os filtros (combinados por operadores **OU**) são combinados com a consulta de pesquisa pelo operador **E**. Vamos ver o exemplo anterior, em que um filtro de pesquisa permite que Bob pesquise apenas as caixas de correio dos membros do grupo de distribuição Funcionários. Em seguida, vamos criar outro filtro que impede que Paulo pesquise a caixa de correio do Pedro ("Mailbox_Alias -ne 'Pedro'"). E vamos supor também que Pedro seja membro do grupo Funcionários. Quando Bob executa uma Pesquisa de Conteúdo (do exemplo anterior) em todas as caixas de correio na organização, os resultados da pesquisa são retornados para a caixa de correio de Pedro, mesmo que você tenha aplicado filtro para impedir que Bob pesquise na caixa de correio de Pedro. Isso ocorre porque o primeiro filtro, que permite que Paulo pesquise no grupo Funcionários, é verdadeiro. Assim, como Pedro é um membro do grupo Funcionários, Paulo pode pesquisar na caixa de correio dele. 
    
- **A filtragem de permissões de pesquisa funciona para caixas de correio inativas?** Sim, você pode usar filtros de conteúdo de caixa de correio e caixa de correio para limitar quem pode pesquisar caixas de correio inativas em sua organização. Como uma caixa de correio normal, uma caixa de correio inativa deve ser configurada com a propriedade de destinatário usada para criar um filtro de permissões. Se necessário, você pode usar o comando **Get-Mailbox -InactiveMailboxOnly** para exibir as propriedades de caixas de correio inativas. Para saber mais, confira Criar e gerenciar caixas de correio [inativas no Office 365.](create-and-manage-inactive-mailboxes.md)
    
- **A filtragem de permissões de pesquisa funciona para pastas públicas?** Não. Conforme explicado anteriormente, a filtragem de permissões de pesquisa não pode ser usada para limitar quem pode pesquisar pastas públicas no Exchange. Por exemplo, os itens em locais de pastas públicas não podem ser excluídos dos resultados da pesquisa por um filtro de permissões. 
    
- **Permitir que um usuário pesquise todos os locais de conteúdo em um serviço específico também impede que ele pesquise locais de conteúdo em um serviço diferente?** Não. Conforme explicado anteriormente, você precisa criar um filtro de permissões de pesquisa para impedir explicitamente que os usuários pesquisem locais de conteúdo em um serviço específico (como impedir que um usuário pesquise em qualquer caixa de correio do Exchange ou em qualquer site do SharePoint). Em outras palavras, criar um filtro de permissões de pesquisa que permita que um usuário pesquise todos os sites do SharePoint na organização não impede que esse usuário pesquise caixas de correio. Por exemplo, para permitir que os administradores do SharePoint pesquisem apenas sites do SharePoint, você precisa criar um filtro que os impeça de pesquisar caixas de correio. Da mesma forma, para permitir que os administradores do Exchange pesquisem apenas caixas de correio, você precisa criar um filtro que os impeça de pesquisar sites.
