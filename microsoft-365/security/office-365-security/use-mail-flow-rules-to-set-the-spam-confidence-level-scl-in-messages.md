---
title: Usar regras de fluxo de emails para o SCL em mensagens
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: Saiba como criar regras de fluxo de emails (regras de transporte) para identificar mensagens e definir o nível de confiança de spam (SCL) de mensagens no Exchange Online Protection.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: aa2893214543f77114d517dc38f874d6172a920a
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287552"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a>Usar regras de fluxo de emails para definir o nível de confiança de spam (SCL) em mensagens no EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Nas organizações do Microsoft 365 com caixas de correio no Exchange Online ou em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, o EOP usa políticas anti-spam (também conhecidas como políticas de filtro de spam ou políticas de filtro de conteúdo) para verificar mensagens de entrada em busca de spam. Para obter mais informações, consulte [Configure as políticas de anti-spam no EOP](configure-your-spam-filter-policies.md).

Se você quiser marcar mensagens específicas como spam antes que elas ainda são examinadas pela filtragem de spam ou marcar mensagens para que elas ignorem a filtragem de spam, você pode criar regras de fluxo de emails (também conhecidas como regras de transporte) para identificar as mensagens e definir o nível de confiança de spam (SCL). Para obter mais informações sobre o SCL, consulte O nível de confiança [de spam (SCL) no EOP.](spam-confidence-levels.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Para fazer os procedimentos deste artigo, você precisa ter permissões no Exchange Online ou no Exchange Online Protection. Especificamente, você precisa da **função** Regras de Transporte, que é atribuída aos  grupos de função Gerenciamento da Organização **,** Gerenciamento de Conformidade **(administradores** globais) e Gerenciamento de Registros por padrão.

  Para mais informações, confira os seguintes tópicos:

  - [Permissões no Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
  - [Permissões no EOP autônomo](feature-permissions-in-eop.md)
  - [Usar o EAC para modificar a lista de membros em grupos de função](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Para abrir o EAC no Exchange Online, confira o Centro de administração [do Exchange no Exchange Online.](https://docs.microsoft.com/Exchange/exchange-admin-center) Para abrir o EAC no EOP autônomo, confira o Centro de administração do [Exchange no EOP autônomo.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Para obter mais informações sobre regras de fluxo de emails no Exchange Online e na Proteção do Exchange Online, consulte Regras de fluxo de email (regras de [transporte) no Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a>Usar o EAC para criar uma regra de fluxo de emails que define o SCL de uma mensagem

1. No EAC, vá para **Fluxo de emails** \> **Regras**.

2. Clique **no** ![ ícone Adicionar e selecione Criar uma nova ](../../media/ITPro-EAC-AddIcon.png) **regra.**

3. Na página **Nova regra** que é aberta, de configure as seguintes configurações:

   - **Nome:** insira um nome exclusivo e descritivo para a regra.

   - Clique **em Mais Opções.**

   - **Aplique essa regra se:** selecionar uma ou mais condições para identificar mensagens. Para saber mais, confira Condições e exceções da regra de [fluxo de emails (predicados) no Exchange Online.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

   - **Faça o seguinte:** Selecione **Modificar as propriedades da mensagem** para definir o nível de confiança de spam \> **(SCL).** Na caixa **de diálogo Especificar SCL** exibida, configure um dos seguintes valores:

   - **Ignorar a filtragem de** spam: as mensagens ignorarão a filtragem de spam.

     > [!CAUTION]
     > Tenha muito cuidado ao permitir que as mensagens ignorem a filtragem de spam. Os invasores podem usar essa vulnerabilidade para enviar phishing e outras mensagens mal-intencionadas para sua organização. As regras de fluxo de emails exigem mais do que apenas o endereço de email ou domínio do remetente. Para obter mais informações, [consulte Criar listas de remetentes seguros no EOP.](create-safe-sender-lists-in-office-365.md)

   - **0 a 4:** A mensagem é enviada por meio da filtragem de spam para processamento adicional.

   - **5 ou 6**: A mensagem é marcada como **Spam**. A ação que você configurou para vereditos de filtragem de **spam** em suas políticas anti-spam é aplicada à mensagem (o valor padrão é Mover mensagem para a pasta Lixo **Eletrônico).**

   - **7 a 9:** A mensagem é marcada como **spam de alta confiança.** A ação que você configurou para vereditos de filtragem de **spam** de alta confiança em suas políticas anti-spam é aplicada à mensagem (o valor padrão é Mover mensagem para a pasta Lixo **Eletrônico).**

4. Especifique as propriedades adicionais que você deseja para a regra. Quando concluir, clique em **Salvar**.

## <a name="how-do-you-know-this-worked"></a>Como saber se funcionou?

Para verificar se esse procedimento está funcionando corretamente, envie uma mensagem de email para alguém dentro da sua organização e verifique se a ação executada na mensagem está conforme o esperado. Por exemplo, se você definir o nível de confiança de **spam (SCL)** como Ignorar a filtragem de **spam,** a mensagem deverá ser enviada para a caixa de entrada do destinatário especificado. No entanto, se você definir o nível de confiança de **spam (SCL)** como **9,** e a ação de **spam** de alta confiança para suas políticas anti-spam aplicáveis for mover a mensagem para a pasta Lixo Eletrônico, a mensagem deverá ser enviada para a pasta Lixo Eletrônico do destinatário especificado.
