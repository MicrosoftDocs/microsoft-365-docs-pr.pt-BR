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
description: Você pode receber erros ao configurar caixas de correio compartilhadas. Experimente essas soluções se você tiver problemas com caixas de correio compartilhadas.
ms.openlocfilehash: 89cdfbe29ab035b1eb6c3a0183629eef59d67477
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706125"
---
# <a name="resolve-issues-with-shared-mailboxes"></a>Resolver problemas com caixas de correio compartilhadas

Se você vir mensagens de erro ao criar ou usar uma caixa de correio compartilhada, experimente essas soluções possíveis. 

## <a name="error-when-creating-shared-mailboxes"></a>Erro ao criar caixas de correio compartilhadas
<a name="bkmk_Fix"> </a>

Se você vir a mensagem de erro, o endereço proxy "smtp:<nome de caixa de correio compartilhado " já está sendo usado pelos endereços proxy ou **\> LegacyExchangeDN de " \<name> ". Escolha outro endereço proxy**, isso significa que você está tentando dar à caixa de correio compartilhada um nome que já esteja em uso. Por exemplo, digamos que você deseja nomear as caixas de correio compartilhadas como info@dominio1 e info@dominio2. Há duas maneiras de fazer isso:

  - Use o Windows PowerShell. Consulte esta postagem de blog para obter instruções: [Criar caixas de correio compartilhadas com o mesmo alias em domínios diferentes](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)
    
  - Nomeia a segunda caixa de correio compartilhada algo diferente do início para dar a volta ao erro. Em seguida, no centro de administração, renomeie a caixa de correio compartilhada para o que você deseja que ela seja.

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a>Erro sobre não ter permissões de envio ao usar uma caixa de correio compartilhada

Se você criou uma caixa de correio compartilhada e, em seguida, tentar enviar uma mensagem dela, você pode obter isso:

**Esta mensagem não pôde ser enviada. Você não tem permissão para enviar a mensagem em nome do usuário especificado.**

Essa mensagem aparece quando Microsoft 365 está enfrentando um problema de latência de replicação. Ele deve desaparecer em uma hora ou mais, quando as informações sobre sua nova caixa de correio compartilhada (ou usuário adicionado) são replicadas em todos os nossos data centers. Aguarde uma hora e tente novamente enviar uma mensagem.

## <a name="related-content"></a>Conteúdo relacionado

[Sobre as caixas de correio compartilhadas](about-shared-mailboxes.md) (artigo)\
[Criar uma caixa de correio compartilhada](create-a-shared-mailbox.md) (artigo)\
[Configurar uma caixa de correio compartilhada](configure-a-shared-mailbox.md) (artigo)\
[Converter uma caixa de correio do usuário em uma caixa de correio compartilhada](convert-user-mailbox-to-shared-mailbox.md) (artigo)\
[Remover uma licença de uma caixa de correio compartilhada](remove-license-from-shared-mailbox.md) (artigo)


    

