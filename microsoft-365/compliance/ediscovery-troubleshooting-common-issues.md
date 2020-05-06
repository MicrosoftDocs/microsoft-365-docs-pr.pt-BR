---
title: Solucionando problemas comuns de descoberta eletrônica
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Saiba mais sobre as etapas básicas de solução de problemas que você pode executar para resolver problemas comuns na descoberta eletrônica do Office 365.
siblings_only: true
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f8b73e886e9aa639ff5575f10822417411a0784e
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035663"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a>Investigar, solucionar problemas e resolver problemas comuns de descoberta eletrônica

Este tópico aborda as etapas básicas de solução de problemas que podem ser tomadas para identificar e resolver problemas que você pode encontrar durante uma pesquisa de descoberta eletrônica ou em qualquer outro lugar no processo de descoberta eletrônica. A resolução de alguns desses cenários requer ajuda do suporte da Microsoft. As informações sobre quando entrar em contato com o suporte da Microsoft estão incluídas nas etapas de resolução.

## <a name="errorissue-ambiguous-location"></a>Erro/problema: local ambíguo

Se você tentar adicionar o local da caixa de correio do usuário para pesquisar e houver objetos duplicados ou conflitantes com o mesmo userID no diretório do Exchange Online Protection (EOP), você receberá esse erro: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`. 

### <a name="resolution"></a>Resolução

Verifique se há usuários duplicados ou lista de distribuição com a mesma ID de usuário.

1. Conecte-se ao [PowerShell do centro de conformidade & segurança](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

2. Execute o seguinte comando para recuperar todas as instâncias do nome de usuário:

    ```powershell
    Get-Recipient <username>
    ```

   A saída de ' useralias@contoso.com ' seria semelhante à seguinte:

   > 
   > |Nome  |RecipientType  |
   > |---------|---------|
   > |Alias, usuário     |MailUser         |
   > |Alias, usuário     |Usuário         |

3. Se vários usuários forem retornados, localize e corrija o objeto conflitante.

## <a name="errorissue-search-fails-on-specific-locations"></a>Erro/problema: a pesquisa falha em locais específicos

Uma pesquisa de descoberta eletrônica ou conteúdo pode resultar no seguinte erro:
>Esta pesquisa foi concluída com erros (#).  Você gostaria de repetir a pesquisa nos locais com falha?

![Falha na captura de tela de erro de local específico da pesquisa](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a>Resolução

Se você receber esse erro, recomendamos verificar os locais que falharam na pesquisa e, em seguida, executar a pesquisa apenas nos locais com falha.

1. Conecte-se ao [PowerShell do centro de conformidade & segurança](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) e execute o seguinte comando:

    ```powershell
    Get-ComplianceSearch <searchname> | FL 
    ```

2. Na saída do PowerShell, exiba os locais com falha no campo erros ou nos detalhes de status no erro do resultado da pesquisa.

3. Repita a pesquisa de descoberta eletrônica somente nos locais com falha.

4. Se você continuar recebendo esses erros, confira [locais de falha na tentativa](https://docs.microsoft.com/Office365/SecurityCompliance/retry-failed-content-search) de obter mais etapas de solução de problemas.

## <a name="errorissue-file-not-found"></a>Erro/problema: arquivo não encontrado

Ao executar uma pesquisa de descoberta eletrônica que inclui o SharePoint Online e uma unidade para locais comerciais, você pode `File Not Found` receber o erro, embora o arquivo esteja localizado no site. Esse erro estará nos avisos de exportação e erros. csv ou itens ignorados. csv. Isso pode ocorrer se o arquivo não puder ser encontrado no site ou se o índice estiver desatualizado. Este é o texto de um erro real (com ênfase adicionada).
  
> 28.06.2019 10:02:19_FailedToExportItem_Failed para baixar conteúdo. Informações adicionais de diagnóstico: Microsoft. Office. Compliance. EDiscovery. ExportWorker. Exceptions. ContentDownloadTemporaryFailure: falha ao baixar do conteúdo 6ea52149-91cd-4965-b5bb-82ca6a3ec9be do tipo documento. ID de correlação: 3bd84722-937b-4c23-b61b-08d6fba9ec32. ServerErrorCode:-2147024894---> Microsoft. SharePoint. Client. ServerException: ***arquivo não encontrado***. em Microsoft. SharePoint. Client. ClientRequest. ProcessResponseStream (Stream responseStream) em Microsoft. SharePoint. Client. ClientRequest. ProcessResponse ()---fim de rastreamento de pilha de exceção interna---

### <a name="resolution"></a>Resolução

1. Verifique o local identificado na pesquisa para garantir que o local do arquivo está correto e adicionado nos locais de pesquisa.

2. Use os procedimentos a fim de [solicitar manualmente o rastreamento e a reindexação de um site, uma biblioteca ou uma lista](https://docs.microsoft.com/sharepoint/crawl-site-content) para reindexar o site.

## <a name="errorissue-search-fails-because-recipient-is-not-found"></a>Erro/problema: a pesquisa falha porque o destinatário não foi encontrado

Uma pesquisa de descoberta eletrônica falha com `recipient not found`o erro. Esse erro pode ocorrer se o objeto de usuário não puder ser encontrado na proteção do Exchange Online (EOP) porque o objeto não foi sincronizado.

### <a name="resolution"></a>Resolução

1. Conecte-se ao [PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

2. Execute o seguinte comando para verificar se o usuário foi sincronizado com a proteção do Exchange Online:

    ```powershell
    Get-Recipient <userId> | FL
    ```

3. Deve haver um objeto de usuário de email para a pergunta do usuário. Se nada for retornado, investigue o objeto user. Entre em contato com o suporte da Microsoft se o objeto não puder ser sincronizado.

## <a name="errorissue-exporting-search-results-is-slow"></a>Erro/problema: a exportação dos resultados da pesquisa é lenta

Ao exportar os resultados da pesquisa de descoberta eletrônica ou de pesquisa de conteúdo no centro de segurança e conformidade, o download demora mais do que o esperado.  Você pode verificar para ver a quantidade de dados a serem baixados e, possivelmente, aumentar a velocidade de exportação.

### <a name="resolution"></a>Resolução

1.    Tente usar as etapas identificadas no artigo [aumentar as velocidades de download](https://docs.microsoft.com/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results).

2.    Se você ainda tiver problemas, conecte-se ao [PowerShell do centro de conformidade & segurança](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) e execute o seguinte comando:

    ```powershell
    Get-ComplianceSearch <searchname> | FL
    ```

4. Encontre a quantidade de dados a serem baixados nos parâmetros SearchResults e SearchStatistics.

5. Execute o seguinte comando:

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

6. No campo resultados, localize os dados que foram exportados e exiba os erros encontrados.

7. Verifique o arquivo Trace. log localizado no diretório em que você exportou o conteúdo para qualquer erro.

## <a name="errorissue-internal-server-error-500-occurred"></a>Erro/problema: ocorreu o erro interno do servidor (500)

Ao executar uma pesquisa de descoberta eletrônica, se a pesquisa falhar continuamente com um erro semelhante a "erro interno do servidor (500)", você pode precisar executar novamente a pesquisa em locais de caixa de correio específicos.

![Captura de tela do erro do servidor interno 500](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a>Resolução

1. Divida a pesquisa em pesquisas menores e execute a pesquisa novamente.  Tente usar um intervalo de datas menor ou limitar o número de locais que estão sendo pesquisados.

2. Conecte-se ao [PowerShell do centro de conformidade & segurança](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) e execute o seguinte comando:

    ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
    Get-ComplianceSearch <searchname> | FL
    ```

