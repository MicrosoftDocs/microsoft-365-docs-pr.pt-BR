---
title: Criar listas de remetentes bloqueados no Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 5/6/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
description: Bloquear as opções da lista de remetentes incluem remetentes bloqueados do Outlook, listas de bloqueios de remetente/domínio antispam, listas de bloqueio de IP e regras de fluxo de emails do Exchange (regras de transporte).
ms.openlocfilehash: fb5228bca7ac0c98a2aafd9d7b582e370698649a
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599538"
---
# <a name="create-block-sender-lists-in-office-365"></a>Criar listas de remetentes bloqueados no Office 365

Às vezes, é necessário bloquear emails indesejados de remetentes. Há vários métodos disponíveis para escolher. Essas opções incluem remetentes bloqueados do Outlook, listas de bloqueio de remetente/domínio antispam, listas de bloqueio de IP e regras de fluxo de emails do Exchange (também conhecidas como regras de transporte).

> [!NOTE]
> Enquanto as listas de bloqueio da organização podem ser usadas para tratar de falsos negativos (spam perdido), esses candidatos também devem ser enviados para a Microsoft para análise. O gerenciamento de falsos negativos usando listas de bloqueio aumenta significativamente a sobrecarga administrativa. Se você usar uma lista de bloqueios para esse propósito, você também precisará manter o artigo para [enviar mensagens de spam, não spam e golpes de phishing para a Microsoft para análise](https://docs.microsoft.com/office365/SecurityCompliance/submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis), no Ready.

O método apropriado para configurar listas de remetentes bloqueados varia dependendo do escopo do impacto. Para o impacto de um único usuário, a solução certa pode ser usar remetentes bloqueados do Outlook, mas se vários usuários ou todos os usuários estiverem sendo afetados, uma das outras opções será mais apropriada.

## <a name="options-from-least-to-broadest-scope"></a>Opções do menor para o maior escopo

Ao criar uma lista de bloqueios, é importante escolher o método adequado com base no escopo do impacto (quantas pessoas serão impactadas), para que ela coincida com a amplitude do método de bloqueio. As opções listadas abaixo são classificadas por escopo e por amplitude. A lista vai de estreito a amplo, mas *Leia as especificações* de recomendações completas.

- Remetentes bloqueados do Outlook
- Política antispam: listas de bloqueios de remetente/domínio
- Regras de fluxo de email do Exchange
- Política antispam: listas de bloqueios de IP

## <a name="use-outlook-blocked-senders"></a>Usar remetentes bloqueados do Outlook

Quando somente um pequeno número de usuários é afetado, isso ocorre quando os remetentes bloqueados do Outlook devem ser usados, pois isso afetará apenas o envio de emails para eles.

> [!IMPORTANT]
> Se as mensagens indesejadas forem boletins informativos de uma fonte confiável e reconhecível, a cancelamento do email é outra opção para impedir que o usuário obtenha os emails no futuro.

As etapas para configurar isso são diferentes entre o [Outlook na Web](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46) e o [cliente do Outlook](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089). **Quando as mensagens são bloqueadas com êxito devido a remetentes bloqueados, você verá SFV: BLK no X-Forefront-antispam-Report** , que indica que a mensagem está sendo bloqueada.

## <a name="use-anti-spam-policy-senderdomain-block-lists"></a>Usar listas de bloqueio de remetente/domínio de política antispam

Quando vários usuários estão sendo afetados, o escopo é mais largo e você precisa usar uma política anti-spam de lista de remetente/domínio em toda a empresa. As etapas detalhadas podem ser encontradas em [configurar suas políticas de filtro de spam](configure-your-spam-filter-policies.md). Qualquer mensagem bloqueada por esse método seguirá a ação de spam conforme configurada na política.

O limite máximo para essas listas é de aproximadamente 1000 entradas; no entanto, você poderá inserir 30 entradas no Portal. Você deve usar o PowerShell para adicionar mais de 30 entradas.

## <a name="use-exchange-mail-flow-rules-specific-senders"></a>Usar remetentes específicos de regras de fluxo de email do Exchange

Se você precisar impedir que as mensagens sejam enviadas para usuários específicos ou por toda a organização, você pode usar regras de fluxo de email. As regras de fluxo de emails são mais flexíveis porque podem disparar o endereço de email do remetente ou o domínio, bem como palavras-chave e outras propriedades da mensagem. Essa flexibilidade permitirá a criação de blocos de conclusão parcial. Para obter mais informações sobre regras de fluxo de emails, consulte [use Mail Flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).

> [!IMPORTANT]
> É fácil criar regras que são muito agressivas, como resultado, é importante que o critério que está sendo usado seja *o mais específico* possível. Além disso, certifique-se de habilitar a auditoria na regra que você criou e teste para garantir que tudo funcione conforme o esperado.

## <a name="use-anti-spam-policy-ip-block-lists"></a>Usar listas de bloqueio de IP de política antispam

Quando não é possível usar uma das outras opções para bloquear um *remetente, você* pode usar a lista de IPs bloqueados de política antispam. Para obter mais informações, consulte [Configurar a política de filtro de conexão](configure-the-connection-filter-policy.md). É importante manter o número mínimo de IPs bloqueados, portanto, *não* é recomendável bloquear intervalos de endereços IP inteiros.

Você deve *especialmente* evitar a adição de intervalos de endereços IP que pertencem a serviços de consumidor ou infraestruturas compartilhadas, e também garantir que você revise a lista de endereços IP permitidos como parte da manutenção normal. **Como o permite que as entradas possam abrir rotas para ataques, você deve gerenciar de forma mais detalhada essa lista e remover regularmente as entradas que não são mais necessárias.** Além disso, se você permitir, em uma lista de remetentes seguros, leia e entenda os riscos e precauções em *[criar listas de remetentes seguros no Office 365](create-safe-sender-lists-in-office-365.md)*.
