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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a aplicar as configurações de política padrão e estrita nos recursos de proteção do Exchange Online Protection (EOP) e no Office 365 Advanced Threat Protection (ATP)
ms.openlocfilehash: a2f0472d8dd44c90fd5db14e71d2db0d5d323b50
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825252"
---
# <a name="preset-security-policies-in-eop-and-office-365-atp"></a>Políticas de segurança predefinidas no EOP e no Office 365 ATP

As políticas de segurança predefinidas fornecem um local centralizado para aplicar todas as políticas recomendadas de spam, malware e phishing aos usuários de uma só vez. As configurações de política não são configuráveis. Em vez disso, eles são definidos por nós e são baseados em observações e experiências nos data centers para obter um equilíbrio entre manter o conteúdo prejudicial longe dos usuários sem interromper o trabalho.

O restante deste tópico descreve as políticas de segurança predefinidas e como configurá-las.

## <a name="what-preset-security-policies-are-made-of"></a>Quais políticas de segurança predefinidas são feitas

As políticas de segurança predefinidas consistem nos seguintes elementos:

- Perfis
- Políticas
- Configurações de política

Além disso, a ordem de precedência é importante se várias diretivas de segurança predefinidas e outras políticas se aplicarem à mesma pessoa.

### <a name="profiles-in-preset-security-policies"></a>Perfis em políticas de segurança predefinidas

Um perfil determina o nível de proteção. Os seguintes perfis estão disponíveis:

- **Proteção padrão**: um perfil de proteção de linha de base adequado para a maioria dos usuários.
- **Proteção estrita**: um perfil de proteção mais agressivo para usuários selecionados (metas de alto valor ou usuários com prioridade).

Você usa regras com condições e exceções que determinam a quem os perfis estão ou não são aplicados.

Só é possível usar uma condição ou exceção uma vez; contudo, você pode especificar vários valores para a condição ou exceção. Vários valores da mesma condição ou exceção usam a lógica OU (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_). Para diferentes condições ou exceções, use a lógica E (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_).

As condições e exceções disponíveis são:

- **Os destinatários são**: caixas de correio, usuários de email ou contatos de email em sua organização.
- **Os destinatários são membros de**: grupos na sua organização.
- **Os domínios de destinatário são**: domínios aceitos que são configurados no Microsoft 365.

### <a name="policies-in-preset-security-policies"></a>Políticas em políticas de segurança predefinidas

As políticas de segurança predefinidas usam as políticas correspondentes dos vários recursos de proteção no EOP e no Office 365 ATP. Essas políticas são criadas _depois_ que você atribui as políticas de segurança predefinidas de **proteção padrão** ou **proteção estrita** aos usuários. Você não pode modificar essas políticas.

