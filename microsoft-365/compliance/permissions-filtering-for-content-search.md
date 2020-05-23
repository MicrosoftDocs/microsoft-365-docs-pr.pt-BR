---
title: Configurar permissões de filtragem para a Pesquisa de Conteúdo
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
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
description: Use filtragem de permissões de pesquisa de conteúdo para permitir que um gerente de descoberta eletrônica pesquise somente um subconjunto de caixas de correio e sites em sua organização.
ms.openlocfilehash: 9628548b3cb2f6af5bedf7895a8714822731361f
ms.sourcegitcommit: 8d9509e617ede7cc5ba933c54fb9300d2d1c6344
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/22/2020
ms.locfileid: "44347780"
---
# <a name="configure-permissions-filtering-for-content-search"></a>Configurar permissões de filtragem para a Pesquisa de Conteúdo

Você pode usar a filtragem de permissões de pesquisa para permitir que um gerente de descoberta eletrônica pesquise somente um subconjunto de caixas de correio e sites em sua organização. Você também pode usar permissões de filtragem para que esse mesmo gerente de Descoberta Eletrônica procure somente o conteúdo da caixa de correio ou site que atende aos critérios de pesquisa específicos. Por exemplo, você pode permitir que um gerente de Descoberta Eletrônica pesquise apenas as caixas de correio de usuários em um local ou departamento específico. Para fazer isso, crie um filtro que use um filtro de destinatário com suporte para limitar as caixas de correio que um usuário ou grupo de usuários específico pode pesquisar. Você também pode criar um filtro que especifica o conteúdo da caixa de correio que um usuário pode pesquisar. Isso é feito criando um filtro que usa uma propriedade de mensagem pesquisável. Da mesma forma, você pode permitir que um gerente de descoberta eletrônica pesquise apenas sites específicos do SharePoint em sua organização. Você pode fazer isso criando um filtro que limita qual site pode ser pesquisado. Você também pode criar um filtro que especifica qual conteúdo de site pode ser pesquisado. Isso é feito criando um filtro que usa uma propriedade de site pesquisável.

Você também pode usar a filtragem de permissões de pesquisa para criar limites lógicos (chamados de *limites de conformidade*) dentro de uma organização que controlam os locais de conteúdo do usuário (como caixas de correio, sites do SharePoint e contas do onedrive) que os gerentes de descoberta eletrônica específicos podem pesquisar. Para obter mais informações, consulte [configurar limites de conformidade para investigações de descoberta eletrônica no Office 365](tagging-and-assessment-in-advanced-ediscovery.md).
  
A filtragem de permissões de pesquisa é suportada pelo recurso de pesquisa de conteúdo no centro de conformidade do & de segurança. Estes quatro cmdlets permitem que você configure e gerencie filtros de permissões de pesquisa:
  
