---
title: Coletar informações de diagnóstico de descoberta eletrônica
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Saiba mais sobre como coletar informações de diagnóstico de Descoberta e Para um caso de Suporte da Microsoft.
ms.openlocfilehash: 842f8baf770f178df3298bbfa911de26ce946ed0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926551"
---
# <a name="collect-ediscovery-diagnostic-information"></a>Coletar informações de diagnóstico de descoberta eletrônica

Ocasionalmente, os engenheiros de Suporte da Microsoft exigem informações específicas sobre seu problema quando você abre um caso de suporte relacionado à Descoberta Básica de Advanced eDiscovery. Este artigo fornece orientações sobre como coletar informações de diagnóstico para ajudar os engenheiros a investigar e resolver problemas. Normalmente, você não precisa coletar essas informações até ser solicitado por um engenheiro de Suporte da Microsoft.

> [!IMPORTANT]
> A saída dos cmdlets e informações de diagnóstico descritas neste artigo pode incluir informações confidenciais sobre litígio ou investigações internas em sua organização. Antes de enviar as informações de diagnóstico brutas para o Suporte da Microsoft, você deve revisar as informações e rediscar quaisquer informações confidenciais (como nomes ou outras informações sobre partes para litígio ou investigação) substituindo-as por `XXXXXXX` . O uso desse método também indicará ao engenheiro de Suporte da Microsoft que as informações foram redacted.

## <a name="collect-diagnostic-information-for-core-ediscovery"></a>Coletar informações de diagnóstico para a Descoberta Principal

A coleta de informações de diagnóstico para a Descoberta Eletrônica Principal é baseada em cmdlet, portanto, você terá que usar o Centro de Conformidade e Segurança & PowerShell. Os exemplos a seguir do PowerShell executarão cmdlets e salvarão a saída em um arquivo de texto especificado. Na maioria dos casos de suporte, você deve executar apenas um desses comandos.

Para executar os cmdlets a seguir, conecte-se ao Centro de [Conformidade e Segurança & PowerShell </span> ](/powershell/exchange/connect-to-scc-powershell). Depois de conectado, execute um ou mais dos seguintes comandos e substitua os espaço reservados por nomes de objeto reais.

Depois de revisar o arquivo de texto gerado e redactar informações confidenciais, envie-o para o engenheiro de Suporte da Microsoft que está trabalhando em seu caso.

> [!NOTE]
> Você também pode executar os comandos nesta seção para coletar informações de  diagnóstico para as pesquisas e exportações listadas na página de pesquisa de conteúdo no centro de conformidade Microsoft 365 de conteúdo.

### <a name="collect-information-about-searches"></a>Coletar informações sobre pesquisas

O comando a seguir coleta informações que são úteis ao investigar problemas com uma pesquisa de conteúdo ou uma pesquisa associada a um caso core de Descoberta e Descoberta.

```powershell
Get-ComplianceSearch "<Search name>" | FL > "ComplianceSearch.txt"
```

### <a name="collect-information-about-search-actions"></a>Coletar informações sobre ações de pesquisa

O comando a seguir coleta informações para investigar problemas de visualização, exportação ou purgação dos resultados de uma pesquisa de Conteúdo ou de uma pesquisa associada a um caso de Descoberta Principal de Descoberta e. Você pode identificar o nome da ação de pesquisa clicando em uma exportação listada na **guia Exportações.** Para identificar os nomes das ações de visualização e limpeza, você pode executar o cmdlet **Get-ComplianceSearchAction** para exibir uma lista de todas as ações. O formato do nome da ação de pesquisa é construído por appending , ou pelo `_Preview` nome da pesquisa `_Export` `_Purge` correspondente.

```powershell
Get-ComplianceSearchAction "<Search action name>" | FL > "ComplianceSearchAction.txt"
```

### <a name="collect-information-about-ediscovery-holds"></a>Coletar informações sobre os ressamentos de Descoberta e

Quando uma responsabilidade de Descoberta Externa associada a um caso de Descoberta Externa Principal não estiver funcionando conforme o esperado, execute o seguinte comando para coletar informações sobre a Política de Recolhimento de Caso e a Regra de Recolhimento de Caso associada para a recolhimento de Descoberta e Descoberta. O *nome da política de espera de* caso no comando a seguir é o mesmo que o nome da ressução de Descoberta e. Você pode identificar esse nome nas guias **Retém** no caso descoberta principal.

```powershell
Get-CaseHoldPolicy "<Case hold policy name>" | %{"--CaseHoldPolicy--";$_|FL;"--CaseHoldRule--";Get-CaseHoldRule -Policy $_.Name | FL} > "eDiscoveryCaseHold.txt"
```

### <a name="collect-all-case-information"></a>Coletar todas as informações de caso

Às vezes, não é evidente quais informações são necessárias para o Suporte da Microsoft investigar seu problema. Nessa situação, você pode coletar todas as informações de diagnóstico para um caso core de Descoberta eDiscovery. O nome da ocorrência de Descoberta *eDiscovery* Principal no comando a seguir é o mesmo que o nome de uma ocorrência exibida na página Descoberta Principal da **Descoberta** e No centro de conformidade Microsoft 365.

```powershell
Get-ComplianceCase "<Core eDiscovery case name>"| %{"$($_.Name)";"`t==Searches==";Get-ComplianceSearch -Case $_.Name | FL;"`t==Search Actions==";Get-ComplianceSearchAction -Case $_.Name |FL;"`t==Holds==";Get-CaseHoldPolicy -Case $_.Name | %{$_|FL;"`t`t ==$($_.Name) Rules==";Get-CaseHoldRule -Policy $_.Name | FL}} > "eDiscoveryCase.txt"
```

## <a name="collect-diagnostic-information-for-advanced-ediscovery"></a>Coletar informações de diagnóstico para Advanced eDiscovery

A **Configurações** guia em um caso Advanced eDiscovery permite copiar rapidamente as informações de diagnóstico para o caso. As informações de diagnóstico são salvas na área de transferência para que você possa colar em um arquivo de texto e enviar para o Suporte da Microsoft.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique em Mostrar todas as > Descoberta > **Avançado**.

2. Selecione um caso e clique na guia **Configurações.**

3. Em **Informações de Caso,** clique **em Selecionar**.

4. Na página de sobrevoo, clique em Copiar informações **de diagnóstico** para copiar as informações para a área de transferência.

5. Abra um arquivo de texto (em Bloco de notas) e, em seguida, colar as informações no arquivo de texto.

6. Salve o arquivo de texto e nomee-o como algo parecido `AeD Diagnostic Info YYYY.MM.DD` (por exemplo, `AeD Diagnostic Info 2020.11.03` ).

Depois de revisar o arquivo e redactar informações confidenciais, envie-o para o engenheiro de Suporte da Microsoft que está trabalhando em seu caso.