---
title: Perguntas frequentes gerais sobre o EOP
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 1/2/2018
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9dbff00a-474e-4452-aeb5-5be9a6b8c6d5
description: 'Aqui, respondemos às dúvidas gerais mais comuns sobre o Proteção do Exchange Online (EOP), o serviço de filtragem de email hospedado na nuvem da Microsoft. Para ver mais tópicos de perguntas frequentes, vá para os seguintes links:'
ms.openlocfilehash: 899109a768399f53674b97fc8df2f71aa822316d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636247"
---
# <a name="eop-general-faq"></a>Perguntas frequentes gerais sobre o EOP

Aqui, respondemos às dúvidas gerais mais comuns sobre o Proteção do Exchange Online (EOP), o serviço de filtragem de email hospedado na nuvem da Microsoft. Para ver mais tópicos de perguntas frequentes, vá para os seguintes links:

- [Perguntas frequentes sobre mensagens enfileiradas, adiadas e retornadas do EOP](eop-queued-deferred-and-bounced-messages-faq.md)

- [Perguntas frequentes sobre administração delegada](delegated-administration-faq.md)

- [Perguntas frequentes sobre a proteção antispam](anti-spam-protection-faq.md)

- [Quarantine FAQ](quarantine-faq.md)

- [Perguntas frequentes sobre proteção antimalware](anti-malware-protection-faq-eop.md)

- [Perguntas Frequentes sobre Rastreamento de Mensagens](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq)

**P. O que é o EOP?**

R. EOP é um serviço de filtragem de email hospedado na nuvem, criado para proteger os clientes contra spam e malware, além de implementar regras de política personalizadas.

**P. Como eu me inscrevo para uma avaliação do EOP ou para comprar o EOP?**

R. Inscreva-se para uma avaliação do EOP ou para comprar o EOP pela Web na [home page do Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection). Observe que a funcionalidade de uma compra de avaliação é a mesma de uma assinatura paga, mas também inclui recursos adicionais fornecidos com o plano de assinatura [Exchange Enterprise CAL com serviços](https://products.office.com/exchange/microsoft-exchange-server-licensing-licensing-overview).

**R. Como é definido o preço do EOP?**

R. O EOP é licenciado por usuário. Para ver as informações mais recentes sobre preços, consulte a [Home page do Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection).

**P. Quanto tempo é necessário para colocar o EOP em produção?**

R. Quando você altera seu registro do MX, de acordo com as etapas descritas em [Configurar seu serviço EOP](set-up-your-eop-service.md), e seu email flui pelo EOP, a filtragem começa imediatamente. O registro MX pode demorar até 24 a 48 horas para ser propagado via DNS. Você pode ajustar suas configurações de proteção no centro de administração do Exchange (EAC) a qualquer momento durante esse processo.

**P. tenho que usar todos os recursos do Microsoft 365 para usar o EOP? E se eu quiser apenas a proteção do EOP?**

R. Você pode usar o EOP para proteger suas caixas de correio locais sem usar outros recursos do Microsoft 365. Isso é conhecido como assinatura autônoma. Uma lista de recursos da EOP pode ser encontrada em [Serviço de Descrição da Proteção do Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

**P. por que preciso de um locatário do Microsoft 365 ao se inscrever para filtragem de email por meio do EOP?**

R. O Microsoft 365 é o nome dado a uma coleção de produtos e serviços que podem ser acessados por meio de um locatário do Microsoft 365. Considere o Microsoft 365 locatário como o ponto de partida para o qual você pode adicionar licenças para filtragem de email.

**P. O EOP tem um portal de comunicação em que posso obter informações sobre problemas conhecidos e resoluções esperadas? E quanto a novos recursos?**

R. O centro de administração do Microsoft 365 terá algumas dessas informações. Se você for afetado por um evento de nível de serviço, deverá ver um alerta de comunicação (normalmente acompanhado por um ícone de sino) após entrar no centro de administração do Microsoft 365. Recomendamos que leia e realize as ações apropriadas em todos os itens.

Sobre os novos recursos do EOP, o [Microsoft 365 for Business Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) é um bom recurso para descobrir informações sobre os novos recursos do futuro. Também vamos postar artigos do blog sobre novos recursos no site do [Microsoft 365 Blogs](https://www.microsoft.com/microsoft-365/blog/) .

**P. O serviço funciona com versões herdadas do Exchange (como o Exchange Server 2010) e ambientes que não sejam Exchange?**

R. Sim, o serviço é independente do servidor e pode ser usado com qualquer agente de transferência de email SMTP.

**P. O serviço pode ser usado por organizações de que tamanho?**

R. Qualquer tamanho. A rede do EOP tem capacidade suficiente para acomodar seu crescimento, mesmo que ele seja muito rápido.

**Quais são as permissões necessárias para configurar o EOP?**

Para configurar o EOP, você deve ser um administrador global ou um administrador da empresa do Exchange (o grupo de funções Gerenciamento da organização).

**P. Como eu sei se meus dados e informações particulares estão seguros?**

R. Para saber mais sobre as medidas que adotamos para garantir a segurança dos seus dados e informações particulares, inclusive informações sobre Contratos de Nível de Serviço (SLAs), vá para a [Central de Confiabilidade do Office 365](https://www.microsoft.com/trust-center).

**P. Há algum limite que eu deva conhecer; por exemplo, limitações de tamanho da mensagem?**

A. Sim. Para obter mais informações sobre limites no EOP, consulte [Limites do Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits).

**P. o EOP oferece suporte ao PowerShell?**

R. Sim, a funcionalidade do EOP completo está disponível por meio do PowerShell. Para obter mais informações, consulte [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/exchange-online-protection-powershell).
