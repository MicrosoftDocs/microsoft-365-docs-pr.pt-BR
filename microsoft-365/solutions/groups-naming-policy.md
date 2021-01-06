---
title: Política de nomenclatura de grupos do Microsoft 365
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
description: Saiba como criar uma política de nomenclatura para os grupos do Microsoft 365.
ms.openlocfilehash: acf660375508760bd2e9874a07454709849929b0
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49759819"
---
# <a name="microsoft-365-groups-naming-policy"></a>Política de nomenclatura de grupos do Microsoft 365

Você pode usar uma política de nomeação de grupo para impor uma estratégia de nomenclatura consistente para grupos criados por usuários em sua organização. Uma política de nomenclatura pode ajudar você e seus usuários a identificar a função do grupo, da associação, da região geográfica ou quem criou o grupo. A política de nomenclatura também pode ajudar a categorizar grupos no catálogo de endereços. Você pode usar a política para bloquear a utilização de palavras específicas em nomes de grupo e aliases.

A política de nomenclatura é aplicada a grupos criados em todas as cargas de trabalho de grupos (como Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc.). Ela é aplicada ao nome do grupo e ao alias do grupo. Ela também é aplicada quando um usuário cria um grupo e quando o nome do grupo, alias, descrição ou avatar é editado para um grupo existente.

> [!TIP]
> Uma política de nomenclatura de grupo do Microsoft 365 só se aplica aos grupos do Microsoft 365. Ele não se aplica a grupos de distribuição criados no Exchange Online. Para criar uma política de nomenclatura para grupos de distribuição, consulte [criar uma política de nomenclatura de grupo de distribuição](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).

A política de nomeação de grupo consiste nos seguintes recursos:

- **Política de nomenclatura de sufixo de prefixo**: você pode usar prefixos ou sufixos para definir a Convenção de nomenclatura de grupos (por exemplo: " \_ minha engenharia de grupo dos EUA \_ "). Os prefixos/sufixos podem ser cadeias de caracteres fixas ou atributos de usuário como [departamento] que serão substituídos com base no usuário que está criando o grupo.

- **Palavras bloqueadas personalizadas**: você pode carregar um conjunto de palavras bloqueadas específicas para sua organização que seriam bloqueados em grupos criados por usuários. (Por exemplo: "CEO, folha de pagamento, RH").

## <a name="licensing-requirements"></a>Requisitos de licença

O uso da política de nomenclatura do Azure AD para grupos do Microsoft 365 requer que você tenha, mas não necessariamente, atribua uma licença do Azure Active Directory Premium P1 ou uma licença do Azure AD Basic EDU para cada usuário exclusivo (incluindo convidados) que seja membro de um ou mais grupos da Microsoft 365.

Isso também é necessário para o administrador que cria a política de nomenclatura de grupos.

## <a name="prefix-suffix-naming-policy"></a>Política de nomenclatura Prefix-Suffix

Os prefixos e sufixos podem ser cadeias de caracteres fixas ou atributos de usuário.

### <a name="fixed-strings"></a>Cadeias de caracteres fixas

Você pode usar cadeias de caracteres curtas que podem ajudá-lo a diferenciar grupos na GAL e à navegação à esquerda das cargas de trabalho do grupo. Alguns dos sufixos de prefixos comuns são palavras-chave como "GRP \_ name", " \# name", " \_ name"

### <a name="attributes"></a>Atributos

Você pode usar atributos que podem ajudar a identificar quem criou o grupo como [departamento] e onde ele foi criado de como [país].

Exemplos:

- Policy = "GRP [Nome_do_grupo] [departamento]"
- Departamento do usuário = engenharia
- Nome do grupo criado = "engenharia de grupo meu GRP"

Os atributos do Azure Active Directory (Azure AD) com suporte são [departamento], [empresa], [Office], [StateOrProvince], [CountryOrRegion] e [título].

- Atributos de usuário não suportados são considerados cadeias de caracteres fixas, por exemplo, [postalCode].

- Não há suporte para atributos de extensão e atributos personalizados.

