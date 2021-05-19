---
title: Microsoft 365 de nomeação de grupos
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
recommendations: false
description: Saiba como criar uma política de nomen por Microsoft 365 grupos.
ms.openlocfilehash: 5ab5f252e2b81470413b4efea17b131613aabc18
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538166"
---
# <a name="microsoft-365-groups-naming-policy"></a>Microsoft 365 de nomeação de grupos

Você pode usar uma política de nomenis de grupo para impor uma estratégia de nomenisão consistente para grupos criados pelos usuários em sua organização. Uma política de nomenrção pode ajudar você e seus usuários a identificar a função do grupo, associação, região geográfica ou quem criou o grupo. A política de nomenrção também pode ajudar a categorizar grupos no livro de endereços. Você pode usar a política para impedir que palavras específicas são usadas em nomes de grupo e aliases.

A política de nomenisagem é aplicada a grupos criados em todas as cargas de trabalho de grupos (como Outlook, Microsoft Teams, SharePoint, Planner, Yammer etc.). Ele é aplicado ao nome do grupo e ao alias do grupo. Ele também é aplicado quando um usuário cria um grupo e quando o nome do grupo, alias, descrição ou avatar é editado para um grupo existente.

> [!TIP]
> Uma Microsoft 365 de nomenis de grupo só se aplica a Microsoft 365 grupos. Ele não se aplica a grupos de distribuição criados em Exchange Online. Para criar uma política de nomenisão para grupos de distribuição, consulte [Create a distribution group noming policy](/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).

A política de nomenisagem de grupo consiste nos seguintes recursos:

- **Política de** nomenis de prefixo-sufixo : você pode usar prefixos ou sufixos para definir a convenção de nomenis de grupos (por exemplo: "US \_ My Group \_ Engineering"). Os prefixos/sufixos podem ser cadeias de caracteres fixas ou atributos de usuário como [Departamento] que serão substituídos com base no usuário que está criando o grupo.

- **Palavras bloqueadas** personalizadas: você pode carregar um conjunto de palavras bloqueadas específicas para sua organização que seriam bloqueadas em grupos criados pelos usuários. (Por exemplo: "CEO, Folha de Pagamento, RH").

## <a name="licensing-requirements"></a>Requisitos de licenciamento

O uso da política de nomenização do Azure AD para grupos do Microsoft 365 exige que você possua, mas não necessariamente atribua uma licença P1 do Azure Active Directory Premium ou uma licença do Azure AD Basic EDU para cada usuário exclusivo (incluindo convidados) que seja membro de um ou mais grupos Microsoft 365.

Isso também é necessário para o administrador que cria a política de nomenrção de grupos.

## <a name="prefix-suffix-naming-policy"></a>Prefix-Suffix de nomenis

Prefixos e sufixos podem ser cadeias de caracteres fixas ou atributos de usuário.

### <a name="fixed-strings"></a>Cadeias de caracteres fixas

Você pode usar cadeias de caracteres curtas que podem ajudá-lo a diferenciar grupos na GAL e à esquerda da navegação das cargas de trabalho do grupo. Alguns dos sufixos de prefixos comuns são palavras-chave como 'Grp \_ Name' , ' \# Name', ' \_ Name'

### <a name="attributes"></a>Atributos

Você pode usar atributos que podem ajudar a identificar quem criou o grupo como [Departamento] e onde ele foi criado a partir de como [País].

Exemplos:

- Política = "GRP [GroupName] [Department]"
- Departamento do usuário = Engenharia
- Nome do grupo criado = "GRP My Group Engineering"

Os atributos Azure Active Directory (Azure AD) são [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion], e [Title].

- Atributos de usuário sem suporte são considerados como cadeias de caracteres fixas, por exemplo [postalCode].

- Atributos de extensão e atributos personalizados não são suportados.

É recomendável que você use atributos que tenham valores preenchidos para todos os usuários em sua organização e não use atributos que tenham valores mais longos.

