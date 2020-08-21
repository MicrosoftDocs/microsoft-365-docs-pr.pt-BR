---
title: Alternar para EOP de outro serviço de proteção
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 81b75194-3b04-48da-8b81-951afbabedde
ms.custom:
- seo-marvel-apr2020
description: Neste artigo, você aprenderá a alternar para o Exchange Online Protection (EOP) de um dispositivo de higiene de email local ou serviço de proteção baseado em nuvem.
ms.openlocfilehash: a6405411a130abf8369b312f553060caf0bf3855
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827792"
---
# <a name="switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco-ironport"></a>Mudando para EOP da Google Postini, Firewall de Vírus ou Spam Barracuda ou Cisco IronPort

 O objetivo deste tópico é ajudar você a entender o processo de optar pelo Exchange Online Protection (EOP) a partir de um serviço de proteção na nuvem ou ferramenta de higienização de email local e então oferecer recursos de ajuda para começar. Existem muitas soluções de filtragem de spam, mas o processo de alterar para EOP é similar na maioria dos casos.

Se você é novo no EOP e deseja ler uma visão geral de seus recursos antes de decidir alternar, comece com o tópico [visão geral da proteção do Exchange Online](exchange-online-protection-overview.md) .

Antes de mudar para EOP, é importante que você decida se deseja hospedar as suas caixas de correio protegias pelo EOP na nuvem, com o Exchange Online, localmente ou em um cenário híbrido. (Hybrid significa que você tem algumas caixas de correio hospedadas no local e outra parte hospedado com o Exchange Online.) Cada um desses cenários de hospedagem: nuvem, no local, e híbrido, é possível, mas as etapas de configuração podem variar. Aqui estão algumas considerações para ajudar você a escolher a implantação apropriada:

- **EOP proteção com caixas de correio locais**: esse cenário será apropriado se você tiver uma infraestrutura de Hospedagem de emails existente que você deseja usar ou se tiver requisitos de negócios para manter as caixas de correio locais e quiser usar o EOP como sua proteção de email baseada em nuvem. [Switch to EOP standalone](#switch-to-eop-standalone) describes this scenario in more detail.

- **Proteção do EOP com caixas de correio do Exchange Online**: esse cenário será apropriado se você quiser proteção do EOP e todas as suas caixas de correio hospedadas na nuvem. It can help you reduce complexity, because you don't have to maintain on-premises messaging servers. [Switch to Exchange Online](#switch-to-exchange-online) describes this scenario.

- **EOP proteção com caixas de correio híbridas**: Talvez você queira manter caixas de correio em nuvem, mas precisa manter caixas de correio para alguns usuários no local. Choose this scenario if you want some mailboxes hosted on-premises and another portion hosted with Exchange Online. [Switch to a hybrid solution](#switch-to-a-hybrid-solution) describes this scenario.

## <a name="switch-to-eop-standalone"></a>Mudar para EOP standalone

Se você atualmente hospeda as suas caixas de correio localmente e use uma ferramenta de proteção local ou um serviço de proteção de mensagem na nuvem, você pode mudar para EOP para tirar vantagem dos seus recursos de proteção e disponibilidade. Para instalar o EOP em um cenário autônomo, o que significa que você hospeda as suas caixas de correio localmente e usa o EOP para fornecer proteção de email, você pode seguir as etapas destacadas em [Configurar seu serviço EOP](set-up-your-eop-service.md). O tópico destaca as etapas para instalar a proteção EOP, incluindo se inscrever, adicionar o seu domínio e configurar o fluxo de email com conectores.

## <a name="switch-to-exchange-online"></a>Mude para o Exchange Online

Talvez você tenha caixas de correio locais protegidas por um dispositivo local e queira saltar para as caixas de correio hospedadas na nuvem do Exchange Online e a proteção do EOP para aproveitar os recursos de proteção e mensagens na nuvem da Microsoft 365. Para começar, você pode se inscrever no Microsoft 365 e adicionar seu domínio. Este cenário não exige que você instale conectores, porque nao há nenhum roteamento para caixas de correio locais. Comece a [obter os recursos avançados mais recentes com o Microsoft 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans) para se inscrever e se familiarizar com seus recursos.

Durante o processo de instalação do Microsoft 365, você irá criar seus usuários de caixa de correio baseados na nuvem.

## <a name="switch-to-a-hybrid-solution"></a>Mudar para uma solução híbrida

Você pode querer mover apenas uma porção das suas caixas de correio para a nuvem por causa de considerações regulatórias ou de requisitos de negócio. Quando você implanta um cenário híbrido, você pode mover as caixas de correio para a nuvem conforme determinação dos requisitos do seu negócio. Migrar para um cenário híbrido com proteção EOP é mais complicado do que mover para um cenário completamente na nuvem, mas a Microsoft fornece suporte total e amplos recursos para facilitar a mudança para um cenário híbrido.

O melhor lugar para começar, se você estiver considerando uma implantação híbrida, é as [implantações híbridas do Exchange Server](https://docs.microsoft.com/exchange/exchange-hybrid). Além disso, existem algumas maneiras diferentes de você rotear o seu email em um cenário híbrido que é importante que você entenda. O [Roteamento de transporte em implantações híbridas do Exchange](https://docs.microsoft.com/exchange/transport-routing) explica cada tipo, portanto, você pode escolher o melhor cenário de roteamento, com base em seus requisitos de negócios.

## <a name="migration-planning"></a>Planejamento de migração

Quando você decide mudar para EOP, certifique-se de que você está considerando especialmente as seguintes áreas:

- **Regras de filtragem personalizadas**: se você tiver regras de filtro ou de política de negócios personalizadas para detectar spam específico, recomendamos que você tente EOP com as configurações padrão para um período de tempo antes de migrar suas regras. EOP offers enterprise-level spam protection with the default settings, it may turn out that you don't need to migrate some of your rules to EOP. Of course, if you have rules in place that enforce specific custom business policies, you can create those. [Regras de fluxo de email (regras de transporte) no Exchange Online Protection](mail-flow-rules-transport-rules-0.md) fornece instruções detalhadas para a criação de regras de fluxo de email no EOP.

- Listas de **IPs permitidos e listas de bloqueios de IP**: se você tiver listas de permissões e listas de bloqueio por usuário, espere algum tempo para copiar as listas para o EOP como parte do processo de instalação. Para obter mais informações sobre a lista de permissões de IP e a lista de IPs bloqueados, consulte [Configurar a política de filtro de conexão](configure-the-connection-filter-policy.md).

- **Comunicação segura**: se você tiver um parceiro que exija mensagens criptografadas, recomendamos que você configure isso no centro de administração do Exchange. Para configurar este cenário, confira [set up Connectors for Secure Mail Flow with a Partner Organization](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner).

> [!TIP]
> Quando você mudar de uma ferramenta local para EOP, é possível deixar a sua ferramenta ou um servidor preparado para realizar as verificações de regra de negócio. Por exemplo, se o seu dispositivo executar filtragem personalizada no email de saída e você quiser continuar fazendo isso, você pode configurar o EOP para enviar emails diretamente para o dispositivo para filtragem adicional, antes que ele seja roteado para a Internet.
