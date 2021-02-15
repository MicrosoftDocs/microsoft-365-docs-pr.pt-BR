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
description: Saiba mais sobre como coletar informações de diagnóstico de DescobertaScoberta para um caso de Suporte da Microsoft.
ms.openlocfilehash: 107309748e2f27b50be5f8e8fc76afcb693989f9
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944385"
---
# <a name="collect-ediscovery-diagnostic-information"></a>Coletar informações de diagnóstico de descoberta eletrônica

Ocasionalmente, os engenheiros do Suporte da Microsoft exigem informações específicas sobre seu problema quando você abre um caso de suporte relacionado à Descoberta Principal ou Descoberta Avançada. Este artigo fornece orientações sobre como coletar informações de diagnóstico para ajudar os engenheiros de suporte a investigar e resolver problemas. Normalmente, você não precisa coletar essas informações até que seja solicitado por um engenheiro de Suporte da Microsoft.

> [!IMPORTANT]
> A saída dos cmdlets e informações de diagnóstico descritas neste artigo pode incluir informações confidenciais sobre litígios ou investigações internas em sua organização. Antes de enviar as informações de diagnóstico brutas para o Suporte da Microsoft, você deve revisar as informações e reexenciá-la (como nomes ou outras informações sobre partes para litígio ou investigação) substituindo-as `XXXXXXX` por . Usar esse método também indicará ao engenheiro de Suporte da Microsoft que as informações foram redadas.

## <a name="collect-diagnostic-information-for-core-ediscovery"></a>Coletar informações de diagnóstico para a Descoberta Principal

A coleta de informações de diagnóstico para a Descoberta Eletrônica Principal é baseada em cmdlet, portanto, você terá que usar o PowerShell do Centro de Conformidade & Segurança. Os exemplos do PowerShell a seguir executarão cmdlets e salvarão a saída em um arquivo de texto especificado. Na maioria dos casos de suporte, você só deve ter que executar um desses comandos.

Para executar os cmdlets a seguir, [conecte-se </span> ao Centro de Conformidade & Segurança do PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) Depois de conectar, execute um ou mais dos seguintes comandos e substitua os espaço reservados por nomes de objeto reais.

Depois de analisar o arquivo de texto gerado e reactar informações confidenciais, envie-o para o engenheiro de Suporte da Microsoft que está trabalhando em seu caso.

> [!NOTE]
> Você também pode executar os comandos nesta seção para coletar informações de  diagnóstico para as pesquisas e exportações listadas na página Pesquisa de conteúdo no centro de conformidade do Microsoft 365.

### <a name="collect-information-about-searches"></a>Coletar informações sobre pesquisas

O comando a seguir coleta informações que são úteis ao investigar problemas com uma pesquisa de conteúdo ou uma pesquisa associada a um caso de Descoberta e Principal.

```powershell
Get-ComplianceSearch "<Search name>" | FL > "ComplianceSearch.txt"
```

### <a name="collect-information-about-search-actions"></a>Coletar informações sobre ações de pesquisa

O comando a seguir coleta informações para investigar problemas de visualização, exportação ou purgação dos resultados de uma pesquisa de Conteúdo ou de uma pesquisa associada a um caso de Descoberta e Principal. Você pode identificar o nome da ação de pesquisa clicando em uma exportação listada na **guia** Exportações. Para identificar os nomes das ações de visualização e limpeza, você pode executar o cmdlet **Get-ComplianceSearchAction** para exibir uma lista de todas as ações. O formato para o nome da ação de pesquisa é construído por meio de adendo , ou `_Preview` ao nome da pesquisa `_Export` `_Purge` correspondente.

```powershell
Get-ComplianceSearchAction "<Search action name>" | FL > "ComplianceSearchAction.txt"
```

### <a name="collect-information-about-ediscovery-holds"></a>Coletar informações sobre retém de Descoberta eDiscovery

Quando um caso de Descoberta eDiscovery principal não estiver funcionando conforme o esperado, execute o seguinte comando para coletar informações sobre a Política de Caso de Espera e a Regra de Espera de Caso associada para a espera de Descoberta. O *nome da política de isenção* de caso no comando a seguir é o mesmo que o nome da isenção de Descoberta. Você pode identificar esse nome nas guias **Retém** no caso principal de Descoberta eDiscovery.

```powershell
Get-CaseHoldPolicy "<Case hold policy name>" | %{"--CaseHoldPolicy--";$_|FL;"--CaseHoldRule--";Get-CaseHoldRule -Policy $_.Name | FL} > "eDiscoveryCaseHold.txt"
```

### <a name="collect-all-case-information"></a>Coletar todas as informações sobre ocorrências

Às vezes, não fica aparente quais informações são necessárias ao Suporte da Microsoft para investigar seu problema. Nessa situação, você pode coletar todas as informações de diagnóstico para um caso de Descoberta e Principal. O nome da ocorrência de Descoberta e Principal no comando a seguir é o mesmo que o nome de uma ocorrência exibida na página **Descoberta eDiscovery** Principal no centro de conformidade do Microsoft 365. 

```powershell
Get-ComplianceCase "<Core eDiscovery case name>"| %{"$($_.Name)";"`t==Searches==";Get-ComplianceSearch -Case $_.Name | FL;"`t==Search Actions==";Get-ComplianceSearchAction -Case $_.Name |FL;"`t==Holds==";Get-CaseHoldPolicy -Case $_.Name | %{$_|FL;"`t`t ==$($_.Name) Rules==";Get-CaseHoldRule -Policy $_.Name | FL}} > "eDiscoveryCase.txt"
```

## <a name="collect-diagnostic-information-for-advanced-ediscovery"></a>Coletar informações de diagnóstico para Descoberta Avançada

A **guia Configurações** em um caso de Descoberta e Avançada permite copiar rapidamente as informações de diagnóstico para a ocorrência. As informações de diagnóstico são salvas na área de transferência para que você possa colar em um arquivo de texto e enviar para o Suporte da Microsoft.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique em Mostrar todas as > **eDiscovery > Avançado.**

2. Selecione uma ocorrência e clique na **guia Configurações.**

3. Under **Case Information**, click **Select**.

4. Na página do flyout, clique em **Copiar informações de diagnóstico** para copiar as informações para a área de transferência.

5. Abra um arquivo de texto (no Bloco de Notas) e, em seguida, colar as informações no arquivo de texto.

6. Salve o arquivo de texto e nomee-o como algo parecido `AeD Diagnostic Info YYYY.MM.DD` (por exemplo, `AeD Diagnostic Info 2020.11.03` ).

Depois de analisar o arquivo e reactar informações confidenciais, envie-o para o engenheiro de Suporte da Microsoft que está trabalhando em seu caso.
