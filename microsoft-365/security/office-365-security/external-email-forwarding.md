---
title: Configurando e controlando o encaminhamento de emails externos, encaminhamento automático, acesso de 5.7.520 negado, desabilitar o encaminhamento externo, o administrador desabilitou o encaminhamento externo, política antispam de saída
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2020
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.openlocfilehash: 7cb2ab9c6987900f2b53a17c3eda49001bca4d84
ms.sourcegitcommit: 90efec455336b4cecc06a8cbf0ce287740433523
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2020
ms.locfileid: "46898047"
---
# <a name="configuring-external-email-forwarding-in-office-365"></a>Configurando o encaminhamento de email externo no Office 365

O encaminhamento externo é controlado pela *política antispam de saída* e com escopo para os usuários com base na configuração configurada. As 3 configurações atualmente são suportadas:

- **Automático** – nesse modo, o sistema é responsável por decidir se uma mensagem encaminhada é permitida ou não.  Este é o modo padrão e, nesse modo, o sistema bloqueará o encaminhamento externo automático.

- **Ativado** – o encaminhamento externo automático é permitido e não é restrito.

- **Off** – o encaminhamento externo automático está desabilitado e resultará em um relatório de falha na entrega (NDR) para o usuário final.

Consulte [Configure Outbound spam Filtering in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide) para obter mais informações sobre como definir essas configurações.

## <a name="controlling-external-email-forwarding"></a>Controle de encaminhamento de email externo

Como administrador de uma organização, você pode ter requisitos de empresa para restringir ou controlar quem poderá encaminhar emails automaticamente usando regras de caixa de entrada ou encaminhamento SMTP, fora da organização. O encaminhamento de emails pode ser um recurso útil, mas também pode representar um risco por meio da possível divulgação de informações, mesmo fornecendo informações a invasores que podem ser aproveitados para atacar a organização ou seus parceiros.

O Office 365 não permite o encaminhamento externo automático por regras de caixa de entrada ou configuração de caixa de correio, que fornece uma política padrão segura. No entanto, o administrador pode modificar essas configurações para todos ou alguns usuários da organização. O encaminhamento de mensagens entre usuários internos não é afetado por tal modificação.

> [!NOTE]
> Desabilitar o encaminhamento automático para endereços externos no Office 365 está sendo lançado em fases com detalhes comunicados por meio de postagens do [centro de mensagens](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) . Para ajudar os administradores a se preparar para essas alterações, eles modificam as políticas antecipadamente para garantir que não haja interrupção nos seus usuários.

Mais informações sobre os usuários que usam o encaminhamento automático (regras de caixa de entrada ou encaminhamento SMTP) em sua organização podem ser encontradas no [relatório de mensagens de encaminhamento automático](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide).

## <a name="how-does-this-policy-work-with-other-automatic-forwarding-controls"></a>Como essa política funciona com outros controles de encaminhamento automáticos

Como administrador, você pode já ter outros tipos de controles em vigor, bloqueando o encaminhamento automático em [domínios remotos](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) e o uso de uma regra de transporte do Exchange (ETR). Esses dois controles são independentes desse recurso específico, por exemplo, se você permitir o encaminhamento automático para um domínio remoto, mas bloquear o encaminhamento automático por meio da política de spam de saída, o resultado será que a mensagem encaminhada automaticamente é bloqueada. Da mesma forma, se você permitir o encaminhamento automático na política de spam de saída, mas bloqueá-lo em um ETR ou domínio remoto, a mensagem será bloqueada por qualquer um desses controles. Isso permite que você, por exemplo, permita o encaminhamento automático na política de spam de saída e utilize domínios remotos para controlar os domínios para os quais os usuários podem encaminhar mensagens automaticamente.


## <a name="the-blocked-email-forwarding-message"></a>A mensagem de encaminhamento de email bloqueado

Quando uma mensagem é detectada como encaminhada automaticamente e a política organizacional *bloqueia* que a atividade de um relatório de falha na **entrega (NDR)** será gerada de volta para o usuário final. O relatório indicará que a mensagem não foi entregue. O NDR terá o seguinte formato: 

`5.7.520 Access Denied – Your administrator has disabled external forwarding – AS(XXXX)`
