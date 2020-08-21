---
title: Fluxo de emails no EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: O administrador pode aprender sobre as opções de configuração de fluxo de email e roteamento na proteção do Exchange Online (EOP).
ms.openlocfilehash: c58981afaadf2c4083b6a6db99c74cf9544715c3
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827720"
---
# <a name="mail-flow-in-eop"></a>Fluxo de e-mails no EOP

Nas organizações do Microsoft 365 com caixas de correio do Exchange Online, ou organizações autônomas do Exchange Online Protection (EOP), sem caixas de correio do Exchange Online, todas as mensagens enviadas para sua organização passam pelo EOP antes que seus funcionários os vejam. Você tem opções sobre como rotear mensagens que passam pelo EOP para processamento antes de serem encaminhadas para suas caixas de entrada de trabalho.

## <a name="working-with-messages-and-message-access-options"></a>Trabalhando com mensagens e opções de acesso a mensagens

O EOP oferece flexibilidade no modo como as mensagens são encaminhadas. Os tópicos a seguir explicam as etapas no processo de fluxo de email.

[Usar o bloqueio de borda baseado em diretório para rejeitar mensagens enviadas a destinatários inválidos](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Descreve o recurso de bloqueio de borda baseado em diretório, que permite rejeitar mensagens para destinatários inválidos no perímetro da rede de serviço.

[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) descreve como gerenciar domínios que são associados ao seu serviço EOP.

Se você adicionar subdomínios à sua organização, o serviço do EOP poderá ajudá-lo a gerenciá-los também. Saiba mais sobre subdomínios em [habilitar o fluxo de emails para subdomínios no Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).

[Configurar o fluxo de email usando conectores](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduz conectores e mostra como você pode usá-los para personalizar o roteamento de emails. Os cenários incluem garantir uma comunicação segura com uma organização parceira e configurar um host inteligente.

[Filtragem avançada para conectores](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) descreve como configurar conectores se o email for roteado para um serviço ou dispositivo antes de EOP.

Em organizações EOP autônomas, você precisa executar algumas etapas de configuração para garantir que o lixo eletrônico seja roteado corretamente para a pasta lixo eletrônico de cada usuário. Eles são detalhados em [Configurar o EOP autônomo para entregar o spam à pasta lixo eletrônico em ambientes híbridos](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). Se não quiser mover mensagens para a pasta de lixo eletrônico de cada usuário, você pode escolher outra ação editando suas políticas antispam (também conhecidas como políticas de filtro de conteúdo). Para saber mais, confira [Configurar políticas anti-spam](configure-your-spam-filter-policies.md).

## <a name="verify-mail-flow"></a>Verificar fluxo de mensagens

Para verificar se a sua instalação do EOP, incluindo a configuração de conectores, está funcionando corretamente, consulte a seção "Como saber se esta tarefa funcionou?" em [Configurar seu serviço EOP](set-up-your-eop-service.md).

[Testar o fluxo de emails Validando seus conectores do Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) fornece instruções para testar se seu fluxo de email está configurado corretamente.
