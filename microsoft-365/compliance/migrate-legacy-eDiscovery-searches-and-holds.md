---
title: Migrar pesquisas de descoberta eletrônica herdadas e isenções para o centro de conformidade da Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: 216ec3853f1b55c7fb34de3a236f50094202bca5
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352461"
---
# <a name="migrate-legacy-ediscovery-searches-and-holds-to-the-microsoft-365-compliance-center"></a>Migrar pesquisas de descoberta eletrônica herdadas e isenções para o centro de conformidade da Microsoft 365

O centro de conformidade da Microsoft 365 oferece uma experiência aprimorada para uso da descoberta eletrônica, incluindo: maior confiabilidade, melhor desempenho e vários recursos adaptados para fluxos de trabalho de descoberta eletrônica, incluindo casos para organizar seu conteúdo por questão, revisar conjuntos para revisar conteúdo e análise para ajudar a analisar dados para revisão, como agrupamento Near-Duplicate, encadeamento de email, análise de temas

Para ajudar os clientes a aproveitar as funcionalidades novas e aprimoradas, este artigo fornece orientação básica sobre como migrar pesquisas de descoberta eletrônica in-loco e bloqueios do centro de administração do Exchange para o centro de conformidade do Microsoft 365.

> [!NOTE]
> Como há muitos cenários diferentes, este artigo fornece orientação geral para fazer a transição de pesquisas e se comporta para uma caixa de descoberta eletrônica principal no centro de conformidade da Microsoft 365. O uso de casos de descoberta eletrônica nem sempre é necessário, mas eles adicionam uma camada extra de segurança, permitindo que você atribua permissões para controlar quem tem acesso aos casos de descoberta eletrônica em sua organização.

## <a name="before-you-begin"></a>Antes de começar

- Você precisa ser membro do grupo de função Gerenciador de descoberta eletrônica no centro de conformidade do & de segurança para executar os comandos do PowerShell descritos neste artigo. Você também precisa ser membro do grupo de função gerenciamento de descoberta no centro de administração do Exchange.

- Este artigo fornece orientação sobre como criar um controle de descoberta eletrônica. A política de retenção será aplicada às caixas de correio por meio de um processo assíncrono. Ao criar um bloqueio de descoberta eletrônica, você deve criar um CaseHoldPolicy e um CaseHoldRule, caso contrário, a isenção não será criada e os locais de conteúdo não serão colocados em espera.

## <a name="step-1-connect-to-exchange-online-powershell-and-security--compliance-center-powershell"></a>Etapa 1: conectar-se ao PowerShell do centro de conformidade e segurança & do Exchange Online

A primeira etapa é conectar-se ao PowerShell do centro de conformidade e segurança & do Exchange Online. Você pode copiar o script a seguir, colá-lo em uma janela do PowerShell e executá-lo. Você será solicitado a fornecer credenciais para a organização à qual você deseja se conectar. 

```powershell
$UserCredential = Get-Credential
$sccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $sccSession -DisableNameChecking
$exoSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $exoSession -AllowClobber -DisableNameChecking
```

Você precisa executar os comandos nas etapas a seguir nesta sessão do PowerShell.

## <a name="step-2-get-a-list-of-in-place-ediscovery-searches-by-using-get-mailboxsearch"></a>Etapa 2: obter uma lista de pesquisas de descoberta eletrônica in-loco usando Get-MailboxSearch

Depois de autenticar, você pode obter uma lista de pesquisas de descoberta eletrônica in-loco executando o cmdlet **Get-MailboxSearch** . Copie e cole o seguinte comando no PowerShell e execute-o. Uma lista de pesquisas será listada com seus nomes e o status de qualquer bloqueio in-loco.

```powershell
Get-MailboxSearch
```

A saída do cmdlet será semelhante à seguinte:

![Exemplo de Get-MailboxSearch do PowerShell](../media/MigrateLegacyeDiscovery1.png)

## <a name="step-3-get-information-about-the-in-place-ediscovery-searches-and-in-place-holds-you-want-to-migrate"></a>Etapa 3: obter informações sobre as pesquisas de descoberta eletrônica in-loco e bloqueios in-loco que você deseja migrar

