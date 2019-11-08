---
title: Criar listas de remetentes bloqueados no Office 365
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
description: Bloquear as opções da lista de remetentes incluem remetentes bloqueados do Outlook, listas de bloqueios de remetente/domínio antispam, listas de bloqueio de IP e regras de transporte do Exchange (ETRs) também chamadas de fluxo de emails.
ms.openlocfilehash: 7f52472f54fb1de93f02b271ec6338da3fb1af93
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2019
ms.locfileid: "38032396"
---
# <a name="create-block-sender-lists-in-office-365"></a>Criar listas de remetentes bloqueados no Office 365

Às vezes, é necessário bloquear emails indesejados de remetentes. Há vários métodos disponíveis para escolher. Essas opções incluem remetentes bloqueados do Outlook, listas de bloqueios de remetente/domínio antispam, listas de bloqueio de IP e regras de transporte do Exchange (ETRs, que também são conhecidas como regras de fluxo de emails).

> [!NOTE]
> Enquanto as listas de bloqueio da organização podem ser usadas para tratar de falsos negativos (spam perdido), esses candidatos também devem ser enviados para a Microsoft para análise. O gerenciamento de falsos negativos usando listas de bloqueio aumenta significativamente a sobrecarga administrativa. Se você usar uma lista de bloqueios para esse propósito, você também precisará manter o artigo para [enviar mensagens de spam, não spam e golpes de phishing para a Microsoft para análise](https://docs.microsoft.com/office365/SecurityCompliance/submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis), no Ready.

O método apropriado para configurar listas de remetentes bloqueados varia dependendo do escopo do impacto. Para o impacto de um único usuário, a solução certa pode ser usar remetentes bloqueados do Outlook, mas se vários usuários ou todos os usuários estiverem sendo afetados, uma das outras opções será mais apropriada.

## <a name="options-from-least-to-broadest-scope"></a>Opções do menor para o maior escopo

Ao criar uma lista de bloqueios, é importante escolher o método adequado com base no escopo do impacto (quantas pessoas serão impactadas), para que ela coincida com a amplitude do método de bloqueio. As opções listadas abaixo são classificadas por escopo e por amplitude. A lista vai de estreito a amplo, mas *Leia as especificações* de recomendações completas.

- Remetentes bloqueados do Outlook
- Política antispam: listas de bloqueios de remetente/domínio
- Regras de transporte do Exchange (ETRs também chamadas de regras de fluxo de emails)
- Política antispam: listas de bloqueios de IP

## <a name="use-outlook-blocked-senders"></a>Usar remetentes bloqueados do Outlook

Quando somente um pequeno número de usuários é afetado, isso ocorre quando os remetentes bloqueados do Outlook devem ser usados, pois isso afetará apenas o envio de emails para eles.

> [!IMPORTANT]
> Se as mensagens indesejadas forem boletins informativos de uma fonte confiável e reconhecível, a cancelamento do email é outra opção para impedir que o usuário obtenha os emails no futuro.

As etapas para configurar isso são diferentes entre o [Outlook Web App](https://support.office.com/article/block-or-allow-junk-email-settings-48c9f6f7-2309-4f95-9a4d-de987e880e46) e o [cliente do Outlook](https://support.office.com/article/overview-of-the-junk-email-filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089). **Quando as mensagens são bloqueadas com êxito devido a remetentes bloqueados, você verá SFV: BLK no X-Forefront-antispam-Report** , que indica que a mensagem está sendo bloqueada.

## <a name="use-anti-spam-policy-senderdomain-block-lists"></a>Usar listas de bloqueio de remetente/domínio de política antispam

Quando vários usuários estão sendo afetados, o escopo é mais largo e você precisa usar uma política anti-spam de lista de remetente/domínio em toda a empresa. As etapas detalhadas podem ser encontradas em [configurar seu documento de políticas de filtro de spam](https://docs.microsoft.com/office365/securitycompliance/configure-your-spam-filter-policies) . Qualquer mensagem bloqueada por esse método seguirá a ação de spam conforme configurada na política.

O limite máximo para essas listas é de aproximadamente 1000 entradas.

## <a name="use-exchange-transport-rules-etrs-to-block-specific-senders"></a>Usar regras de transporte do Exchange (ETRs) para bloquear remetentes específicos

Se for necessário bloquear as mensagens enviadas para usuários específicos ou por toda a organização, o ETRs (também chamado de regras de fluxo de email) poderá ser usado. ETRs são mais flexíveis porque podem disparar o endereço de email do remetente ou o domínio, bem como palavras-chave e outras propriedades da mensagem. Essa flexibilidade permitirá a criação de blocos de conclusão parcial. [Clique para obter as etapas para criar um ETR, também conhecido como regras de fluxo de emails](https://docs.microsoft.com/office365/SecurityCompliance/use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages).

> [!IMPORTANT]
> É fácil criar regras que são muito agressivas, como resultado, é importante que o critério que está sendo usado seja *o mais específico* possível. Além disso, certifique-se de habilitar a auditoria na regra que você criou e teste para garantir que tudo funcione conforme o esperado.

## <a name="use-anti-spam-policy-ip-block-lists"></a>Usar listas de bloqueio de IP de política antispam

Quando não é possível usar uma das outras opções para bloquear um remetente *, a lista* de IPs bloqueados de política antispam pode ser usada. [As etapas detalhadas podem ser encontradas no artigo configurar a política de filtro de conexão](https://docs.microsoft.com/office365/securitycompliance/configure-the-connection-filter-policy). É importante manter a lista de IPs bloqueados para um *mínimo* e usar intervalos de endereços IP aqui *não* é recomendável.

Você deve *especialmente* evitar a adição de intervalos de endereços IP que pertencem a serviços de consumidor ou infraestruturas compartilhadas, e também garantir que você revise a lista de endereços IP permitidos como parte da manutenção normal. **Como o permite que as entradas possam abrir rotas para ataques, você deve gerenciar de forma mais detalhada essa lista e remover regularmente as entradas que não são mais necessárias.** Além disso, se você permitir, em uma lista de remetentes seguros, leia e entenda os riscos e precauções em *[criar listas de remetentes seguros no Office 365](create-safe-sender-lists-in-office-365.md)*.
