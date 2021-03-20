---
title: Serviços para não clientes que enviam emails para o Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 19fd3e0f-8dbf-4049-a810-2c8ee6cefd48
ms.collection:
- M365-security-compliance
description: Para ajudar a manter a confiança do usuário no uso de email, a Microsoft colocou em uso várias políticas e tecnologias para ajudar a proteger nossos usuários.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3213cae1b04b3f1a1b861e8f2cfc698576013546
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903792"
---
# <a name="services-for-non-customers-sending-mail-to-microsoft-365"></a>Serviços para não clientes que enviam emails para o Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


O abuso de email, lixo eletrônico e emails fraudulentos (phishing) continuam a sobrecarregar todo o ecossistema de email. Para ajudar a manter a confiança do usuário no uso de email, a Microsoft colocou várias políticas e tecnologias para ajudar a proteger nossos usuários. No entanto, a Microsoft entende que o email legítimo não deve ser afetado negativamente. Portanto, estabelecemos um pacote de serviços para ajudar os enviadores a melhorar a capacidade de entregar emails aos usuários do Microsoft 365 gerenciando proativamente sua reputação de envio.

Esta visão geral fornece informações sobre os benefícios que fornecemos à sua organização, mesmo que você não seja um cliente.

## <a name="sender-solutions"></a>Soluções de remetente

****

|Serviço|Benefícios|
|---|---|
|Este conteúdo de ajuda online|Fornece: <ul><li>Um ponto de partida para quaisquer perguntas relacionadas à entrega de comunicações aos usuários do EOP.</li><li>Inclui um guia online simples com nossas políticas e requisitos.</li><li>Uma visão geral dos filtros de lixo eletrônico e das tecnologias de autenticação empregadas pela Microsoft.</li><ul>|
|[Suporte da Microsoft](#microsoft-support)|Fornece suporte de auto-ajuda e escalonamento para problemas de entrega.|
|[Portal de Lista de IP Anti-Spam](#anti-spam-ip-delist-portal)|Uma ferramenta para enviar solicitação de lista de IP. Antes de enviar essa solicitação, é responsabilidade do remetente garantir que qualquer email que se origine do IP em questão não seja abusivo ou mal-intencionado.|
|[Relatórios de spam e abuso de lixo eletrônico provenientes do Exchange Online](#abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online)|Impede que o spam e outros emails indesejados seja enviados do Exchange Online e atrapalha a Internet e seu sistema de email.|
|

## <a name="microsoft-support"></a>Suporte da Microsoft

A Microsoft oferece várias opções de suporte para pessoas com problemas para enviar emails para destinatários do Microsoft 365. Recomendamos que você:

- Siga as instruções em qualquer relatório que não seja de entrega recebido.

- Confira os problemas mais comuns encontrados por não clientes em Solução de problemas [de emails enviados para o Office 365](troubleshooting-mail-sent-to-office-365.md).

- Use o portal de [lista do Microsoft 365](https://sender.office.com) para enviar uma solicitação para que seu IP seja removido da lista de remetentes bloqueados.

- Leia os fóruns [da comunidade microsoft](https://community.office365.com/f/).

- Entre em contato com o cliente que você está tentando enviar por email usando outro método e peça que contate o Suporte da Microsoft e abra um tíquete de suporte em seu nome. Em alguns casos, por motivos legais, o Suporte da Microsoft deve se comunicar diretamente com o remetente que possui o espaço IP que está sendo bloqueado. No entanto, não clientes normalmente não podem abrir tíquetes de suporte.

  Para obter mais informações sobre o suporte técnico da Microsoft para o Office 365, consulte [Support](/office365/servicedescriptions/office-365-platform-service-description/support).

## <a name="anti-spam-ip-delist-portal"></a>Portal de Lista de IP Anti-Spam

Este é um portal de autoatendir que você pode usar para remover a si mesmo da lista de envios bloqueados do Microsoft 365. Use este portal se você estiver recebendo uma mensagem de erro ao tentar enviar um email para um destinatário cujo endereço de email está no Microsoft 365 e você acha que não deve estar. Para obter mais informações, veja [Usar o portal de remoção para remover seu nome na lista de remetentes bloqueados](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).

## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a>Relatórios de spam e abuso de lixo eletrônico provenientes do Exchange Online

Às vezes, o Microsoft365 é usado por terceiros para enviar lixo eletrônico, violando nossos termos de uso e política. Se você receber qualquer lixo eletrônico do Office 365, poderá relatar essas mensagens à Microsoft. Para obter instruções, consulte [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).