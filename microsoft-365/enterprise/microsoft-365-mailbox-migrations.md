---
title: Migrações de caixa de correio do Microsoft 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Este artigo contém um breve resumo sobre as migrações de caixa de correio do Microsoft 365 e uma lista dos cmdlets usados para migrações.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 63080643e4994d6b16e77298907725a827997cef
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546793"
---
# <a name="microsoft-365-mailbox-migrations"></a>Migrações de caixa de correio do Microsoft 365

Com uma implantação híbrida baseada no Exchange, os clientes podem optar por mover caixas de correio locais do Exchange para uma organização do [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online) ou mover caixas de correio do Exchange Online para uma organização [local do Exchange](https://docs.microsoft.com/Exchange/exchange-server) . Os lotes de migração são usados ao mover caixas de correio entre as organizações locais e do Exchange Online.

Os clientes podem rever as estatísticas e outras informações sobre as migrações de caixa de correio com os seguintes cmdlets:

- [Get-MoveRequestStatistics](https://docs.microsoft.com/powershell/module/exchange/get-moverequeststatistics): fornece estatísticas padrão para uma caixa de correio de usuário, que inclui o status, tamanho da caixa de correio, tamanho da caixa de correio de arquivo morto e porcentagem concluída.
- [Get-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox
): fornece uma lista resumida de objetos e atributos de caixa de correio na organização.
- [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient): fornece uma lista de objetos habilitados para email existentes, como caixas de correio, usuários de email, contatos e grupos de distribuição.
- [Get-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/get-moverequest): fornece um status detalhado de uma migração de caixa de correio em andamento.
- [Get-MigrationUser](https://docs.microsoft.com/powershell/module/exchange/get-migrationuser): fornece informações sobre os usuários de movimentação e migração de caixa de correio.
- [Get-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/get-migrationbatch): fornece informações sobre o status do lote de migração atual.
- [Get-MigrationUserStatistics](https://docs.microsoft.com/powershell/module/exchange/get-migrationuserstatistics): fornece informações detalhadas sobre o status de migração para um usuário específico.
- [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics): fornece informações sobre caixas de correio, como tamanho, o número de mensagens e a hora do último acesso.

Para obter mais informações sobre cmdlets, consulte os [cmdlets de movimentação e migração no Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell).
