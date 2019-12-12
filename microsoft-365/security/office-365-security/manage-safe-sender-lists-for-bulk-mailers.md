---
title: Gerenciar listas seguras de remetentes para mensageiros em massa
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d48db4a3-9fbe-45e2-bbaa-1017ffdf96f8
ms.collection:
- M365-security-compliance
description: 'Se quiser usar listas de remetentes seguros, você deve saber que o Exchange Online Protection (EOP) e o processamento do Outlook lidam de forma diferente. O serviço respeita os remetentes e domínios seguros inspecionando o endereço RFC 5321. MailFrom e o endereço RFC 5322. from, enquanto o Outlook adiciona o endereço RFC 5322. from à lista de remetentes seguros de um usuário. (Observação: o serviço inspeciona o endereço 5321. MailFrom e o endereço 5322. from para os remetentes e domínios bloqueados.)'
ms.openlocfilehash: 2dcfd73cc987290bbc8ca8111580a374216a843e
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2019
ms.locfileid: "39970297"
---
# <a name="manage-safe-sender-lists-for-bulk-mailers"></a>Gerenciar listas seguras de remetentes para mensageiros em massa

Se quiser usar listas de remetentes seguros, você deve saber que o Exchange Online Protection (EOP) e o processamento do Outlook lidam de forma diferente. O serviço do Office 365 respeita os remetentes e domínios seguros inspecionando `RFC 5321.MailFrom` o endereço e `RFC 5322.From` o endereço, enquanto o Outlook `RFC 5322.From` adiciona o endereço à lista de remetentes seguros de um usuário. (Observação: o serviço inspeciona o endereço e `5321.MailFrom` `5322.From` o endereço de remetentes e domínios bloqueados.)

O `SMTP MAIL FROM` endereço, caso contrário, conhecido `RFC 5321.MailFrom address`como o, é o endereço de email usado para executar verificações de SPF e, se o email não puder ser entregue, o caminho para o qual a mensagem devolvida será entregue. Esse endereço de email é colocado no `Return-Path` nos cabeçalhos da mensagem por padrão, embora seja possível que o remetente designe um endereço diferente. `Return-Path`

O `From:` endereço nos cabeçalhos da mensagem, caso contrário, conhecido `RFC 5322.From` como endereço, é o endereço de email exibido no cliente de email, como o Outlook.

Na maioria das vezes, os `5321.MailFrom` endereços `5322.From` e são os mesmos. Isso é típico para comunicação pessoa a pessoa. No entanto, quando o email é enviado em nome de outra pessoa, os endereços são frequentemente diferentes. Isso geralmente acontece com mais frequência para mensagens de email em massa.

Por exemplo, suponha que as companhias aéreas Yonder azuis contratam a viagem da Margie para enviar seu anúncio de email. Você recebe uma mensagem em sua caixa de entrada do remetente blueyonder@news.blueyonderairlines.com. Neste exemplo:

- O `5321.MailFrom` endereço é blueyonder.Airlines@margiestravel.com.

- O `5322.From` endereço é blueyonder@news.blueyonderairlines.com, que é o que você verá no Outlook.

Para impedir que esta mensagem seja filtrada, você pode:

- **Como um usuário**: Adicione o `RFC 5322.From` endereço como um remetente seguro no Outlook.

- **Como um administrador**: configurar uma [regra de fluxo de emails](anti-spam-protection.md#beyond-the-basics-more-ways-to-prevent-spam-in-office-365) (também conhecida como regra de transporte).
