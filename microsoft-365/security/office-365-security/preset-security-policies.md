---
title: Predefinir políticas de segurança
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a aplicar configurações de política padrão e estrita nos recursos de proteção do Proteção do Exchange Online (EOP) e do Microsoft Defender para Office 365
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 24fe67a7465ec71451b649dbc5963c28e0dc7cf3
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879007"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a>Políticas de segurança predefinidas no EOP e no Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

As políticas de segurança predefinidas fornecem um local centralizado para aplicar todas as políticas recomendadas de spam, malware e phishing aos usuários de uma só vez. As configurações de política não são configuráveis. Em vez disso, eles são definidos por nós e se baseiam em nossas observações e experiências nos datacenters para um equilíbrio entre manter o conteúdo prejudicial longe dos usuários e evitar interrupções desnecessárias.

O restante deste artigo descreve políticas de segurança predefinidas e como configurá-las.

## <a name="what-preset-security-policies-are-made-of"></a>De que políticas de segurança predefinidas são feitas

As políticas de segurança predefinidas consistem nos seguintes elementos:

- Perfis
- Políticas
- Configurações de política

Além disso, a ordem de precedência é importante se várias políticas de segurança predefinidas e outras políticas se aplicarem à mesma pessoa.

### <a name="profiles-in-preset-security-policies"></a>Perfis em políticas de segurança predefinidas

Um perfil determina o nível de proteção. Os seguintes perfis estão disponíveis:

- **Proteção padrão**: um perfil de proteção de linha de base adequado para a maioria dos usuários.
- **Proteção estrita**: um perfil de proteção mais agressivo para usuários selecionados (destinos de alto valor ou usuários prioritários).

Você usa regras com condições e exceções que determinam a quem os perfis são ou não aplicados.

As condições e exceções disponíveis são:

- **Usuários**: as caixas de correio, os usuários de email, ou os contatos de email especificados na organização.
- **Grupos**: os grupos de distribuição, os grupos de segurança habilitados para email ou os grupos do Microsoft 365 habilitados na organização.
- **Domínios**: todos os destinatários nos [domínios aceitos](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) especificados na organização.

Só é possível usar uma condição ou exceção uma vez; contudo, você pode especificar vários valores para a condição ou exceção. Vários valores da mesma condição ou exceção usam a lógica OU (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_). Para diferentes condições ou exceções, use a lógica E (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_).

### <a name="policies-in-preset-security-policies"></a>Políticas em políticas de segurança predefinidas

As políticas de segurança predefinidas usam as políticas correspondentes dos vários recursos de proteção no EOP e no Microsoft Defender para Office 365. Essas políticas são _criadas depois que_ você atribui a **proteção padrão** ou políticas **de** segurança predefinidas de proteção estrita aos usuários. Não é possível modificar essas políticas.

