---
title: Definir políticas de barreira de informações
description: Saiba como definir políticas para barreiras de informações no Microsoft Teams.
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 09e680d2bcf8f1e0fd5237adbf640349741c26fd
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126580"
---
# <a name="define-information-barrier-policies"></a>Definir políticas de barreira de informações

Com barreiras de informações, você pode definir políticas projetadas para impedir que determinados segmentos de usuários se comuniquem uns com os outros ou permitir que segmentos específicos se comuniquem apenas com determinados outros segmentos. As políticas de barreira de informações podem ajudar sua organização a manter a conformidade com padrões e regulamentações relevantes do setor e evitar possíveis conflitos de interesse. Para saber mais, consulte [Barreiras de informações.](information-barriers.md)

Este artigo descreve como planejar, definir, implementar e gerenciar políticas de barreira de informações. Várias etapas estão envolvidas, e o fluxo de trabalho é dividido em várias partes. Leia os [pré-requisitos](#prerequisites) e todo o processo antes de começar a definir (ou editar) políticas de barreira de informações.

> [!TIP]
> Este artigo inclui um cenário de [exemplo e](#example-contosos-departments-segments-and-policies) uma planilha do Excel baixável para [ajudá-lo](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx) a planejar e definir suas políticas de barreira de informações.

## <a name="concepts-of-information-barrier-policies"></a>Conceitos de políticas de barreira de informações

Ao definir políticas para barreiras de informações, você trabalhará com atributos de conta de usuário, segmentos, políticas de "bloqueio" e/ou "permitir" e aplicativo de política.

- Os atributos da conta de usuário são definidos no Azure Active Directory (ou no Exchange Online). Esses atributos podem incluir departamento, cargo, local, nome da equipe e outros detalhes do perfil de trabalho. 
- Segmentos são conjuntos de usuários definidos no Centro de Conformidade e Segurança & usando um atributo de **conta de usuário selecionado.** (Consulte a [lista de atributos com suporte.)](information-barriers-attributes.md)
- As políticas de barreira de informações determinam limites ou restrições de comunicação. Ao definir políticas de barreira de informações, você escolhe entre dois tipos de políticas:
    - As políticas "Bloquear" impedem que um segmento se comunique com outro segmento.
    - As políticas "Permitir" permitem que um segmento se comunique apenas com determinados outros segmentos.
- O aplicativo de política é feito depois que todas as políticas de barreira de informações são definidas e você está pronto para aplicá-las em sua organização.

## <a name="the-work-flow-at-a-glance"></a>Visão geral do fluxo de trabalho 

|**Fase**|**O que está envolvido**|
|:--------|:------------------|
| [Certifique-se de que os pré-requisitos foram atendidos](#prerequisites) | - Verifique se você tem [as licenças e permissões necessárias](information-barriers.md#required-licenses-and-permissions)<br/>- Verifique se o diretório inclui dados para segmentação de usuários<br/>- Habilitar a pesquisa de diretório com escopo para o Microsoft Teams<br/>- Certifique-se de que o log de auditoria está ligado<br/>- Certifique-se de que nenhuma política de agenda do Exchange está em operação<br/>- Usar o PowerShell (são fornecidos exemplos)<br/>– Fornecer consentimento de administrador para o Microsoft Teams (as etapas estão incluídas) |
| [Parte 1: Segmentar usuários em sua organização](#part-1-segment-users) | - Determinar quais políticas são necessárias<br/>- Fazer uma lista de segmentos a definir<br/>- Identificar quais atributos usar<br/>- Definir segmentos em termos de filtros de política |
| [Parte 2: Definir políticas de barreira de informações](#part-2-define-information-barrier-policies) | - Definir suas políticas (não se aplicam ainda)<br/>- Escolher entre dois tipos (bloquear ou permitir) |
| [Parte 3: Aplicar políticas de barreira de informações](#part-3-apply-information-barrier-policies) | - Definir políticas para o status ativo<br/>- Executar o aplicativo de política<br/>- Exibir o status da política |
| (Conforme necessário) [Editar um segmento ou uma política](information-barriers-edit-segments-policies.md) | - Editar um segmento<br/>- Editar ou remover uma política<br/>- Rerun the policy application<br/>- Exibir o status da política |
| (Conforme necessário) [Solução de problemas](information-barriers-troubleshooting.md)| - Tomar medidas quando as coisas não estão funcionando conforme o esperado|

## <a name="prerequisites"></a>Pré-requisitos

Além das [licenças e permissões necessárias,](information-barriers.md#required-licenses-and-permissions)certifique-se de que os seguintes requisitos sejam atendidos:

- Dados de diretório – certifique-se de que a estrutura da sua organização seja refletida nos dados de diretório. Para realizar essa ação, certifique-se de que os atributos da conta de usuário, como a associação ao grupo, o nome do departamento etc. sejam preenchidos corretamente no Azure Active Directory (ou no Exchange Online). Para saber mais, confira os seguintes recursos:
  - [Atributos das políticas de barreira de informações](information-barriers-attributes.md)
  - [Adicionar ou atualizar as informações de perfil de um usuário usando o Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)
  - [Configurar propriedades da conta de usuário com o Office 365 PowerShell](/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell)

- Pesquisa de diretório com escopo - Antes de definir a primeira política de barreira de informações da sua organização, você deve habilitar a pesquisa de diretório com [escopo no Microsoft Teams.](/MicrosoftTeams/teams-scoped-directory-search) Aguarde pelo menos 24 horas após a habilitação da pesquisa de diretório com escopo antes de configurar ou definir políticas de barreira de informações.

- Licença EXO - as políticas de IB funcionam somente se os usuários de destino foram atribuídos com uma licença EXO.

- Log de auditoria - Para procurar o status de um aplicativo de política, o log de auditoria deve estar ligado. Recomendamos que você habilita a auditoria antes de começar a definir segmentos ou políticas. Para saber mais, confira Ativar ou desativar a [pesquisa de log de auditoria.](turn-audit-log-search-on-or-off.md)

- Sem políticas de lista de endereços - Antes de definir e aplicar políticas de barreira de informações, certifique-se de que nenhuma política de agenda do Exchange está em uso. As barreiras de informações são baseadas em políticas de agendamento de endereço, mas os dois tipos de políticas não são compatíveis. Se você tiver essas políticas, certifique-se de [remover suas políticas de agendas primeiro.](/exchange/address-books/address-book-policies/remove-an-address-book-policy) Depois que as políticas de barreira de informações são  habilitadas e você tem o [](/exchange/address-books/hierarchical-address-books/hierarchical-address-books) agendamento hierárquico habilitado, todos os usuários que não estão incluídos em um segmento de barreira de informações verão o livro de endereços hierárquico no Exchange online.

- PowerShell – Atualmente, as políticas de barreira de informações são definidas e gerenciadas no Centro de Conformidade e Segurança do Office 365 & usando cmdlets do PowerShell. Embora vários exemplos sejam fornecidos neste artigo, você precisará estar familiarizado com cmdlets e parâmetros do PowerShell. Você também precisará do módulo do Azure PowerShell.
    - [Conectar-se ao PowerShell do Centro de Conformidade e Segurança](/powershell/exchange/connect-to-scc-powershell)
    - [Instalar o módulo do Azure PowerShell](/powershell/azure/install-az-ps?view=azps-2.3.2)

- Consentimento do administrador para barreiras de informações no Microsoft Teams - Quando suas políticas estão em uso, as barreiras de informações podem remover as pessoas das sessões de chat em que elas não deveriam estar. Essa configuração ajuda a garantir que sua organização permaneça em conformidade com políticas e regulamentos. Use o procedimento a seguir para permitir que as políticas de barreira de informações funcionem conforme o esperado no Microsoft Teams.

   1. Execute os seguintes cmdlets do PowerShell:

      ```powershell
      Connect-AzureAD 
      $appId="bcf62038-e005-436d-b970-2a472f8c1982" 
      $sp=Get-AzADServicePrincipal -ServicePrincipalName $appId
      if ($sp -eq $null) { New-AzADServicePrincipal -ApplicationId $appId }
      Start-Process  "https://login.microsoftonline.com/common/adminconsent?client_id=$appId"
      ```

   2. Quando solicitado, entre usando sua conta de trabalho ou de estudante do Office 365.

   3. Na caixa **de diálogo Permissões solicitadas,** revise as informações e escolha **Aceitar**.

Quando todos os pré-requisitos são atendidos, prossiga para a próxima seção.

> [!TIP]
> Para ajudá-lo a preparar seu plano, um cenário de exemplo está incluído neste artigo. [Consulte departamentos, segmentos](#example-contosos-departments-segments-and-policies)e políticas da Contoso.<p>Além disso, uma planilha do Excel para download está disponível para ajudá-lo a planejar e definir seus segmentos e políticas (e criar seus cmdlets do PowerShell). [Obter a workbook](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx).

## <a name="part-1-segment-users"></a>Parte 1: Segmentar usuários

Durante essa fase, você determina quais políticas de barreira de informações são necessárias, faz uma lista de segmentos a definir e, em seguida, define seus segmentos.

### <a name="determine-what-policies-are-needed"></a>Determinar quais políticas são necessárias

Considerando regulamentos legais e do setor, quem são os grupos dentro de sua organização que precisarão de políticas de barreira de informações? Faça uma lista. Há algum grupo que deve ser impedido de se comunicar com outro grupo? Há algum grupo que deve ter permissão para se comunicar apenas com um ou dois outros grupos? Pense nas políticas de que você precisa como pertencente a um dos dois grupos:

- As políticas "Bloquear" impedem que um grupo se comunique com outro grupo.
- As políticas "Permitir" permitem que um grupo se comunique apenas com determinados outros grupos específicos.

Quando você tiver sua lista inicial de grupos e políticas, prossiga para identificar os segmentos necessários.

### <a name="identify-segments"></a>Identificar segmentos

Além da lista inicial de políticas, faça uma lista de segmentos para sua organização. Os usuários que serão incluídos nas políticas de barreira de informações devem pertencer a um segmento. Planeje seus segmentos com cuidado, pois um usuário só pode estar em um segmento. Cada segmento pode ter apenas uma política de barreira de informações aplicada.

> [!IMPORTANT]
> Um usuário só pode estar em um segmento.

Determine quais atributos nos dados de diretório da sua organização você usará para definir segmentos. Você pode usar *Department*, *MemberOf* ou qualquer um dos atributos com suporte. Certifique-se de que você tenha valores no atributo selecionado para os usuários. [Consulte a lista de atributos com suporte para barreiras de informações.](information-barriers-attributes.md)

> [!IMPORTANT]
> **Antes de prosseguir para a próxima seção, certifique-se** de que seus dados de diretório têm valores para atributos que você pode usar para definir segmentos. Se os dados de diretório não têm valores para os atributos que você deseja usar, as contas de usuário devem ser atualizadas para incluir essas informações antes de prosseguir com as barreiras de informações. Para obter ajuda com isso, consulte os seguintes recursos:<br/>- [Configurar propriedades de conta de usuário com o Office 365 PowerShell](/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell)<br/>- [Adicionar ou atualizar as informações de perfil de um usuário usando o Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

### <a name="define-segments-using-powershell"></a>Definir segmentos usando o PowerShell

A definição de segmentos não afeta os usuários; ele apenas define o estágio para que as políticas de barreira de informações sejam definidas e, em seguida, aplicadas.

1. Use o cmdlet **New-OrganizationSegment** com o **parâmetro UserGroupFilter** que corresponde ao [atributo](information-barriers-attributes.md) que você deseja usar.

    |**Sintaxe**|**Exemplo**|
    |:---------|:----------|
    | `New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -eq 'attributevalue'"` |`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` <p>Neste exemplo, um segmento chamado *RH* é definido usando *RH*, um valor no *atributo Department* . A **parte -eq** do cmdlet refere-se a "igual a". (Como alternativa, você pode usar **-ne** para significar "diferente de". See [Using "equals" and "not equals" in segment definitions](#using-equals-and-not-equals-in-segment-definitions).) |

    Depois de executar cada cmdlet, você deverá ver uma lista de detalhes sobre o novo segmento. Os detalhes incluem o tipo do segmento, quem o criou ou modificou pela última vez e assim por diante. 

2. Repita esse processo para cada segmento que você deseja definir.

    > [!IMPORTANT]
    > **Certifique-se de que seus segmentos não se sobreponham.** Cada usuário que será afetado pelas barreiras de informações deve pertencer a um (e apenas um) segmento. Nenhum usuário deve pertencer a dois ou mais segmentos. (Consulte [Exemplo: segmentos definidos da Contoso](#contosos-defined-segments) neste artigo.)

Depois de definir seus segmentos, prossiga para definir políticas de barreira [de informações.](#part-2-define-information-barrier-policies)

### <a name="using-equals-and-not-equals-in-segment-definitions"></a>Usando "igual a" e "não é igual" em definições de segmento

No exemplo a seguir, estamos definindo um segmento de forma que "Departamento é igual a RH". 

|**Exemplo**|**Observação**|
|:----------|:-------|
|`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` | Observe que, neste exemplo, a definição de segmento inclui um parâmetro "igual a" denodo **como -eq**. |

Você também pode definir segmentos usando um parâmetro "não é igual", indicado como **-ne,** conforme mostrado na tabela a seguir:

|**Sintaxe**|**Exemplo**|
|:---------|:----------|
| `New-OrganizationSegment -Name "NotSales" -UserGroupFilter "Department -ne 'Sales'"` | Neste exemplo, definimos um segmento chamado *NotSales* que inclui todas as pessoas que não estão em *Vendas*. A **parte -ne** do cmdlet refere-se a "not equals". |

Além de definir segmentos usando "igual a" ou "não igual a", você pode definir um segmento usando os parâmetros "equals" e "not equals". Você também pode definir filtros de grupo complexos usando *operadores AND* e *OR lógicos.*

|**Sintaxe**|**Exemplo**|
|:---------|:----------|
| `New-OrganizationSegment -Name "LocalFTE" -UserGroupFilter "Location -eq 'Local'" -and "Position -ne 'Temporary'"` | Neste exemplo, definimos um segmento chamado *LocalFTE* que inclui as pessoas que estão localizadas localmente e cujas posições não estão listadas como *Temporárias*. |
| `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "MemberOf -eq 'group1@contoso.com'' -and MemberOf -ne 'group3@contoso.com'"`| Neste exemplo, definimos um segmento chamado *Segment1* que inclui pessoas que são membros do group1@contoso.com e não membros do group3@contoso.com. |
| `New-OrganizationSegment -Name "Segment2" -UserGroupFilter "MemberOf -eq 'group2@contoso.com' -or MemberOf -ne 'group3@contoso.com'"` | Neste exemplo, definimos um segmento chamado *Segment2* que inclui pessoas que são membros do group2@contoso.com e não membros do group3@contoso.com. |
| `New-OrganizationSegment -Name "Segment1and2" -UserGroupFilter "(MemberOf -eq 'group1@contoso.com' -or MemberOf -eq 'group2@contoso.com') -and MemberOf -ne 'group3@contoso.com'"`| Neste exemplo, definimos um segmento chamado *Segment1and2* que inclui membros de group1@contoso.com e group2@contoso.com e não membros group3@contoso.com. |

> [!TIP]
> Se possível, use definições de segmento que incluem "-eq" ou "-ne". Tente não definir definições de segmento complexas.

## <a name="part-2-define-information-barrier-policies"></a>Parte 2: Definir políticas de barreira de informações

Determine se você precisa impedir comunicações entre determinados segmentos ou limitar as comunicações a determinados segmentos. Idealmente, você usará o número mínimo de políticas para garantir que sua organização está em conformidade com os requisitos legais e do setor.

Com sua lista de segmentos de usuário e as políticas de barreira de informações que você deseja definir, selecione um cenário e siga as etapas.

- [Cenário 1: Bloquear comunicações entre segmentos](#scenario-1-block-communications-between-segments)
- [Cenário 2: Permitir que um segmento se comunique apenas com um outro segmento](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)

> [!IMPORTANT]
> **Certifique-se de que, ao definir políticas, você não atribua mais de uma política a um segmento.** Por exemplo, se você definir uma política para um segmento chamado *Vendas,* não defina uma política adicional para *Vendas*.<p> Além disso, ao definir políticas de barreira de informações, certifique-se de definir essas políticas como status inativo até que você esteja pronto para aplicá-las. Definir (ou editar) políticas não afeta os usuários até que essas políticas sejam definidas para o status ativo e depois aplicadas.

(Veja [exemplo: as políticas de barreira de](#contosos-information-barrier-policies) informações da Contoso neste artigo.)

### <a name="scenario-1-block-communications-between-segments"></a>Cenário 1: Bloquear comunicações entre segmentos

Quando você deseja impedir que segmentos se comunique uns com os outros, defina duas políticas: uma para cada direção. Cada política bloqueia a comunicação apenas de uma só maneira.

Por exemplo, suponha que você queira bloquear as comunicações entre o Segmento A e o Segmento B. Nesse caso, defina uma política impedindo que o Segmento A se comunique com o Segmento B e defina uma segunda política para impedir que o Segmento B se comunique com o Segmento A.

1. Para definir sua primeira política de bloqueio, use o cmdlet **New-InformationBarrierPolicy** com **o parâmetro SegmentsBlocked.**

    |**Sintaxe** | **Exemplo**| |**--------|:----------| |`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsBlocked "segment2name"` | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> Neste exemplo, definimos uma política chamada *Sales-Research* para um segmento chamado *Vendas*. Quando ativa e aplicada, essa política impede que as pessoas em *Vendas* se comunique com pessoas em um segmento chamado *Pesquisa*. |

2. Para definir seu segundo segmento de bloqueio, use o cmdlet **New-InformationBarrierPolicy** com o parâmetro **SegmentsBlocked** novamente, desta vez com os segmentos invertidos.

    |**Exemplo**|**Observação**|
    |:----------|:-------|
    |`New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` | Neste exemplo, definimos uma política chamada *Research-Sales* para impedir que *Research* se comunique com *Vendas.* |

3. Prossiga para uma das seguintes ações:

   - (Se necessário) [Definir uma política para permitir que um segmento se comunique somente com um outro segmento](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment) 
   - (Depois que todas as políticas são definidas) [Aplicar políticas de barreira de informações](#part-3-apply-information-barrier-policies)

### <a name="scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment"></a>Cenário 2: Permitir que um segmento se comunique apenas com um outro segmento

1. Para permitir que um segmento se comunique com apenas um outro segmento, use o cmdlet **New-InformationBarrierPolicy** com o parâmetro **SegmentsAllowed.**

    |**Sintaxe**|**Exemplo**|
    |:----------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name","segment1name"` | `New-InformationBarrierPolicy -Name "Manufacturing-HR" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Manufacturing" -State Inactive` <p> Neste exemplo, definimos uma política chamada *Manufacturing-HR* para um segmento chamado *Fabricação.* Quando ativa e aplicada, essa política permite que as pessoas em *Fabricação* se comuniquem somente com pessoas em um segmento chamado *RH*. (Nesse caso, a *Fabricação não* pode se comunicar com usuários que não fazem parte do *RH.)* |

    **Se necessário, você pode especificar vários segmentos com esse cmdlet, conforme mostrado no exemplo a seguir.**

    |**Sintaxe**|**Exemplo**|
    |:---------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name", "segment3name","segment1name"` | `New-InformationBarrierPolicy -Name "Research-HRManufacturing" -AssignedSegment "Research" -SegmentsAllowed "HR","Manufacturing","Research" -State Inactive` <p> Neste exemplo, definimos uma política que permite que o segmento *Research* se comunique somente com *RH* e *Fabricação.* |

    Repita essa etapa para cada política que você deseja definir para permitir que segmentos específicos se comuniquem apenas com determinados outros segmentos específicos.

2. Prossiga para uma das seguintes ações:

   - (Se necessário) [Definir uma política para bloquear comunicações entre segmentos](#scenario-1-block-communications-between-segments) 
   - (Depois que todas as políticas são definidas) [Aplicar políticas de barreira de informações](#part-3-apply-information-barrier-policies)

## <a name="part-3-apply-information-barrier-policies"></a>Parte 3: Aplicar políticas de barreira de informações

As políticas de barreira de informações não entrarão em vigor até que elas sejam definidas como status ativo e, em seguida, aplicar as políticas.

1. Use o cmdlet **Get-InformationBarrierPolicy** para ver uma lista de políticas que foram definidas. Observe o status e a identidade (GUID) de cada política.

    Sintaxe: `Get-InformationBarrierPolicy`

2. Para definir uma política como status ativo, use o cmdlet **Set-InformationBarrierPolicy** com um parâmetro **Identity** e o parâmetro **State** definido como **Active**. 

    |**Sintaxe**|**Exemplo**|
    |:---------|:----------|
    | `Set-InformationBarrierPolicy -Identity GUID -State Active` | `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -State Active` <p> Neste exemplo, definimos uma política de barreira de informações que tem o GUID *43c37853-ea10-4b90-a23d-ab8c93772471* como status ativo. |

    Repita essa etapa conforme apropriado para cada política.

3. Quando terminar de definir suas políticas de barreira de informações para o status ativo, use o cmdlet **Start-InformationBarrierPoliciesApplication** no Centro de Conformidade e & Segurança.

    Sintaxe: `Start-InformationBarrierPoliciesApplication`

    Depois de `Start-InformationBarrierPoliciesApplication` executar, deixe 30 minutos para que o sistema comece a aplicar as políticas. O sistema aplica políticas usuário por usuário. O sistema processa cerca de 5.000 contas de usuário por hora.

## <a name="view-status-of-user-accounts-segments-policies-or-policy-application"></a>Exibir o status de contas de usuário, segmentos, políticas ou aplicativo de política

Com o PowerShell, você pode exibir o status de contas de usuário, segmentos, políticas e aplicativos de política, conforme listado na tabela a seguir.

|**Para exibir essas informações**|**Tomar esta ação**|
|:---------------|:----------|
| Contas de usuário | Use o cmdlet **Get-InformationBarrierRecipientStatus** com parâmetros de Identidade. <p> Sintaxe: `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> É possível usar qualquer valor que identifique com exclusividade cada usuário, como nome, alias, nome diferenciado, nome de domínio canônico, endereço de email ou GUID. <p> Exemplo: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> Neste exemplo, nos referimos a duas contas de usuário no Office 365: *meganb* para *Megan* e *alexw* para *Alex*. <p> (Você também pode usar esse cmdlet para um único usuário: `Get-InformationBarrierRecipientStatus -Identity <value>` ) <p> Este cmdlet retorna informações sobre usuários, como valores de atributos e quaisquer políticas de barreira de informações aplicadas.|
| Segmentos | Use o cmdlet **Get-OrganizationSegment.**<p> Sintaxe: `Get-OrganizationSegment` <p> Este cmdlet exibirá uma lista de todos os segmentos definidos para sua organização. |
| Políticas de barreira de informações | Use o cmdlet **Get-InformationBarrierPolicy.** <p> Sintaxe: `Get-InformationBarrierPolicy` <p> Este cmdlet exibirá uma lista de políticas de barreira de informações que foram definidas e seu status. |
| O aplicativo de política de barreira de informações mais recente | Use o cmdlet **Get-InformationBarrierPoliciesApplicationStatus.** <p> Sintaxe: `Get-InformationBarrierPoliciesApplicationStatus`<p> Este cmdlet exibirá informações sobre se o aplicativo de política foi concluído, se falhou ou está em andamento. |
| Todos os aplicativos de política de barreira de informações|Usar o `Get-InformationBarrierPoliciesApplicationStatus -All`<p> Este cmdlet exibirá informações sobre se o aplicativo de política foi concluído, se falhou ou está em andamento.|

<!-- IN the " The most recent information barrier policy application, add link to troubleshooting topic -->

## <a name="what-if-i-need-to-remove-or-change-policies"></a>E se eu precisar remover ou alterar políticas?

Os recursos estão disponíveis para ajudá-lo a gerenciar suas políticas de barreira de informações.

- Se algo der errado com barreiras de informações, consulte [Solução de problemas de barreiras de informações.](information-barriers-troubleshooting.md)
- Para impedir a aplicação de políticas, consulte [Parar um aplicativo de política.](information-barriers-edit-segments-policies.md#stop-a-policy-application)
- Para remover uma política de barreira de informações, [consulte Remover uma política.](information-barriers-edit-segments-policies.md#remove-a-policy)
- Para fazer alterações em segmentos ou políticas, consulte [Editar (ou remover)](information-barriers-edit-segments-policies.md)políticas de barreira de informações.

## <a name="example-contosos-departments-segments-and-policies"></a>Exemplo: departamentos, segmentos e políticas da Contoso

Para ver como uma organização pode abordar a definição de segmentos e políticas, considere o exemplo a seguir.

### <a name="contosos-departments-and-plan"></a>Departamentos e planos da Contoso

A Contoso tem cinco departamentos: RH, Vendas, Marketing, Pesquisa e Fabricação. Para manter a conformidade com os regulamentos do setor, as pessoas em alguns departamentos não devem se comunicar com outros departamentos, conforme listado na tabela a seguir:

|**Segmento**|**Pode falar com**|**Não é possível falar com**|
|:----------|:--------------|:-----------------|
| HR | Todos | (sem restrições) |
| Vendas | RH, Marketing, Fabricação | Pesquisar |
| Marketing | Todos | (sem restrições) |
| Pesquisar | RH, Marketing, Fabricação | Vendas |
| Indústria | RH, Marketing | Qualquer pessoa que não seja RH ou Marketing |

Para essa estrutura, o plano da Contoso inclui três políticas de barreira de informações:

1. Uma política projetada para impedir que Vendas se comunique com a Pesquisa (e outra política para impedir que a Pesquisa se comunique com vendas).
2. Uma política projetada para permitir que a Fabricação se comunique somente com RH e Marketing.

Para esse cenário, não é necessário definir políticas para RH ou Marketing.

### <a name="contosos-defined-segments"></a>Segmentos definidos da Contoso

A Contoso usará o atributo Department no Azure Active Directory para definir segmentos, da seguinte forma:

|**Departamento**|**Definição de segmento**|
|:-------------|:---------------------|
| HR | `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` |
| Vendas | `New-OrganizationSegment -Name "Sales" -UserGroupFilter "Department -eq 'Sales'"` |
| Marketing | `New-OrganizationSegment -Name "Marketing" -UserGroupFilter "Department -eq 'Marketing'"` |
| Pesquisar | `New-OrganizationSegment -Name "Research" -UserGroupFilter "Department -eq 'Research'"` |
| Indústria | `New-OrganizationSegment -Name "Manufacturing" -UserGroupFilter "Department -eq 'Manufacturing'"` |

Com os segmentos definidos, a Contoso continua a definir políticas.

### <a name="contosos-information-barrier-policies"></a>Políticas de barreira de informações da Contoso

A Contoso define três políticas, conforme descrito na tabela a seguir:

|**Política**|**Definição de política**|
|:---------|:--------------------|
| **Política 1: Impedir que vendas se comunique com a Pesquisa** | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> Neste exemplo, a política de barreira de informações é chamada *sales-research*. Quando essa política estiver ativa e aplicada, ela ajudará a impedir que os usuários que estão no segmento vendas se comuniquem com usuários no segmento Pesquisa. Essa política é uma política de uso único; isso não impedirá que a Pesquisa se comunique com Vendas. Para isso, a Política 2 é necessária. |
| **Política 2: Impedir que a Pesquisa se comunique com vendas** | `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` <p> Neste exemplo, a política de barreira de informações é chamada *de Research-Sales*. Quando essa política estiver ativa e aplicada, ela ajudará a impedir que os usuários que estão no segmento Pesquisa se comuniquem com usuários no segmento vendas. |
| **Política 3: Permitir que a Fabricação se comunique somente com RH e Marketing** | `New-InformationBarrierPolicy -Name "Manufacturing-HRMarketing" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Marketing","Manufacturing" -State Inactive` <p> Nesse caso, a política de barreira de informações é chamada *manufacturing-HRMarketing*. Quando essa política está ativa e aplicada, a Fabricação pode se comunicar somente com RH e Marketing. RH e Marketing não estão restritos a se comunicar com outros segmentos. |

Com segmentos e políticas definidos, a Contoso aplica as políticas executando o cmdlet **Start-InformationBarrierPoliciesApplication.**

Quando o cmdlet terminar, a Contoso está em conformidade com os requisitos legais e do setor.

## <a name="resources"></a>Recursos

- [Obter uma visão geral das barreiras de informações](information-barriers.md)
- [Saiba mais sobre barreiras de informações no Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [Saiba mais sobre barreiras de informações no SharePoint Online](/sharepoint/information-barriers)
- [Saiba mais sobre barreiras de informações no OneDrive](/onedrive/information-barriers)
