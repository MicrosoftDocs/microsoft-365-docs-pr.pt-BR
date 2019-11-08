---
title: Serviços para não clientes enviando emails para o Office 365
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 5/2/2016
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 19fd3e0f-8dbf-4049-a810-2c8ee6cefd48
ms.collection:
- M365-security-compliance
description: Para ajudar a manter a confiança do usuário no uso de email, a Microsoft colocou várias políticas e tecnologias para ajudar a proteger os usuários.
ms.openlocfilehash: cabb583aebc1baff1eb9f8286fceb2864b26deea
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2019
ms.locfileid: "38031766"
---
# <a name="services-for-non-customers-sending-mail-to-office-365"></a>Serviços para não clientes enviando emails para o Office 365

O abuso por email, lixo eletrônico e emails fraudulentos (phishing) continuam a sobrecarregar todo o ecossistema de email. Para ajudar a manter a confiança do usuário no uso de email, a Microsoft colocou várias políticas e tecnologias para ajudar a proteger os usuários. No entanto, a Microsoft reconhece que os emails legítimos não devem ser afetados negativamente. Portanto, estabelecemos um pacote de serviços para ajudar os remetentes a aprimorar a capacidade de enviar emails para os usuários do Office 365 ao gerenciar proativamente sua reputação de envio.

Esta visão geral fornece informações sobre os benefícios que fornecemos à sua organização, mesmo que você não seja um cliente do Office 365.

## <a name="sender-solutions"></a>Soluções de remetente

|**Serviço**|**Benefícios**|
|:-----|:-----|
|Este conteúdo da ajuda online| Lhe  <br/>  Um ponto de partida para qualquer dúvida relacionada ao fornecimento de comunicações com usuários do EOP  <br/>  Inclui um guia online simples com nossas políticas e requisitos  <br/>  Uma visão geral dos filtros de lixo eletrônico e tecnologias de autenticação empregadas pela Microsoft|
|[Suporte da Microsoft](#microsoft-support)|Fornece suporte a auto-ajuda e escalonamento para problemas de entrega.|
|[Portal de deslista de IPS do Office 365 anti-spam](#office-365-anti-spam-ip-delist-portal)|Uma ferramenta para enviar a solicitação de deslistação de IP. Antes de enviar essa solicitação, é responsabilidade do remetente garantir que qualquer email proveniente do IP em questão não seja abusiva ou mal-intencionada.|
|[Relatórios de abuso e spam para lixo eletrônico originado do Exchange Online](#abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online)|Mantém spam e outras mensagens indesejadas enviadas do Exchange Online e truncando a Internet e seu sistema de email.|

## <a name="microsoft-support"></a>Suporte da Microsoft

A Microsoft oferece várias opções de suporte para pessoas com problemas de envio de email para caixas de entrada do Office 365. Recomendamos que você:

- Siga as instruções em qualquer notificação de falha na entrega que você receber.

- Confira os problemas mais comuns que não os clientes encontram na [solução de problemas de email enviados para o Office 365](troubleshooting-mail-sent-to-office-365.md).

- Use o [portal de deslistação do Office 365](https://sender.office.com) para enviar uma solicitação para que o seu IP seja removido da lista do remetente bloqueado.

- Leia os [fóruns da Comunidade da Microsoft](https://community.office365.com/f/).

- Entre em contato com o cliente do Office 365 em que você está tentando enviar um email usando outro método e peça a ele para entrar em contato com o suporte da Microsoft e abrir um tíquete de suporte em seu nome. Em alguns casos, por motivos legais, o suporte da Microsoft deve se comunicar diretamente com o remetente que possui o espaço IP que está sendo bloqueado. No entanto, os usuários que não são normalmente não podem abrir tíquetes de suporte.

  Para obter mais informações sobre o suporte técnico da Microsoft para o Office 365, consulte [support](https://technet.microsoft.com/library/office-365-support.aspx).

## <a name="office-365-anti-spam-ip-delist-portal"></a>Portal de deslista de IPS do Office 365 anti-spam

Este é um portal de autoatendimento que você pode usar para se remover da lista de remetentes bloqueados do Office 365. Use este portal se você estiver recebendo uma mensagem de erro ao tentar enviar um email para um destinatário cujo endereço de email está no Office 365 e não achar que deve ser. Para obter mais informações, confira [Usar o portal para remoção da lista para remover seu nome na lista de remetentes bloqueados do Office 365](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).

## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a>Relatórios de abuso e spam para lixo eletrônico originado do Exchange Online

Às vezes, o Office 365 é usado por terceiros para enviar lixo eletrônico, violando nossos termos de uso e políticas. Se você receber uma mensagem de lixo eletrônico do Office 365, é possível relatar essas mensagens para o [junk@office365.microsoft.com](mailto:junk@office365.microsoft.com). Anexe as mensagens incorretas, incluindo o cabeçalho completo da mensagem, no formato RFC 5322 ou ARF. Os usuários do Outlook na Web podem usar ferramentas internas para relatar lixo eletrônico. Para saber mais, confira [relatar spam e golpes de phishing no Outlook na Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md).