[New-ComplianceSecurityFilter](#new-compliancesecurityfilter)

[Get-ComplianceSecurityFilter](#get-compliancesecurityfilter)

[Set-ComplianceSecurityFilter](#set-compliancesecurityfilter)

[Remove-ComplianceSecurityFilter](#remove-compliancesecurityfilter)

## <a name="before-you-begin"></a>Antes de começar

- Para executar os cmdlets de filtro de segurança de conformidade, você precisa ser membro do grupo de função gerenciamento da organização no centro de conformidade do & de segurança. Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).
    
- Você precisa conectar o Windows PowerShell ao centro de conformidade & segurança e à sua organização do Exchange Online para usar os cmdlets de filtro de segurança de conformidade. Isso é necessário porque esses cmdlets exigem acesso às propriedades da caixa de correio, que é o motivo pelo qual você precisa se conectar ao Exchange Online. Veja as etapas na próxima seção. 
    
- Consulte a seção [Mais informações](#more-information) para obter informações adicionais sobre os filtros de permissões de pesquisa. 
    
- A filtragem de permissões de pesquisa é aplicável a caixas de correio inativas, o que significa que você pode usar a filtragem de conteúdo da caixa de correio e caixa de correio para limitar quem pode pesquisar uma caixa de correio inativa Consulte a seção [mais informações](#more-information) para obter informações adicionais sobre filtragem de permissões e caixas de correio inativas. 
    
-  A filtragem de permissões de pesquisa não pode ser usada para limitar quem pode pesquisar pastas públicas no Exchange. 
    
- Não há limite para o número de filtros de permissões de pesquisa que podem ser criados em uma organização. Mas o desempenho da pesquisa será afetado quando houver mais de 100 filtros de permissões de pesquisa. Para manter o número de filtros de permissão de pesquisa em sua organização o menor possível, crie filtros que combinem regras para o Exchange, SharePoint e OneDrive em um único filtro sempre que possível.
    
## <a name="connect-to-the-security--compliance-center-and-exchange-online-in-a-single-remote-powershell-session"></a>Conectar-se ao centro de conformidade & segurança e ao Exchange Online em uma única sessão remota do PowerShell

1. Salve o seguinte texto em um arquivo de script do Windows PowerShell usando um sufixo de nome de arquivo **. ps1**. Por exemplo, você pode salvá-lo em um arquivo chamado **ConnectEXO-CC. ps1**.
    
    ```powershell
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -AllowClobber -DisableNameChecking
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. No computador local, abra o Windows PowerShell, vá para a pasta onde o script criado na etapa anterior está localizado e, em seguida, execute o script; por exemplo:
    
    ```powershell
    .\ConnectEXO-CC.ps1
    ```

Como saber se funcionou? Depois de executar o script, os cmdlets do centro de conformidade & segurança e do Exchange Online são importados para sua sessão local do Windows PowerShell. Se nenhum erro aparecer, a conexão terá sido estabelecida. Um teste rápido é executar um cmdlet do centro de conformidade de segurança & e um cmdlet do Exchange Online. Por exemplo, você pode executar **install-UnifiedCompliancePrerequisite** e **Get-Mailbox**. 
  
Caso você receba erros, verifique os seguintes requisitos:
  
- Um problema comum é uma senha incorreta. Execute as duas etapas novamente e preste muita atenção ao nome de usuário e à senha inseridos na Etapa 1.
    
- Verifique se sua conta tem permissão para acessar o centro de conformidade de & de segurança. Para obter detalhes, consulte [conceder aos usuários acesso ao centro de conformidade de & de segurança](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).
    
- Para ajudar a evitar ataques de negação de serviço (DoS), você está limitado a três conexões do PowerShell remoto abertas para o centro de conformidade & segurança.
    
- O Windows PowerShell deve ser configurado para executar scripts. Isso só precisa ser feito uma vez, não sempre que você se conecta. Para permitir que o Windows PowerShell execute scripts assinados, execute o seguinte comando em uma janela elevada do Windows PowerShell (uma janela do Windows PowerShell aberta com a seleção de **Executar como administrador**).

    ```powershell
    Set-ExecutionPolicy RemoteSigned
    ```

- O tráfego da porta TCP 80 precisa estar aberto entre seu computador local e o Office 365. Provavelmente ele está aberto, mas é algo a ser considerado caso a sua organização tenha uma política de acesso à Internet restritiva.

  
## <a name="new-compliancesecurityfilter"></a>New-ComplianceSecurityFilter

O **New-ComplianceSecurityFilter** é usado para criar um filtro de permissões de pesquisa. A tabela a seguir descreve os parâmetros para esse cmdlet. Todos os parâmetros são necessários para criar um filtro de segurança de conformidade. 
  
|**Parâmetro**|**Descrição**|
|:-----|:-----|
| _Action_ <br/> | O parâmetro _Action_ especifica o tipo de ação de pesquisa à qual o filtro é aplicado. As ações de pesquisa de conteúdo possíveis são:  <br/><br/> **Exportar:** O filtro é aplicado ao exportar os resultados da pesquisa.  <br/> **Visualização:** O filtro é aplicado durante a visualização dos resultados da pesquisa.  <br/> **Limpeza:** O filtro é aplicado ao limpar os resultados da pesquisa.  <br/> **Pesquisa:** O filtro é aplicado ao executar uma pesquisa.  <br/> **All:** O filtro é aplicado a todas as ações de pesquisa.  <br/> |
| _FilterName_ <br/> |O parâmetro _FilterName_ especifica o nome do filtro de permissões. Esse nome é usado para identificar um filtro ao usar os cmdlets **Get-ComplianceSecurityFilter**, **Set-ComplianceSecurityFilter,** e **Remove-ComplianceSecurityFilter**.  <br/> |
| _Filtros_ <br/> | O parâmetro _Filters_ especifica os critérios de pesquisa para o filtro de segurança de conformidade. Você pode criar três tipos diferentes de filtros:  <br/><br/> **Filtragem de caixa de correio:** Esse tipo de filtro especifica as caixas de correio que os usuários atribuídos (especificados pelo parâmetro _Users_ ) podem pesquisar. A sintaxe desse tipo de filtro é **Mailbox_** _MailboxPropertyName_, onde _MailboxPropertyName_ especifica uma propriedade de caixa de correio usada para fazer o escopo das caixas de correio que podem ser pesquisadas. Por exemplo, o filtro de caixa de correio `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` permitiria que o usuário atribuisse este filtro pesquise apenas as caixas de correio com o valor "OttawaUsers" na propriedade CustomAttribute10.  <br/>  Qualquer propriedade de destinatário filtrável com suporte pode ser usada para a propriedade _MailboxPropertyName_ . Para obter uma lista de propriedades com suporte, consulte [Filterable Properties for the-RecipientFilter Parameter](https://go.microsoft.com/fwlink/p/?LinkId=784903).  <br/><br/> **Filtragem de conteúdo de caixa de correio:** Esse tipo de filtro é aplicado ao conteúdo que pode ser pesquisado. Especifica o conteúdo da caixa de correio que os usuários atribuídos podem pesquisar. A sintaxe desse tipo de filtro é **MailboxContent_** _SearchablePropertyName: Value_, onde _SearchablePropertyName_ especifica uma propriedade da linguagem de consulta de palavra-chave (KQL) que pode ser especificada em uma pesquisa de conteúdo. Por exemplo, o filtro de conteúdo de caixa de correio `MailboxContent_recipients:contoso.com` permitiria que o usuário atribuisse esse filtro apenas pesquisasse mensagens enviadas a destinatários no domínio contoso.com.  <br/>  Para obter uma lista das propriedades de mensagem pesquisáveis, Confira as [consultas de palavras-chave e condições de pesquisa para pesquisa de conteúdo](keyword-queries-and-search-conditions.md). <br/> <br/> **Importante:**  Um único filtro de pesquisa não pode conter um filtro de caixa de correio e um filtro de conteúdo de caixa de correio. Para combiná-los em um único filtro, você precisa usar uma [lista de filtros](#using-a-filters-list-to-combine-filter-types).  Mas um filtro pode conter uma consulta mais complexa do mesmo tipo. Por exemplo,  `"Mailbox_CustomAttribute10 -eq 'FTE' -and Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'"`  <br/><br/> **Filtragem de conteúdo de site e site:** Há dois filtros relacionados a sites do SharePoint e do OneDrive for Business que você pode usar para especificar o conteúdo do site ou site que os usuários atribuídos podem pesquisar:  <br/><br/> - **Site_** _SearchableSiteProperty_ <br/> - **SiteContent_** _SearchableSiteProperty_ <br/><br/>  Esses dois filtros são intercambiáveis. Por exemplo, `"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` e `"SiteContent_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` retornar os mesmos resultados. Mas para ajudá-lo a identificar o que um filtro faz, você pode usar `Site_` para especificar propriedades relacionadas a sites (como uma URL de site) e `SiteContent_` para especificar propriedades relacionadas a conteúdo (como tipos de documento. Por exemplo, o filtro `"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` permitiria que o usuário atribuisse esse filtro apenas pesquisasse conteúdo no https://contoso.sharepoint.com/sites/doctors conjunto de sites. O filtro `"SiteContent_FileExtension -eq 'docx'"` permitiria que o usuário atribuisse este filtro apenas pesquise documentos do Word (Word 2007 e posterior).  <br/><br/>  Para obter uma lista de propriedades de site pesquisáveis, confira [visão geral das propriedades rastreadas e gerenciadas no SharePoint](https://go.microsoft.com/fwlink/p/?LinkId=331599). As propriedades marcadas com um **Sim** na coluna **consultável** podem ser usadas para criar um filtro de conteúdo do site ou site.  <br/><br/> **Importante:** Você precisa criar um filtro de permissões de pesquisa para impedir explicitamente que os usuários pesquisem locais de conteúdo em um serviço específico (como impedir que um usuário pesquise qualquer caixa de correio do Exchange ou qualquer site do SharePoint). Em outras palavras, a criação de um filtro de permissões de pesquisa que permite a um usuário Pesquisar todos os sites do SharePoint na organização não impede que o usuário pesquise caixas de correio. Por exemplo, para permitir que os administradores do SharePoint pesquisem apenas sites do SharePoint, você precisa criar um filtro que impeça que eles pesquisem caixas de correio. Da mesma forma, para permitir que administradores do Exchange pesquisem apenas as caixas de correio, você precisa criar um filtro que impeça que eles pesquisem sites.           |
| _Usuários_ <br/> |O parâmetro _Users_ especifica os usuários que recebem esse filtro aplicado às suas pesquisas de conteúdo. Identifica os usuários por seus alias ou endereço SMTP principal. Você pode especificar vários valores separados por vírgulas ou pode atribuir o filtro a todos os usuários usando o valor **All**.  <br/> Você também pode usar o parâmetro _Users_ para especificar um grupo de funções do centro de conformidade de & de segurança. Isso permite que você crie um grupo de função personalizada e, em seguida, atribua esse grupo de função a um filtro de permissões de pesquisa. Por exemplo, digamos que você tenha um grupo de função personalizada para gerentes de Descoberta Eletrônica para a subsidiária americana de uma multinacional. Você pode usar o parâmetro _Users_ para especificar esse grupo de função (usando a propriedade Name do grupo de função) e, em seguida, usar o parâmetro _Filter_ para permitir que apenas caixas de correio nos EUA sejam pesquisadas.  <br/> Você não pode especificar um grupo de distribuição com esse parâmetro.  <br/> |
   
### <a name="using-a-filters-list-to-combine-filter-types"></a>Usando uma lista de filtros para combinar tipos de filtro

Uma *lista de filtros* é um filtro que inclui um filtro de caixa de correio e um filtro de site separado por uma vírgula. O uso de uma lista de filtros é o único método com suporte para combinar diferentes tipos de filtros. No exemplo a seguir, observe que uma vírgula separa os filtros de **caixa de correio** e de **site** :

```powershell
-Filters "Mailbox_CustomAttribute10 -eq 'OttawaUsers'", "Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"
```

Quando um filtro que contém uma lista de filtros é processado durante a execução de uma pesquisa de conteúdo, dois filtros de permissão de pesquisa são criados a partir da lista de filtros: um para cada filtro separado por uma vírgula. Portanto, no exemplo anterior, um filtro de permissões de pesquisa de caixa de correio e um filtro de permissões de pesquisa de site será criado. 

Uma alternativa ao uso de uma lista de filtros seria criar dois filtros de permissões de pesquisa separados. Portanto, no exemplo anterior, crie um filtro para o atributo de caixa de correio e um filtro para o atributo de site. Em ambos os casos, os resultados são os mesmos. O uso de uma lista de filtros ou a criação de filtros de permissões de pesquisa separados é uma questão de preferência.

Tenha em mente as seguintes coisas em relação ao uso de uma lista de filtros:

- Você precisa usar uma lista de filtros para criar um filtro que inclua um filtro de **caixa de correio** e um filtro do **MailboxContent** . 

- Como sugerido anteriormente, você não precisa usar uma lista de filtros para incluir um **site** e um filtro do **SiteContent** em um único filtro de permissões de pesquisa. Por exemplo, você pode combinar os filtros **site** e **SiteContent** usando um operador **or** .

   ```powershell
   -Filters "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"
   ```

- Cada componente de uma lista de filtros pode conter uma sintaxe de filtro complexa. Por exemplo, os filtros de caixa de correio e de site podem conter vários filtros separados por um **ou** um operador:

   ```powershell
   -Filters "Mailbox_Department -eq 'CohoWinery' -or Mailbox_CustomAttribute10 -eq 'CohoUsers'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'"
   ```

## <a name="examples-of-creating-search-permissions-filters"></a>Exemplos de criação de filtros de permissão de pesquisa

Estes são exemplos de como usar o cmdlet **New-ComplianceSecurityFilter** para criar um filtro de permissões de pesquisa. 
  
Este exemplo permite que o usuário annb@contoso.com execute todas as ações de pesquisa de conteúdo somente para caixas de correio no Canadá. O filtro usa o código de país numérico de três dígitos para o Canadá da ISO 3166-1.

```powershell
New-ComplianceSecurityFilter -FilterName CountryFilter  -Users annb@contoso.com -Filters "Mailbox_CountryCode  -eq '124'" -Action All
```

Este exemplo permite que os usuários do viniciusm e do clarab pesquisem apenas as caixas de correio que têm o valor "marketing" para a propriedade de caixa de correio CustomAttribute1.

```powershell
New-ComplianceSecurityFilter -FilterName MarketingFilter  -Users donh,suzanf -Filters "Mailbox_CustomAttribute1  -eq 'Marketing'" -Action Search
```

Este exemplo permite que os membros do grupo de função "Gerentes de Descoberta dos EUA" executem todas as ações de pesquisa de conteúdo apenas em caixas de correio nos Estados Unidos. O filtro usa o código de país numérico de três dígitos para os Estados Unidos da ISO 3166-1.
  
```powershell
New-ComplianceSecurityFilter -FilterName USDiscoveryManagers  -Users "US Discovery Managers" -Filters "Mailbox_CountryCode  -eq '840'" -Action All
```

Este exemplo permite que os membros do grupo de função Gerenciador de descoberta eletrônica pesquisem apenas as caixas de correio dos membros do grupo de distribuição usuários do Ottawa. O cmdlet Get-Distribution no PowerShell do Exchange Online é usado para localizar os membros do grupo usuários do Ottawa.
  
```powershell
$DG = Get-DistributionGroup "Ottawa Users"
```

```powershell
New-ComplianceSecurityFilter -FilterName DGFilter  -Users eDiscoveryManager -Filters "Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'" -Action Search
```

Este exemplo impede que qualquer usuário exclua o conteúdo de caixas de correio dos membros do grupo de distribuição Equipe Executiva. O cmdlet Get-Distribution no PowerShell do Exchange Online é usado para localizar os membros do grupo de equipe executivo.

```powershell
$DG = Get-DistributionGroup "Executive Team"
```

```powershell
New-ComplianceSecurityFilter -FilterName NoExecutivesPreview  -Users All -Filters "Mailbox_MemberOfGroup -ne '$($DG.DistinguishedName)'" -Action Purge
```

Este exemplo permite que os membros do grupo de função personalizado gerentes de descoberta eletrônica do OneDrive pesquisem apenas o conteúdo em locais do OneDrive for Business na organização.

```powershell
New-ComplianceSecurityFilter -FilterName OneDriveOnly  -Users "OneDrive eDiscovery Managers" -Filters "Site_Path -like 'https://contoso-my.sharepoint.com/personal*'" -Action Search
```

> [!NOTE]
> Para restringir os usuários a pesquisarem sites específicos, use o filtro `Site_Path` , conforme mostrado no exemplo anterior. O uso do `Site_Site` não funcionará. 
  
Este exemplo restringe o usuário a executar todas as ações de Pesquisa de Conteúdo somente em mensagens de email enviadas durante o ano de 2015.

```powershell
New-ComplianceSecurityFilter -FilterName EmailDateRestrictionFilter -Users donh@contoso.com -Filters "MailboxContent_Received -ge '01-01-2015' -and MailboxContent_Received -le '12-31-2015'" -Action All
```

Semelhante ao exemplo anterior, este exemplo restringe o usuário a executar todas as ações de pesquisa de conteúdo em documentos alterados pela última vez em algum ponto no ano de 2015.

```powershell
New-ComplianceSecurityFilter -FilterName DocumentDateRestrictionFilter -Users donh@contoso.com -Filters "SiteContent_LastModifiedTime -ge '01-01-2015' -and SiteContent_LastModifiedTime -le '12-31-2015'" -Action All
```

Este exemplo impede que os membros do grupo de função "gerentes de descoberta do OneDrive" executem ações de pesquisa de conteúdo em qualquer caixa de correio na organização. 

```powershell
New-ComplianceSecurityFilter -FilterName NoEXO -Users "OneDrive Discovery Managers" -Filters "Mailbox_Alias -notlike '*'"  -Action All
```

Este exemplo impede que qualquer pessoa na organização pesquise mensagens de email que foram enviadas ou recebidas por janets ou transmitidas.

```powershell
New-ComplianceSecurityFilter -FilterName NoSaraJanet -Users All -Filters "MailboxContent_Participants -notlike 'janets@contoso.onmicrosoft.com' -and MailboxContent_Participants -notlike 'sarad@contoso.onmicrosoft.com'" -Action Search
```

Este exemplo usa uma lista de filtros para combinar filtros de caixa de correio e de site.

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="get-compliancesecurityfilter"></a>Get-ComplianceSecurityFilter

O **Get-ComplianceSecurityFilter** é usado para retornar uma lista de filtros de permissão de pesquisa. Use o parâmetro _FilterName_ para retornar informações de um filtro de pesquisa específico. 
  
## <a name="set-compliancesecurityfilter"></a>Set-ComplianceSecurityFilter

O **set-ComplianceSecurityFilter** é usado para modificar um filtro de permissões de pesquisa existente. O único parâmetro Required é _FilterName_. 
  
|**Parâmetro**|**Descrição**|
|:-----|:-----|
| _Action_| O parâmetro _Action_ especifica o tipo de ação de pesquisa à qual o filtro é aplicado. As ações de pesquisa de conteúdo possíveis são: <br/><br/> **Exportar:** O filtro é aplicado ao exportar os resultados da pesquisa.  <br/> **Visualização:** O filtro é aplicado durante a visualização dos resultados da pesquisa.  <br/> **Limpeza:** O filtro é aplicado ao limpar os resultados da pesquisa.  <br/> **Pesquisa:** O filtro é aplicado ao executar uma pesquisa.  <br/> **All:** O filtro é aplicado a todas as ações de pesquisa.  <br/> |
| _FilterName_|O parâmetro _FilterName_ especifica o nome do filtro de permissões. |
| _Filtros_| O parâmetro _Filters_ especifica os critérios de pesquisa para o filtro de segurança de conformidade. Você pode criar dois tipos diferentes de filtros: <br/><br/>**Filtragem de caixa de correio:** Esse tipo de filtro especifica as caixas de correio que os usuários atribuídos (especificados pelo parâmetro _Users_ ) podem pesquisar. A sintaxe desse tipo de filtro é **Mailbox_** _MailboxPropertyName_, onde _MailboxPropertyName_ especifica uma propriedade de caixa de correio usada para fazer o escopo das caixas de correio que podem ser pesquisadas. Por exemplo, o filtro de caixa de correio `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` permitiria que o usuário atribuisse este filtro pesquise apenas as caixas de correio com o valor "OttawaUsers" na propriedade CustomAttribute10.  Qualquer propriedade de destinatário filtrável com suporte pode ser usada para a propriedade _MailboxPropertyName_ . Para obter uma lista de propriedades com suporte, consulte [Filterable Properties for the-RecipientFilter Parameter](https://go.microsoft.com/fwlink/p/?LinkId=784903). <br/><br/>**Filtragem de conteúdo de caixa de correio:** Esse tipo de filtro é aplicado ao conteúdo que pode ser pesquisado. Especifica o conteúdo da caixa de correio que os usuários atribuídos podem pesquisar. A sintaxe desse tipo de filtro é **MailboxContent_** _SearchablePropertyName: Value_, onde _SearchablePropertyName_ especifica uma propriedade da linguagem de consulta de palavra-chave (KQL) que pode ser especificada em uma pesquisa de conteúdo. Por exemplo, o filtro de conteúdo de caixa de correio `MailboxContent_recipients:contoso.com` permitiria que o usuário atribuisse esse filtro apenas pesquisasse mensagens enviadas a destinatários no domínio contoso.com.  Para obter uma lista das propriedades de mensagem pesquisáveis, consulte [keyword queries for Content Search](keyword-queries-and-search-conditions.md). <br/><br/>**Filtragem de conteúdo de site e site:** Há dois filtros relacionados a sites do SharePoint e do OneDrive for Business que você pode usar para especificar o conteúdo do site ou site que os usuários atribuídos podem pesquisar: <br/><br/>- **Site_** *SearchableSiteProperty* <br/>- **SiteContent**_*SearchableSiteProperty*<br/><br/>Esses dois filtros são intercambiáveis. Por exemplo, `"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` e `"SiteContent_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` retorna os mesmos resultados. Mas para ajudá-lo a identificar o que um filtro faz, você pode usar `Site_` para especificar propriedades relacionadas a sites (como uma URL de site) e `SiteContent_` para especificar propriedades relacionadas a conteúdo (como tipos de documento. Por exemplo, o filtro `"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` permitiria que o usuário atribuisse esse filtro apenas pesquisasse conteúdo no https://contoso.spoppe.com/sites/doctors conjunto de sites. O filtro `"SiteContent_FileExtension -eq 'docx'"` permitiria que o usuário atribuisse este filtro apenas pesquise documentos do Word (Word 2007 e posterior).  <br/><br/>Para obter uma lista de propriedades de site pesquisáveis, confira [visão geral das propriedades rastreadas e gerenciadas no SharePoint](https://go.microsoft.com/fwlink/p/?LinkId=331599). As propriedades marcadas com um **Sim** na coluna **consultável** podem ser usadas para criar um filtro de conteúdo do site ou site. <br/><br/>          |
| _Usuários_|O parâmetro _Users_ especifica os usuários que recebem esse filtro aplicado às suas pesquisas de conteúdo. Como esta é uma propriedade de vários valores, a especificação de um usuário ou grupo de usuários com esse parâmetro substitui a lista existente de usuários. Consulte os exemplos a seguir para obter a sintaxe para adicionar e remover usuários selecionados. <br/><br/>Você também pode usar o parâmetro _Users_ para especificar um grupo de funções do centro de conformidade de & de segurança. Isso permite que você crie um grupo de função personalizada e, em seguida, atribua esse grupo de função a um filtro de permissões de pesquisa. Por exemplo, digamos que você tenha um grupo de função personalizada para gerentes de Descoberta Eletrônica para a subsidiária americana de uma multinacional. Você pode usar o parâmetro _Users_ para especificar esse grupo de função (usando a propriedade Name do grupo de função) e, em seguida, usar o parâmetro _Filter_ para permitir que apenas caixas de correio nos EUA sejam pesquisadas. <br/><br/>Você não pode especificar um grupo de distribuição com esse parâmetro. |

## <a name="examples-of-changing-search-permissions-filters"></a>Exemplos de alteração de filtros de permissão de pesquisa

Estes exemplos mostram como usar os cmdlets **Get-ComplianceSecurityFilter** e **set-ComplianceSecurityFilter** para adicionar ou remover um usuário à lista existente de usuários aos quais o filtro é atribuído. Quando você adiciona ou remove usuários de um filtro, especifique o usuário com o endereço SMTP correspondente. 
  
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

O **Remove-ComplianceSecurityFilter** é usado para excluir um filtro de pesquisa. Use o parâmetro _FilterName_ para especificar o filtro que você deseja excluir. 
  
## <a name="more-information"></a>Mais informações

- **Como funciona a filtragem de permissões de pesquisa?** O filtro de permissões é adicionado à consulta de pesquisa quando uma pesquisa de conteúdo é executada. O filtro de permissões é associado à consulta de pesquisa pelo **operador Boolean.** Por exemplo, você tem um filtro de permissões que permite que Bob realize todas as ações de pesquisa nas caixas de correio dos membros do grupo de distribuição funcionários. Em seguida, Bob executa uma pesquisa de conteúdo em todas as caixas de correio da organização com a consulta de pesquisa `sender:jerry@adatum.com` . Como o filtro de permissões e a consulta de pesquisa são logicamente combinados por um operador **and** , a pesquisa retorna qualquer mensagem enviada por Jerry@adatum.com para qualquer membro do grupo de distribuição funcionários. 
    
- **O que acontece se você tiver vários filtros de permissões de pesquisa?** Em uma consulta de pesquisa de conteúdo, vários filtros de permissões são combinados por operadores boolianos **OU**. Dessa forma, os resultados serão retornados se qualquer um dos filtros for verdadeiro. Em uma pesquisa de conteúdo, todos os filtros (combinados por operadores **OU**) são combinados com a consulta de pesquisa pelo operador **E**. Vamos executar o exemplo anterior, em que um filtro de pesquisa permite que Bob pesquise apenas as caixas de correio dos membros do grupo de distribuição funcionários. Em seguida, vamos criar outro filtro que impede que Paulo pesquise a caixa de correio do Pedro ("Mailbox_Alias -ne 'Pedro'"). E vamos supor também que Pedro seja membro do grupo Funcionários. Quando Bob executa uma pesquisa de conteúdo (do exemplo anterior) em todas as caixas de correio na organização, os resultados da pesquisa são retornados para a caixa de correio de Phil, mesmo que você tenha aplicado o filtro para impedir que Bob pesquise a caixa de correio de Phil. Isso ocorre porque o primeiro filtro, que permite que Paulo pesquise no grupo Funcionários, é verdadeiro. Assim, como Pedro é um membro do grupo Funcionários, Paulo pode pesquisar na caixa de correio dele. 
    
- **A filtragem de permissões de pesquisa funciona para caixas de correio inativas?** Sim, você pode usar os filtros de conteúdo de caixa de correio e caixa de correio para limitar quem pode pesquisar caixas de correio inativas em sua organização. Como uma caixa de correio comum, uma caixa de correio inativa deve ser configurada com a propriedade Recipient que é usada para criar um filtro de permissões. Se necessário, você pode usar o comando **Get-Mailbox-InactiveMailboxOnly** para exibir as propriedades de caixas de correio inativas. Para obter mais informações, consulte [criar e gerenciar caixas de correio inativas no Office 365](create-and-manage-inactive-mailboxes.md).
    
- **A filtragem de permissões de pesquisa funciona para pastas públicas?** Não. Como explicado anteriormente, a filtragem de permissões de pesquisa não pode ser usada para limitar quem pode pesquisar pastas públicas no Exchange. Por exemplo, os itens em locais de pasta pública não podem ser excluídos dos resultados da pesquisa por um filtro de permissões. 
    
- **Permitir que um usuário Pesquise todos os locais de conteúdo em um serviço específico também impede que eles pesquisem locais de conteúdo em um serviço diferente?** Não. Como explicado anteriormente, você precisa criar um filtro de permissões de pesquisa para impedir explicitamente que os usuários pesquisem locais de conteúdo em um serviço específico (como impedir que um usuário pesquise qualquer caixa de correio do Exchange ou qualquer site do SharePoint). Em outras palavras, a criação de um filtro de permissões de pesquisa que permite a um usuário Pesquisar todos os sites do SharePoint na organização não impede que o usuário pesquise caixas de correio. Por exemplo, para permitir que os administradores do SharePoint pesquisem apenas sites do SharePoint, você precisa criar um filtro que impeça que eles pesquisem caixas de correio. Da mesma forma, para permitir que administradores do Exchange pesquisem apenas as caixas de correio, você precisa criar um filtro que impeça que eles pesquisem sites.
