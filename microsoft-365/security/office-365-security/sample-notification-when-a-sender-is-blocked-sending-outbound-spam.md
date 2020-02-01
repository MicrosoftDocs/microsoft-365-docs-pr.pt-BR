---
title: Notificação de exemplo de quando um remetente é bloqueado ao enviar spam de saída
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/02/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c33fd406-a4c8-4ac8-ad85-123996c5cded
ms.collection:
- M365-security-compliance
description: 'Quando um remetente é bloqueado do serviço devido ao envio de spam de saída, o administrador de domínio especificado ao configurar a política de spam de saída receberá um email de notificação semelhante ao seguinte:'
ms.openlocfilehash: 537e97fe952ad9a5b2ca854c44fe6c53b642e3ac
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598498"
---
# <a name="sample-notification-when-a-sender-is-blocked-sending-outbound-spam"></a>Notificação de exemplo de quando um remetente é bloqueado ao enviar spam de saída

Quando um remetente é bloqueado do serviço devido ao envio de spam de saída, o administrador de domínio especificado ao [Configurar a política de spam de saída](configure-the-outbound-spam-policy.md) receberá um email de notificação semelhante ao seguinte: 
  
 **Endereço do remetente:** spamalerts@microsoft.com 
  
 **Assunto:** Notificação de spam de \<saída- *nome* \> da conta bloqueado do envio de email de saída     
  
 **Corpo:** Esta é uma resposta automática do sistema de análise de spam do Exchange Online Protection. 
  
Você está sendo contatado porque detectamos altos volumes de email marcados como spam ou outro comportamento suspeito originado da sua organização. As contas de email a seguir foram impedidas de enviar email (eles ainda podem receber emails):
  
\<*nome da conta*  \> 
  
É provável que essa conta de email tenha sido comprometida. Siga estas etapas:
  
1. Resolva este problema ao seu lado:
    
  - Alterar a senha da conta.
    
  - Determinando como a conta foi comprometida.
    
  - Tomar precauções para garantir que essa vulnerabilidade não será explorada novamente.
    
  - Confirmando que a fila de saída de emails foi limpa de todas as mensagens transgressores.
    
2. Entre em contato com o suporte da Microsoft usando seu canal de contato normal.
    
3. Explique que você tem um usuário que é bloqueado pelo envio de emails e que o problema foi tratado.
    
4. O agente criará um tíquete de suporte com as informações que você fornecer e o escalonará para ter o endereço de email ou o domínio desbloqueado.
    
5. Depois que o endereço tiver sido desbloqueado e não tiver outros problemas, você será contatado e alertado para o desbloqueio.
    
Obrigado por nos ajudar a controlar emails indesejados.
  
Proteção do Exchange Online.
  
\*\*Observação: não responda a este email à medida que ele é enviado de um endereço não monitorado\*\*
  
> [!TIP]
> Você também pode entrar em contato com o suporte via opções documentadas em [ajuda e suporte para o EOP](help-and-support-for-eop.md). 
  

