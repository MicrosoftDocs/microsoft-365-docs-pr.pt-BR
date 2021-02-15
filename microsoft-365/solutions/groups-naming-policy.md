---
title: Política de nomeação de grupos do Microsoft 365
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
description: Saiba como criar uma política de nomeação para grupos do Microsoft 365.
ms.openlocfilehash: acf660375508760bd2e9874a07454709849929b0
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49759819"
---
# <a name="microsoft-365-groups-naming-policy"></a>Política de nomeação de grupos do Microsoft 365

Você pode usar uma política de nomeação de grupo para impor uma estratégia de nomeação consistente para grupos criados por usuários em sua organização. Uma política de nomeação pode ajudar você e seus usuários a identificar a função do grupo, associação, região geográfica ou quem criou o grupo. A política de nomeação também pode ajudar a categorizar grupos no livro de endereços. Você pode usar a política para impedir que palavras específicas são usadas em aliases e nomes de grupo.

A política de nomeação é aplicada a grupos criados em todas as cargas de trabalho de grupos (como Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc.). Ele é aplicado ao nome do grupo e ao alias do grupo. Ele também é aplicado quando um usuário cria um grupo e quando o nome do grupo, alias, descrição ou avatar é editado para um grupo existente.

> [!TIP]
> Uma política de nomeação de grupo do Microsoft 365 só se aplica a grupos do Microsoft 365. Não se aplica a grupos de distribuição criados no Exchange Online. Para criar uma política de nomeação para grupos de distribuição, consulte [Criar uma política de nomeação de grupo de distribuição.](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy)

A política de nomeação de grupo consiste nos seguintes recursos:

- Política de **nomeação** de prefixo-sufixo: você pode usar prefixos ou sufixos para definir a convenção de nomen por grupos (por exemplo: "US \_ My Group \_ Engineering"). Os prefixos/sufixos podem ser cadeias de caracteres fixas ou atributos de usuário como [Departamento] que serão substituídos com base no usuário que está criando o grupo.

- **Palavras bloqueadas** personalizadas: você pode carregar um conjunto de palavras bloqueadas específicas para sua organização que seriam bloqueadas em grupos criados por usuários. (Por exemplo: "CEO, Folha de Pagamento, RH").

## <a name="licensing-requirements"></a>Requisitos de licença

O uso da política de nomeação do Azure AD para Grupos do Microsoft 365 exige que você possua, mas não necessariamente atribua uma licença do Azure Active Directory Premium P1 ou uma licença do Azure AD Basic EDU para cada usuário exclusivo (incluindo convidados) que seja membro de um ou mais grupos do Microsoft 365.

Isso também é necessário para o administrador que cria a política de nomeação de grupos.

## <a name="prefix-suffix-naming-policy"></a>Prefix-Suffix nomeação de política

Prefixos e sufixos podem ser cadeias de caracteres fixas ou atributos do usuário.

### <a name="fixed-strings"></a>Cadeias de caracteres fixas

Você pode usar cadeias de caracteres curtas que podem ajudá-lo a diferenciar grupos na GAL e à esquerda da navegação das cargas de trabalho do grupo. Alguns dos sufixos de prefixos comuns são palavras-chave como 'Grp \_ Name', ' \# Name', ' \_ Name'

### <a name="attributes"></a>Atributos

Você pode usar atributos que podem ajudar a identificar quem criou o grupo como [Departamento] e onde ele foi criado a partir de [País].

Exemplos:

- Policy = "GRP [GroupName] [Department]"
- Departamento do usuário = Engenharia
- Nome do grupo criado = "GRP My Group Engineering"

Os atributos com suporte do Azure Active Directory (Azure AD) são [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion], e [Title].

- Atributos de usuário sem suporte são considerados cadeias de caracteres fixas, por exemplo [postalCode].

- Atributos de extensão e atributos personalizados não são suportados.

É recomendável que você use atributos que tenham valores preenchidos para todos os usuários em sua organização e não use atributos com valores mais longos.

