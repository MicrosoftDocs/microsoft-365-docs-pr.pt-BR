---
title: Problemas comuns de descoberta eletrônica do Troublshooting
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
description: Investigue, solucione problemas e resolva problemas comuns na descoberta eletrônica do Office 365.
siblings_only: true
ms.openlocfilehash: db355067aa4e3fc41541e6414b59c92aaac1b5b3
ms.sourcegitcommit: 75c8f89049081f08852699c8d51c3a07b12165da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/26/2019
ms.locfileid: "37207284"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a>Investigar, solucionar problemas e resolver problemas comuns de descoberta eletrônica

Este tópico aborda as etapas básicas de solução de problemas que podem ser tomadas para identificar e resolver problemas que você pode encontrar durante uma pesquisa de descoberta eletrônica ou em qualquer outro lugar no processo de descoberta eletrônica. A resolução de alguns desses cenários requer ajuda dos serviços de suporte ao cliente (CSS). As informações sobre quando entrar em contato com CSS estão incluídas nas etapas de resolução.

## <a name="errorissue-ambiguous-location"></a>Localização ambígua de erro/problema

Você receberá este erro "a pesquisa de conformidade contém o seguinte local `(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous"` inválido se você tentou adicionar o local da caixa de correio do usuário para pesquisar e há objetos duplicados ou conflitantes com a mesma ID de usuário na proteção do Exchange Online (EOP) Directory.

### <a name="resolution"></a>Resolução

Verifique se há usuários duplicados ou lista de distribuição com a mesma ID de usuário.

1. Conecte-se ao [PowerShell do Exchange Online](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).
2. Recuperar todas as instâncias do nome de usuário, digite:

```powershell
Get-Recipient <username>
```

A saída de ' useralias@contoso.com ' pode ser

> 
> |Nome  |RecipientType  |
> |---------|---------|
> |Alias, usuário     |MailUser         |
> |Alias, usuário     |Usuário         |

3. Se vários usuários forem retornados, localize e corrija o objeto conflitante.

## <a name="errorissue-search-fails-on-specific-locations"></a>Falha de pesquisa de erro/problema em locais específicos

Uma pesquisa de descoberta eletrônica ou conteúdo pode resultar no seguinte erro:
>Esta pesquisa foi concluída com erros (#).  Você gostaria de repetir a pesquisa nos locais com falha?

![falha na captura de tela de erro de local específico de pesquisa]( media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a>Resolução

Se você receber esse erro, recomendamos verificar os locais que falharam na pesquisa e, em seguida, executar novamente a pesquisa nos locais com falha.

1. Conecte-se ao [PowerShell do Exchange Online Protection](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).
1. Tipo:

```powershell
Get-Compliancesearch searchname|fl 
```

3. Na saída do PowerShell, exiba os locais com falha no campo erros ou nos detalhes de status no erro do resultado da pesquisa.
1. Repita a pesquisa de descoberta eletrônica somente nos locais com falha.
1. Se você continuar recebendo esse erro, veja [locais de falha na tentativa](https://docs.microsoft.com/en-us/Office365/SecurityCompliance/retry-failed-content-search) de etapas adicionais de solução de problemas.

## <a name="errorissue-file-not-found"></a>Erro/arquivo de problema não encontrado

Ao executar uma pesquisa de descoberta eletrônica que inclui o SharePoint Online e uma unidade para locais comerciais, você pode `File Not Found` receber o erro, embora o arquivo esteja localizado no site. Este erro estará nos avisos de exportação e erros. csv ou itens ignorados. csv isso pode ocorrer se o arquivo não puder ser localizado no site ou se o índice estiver desatualizado. Este é o texto de um erro real, com ênfase adicionada.
  
> 28.06.2019 10:02:19_FailedToExportItem_Failed para baixar conteúdo. Informações adicionais de diagnóstico: Microsoft. Office. Compliance. EDiscovery. ExportWorker. Exceptions. ContentDownloadTemporaryFailure: falha ao baixar do conteúdo 6ea52149-91cd-4965-b5bb-82ca6a3ec9be do tipo documento. ID de correlação: 3bd84722-937b-4c23-b61b-08d6fba9ec32. ServerErrorCode:-2147024894---> Microsoft. SharePoint. Client. ServerException: ***arquivo não encontrado***. em Microsoft. SharePoint. Client. ClientRequest. ProcessResponseStream (Stream responseStream) em Microsoft. SharePoint. Client. ClientRequest. ProcessResponse ()---fim de rastreamento de pilha de exceção interna---

### <a name="resolution"></a>Resolução

1. Verifique o local identificado na pesquisa para garantir que o local do arquivo está correto e adicionado nos locais de pesquisa.
2. Use os procedimentos a fim de [solicitar manualmente o rastreamento e a reindexação de um site, uma biblioteca ou uma lista](https://docs.microsoft.com/en-us/sharepoint/crawl-site-content) para reindexar o site.

## <a name="errorissue-search-fails-recipient-not-found"></a>Erro/pesquisa de problema falha de destinatário não encontrada

a pesquisa de descoberta eletrônica `recipient not found`falha com erro. Esse erro pode ocorrer se o objeto de usuário não puder ser encontrado na proteção do Exchange Online (EOP) porque o objeto não foi sincronizado.

### <a name="resolution"></a>Resolução

1. Conecte-se ao [PowerShell do Exchange Online Protection](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).
1. Verifique se o objeto do usuário está sincronizado com o tipo de proteção do Exchange Online:

```powershell
Get-Recipient userId|fl
```

3. Deve haver um objeto MailUser para a pergunta do usuário. Se nada for retornado, investigue o objeto user. Contato CSS se o objeto não pode ser sincronizado.

## <a name="errorissue-exporting-search-results-is-slow"></a>Erro/problema a exportação dos resultados da pesquisa é lenta

Ao exportar os resultados da pesquisa de descoberta eletrônica ou de pesquisa de conteúdo no centro de segurança e conformidade, o download demora mais do que o esperado.  Você pode verificar para ver a quantidade de dados a serem baixados e, possivelmente, aumentar a velocidade de exportação.

### <a name="resolution"></a>Resolução

1.  Tente usar as etapas identificadas no artigo [aumentar as velocidades de download](https://docs.microsoft.com/en-us/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results).
2.  Se você ainda tiver problemas, conecte-se à [proteção do Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) e digite:

```powershell
Get-ComplianceSearch searchname\fl
```

4. Encontre a quantidade de dados a serem baixados nos parâmetros SearchResults e SearchStatistics.
5. Tipo:

```powershell
Get-ComplianceSearchAction |fl
```

6. No campo resultados, localize os dados que foram exportados e exiba os erros encontrados.
7. Verifique o arquivo Trace. log localizado no diretório em que você exportou o conteúdo para qualquer erro.

## <a name="errorissue-internal-server-error-500-occurred"></a>Erro/problema ocorreu o erro interno do servidor (500)

Ao executar uma pesquisa de descoberta eletrônica, se a pesquisa falhar continuamente com um erro semelhante a "erro interno do servidor (500)", você pode precisar executar novamente a pesquisa em locais de caixa de correio específicos.

![captura de tela do erro do servidor interno 500](media/edisc-tshoot-error-500.png)

### <a name="resolution"></a>Resolução

1. Divida a pesquisa em pesquisas menores e execute a pesquisa novamente.  Tente usar um intervalo de datas menor ou limitar o número de locais que estão sendo pesquisados.
2. Conectar-se ao PowerShell e ao tipo de [proteção do Exchange Online](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) :

```powershell
Get-ComplianceSearch searchname |fl
```

3. Examine a saída para obter resultados e erros.
3. Examine o arquivo Trace. log. Ele será na mesma pasta para a qual você enviou a exportação.
4. Contatar o CSS de suporte.

## <a name="errorissue-holds-dont-sync"></a>Erro/problema contém não sincronizar

erro de distribuição de política de retenção de caso de descoberta eletrônica. O erro diz:

> "Recursos: está demorando mais do que o esperado para implantar a política. Pode levar mais duas horas para atualizar o status de implantação final, portanto, verifique novamente em algumas horas. "

### <a name="resolution"></a>Resolução

1.  Conectar-se ao PowerShell e ao tipo de [proteção do Exchange Online](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) :

```powershell
Get-RetentionCompliancePolicy  policyname - Distributiondetail|fl
```

2. Examine o valor no parâmetro Distributiondetail para obter erros como o seguinte:

> Se houver erro, crie escalonamento para PG para forçar uma nova sincronização manual na política.

3. CSS do contato.

## <a name="see-also"></a>Confira também
- [Dicas para evitar erros de localização de conteúdo](https://docs.microsoft.com/en-us/microsoft-365/compliance/retry-failed-content-search%23tips-to-avoid-content-location-errors)