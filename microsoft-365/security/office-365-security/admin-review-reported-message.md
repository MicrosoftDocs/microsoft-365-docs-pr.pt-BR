---
title: Análise do administrador de mensagens relatadas
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Saiba como revisar as mensagens relatadas e fazer comentários aos usuários.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7386f5b283e2bfabb76eee91d33dfda0e42ec7b1
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769120"
---
# <a name="admin-review-for-reported-messages"></a>Análise do administrador de mensagens relatadas

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!NOTE]
> As informações neste artigo se relacionam a um produto de visualização que pode ser substancialmente modificado antes de ser lançado comercialmente. Este documento é fornecido apenas para fins de avaliação e exploração.

**Aplica-se a**
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Em Microsoft 365 com caixas de correio Exchange Online e o Microsoft Defender para Office 365, os administradores agora podem enviar mensagens com modelos de volta aos usuários finais depois de revisarem as mensagens relatadas. Isso também pode ser personalizado para sua organização e com base no veredito do administrador.

Esse recurso foi projetado para dar feedback aos usuários, mas não altera os vereditos das mensagens no sistema. Para ajudar a Microsoft a atualizar e melhorar seus filtros, você precisará enviar mensagens para análise usando [o envio de Administrador.](admin-submission.md)

Você só poderá marcar e notificar os usuários dos resultados da revisão se a mensagem for relatada como falsos [positivos ou falsos negativos.](report-false-positives-and-false-negatives.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Do que você precisa saber para começar?

- Para modificar a configuração para envios do usuário, você precisa ser membro de um dos seguintes grupos de função:
  - Gerenciamento da organização ou Administrador de Segurança [no Microsoft 365 de segurança.](permissions-microsoft-365-security-center.md)
  - Gerenciamento de organização em [Exchange Online](/Exchange/permissions-exo/permissions-exo).

- Você também precisará de acesso ao Exchange Online PowerShell. Se a conta que você está tentando usar não tiver acesso ao Exchange Online PowerShell, você receberá um erro que diz Especificar um endereço de email em *seu domínio*. Para obter mais informações sobre a habilitação ou desabilitação do acesso ao Exchange Online PowerShell, consulte os seguintes tópicos:
  - [Habilitar ou desabilitar o acesso Exchange Online PowerShell](/powershell/exchange/disable-access-to-exchange-online-powershell)
  - [Regras de Acesso para Cliente no Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="configure-the-messages-used-to-notify-users"></a>Configurar as mensagens usadas para notificar os usuários

1. No centro [de Microsoft 365 de segurança](../defender/overview-security-center.md), vá para Políticas & **políticas** de ameaça As configurações de mensagem \>  \> **relatadas pelo usuário.**

2. Se você quiser especificar o nome de exibição do remetente, marque Office 365 caixa especificar um endereço de **email** para usar como remetente na seção Notificações de **email** para resultados de revisão de administrador e insira o nome que deseja usar. Este é o endereço de email que ficará visível no Outlook e para onde as respostas serão.

3. Se você quiser personalizar qualquer um dos modelos, clique em **Personalizar notificação de email**. Neste sobrevoo, você poderá personalizar apenas o seguinte:
    - Phishing
    - Lixo eletrônico
    - Nenhuma ameaça encontrada
    - Treinamento de conscientização
    - Rodapé

4. Quando concluir, clique em **Salvar**. Para limpar esses valores, clique **em Descartar** na página Envios do usuário.
