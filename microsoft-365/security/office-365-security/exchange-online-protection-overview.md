---
title: Visão geral do Exchange Online Protection
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
description: O Microsoft Proteção do Exchange Online (EOP) é um serviço de filtragem de e-mails baseado na nuvem que ajuda a proteger sua organização contra spam e malware, e inclui recursos para defender sua organização das violações da política de mensagens.
ms.openlocfilehash: b00de649bf0517d3c5cda99f1c20579ad1dfeec5
ms.sourcegitcommit: 333ecfb8bfeb34f9f08d82d295b40d37de6ba8b9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/29/2019
ms.locfileid: "37772265"
---
# <a name="exchange-online-protection-overview"></a>Visão geral do Exchange Online Protection

O Microsoft Proteção do Exchange Online (EOP) é um serviço de filtragem de e-mails baseado na nuvem que ajuda a proteger sua organização contra spam e malware, e inclui recursos para defender sua organização das violações da política de mensagens. O EOP pode simplificar o gerenciamento de seu ambiente de mensagem e reduzir muitos dos problemas que surgem na manutenção do hardware e do software locais.

A lista a seguir descreve como você pode usar o EOP para proteção de mensagens:

- **Em um cenário autônomo: o**EOP fornece proteção de email baseada em nuvem para sua organização local do Exchange ou para qualquer outra solução de email SMTP local.

- **Como parte do Exchange Online**: EOP é a proteção interna para caixas de correio hospedadas na nuvem no Exchange Online e no Office 365. Confira [proteção contra ameaças](protect-against-threats.md) para ajudar a configurar esses recursos do Exchange Online.

- **Em uma implantação híbrida: o**EOP pode ser configurado para proteger seu ambiente de mensagens e controlar o roteamento de email quando você tem uma combinação de caixas de correio locais e em nuvem.

> [!NOTE]
> Estes artigos da proteção do Exchange Online se aplicam a ambientes híbridos e locais.

## <a name="how-eop-works"></a>Como o EOP funciona

Para entender como o EOP funciona, ele o ajuda a ver como processa o email de entrada:

![Diagrama de processo de email.](../media/GitHubBugs/emailprocessingineop1.png)

Uma mensagem de entrada passa inicialmente pela filtragem de conexão, que verifica a reputação do remetente e inspeciona a mensagem em busca de malware. Grande parte do spam é interceptada nesse ponto e excluída pelo EOP. As mensagens continuam por meio da filtragem de política, onde as mensagens são avaliadas em relação às regras de fluxo de emails personalizadas (também conhecidas como regras de transporte) que você cria ou impõe de um modelo. Por exemplo, você pode ter uma regra que envia uma notificação a um gerente quando o email chega de um remetente específico. (As verificações preventivas de perda de dados também acontecem nesse ponto, caso você tenha esse recurso; para saber mais sobre a disponibilidade do recurso, veja [Descrição do serviço de proteção do Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=320619).) Em seguida, as mensagens passam pela filtragem de conteúdo, na qual o conteúdo é verificado com relação à terminologia ou propriedades comuns ao spam. Uma mensagem determinada como spam pelo filtro de conteúdo pode ser enviada para a pasta de lixo eletrônico de um usuário ou para a quarentena, entre outras opções (incluindo caixa de entrada ou pasta personalizada), com base nas suas configurações. Depois que uma mensagem passa todas essas camadas de proteção com êxito, ela é entregue ao destinatário.

### <a name="eop-datacenters"></a>Datacenters EOP

O EOP é executado em uma rede mundial de data center projetados para fornecer a melhor disponibilidade. Por exemplo, se um data center ficar indisponível, mensagens de email são automaticamente roteadas para um outro data center sem qualquer interrupção no serviço. Os servidores em cada data center aceitam mensagens em seu nome, fornecendo uma camada de separação entre sua organização e a Internet, reduzindo assim a carga em seus servidores. Por meio dessa rede altamente disponível, a Microsoft pode assegurar que esse email chegue a sua organização pontualmente.

EOP realiza balanceamento de carga entre data centers, mas apenas dentro de uma região. Se você for aprovisionado em uma região, todas as suas mensagens serão processadas usando o roteamento de email para essa região. A lista a seguir mostra como o roteamento de email regional funciona para os data centers EOP:

- Na Europa, Oriente Médio e África (EMEA), todas as caixas de correio do Exchange Online são localizadas nos data centers da EMEA e todas as mensagens são roteadas através de data centers da EMEA para filtragem do EOP.

- No Pacífico Asiático (Ásia), todas as caixas de correio do Exchange Online estão localizadas em datacenters da Ásia e as mensagens são roteadas atualmente através de datacenters da Ásia para filtragem do EOP.

- Nas Américas, todas as caixas de correio do Exchange Online estão localizadas em datacenters dos EUA, com a exceção da América do Sul onde os datacenters no Brasil e no Chile são usados e no Canadá em que os datacenters do Canadá são usados. Todas as mensagens de email, incluindo mensagens para clientes na América do Sul e Canadá, são roteadas através de datacenters locais para filtragem do EOP; o email em quarentena é armazenado no datacenter onde o locatário está localizado.

- Para a Nuvem de Comunidade Governamental (GCC), todas as caixas de correio do Exchange Online localizadas em data centers dos EUA e todas as mensagens são roteadas através de data centers dos EUA para filtragem do EOP.

## <a name="eop-plans-and-features"></a>Planos e recursos do EOP

Os planos de assinatura disponíveis do EOP são:

- **EOP autônomo**: você se inscreve no EOP para proteger sua organização de email local.

- **Recursos do EOP no Exchange Online**: qualquer assinatura que inclua o Exchange Online (autônomo ou como parte do Office 365) usa o EOP para proteger suas caixas de correio do Exchange Online.

- **Exchange Enterprise CAL com serviços**: se você tiver uma organização do Exchange no local onde comprou o Exchange Enterprise CAL adicional com licenças de serviços, o EOP faz parte dos serviços incluídos.

Para mais informações sobre as exigências, limites importantes e disponibilidade de recursos em todos os planos de assinatura do EOP, consulte a [Descrição do serviço de proteção do Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=320619).

## <a name="setting-up-eop"></a>Configuração do EOP

A configuração do EOP pode ser simples, especialmente no caso de uma pequena organização com um punhado de regras de conformidade. No entanto, se você tiver uma organização de grande porte com vários domínios, regras de conformidade personalizadas ou fluxo de email híbrido, a configuração pode precisar de mais planejamento e tempo.

Se você já comprou o EOP, consulte [Configurar seu serviço EOP](set-up-your-eop-service.md) para garantir a conclusão de todas as etapas necessárias de configuração do EOP, a fim de proteger seu ambiente de mensagens.

## <a name="for-more-information"></a>Para obter mais informações

[Recursos EOP](eop-features.md)

[Perguntas frequentes gerais sobre o EOP](eop-general-faq.md)

[Perguntas frequentes sobre mensagens enfileiradas, adiadas e retornadas do EOP](eop-queued-deferred-and-bounced-messages-faq.md)

[Perguntas frequentes sobre administração delegada](delegated-administration-faq.md)

[Mover domínios e configurações de uma organização do EOP para outra organização do EOP](move-domains-and-settings-from-one-eop-organization-to-another-eop-organization.md)