- **Proteção do Exchange Online (EOP)**: isso inclui organizações Microsoft 365 com caixas de correio Exchange Online e organizações EOP autônomas sem Exchange Online caixas de correio:

  - [Políticas anti-spam denominadas](configure-your-spam-filter-policies.md) Política de **Segurança Predefinida Padrão** e **Política de Segurança Predefinida Estrita.**
  - [Políticas anti-malware denominadas](configure-anti-malware-policies.md) **Política de Segurança Predefinida Padrão** e Política de Segurança **Predefinida Estrita.**
  - [Políticas anti-phishing do EOP denominadas](set-up-anti-phishing-policies.md#spoof-settings) Política de **Segurança Predefinida Padrão** e **Política** de Segurança Predefinida Estrita (configurações de spoof).

- **Políticas do Microsoft Defender para Office 365**: isso inclui organizações com o Microsoft 365 E5 ou o Defender para Office 365 assinaturas de complemento:

  - Políticas anti-phishing no Microsoft Defender para Office 365 chamada de **Política** de Segurança Predefinida Padrão e **Política** de Segurança Predefinida Estrita, que incluem:

    - As mesmas [configurações de spoof](set-up-anti-phishing-policies.md#spoof-settings) que estão disponíveis nas políticas anti-phishing do EOP.
    - [Configurações de representação](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [Limites avançados de phishing](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - [Cofre políticas de links denominadas](set-up-safe-links-policies.md) Política de **Segurança Predefinida Padrão** e **Política de Segurança Predefinida Estrita.**

  - [Cofre de anexos denominadas](set-up-safe-attachments-policies.md) Política de **Segurança Predefinida Padrão** e **Política de Segurança Predefinida Estrita.**

Observe que você pode aplicar proteções EOP a usuários diferentes do Microsoft Defender para Office 365 proteção.

### <a name="policy-settings-in-preset-security-policies"></a>Configurações de política em políticas de segurança predefinidas

Não é possível modificar as configurações de política nos perfis de proteção. Os **valores de configuração** de **política** Padrão e Estrita são descritos em [Configurações recomendadas para EOP](recommended-settings-for-eop-and-office365.md)e Microsoft Defender para Office 365 segurança .

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a>Ordem de precedência para políticas de segurança predefinidas e outras políticas

Quando várias políticas são aplicadas a um usuário, a ordem a seguir é aplicada da prioridade mais alta à prioridade mais baixa:

1. **Política de segurança predefinida** de proteção estrita
2. **Política de segurança predefinida** de proteção padrão
3. Políticas de segurança personalizadas
4. Políticas de segurança padrão

Em outras palavras, as  configurações da política de  proteção estrita substituem as configurações da política de proteção padrão, que substitui as configurações de uma política personalizada, que substitui as configurações da política padrão.

## <a name="assign-preset-security-policies-to-users"></a>Atribuir políticas de segurança predefinidas aos usuários

### <a name="what-do-you-need-to-know-before-you-begin"></a>Do que você precisa saber para começar?

- Você abre o portal Microsoft 365 Defender em <https://security.microsoft.com> . Para ir diretamente para a página **Políticas de segurança** predefinidas, use <https://security.microsoft.com/presetSecurityPolicies> .

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

- Você precisa ter permissões em **Exchange Online** antes de fazer os procedimentos deste artigo:
  - Para configurar políticas de segurança predefinidas, você precisa ser membro dos grupos de função Gerenciamento da Organização **ou** **Administrador de** Segurança.
  - Para acesso somente leitura a políticas de segurança predefinidas, você precisa ser membro do grupo de função **Leitor Global.**

  Para obter mais informações, confira [Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Observação**: a adição de usuários à função Azure Active Directory correspondente no centro de  administração Microsoft 365 oferece aos usuários as permissões e permissões necessárias para outros recursos no Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).

### <a name="use-the-microsoft-365-defender-portal-to-assign-preset-security-policies-to-users"></a>Use o portal Microsoft 365 Defender para atribuir políticas de segurança predefinidas aos usuários

1. No portal Microsoft 365 Defender, acesse **Email & de** colaboração & Políticas de Ameaças de Regras Seção Políticas de \>  \>  \>  \> **segurança predefinidas**.

2. Em **Proteção padrão ou** proteção **estrita,** clique em **Editar**.

3. O **assistente Aplicar Proteção Padrão** ou Aplicar Proteção **Estrita** é iniciado. Nas **proteções do EOP aplicadas à** página, identifique os destinatários internos aos quais as proteções [do EOP](#policies-in-preset-security-policies) se aplicam (condições de destinatário):
   - **Usuários**
   - **Grupos**
   - **Domínios**

   Clique na caixa apropriada, comece a digitar um valor e selecione o valor desejado dos resultados. Repita esse processo quantas vezes for necessário. Para remover uma entrada existente, clique em Remover ![Ícone Remover](../../media/m365-cc-sc-remove-selection-icon.png) ao lado do valor.

   Para usuários ou grupos, você pode usar a maioria dos identificadores (nome, nome de exibição, alias, endereço de email, nome da conta etc.), mas o nome de exibição correspondente será mostrado nos resultados. Para os usuários, insira um asterisco (\*) por si só para ver todos os valores disponíveis.

   - **Excluir estes usuários, grupos e domínios**: para adicionar exceções para os destinatários internos aos quais a política se aplica (exceções de destinatários), selecione essa opção e configure as exceções. As configurações e o comportamento são exatamente como as condições.

   Ao terminar, clique em **Avançar**.

4. No Microsoft Defender para Office 365, você é levado para **o Defender** para Office 365 proteções se aplicam à página para identificar os destinatários internos aos quais o Microsoft Defender para Office 365 [proteções](#policies-in-preset-security-policies) se aplicam (condições de destinatário).

   As configurações e o comportamento são exatamente como as proteções **do EOP se aplicam à** página.

   Ao terminar, clique em **Avançar**.

5. Na página **Revisar e confirmar suas alterações,** verifique suas seleções e clique em **Confirmar**.

### <a name="use-the-microsoft-365-defender-portal-to-modify-the-assignments-of-preset-security-policies"></a>Use o portal Microsoft 365 Defender para modificar as atribuições de políticas de segurança predefinidas

As etapas para modificar  a atribuição da política de segurança proteção padrão ou proteção estrita são as mesmas de quando você atribuiu inicialmente as políticas de segurança predefinidas [aos usuários](#use-the-microsoft-365-defender-portal-to-assign-preset-security-policies-to-users). 

Para desabilitar as  **políticas** de segurança de proteção padrão ou de proteção estrita enquanto ainda preserva as condições e exceções existentes, deslize a alternância para **Desabilitado** ![ Desativar a Alternância ](../../media/scc-toggle-off.png) . Para habilitar as políticas, deslize a alternância **para Habilitado** ![ para ](../../media/scc-toggle-on.png) Ativar.

### <a name="how-do-you-know-these-procedures-worked"></a>Como saber se esses procedimentos funcionaram?

Para verificar se você atribuiu  com êxito  a política de segurança proteção padrão ou proteção estrita a um usuário, use uma configuração de proteção em que o valor padrão é diferente da configuração **de** proteção Padrão, que é diferente da configuração **de** proteção estrita.

Por exemplo, para emails detectados como spam (não spam de alta confiança) verifique  se a mensagem é  entregue à pasta Lixo Eletrônico para usuários de proteção padrão e colocada em quarentena para usuários de proteção estrita.

Ou, para email em [massa,](bulk-complaint-level-values.md)verifique se o valor BCL 6  ou superior entrega a mensagem para a pasta Lixo  Eletrônico para usuários de proteção padrão, e o valor BCL 4 ou superior coloca em quarentena a mensagem para usuários de proteção estrita.
