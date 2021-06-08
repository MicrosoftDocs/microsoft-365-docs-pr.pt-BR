---
title: Solução de problemas comuns de Descoberta e Descoberta
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
description: Saiba mais sobre as etapas básicas de solução de problemas que você pode tomar para resolver problemas comuns Office 365 Descoberta eDiscovery.
siblings_only: true
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 26ca41774e1e09619fdf5e518258f8acf3a9d938
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809114"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a>Investigar, solucionar problemas e resolver problemas comuns de Descoberta e Descoberta

Este tópico aborda as etapas básicas de solução de problemas que podem ser tomadas para identificar e resolver problemas que podem ser encontrados durante uma pesquisa de Descoberta E ou em outro lugar no processo de Descoberta eDiscovery. A resolução de alguns desses cenários requer ajuda do Suporte da Microsoft. As informações sobre quando entrar em contato com o Suporte da Microsoft estão incluídas nas etapas de resolução.

## <a name="errorissue-ambiguous-location"></a>Erro/problema: local ambíguo

Se você tentar adicionar o local da caixa de correio do usuário à pesquisa e houver objetos duplicados ou conflitantes com o mesmo userID no diretório Proteção do Exchange Online (EOP), você receberá este erro: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous` .

### <a name="resolution"></a>Resolução

Verifique se há usuários duplicados ou lista de distribuição com a mesma ID de usuário.

1. Conexão [para o Centro de Conformidade & Segurança powerShell](/powershell/exchange/connect-to-scc-powershell).

2. Execute o seguinte comando para recuperar todas as instâncias do nome de usuário:

    ```powershell
    Get-Recipient <username>
    ```

   A saída para 'useralias@contoso.com' seria semelhante ao seguinte:

   > 
   > |Nome|RecipientType|
   > |---|---|
   > |Alias, User|MailUser|
   > |Alias, User|Usuário|

3. Se vários usuários são retornados, localize e corrige o objeto conflitante.

## <a name="errorissue-search-fails-on-specific-locations"></a>Erro/problema: a pesquisa falha em locais específicos

Uma descoberta de conteúdo ou descoberta de conteúdo pode gerar o seguinte erro: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`

