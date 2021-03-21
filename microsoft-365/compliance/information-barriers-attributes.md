---
title: Atributos das políticas de barreira de informações
description: Este artigo é uma referência para os atributos de conta de usuário do Azure Active Directory que você pode usar para definir segmentos de barreira de informações.
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ee410bf455e770087da7999ad2019c17419a8e00
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919727"
---
# <a name="attributes-for-information-barrier-policies"></a>Atributos das políticas de barreira de informações

Determinados atributos no Azure Active Directory podem ser usados para segmentar usuários. Depois que os segmentos são definidos, esses segmentos podem ser usados como filtros para políticas de barreira de informações. Por exemplo, você pode usar **o Department** para definir segmentos de usuários por departamento em sua organização (supondo que nenhum único funcionário funcione para dois departamentos ao mesmo tempo).

Este artigo descreve como usar atributos com barreiras de informações e fornece uma lista de atributos que podem ser usados. Para saber mais sobre as barreiras de informações, consulte os seguintes recursos:

- [Barreiras de informações](information-barriers.md)
- [Definir políticas para barreiras de informações no Microsoft Teams](information-barriers-policies.md)
- [Editar (ou remover) políticas de barreira de informações](information-barriers-edit-segments-policies.md)

## <a name="how-to-use-attributes-in-information-barrier-policies"></a>Como usar atributos em políticas de barreira de informações

Os atributos listados neste artigo podem ser usados para definir ou editar segmentos de usuários. Seus segmentos definidos servem como parâmetros (chamados *valores UserGroupFilter)* em políticas de barreira [de informações.](information-barriers-policies.md)

1. Determine qual atributo você deseja usar para definir segmentos. (Consulte a [seção Referência](#reference) neste artigo.)

2. Certifique-se de que as contas de usuário tenham valores preenchidos para os atributos selecionados na Etapa 1. Exibir detalhes da conta de usuário e, se necessário, editar contas de usuário para incluir valores de atributo. 

    - Para editar várias contas (ou usar o PowerShell para editar uma única conta), consulte [Configure user account properties with Office 365 PowerShell](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md).

    - Para editar uma única conta, consulte [Add or update a user's profile information using Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).

3. [Definir segmentos usando o PowerShell](information-barriers-policies.md#define-segments-using-powershell), semelhante aos seguintes exemplos:

    |**Exemplo**|**Cmdlet**|
    |:----------|:---------|
    | Definir um segmento chamado Segment1 usando o atributo Department | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"` |
    | Definir um segmento chamado SegmentA usando o atributo MemberOf (suponha que este atributo contenha nomes de grupo, como "BlueGroup") | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"` |
    | Definir um segmento chamado DayTraders usando ExtensionAttribute1 (suponha que este atributo contenha títulos de trabalho, como "DayTrader") | `New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

    > [!TIP]
    > Ao definir segmentos, use o mesmo atributo para todos os segmentos. Por exemplo, se você definir alguns segmentos usando *Department*, defina todos os segmentos usando *Department*. Não defina alguns segmentos usando *Departamento* e outros usando *MemberOf*. Certifique-se de que seus segmentos não se sobreponham; cada usuário deve ser atribuído a exatamente um segmento.

## <a name="reference"></a>Referência

A tabela a seguir lista os atributos que você pode usar com barreiras de informações.

|**Nome da propriedade Azure Active Directory (nome de exibição <br/> LDAP)**|**Nome da propriedade Exchange**|
|:---------------------------------------------------------------|:-------------------------|
| Co | Co |
| Empresa | Empresa |
| Department | Department |
| ExtensionAttribute1 | CustomAttribute1 |
| ExtensionAttribute2 | CustomAttribute2 |
| ExtensionAttribute3 | CustomAttribute3 |
| ExtensionAttribute4 | CustomAttribute4 |
| ExtensionAttribute5 | CustomAttribute5 |
| ExtensionAttribute6 | CustomAttribute6 |
| ExtensionAttribute7 | CustomAttribute7 |
| ExtensionAttribute8 | CustomAttribute8 |
| ExtensionAttribute9 | CustomAttribute9 |
| ExtensionAttribute10 | CustomAttribute10 |
| ExtensionAttribute11 | CustomAttribute11 |
| ExtensionAttribute12 | CustomAttribute12 |
| ExtensionAttribute13 | CustomAttribute13 |
| ExtensionAttribute14 | CustomAttribute14 |
| ExtensionAttribute15 | CustomAttribute15 |
| MSExchExtensionCustomAttribute1 | ExtensionCustomAttribute1 |
| MSExchExtensionCustomAttribute2 | ExtensionCustomAttribute2 |
| MSExchExtensionCustomAttribute3 | ExtensionCustomAttribute3 |
| MSExchExtensionCustomAttribute4 | ExtensionCustomAttribute4 |
| MSExchExtensionCustomAttribute5 | ExtensionCustomAttribute5 |
| MailNickname | Alias |
| PhysicalDeliveryOfficeName | Office |
| PostalCode | PostalCode |
| ProxyAddresses | EmailAddresses |
| StreetAddress | StreetAddress |
| TargetAddress | ExternalEmailAddress |
| UsageLocation | UsageLocation |
| UserPrincipalName | UserPrincipalName |
| Email | WindowsEmailAddress |
| Descrição | Descrição |
| MemberOf | MemberOfGroup |

## <a name="resources"></a>Recursos

- [Definir políticas para barreiras de informações no Microsoft Teams](information-barriers-policies.md)
- [Solução de problemas de barreiras de informações](information-barriers-troubleshooting.md)
- [Barreiras de informações](information-barriers.md)