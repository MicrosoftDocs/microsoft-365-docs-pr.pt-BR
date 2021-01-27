---
title: Solução de problemas comuns de DescobertaScoberta
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
- MOE150
- MET150
ms.assetid: ''
description: Saiba mais sobre as etapas básicas de solução de problemas que você pode seguir para resolver problemas comuns na Descoberta eDiscovery do Office 365.
siblings_only: true
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e1fbda23b730956db42d8e7a92218fb9837868b8
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988135"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a>Investigar, solucionar problemas e resolver problemas comuns de DescobertaScoberta

Este tópico aborda as etapas básicas de solução de problemas que você pode seguir para identificar e resolver problemas que você pode encontrar durante uma pesquisa de Descoberta eDiscovery ou em outro lugar no processo de Descoberta eDiscovery. Resolver alguns desses cenários requer ajuda do Suporte da Microsoft. As informações sobre quando entrar em contato com o Suporte da Microsoft estão incluídas nas etapas de resolução.

## <a name="errorissue-ambiguous-location"></a>Erro/problema: local ambíguo

Se você tentar adicionar o local da caixa de correio do usuário para pesquisar e houver objetos duplicados ou conflitantes com a mesma ID de usuário no diretório do Exchange Online Protection (EOP), você receberá este erro: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous` .

### <a name="resolution"></a>Resolução

Verifique se há usuários duplicados ou lista de distribuição com a mesma ID de usuário.

1. Conecte-se [ao PowerShell & Centro de Conformidade e Segurança.](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)

2. Execute o seguinte comando para recuperar todas as instâncias do nome de usuário:

    ```powershell
    Get-Recipient <username>
    ```

   A saída para "useralias@contoso.com" seria semelhante ao seguinte:

   > 
   > |Nome|RecipientType|
   > |---|---|
   > |Alias, Usuário|MailUser|
   > |Alias, Usuário|Usuário|

3. Se vários usuários são retornados, localize e corrige o objeto conflitante.

## <a name="errorissue-search-fails-on-specific-locations"></a>Erro/problema: a pesquisa falha em locais específicos

Uma pesquisa de conteúdo ou descoberta de eDiscovery pode gerar o seguinte erro: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`