![Local específico da pesquisa falha na captura de tela de erro](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a>Resolução

Se você receber esse erro, recomendamos que você verifique os locais que falharam na pesquisa e, em seguida, reprise a pesquisa somente nos locais com falha.

1. Conexão para o Centro de Conformidade & Segurança do [PowerShell](/powershell/exchange/connect-to-scc-powershell) e execute o seguinte comando:

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. Na saída do PowerShell, veja os locais com falha no campo de erros ou nos detalhes de status no erro da saída de pesquisa.

3. Repetir a pesquisa de Descoberta e somente nos locais com falha.

4. Se você continuar a receber esses erros, consulte Repetir locais [com falha](/Office365/SecurityCompliance/retry-failed-content-search) para obter mais etapas de solução de problemas.

## <a name="errorissue-file-not-found"></a>Erro/problema: Arquivo não encontrado

Ao executar uma pesquisa de Descoberta Virtual que inclui SharePoint online e locais do One Drive For Business, você pode receber o erro, embora o arquivo está `File Not Found` localizado no site. Esse erro estará nos avisos de exportação e errors.csv ou ignorado items.csv. Isso pode ocorrer se o arquivo não puder ser encontrado no site ou se o índice estiver desa datado. Aqui está o texto de um erro real (com ênfase adicionada).

> 28.06.2019 10:02:19_FailedToExportItem_Failed baixar conteúdo. Informações de diagnóstico adicionais : Microsoft. Office. Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Falha ao baixar do conteúdo 6ea52149-91cd-4965-b5bb-82ca6a3ec9be do tipo Document. Id de correlação: 3bd84722-937b-4c23-b61b-08d6fba9ec32. ServerErrorCode: -2147024894 ---> Microsoft. SharePoint. Client.ServerException: ***Arquivo não encontrado***. na Microsoft. SharePoint. Client.ClientRequest.ProcessResponseStream(Stream responseStream) na Microsoft. SharePoint. Client.ClientRequest.ProcessResponse() --- fim da pilha de exceção interna ---

### <a name="resolution"></a>Resolução

1. Verifique o local identificado na pesquisa para garantir que o local do arquivo está correto e adicionado nos locais de pesquisa.

2. Use os procedimentos em Solicitação manual de rastreamento e re indexação de [um site,](/sharepoint/crawl-site-content) uma biblioteca ou uma lista para reindexar o site.

## <a name="errorissue-this-file-wasnt-exported-because-it-doesnt-exist-anymore-the-file-was-included-in-the-count-of-estimated-search-results-because-its-still-listed-in-the-index-the-file-will-eventually-be-removed-from-the-index-and-wont-cause-an-error-in-the-future"></a>Erro/problema: esse arquivo não foi exportado porque ele não existe mais. O arquivo foi incluído na contagem de resultados de pesquisa estimados porque ele ainda está listado no índice. O arquivo eventualmente será removido do índice e não causará um erro no futuro.

Você pode ver esse erro ao executar uma pesquisa de Descoberta Virtual que inclui locais SharePoint Online e One Drive For Business. A Descoberta eDiscovery depende do índice SPO para identificar os locais do arquivo. Se o arquivo foi excluído, mas o índice SPO ainda não foi atualizado, esse erro pode ocorrer.

### <a name="resolution"></a>Resolução 
Abra o local do SPO e verifique se esse arquivo realmente não está lá.
A solução sugerida é reindexar manualmente o site ou aguardar até que o site seja reindexado pelo processo de plano de fundo automático.


## <a name="errorissue-this-search-result-was-not-downloaded-as-it-is-a-folder-or-other-artefact-that-cant-be-downloaded-by-itself-any-items-inside-the-folder-or-library-will-be-downloaded"></a>Erro/problema: esse resultado de pesquisa não foi baixado, pois é uma pasta ou outro artefato que não pode ser baixado por si só, qualquer item dentro da pasta ou biblioteca será baixado.

Você pode ver esse erro ao executar uma pesquisa de Descoberta Virtual que inclui locais SharePoint Online e One Drive For Business. Isso significa que vamos tentar exportar o item relatado no índice, mas ele acabou sendo uma pasta para que não o exportá-lo. Como mencionado no erro, não exportamos itens de pasta, mas exportamos seu conteúdo.


## <a name="errorissue-search-fails-because-recipient-is-not-found"></a>Erro/problema: a pesquisa falha porque o destinatário não foi encontrado

Uma pesquisa de Descoberta E falha com o erro `recipient not found` de . Esse erro pode ocorrer se o objeto do usuário não puder ser encontrado no Proteção do Exchange Online (EOP) porque o objeto não foi sincronizado.

### <a name="resolution"></a>Resolução

1. Conexão para [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Execute o seguinte comando para verificar se o usuário está sincronizado com Proteção do Exchange Online:

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. Deve haver um objeto de usuário de email para a pergunta do usuário. Se nada for retornado, investigue o objeto user. Entre em contato com o Suporte da Microsoft se o objeto não puder ser sincronizado.

## <a name="errorissue-exporting-search-results-is-slow"></a>Erro/problema: a exportação de resultados da pesquisa é lenta

Ao exportar resultados da pesquisa da Descoberta Digital ou da Pesquisa de Conteúdo no Centro de Segurança e Conformidade, o download leva mais tempo do que o esperado.  Você pode verificar a quantidade de dados a serem baixados e possivelmente aumentar a velocidade de exportação.

### <a name="resolution"></a>Resolução

1. Conexão para o Centro de Conformidade & Segurança do [PowerShell](/powershell/exchange/connect-to-scc-powershell) e execute o seguinte comando:

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. Encontre a quantidade de dados a serem baixados nos parâmetros SearchResults e SearchStatistics.

3. Execute o seguinte comando:

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

4. No campo resultados, encontre os dados que foram exportados e exibir quaisquer erros encontrados.

5. Verifique o arquivo trace.log localizado no diretório para o qual você exportou o conteúdo para quaisquer erros.

6. Se você ainda tiver problemas, considere dividir pesquisas que retornam um grande conjunto de resultados em pesquisas menores. Por exemplo, você pode usar intervalos de datas em consultas de pesquisa para retornar um conjunto menor de resultados que podem ser baixados mais rapidamente.

## <a name="errorissue-internal-server-error-500-occurred"></a>Erro/problema: "Erro interno do servidor (500) ocorrido"

Ao executar uma pesquisa de Descoberta Eletrônico, se a pesquisa falhar continuamente com um erro semelhante a "Erro de servidor interno (500) ocorreu", talvez seja necessário executar a pesquisa apenas em locais de caixa de correio específicos.

![Captura de tela de erro de servidor interno 500](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a>Resolução

1. Quebre a pesquisa em pesquisas menores e execute a pesquisa novamente.  Tente usar um intervalo de datas menor ou limite o número de locais que estão sendo pesquisados.

2. Conexão para o Centro de Conformidade & Segurança do [PowerShell](/powershell/exchange/connect-to-scc-powershell) e execute o seguinte comando:

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. Examine a saída em busca de resultados e erros.

4. Examine o arquivo trace.log. Ele está localizado na mesma pasta para a onde você exportou os resultados da pesquisa.

5. Entrar em contato com o Suporte da Microsoft.

## <a name="errorissue-holds-dont-sync"></a>Erro/problema: retém não sincronizar

Erro de Distribuição de Sincronização de Sincronização de Política de Descoberta EDiscovery. O erro diz:

> "Recursos: está demorando mais do que o esperado para implantar a política. Pode levar mais duas horas para atualizar o status final da implantação, portanto, volte em algumas horas."

### <a name="resolution"></a>Resolução

1. Conexão & para o Centro de Conformidade e Segurança do [PowerShell](/powershell/exchange/connect-to-scc-powershell) e execute o seguinte comando para uma ressarção de caso de Descoberta eDiscovery:

   ```powershell
   Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
   ```

    Para uma política de retenção, execute o seguinte comando:

   ```powershell
   Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
   ```

2. Examine o valor no parâmetro DistributionDetail para ver se há erros como o seguinte:

   > Erro: Recursos: está demorando mais do que o esperado para implantar a política. Pode levar mais duas horas para atualizar o status final da implantação, portanto, volte em algumas horas."

3. Tente executar o parâmetro RetryDistribution na política em questão:

   Para os casos de Descoberta eDiscovery:

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

   Para políticas de retenção:

   ```powershell
   Set-RetentionCompliancePolicy <policyname> -RetryDistribution
   ```

4. Entrar em contato com o Suporte da Microsoft.

## <a name="error-the-condition-specified-using-http-conditional-headers-is-not-met"></a>Erro: "A condição especificada usando cabeçalhos condicionais HTTP não é atendida"

Ao baixar os resultados da pesquisa usando a Ferramenta de Exportação de Descoberta Armazenamento, é possível que você receba o seguinte erro: Este é um erro transitório, que normalmente ocorre no local de Armazenamento `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` do Azure.

### <a name="resolution"></a>Resolução

Para resolver esse problema, baixe novamente [os](export-search-results.md#step-2-download-the-search-results)resultados da pesquisa , que reiniciarão a Ferramenta de Exportação de Descoberta e.

## <a name="errorissue-downloaded-export-shows-no-results"></a>Erro/problema: a exportação baixada não mostra resultados

Após uma exportação bem-sucedida, o download concluído por meio da ferramenta de exportação mostra zero arquivos nos resultados.

### <a name="resolution"></a>Resolução

Este é um problema do lado do cliente e, para remediar, tente as seguintes etapas:

1. Tente usar outro cliente/máquina para baixar.

2. Remova pesquisas antigas que não são mais necessárias usando o cmdlet [Remove-ComplianceSearch][/powershell/module/exchange/remove-compliancesearch].

3. Certifique-se de baixar para uma unidade local.

4. Certifique-se de que o scanner de vírus não está em execução.

5. Certifique-se de que nenhuma outra exportação está baixando para a mesma pasta ou qualquer pasta pai.

6. Se as etapas anteriores não funcionarem, desabilite o zipping e a de duplicação.

7. Se isso funcionar, o problema será devido a um scanner de vírus local ou a um problema de disco.
