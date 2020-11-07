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
description: Saiba mais sobre como coletar informações de diagnóstico de descoberta eletrônica para um caso de suporte da Microsoft.
ms.openlocfilehash: 107309748e2f27b50be5f8e8fc76afcb693989f9
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944385"
---
# <a name="collect-ediscovery-diagnostic-information"></a>Coletar informações de diagnóstico de descoberta eletrônica

Ocasionalmente, os engenheiros de suporte da Microsoft exigem informações específicas sobre o problema quando você abre um caso de suporte relacionado à descoberta eletrônica principal ou à descoberta eletrônica avançada. Este artigo fornece orientação sobre como coletar informações de diagnóstico para ajudar os engenheiros de suporte a investigar e resolver problemas. Normalmente, você não precisa coletar essas informações até que seja solicitado por um engenheiro de suporte da Microsoft.

> [!IMPORTANT]
> A saída dos cmdlets e das informações de diagnóstico descritas neste artigo pode incluir informações confidenciais sobre litígios ou investigações internas em sua organização. Antes de enviar as informações de diagnóstico brutos para o suporte da Microsoft, você deve revisar as informações e redigir quaisquer informações confidenciais (como nomes ou outras informações sobre as partes de litígio ou investigação) substituindo-as por `XXXXXXX` . O uso desse método também indicará ao engenheiro de suporte da Microsoft que as informações foram redigidas.

## <a name="collect-diagnostic-information-for-core-ediscovery"></a>Coletar informações de diagnóstico para a descoberta eletrônica principal

A coleta de informações de diagnóstico para a descoberta eletrônica principal é baseada em cmdlet, portanto, você terá que usar o PowerShell de segurança & Compliance Center. Os seguintes exemplos do PowerShell executarão cmdlets e, em seguida, salvarão a saída em um arquivo de texto especificado. Na maioria dos casos de suporte, você só deve executar um desses comandos.

Para executar os cmdlets a seguir, [Conecte-se ao PowerShell </span> do centro de conformidade & segurança](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell). Depois que você estiver conectado, execute um ou mais dos seguintes comandos e certifique-se de substituir os espaços reservados pelos nomes de objeto reais.

Após analisar o arquivo de texto gerado e redigir informações confidenciais, envie-o ao engenheiro de suporte da Microsoft em seu caso.

> [!NOTE]
> Você também pode executar os comandos nesta seção para coletar informações de diagnóstico para as pesquisas e exportações listadas na página de **pesquisa de conteúdo** no centro de conformidade do Microsoft 365.

### <a name="collect-information-about-searches"></a>Coletar informações sobre pesquisas

O comando a seguir coleta informações que são úteis ao investigar problemas com uma pesquisa de conteúdo ou uma pesquisa associada a um caso de descoberta eletrônica principal.

```powershell
Get-ComplianceSearch "<Search name>" | FL > "ComplianceSearch.txt"
```

### <a name="collect-information-about-search-actions"></a>Coletar informações sobre ações de pesquisa

O comando a seguir coleta informações para investigar problemas com a visualização, exportação ou limpeza dos resultados de uma pesquisa de conteúdo ou de uma pesquisa associada a um caso de descoberta eletrônica principal. Você pode identificar o nome da ação de pesquisa clicando em uma exportação que está listada na guia **exportações** . Para identificar os nomes das ações de visualização e limpeza, você pode executar o cmdlet **Get-ComplianceSearchAction** para exibir uma lista de todas as ações. O formato do nome da ação de pesquisa é construído acrescentando `_Preview` , `_Export` ou `_Purge` ao nome da pesquisa correspondente.

```powershell
Get-ComplianceSearchAction "<Search action name>" | FL > "ComplianceSearchAction.txt"
```

### <a name="collect-information-about-ediscovery-holds"></a>Coletar informações sobre as suspensões de descoberta eletrônica

Quando um controle de descoberta eletrônica associado a um caso de descoberta eletrônica principal não está funcionando conforme o esperado, execute o seguinte comando para coletar informações sobre a política de bloqueio de caso e a regra de bloqueio de caso associada para a descoberta eletrônica. O *nome da política de retenção de caso* no seguinte comando é o mesmo que o nome da descoberta eletrônica. Você pode identificar esse nome nas guias **isenções** no caso de descoberta eletrônica principal.

```powershell
Get-CaseHoldPolicy "<Case hold policy name>" | %{"--CaseHoldPolicy--";$_|FL;"--CaseHoldRule--";Get-CaseHoldRule -Policy $_.Name | FL} > "eDiscoveryCaseHold.txt"
```

### <a name="collect-all-case-information"></a>Coletar todas as informações do caso

Às vezes, não é aparente quais informações são necessárias para o suporte da Microsoft investigar seu problema. Nessa situação, você pode coletar todas as informações de diagnóstico para uma ocorrência de descoberta eletrônica principal. O *nome da caixa de descoberta eletrônica principal* no seguinte comando é o mesmo que o nome de um caso exibido na página de **descoberta eletrônica principal** no centro de conformidade da Microsoft 365.

```powershell
Get-ComplianceCase "<Core eDiscovery case name>"| %{"$($_.Name)";"`t==Searches==";Get-ComplianceSearch -Case $_.Name | FL;"`t==Search Actions==";Get-ComplianceSearchAction -Case $_.Name |FL;"`t==Holds==";Get-CaseHoldPolicy -Case $_.Name | %{$_|FL;"`t`t ==$($_.Name) Rules==";Get-CaseHoldRule -Policy $_.Name | FL}} > "eDiscoveryCase.txt"
```

## <a name="collect-diagnostic-information-for-advanced-ediscovery"></a>Coletar informações de diagnóstico para descoberta eletrônica avançada

A guia **configurações** em uma ocorrência de descoberta eletrônica avançada permite que você copie rapidamente as informações de diagnóstico para o caso. As informações de diagnóstico são salvas na área de transferência para que você possa colá-las em um arquivo de texto e enviar para o suporte da Microsoft.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique em **Mostrar todos os > de descoberta eletrônica > avançado**.

2. Selecione uma ocorrência e, em seguida, clique na guia **configurações** .

3. Em **informações do caso** , clique em **selecionar**.

4. Na página do menu suspenso, clique em **copiar informações de diagnóstico** para copiar as informações para a área de transferência.

5. Abra um arquivo de texto (no bloco de notas) e cole as informações no arquivo de texto.

6. Salve o arquivo de texto e nomeie-o como `AeD Diagnostic Info YYYY.MM.DD` (por exemplo, `AeD Diagnostic Info 2020.11.03` ).

Após revisar o arquivo e redigir informações confidenciais, envie-o ao engenheiro de suporte da Microsoft que está trabalhando no seu caso.
