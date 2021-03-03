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
description: Os administradores podem aprender a aplicar configurações de política padrão e estrita nos recursos de proteção do Exchange Online Protection (EOP) e do Microsoft Defender para Office 365
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b49b980d217d60865029c8e64ad02ed722f6b86e
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407451"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a>Políticas de segurança predefinidas no EOP e no Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

As políticas de segurança predefinidas fornecem um local centralizado para aplicar todas as políticas recomendadas de spam, malware e phishing aos usuários de uma só vez. As configurações de política não são configuráveis. Em vez disso, eles são definidos por nós e se baseiam em nossas observações e experiências nos datacenters para um equilíbrio entre manter o conteúdo prejudicial longe dos usuários sem interromper seu trabalho.

O restante deste tópico descreve políticas de segurança predefinidas e como configurá-las.

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

Só é possível usar uma condição ou exceção uma vez; contudo, você pode especificar vários valores para a condição ou exceção. Vários valores da mesma condição ou exceção usam a lógica OU (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_). Para diferentes condições ou exceções, use a lógica E (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_).

As condições e exceções disponíveis são:

- **Os destinatários são**: Caixas de correio, usuários de email ou contatos de email em sua organização.
- **Os destinatários são membros de**: Grupos em sua organização.
- **Os domínios do destinatário são**: Domínios aceitos configurados no Microsoft 365.

### <a name="policies-in-preset-security-policies"></a>Políticas em políticas de segurança predefinidas

As políticas de segurança predefinidas usam as políticas correspondentes dos vários recursos de proteção no EOP e no Microsoft Defender para Office 365. Essas políticas são _criadas depois que_ você atribui a **proteção padrão** ou políticas **de** segurança predefinidas de proteção estrita aos usuários. Não é possível modificar essas políticas.

