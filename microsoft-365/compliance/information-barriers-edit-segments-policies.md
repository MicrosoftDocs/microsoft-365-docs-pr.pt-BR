---
title: Editar políticas de barreira de informações
f1.keywords:
- NOCSH
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
description: Saiba como editar ou remover políticas para barreiras de informação.
ms.openlocfilehash: 7e027d9026818eefacd1c84949e3211c19ae8cf9
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547459"
---
# <a name="edit-or-remove-information-barrier-policies"></a>Editar (ou remover) políticas de barreira de informações

Depois de [definir as políticas de barreira de informações](information-barriers-policies.md), talvez seja necessário fazer alterações nas políticas ou nos segmentos de usuário, como parte da [solução de problemas](information-barriers-troubleshooting.md) ou de manutenção regular. Use este artigo como uma guia.

## <a name="what-do-you-want-to-do"></a>O que você deseja fazer?

|Ação  |Descrição |
|---------|---------|
|[Editar atributos da conta de usuário](#edit-user-account-attributes)     |Preencha os atributos no Azure Active Directory que podem ser usados para definir segmentos.<br/>Editar os atributos da conta de usuário quando os usuários não estão incluídos nos segmentos que devem ser, para alterar quais segmentos os usuários estão ou para definir segmentos usando atributos diferentes.         |
|[Editar um segmento](#edit-a-segment)     |Edite segmentos quando você quiser alterar o modo como um segmento é definido. <br/>Por exemplo, você pode ter originalmente definido segmentos usando *Departamento* e agora deseja usar outro atributo, como *memberOf*.         |
|[Editar uma política](#edit-a-policy)     |Edite uma política de barreira de informações quando quiser alterar a forma como uma política funciona.<br/>Por exemplo, em vez de bloquear comunicações entre dois segmentos, você pode decidir permitir que as comunicações ocorram apenas entre determinados segmentos.         |
|[Definir uma política para o status inativo](#set-a-policy-to-inactive-status)     |Defina uma política como status inativo quando você quiser fazer alterações em uma política ou quando não quiser que uma política entre em vigor.         |
|[Remover uma política](#remove-a-policy)     |Remova uma política de barreira de informações quando não precisar mais de uma determinada política no local.         |
|[Parar um aplicativo de política](#stop-a-policy-application)     |Faça isso quando você quiser interromper o processo de aplicação de políticas de barreira de informações.<br/>Observe que a interrupção de um aplicativo de política não é instantânea e não desfaz políticas já aplicadas aos usuários.         |
|[Definir políticas para barreiras de informações](information-barriers-policies.md)     |Defina uma política de barreira de informações quando você ainda não tiver essas políticas funcionando, e você deve restringir ou limitar a comunicação entre grupos de usuários específicos.         |
|[Solução de problemas de barreiras de informações](information-barriers-troubleshooting.md)     |Consulte este artigo quando você tiver problemas inesperados com barreiras de informação.         |

> [!IMPORTANT]
> Para executar as tarefas descritas neste artigo, você deve receber uma função apropriada, como uma das seguintes:<br/>– Administrador global do Microsoft 365 Enterprise<br/>-Administrador global<br/>-Administrador de conformidade<br/>– Gerenciamento de conformidade do IB (esta é uma nova função!)<p>Para saber mais sobre os pré-requisitos para barreiras de informações, consulte [pré-requisitos (para políticas de barreira de informações)](information-barriers-policies.md#prerequisites).<p>Certifique-se de [se conectar ao PowerShell do centro de conformidade do & de segurança](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).

## <a name="edit-user-account-attributes"></a>Editar atributos da conta de usuário

Use este procedimento para editar atributos que são usados para segmentar usuários. 

Por exemplo, se você estiver usando um atributo Department e uma ou mais contas de usuário não tiver atualmente nenhum valor listado para departamento, você deverá editar essas contas de usuário para incluir informações de departamento. 

Os atributos da conta de usuário são usados para definir os segmentos de modo que as políticas de barreira de informações possam ser atribuídas.

1. Para exibir detalhes de uma conta de usuário específica, como valores de atributo e segmentos atribuídos, use o cmdlet **Get-InformationBarrierRecipientStatus** com parâmetros de identidade. 

    |Sintaxe  |Exemplo  |
    |---------|---------|
    |`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p>   Você pode usar qualquer valor que identifique exclusivamente cada usuário, como nome, alias, nome diferenciado, nome de domínio canônico, endereço de email ou GUID. <p>   (Você também pode usar esse cmdlet para um único usuário: `Get-InformationBarrierRecipientStatus -Identity <value>` )      |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw`  <p>   Neste exemplo, nos referimos a duas contas de usuário no Office 365: *meganb* para *Megan*e *alexw* para *Alex*.         |

2. Determine o atributo que você deseja editar para o (s) perfil (es) da conta de usuário. Consulte [atributos para políticas de barreira de informações](information-barriers-attributes.md) para obter mais detalhes. 

3. Edite uma ou mais contas de usuário para incluir valores para o atributo selecionado na etapa anterior. Para fazer isso, use um dos seguintes procedimentos:

    - Para editar uma única conta, confira [Adicionar ou atualizar as informações de perfil de um usuário usando o Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).

    - Para editar várias contas (ou usar o PowerShell para editar uma única conta), confira [Configurar Propriedades da conta de usuário com o Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell).

## <a name="edit-a-segment"></a>Editar um segmento

Use este procedimento para editar a definição de um segmento de usuário. Por exemplo, você pode alterar o nome de um segmento ou o filtro que é usado para determinar quem está incluído no segmento.

1. Para exibir todos os segmentos existentes, use o cmdlet **Get-OrganizationSegment** .
    
    Possuem `Get-OrganizationSegment`

    Você verá uma lista de segmentos e detalhes para cada um, como tipo de segmento, seu valor UserGroupFilter, que o criou ou modificou pela última vez, GUID e assim por diante.

    > [!TIP]
    > Imprima ou salve sua lista de segmentos para referência posterior. Por exemplo, se quiser editar um segmento, você precisará saber seu nome ou identificar o valor (usado com o parâmetro Identity).

2. Para editar um segmento, use o cmdlet **set-OrganizationSegment** com o parâmetro **Identity** e detalhes relevantes. 

    |Sintaxe  |Exemplo  |
    |---------|---------|
    |`Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"`     |`Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"` <p>Neste exemplo, para o segmento que tem o GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*, atualizamos o nome do departamento para "HRDept".         |

Ao concluir a edição dos segmentos da sua organização, você pode [definir](information-barriers-policies.md#part-2-define-information-barrier-policies) ou [Editar](#edit-a-policy) as políticas de barreira de informações.

## <a name="edit-a-policy"></a>Editar uma política

1. Para exibir uma lista de políticas de barreira de informações atuais, use o cmdlet **Get-InformationBarrierPolicy** .

    Possuem `Get-InformationBarrierPolicy`

    Na lista de resultados, identifique a política que você deseja alterar. Observe o GUID e o nome da política.

2. Use o cmdlet **set-InformationBarrierPolicy** com um parâmetro **Identity** e especifique as alterações que deseja fazer.

    Exemplo: Suponha que uma política foi definida para bloquear o segmento de *pesquisa* de se comunicar com os segmentos *vendas* e *marketing* . A política foi definida usando este cmdlet: `New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`
    
    Suponha que queremos alterá-lo para que as pessoas no segmento de *pesquisa* só possam se comunicar com pessoas no segmento de *RH* . Para fazer essa alteração, usamos este cmdlet: `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`

    Neste exemplo, alteramos "SegmentsBlocked" para "SegmentsAllowed" e especificamos o segmento *HR* .

3. Quando terminar de editar uma política, certifique-se de aplicar as alterações. (Consulte [aplicar políticas de barreira de informações](information-barriers-policies.md#part-3-apply-information-barrier-policies).)

## <a name="set-a-policy-to-inactive-status"></a>Definir uma política para o status inativo

1. Para exibir uma lista de políticas de barreira de informações atuais, use o cmdlet **Get-InformationBarrierPolicy** .

    Possuem `Get-InformationBarrierPolicy`

    Na lista de resultados, identifique a política que você deseja alterar (ou remover). Observe o GUID e o nome da política.

2. Para definir o status da política como inativo, use o cmdlet **set-InformationBarrierPolicy** com um parâmetro Identity e o parâmetro State definido como inativo.

    |Sintaxe  |Exemplo  |
    |---------|---------|
    |`Set-InformationBarrierPolicy -Identity GUID -State Inactive`     |`Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive` <p>Neste exemplo, definimos uma política de barreira de informações que tem o GUID *43c37853-ea10-4b90-a23d-ab8c9377247* para um status inativo.         |

3. Para aplicar suas alterações, use o cmdlet **Start-InformationBarrierPoliciesApplication** .

    Possuem `Start-InformationBarrierPoliciesApplication`

    As alterações são aplicadas, usuário por usuário, para sua organização. Se sua organização for grande, pode levar 24 horas (ou mais) para que esse processo seja concluído. (Como uma diretriz geral, leva cerca de uma hora para processar as contas de usuário 5.000.)

Neste ponto, uma ou mais políticas de barreira de informações estão definidas para o status inativo. A partir daqui, você pode fazer o seguinte:
- Mantê-lo como está (uma política definida como status inativo não tem efeito sobre os usuários)
- [Editar uma política](#edit-a-policy) 
- [Remover uma política](#remove-a-policy)

## <a name="remove-a-policy"></a>Remover uma política

1. Para exibir uma lista de políticas de barreira de informações atuais, use o cmdlet **Get-InformationBarrierPolicy** .

    Possuem `Get-InformationBarrierPolicy`

    Na lista de resultados, identifique a política que você deseja remover. Observe o GUID e o nome da política. Certifique-se de que a política está definida como status inativo.

2. Use o cmdlet **Remove-InformationBarrierPolicy** com um parâmetro Identity.

    |Sintaxe  |Exemplo  |
    |---------|---------|
    |`Remove-InformationBarrierPolicy -Identity GUID`     |`Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471` <p>Neste exemplo, estamos removendo a política com GUID *43c37853-ea10-4b90-a23d-ab8c93772471*.          |

    Quando solicitado, confirme a alteração.

3. Repita as etapas 1-2 para cada política que você deseja remover.

4. Quando terminar de remover as políticas, aplique as alterações. Para fazer isso, use o cmdlet **Start-InformationBarrierPoliciesApplication** .

    Possuem `Start-InformationBarrierPoliciesApplication`

    As alterações são aplicadas, usuário por usuário, para sua organização. Se sua organização for grande, pode levar 24 horas (ou mais) para que esse processo seja concluído.

## <a name="stop-a-policy-application"></a>Parar um aplicativo de política

Se, depois de começar a aplicar as políticas de barreira de informações, você quiser impedir que essas políticas sejam aplicadas, use o procedimento a seguir. Tenha em mente que levará aproximadamente 30-35 minutos para que o processo seja iniciado.

1. Para exibir o status do aplicativo de política de barreira de informações mais recente, use o cmdlet **Get-InformationBarrierPoliciesApplicationStatus** .

    Possuem `Get-InformationBarrierPoliciesApplicationStatus`

    Observe o GUID do aplicativo.

2. Use o cmdlet **Stop-InformationBarrierPoliciesApplication** com um parâmetro Identity.

    |Sintaxe  |Exemplo  |
    |---------|---------|
    |`Stop-InformationBarrierPoliciesApplication -Identity GUID`     |`Stop-InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1` <p>Neste exemplo, estamos interrompendo as políticas de barreira de informações de serem aplicadas.         |

## <a name="related-articles"></a>Artigos relacionados

[Obter uma visão geral das barreiras de informação](information-barriers.md)

[Definir políticas para barreiras de informações](information-barriers-policies.md)

[Saiba mais sobre as barreiras de informação no Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

[Atributos das políticas de barreira de informações](information-barriers-attributes.md)

[Solução de problemas de barreiras de informações](information-barriers-troubleshooting.md)
