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
ms.openlocfilehash: 217f5ebb1692d68b5dc70988888bf78d4bd36a0c
ms.sourcegitcommit: d0c160e89e17f451199bc4a85699effd2d935213
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2021
ms.locfileid: "52893723"
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

- Você abre o portal Microsoft 365 Defender em <https://security.microsoft.com/> . Para ir diretamente para a página **Envios,** use <https://security.microsoft.com/reportsubmission> .

- Para modificar a configuração para envios do usuário, você precisa ser membro de um dos seguintes grupos de função:
  - Gerenciamento da organização ou Administrador de Segurança [no portal Microsoft 365 Defender.](permissions-microsoft-365-security-center.md)
  - Gerenciamento de organização em [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).

- Você também precisará de acesso ao Exchange Online PowerShell. Se a conta que você está tentando usar não tiver acesso ao Exchange Online PowerShell, você receberá um erro que diz Especificar um endereço de email em *seu domínio*. Para obter mais informações sobre a habilitação ou desabilitação do acesso ao Exchange Online PowerShell, consulte os seguintes tópicos:
  - [Habilitar ou desabilitar o acesso Exchange Online PowerShell](/powershell/exchange/disable-access-to-exchange-online-powershell)
  - [Regras de Acesso para Cliente no Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="configure-the-messages-used-to-notify-users"></a>Configurar as mensagens usadas para notificar os usuários

1. No portal Microsoft 365 Defender, acesse **Email & políticas** de colaboração & políticas de ameaça Outras seção Configurações de mensagem \>  \>  \>  \> **relatadas pelo usuário**.

2. Na página **Envios** de usuário, se você quiser especificar o nome de exibição do remetente **Office 365,** marque a caixa para Especificar um endereço de email para usar como remetente na seção Notificações de email para resultados de revisão de administrador e insira o nome que deseja usar.  Este é o endereço de email que ficará visível no Outlook e para onde as respostas serão.

3. Se você quiser personalizar qualquer um dos modelos, clique em **Personalizar notificação de email**. Neste sobrevoo, você poderá personalizar apenas o seguinte:
    - Phishing
    - Lixo eletrônico
    - Nenhuma ameaça encontrada
    - Treinamento de conscientização
    - Rodapé

4. Quando concluir, clique em **Salvar**. Para limpar esses valores, clique **em Descartar** na página Envios do usuário.