3. Examine a saída para obter resultados e erros.

4. Examine o arquivo Trace. log. Ele está localizado na mesma pasta para a qual você exportou os resultados da pesquisa.

5. Entrar em contato com o Suporte da Microsoft.

## <a name="errorissue-holds-dont-sync"></a>Erro/problema: isenções não sincronizar

erro de distribuição de política de retenção de caso de descoberta eletrônica. O erro diz:

> "Recursos: está demorando mais do que o esperado para implantar a política. Pode levar mais duas horas para atualizar o status de implantação final, portanto, verifique novamente em algumas horas. "

### <a name="resolution"></a>Resolução

1.    Conecte-se ao [PowerShell do centro de conformidade & segurança](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) e, em seguida, execute o seguinte comando para uma retenção de caso de descoberta eletrônica:

    ```powershell
    Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
    ```

    Para uma política de retenção, execute o seguinte comando:

    ```powershell
    Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
    ```

2. Examine o valor no parâmetro DistributionDetail para obter erros como o seguinte:
 
   > Erro: recursos: está demorando mais do que o esperado para implantar a política. Pode levar mais duas horas para atualizar o status de implantação final, portanto, verifique novamente em algumas horas. " 
   
3. Tente executar o parâmetro RetryDistribution na política em questão:
   
    
    Para isenções de caso de descoberta eletrônica:

    ```powershell
    Set-CaseHoldPolicy <policyname> -RetryDistribution
    ```

    Para políticas de retenção:

    ```powershell
    Set-RetentionCompliancePolicy <policyname> -RetryDistribution
    ``` 

4. Entrar em contato com o Suporte da Microsoft.

## <a name="see-also"></a>Confira também

- [Dicas para evitar erros de localização de conteúdo](retry-failed-content-search.md#tips-to-avoid-content-location-errors)
