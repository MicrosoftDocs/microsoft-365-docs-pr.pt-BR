---
title: Definir políticas de barreira de informações
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: Saiba como definir políticas para barreiras de informações no Microsoft Teams.
ms.openlocfilehash: 11195e588a983bb5617dd3f556734074bc0060b0
ms.sourcegitcommit: af7950d9674f0eab3aee03f9afccff9ca2f4709a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40970839"
---
# <a name="define-policies-for-information-barriers"></a>Definir políticas para barreiras de informações

## <a name="overview"></a>Visão Geral

Com as barreiras de informação, você pode definir políticas projetadas para impedir que determinados segmentos de usuários se comuniquem entre si ou permitir que segmentos específicos se comuniquem apenas com determinados segmentos. As políticas de barreira de informações podem ajudar sua organização a manter a conformidade com normas e regulamentos relevantes do setor e evitar possíveis conflitos de interesse. Para saber mais, confira [barreiras de informação](information-barriers.md). 

Este artigo descreve como planejar, definir, implementar e gerenciar políticas de barreira de informações. Várias etapas estão envolvidas e o fluxo de trabalho é dividido em várias partes. Certifique-se de ler os [pré-requisitos](#prerequisites) e todo o processo antes de começar a definir (ou editar) as políticas de barreira de informações.

> [!TIP]
> Este artigo inclui um [cenário de exemplo](#example-contosos-departments-segments-and-policies) e uma [pasta de trabalho do Excel baixável](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx) para ajudá-lo a planejar e definir suas políticas de barreira de informações.

## <a name="concepts-of-information-barrier-policies"></a>Conceitos de políticas de barreira de informações

Ao definir políticas para barreiras de informações, você trabalhará com atributos de conta de usuário, segmentos, políticas de "bloquear" e/ou "permitir" e aplicativo de política.

- Os **atributos da conta de usuário** são definidos no Azure Active Directory (ou no Exchange Online). Esses atributos podem incluir departamento, cargo, local, nome da equipe e outros detalhes do perfil de trabalho. 

- Os **segmentos** são conjuntos de usuários que são definidos no centro de conformidade & segurança do Office 365 usando um **atributo de conta de usuário**selecionado. (Confira a [lista de atributos com suporte](information-barriers-attributes.md).) 

- **As políticas de barreira de informações** determinam limites ou restrições de comunicação. Ao definir políticas de barreira de informações, escolha um dos dois tipos de políticas:
    - As políticas de "bloqueio" impedem um segmento de se comunicar com outro segmento.
    - As políticas de "permitir" permitem que um segmento se comunique apenas com determinados segmentos.

- O **aplicativo de política** é feito após a definição de todas as políticas de barreira de informações e você está pronto para aplicá-las em sua organização.

## <a name="the-work-flow-at-a-glance"></a>Visão geral do fluxo de trabalho 

|Fase    |O que está envolvido  |
|---------|---------|
|[Verifique se os pré-requisitos foram atendidos](#prerequisites)     |– Verifique se você tem as [licenças e permissões necessárias](information-barriers.md#required-licenses-and-permissions)<br/>– Verifique se o diretório inclui dados para segmentação de usuários<br/>-Habilitar a pesquisa de diretório no escopo para o Microsoft Teams<br/>– Verifique se o registro em log de auditoria está ativado<br/>– Verifique se nenhuma política de catálogo de endereços do Exchange está no local<br/>– Use o PowerShell (exemplos são fornecidos)<br/>– Fornecer consentimento de administrador para o Microsoft Teams (etapas incluídas)          |
|[Parte 1: segmentar usuários em sua organização](#part-1-segment-users)     |– Determinar quais políticas são necessárias<br/>-Criar uma lista de segmentos para definir<br/>– Identificar quais atributos usar<br/>-Definir segmentos em termos de filtros de política        |
|[Parte 2: definir as políticas de barreira de informações](#part-2-define-information-barrier-policies)     |-Definir suas políticas (não se aplica ainda)<br/>-Escolha entre dois tipos (bloquear ou permitir) |
|[Parte 3: aplicar políticas de barreira de informações](#part-3-apply-information-barrier-policies)     |-Definir políticas para status ativo<br/>– Executar o aplicativo de política<br/>-Exibir status da política         |
|(Conforme necessário) [Editar um segmento ou uma política](information-barriers-edit-segments-policies.md)    |-Editar um segmento<br/>– Editar ou remover uma política<br/>– Execute novamente o aplicativo de política<br/>-Exibir status da política         |
|(Conforme necessário) [Solução de problemas](information-barriers-troubleshooting.md)|-Tomar medidas quando as coisas não estiverem funcionando conforme o esperado|

## <a name="prerequisites"></a>Pré-requisitos

Além das [licenças e permissões necessárias](information-barriers.md#required-licenses-and-permissions), certifique-se de que os seguintes requisitos são atendidos: 
     
- **Dados de diretório**. Certifique-se de que a estrutura da sua organização é refletida nos dados do diretório. Para fazer isso, verifique se os atributos da conta de usuário, como associação de grupo, nome do departamento, etc. estão preenchidos corretamente no Azure Active Directory (ou Exchange Online). Para saber mais, confira os seguintes recursos:
  - [Atributos das políticas de barreira de informações](information-barriers-attributes.md)
  - [Adicionar ou atualizar as informações de perfil de um usuário usando o Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)
  - [Configurar propriedades da conta de usuário com o Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)

- **Pesquisa de diretório com escopo**. Antes de definir a primeira política de barreira de informações da sua organização, você deve [habilitar a pesquisa de diretório com escopo no Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search). Aguarde pelo menos 24 horas depois de habilitar a pesquisa de diretório com escopo antes de configurar ou definir as políticas de barreira de informações.

- **Log de auditoria**. Para pesquisar o status de um aplicativo de política, o log de auditoria deve estar ativado. É recomendável fazer isso antes de começar a definir segmentos ou políticas. Para saber mais, confira [Ativar ou desativar a pesquisa de log de auditoria do Office 365](turn-audit-log-search-on-or-off.md).

- **Nenhuma política de catálogo de endereços**. Antes de definir e aplicar as políticas de barreira de informações, certifique-se de que não haja nenhuma política do catálogo de endereços do Exchange. (As barreiras de informação são baseadas nas políticas do catálogo de endereços, mas os dois tipos de políticas não são intercambiáveis.) Se você tiver essas políticas, certifique-se de [remover primeiro as políticas do catálogo de endereços](https://docs.microsoft.com/exchange/address-books/address-book-policies/remove-an-address-book-policy) .

- **PowerShell**. Atualmente, as políticas de barreira de informações são definidas e gerenciadas no centro de conformidade & segurança do Office 365 usando cmdlets do PowerShell. Embora vários exemplos sejam fornecidos neste artigo, você precisará estar familiarizado com os cmdlets e parâmetros do PowerShell. Você também precisará do módulo AzureRM.
    - [Conecte-se ao PowerShell do Centro de Conformidade e Segurança do Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)
    - [Instalar o módulo do Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-2.3.2)

- **Consentimento do administrador para barreiras de informação no Microsoft Teams**. Quando suas políticas estão vigentes, as barreiras de informação podem remover pessoas de sessões de chat que não deveriam estar. Isso ajuda a garantir que sua organização permaneça em conformidade com políticas e regulamentações. Use o procedimento a seguir para permitir que as políticas de barreira de informações funcionem conforme o esperado no Microsoft Teams. 

   1. Execute os seguintes cmdlets do PowerShell:

      ```powershell
      Login-AzureRmAccount 
      $appId="bcf62038-e005-436d-b970-2a472f8c1982" 
      $sp=Get-AzureRmADServicePrincipal -ServicePrincipalName $appId
      if ($sp -eq $null) { New-AzureRmADServicePrincipal -ApplicationId $appId }
      Start-Process  "https://login.microsoftonline.com/common/adminconsent?client_id=$appId"
      ```

   2. Quando solicitado, entre usando sua conta corporativa ou de estudante para o Office 365.

   3. Na caixa de diálogo **permissões solicitadas** , revise as informações e, em seguida, escolha **aceitar**.

Quando todos os pré-requisitos forem atendidos, prossiga para a próxima seção.

> [!TIP]
> Para ajudá-lo a preparar seu plano, um cenário de exemplo está incluído neste artigo. [Veja departamentos, segmentos e políticas da Contoso](#example-contosos-departments-segments-and-policies).<p>Além disso, uma pasta de trabalho do Excel para download está disponível para ajudá-lo a planejar e definir seus segmentos e políticas (e criar seus cmdlets do PowerShell). [Obter a pasta de trabalho](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx). 

## <a name="part-1-segment-users"></a>Parte 1: segmentar usuários

Durante esta fase, você determina quais políticas de barreira de informações são necessárias, fazem uma lista de segmentos para definir e, em seguida, define seus segmentos.

### <a name="determine-what-policies-are-needed"></a>Determinar quais políticas são necessárias

Considerar as normas legais e industriais, que são os grupos dentro da sua organização que precisarão de políticas de barreira de informações? Faça uma lista. Há grupos que devem ser impedidos de se comunicar com outro grupo? Há grupos que devem ter permissão para se comunicar apenas com um ou dois outros grupos? Considere as políticas necessárias para pertencer a um dos dois grupos:
- As políticas de "bloqueio" impedem um grupo de se comunicar com outro grupo.
- As políticas de "permitir" permitem que um grupo se comunique apenas com alguns outros grupos específicos.

Quando você tiver sua lista inicial de grupos e políticas, prossiga para identificar os segmentos necessários. 

### <a name="identify-segments"></a>Identificar segmentos

Além da sua lista inicial de políticas, faça uma lista de segmentos para sua organização. Os usuários que serão incluídos nas políticas de barreira de informações devem pertencer a um segmento. Planeje seus segmentos com cuidado, pois um usuário só pode estar em um segmento. Cada segmento pode ter apenas uma política de barreira de informações aplicada.

> [!IMPORTANT]
> Um usuário só pode estar em um segmento.

Determine quais atributos dos dados de diretório da sua organização você usará para definir segmentos. Você pode usar *Department*, *memberOf*ou qualquer um dos atributos com suporte. Certifique-se de que você tem valores no atributo que você selecionou para os usuários. [Consulte a lista de atributos com suporte para barreiras de informações](information-barriers-attributes.md).

> [!IMPORTANT]
> **Antes de prosseguir para a próxima seção, certifique-se de que os dados do diretório têm valores para atributos que você pode usar para definir segmentos**. Se os dados do diretório não tiverem valores para os atributos que você deseja usar, as contas de usuário devem ser atualizadas para incluir essas informações antes de prosseguir com as barreiras de informação. Para obter ajuda com isso, consulte os seguintes recursos:<br/>- [Configurar propriedades da conta de usuário com o Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)<br/>- [Adicionar ou atualizar as informações de perfil de um usuário usando o Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

### <a name="define-segments-using-powershell"></a>Definir segmentos usando o PowerShell

A definição de segmentos não afeta os usuários; Ele apenas define o estágio para que as políticas de barreira de informações sejam definidas e, em seguida, aplicadas.

1. Use o cmdlet **New-OrganizationSegment** com o parâmetro **UserGroupFilter** que corresponde ao [atributo](information-barriers-attributes.md) que você deseja usar.

    |Sintaxe   |Exemplo  |
    |---------|---------|
    |`New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -eq 'attributevalue'"`     |`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` <p>Neste exemplo, um segmento chamado *HR* é definido usando *HR*, um valor no atributo *Department* . A parte **-EQ** do cmdlet se refere a "igual a". (Como alternativa, você pode usar **-ne** para significar "não é igual a". Consulte [usar "igual a" e "não é igual a" em definições de segmento](#using-equals-and-not-equals-in-segment-definitions).        |

    Após executar cada cmdlet, você verá uma lista de detalhes sobre o novo segmento. Os detalhes incluem o tipo do segmento, que o criou ou modificou pela última vez, e assim por diante. 

2. Repita esse processo para cada segmento que você deseja definir.

    > [!IMPORTANT]
    > Certifique-se de **que seus segmentos não se sobreponham**. Cada usuário que será afetado por barreiras de informação deve pertencer a um único segmento (e apenas um). Nenhum usuário deve pertencer a dois ou mais segmentos. (Consulte [exemplo: segmentos definidos pela contoso](#contosos-defined-segments) neste artigo.)


Após ter definido seus segmentos, vá para [definir políticas de barreira de informações](#part-2-define-information-barrier-policies).

### <a name="using-equals-and-not-equals-in-segment-definitions"></a>Usando "igual a" e "não é igual a" nas definições de segmento

No exemplo a seguir, estamos definindo um segmento de forma que "departamento seja igual a HR". 

|Exemplo  |
|---------|
|`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` <p>Observe que, neste exemplo, a definição de segmento inclui um parâmetro "Equals" indicado como **-EQ**. 
  |

Você também pode definir segmentos usando um parâmetro "not Equals", indicado como **-ne**, conforme mostrado na tabela a seguir:

|Sintaxe  |Exemplo  |
|---------|---------|
|`New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -ne 'attributevalue'"`    |`New-OrganizationSegment -Name "NotSales" -UserGroupFilter "Department -ne 'Sales'"` <p>Neste exemplo, definimos um segmento chamado minhas *vendas* que inclui todos os que não estão em *vendas*. A parte **-ne** do cmdlet se refere a "não é igual a".  |

Além de definir os segmentos usando "igual a" ou "não é igual a", você pode definir um segmento usando os parâmetros "Equals" e "not Equals".

|Exemplo  |
|---------|
|`New-OrganizationSegment -Name "LocalFTE" -UserGroupFilter "Location -eq 'Local'" and "Position -ne 'Temporary'"` <p>Neste exemplo, definimos um segmento chamado *LocalFTE* que inclui pessoas que estão localizadas localmente e cujas posições não estão listadas como *temporárias*.    |

> [!TIP]
> Se possível, use definições de segmento que incluem "-eq" ou "-ne". Tente não definir definições de segmento complexas. 

## <a name="part-2-define-information-barrier-policies"></a>Parte 2: definir as políticas de barreira de informações

Determine se você precisa impedir a comunicação entre determinados segmentos ou limitar a comunicação a determinados segmentos. O ideal é usar o número mínimo de políticas para garantir que sua organização seja compatível com os requisitos jurídicos e do setor.

Com sua lista de segmentos de usuário e as políticas de barreira de informações que você deseja definir, selecione um cenário e siga as etapas. 

- [Cenário 1: bloquear comunicações entre segmentos](#scenario-1-block-communications-between-segments)
- [Cenário 2: permitir que um segmento se comunique apenas com um outro segmento](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)

> [!IMPORTANT]
> **Certifique-se de que ao definir políticas, você não atribua mais de uma política a um segmento**. Por exemplo, se você definir uma política para um segmento chamado *vendas*, não defina uma política adicional para *vendas*.<p>Além disso, conforme você define as políticas de barreira de informações, certifique-se de definir essas políticas como inativas até que você esteja pronto para aplicá-las. A definição de políticas (ou edição) não afeta os usuários até que essas políticas sejam definidas como status ativo e, em seguida, aplicadas.

(Consulte [exemplo: políticas de barreira de informações da Contoso](#contosos-information-barrier-policies) neste artigo.)

### <a name="scenario-1-block-communications-between-segments"></a>Cenário 1: bloquear comunicações entre segmentos

Quando você quiser bloquear segmentos de se comunicar uns com os outros, defina duas políticas: uma para cada direção. Cada política bloqueia apenas a comunicação de uma forma.

Por exemplo, suponha que você queira bloquear comunicações entre o segmento A e o segmento B. Nesse caso, você define uma política impedindo o segmento A de se comunicar com o segmento B e, em seguida, definir uma segunda política para impedir que o segmento B se comunique com o segmento A.

1. Para definir sua primeira política de bloqueio, use o cmdlet **New-InformationBarrierPolicy** com o parâmetro **SegmentsBlocked** . 

    |Sintaxe  |Exemplo  |
    |---------|---------|
    |`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsBlocked "segment2name"`     |`New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p>    Neste exemplo, definimos uma diretiva chamada *Sales-Research* para um segmento chamado *Sales*. Quando ativo e aplicado, essa política impede que as pessoas em *vendas* se comuniquem com pessoas em um segmento chamado *pesquisa*.         |

2. Para definir seu segundo segmento de bloqueio, use o cmdlet **New-InformationBarrierPolicy** com o parâmetro **SegmentsBlocked** novamente, desta vez com os segmentos revertidos.

    |Exemplo  |
    |---------|
    |`New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` <p>    Neste exemplo, definimos uma política chamada *Research-Sales* para impedir que a *pesquisa* se comunique com *vendas*.     |

2. Siga um destes procedimentos:

   - (Se necessário) [Definir uma política para permitir que um segmento se comunique apenas com um outro segmento](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment) 
   - (Após todas as suas políticas serem definidas) [Aplicar políticas de barreira de informações](#part-3-apply-information-barrier-policies)

### <a name="scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment"></a>Cenário 2: permitir que um segmento se comunique apenas com um outro segmento

1. Para permitir que um segmento se comunique com apenas um outro segmento, use o cmdlet **New-InformationBarrierPolicy** com o parâmetro **SegmentsAllowed** . 

    |Sintaxe  |Exemplo  |
    |---------|---------|
    |`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name"`     |`New-InformationBarrierPolicy -Name "Manufacturing-HR" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR" -State Inactive` <p>    Neste exemplo, definimos uma diretiva chamada *Manufacturing-HR* para um segmento chamado *Manufacturing*. Quando ativo e aplicado, essa política permite que as pessoas na *fabricação* se comuniquem somente com pessoas em um segmento chamado *RH*. (Nesse caso, a *fabricação* não pode se comunicar com usuários que não fazem parte do *RH*.)         |

    **Se necessário, você pode especificar vários segmentos com este cmdlet, conforme mostrado no exemplo a seguir.**

    |Sintaxe  |Exemplo  |
    |---------|---------|
    |`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name", "segment3name"`     |`New-InformationBarrierPolicy -Name "Research-HRManufacturing" -AssignedSegment "Research" -SegmentsAllowed "HR","Manufacturing" -State Inactive` <p>Neste exemplo, definimos uma política que permite que o segmento de *pesquisa* se comunique apenas com o *HR* e o *Manufacturing*.        |

    Repita essa etapa para cada política que você deseja definir para permitir que segmentos específicos se comuniquem apenas com determinados segmentos específicos.

2. Siga um destes procedimentos:

   - (Se necessário) [Definir uma política para bloquear comunicações entre segmentos](#scenario-1-block-communications-between-segments) 
   - (Após todas as suas políticas serem definidas) [Aplicar políticas de barreira de informações](#part-3-apply-information-barrier-policies)

## <a name="part-3-apply-information-barrier-policies"></a>Parte 3: aplicar políticas de barreira de informações

As políticas de barreira de informações não estão em vigor até que você as defina como status ativo e, em seguida, aplique as políticas.

1. Use o cmdlet **Get-InformationBarrierPolicy** para ver uma lista de políticas que foram definidas. Observe o status e a identidade (GUID) de cada política.

    Possuem`Get-InformationBarrierPolicy`

2. Para definir uma política para o status ativo, use o cmdlet **set-InformationBarrierPolicy** com um parâmetro **Identity** e o parâmetro **State** definido como **ativo**. 

    |Sintaxe  |Exemplo  |
    |---------|---------|
    |`Set-InformationBarrierPolicy -Identity GUID -State Active`     |`Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -State Active` <p>    Neste exemplo, definimos uma política de barreira de informações com o GUID *43c37853-ea10-4b90-a23d-ab8c93772471* para o status ativo.   |

    Repita essa etapa conforme apropriado para cada política.

3. Ao concluir a configuração das políticas de barreira de informações para o status ativo, use o cmdlet **Start-InformationBarrierPoliciesApplication** no centro de conformidade & segurança do Office 365.

    Possuem`Start-InformationBarrierPoliciesApplication`

    Após aproximadamente meia hora, as políticas são aplicadas, usuário por usuário, para sua organização. Se sua organização for grande, pode levar 24 horas (ou mais) para que esse processo seja concluído. (Como uma diretriz geral, leva cerca de uma hora para processar as contas de usuário 5.000.)

## <a name="view-status-of-user-accounts-segments-policies-or-policy-application"></a>Exibir o status de contas de usuário, segmentos, políticas ou aplicativos de política

Com o PowerShell, você pode exibir o status de contas de usuário, segmentos, políticas e aplicativos de política, conforme listado na tabela a seguir.

|Para exibir este  |Faça isto  |
|---------|---------|
|Contas de usuário     |Use o cmdlet **Get-InformationBarrierRecipientStatus** com parâmetros de identidade. <p>Possuem`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p>Você pode usar qualquer valor que identifique exclusivamente cada usuário, como nome, alias, nome diferenciado, nome de domínio canônico, endereço de email ou GUID. <p>Exemplo: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p>Neste exemplo, nos referimos a duas contas de usuário no Office 365: *meganb* para *Megan*e *alexw* para *Alex*. <p>(Você também pode usar esse cmdlet para um único usuário: `Get-InformationBarrierRecipientStatus -Identity <value>`) <p>Este cmdlet retorna informações sobre usuários, como valores de atributos e quaisquer políticas de barreira de informação aplicadas.|
|Segui     |Use o cmdlet **Get-OrganizationSegment** .<p>Possuem`Get-OrganizationSegment` <p>Isso exibirá uma lista de todos os segmentos definidos para sua organização.         |
|Políticas de barreira de informações     |Use o cmdlet **Get-InformationBarrierPolicy** . <p> Possuem`Get-InformationBarrierPolicy` <p>Isso exibirá uma lista de políticas de barreira de informações que foram definidas e seu status.       |
|O aplicativo de política de barreira de informações mais recente     | Use o cmdlet **Get-InformationBarrierPoliciesApplicationStatus** . <p>Possuem`Get-InformationBarrierPoliciesApplicationStatus`<p>    Isso exibirá informações sobre se o aplicativo de política foi concluído, falhou ou está em andamento.       |
|Todos os aplicativos de política de barreira de informações|Use`Get-InformationBarrierPoliciesApplicationStatus -All $true`<p>Isso exibirá informações sobre se o aplicativo de política foi concluído, falhou ou está em andamento.|

## <a name="what-if-i-need-to-remove-or-change-policies"></a>E se eu precisar remover ou alterar políticas?

Os recursos estão disponíveis para ajudá-lo a gerenciar suas políticas de barreira de informações.

- Se algo der errado com as barreiras de informações, consulte [Solucionando problemas de barreiras de informações](information-barriers-troubleshooting.md).

- Para impedir que as políticas sejam aplicadas, consulte [parar um aplicativo de política](information-barriers-edit-segments-policies.md#stop-a-policy-application).

- Para remover uma política de barreira de informações, consulte [remover uma política](information-barriers-edit-segments-policies.md#remove-a-policy).

- Para fazer alterações em segmentos ou políticas, consulte [Editar (ou remover) políticas de barreira de informações](information-barriers-edit-segments-policies.md).

## <a name="example-contosos-departments-segments-and-policies"></a>Exemplo: departamentos, segmentos e políticas da contoso

Para ver como uma organização pode abordar a definição de segmentos e políticas, considere o exemplo a seguir.

### <a name="contosos-departments-and-plan"></a>Departamentos e planos da contoso

A contoso tem cinco departamentos: RH, vendas, marketing, pesquisa e produção. Para manter a conformidade com as regulamentações do setor, as pessoas de alguns departamentos não devem se comunicar com outros departamentos, conforme listado na tabela a seguir:

|Segmento  |Pode falar com  |Não é possível falar com  |
|---------|---------|---------|
|HUMANOS     |Todos         |(sem restrições)         |
|Vendas     |RH, marketing, manufatura         |Pesquisar         |
|Marketing     |Todos         |(sem restrições)         |
|Pesquisar     |RH, marketing, manufatura        |Vendas     |
|Fabricação |RH, marketing |Qualquer pessoa que não seja RH ou marketing |

Com isso em mente, o plano da Contoso inclui três políticas de barreira de informações:

1. Uma política projetada para impedir que as vendas se comuniquem com a pesquisa (e outra política para impedir que a pesquisa se comunique com as vendas)
2. Uma política projetada para permitir que a fabricação se comunique apenas com RH e marketing 

Não é necessário definir políticas de RH ou marketing.

### <a name="contosos-defined-segments"></a>Segmentos definidos pela contoso

A Contoso usará o atributo Department no Azure Active Directory para definir segmentos, da seguinte maneira:

|Departamento  |Definição de segmento  |
|---------|---------|
|HUMANOS     | `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"`        |
|Vendas     | `New-OrganizationSegment -Name "Sales" -UserGroupFilter "Department -eq 'Sales'"`        |
|Marketing     | `New-OrganizationSegment -Name "Marketing" -UserGroupFilter "Department -eq 'Marketing'"`        |
|Pesquisar     | `New-OrganizationSegment -Name "Research" -UserGroupFilter "Department -eq 'Research'"`        |
|Fabricação     | `New-OrganizationSegment -Name "Manufacturing" -UserGroupFilter "Department -eq 'Manufacturing'"`        |

Com os segmentos definidos, a contoso prossegue para definir políticas. 

### <a name="contosos-information-barrier-policies"></a>Políticas de barreira de informações da contoso

A contoso define três políticas, conforme descrito na tabela a seguir:

|Política  |Definição de política  |
|---------|---------|
|Política 1: impedir que as vendas se comuniquem com a pesquisa     | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> Neste exemplo, a política de barreira de informações é chamada de *pesquisa de vendas*. Quando essa política estiver ativa e aplicada, ela ajudará a impedir que os usuários que estão no segmento de vendas se comuniquem com os usuários no segmento de pesquisa. Esta é uma política unidirecional; não impedirá que a pesquisa se comunique com as vendas. Para isso, a política 2 é necessária.      |
|Política 2: impedir que a pesquisa se comunique com as vendas     | `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` <p> Neste exemplo, a política de barreira de informações é chamada *de pesquisa-vendas*. Quando essa política estiver ativa e aplicada, ela ajudará a impedir que os usuários que estão no segmento de pesquisa se comuniquem com os usuários no segmento de vendas.       |
|Política 3: permitir a fabricação se comunicar somente com RH e marketing     | `New-InformationBarrierPolicy -Name "Manufacturing-HRMarketing" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Marketing" -State Inactive` <p>Nesse caso, a política de barreira de informações é chamada de *fabricação-HRMarketing*. Quando essa política estiver ativa e aplicada, a fabricação só poderá se comunicar com o RH e o marketing. Observe que o HR e o marketing não estão restritos à comunicação com outros segmentos. |

Com segmentos e políticas definidas, a contoso aplica as políticas executando o cmdlet **Start-InformationBarrierPoliciesApplication** . 

Quando isso é concluído, a contoso é compatível com os requisitos jurídicos e do setor.

## <a name="related-articles"></a>Artigos relacionados

- [Obter uma visão geral das barreiras de informação](information-barriers.md)

- [Barreiras de informação no Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)
