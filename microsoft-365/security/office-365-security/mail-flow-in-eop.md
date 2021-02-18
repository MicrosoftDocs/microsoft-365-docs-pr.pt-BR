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
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: O administrador pode saber mais sobre as opções para configurar o fluxo de emails e o roteamento no Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c988f58a04abf2322e993ae1b75106a338674acb
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289646"
---
# <a name="mail-flow-in-eop"></a>Fluxo de emails no EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Em organizações do Microsoft 365 com caixas de correio do Exchange Online ou organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, todas as mensagens enviadas para sua organização passam pelo EOP antes que seus funcionários as vejam. Você tem opções sobre como encaminhar mensagens que passam pelo EOP para processamento antes que elas sejam roteadas para suas caixas de entrada de trabalho.

## <a name="working-with-messages-and-message-access-options"></a>Trabalhando com mensagens e opções de acesso a mensagens

O EOP oferece flexibilidade na forma como suas mensagens são roteadas. Os tópicos a seguir explicam as etapas no processo de fluxo de email.

[Usar Bloqueio de Borda Baseado em Diretório para rejeitar mensagens enviadas a destinatários inválidos](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Descreve o recurso Bloqueio de Borda Baseado em Diretório que permite rejeitar mensagens de destinatários inválidos no perímetro da rede de serviço.

[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) descreve como gerenciar domínios que são associados ao seu serviço EOP.

Se você adicionar subdomínios à sua organização, o serviço do EOP poderá ajudá-lo a gerenciá-los também. Saiba mais sobre sub-vírgulas em [Habilitar fluxo de emails para sub-vírgulas no Exchange Online.](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)

[Configurar o fluxo de emails usando conectores](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduz conectores e mostra como você pode usá-los para personalizar o roteamento de email. Os cenários incluem garantir uma comunicação segura com uma organização parceira e configurar um host inteligente.

[A Filtragem Aprimorada](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) para Conectores descreve como configurar conectores se seu email for roteado para um serviço ou dispositivo antes do EOP.

Em organizações autônomas do EOP, você precisa executar algumas etapas de configuração para garantir que o lixo eletrônico seja roteado corretamente para a pasta de lixo eletrônico de cada usuário. Eles são detalhados em Configurar o EOP autônomo para entregar spam à pasta Lixo Eletrônico [em ambientes híbridos.](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md) Se você não quiser mover mensagens para a pasta de lixo eletrônico de cada usuário, poderá escolher outra ação editando suas políticas anti-spam (também conhecidas como políticas de filtro de conteúdo). Para saber mais, confira [Configurar políticas anti-spam](configure-your-spam-filter-policies.md).

## <a name="verify-mail-flow"></a>Verificar fluxo de mensagens

Para verificar se a sua instalação do EOP, incluindo a configuração de conectores, está funcionando corretamente, consulte a seção "Como saber se esta tarefa funcionou?" em [Configurar seu serviço EOP](set-up-your-eop-service.md).

Testar o fluxo de emails validando seus conectores do [Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) fornece instruções para testar se o fluxo de emails está definido corretamente.