### <a name="things-to-look-out-for"></a>Coisas para se ter em atenção

- Durante a criação de política, o comprimento da cadeia de caracteres de prefixos e sufixos totais é restrito a 53 caracteres.

- Prefixos e sufixos podem conter caracteres especiais com suporte no nome do grupo e no alias do grupo. Quando os prefixos e sufixos contêm caracteres especiais que não são permitidos no alias do grupo, eles são aplicados apenas ao nome do grupo. Nesse caso, os prefixos e sufixos aplicados ao nome do grupo seriam diferentes dos aplicados ao alias do grupo.

  > [!NOTE]
  > Um ponto (.) ou um hífen (-) é permitido em qualquer lugar no nome do grupo, exceto no início ou no final do nome. Um sublinhado (_) é permitido em qualquer lugar no nome do grupo, incluindo no início ou no final do nome.

- Se você estiver usando Yammer Office 365 grupos conectados, evite usar os seguintes caracteres em sua política de nomenisagem: @, \# \[ , , , \] \<, and \> . Se esses caracteres estão na política de nomenisagem, Yammer usuários regulares não poderão criar grupos.

> [!Tip]
> - Use cadeias de caracteres curtas como sufixo.
> - Use atributos com valores.
> - Não seja muito criativo, o comprimento total do nome tem no máximo 264 caracteres.
> - Upload palavras bloqueadas específicas da sua organização para restringir o uso.

## <a name="custom-blocked-words"></a>Palavras bloqueadas personalizadas

Você pode inserir uma lista separada por vírgulas de palavras bloqueadas que serão bloqueadas em nomes de grupo e aliases.

Nenhuma pesquisa de sub-cadeia de caracteres é realizada; especificamente, uma combinação exata entre o nome inserido pelo usuário e as palavras bloqueadas personalizadas é necessária para disparar uma falha.

**Coisas a se ter em atenção:**

- As palavras bloqueadas não têm maiúsculas de minúsculas.

- Quando um usuário inserir uma palavra bloqueada, o cliente de grupo mostrará uma mensagem de erro com a palavra bloqueada.

- Não há restrições de caractere nas palavras bloqueadas usadas.

- Há um limite de 5.000 palavras que podem ser definidas como palavras bloqueadas.

## <a name="admin-override"></a>Substituição de administrador

Alguns administradores são isentos dessas políticas, em todas as cargas de trabalho de grupo e pontos de extremidade, para que eles possam criar grupos com essas palavras bloqueadas e com suas convenções de nomenais desejadas. Veja a seguir a lista de funções de administrador isentas da política de nomenis de grupo.

- Administrador global

- Suporte ao Partner Tier 1

- Suporte ao Partner Tier 2

- Administrador de conta de usuário

## <a name="how-to-set-up-the-naming-policy"></a>Como configurar a política de nomen

Para configurar uma política de nomenrção:

1. Em [Azure Active Directory](https://aad.portal.azure.com), em **Gerenciar,** clique em **Grupos**.
2. Em **Configurações,** clique **em Política de Nomenis.**
3. Escolha a **guia Política de nomenis de** grupo.
4. Em **Política atual,** escolha se deseja exigir um prefixo ou sufixo ou ambos e selecione as caixas de seleção apropriadas.
5. Escolha entre **Atributo** e **Cadeia de** Caracteres para cada linha e especifique o atributo ou a cadeia de caracteres.
6. Quando tiver adicionado os prefixos e sufixos necessários, clique em **Salvar**.

![Captura de tela das configurações de política de nomeação de grupos no Azure Active Directory](../media/groups-naming-policy-azure.png)

## <a name="related-topics"></a>Tópicos relacionados

[Planejamento de governança de colaboração passo a passo](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Criar seu plano de governança de colaboração](collaboration-governance-first.md)

[Cmdlets Azure Active Directory para definição de configurações de grupo](/azure/active-directory/enterprise-users/groups-settings-cmdlets)