- Políticas de Proteção do **Exchange Online (EOP)**: Isso inclui organizações do Microsoft 365 com caixas de correio do Exchange Online e organizações EOP autônomas sem caixas de correio do Exchange Online:

  - [Políticas anti-spam denominadas](configure-your-spam-filter-policies.md) Política de **Segurança Predefinida Padrão** e **Política de Segurança Predefinida Estrita.**
  - [Políticas anti-malware denominadas](configure-anti-malware-policies.md) **Política de Segurança Predefinida Padrão** e Política de Segurança **Predefinida Estrita.**
  - [Políticas anti-phishing do EOP denominadas](set-up-anti-phishing-policies.md#spoof-settings) Política de **Segurança Predefinida Padrão** e **Política** de Segurança Predefinida Estrita (configurações de spoof).

- **Políticas do Microsoft Defender para Office 365**: Isso inclui organizações com assinaturas de complemento do Microsoft 365 E5 ou do Defender para Office 365:

  - Políticas anti-phishing no Microsoft Defender para Office 365 denominadas **Política** de Segurança Predefinida Padrão e **Política** de Segurança Predefinida Estrita , que incluem:

    - As mesmas [configurações de spoof](set-up-anti-phishing-policies.md#spoof-settings) que estão disponíveis nas políticas anti-phishing do EOP.
    - [Configurações de representação](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [Limites avançados de phishing](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - [Políticas de Links Seguros](set-up-atp-safe-links-policies.md) **denominadas Política de Segurança Predefinida Padrão** e Política de Segurança **Predefinida Estrita.**

  - [Políticas de Anexos Seguros denominadas](set-up-atp-safe-attachments-policies.md) **Política de Segurança Predefinida Padrão** e Política de Segurança **Predefinida Estrita.**

Observe que você pode aplicar proteções do EOP a usuários diferentes do Microsoft Defender para proteções do Office 365.

### <a name="policy-settings-in-preset-security-policies"></a>Configurações de política em políticas de segurança predefinidas

Não é possível modificar as configurações de política nos perfis de proteção. Os **valores de configuração** de **política** Padrão e Estrita são descritos em Configurações recomendadas para a segurança do EOP e do Microsoft Defender para o [Office 365.](recommended-settings-for-eop-and-office365-atp.md)

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a>Ordem de precedência para políticas de segurança predefinidas e outras políticas

Quando várias políticas são aplicadas a um usuário, a ordem a seguir é aplicada da prioridade mais alta à prioridade mais baixa:

1. **Política de segurança predefinida** de proteção estrita
2. **Política de segurança predefinida** de proteção padrão
3. Políticas de segurança personalizadas
4. Políticas de segurança padrão

Em outras palavras, as  configurações da política de  proteção estrita substituem as configurações da política de proteção padrão, que substitui as configurações de uma política personalizada, que substitui as configurações da política padrão.

## <a name="assign-preset-security-policies-to-users"></a>Atribuir políticas de segurança predefinidas aos usuários

### <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>. Para ir diretamente para a página **Políticas de segurança** predefinidas, use <https://protection.office.com/presetSecurityPolicies> .

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Você precisa ter permissões atribuídas no **Exchange Online** antes de poder fazer os procedimentos neste artigo:
  - Para configurar políticas de segurança predefinidas, você precisa ser membro dos grupos de função Gerenciamento da Organização **ou** **Administrador de** Segurança.
  - Para acesso somente leitura a políticas de segurança predefinidas, você precisa ser membro do grupo de função **Leitor Global.**

  Para obter mais informações, confira [Permissões no Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).

  **Observação**: Adicionar usuários à função correspondente do Azure Active Directory no Centro de  administração do Microsoft 365 fornece aos usuários as permissões e permissões necessárias para outros recursos no Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).

### <a name="use-the-security--compliance-center-to-assign-preset-security-policies-to-users"></a>Use o Centro de Conformidade & segurança para atribuir políticas de segurança predefinidas aos usuários

1. No Centro de Conformidade & segurança,  acesse Políticas de segurança Predefinidas de Política de Gerenciamento \>  \> **de Ameaças.**

2. Em **Proteção padrão ou** proteção **estrita,** clique em **Editar**.

3. O **assistente Aplicar Proteção Padrão** ou Aplicar Proteção **Estrita** é iniciado. Nas **proteções do EOP se aplicam à** etapa, identifique os destinatários internos aos quais as proteções [EOP](#policies-in-preset-security-policies) se aplicam:

   1. Clique **em Adicionar uma condição**. No menu suspenso exibido, selecione uma condição em **Aplicado se**:

      - **Os destinatários são**
      - **Os destinatários são membros de**
      - **Os domínios do destinatário são**

      Você só pode usar uma condição uma vez, mas pode especificar vários valores para a condição. Vários valores da mesma condição usam a lógica OR (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_ ).

   2. A condição selecionada aparece em uma seção sombreada. Nessa seção, clique na **caixa Qualquer um desses.** Se você aguardar um momento, uma lista aparecerá para que você possa selecionar um valor. Ou você pode começar a digitar um valor para filtrar a lista e selecionar um valor. Repita essa etapa quantas vezes forem necessárias. Para remover um valor individual, clique em **Remover** ![ ícone remover no ](../../media/scc-remove-icon.png) valor. Para remover toda a condição, clique em **Remover** ![ ícone remover na ](../../media/scc-remove-icon.png) condição.

   3. Para adicionar outra condição, clique **em Adicionar uma condição** e selecione entre as condições restantes. Condições diferentes usam a lógica AND (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_ ).

      Repita a etapa anterior para adicionar valores à condição e repita essa etapa quantas vezes for necessário ou até ficar sem condições.

   4. Para adicionar uma exceção, clique **em Adicionar uma condição**. Na lista lista listada exibida, selecione uma condição em **Except when**. As configurações e o comportamento são exatamente como as condições.

   Quando terminar, clique em **Avançar**.

4. Se sua organização tiver o Microsoft Defender para Office 365, você será levado para as proteções **atp** aplicar-se à etapa para identificar os destinatários internos aos quais as proteções do [Microsoft Defender para Office 365](#policies-in-preset-security-policies) se aplicam.

   As configurações e o comportamento são exatamente como as proteções **do EOP se aplicam à** etapa.

   Quando terminar, clique em **Avançar**.

5. Na etapa **Confirmar,** verifique suas seleções e clique em **Confirmar**.

### <a name="use-the-security--compliance-center-to-modify-the-assignments-of-preset-security-policies"></a>Use o Centro de Conformidade & segurança para modificar as atribuições de políticas de segurança predefinidas

As etapas para modificar  a atribuição da política de segurança proteção padrão ou proteção estrita são as mesmas de quando você atribuiu inicialmente as políticas de segurança predefinidas [aos usuários](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users). 

Para desabilitar as  **políticas** de segurança de proteção padrão ou proteção estrita enquanto ainda preserva as condições e exceções existentes, deslize a alternância para **Desabilitado**. Para habilitar as políticas, deslize a alternância **para Habilitado**.

### <a name="how-do-you-know-these-procedures-worked"></a>Como saber se esses procedimentos funcionaram?

Para verificar se você atribuiu  com êxito  a política de segurança proteção padrão ou proteção estrita a um usuário, use uma configuração de proteção em que o valor padrão é diferente da configuração **de** proteção Padrão, que é diferente da configuração **de** proteção estrita.

Por exemplo, para emails detectados como spam (não spam de alta confiança) verifique  se a mensagem é  entregue à pasta Lixo Eletrônico para usuários de proteção padrão e colocada em quarentena para usuários de proteção estrita.

Ou, para email em [massa,](bulk-complaint-level-values.md)verifique se o valor BCL 6  ou superior entrega a mensagem para a pasta Lixo  Eletrônico para usuários de proteção padrão, e o valor BCL 4 ou superior coloca em quarentena a mensagem para usuários de proteção estrita.
