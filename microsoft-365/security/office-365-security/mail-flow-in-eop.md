---
title: Fluxo de emails no EOP
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
description: Como um cliente do Proteção do Exchange Online (EOP), todas as mensagens enviadas para sua organização passam através de EOP antes que seus funcionários as vejam. Se você hospedar todas as suas caixas de correio na nuvem com o Exchange Online, ou se você hospedar suas caixas de correio no local (cenário autônomo), talvez para continuar aproveitando sua infraestrutura existente, você tem opções sobre como encaminhar mensagens que passarão pelo EOP para processamento antes que sejam encaminhadas para as caixas de entrada dos seus funcionários.
ms.openlocfilehash: e2575cc506234877b4fbc43092927d82662b947c
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2019
ms.locfileid: "37441098"
---
# <a name="mail-flow-in-eop"></a>Fluxo de emails no EOP

Como um cliente do Proteção do Exchange Online (EOP), todas as mensagens enviadas para sua organização passam através de EOP antes que seus funcionários as vejam. Se você hospedar todas as suas caixas de correio na nuvem com o Exchange Online, ou se você hospedar suas caixas de correio no local (cenário autônomo), talvez para continuar aproveitando sua infraestrutura existente, você tem opções sobre como encaminhar mensagens que passarão pelo EOP para processamento antes que sejam encaminhadas para as caixas de entrada dos seus funcionários.

Você pode querer configurar o encaminhamento de email padrão para que seu serviço de mensagens atenda a um requisito comercial. Por exemplo, você pode passar todos os seus emails de saída através de um dispositivo de filtragem de política.

## <a name="working-with-messages-and-message-access-options"></a>Trabalhando com mensagens e opções de acesso a mensagens

O EOP oferece muita flexibilidade no modo como suas mensagens são encaminhadas. Os tópicos a seguir explicam as etapas no processo de fluxo de email.

[Usar o bloqueio de borda baseado em diretório para rejeitar mensagens enviadas a destinatários inválidos](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Descreve o recurso de bloqueio de borda baseado em diretório, que permite rejeitar mensagens para destinatários inválidos no perímetro da rede de serviço.

[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) descreve como gerenciar domínios que são associados ao seu serviço EOP.

Se você adicionar subdomínios à sua organização, o serviço do EOP poderá ajudá-lo a gerenciá-los também. Saiba mais sobre subdomínios em [habilitar o fluxo de emails para subdomínios no Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).

[Configure mail flow using connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) apresenta conectores de EOP e mostra como você pode usá-los para personalizar o roteamento de email. Os cenários incluem garantir uma comunicação segura com uma organização parceira e configurar um host inteligente.

Para garantir que o lixo eletrônico seja roteado corretamente para a pasta de lixo eletrônico de cada usuário, é necessário realizar alguns passos de configuração. Eles são detalhados [para garantir que o spam seja roteado para a pasta lixo eletrônico de cada usuário](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). Se não quiser mover mensagens para a pasta de lixo eletrônico de cada usuário, você pode escolher outra ação editando suas políticas de filtro de conteúdo no centro de administração do Exchange. Para saber mais, confira [Configure your spam filter policies](configure-your-spam-filter-policies.md).

## <a name="verify-mail-flow"></a>Verificar fluxo de mensagens

Para verificar se a sua instalação do EOP, incluindo a configuração de conectores, está funcionando corretamente, consulte a seção "Como saber se esta tarefa funcionou?" em [Configurar seu serviço EOP](set-up-your-eop-service.md).

[Testar o fluxo de emails ao validar seus conectores do Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) fornece instruções para testar se seu fluxo de email está configurado corretamente.
