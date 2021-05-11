---
title: Migrar pesquisas e retês de Descobertas EDiscovery herdado para o Microsoft 365 de conformidade
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
ms.openlocfilehash: aaae5e6bddc48f29cc0766fe26a1976672c7dd49
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52310783"
---
# <a name="migrate-legacy-ediscovery-searches-and-holds-to-the-microsoft-365-compliance-center"></a>Migrar pesquisas e retês de Descobertas EDiscovery herdado para o Microsoft 365 de conformidade

O centro de conformidade do Microsoft 365 oferece uma experiência aprimorada para o uso de Descoberta Eletrônico, incluindo: maior confiabilidade, melhor desempenho e muitos recursos personalizados para fluxos de trabalho de Descoberta Eletrônico, incluindo casos para organizar seu conteúdo por questão, conjuntos de revisão para revisar conteúdo e análise para ajudar a analisar dados para revisão, como agrupação quase duplicada, threading de email, análise de temas e codificação preditiva.

Para ajudar os clientes In-Place aproveitar a funcionalidade nova e aprimorada, este artigo fornece orientações básicas sobre como migrar pesquisas e retês de descobertas e descobertas In-Place do centro de administração do Exchange para o centro de conformidade Microsoft 365.

> [!NOTE]
> Como há muitos cenários diferentes, este artigo fornece orientações gerais para fazer a transição de pesquisas e retém para um caso de Descoberta eDiscovery principal no centro de conformidade Microsoft 365 de segurança. O uso de casos de Descoberta Digital nem sempre é necessário, mas eles adicionam uma camada extra de segurança, ao permitir que você atribua permissões para controlar quem tem acesso aos casos de Descoberta Digital em sua organização.

## <a name="before-you-begin"></a>Antes de começar

- Você precisa ser membro do grupo de funções do Gerenciador de Descobertas e no Centro de Conformidade & Segurança para executar os comandos do PowerShell descritos neste artigo. Você também precisa ser membro do grupo de função Gerenciamento de Descoberta no centro de Exchange de administração.

- Este artigo fornece orientações sobre como criar uma ressalto de Descoberta e. A política de espera será aplicada a caixas de correio por meio de um processo assíncrono. Ao criar uma contenção de Descoberta eDiscovery, você deve criar um CaseHoldPolicy e CaseHoldRule, caso contrário, a responsabilidade não será criada e os locais de conteúdo não serão colocados em espera.

## <a name="step-1-connect-to-exchange-online-powershell-and-security--compliance-center-powershell"></a>Etapa 1: Conexão para Exchange Online PowerShell e Segurança & Centro de Conformidade do PowerShell

A primeira etapa é conectar-se Exchange Online powershell e segurança & Centro de Conformidade do PowerShell. Você pode copiar o script a seguir, colar-o em uma janela do PowerShell e, em seguida, execute-o. Você será solicitado a solicitar credenciais para a organização à que deseja se conectar. 

```powershell
$UserCredential = Get-Credential
$sccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $sccSession -DisableNameChecking
$exoSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $exoSession -AllowClobber -DisableNameChecking
```

Você precisa executar os comandos nas etapas a seguir nesta sessão do PowerShell.

## <a name="step-2-get-a-list-of-in-place-ediscovery-searches-by-using-get-mailboxsearch"></a>Etapa 2: obter uma lista de In-Place de Descoberta In-Place usando Get-MailboxSearch

Após a autenticação, você pode obter uma lista de In-Place de Descoberta Eletrônica executando o cmdlet **Get-MailboxSearch.** Copie e colar o seguinte comando no PowerShell e execute-o. Uma lista de pesquisas será listada com seus nomes e o status de qualquer In-Place Holds.

```powershell
Get-MailboxSearch
```

A saída do cmdlet será semelhante à seguinte:

![Exemplo do PowerShell Get-MailboxSearch](../media/MigrateLegacyeDiscovery1.png)

## <a name="step-3-get-information-about-the-in-place-ediscovery-searches-and-in-place-holds-you-want-to-migrate"></a>Etapa 3: obter informações sobre as pesquisas In-Place descoberta e In-Place que você deseja migrar

