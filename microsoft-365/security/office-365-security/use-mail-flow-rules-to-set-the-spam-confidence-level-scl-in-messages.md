---
title: Usar regras de fluxo de email para o SCL nas mensagens
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: Saiba como criar regras de fluxo de emails (regras de transporte) para identificar mensagens e definir o nível de confiança de spam (SCL) das mensagens na proteção do Exchange Online.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 67a4c25a1006e9b1554cf8ffbc2d5e29b4063752
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827368"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a>Usar regras de fluxo de emails para definir o nível de confiança de spam (SCL) em mensagens no EOP

Nas organizações do Microsoft 365 com caixas de correio em organizações do Exchange Online ou do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, o EOP usa políticas antispam (também conhecidas como políticas de filtro de spam ou políticas de filtro de conteúdo) para examinar mensagens de entrada para spam. Para obter mais informações, consulte [Configure as políticas de anti-spam no EOP](configure-your-spam-filter-policies.md).

Se você deseja marcar mensagens específicas como spam antes que elas sejam verificadas por filtragem de spam ou marcar mensagens para que elas ignorem a filtragem de spam, você pode criar regras de fluxo de emails (também conhecidas como regras de transporte) para identificar as mensagens e definir o SCL (nível de confiança de spam). Para obter mais informações sobre o SCL, consulte [nível de confiança de spam (SCL) no EOP](spam-confidence-levels.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Você precisa receber permissões no Exchange Online antes de poder executar estes procedimentos. Especificamente, você precisa receber a função de **regras de transporte** , que é atribuída às funções de gerenciamento da **organização**, **Gerenciamento de conformidade**e gerenciamento de **registros** por padrão. Para saber mais, confira [Gerenciar Grupos de Funções do Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).

- Para abrir o Eat no Exchange Online, confira [Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).

- Para obter mais informações sobre regras de fluxo de email no Exchange Online, consulte [regras de fluxo de emails (regras de transporte) no Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a>Use o Eat para criar uma regra de fluxo de emails que define o SCL de uma mensagem

1. No EAC, vá para **Fluxo de emails** \> **Regras**.

2. Clique em **Adicionar** ![ ícone ](../../media/ITPro-EAC-AddIcon.png) de adição e selecione **criar uma nova regra**.

3. Na página **nova regra** que é aberta, defina as seguintes configurações:

   - **Name**: Insira um nome exclusivo e descritivo para a regra.

   - Clique em **mais opções**.

   - **Aplicar esta regra se**: selecione uma ou mais condições para identificar mensagens. Para obter mais informações, consulte [regras e exceções de regra de fluxo de emails (predicados) no Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).

   - **Faça o seguinte**: selecione **modificar as propriedades da mensagem** \> **definem o nível de confiança de spam (SCL)**. Na caixa de diálogo **especificar SCL** exibida, configure um dos seguintes valores:

   - **Ignorar filtragem de spam**: as mensagens irão ignorar a filtragem de spam.

     > [!CAUTION]
     > Tenha muito cuidado para permitir que as mensagens ignorem a filtragem de spam. Os invasores podem usar essa vulnerabilidade para enviar phishing e outras mensagens mal-intencionadas para sua organização. As regras de fluxo de emails exigem mais do que apenas o domínio ou endereço de email do remetente. Para obter mais informações, consulte [criar listas de remetentes seguros no EOP](create-safe-sender-lists-in-office-365.md).

   - **0 a 4**: a mensagem é enviada por filtragem de spam para processamento adicional.

   - **5 ou 6**: a mensagem é marcada como **spam**. A ação que você configurou para filtragem de **spam** verdicts em suas políticas antispam é aplicada à mensagem (o valor padrão é **mover mensagem para a pasta lixo eletrônico**).

   - **7 a 9**: a mensagem é marcada como **spam de alta confiança**. A ação que você configurou para a filtragem de **spam de alta confiança** verdicts nas políticas antispam é aplicada à mensagem (o valor padrão é **mover mensagem para a pasta lixo eletrônico**).

4. Especifique as propriedades adicionais que você deseja para a regra. Quando concluir, clique em **Salvar**.

## <a name="how-do-you-know-this-worked"></a>Como saber se funcionou?

Para verificar se esse procedimento está funcionando corretamente, envie uma mensagem de email para alguém dentro da sua organização e verifique se a ação executada na mensagem é conforme o esperado. Por exemplo, se você **definir o nível de confiança de spam (SCL)** para **ignorar a filtragem de spam**, a mensagem deverá ser enviada para a caixa de entrada do destinatário especificado. No entanto, se você **definir o nível de confiança de spam (SCL)** como **9**e a ação de **spam de alta confiança** para suas políticas antispam aplicáveis for mover a mensagem para a pasta lixo eletrônico, a mensagem deverá ser enviada para a pasta de lixo eletrônico do destinatário especificado.
