---
title: Gerenciar políticas de barreira de informações
description: Saiba como editar ou remover políticas para barreiras de informações.
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.openlocfilehash: 62e9910a1b94862ba23ecdc63c0fea1ec644043a
ms.sourcegitcommit: c10eb675da725830e9776d2a0566ba3622eb361c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/26/2021
ms.locfileid: "49980074"
---
# <a name="manage-information-barrier-policies"></a>Gerenciar políticas de barreira de informações

Depois de definir [políticas de](information-barriers-policies.md)barreira de informações, talvez seja necessário fazer alterações [](information-barriers-troubleshooting.md) nessas políticas ou em seus segmentos de usuário, como parte da solução de problemas ou como manutenção regular. Use este artigo como guia.

## <a name="what-do-you-want-to-do"></a>O que você deseja fazer?

|**Ação**|**Descrição**|
|:---------|:--------------|
| [Editar atributos de conta de usuário](#edit-user-account-attributes) | Preencha atributos no Azure Active Directory que podem ser usados para definir segmentos.<br/>Edite atributos de conta de usuário quando os usuários não estão incluídos em segmentos que deveriam estar, para alterar em quais segmentos os usuários estão ou para definir segmentos usando atributos diferentes. |
| [Editar um segmento](#edit-a-segment) | Edite segmentos quando quiser alterar a forma como um segmento é definido. <br/>Por exemplo, você pode ter definido  originalmente segmentos usando Departamento e agora deseja usar outro atributo, como *MemberOf*. |
| [Editar uma política](#edit-a-policy) | Edite uma política de barreira de informações quando quiser alterar o modo como uma política funciona.<br/>Por exemplo, em vez de bloquear as comunicações entre dois segmentos, você pode decidir que deseja permitir que as comunicações ocorram apenas entre determinados segmentos. |
| [Definir uma política como status inativo](#set-a-policy-to-inactive-status) |Definir uma política como status inativo quando você quiser fazer alterações em uma política ou quando não quiser que uma política entre em vigor. |
| [Remover uma política](#remove-a-policy) | Remova uma política de barreira de informações quando não precisar mais de uma política específica. |
| [Parar um aplicativo de política](#stop-a-policy-application) | Tome esta ação quando quiser interromper o processo de aplicação de políticas de barreira de informações.<br/> Parar um aplicativo de política não é instantâneo e não desfaz políticas já aplicadas aos usuários. |
| [Definir políticas para barreiras de informações](information-barriers-policies.md) | Defina uma política de barreira de informações quando ainda não tiver essas políticas em uso e deverá restringir ou limitar as comunicações entre grupos de usuários específicos. |
| [Solução de problemas de barreiras de informações](information-barriers-troubleshooting.md) | Consulte este artigo quando você tem problemas inesperados com barreiras de informações. |

> [!IMPORTANT]
> Para executar as tarefas descritas neste artigo, você deve ter uma função apropriada, como uma das seguintes:<br/>– Administrador Global do Microsoft 365 Enterprise<br/>- Administrador Global<br/>- Administrador de Conformidade<br/>– Gerenciamento de Conformidade do IB (esta é uma nova função!)<br><br>Para saber mais sobre os pré-requisitos para barreiras de informações, consulte [Pré-requisitos (para](information-barriers-policies.md#prerequisites)políticas de barreira de informações).<br><br> Certifique-se [de se conectar ao PowerShell do Centro de Conformidade & segurança.](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)

## <a name="edit-user-account-attributes"></a>Editar atributos de conta de usuário

Use este procedimento para editar atributos usados para segmentar usuários. Por exemplo, se você estiver usando um atributo Department e uma ou mais contas de usuário não têm atualmente valores listados para Departamento, você deve editar essas contas de usuário para incluir informações de departamento. Atributos de conta de usuário são usados para definir segmentos para que as políticas de barreira de informações possam ser atribuídas.

1. Para exibir detalhes de uma conta de usuário específica, como valores de atributos e segmentos atribuídos, use o cmdlet **Get-InformationBarrierRecipientStatus** com parâmetros de Identidade.

    |**Sintaxe**|**Exemplo**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> É possível usar qualquer valor que identifique cada usuário com exclusividade, como nome, alias, nome diferenciado, nome de domínio canônico, endereço de email ou GUID. <p> (Você também pode usar esse cmdlet para um único usuário: `Get-InformationBarrierRecipientStatus -Identity <value>` ) |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> Neste exemplo, nos referimos a duas contas de usuário no Office 365: *meganb* para *Megan* e *alexw* para *Alex*. |

2. Determine qual atributo você deseja editar para seus perfis de conta de usuário. Para obter mais informações, consulte [Atributos para políticas de barreira de informações.](information-barriers-attributes.md) 

3. Edite uma ou mais contas de usuário para incluir valores para o atributo selecionado na etapa anterior. Para tomar essa ação, use um dos seguintes procedimentos:

    - Para editar uma única conta, confira Adicionar ou atualizar as informações de perfil de um [usuário usando o Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

    - Para editar várias contas (ou usar o PowerShell para editar uma única conta), confira Configurar propriedades de conta de usuário com o [Office 365 PowerShell.](https://docs.microsoft.com/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell)

## <a name="edit-a-segment"></a>Editar um segmento

Use este procedimento para editar a definição de um segmento de usuário. Por exemplo, você pode alterar o nome de um segmento ou o filtro usado para determinar quem está incluído no segmento.

1. Para exibir todos os segmentos existentes, use o cmdlet **Get-OrganizationSegment.**

    Sintaxe: `Get-OrganizationSegment`

    Você verá uma lista de segmentos e detalhes de cada um, como tipo de segmento, seu valor UserGroupFilter, quem o criou ou modificou pela última vez, GUID e assim por diante.

    > [!TIP]
    > Imprima ou salve sua lista de segmentos para referência posteriormente. Por exemplo, se você quiser editar um segmento, precisará saber seu nome ou identificar o valor (isso é usado com o parâmetro Identity).

2. Para editar um segmento, use o cmdlet **Set-OrganizationSegment** com o parâmetro **Identity** e detalhes relevantes.

    |**Sintaxe**|**Exemplo**|
    |:---------|:----------|
    | `Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"` |`Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"` <p> Neste exemplo, para o segmento que tem o GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*, atualizamos o nome do departamento para "HRDept". |

Quando terminar de editar segmentos para sua organização, você poderá [definir](information-barriers-policies.md#part-2-define-information-barrier-policies) ou [editar](#edit-a-policy) políticas de barreira de informações.

## <a name="edit-a-policy"></a>Editar uma política

1. Para exibir uma lista de políticas atuais de barreira de informações, use o cmdlet **Get-InformationBarrierPolicy.**

    Sintaxe: `Get-InformationBarrierPolicy`

    Na lista de resultados, identifique a política que você deseja alterar. Observe o GUID e o nome da política.

2. Use o cmdlet **Set-InformationBarrierPolicy** com um parâmetro **Identity** e especifique as alterações que você deseja fazer.

    Exemplo: suponha que uma política foi definida para impedir que *o segmento Research* se comunique com os segmentos *vendas* *e* marketing. A política foi definida usando este cmdlet: `New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`

    Suponha que queiramos alterá-la para que as pessoas no segmento *Pesquisa* só possam se comunicar com pessoas no *segmento de* RH. Para fazer essa alteração, usamos este cmdlet: `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`

    Neste exemplo, trocamos "SegmentsBlocked" para "SegmentsAllowed" e especificamos o *segmento rh.*

3. Quando terminar de editar uma política, certifique-se de aplicar suas alterações. (Consulte [Aplicar políticas de barreira de informações.)](information-barriers-policies.md#part-3-apply-information-barrier-policies)

## <a name="set-a-policy-to-inactive-status"></a>Definir uma política como status inativo

1. Para exibir uma lista de políticas atuais de barreira de informações, use o cmdlet **Get-InformationBarrierPolicy.**

    Sintaxe: `Get-InformationBarrierPolicy`

    Na lista de resultados, identifique a política que você deseja alterar (ou remover). Observe o GUID e o nome da política.

2. Para definir o status da política como inativo, use o cmdlet **Set-InformationBarrierPolicy** com um parâmetro Identity e o parâmetro State definido como Inativo.

    |**Sintaxe**|**Exemplo**|
    |:---------|:----------|
    | `Set-InformationBarrierPolicy -Identity GUID -State Inactive` | `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive` <p> Neste exemplo, definimos uma política de barreira de informações com GUID *43c37853-ea10-4b90-a23d-ab8c9377247* como um status inativo. |

3. Para aplicar suas alterações, use o cmdlet **Start-InformationBarrierPoliciesApplication.**

    Sintaxe: `Start-InformationBarrierPoliciesApplication`

    As alterações são aplicadas, usuário por usuário, para sua organização. Se sua organização for grande, pode levar 24 horas (ou mais) para que esse processo seja concluído. (Como diretriz geral, leva cerca de uma hora para processar 5.000 contas de usuário.)

Neste ponto, uma ou mais políticas de barreira de informações são definidas como status inativo. A partir daqui, você pode fazer qualquer uma das seguintes ações:

- Mantenha-o como está (uma política definida como status inativo não tem efeito sobre os usuários)
- [Editar uma política](#edit-a-policy) 
- [Remover uma política](#remove-a-policy)

## <a name="remove-a-policy"></a>Remover uma política

1. Para exibir uma lista de políticas atuais de barreira de informações, use o cmdlet **Get-InformationBarrierPolicy.**

    Sintaxe: `Get-InformationBarrierPolicy`

    Na lista de resultados, identifique a política que você deseja remover. Observe o GUID e o nome da política. Certifique-se de que a política está definida como status inativo.

2. Use o **cmdlet Remove-InformationBarrierPolicy** com um parâmetro Identity.

    |**Sintaxe**|**Exemplo**|
    |:---------|:----------|
    | `Remove-InformationBarrierPolicy -Identity GUID` | `Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471` <p> Neste exemplo, estamos removendo a política que tem GUID *43c37853-ea10-4b90-a23d-ab8c93772471.* |

    Quando solicitado, confirme a alteração.

3. Repita as etapas 1 a 2 para cada política que você deseja remover.

4. Quando terminar de remover políticas, aplique suas alterações. Para tomar essa ação, use o cmdlet **Start-InformationBarrierPoliciesApplication.**

    Sintaxe: `Start-InformationBarrierPoliciesApplication`

    As alterações são aplicadas, usuário por usuário, para sua organização. Se sua organização for grande, pode levar 24 horas (ou mais) para que esse processo seja concluído.

## <a name="stop-a-policy-application"></a>Parar um aplicativo de política

Depois de começar a aplicar políticas de barreira de informações, se quiser impedir a aplicação dessas políticas, use o procedimento a seguir. Levará aproximadamente de 30 a 35 minutos para que o processo comece.

1. Para exibir o status do aplicativo de política de barreira de informações mais recente, use o cmdlet **Get-InformationBarrierPoliciesApplicationStatus.**

    Sintaxe: `Get-InformationBarrierPoliciesApplicationStatus`

    Observe o GUID do aplicativo.

2. Use o cmdlet **Stop-InformationBarrierPoliciesApplication** com um parâmetro Identity.

    |**Sintaxe**|**Exemplo**|
    |:---------|:----------|
    | `Stop-InformationBarrierPoliciesApplication -Identity GUID` | `Stop-InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1` <p> Neste exemplo, estamos impedindo a aplicação de políticas de barreira de informações. |

## <a name="resources"></a>Recursos

- [Obter uma visão geral das barreiras de informações](information-barriers.md)
- [Definir políticas para barreiras de informações](information-barriers-policies.md)
- [Saiba mais sobre barreiras de informações no Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)
- [Atributos das políticas de barreira de informações](information-barriers-attributes.md)
- [Solução de problemas de barreiras de informações](information-barriers-troubleshooting.md)