É recomendável que você use atributos com valores preenchidos para todos os usuários em sua organização e não use atributos com valores mais longos.

### <a name="things-to-look-out-for"></a>Aspectos a serem verificados

- Durante a criação da política, o comprimento total de cadeias de caracteres e sufixos é restrito a 53 caracteres.

- Os prefixos e sufixos podem conter caracteres especiais compatíveis com o nome do grupo e o alias do grupo. Quando os prefixos e sufixos contêm caracteres especiais que não são permitidos no alias do grupo, eles são aplicados apenas ao nome do grupo. Portanto, nesse caso, os prefixos e sufixos aplicados ao nome do grupo seriam diferentes dos que foram aplicados ao alias do grupo.

  > [!NOTE]
  > Um ponto (.) ou um hífen (-) é permitido em qualquer lugar no nome do grupo, exceto no início ou no final do nome. Um sublinhado (_) é permitido em qualquer lugar no nome do grupo, incluindo no início ou no final do nome.

- Se você estiver usando os grupos conectados do Yammer Office 365, evite usar os seguintes caracteres em sua política de nomenclatura: @, \# , \[ , \] , \<, and \> . Se esses caracteres estiverem na política de nomenclatura, os usuários normais do Yammer não poderão criar grupos.

> [!Tip]
> - Usar cadeias de caracteres curtas como sufixo.
> - Use atributos com valores.
> - Não seja muito criativo, o comprimento total do nome tem um máximo de 264 caracteres.
> - Carregue suas palavras bloqueadas específicas da organização para restringir o uso.

## <a name="custom-blocked-words"></a>Palavras bloqueadas personalizadas

Você pode inserir uma lista separada por vírgulas de palavras bloqueadas que serão bloqueadas em nomes de grupo e aliases.

Nenhuma pesquisa de subcadeias de caracteres é executada; especificamente, uma correspondência exata entre o nome digitado pelo usuário e as palavras bloqueadas personalizadas é necessária para acionar uma falha.

**Aspectos a serem verificados**:

- As palavras bloqueadas não diferenciam maiúsculas de minúsculas.

- Quando um usuário insere uma palavra bloqueada, o cliente do grupo mostrará uma mensagem de erro com a palavra bloqueada.

- Não há restrições de caracteres nas palavras bloqueadas usadas.

- Há um limite de 5000 palavras que podem ser definidas como palavras bloqueadas.

## <a name="admin-override"></a>Substituição de administrador

Alguns administradores são isentos dessas políticas, em todas as cargas de trabalho de grupo e pontos de extremidade, para que eles possam criar grupos com essas palavras bloqueadas e com as convenções de nomenclatura desejadas. Veja a seguir a lista de funções de administrador isentas da política de nomeação de grupo.

- Administração global

- Suporte da camada 1 do parceiro

- Suporte da camada 2 do parceiro

- Administrador de conta de usuário

## <a name="how-to-set-up-the-naming-policy"></a>Como configurar a política de nomenclatura

Para configurar uma política de nomenclatura:

1. No [Azure Active Directory](https://aad.portal.azure.com), em **gerenciar**, clique em **grupos**.
2. Em **configurações**, clique em **política de nomenclatura**.
3. Escolha a guia **política de nomeação de grupo** .
4. Em **política atual**, escolha se você deseja exigir um prefixo ou sufixo, ou ambos, e marque as caixas de seleção apropriadas.
5. Escolha entre **atributo** e **cadeia de caracteres** para cada linha e, em seguida, especifique o atributo ou a cadeia de caracteres.
6. Após adicionar os prefixos e sufixos necessários, clique em **salvar**.

![Captura de tela das configurações de política de nomenclatura de grupos no Azure Active Directory](../media/groups-naming-policy-azure.png)

## <a name="related-topics"></a>Tópicos relacionados

[Passo a passo de planejamento de governança de colaboração](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Criar seu plano de governança de colaboração](collaboration-governance-first.md)

[Cmdlets do Azure Active Directory para definição de configurações de grupo](https://go.microsoft.com/fwlink/?linkid=868341)