- **Políticas de proteção do Exchange Online (EOP)**: isso inclui as organizações do Microsoft 365 com caixas de correio do Exchange Online e organizações autônomas do EOP sem caixas de correio do Exchange Online:
  
  - [Políticas antispam](configure-your-spam-filter-policies.md) chamadas política de **segurança predefinida padrão** e **política de segurança predefinida restrita**.
  - [Diretivas Antimalware](configure-anti-malware-policies.md) chamadas **política de segurança predefinida padrão** e **política de segurança predefinida restrita**.
  - [EOP políticas anti-phishing](set-up-anti-phishing-policies.md#spoof-settings) chamadas política de **segurança** predefinida padrão e **política de segurança predefinida restrita** (configurações de spoof).

- **Políticas de proteção avançada contra ameaças (ATP) do office 365**: inclui organizações com as assinaturas do Microsoft 365 E5 ou do Office 365 ATP Add-on:

  - Diretivas antiphishing da ATP chamadas de **política de segurança predefinida padrão** e **política de segurança predefinida estrita**, que incluem:

    - As mesmas [configurações de spoof](set-up-anti-phishing-policies.md#spoof-settings) que estão disponíveis nas políticas anti-phishing do EOP.
    - [Configurações de representação](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [Limites avançados de phishing](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - [Políticas de links seguros](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users) chamada **política de segurança predefinida padrão** e **política de segurança predefinida estrita**.

  - [Políticas de anexos seguros](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users) chamadas **política de segurança predefinida padrão** e **política de segurança predefinida estrita**.

Observe que você pode aplicar proteções do EOP a diferentes usuários do que as proteções ATP.

### <a name="policy-settings-in-preset-security-policies"></a>Configurações de política em políticas de segurança predefinidas

Você não pode modificar as configurações de política nos perfis de proteção. Os valores de configuração de política **padrão** e **estrito** são descritos em [configurações recomendadas para a segurança do EOP e do Office 365 ATP](recommended-settings-for-eop-and-office365-atp.md).

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a>Ordem de precedência para políticas de segurança predefinidas e outras políticas

Quando várias políticas são aplicadas a um usuário, a ordem a seguir é aplicada da prioridade mais alta à prioridade mais baixa:

1. Política de segurança predefinida de **proteção estrita**
2. Política de segurança predefinida de **proteção padrão**
3. Políticas de segurança personalizadas
4. Políticas de segurança padrão

Em outras palavras, as configurações da política de **proteção estrita** substituem as configurações da política de **proteção padrão** , que substitui as configurações de uma política personalizada, que substitui as configurações da política padrão.

## <a name="assign-preset-security-policies-to-users"></a>Atribuir políticas de segurança predefinidas aos usuários

### <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>. Para ir diretamente para a página **políticas de segurança predefinidas** , use <https://protection.office.com/presetSecurityPolicies> .

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Você precisa ter permissões atribuídas antes de poder executar os procedimentos neste tópico:

  - Para configurar políticas de segurança predefinidas, você precisa ser membro de um dos grupos de função a seguir:

    - **Gerenciamento de organizações** ou **Administrador de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).
    - **Gerenciamento de organizações** ou **Gerenciamento de higiene** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - Para acesso somente leitura às políticas de segurança predefinidas, você precisa ser membro de um dos seguintes grupos de função:

    - **Leitor de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).
    - **Gerenciamento da organização Somente visualização** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

### <a name="use-the-security--compliance-center-to-assign-preset-security-policies-to-users"></a>Usar o centro de conformidade de & de segurança para atribuir políticas de segurança predefinidas aos usuários

1. No centro de conformidade & segurança, vá para **Threat management** \> **Policy** \> **políticas de segurança predefinidas**da política de gerenciamento de ameaças.

2. Em **proteção padrão** ou **proteção estrita**, clique em **Editar**.

3. O assistente **aplicar proteção padrão** ou **aplicar proteção estrita** é iniciado. Nas **proteções do EOP aplicam** -se à etapa, identifique os destinatários internos aos quais as [proteções do EOP](#policies-in-preset-security-policies) se aplicam:

   1. Clique em **Adicionar uma condição**. Na lista suspensa exibida, selecione uma condição em **aplicado se**:

      - **Os destinatários são**
      - **Os destinatários são membros de**
      - **Os domínios do destinatário são**

      Você só pode usar uma condição uma vez, mas pode especificar vários valores para a condição. Vários valores do mesmo uso ou lógica de condição (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_ ).

   2. A condição selecionada aparece em uma seção sombreada. Nessa seção, clique na caixa **qualquer uma** dessas caixas. Se você esperar um instante, uma lista será exibida para que você possa selecionar um valor. Ou você pode começar a digitar um valor para filtrar a lista e selecionar um valor. Repita essa etapa quantas vezes forem necessárias. Para remover um valor individual, clique em **remover** ![ ícone de remoção ](../../media/scc-remove-icon.png) no valor. Para remover a condição inteira, clique em **remover** ![ ícone de remoção ](../../media/scc-remove-icon.png) na condição.

   3. Para adicionar outra condição, clique em **Adicionar uma condição** e selecione entre as condições restantes. Condições diferentes de uso e lógica (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_ ).

      Repita a etapa anterior para adicionar valores à condição e repita essa etapa quantas vezes forem necessárias ou até que você fique sem condições.

   4. Para adicionar uma exceção, clique em **Adicionar uma condição**. Na lista suspensa exibida, selecione uma condição em **exceto quando**. As configurações e o comportamento são exatamente como as condições.

   Quando terminar, clique em **Avançar**.

4. Se sua organização tiver o Office 365 ATP, você será levado para as **proteções de ATP aplicam** -se à etapa para identificar os destinatários internos aos quais as [proteções do Office 365 ATP](#policies-in-preset-security-policies) se aplicam.

   As configurações e o comportamento são exatamente como as **proteções do EOP se aplicam à** etapa.

   Quando terminar, clique em **Avançar**.

5. Na etapa **confirmar** , verifique suas seleções e clique em **confirmar**.

### <a name="use-the-security--compliance-center-to-modify-the-assignments-of-preset-security-policies"></a>Usar o centro de conformidade de & de segurança para modificar as atribuições de políticas de segurança predefinidas

As etapas para modificar a atribuição da política de segurança de **proteção padrão** ou **proteção estrita** são as mesmas de quando você [atribuiu inicialmente as políticas de segurança predefinidas aos usuários](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users).

Para desabilitar a **proteção padrão** ou políticas de segurança de **proteção estrita** e, ao mesmo tempo, preservar as condições e exceções existentes, deslize a opção para **desabilitado**. Para habilitar as políticas, deslize a opção para **habilitado**.

### <a name="how-do-you-know-these-procedures-worked"></a>Como saber se esses procedimentos funcionaram?

Para verificar se você atribuiu com êxito a política de segurança de proteção **padrão** ou **proteção estrita** a um usuário, use uma configuração de proteção onde o valor padrão é diferente da configuração de **proteção padrão** , que é diferente da configuração de **proteção estrita** .

Por exemplo, para email que é detectado como spam (não spam de alta confiança) Verifique se a mensagem foi entregue à pasta lixo eletrônico para usuários de **proteção padrão** e em quarentena para usuários de **proteção estrita** .

Ou, para [emails em massa](bulk-complaint-level-values.md), verifique se o valor de BCL 6 ou superior entrega a mensagem para a pasta lixo eletrônico para usuários de **proteção padrão** e o valor de BCL 4 ou superior coloca em quarentena a mensagem para usuários de **proteção estrita** .