### <a name="things-to-look-out-for"></a>Coisas a se procurar

- Durante a criação da política, o comprimento total de prefixos e sufixos é restrito a 53 caracteres.

- Prefixos e sufixos podem conter caracteres especiais com suporte no nome do grupo e no alias do grupo. Quando os prefixos e sufixos contêm caracteres especiais que não são permitidos no alias de grupo, eles são aplicados apenas ao nome do grupo. Portanto, nesse caso, os prefixos e sufixos aplicados ao nome do grupo seriam diferentes dos aplicados ao alias de grupo.

  > [!NOTE]
  > Um ponto (.) ou um hífen (-) é permitido em qualquer lugar no nome do grupo, exceto no início ou no final do nome. Um sublinhado (_) é permitido em qualquer lugar no nome do grupo, incluindo no início ou no final do nome.

- Se você estiver usando os grupos conectados do Yammer do Office 365, evite usar os seguintes caracteres em sua política de nomeação: @, \# , \[ , \] \<, and \> . Se esses caracteres estão na política de nomeação, os usuários regulares do Yammer não poderão criar grupos.

> [!Tip]
> - Use cadeias de caracteres curtas como sufixo.
> - Use atributos com valores.
> - Não seja muito criativo, o comprimento total do nome tem no máximo 264 caracteres.
> - Carregue palavras bloqueadas específicas da sua organização para restringir o uso.

## <a name="custom-blocked-words"></a>Palavras bloqueadas personalizadas

Você pode inserir uma lista separada por vírgulas de palavras bloqueadas que serão bloqueadas em aliases e nomes de grupo.

Nenhuma pesquisa de sub-cadeia de caracteres é realizada; especificamente, é necessária uma combinação exata entre o nome inserido pelo usuário e as palavras bloqueadas personalizadas para disparar uma falha.

**Coisas a se procurar:**

- As palavras bloqueadas não fazem parte de maiúsculas e minúsculas.

- Quando um usuário inserir uma palavra bloqueada, o cliente do grupo mostrará uma mensagem de erro com a palavra bloqueada.

- Não há restrições de caractere nas palavras bloqueadas usadas.

- Há um limite de 5.000 palavras que podem ser definidas como palavras bloqueadas.

## <a name="admin-override"></a>Substituição de administrador

Alguns administradores estão isentos dessas políticas, em todas as cargas de trabalho e pontos de extremidade do grupo, para que possam criar grupos com essas palavras bloqueadas e com suas convenções de nomenais desejadas. A seguir estão a lista de funções de administrador isentas da política de nomeação de grupo.

- Administrador global

- Suporte ao Nível 1 do Parceiro

- Suporte ao Nível 2 do Parceiro

- Administrador de conta de usuário

## <a name="how-to-set-up-the-naming-policy"></a>Como configurar a política de nomeação

Para configurar uma política de nomeação:

1. No [Azure Active Directory,](https://aad.portal.azure.com)em **Gerenciar,** clique em **Grupos.**
2. Em **Configurações,** clique **em Política de Nomen por nomeação.**
3. Escolha a **guia Política de nomeação de** grupo.
4. Em **Política atual,** escolha se deseja exigir um prefixo ou sufixo ou ambos e marque as caixas de seleção apropriadas.
5. Escolha entre **Atributo** e **Cadeia de** Caracteres para cada linha e especifique o atributo ou a cadeia de caracteres.
6. Quando tiver adicionado os prefixos e sufixos necessários, clique em **Salvar.**

![Captura de tela das configurações de política de nomeação de grupos no Azure Active Directory](../media/groups-naming-policy-azure.png)

## <a name="related-topics"></a>Tópicos relacionados

[Planejamento de governança de colaboração passo a passo](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Criar seu plano de governança de colaboração](collaboration-governance-first.md)

[Cmdlets Azure Active Directory para definição de configurações de grupo](https://go.microsoft.com/fwlink/?linkid=868341)
