---
title: Perguntas frequentes gerais sobre o EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
ms.assetid: 9dbff00a-474e-4452-aeb5-5be9a6b8c6d5
ms.custom:
- seo-marvel-apr2020
description: Obter respostas para as perguntas gerais mais comuns sobre o serviço de filtragem de email hospedado na nuvem do Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 04246b7c0a241c672328febd1584a56aa11becf2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054388"
---
# <a name="eop-general-faq"></a>Perguntas frequentes gerais sobre o EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
-  [Proteção autônoma do Exchange Online](exchange-online-protection-overview.md)

Aqui, respondemos às perguntas gerais mais comuns sobre o serviço de filtragem de email hospedado na nuvem do Exchange Online Protection (EOP). Para ver mais tópicos de perguntas frequentes, vá para os seguintes links:

- [Perguntas frequentes sobre mensagens enfileiradas, adiadas e retornadas do EOP](eop-queued-deferred-and-bounced-messages-faq.md)

- [Perguntas frequentes sobre administração delegada](delegated-administration-faq.md)

- [Perguntas frequentes sobre a proteção antispam](anti-spam-protection-faq.md)

- [Quarantine FAQ](quarantine-faq.md)

- [Perguntas frequentes sobre proteção antimalware](anti-malware-protection-faq-eop.md)

- [Perguntas Frequentes sobre Rastreamento de Mensagens](/exchange/monitoring/trace-an-email-message/message-trace-faq)

## <a name="what-is-eop"></a>O que é o EOP?

EOP é um serviço de filtragem de email hospedado na nuvem, criado para proteger os clientes contra spam e malware, além de implementar regras de política personalizadas. O EOP está incluído em qualquer assinatura do Microsoft 365 que contenha caixas de correio do Exchange Online. O EOP também está disponível como uma oferta autônoma para ajudar a proteger ambientes de email locais.

## <a name="how-do-i-sign-up-for-an-eop-trial-or-purchase-eop"></a>Como eu me inscrevo para uma avaliação do EOP ou para comprar o EOP?

Inscreva-se para uma avaliação do EOP ou para comprar o EOP pela Web na [home page do Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection). Observe que a funcionalidade de uma compra de avaliação é a mesma de uma assinatura paga, mas também inclui recursos adicionais fornecidos com o plano de assinatura [Exchange Enterprise CAL com serviços](https://products.office.com/exchange/microsoft-exchange-server-licensing-licensing-overview).

## <a name="how-is-eop-priced"></a>Como é definido o preço do EOP?

O EOP é licenciado por usuário. Para ver as informações mais recentes sobre preços, consulte a [Home page do Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection).

## <a name="how-long-does-it-take-to-put-eop-into-production"></a>Quanto tempo é necessário para colocar o EOP em produção?

Quando você altera seu registro do MX, de acordo com as etapas descritas em [Configurar seu serviço EOP](set-up-your-eop-service.md), e seu email flui pelo EOP, a filtragem começa imediatamente. O registro MX pode demorar até 24 a 48 horas para ser propagado via DNS. Você pode ajustar suas configurações de proteção a qualquer momento durante esse processo.

## <a name="do-i-have-to-use-all-features-of-microsoft-365-to-use-eop-what-if-i-just-want-eop-protection-and-thats-all"></a>Preciso usar todos os recursos do Microsoft 365 para usar o EOP? E se eu apenas quiser proteção EOP e isso é tudo?

Você pode usar o EOP para proteger suas caixas de correio locais sem usar outros recursos do Microsoft 365. Isso é conhecido como assinatura autônoma. Uma lista de recursos da EOP pode ser encontrada em [Serviço de Descrição da Proteção do Exchange Online](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

## <a name="why-do-i-need-a-microsoft-365-tenant-when-signing-up-for-email-filtering-through-eop"></a>Por que preciso de um locatário do Microsoft 365 ao se inscrever para a filtragem de email por meio do EOP?

O Microsoft 365 é o nome dado a uma coleção de produtos e serviços que podem ser acessados por meio de um locatário do Microsoft 365. Pense no locatário do Microsoft 365 como o ponto de partida para o qual você pode adicionar licenças para filtragem de email.

## <a name="does-eop-have-a-communication-portal-where-i-can-find-out-about-known-issues-and-expected-resolutions-what-about-new-features"></a>O EOP tem um portal de comunicação em que posso obter informações sobre problemas conhecidos e resoluções esperadas? E quanto a novos recursos?

O Centro de administração do Microsoft 365 terá algumas dessas informações. Se você for afetado por um Evento de Nível de Serviço, deverá ver um alerta de comunicação (normalmente acompanhado por um ícone de sino) após entrar no centro de administração do Microsoft 365. Recomendamos que leia e realize as ações apropriadas em todos os itens.

Em relação aos novos recursos do EOP, o roteiro do [Microsoft 365 for business](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) é um bom recurso para descobrir informações sobre os novos recursos futuros. Também postaremos artigos de blog sobre novos recursos no site [blogs do Microsoft 365.](https://www.microsoft.com/microsoft-365/blog/)

## <a name="does-the-service-work-with-legacy-exchange-versions-such-as-exchange-server-2010-and-non-exchange-environments"></a>O serviço funciona com versões herdadas do Exchange (como o Exchange Server 2010) e ambientes que não sejam Exchange?

Sim, o serviço é independente do servidor e pode ser usado com qualquer agente de transferência de email SMTP.

## <a name="what-size-organization-can-use-the-service"></a>O serviço pode ser usado por organizações de que tamanho?

Qualquer tamanho. A rede do EOP tem capacidade suficiente para acomodar seu crescimento, mesmo que ele seja muito rápido.

## <a name="what-permissions-do-i-need-to-set-up-eop"></a>Quais são as permissões necessárias para configurar o EOP?

Para configurar o EOP, você deve ser um administrador global ou um Administrador da Empresa do Exchange (o grupo de função Gerenciamento da Organização).

## <a name="how-do-i-know-my-data-and-private-information-are-safe"></a>Como eu sei se meus dados e informações particulares estão seguros?

Para saber mais sobre as medidas que adotamos para garantir a segurança dos seus dados e informações particulares, inclusive informações sobre Contratos de Nível de Serviço (SLAs), vá para a [Central de Confiabilidade do Office 365](https://www.microsoft.com/trust-center).

## <a name="are-there-any-limits-i-should-be-aware-of-such-as-message-size-limitations"></a>Há algum limite que eu deva conhecer; por exemplo, limitações de tamanho da mensagem?

Sim. Para obter mais informações sobre limites no EOP, consulte [Limites do Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits).

## <a name="does-eop-support-powershell"></a>O EOP dá suporte ao PowerShell?

Sim, a funcionalidade completa do EOP está disponível por meio do PowerShell: PowerShell do Exchange Online para organizações com caixas de correio do Exchange Online; EOP PowerShell autônomo para organizações EOP autônomas. Para obter mais informações, consulte [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell) e [Exchange Online Protection PowerShell](/powershell/exchange/exchange-online-protection-powershell).