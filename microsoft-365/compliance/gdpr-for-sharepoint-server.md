---
title: RGPD para SharePoint Server
description: Aprenda a resolver Regulamentações Gerais de Proteção de Dados (RGPD) para o SharePoint Server local.
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
titleSuffix: Microsoft GDPR
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 58ddbe98ec5ca6b08e6d6be58c4258265c13e3de
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036224"
---
# <a name="gdpr-for-sharepoint-server"></a>RGPD para SharePoint Server

Aplicável a:
- SharePoint Server 2013
- SharePoint Server 2016
- SharePoint Server 2019

Como parte da proteção de informações pessoais, recomendamos o seguinte:

-   Classifique seus dados usando a Proteção de Informações do Azure.

-   Execute o SharePoint Server em uma configuração de privilégios mínimos. Consulte [Planejamento para administração de privilégios mínimos no SharePoint Server](https://docs.microsoft.com/SharePoint/security-for-sharepoint-server/plan-for-least-privileged-administration) e [Segurança para o SharePoint Server](https://docs.microsoft.com/sharepoint/security-for-sharepoint-server/security-for-sharepoint-server) para saber mais.

-   [Habilite a criptografia BitLocker em seus servidores](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-how-to-deploy-on-windows-server).

## <a name="user-generated-content"></a>Conteúdo gerado pelo usuário

A abordagem básica recomendada para o conteúdo gerado pelo usuário em sites e bibliotecas do SharePoint Server é a seguinte:

-   Use a Proteção de Informações do Azure para identificar os dados confidenciais.

-   Use a [Pesquisa do SharePoint Server](https://docs.microsoft.com/SharePoint/search/search) e a [Descoberta Eletrônica](https://docs.microsoft.com/SharePoint/governance/ediscovery-and-in-place-holds-in-sharepoint-server) para recuperar dados confidenciais.

A abordagem recomendada para compartilhamentos de arquivos e sites do SharePoint inclui estas etapas:

1.  **[Instale e configure o verificador da Proteção de Informações do Azure.](https://docs.microsoft.com/azure/information-protection/rms-client/client-admin-guide-install#options-to-install-the-azure-information-protection-client-for-users)**

    -   Decida quais tipos de dados confidenciais usar.

    -   Especifique quais sites do SharePoint usar.

2.  **Execute um ciclo de descoberta**.

    -   Execute o verificador no modo de descoberta e valide os resultados.

    -   Se necessário, otimize as condições e os tipos de informações confidenciais.

    -   Avalie o impacto esperado de aplicar rótulos automaticamente.

3.  **Execute o verificador da Proteção de Informações do Azure para aplicar rótulos a documentos qualificados**.

4.  **Para a proteção:**

    a. Configure regras de prevenção contra a perda de dados do Exchange para proteger documentos com o rótulo desejado.

    b. Certifique-se de usar permissões para limitar quem pode acessar os arquivos.

    c. Para o SharePoint, use a proteção de IRM para bibliotecas.

5.  **Para monitorar, integre os logs do Windows Server com uma ferramenta SIEM.**

    a. Para localizar dados pessoais para solicitações de titulares de dados, use o Centro de Pesquisa ou a Descoberta Eletrônica.

Ao aplicar rótulos em dados confidenciais, certifique-se de usar um rótulo que não esteja configurado com proteção. Isso inclui criptografia que impeça que os serviços detectem dados confidenciais nos arquivos.

Saiba mais sobre como usar o verificador da Proteção de Informações do Azure para localizar e rotular dados pessoais no [Microsoft GDPR Data Discovery Toolkit](https://aka.ms/gdprpartners) (https://aka.ms/gdprpartners).

Consulte informações sobre como configurar o verificador para analisar condições e os tipos de informações confidenciais para prevenção contra perda de dados (DLP) do Office 365 em [Como configurar as condições de classificação automática e recomendada para a Proteção de Informações do Azure](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-classification). Observe que os novos tipos de informações confidenciais do Office 365 não estarão disponíveis imediatamente para usar com o verificador e tipos de informações confidenciais personalizados não podem ser usados com o verificador.

## <a name="removing-personal-information-from-office-files"></a>Remover informações pessoais de arquivos do Office

A remoção de informações pessoais (como metadados ou comentários em um documento do Word) de arquivos do Office que estão armazenados em uma biblioteca de documentos do SharePoint deve ser feita manualmente. Siga estas etapas:

1.  Baixe uma cópia do documento do SharePoint Server para seu disco local.

2.  Exclua o documento da biblioteca de documentos do SharePoint.

3.  Siga as etapas em [Remover dados ocultos e informações pessoais ao inspecionar documentos](https://support.office.com/article/356B7B5D-77AF-44FE-A07F-9AA4D085966F).

4.  Reenvie o documento para a biblioteca de documentos do SharePoint.

## <a name="telemetry-and-log-files"></a>Telemetria e arquivos de log

### <a name="uls-logs"></a>Logs do ULS

O Serviço de Log Unificado (ULS) e o Log de uso no SharePoint Server acompanham diversas funções de sistema e podem conter informações do usuário. Logs do ULS e logs de uso são arquivos de texto e podem ser pesquisados usando diversas ferramentas de pesquisa. O [cmdlet Merge-SPLogFile do PowerShell](https://docs.microsoft.com/powershell/module/sharepoint-server/merge-splogfile) fornece uma maneira de retornar os registros dos logs do ULS em vários servidores de um farm.

Considere configurar as políticas de retenção de logs para o valor mínimo necessário para seus objetivos de negócios. Consulte informações sobre como configurar o registro em log no SharePoint Server em [Configurar o registro de diagnóstico no SharePoint Server](https://docs.microsoft.com/SharePoint/administration/configure-diagnostic-logging).

Observe que alguns eventos de sistema também são registrados no Log de eventos do Windows.

### <a name="usage-database"></a>Banco de dados de uso

O banco de dados de uso do SharePoint Server (nome padrão WSS_Logging) contém um subconjunto das informações encontradas nos logs do ULS. A retenção máxima dos dados nesse banco de dados é de 30 dias. Recomendamos que você defina essa configuração para a menor duração permitida por suas necessidades de negócios. Para saber mais, consulte [Configurar o registro de diagnóstico no SharePoint Server](https://docs.microsoft.com/SharePoint/administration/configure-diagnostic-logging).

## <a name="personal-information-and-search"></a>Informações pessoais e pesquisa

Os registros de uso e de histórico de consultas de pesquisa contêm referências a nomes de usuários.

### <a name="query-history-and-favorite-queries"></a>Histórico de consultas e consultas favoritas

No SharePoint Server, históricos de consultas e consultas "favoritas" expiram automaticamente após 365 dias. Quando um usuário deixa sua organização, é possível remover referências ao nome dele do histórico de consultas usando as etapas abaixo.

As consultas SQL a seguir aplicam-se ao SharePoint Server e permitem:

-   Exportar o histórico de consultas ou as consultas favoritas de um usuário

-   Remover referências a nomes de usuários do histórico de consultas

#### <a name="export-a-users-queries-since-a-specific-date"></a>Exportar as consultas de um usuário desde uma data específica 

Use o procedimento a seguir para exportar as consultas das tabelas de logs de consulta Link Store, executada por @UserName desde @StartTime.

```sql
[In dbo].[LinkStore_<ID>]:
CREATE PROCEDURE proc_MSS_GetQueryTermsForUser 
( 
    @UserName nvarchar(256), 
    @StartTime datetime 
) 
AS 
BEGIN 
    SET NOCOUNT ON; 
    SELECT searchTime, queryString 
    FROM 
        dbo.MSSQLogPageImpressionQuery 
    WITH 
        (NOLOCK) 
    WHERE 
        userName = @UserName AND 
        searchTime > @StartTime 
END 
GO 
```

#### <a name="export-a-users-queries-from-the-past-100-days"></a>Exportar as consultas dos últimos 100 dias para um usuário

```sql
DECLARE @FROMDATE datetime 
SET @FROMDATE = DATEADD(day, -100, GETUTCDATE()) 
EXECUTE proc_MSS_GetQueryTermsForUser '0#.w|domain\username', @FROMDATE 
```

#### <a name="export-a-users-favorite-queries"></a>Exportar as consultas favoritas de um usuário

Use o procedimento a seguir para exportar as consultas favoritas de um usuário das tabelas de resultado pessoal do banco de dados Search Admin, executadas por @UserName, desde <DateTime>.

```sql
In [dbo].[Search_<ID>]:
CREATE PROCEDURE proc_MSS_GetPersonalFavoriteQueries 
( 
    @UserName nvarchar(256), 
    @SearchTime datetime 
) 
AS 
BEGIN 
    SET NOCOUNT ON; 
    SELECT max(queries.SearchTime) as SearchTime, 
           max(queries.querystring) as queryString, 
           max(url.url) as URL 
    FROM MSSQLogOwner owners WITH(NOLOCK) 
    JOIN MSSQLogPersonalResults results WITH(NOLOCK) on owners.OwnerId = results.OwnerId 
    JOIN MSSQLogUrl url WITH(NOLOCK) on results.ClickedUrlId = url.urlId 
    JOIN MSSQLogPersonalQueries queries WITH(NOLOCK) on results.OwnerId = queries.OwnerId 
    WHERE queries.SearchTime > @SearchTime 
        AND queries.UserName = @UserName 
        GROUP BY queries.QueryString,url.url 
END 
GO 
```

#### <a name="export-a-users-favorite-queries-from-the-past-100-days"></a>Exportar as consultas favoritas dos últimos 100 dias para um usuário 

```sql
DECLARE @FROMDATE datetime 
SET @FROMDATE = DATEADD(day, -100, GETUTCDATE()) 
EXECUTE proc_MSS_GetPersonalFavoriteQueries '0#.w|domain\username', @FROMDATE 
```

#### <a name="remove-references-to-user-names-that-are-more-than-x-days-old"></a>Remover referências a nomes de usuários com mais de X dias

Use o procedimento a seguir para remover as referências a *todos* os nomes de usuários que têm mais do que @Days das tabelas de log de consultas Links Store. O procedimento removerá apenas as referências anteriores ao momento atual até atingir o @LastCleanupTime.

```sql
In [dbo].[LinksStore_<ID>]:  
CREATE PROCEDURE proc_MSS_QLog_Cleanup_Users 
( 
    @LastCleanupTime datetime, 
    @Days int 
) 
AS 
BEGIN 
    DECLARE @TooOld datetime 
    SET @TooOld = DATEADD(day, -@Days, GETUTCDATE()) 
    DECLARE @FromLast datetime 
    SET @FromLast = DATEADD(day, -@Days, @LastCleanupTime) 
    BEGIN TRANSACTION 
         UPDATE MSSQLogPageImpressionQuery 
    SET userName = 'NA' 
    WHERE @FromLast <= searchTime AND searchTime < @TooOld 
    UPDATE MSSQLogO14PageClick 
    SET userName = 'NA' 
    WHERE @FromLast <= searchTime AND searchTime < @TooOld 
    COMMIT TRANSACTION 
END 
GO 
```

#### <a name="remove-references-to-a-specific-user-name-thats-more-than-x-days-old"></a>Remover referências a um nome de usuário específico com mais de X dias

Use o procedimento a seguir para remover as referências a um nome de usuário *específico* das tabelas de log de consultas Links Store, onde as referências têm mais de @Days. O procedimento removerá apenas as referências anteriores ao momento atual até atingir o @LastCleanupTime.

```sql
In [dbo].[LinksStore_<ID>]:
CREATE PROCEDURE proc_MSS_QLog_Cleanup_Users 
( 
    @UserName nvarchar(256),
    @LastCleanupTime datetime, 
    @Days int 
) 
AS 
BEGIN 
    DECLARE @TooOld datetime 
    SET @TooOld = DATEADD(day, -@Days, GETUTCDATE()) 
    DECLARE @FromLast datetime 
    SET @FromLast = DATEADD(day, -@Days, @LastCleanupTime) 
    BEGIN TRANSACTION 
         UPDATE MSSQLogPageImpressionQuery 
    SET userName = 'NA' 
    WHERE @FromLast <= searchTime AND searchTime < @TooOld AND userName = @UserName
    UPDATE MSSQLogO14PageClick 
    SET userName = 'NA' 
    WHERE @FromLast <= searchTime AND searchTime < @TooOld AND userName = @UserName
    COMMIT TRANSACTION 
END 
GO 
```

#### <a name="remove-references-to-all-user-names-in-the-query-history-from-a-date-and-up-to-the-past-30-days"></a>Remover referências a todos os nomes de usuário no histórico de consultas a partir de determinada data até os últimos 30 dias

```sql
EXECUTE proc_MSS_QLog_Cleanup_Users '1-1-2017', 30 
```

### <a name="delete-usage-records"></a>Excluir registros de uso

O SharePoint Server exclui automaticamente os registros de uso após três anos. É possível excluí-los manualmente usando o procedimento a seguir:

Para excluir todos os registros de uso associados a documentos excluídos: 

1.  Verifique se você tem a atualização mais recente do SharePoint. 

2.  Inicie um shell de Gerenciamento do SharePoint.

3.  Interrompa e desmarque a Análise de Uso: 

    ```powershell
    $tj = Get-SPTimerJob -Type Microsoft.Office.Server.Search.Analytics.UsageAnalyticsJobDefinition 
    $tj.DisableTimerjobSchedule()
    $tj.StopAnalysis() 
    $tj.ClearAnalysis() 
    $tj.EnableTimerjobSchedule()
    ```

4.  Espere até que a análise seja iniciada novamente (pode levar até 24 horas). 

5.  Na próxima execução da análise, ela despejará todos os registros do banco de dados de Relatórios de Análise. Esse despejo completo pode levar algum tempo se o banco de dados tiver várias entradas.

6.  Aguarde 10 dias. A análise é executada diariamente e os registros associados a documentos excluídos serão removidos após a décima execução. Essa execução pode levar mais tempo do que o normal se muitos registros precisarem ser excluídos. 

### <a name="personal-information-and-search-in-sharepoint-server-2010"></a>Informações pessoais e pesquisa no SharePoint Server 2010

#### <a name="fast-search-server-2010-for-sharepoint"></a>Microsoft FAST Search Server 2010 para SharePoint 

Além de armazenar arquivos no índice, o complemento FAST Search Server 2010 também armazena arquivos em um formato intermediário chamado FixML. Arquivos FiXML são compactados regularmente, por padrão, entre 3h e 5h toda noite. A compactação remove os arquivos excluídos dos arquivos FiXML automaticamente. Para garantir a remoção em tempo hábil das informações pertencentes a usuários ou documentos excluídos, certifique-se de que a compactação esteja sempre habilitada.

### <a name="hybrid-search"></a>Pesquisa híbrida 

As ações recomendadas para as soluções de pesquisa híbrida são as mesmas que para a pesquisa no SharePoint Server ou no SharePoint Online. Existem duas soluções de pesquisa híbrida:

**A solução de pesquisa híbrida em nuvem**: com a solução de pesquisa híbrida em nuvem para SharePoint, você indexa todo o seu conteúdo rastreado, incluindo o conteúdo do local, no índice de pesquisa do Office 365. Quando os usuários consultam o índice de pesquisa no Office 365, eles obtêm resultados de pesquisa do conteúdo local e do Office 365. Quando documentos são excluídos do ambiente do SharePoint Server, eles também são excluídos do índice de pesquisa do Office 365. [Leia mais sobre a solução de pesquisa híbrida em nuvem](https://docs.microsoft.com/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint) e [como componentes e bancos de dados de pesquisa interagem na pesquisa híbrida em nuvem](https://docs.microsoft.com/sharepoint/hybrid/plan-cloud-hybrid-search-for-sharepoint) para entender melhor como o RGPD afeta o ambiente híbrido.

**A solução de pesquisa federada híbrida**: com a solução de pesquisa federada híbrida, você usa o índice no SharePoint Server e no Office 365. Ambos os serviços de pesquisa do SharePoint Server e do SharePoint Online podem consultar o índice de pesquisa em outro lugar e retornar resultados federados. Quando os usuários pesquisam no Centro de Pesquisa, os resultados são exibidos tanto no índice de pesquisa no SharePoint Server quanto no índice de pesquisa no Office 365. [Leia mais sobre a solução de pesquisa híbrida federada ](https://docs.microsoft.com/sharepoint/hybrid/learn-about-hybrid-federated-search-for-sharepoint) para entender melhor como o RGPD afeta o ambiente híbrido.

## <a name="on-prem-to-cloud-migrations"></a>Migrações do local para a nuvem

Durante a migração de dados do SharePoint Server para o SharePoint Online, pode haver dados duplicados em ambos os locais por um período. Se você tiver dados que precisa excluir durante a migração, recomendamos concluir a migração primeiro e excluir os dados de ambos os locais. Você pode consultar os dados para exportação de qualquer local.

## <a name="user-profile-data"></a>Dados de perfil do usuário

O serviço Perfil de Usuário permite a importação de dados de perfil de uma variedade de fontes externas. Consultas e atualizações desses dados de perfil devem ser realizadas nos sistemas nos quais os dados são dominados. Caso você faça atualizações no sistema externo, sincronize novamente os perfis de usuário no SharePoint Server.

Siga estas etapas básicas para remover as informações pessoais de um usuário de seu perfil do SharePoint Server:

1.  Remova as informações do usuário de qualquer sistema externo que alimente o perfil de usuário do SharePoint Server. Se você estiver usando a sincronização de diretórios, o usuário deverá ser removido do ambiente do Active Directory local.

2.  Execute uma [sincronização de perfil](https://docs.microsoft.com/sharepoint/administration/start-profile-synchronization-manually) no SharePoint Server.

3.  Excluir o perfil do SharePoint Server. Quando terminar, o SharePoint Server removerá totalmente o perfil do banco de dados de perfis de usuários em 30 dias. A página de perfil e o site pessoal de usuário serão excluídos.

Depois de excluir o perfil de um usuário, algumas informações limitadas (como a ID do usuário) ainda poderão estar registradas em conjuntos de sites que o usuário acessou. Se quiser excluir dados de um conjunto de sites, isso pode ser feito usando o CSOM. Um exemplo de script é fornecido abaixo:

```powershell
$username = "<admin@company.sharepoint.com>"
$password = "password"
$url = "<https://site.sharepoint.com>"
$securePassword = ConvertTo-SecureString $Password -AsPlainText -Force

# the path here may need to change if you used e.g. C:Lib.
Add-Type -Path "c:\Program Files\Common Files\microsoft shared\Web Server Extensions\16ISAPIMicrosoft.SharePoint.Client.dll"
Add-Type -Path "c:\Program Files\Common Files\microsoft shared\Web Server Extensions\16ISAPIMicrosoft.SharePoint.Client.Runtime.dll"

# connect/authenticate to SharePoint Online and get ClientContext object.
$clientContext = New-Object Microsoft.SharePoint.Client.ClientContext($url)
$credentials = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($username, $securePassword)
$clientContext.Credentials = $credentials
if (!$clientContext.ServerObjectIsNull.Value)
{
    Write-Host "Connected to SharePoint Online site: '$Url'" -ForegroundColor Green
}

# Get user
$user = $clientContext.Web.SiteUsers.GetByLoginName("i:0#.f|membership|user@company.sharepoint.com")

# Redact user
$user.Email = "Redacted"
$user.Title = "Redacted"
$user.Update()
$clientContext.Load($user)
$clientContext.ExecuteQuery()

# Get users
$users = $clientContext.Web.SiteUsers

# Remove user from site
$users.RemoveById($user.Id)
$clientContext.Load($users)
$clientContext.ExecuteQuery()
```
