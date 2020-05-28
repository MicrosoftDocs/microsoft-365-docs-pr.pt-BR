---
title: Resolver problemas com caixas de correio compartilhadas
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
search.appverid:
- BCS160
- MET150
- MOE150
description: Tente estas soluções se você tiver problemas com caixas de correio compartilhadas.
ms.openlocfilehash: 5d6de9ac66b11f0e50b259cdca0b1bb50b8326ee
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400011"
---
# <a name="resolve-issues-with-shared-mailboxes"></a>Resolver problemas com caixas de correio compartilhadas

Se você vir mensagens de erro ao criar ou usar uma caixa de correio compartilhada, tente estas soluções possíveis. 

## <a name="error-when-creating-shared-mailboxes"></a>Erro ao criar caixas de correio compartilhadas
<a name="bkmk_Fix"> </a>

Se você vir a mensagem de erro, **o endereço de proxy "SMTP: <nome da caixa de correio compartilhada \> " já estiver sendo usado pelos endereços proxy ou legacyExchangeDN de " \<name> ". Escolha outro endereço de proxy**, significa que você está tentando dar um nome à caixa de correio compartilhada que já está em uso. Por exemplo, digamos que você deseja nomear as caixas de correio compartilhadas como info@dominio1 e info@dominio2. Há duas maneiras de fazer isso:

  - Use o Windows PowerShell. Confira esta postagem de blog para obter instruções: [criar caixas de correio compartilhadas com o mesmo alias em domínios diferentes](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)
    
  - Nomeie a segunda caixa de correio compartilhada algo diferente do início para contornar o erro. Em seguida, no centro de administração, renomeie a caixa de correio compartilhada para o que você deseja.

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a>Erro sobre não ter permissões de envio ao usar uma caixa de correio compartilhada

Se você criou uma caixa de correio compartilhada e, em seguida, tenta enviar uma mensagem dela, você pode fazer isso:

**Não foi possível enviar esta mensagem. Você não tem permissão para enviar a mensagem em nome do usuário especificado.**

Esta mensagem é exibida quando o Microsoft 365 está enfrentando um problema de latência de replicação. Ela deve desaparecer em uma hora ou assim, quando as informações sobre sua nova caixa de correio compartilhada (ou usuário adicionado) são replicadas em todos os nossos data centers. Aguarde uma hora e tente novamente enviar uma mensagem.

## <a name="related-articles"></a>Artigos relacionados

[Sobre as caixas de correio compartilhadas](about-shared-mailboxes.md)

[Criar uma caixa de correio compartilhada](create-a-shared-mailbox.md)

[Configurar uma caixa de correio compartilhada](configure-a-shared-mailbox.md)

[Converter uma caixa de correio do usuário em uma caixa de correio compartilhada](convert-user-mailbox-to-shared-mailbox.md).

[Remover uma licença de uma caixa de correio compartilhada](remove-license-from-shared-mailbox.md)


    