Novamente, você usará o cmdlet **Get-MailboxSearch,** mas desta vez para obter as propriedades da pesquisa. Você pode armazenar essas propriedades em uma variável para uso posteriormente. O exemplo a seguir armazena os resultados do cmdlet **Get-MailboxSearch** em uma variável e exibe as propriedades da pesquisa.

```powershell
$search = Get-MailboxSearch -Identity "Search 1"
```

```powershell
$search | FL
```

A saída desses dois comandos será semelhante à seguinte:

![Exemplo de saída do PowerShell de usar Get-MailboxSearch para uma pesquisa individual](../media/MigrateLegacyeDiscovery2.png)

> [!NOTE]
> A duração da In-Place neste exemplo é indefinida (*ItemHoldPeriod: Unlimited*). Isso é típico para cenários de Descoberta e Investigação Legal. Se a duração da retenção tiver um valor diferente do indefinido, o motivo provavelmente será porque a retenção está sendo usada para reter conteúdo em um cenário de retenção. Em vez de usar os cmdlet & s de Descoberta Eletrônica no Centro de Conformidade e Segurança do PowerShell para cenários de retenção, recomendamos que você use [New-RetentionCompliancePolicy](/powershell/module/exchange/new-retentioncompliancepolicy) e [New-RetentionComplianceRule](/powershell/module/exchange/new-retentioncompliancerule) para reter conteúdo. O resultado do uso desses cmdlets será semelhante ao uso de **New-CaseHoldPolicy** e **New-CaseHoldRule**, mas você poderá especificar um período de retenção e uma ação de retenção, como a exclusão de conteúdo após o período de retenção expirar. Além disso, o uso dos cmdlets de retenção não exige que você associe os retenções de retenção a um caso de Descoberta Eletrônica.

## <a name="step-4-create-a-case-in-the-microsoft-365-compliance-center"></a>Etapa 4: Criar um caso no centro Microsoft 365 Conformidade

Para criar uma responsabilidade de Descoberta eDiscovery, você precisa criar um caso de Descoberta e Para associar a responsabilidade. O exemplo a seguir cria um caso de Descoberta E usando um nome de sua escolha. Armazenaremos as propriedades do novo caso em uma variável para uso posteriormente. Você pode exibir essas propriedades executando o `$case | FL` comando depois de criar o caso.

```powershell
$case = New-ComplianceCase -Name "[Case name of your choice]"
```
![Exemplo de execução do New-ComplianceCase comando](../media/MigrateLegacyeDiscovery3.png)

## <a name="step-5-create-the-ediscovery-hold"></a>Etapa 5: Criar a espera de Descoberta e

Depois que o caso for criado, você poderá criar a iseção e associá-la ao caso que você criou na etapa anterior. É importante lembrar que você deve criar uma política de espera de caso e uma regra de ressarção de caso. Se a regra de espera de caso não for criada depois que você criou a política de responsabilidade de caso, a responsabilidade de Descoberta eDiscovery não será criada e qualquer conteúdo não será colocado em espera.

Execute os seguintes comandos para re-criar a reenconsução de Descoberta e que você deseja migrar. Esses exemplos usam as propriedades In-Place a partir da Etapa 3 que você deseja migrar. O primeiro comando cria uma nova política de espera de caso e salva as propriedades em uma variável. O segundo comando cria a regra de espera de caso correspondente.

```powershell
$policy = New-CaseHoldPolicy -Name $search.Name -Case $case.Identity -ExchangeLocation $search.SourceMailboxes
```

```powershell
New-CaseHoldRule -Name $search.Name -Policy $policy.Identity
```

![Exemplo de uso de cmdlets NewCaseHoldPolicy e NewCaseHoldRule](../media/MigrateLegacyeDiscovery4.png)

## <a name="step-6-verify-the-ediscovery-hold"></a>Etapa 6: Verificar a espera de Descoberta e