Novamente, você usará o cmdlet **Get-MailboxSearch** , mas desta vez para obter as propriedades da pesquisa. Você pode armazenar essas propriedades em uma variável para uso posterior. O exemplo a seguir armazena os resultados do cmdlet **Get-MailboxSearch** em uma variável e, em seguida, exibe as propriedades da pesquisa.

```powershell
$search = Get-MailboxSearch -Identity "Search 1"
```

```powershell
$search | FL
```

A saída desses dois comandos será semelhante à seguinte:

![Exemplo de saída do PowerShell usando Get-MailboxSearch para uma pesquisa individual](../media/MigrateLegacyeDiscovery2.png)

> [!NOTE]
> A duração do bloqueio in-loco neste exemplo está indefinida (*ItemHoldPeriod: Unlimited*). Isso é típico para cenários de descoberta eletrônica e investigação legal. Se a duração da retenção tiver um valor diferente de indefinido, o motivo provavelmente será que a retenção está sendo usada para reter o conteúdo em um cenário de retenção. Em vez de usar os cmdlets de descoberta eletrônica no PowerShell do centro de conformidade & de segurança para cenários de retenção, recomendamos que você use [New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy) e [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule) para reter conteúdo. O resultado do uso desses cmdlets será semelhante ao uso de **New-CaseHoldPolicy** e **New-CaseHoldRule**, mas você poderá especificar um período de retenção e uma ação de retenção, como excluir o conteúdo depois que o período de retenção expirar. Além disso, usar os cmdlets de retenção não exige que você associe o bloqueio de retenção a uma ocorrência de descoberta eletrônica.

## <a name="step-4-create-a-case-in-the-microsoft-365-compliance-center"></a>Etapa 4: criar um caso no centro de conformidade da Microsoft 365

Para criar um bloqueio de descoberta eletrônica, você precisa criar uma ocorrência de descoberta eletrônica para associar a isenção. O exemplo a seguir cria uma ocorrência de descoberta eletrônica usando um nome de sua escolha. Armazenaremos as propriedades do novo caso em uma variável para uso posterior. Você pode exibir essas propriedades executando o `$case | FL` comando após criar o caso.

```powershell
$case = New-ComplianceCase -Name "[Case name of your choice]"
```
![Exemplo de execução do comando New-ComplianceCase](../media/MigrateLegacyeDiscovery3.png)

## <a name="step-5-create-the-ediscovery-hold"></a>Etapa 5: criar o bloqueio de descoberta eletrônica

Depois que o caso é criado, você pode criar a isenção e associá-la ao caso que você criou na etapa anterior. É importante lembrar que você deve criar uma política de bloqueio de caso e uma regra de bloqueio de caso. Se a regra de bloqueio de caso não for criada após a criação da política de retenção de caso, a descoberta eletrônica não será criada e qualquer conteúdo não será colocado em espera.

Execute os comandos a seguir para recriar a descoberta eletrônica suspensa que você deseja migrar. Estes exemplos usam as propriedades de bloqueio in-loco da etapa 3 que você deseja migrar. O primeiro comando cria uma nova política de bloqueio de caso e salva as propriedades em uma variável. O segundo comando cria a regra de bloqueio de caso correspondente.

```powershell
$policy = New-CaseHoldPolicy -Name $search.Name -Case $case.Identity -ExchangeLocation $search.SourceMailboxes
```

```powershell
New-CaseHoldRule -Name $search.Name -Policy $policy.Identity
```

![Exemplo de uso de cmdlets do NewCaseHoldPolicy e do NewCaseHoldRule](../media/MigrateLegacyeDiscovery4.png)

## <a name="step-6-verify-the-ediscovery-hold"></a>Etapa 6: verificar a retenção de descoberta eletrônica