![Localização específica da pesquisa falha na captura de tela de erro](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a>Resolução

Se você receber esse erro, recomendamos que verifique os locais que falharam na pesquisa e, em seguida, reruncar a pesquisa somente nos locais com falha.

1. [Conecte-se ao PowerShell do & Centro de Conformidade](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) e Segurança e execute o seguinte comando:

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. Na saída do PowerShell, veja os locais com falha no campo de erros ou nos detalhes de status no erro da saída da pesquisa.

3. Retry the eDiscovery search on the failed locations only.

4. Se você continuar recebendo esses erros, consulte [Retry failed locations](https://docs.microsoft.com/Office365/SecurityCompliance/retry-failed-content-search) for more troubleshooting steps.

## <a name="errorissue-file-not-found"></a>Erro/problema: arquivo não encontrado

Ao executar uma pesquisa de Descoberta Online que inclui locais do SharePoint Online e do OneDrive for Business, você pode receber o erro, embora o arquivo está `File Not Found` localizado no site. Esse erro estará nos avisos de exportação e errors.csv ou ignorado items.csv. Isso poderá ocorrer se o arquivo não puder ser encontrado no site ou se o índice estiver desa datado. Aqui está o texto de um erro real (com ênfase adicionada).

> 28.06.2019 10:02:19_FailedToExportItem_Failed para baixar conteúdo. Informações de diagnóstico adicionais : Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Falha ao baixar do conteúdo 6ea52149-91cd-4965-b5bb-82ca6a3ec9be do tipo Documento. ID de Correlação: 3bd84722-937b-4c23-b61b-08d6fba9ec32. ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***arquivo não encontrado.*** at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---

### <a name="resolution"></a>Resolução

1. Verifique o local identificado na pesquisa para garantir que o local do arquivo está correto e adicionado nos locais de pesquisa.

2. Use os procedimentos na solicitação manual de rastreamento e [reindexação](https://docs.microsoft.com/sharepoint/crawl-site-content) de um site, biblioteca ou lista para reindexar o site.

## <a name="errorissue-search-fails-because-recipient-is-not-found"></a>Erro/problema: a pesquisa falha porque o destinatário não foi encontrado

Uma pesquisa de Descoberta Descoberta falha com o erro `recipient not found` . Esse erro poderá ocorrer se o objeto do usuário não puder ser encontrado no Exchange Online Protection (EOP) porque o objeto não foi sincronizado.

### <a name="resolution"></a>Resolução

1. Conecte-se [ao PowerShell do Exchange Online.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

2. Execute o seguinte comando para verificar se o usuário está sincronizado com o Exchange Online Protection:

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. Deve haver um objeto de usuário de email para a pergunta do usuário. Se nada for retornado, investigue o objeto do usuário. Entre em contato com o Suporte da Microsoft se o objeto não puder ser sincronizado.

## <a name="errorissue-exporting-search-results-is-slow"></a>Erro/problema: a exportação dos resultados da pesquisa está lenta

Ao exportar os resultados da pesquisa da Descoberta e ou da Pesquisa de Conteúdo no Centro de Conformidade e Segurança, o download leva mais tempo do que o esperado.  Você pode verificar a quantidade de dados a serem baixados e possivelmente aumentar a velocidade de exportação.

### <a name="resolution"></a>Resolução

1. [Conecte-se ao PowerShell do & Centro de Conformidade](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) e Segurança e execute o seguinte comando:

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. Encontre a quantidade de dados a serem baixados nos parâmetros SearchResults e SearchStatistics.

3. Execute o seguinte comando:

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

4. No campo de resultados, encontre os dados que foram exportados e veja quaisquer erros encontrados.

5. Verifique se há erros no arquivo trace.log localizado no diretório para o qual você exportou o conteúdo.

6. Se você ainda tiver problemas, considere dividir as pesquisas que retornam um grande conjunto de resultados em pesquisas menores. Por exemplo, você pode usar intervalos de datas em consultas de pesquisa para retornar um conjunto menor de resultados que podem ser baixados mais rapidamente.

## <a name="errorissue-internal-server-error-500-occurred"></a>Erro/problema: "Erro interno do servidor (500) ocorreu"

Ao executar uma pesquisa de Descoberta Eletrônico, se a pesquisa falhar continuamente com um erro semelhante a "Erro interno do servidor (500) ocorreu", talvez seja necessário executar a pesquisa apenas em locais de caixa de correio específicos.

![Captura de tela de erro 500 do servidor interno](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a>Resolução

1. Quebrar a pesquisa em pesquisas menores e executar a pesquisa novamente.  Tente usar um intervalo de datas menor ou limite o número de locais que estão sendo pesquisados.

2. [Conecte-se ao PowerShell do & Centro de Conformidade](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) e Segurança e execute o seguinte comando:

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. Examine a saída em busca de resultados e erros.

4. Examine o arquivo trace.log. Ele está localizado na mesma pasta para a onde você exportou os resultados da pesquisa.

5. Entrar em contato com o Suporte da Microsoft.

## <a name="errorissue-holds-dont-sync"></a>Erro/problema: as respeções não são sincronizadas

Erro de distribuição de sincronização de política de espera de descoberta do eDiscovery. O erro lê:

> "Recursos: Está demorando mais do que o esperado para implantar a política. Pode levar mais 2 horas para atualizar o status final da implantação, portanto, verifique novamente em algumas horas."

### <a name="resolution"></a>Resolução

1. [Conecte-se ao PowerShell & Centro](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) de Conformidade e Segurança e execute o seguinte comando para um caso de descoberta de eDiscovery:

   ```powershell
   Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
   ```

    Para uma política de retenção, execute o seguinte comando:

   ```powershell
   Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
   ```

2. Examine o valor no parâmetro DistributionDetail em busca de erros como os seguintes:

   > Erro: Recursos: a implantação da política está demorando mais do que o esperado. Pode levar mais 2 horas para atualizar o status final da implantação, portanto, verifique novamente em algumas horas."

3. Tente executar o parâmetro RetryDistribution na política em questão:

   Para o caso de Descoberta eDiscovery:

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

   Para políticas de retenção:

   ```powershell
   Set-RetentionCompliancePolicy <policyname> -RetryDistribution
   ```

4. Entrar em contato com o Suporte da Microsoft.

## <a name="error-the-condition-specified-using-http-conditional-headers-is-not-met"></a>Erro: "A condição especificada usando cabeçalhos condicionais HTTP não é atendida"

Ao baixar os resultados da pesquisa usando a Ferramenta de Exportação de Descobertas, é possível que você receba o seguinte erro: este é um erro transitório, que normalmente ocorre no local de armazenamento do `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` Azure.

### <a name="resolution"></a>Resolução

Para resolver esse problema, retry [downloading the search results](export-search-results.md#step-2-download-the-search-results), which will restart the eDiscovery Export Tool.

## <a name="errorissue-downloaded-export-shows-no-results"></a>Erro/problema: a exportação baixada não mostra resultados

Após uma exportação bem-sucedida, o download concluído por meio da ferramenta de exportação mostra zero arquivos nos resultados.

### <a name="resolution"></a>Resolução

Esse é um problema do lado do cliente e, para remediar, tente as seguintes etapas:

1. Tente usar outro cliente/computador para baixar.

2. Certifique-se de baixar para uma unidade local.

3. Certifique-se de que o scanner de vírus não está em execução.

4. Certifique-se de que nenhuma outra exportação está baixando para a mesma pasta ou qualquer pasta pai.

5. Se as etapas anteriores não funcionarem, desabilite a replicação e a duplicação.

6. Se isso funcionar, o problema é devido a um scanner de vírus local ou um problema de disco.
