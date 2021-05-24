---
title: Alternar para o EOP de outro serviço de proteção
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 81b75194-3b04-48da-8b81-951afbabedde
ms.custom:
- seo-marvel-apr2020
description: Neste artigo, você aprenderá a mudar para Proteção do Exchange Online (EOP) de um dispositivo de higienização de email local ou serviço de proteção baseado em nuvem.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dfbbc44ebfed6cafb97e36b18a4fc34c91840d9b
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624008"
---
# <a name="switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco-ironport"></a>Mudar para EOP do Google Postini, do Firewall de Vírus ou Spam Barracuda, ou do Cisco IronPort

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

 O objetivo deste tópico é ajudar você a entender o processo de optar pelo Exchange Online Protection (EOP) a partir de um serviço de proteção na nuvem ou ferramenta de higienização de email local e então oferecer recursos de ajuda para começar. Existem muitas soluções de filtragem de spam, mas o processo de alterar para EOP é similar na maioria dos casos.

Se você for novo no EOP e quiser ler uma visão geral de seus recursos antes de decidir alternar, comece com o tópico Proteção do Exchange Online [visão](exchange-online-protection-overview.md) geral.

Antes de mudar para EOP, é importante que você decida se deseja hospedar as suas caixas de correio protegias pelo EOP na nuvem, com o Exchange Online, localmente ou em um cenário híbrido. (Hybrid significa que você tem algumas caixas de correio hospedadas no local e outra parte hospedado com o Exchange Online.) Cada um desses cenários de hospedagem: nuvem, no local, e híbrido, é possível, mas as etapas de configuração podem variar. Aqui estão algumas considerações para ajudar você a escolher a implantação apropriada:

- Proteção do **EOP** com caixas de correio locais : este cenário é apropriado se você tiver uma infraestrutura de hospedagem de email existente que deseja usar ou se tiver requisitos comerciais para manter caixas de correio no local e quiser usar o EOP como sua proteção de email baseada na nuvem. [Switch to EOP standalone](#switch-to-eop-standalone) describes this scenario in more detail.

- **Proteção do EOP com Exchange Online** caixas de correio : este cenário é apropriado se você quiser proteção EOP e todas as suas caixas de correio hospedadas na nuvem. It can help you reduce complexity, because you don't have to maintain on-premises messaging servers. [Switch to Exchange Online](#switch-to-exchange-online) describes this scenario.

- **Proteção do EOP com** caixas de correio híbridas : Talvez você queira caixas de correio de nuvem, mas você precisa manter caixas de correio para alguns usuários locais. Choose this scenario if you want some mailboxes hosted on-premises and another portion hosted with Exchange Online. [Switch to a hybrid solution](#switch-to-a-hybrid-solution) describes this scenario.

## <a name="switch-to-eop-standalone"></a>Mudar para EOP standalone

Se você atualmente hospeda as suas caixas de correio localmente e use uma ferramenta de proteção local ou um serviço de proteção de mensagem na nuvem, você pode mudar para EOP para tirar vantagem dos seus recursos de proteção e disponibilidade. Para instalar o EOP em um cenário autônomo, o que significa que você hospeda as suas caixas de correio localmente e usa o EOP para fornecer proteção de email, você pode seguir as etapas destacadas em [Configurar seu serviço EOP](/exchange/standalone-eop/set-up-your-eop-service). O tópico destaca as etapas para instalar a proteção EOP, incluindo se inscrever, adicionar o seu domínio e configurar o fluxo de email com conectores.

## <a name="switch-to-exchange-online"></a>Mude para o Exchange Online

Talvez você tenha caixas de correio locais protegida Exchange Online s por um dispositivo local e queira pular para as caixas de correio hospedadas na nuvem e a proteção do EOP para tirar proveito de Microsoft 365 de mensagens na nuvem e recursos de proteção. Para começar, você pode se inscrever no Microsoft 365 e adicionar seu domínio. Esse cenário não exige que você configurar conectores, porque não há nenhum roteamento para caixas de correio locais. Comece em [Obter os recursos avançados mais recentes com Microsoft 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans) para se inscrever e se familiarizar com seus recursos.

Durante o Microsoft 365 de instalação, você criará seus usuários de caixa de correio baseados em nuvem.

## <a name="switch-to-a-hybrid-solution"></a>Mudar para uma solução híbrida

Você pode querer mover apenas uma porção das suas caixas de correio para a nuvem por causa de considerações regulatórias ou de requisitos de negócio. Quando você implanta um cenário híbrido, você pode mover as caixas de correio para a nuvem conforme determinação dos requisitos do seu negócio. Migrar para um cenário híbrido com proteção EOP é mais complicado do que mover para um cenário completamente na nuvem, mas a Microsoft fornece suporte total e amplos recursos para facilitar a mudança para um cenário híbrido.

O melhor local para iniciar, se você estiver considerando uma implantação híbrida, é Exchange Server [implantações híbridas.](/exchange/exchange-hybrid) Além disso, existem algumas maneiras diferentes de você rotear o seu email em um cenário híbrido que é importante que você entenda. [O Roteamento de Transporte Exchange implantações](/exchange/transport-routing) híbridas explica cada tipo, para que você possa escolher o melhor cenário de roteamento, com base nos requisitos de negócios.

## <a name="migration-planning"></a>Planejamento de migração

Quando você decide mudar para EOP, certifique-se de que você está considerando especialmente as seguintes áreas:

- **Regras de Filtragem** Personalizadas : Se você tiver regras de política de negócios ou filtragem personalizadas para capturar spam específico, recomendamos que você experimente o EOP com as configurações padrão por um período de tempo antes de migrar suas regras. EOP offers enterprise-level spam protection with the default settings, it may turn out that you don't need to migrate some of your rules to EOP. Of course, if you have rules in place that enforce specific custom business policies, you can create those. Para obter mais informações, consulte Regras de fluxo de email [(regras de transporte) em Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).

- **Listas de** IP e listas de bloqueio de IP : Se você tiver listas de bloqueio e listas de bloqueio por usuário, permita algum tempo para copiar as listas para o EOP como parte do processo de instalação. Para obter mais informações sobre a Lista de IDs e a Lista de Bloqueios de IP, consulte [Configure the connection filter policy](configure-the-connection-filter-policy.md).

- **Comunicação Segura**: se você tiver um parceiro que exija mensagens criptografadas, recomendamos que você desarmá-lo no centro de administração Exchange. Para configurar esse cenário, consulte [Set up connectors for secure mail flow with a partner organization](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner).

> [!TIP]
> Quando você mudar de uma ferramenta local para EOP, é possível deixar a sua ferramenta ou um servidor preparado para realizar as verificações de regra de negócio. Por exemplo, se o seu dispositivo executar filtragem personalizada em emails de saída e você quiser que ele continue fazendo isso, você pode configurar o EOP para enviar emails diretamente para o dispositivo para filtragem adicional, antes de ser roteado para a Internet.