Para certificar-se de que não houve problemas na criação da espera, é bom verificar se o status de distribuição de espera é bem-sucedido. Distribuição significa que a espera foi aplicada a todos os locais de conteúdo especificados no parâmetro *ExchangeLocation* na etapa anterior. Para fazer isso, você pode executar o cmdlet **Get-CaseHoldPolicy.** Como as propriedades salvas na *variável* $policy que você criou na etapa anterior não são atualizadas automaticamente na variável, você precisa reprisar o cmdlet para verificar se a distribuição foi bem-sucedida. Pode levar entre 5 minutos e 24 horas para que as políticas de espera de caso sejam distribuídas com êxito.

Execute o comando a seguir para verificar se a ressarção de Descoberta e Foi distribuída com êxito.

```powershell
Get-CaseHoldPolicy -Identity $policy.Identity | Select name, DistributionStatus
```

O valor **de Success para** a propriedade *DistributionStatus* indica que a ressarção foi colocada com êxito nos locais de conteúdo. Se a distribuição ainda não estiver concluída, um valor **de Pendente** será exibido.

![Exemplo Get-CaseHoldPolicy PowerShell](../media/MigrateLegacyeDiscovery5.png)

## <a name="step-7-create-the-search"></a>Etapa 7: Criar a pesquisa

A última etapa é criar a pesquisa que você identificou na Etapa 3 e associá-la ao caso. Depois de criar a pesquisa, você pode executar usando o cmdlet **Start-ComplianceSearch** ou executar posteriormente.

```powershell
New-ComplianceSearch -Name $search.Name -ExchangeLocation $search.SourceMailboxes -ContentMatchQuery $search.SearchQuery -Case $case.name
```

![Exemplo New-ComplianceSearch PowerShell](../media/MigrateLegacyeDiscovery6.png)

## <a name="step-8-verify-the-case-hold-and-search-in-the-microsoft-365-compliance-center"></a>Etapa 8: Verificar o caso, a espera e a pesquisa no Microsoft 365 de conformidade

Para certificar-se de que tudo está definido corretamente, vá para o centro de conformidade Microsoft 365 em , e clique em [https://compliance.microsoft.com](https://compliance.microsoft.com) **Descoberta > Core**.

![Microsoft 365 Descoberta eDiscovery do Centro de Conformidade](../media/MigrateLegacyeDiscovery7.png)

O caso criado na Etapa 3 está listado na página **Descoberta Principal.** Abra a caixa e observe a espera que você criou na Etapa 4 listada na **guia** Espera. Você pode selecionar a espera para ver detalhes na página de sobrevoo, incluindo o número de caixas de correio às quais a 1000 caixas de correio é aplicada e o status de distribuição.

![O eDiscovery é ressado no Microsoft 365 de conformidade](../media/MigrateLegacyeDiscovery8.png)

A pesquisa que você criou na Etapa 7 está listada na guia **Pesquisas** do caso.

![Pesquisa de caso de descoberta de eDiscovery no Microsoft 365 de conformidade](../media/MigrateLegacyeDiscovery9.png)

Se você migrar uma pesquisa de Descoberta In-Place eDiscovery, mas não associá-la a um caso de Descoberta eDiscovery, ela será listada na página de pesquisa de conteúdo no centro de conformidade Microsoft 365.

## <a name="more-information"></a>Mais informações

- Para obter mais informações sobre In-Place & eDiscovery no centro de administração Exchange, consulte:
  
  - [Descoberta Eletrônica In-loco](/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery)

  - [Bloqueio In-loco e Retenção de Litígio](/exchange/security-and-compliance/in-place-and-litigation-holds)

- Para obter mais informações sobre os cmdlets do PowerShell usados no artigo, consulte:

  - [Get-MailboxSearch](/powershell/module/exchange/get-mailboxsearch)
  
  - [New-ComplianceCase](/powershell/module/exchange/new-compliancecase)

  - [New-CaseHoldPolicy](/powershell/module/exchange/new-caseholdpolicy)
  
  - [New-CaseHoldRule](/powershell/module/exchange/new-caseholdrule)

  - [Get-CaseHoldPolicy](/powershell/module/exchange/get-caseholdpolicy)
  
  - [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch)

  - [Start-ComplianceSearch](/powershell/module/exchange/start-compliancesearch)

- Para obter mais informações sobre o Microsoft 365 de conformidade, consulte [Overview of the Microsoft 365 compliance center](microsoft-365-compliance-center.md).