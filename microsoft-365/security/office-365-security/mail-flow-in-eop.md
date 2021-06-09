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
description: O administrador pode aprender sobre as opções para configurar o fluxo de email e o roteamento no Proteção do Exchange Online (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9636025796aee1ba2027edff38a16f131974134f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842489"
---
# <a name="mail-flow-in-eop"></a>Fluxo de emails no EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Em organizações Microsoft 365 com caixas de correio Exchange Online ou organizações autônomas Proteção do Exchange Online (EOP) sem Exchange Online caixas de correio, todas as mensagens enviadas para sua organização passam pelo EOP antes que seus funcionários as vejam. Você tem opções sobre como rotear mensagens que passam pelo EOP para processamento antes que elas sejam roteadas para suas caixas de entrada de trabalho.

## <a name="working-with-messages-and-message-access-options"></a>Trabalhando com mensagens e opções de acesso a mensagens

O EOP oferece flexibilidade na forma como suas mensagens são roteadas. Os tópicos a seguir explicam as etapas no processo de fluxo de email.

[Usar o Bloqueio de Borda Com Base em Diretório para rejeitar mensagens enviadas a destinatários inválidos](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Descreve o recurso Bloqueio de Borda Baseado em Diretório que permite rejeitar mensagens para destinatários inválidos no perímetro da rede de serviço.

[Exibir ou editar domínios aceitos no EOP](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) descreve como gerenciar domínios associados ao seu serviço EOP.

Se você adicionar subdomínios à sua organização, o serviço do EOP poderá ajudá-lo a gerenciá-los também. Saiba mais sobre subdomas em [Habilitar fluxo de emails para subdomas em Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).

[Configurar o fluxo de emails usando conectores](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduz conectores e mostra como você pode usá-los para personalizar o roteamento de email. Os cenários incluem garantir uma comunicação segura com uma organização parceira e configurar um host inteligente.

[A filtragem aprimorada](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) para conectores descreve como configurar conectores se seu email for roteado para um serviço ou dispositivo antes do EOP.

Em ambientes híbridos onde o EOP protege as caixas de correio locais do Exchange, você precisa configurar regras de fluxo de email (também conhecidas como regras de transporte) no Exchange local para traduzir o veredito de filtragem de spam do EOP para que a regra de lixo eletrônico possa mover a mensagem para o Lixo Pasta de email. Para obter detalhes, confira [Configurar o EOP para enviar spam para a pasta Lixo Eletrônico em ambientes híbridos](/exchange/standalone-eop/configure-eop-spam-protection-hybrid). Se você não quiser mover mensagens para a pasta Lixo Eletrônico de cada usuário, poderá escolher outra ação editando suas políticas anti-spam (também conhecidas como políticas de filtro de conteúdo). Para saber mais, confira [Configurar políticas anti-spam](configure-your-spam-filter-policies.md).

## <a name="verify-mail-flow"></a>Verificar fluxo de mensagens

Para verificar se a sua instalação do EOP, incluindo a configuração de conectores, está funcionando corretamente, consulte a seção "Como saber se esta tarefa funcionou?" em [Configurar seu serviço EOP](/exchange/standalone-eop/set-up-your-eop-service).

[Testar o fluxo de emails validando seus conectores Microsoft 365 fornece](/exchange/mail-flow-best-practices/test-mail-flow) instruções para testar se o fluxo de email está definido corretamente.