Para garantir que não houve problemas na criação da isenção, é bom verificar se o status da distribuição de retenção foi bem-sucedido. Distribuição significa que a retenção foi aplicada a todos os locais de conteúdo especificados no parâmetro *ExchangeLocation* na etapa anterior. Para fazer isso, você pode executar o cmdlet **Get-CaseHoldPolicy** . Como as propriedades salvas na variável *$Policy* que você criou na etapa anterior não são atualizadas automaticamente na variável, é necessário executar novamente o cmdlet para verificar se a distribuição foi bem-sucedida. Pode levar entre 5 minutos e 24 horas para que as políticas de bloqueio de caso sejam distribuídas com êxito.

Execute o seguinte comando para verificar se a descoberta eletrônica foi distribuída com êxito.

```powershell
Get-CaseHoldPolicy -Identity $policy.Identity | Select name, DistributionStatus
```

O valor de **Success** para a propriedade *DistributionStatus* indica que a retenção foi colocada com êxito nos locais de conteúdo. Se a distribuição ainda não estiver concluída, um valor de **Pending** será exibido.

![Exemplo de Get-CaseHoldPolicy do PowerShell](../media/MigrateLegacyeDiscovery5.png)

## <a name="step-7-create-the-search"></a>Etapa 7: criar a pesquisa

A última etapa é recriar a pesquisa que você identificou na etapa 3 e associá-la ao caso. Após criar a pesquisa, você poderá executá-la usando o cmdlet **Start-ComplianceSearch** ou executar mais tarde.

```powershell
New-ComplianceSearch -Name $search.Name -ExchangeLocation $search.SourceMailboxes -ContentMatchQuery $search.SearchQuery -Case $case.name
```

![Exemplo do PowerShell New-ComplianceSearch](../media/MigrateLegacyeDiscovery6.png)

## <a name="step-8-verify-the-case-hold-and-search-in-the-microsoft-365-compliance-center"></a>Etapa 8: verificar a ocorrência, a retenção e a pesquisa no centro de conformidade da Microsoft 365

Para certificar-se de que tudo está configurado corretamente, vá para o centro de conformidade da Microsoft 365 em [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique em **descoberta eletrônica > Core**.

![EDiscovery do centro de conformidade da Microsoft 365](../media/MigrateLegacyeDiscovery7.png)

O caso que você criou na etapa 3 está listado na página de **descoberta eletrônica principal** . Abra o caso e, em seguida, observe a suspensão que você criou na etapa 4, listada na guia **isenções** . Você pode clicar na isenção para ver os detalhes, incluindo o número de caixas de correio em que a retenção é aplicada e o status da distribuição.

![bloqueios de descoberta eletrônica no centro de conformidade da Microsoft 365](../media/MigrateLegacyeDiscovery8.png)

A pesquisa criada na etapa 7 está listada na guia **pesquisas** da ocorrência de descoberta eletrônica.

![pesquisa de ocorrência de descoberta eletrônica no centro de conformidade da Microsoft 365](../media/MigrateLegacyeDiscovery9.png)

Se você migrar uma pesquisa de descoberta eletrônica in-loco, mas não associá-la a uma ocorrência de descoberta eletrônica, ela será listada na página de pesquisa de conteúdo no centro de conformidade da Microsoft 365.

## <a name="more-information"></a>Mais informações

- Para obter mais informações sobre descoberta eletrônica in-loco & bloqueios no centro de administração do Exchange, consulte:
  
  - [Descoberta Eletrônica In-loco](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery)

  - [Bloqueio In-loco e Retenção de Litígio](https://docs.microsoft.com/exchange/security-and-compliance/in-place-and-litigation-holds)

- Para obter mais informações sobre os cmdlets do PowerShell usados no artigo, consulte:

  - [Get-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/get-mailboxsearch)
  
  - [New-ComplianceCase](https://docs.microsoft.com/powershell/module/exchange/new-compliancecase)

  - [New-CaseHoldPolicy](https://docs.microsoft.com/powershell/module/exchange/new-caseholdpolicy)
  
  - [New-CaseHoldRule](https://docs.microsoft.com/powershell/module/exchange/new-caseholdrule)

  - [Get-CaseHoldPolicy](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)
  
  - [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch)

  - [Start-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/start-compliancesearch)

- Para obter mais informações sobre o centro de conformidade da Microsoft 365, consulte [visão geral do centro de conformidade da microsoft 365](microsoft-365-compliance-center.md).
