---
title: Resolver problemas com caixas de correio compartilhadas
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: Experimente essas soluções se tiver problemas com caixas de correio compartilhadas.
ms.openlocfilehash: ba62db76edff6e4ab3d738ed0af8db2a40c18394
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926481"
---
# <a name="resolve-issues-with-shared-mailboxes"></a>Resolver problemas com caixas de correio compartilhadas

Se você vir mensagens de erro ao criar ou usar uma caixa de correio compartilhada, experimente estas soluções possíveis. 

## <a name="error-when-creating-shared-mailboxes"></a>Erro ao criar caixas de correio compartilhadas
<a name="bkmk_Fix"> </a>

Se você vir a mensagem de erro, o endereço proxy "smtp:<shared mailbox name " já está sendo usado pelos endereços proxy ou **\> LegacyExchangeDN de " \<name> ". Escolha outro endereço proxy,** significa que você está tentando dar um nome à caixa de correio compartilhada que já está em uso. Por exemplo, digamos que você deseja nomear as caixas de correio compartilhadas como info@dominio1 e info@dominio2. Há duas maneiras de fazer isso:

  - Use o Windows PowerShell. Confira esta postagem de blog para obter instruções: [Criar caixas de correio compartilhadas com o mesmo alias em domínios diferentes](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)
    
  - Nomee a segunda caixa de correio compartilhada diferente do início para evitar o erro. Em seguida, no centro de administração, renomeie a caixa de correio compartilhada como você deseja que ela seja.

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a>Erro sobre não ter permissões de envio ao usar uma caixa de correio compartilhada

Se você criou uma caixa de correio compartilhada e tentou enviar uma mensagem dela, pode receber isto:

**Não foi possível enviar essa mensagem. Você não tem permissão para enviar a mensagem em nome do usuário especificado.**

Esta mensagem é exibida quando o Microsoft 365 está enfrentando um problema de latência de replicação. Ele deve desaparecer em uma hora ou mais, quando as informações sobre sua nova caixa de correio compartilhada (ou usuário adicionado) são replicadas em todos os nossos data centers. Aguarde uma hora e tente novamente enviar uma mensagem.

## <a name="related-articles"></a>Artigos relacionados

[Sobre as caixas de correio compartilhadas](about-shared-mailboxes.md)

[Criar uma caixa de correio compartilhada](create-a-shared-mailbox.md)

[Configurar uma caixa de correio compartilhada](configure-a-shared-mailbox.md)

[Converter uma caixa de correio do usuário em uma caixa de correio compartilhada](convert-user-mailbox-to-shared-mailbox.md).

[Remover uma licença de uma caixa de correio compartilhada](remove-license-from-shared-mailbox.md)


    

