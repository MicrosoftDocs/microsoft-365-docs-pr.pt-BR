---
title: Criar listas de remetentes bloqueados
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150s
description: Os administradores podem saber mais sobre as opções disponíveis e preferenciais para bloquear mensagens de entrada no Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5c95b49db811807a0cb46dce5363b8ae2dbe5602
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287276"
---
# <a name="create-blocked-sender-lists-in-eop"></a>Criar listas de remetentes bloqueados no EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Nas organizações do Microsoft 365 com caixas de correio no Exchange Online ou em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, o EOP oferece várias maneiras de bloquear emails de destinatários indesejados. Essas opções incluem Remetentes Bloqueados do Outlook, listas de remetentes bloqueados ou listas de domínios bloqueados em políticas anti-spam, regras de fluxo de emails do Exchange (também conhecidas como regras de transporte) e a Lista de Bloqueios de IP (filtragem de conexão). Coletivamente, você pode pensar nessas opções como listas _de remetentes bloqueados._

O melhor método para bloquear os envios varia no escopo do impacto. Para um único usuário, a solução certa poderia ser o Outlook Blocked Senders. Para muitos usuários, uma das outras opções seria mais apropriada. As opções a seguir são classificadas por escopo e amplitude de impacto. A lista vai de estreita para ampla, mas *leia as especificações para* recomendações completas.

1. Outlook Blocked Senders (the Blocked Senders list that's stored in each mailbox)

2. Listas de remetentes bloqueados ou listas de domínios bloqueados (políticas anti-spam)

3. Regras do fluxo de email

4. A Lista de Bloqueios de IP (filtragem de conexão)

> [!NOTE]
> Embora você possa usar configurações de bloqueio em toda a organização para lidar com falsos negativos (spam perdido), você também deve enviar essas mensagens à Microsoft para análise. Gerenciar falsos negativos usando listas de bloqueios aumenta significativamente sua sobrecarga administrativa. Se você usar listas de bloqueio para evitar spam perdido, precisará manter o tópico Relatar mensagens e arquivos para a [Microsoft](report-junk-email-messages-to-microsoft.md) quando estiver pronto.

Por outro lado, você também tem várias opções para sempre permitir emails de fontes específicas usando _listas de remetentes confiáveis._ Para obter mais informações, confira [Criar listas de remetentes seguros](create-safe-sender-lists-in-office-365.md).

## <a name="email-message-basics"></a>Noções básicas sobre mensagens de email

Uma mensagem de email SMTP padrão consiste em um *envelope de mensagem* e conteúdo de mensagem. O envelope da mensagem contém informações necessárias para transmitir e entregar a mensagem entre servidores SMTP. O conteúdo da mensagem contém campos de título da mensagem (coletivamente chamado de título da *mensagem)* e o corpo da mensagem. O envelope da mensagem é descrito na RFC 5321 e o header da mensagem é descrito na RFC 5322. Os destinatários nunca veem o envelope real da mensagem porque ele é gerado pelo processo de transmissão da mensagem e não faz parte realmente da mensagem.

- O endereço (também conhecido como endereço MAIL FROM, remetente P1 ou remetente de envelope) é o endereço de email usado na transmissão `5321.MailFrom` SMTP  da mensagem. Esse endereço de email normalmente é registrado no campo de título **Return-Path** no título da mensagem (embora seja possível para o remetente designar um endereço de email de Caminho **de** Retorno diferente). Se a mensagem não puder ser entregue, será o destinatário do relatório de não entrega (também conhecido como NDR ou mensagem de rejeição).

- O (também conhecido como endereço De ou remetente P2) é o endereço de email no campo de título De e é o endereço de email do remetente exibido nos clientes de `5322.From` email.  

Frequentemente, os `5321.MailFrom` `5322.From` endereços e os endereços são os mesmos (comunicação de pessoa para pessoa). No entanto, quando o email é enviado em nome de outra pessoa, os endereços podem ser diferentes.

Listas de remetentes bloqueados e listas de domínios bloqueados em políticas anti-spam no EOP inspecionam os `5321.MailFrom` endereços e os `5322.From` endereços. O Outlook Blocked Senders usa apenas o `5322.From` endereço.

## <a name="use-outlook-blocked-senders"></a>Usar o Outlook Blocked Senders

Quando apenas um pequeno número de usuários recebeu emails indesejados, os usuários ou administradores podem adicionar os endereços de email do remetente à lista remetentes bloqueados na caixa de correio. Para obter instruções, consulte [Definir configurações de lixo eletrônico em caixas de correio do Exchange Online.](configure-junk-email-settings-on-exo-mailboxes.md)

Quando as mensagens são bloqueadas com êxito devido à lista de Usuários Bloqueados, o campo de header **X-Forefront-Antispam-Report** conterá o `SFV:BLK` valor.

> [!NOTE]
> Se as mensagens indesejadas são boletins informativos de uma fonte confiável e reconhecível, cancelar a assinatura do email é outra opção para impedir que o usuário receba as mensagens.

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a>Usar listas de remetentes bloqueados ou listas de domínios bloqueados

Quando vários usuários são afetados, o escopo é mais amplo, portanto, a próxima melhor opção é listas de remetentes bloqueados ou listas de domínios bloqueados em políticas anti-spam. As mensagens dos remetentes nas listas são marcadas como **Spam,** e a ação que você configurou para o veredito do filtro de **spam** é tomada na mensagem. Para saber mais, confira [Configurar políticas anti-spam](configure-your-spam-filter-policies.md).

O limite máximo para essas listas é de aproximadamente 1.000 entradas.

## <a name="use-mail-flow-rules"></a>Usar regras de fluxo de emails

Se você precisar bloquear mensagens enviadas a usuários específicos ou por toda a organização, poderá usar regras de fluxo de emails. As regras de fluxo de emails são mais flexíveis do que bloquear listas de remetentes ou listas de domínios de remetentes bloqueados porque elas também podem procurar palavras-chave ou outras propriedades nas mensagens indesejadas.

Independentemente das condições ou exceções que você usa para identificar as mensagens, configure a ação para definir o nível de confiança de spam (SCL) da mensagem como 9, o que marca a mensagem como **spam** de alta confiança. Para obter mais informações, [consulte Usar regras de fluxo de emails para definir o SCL em mensagens.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

> [!IMPORTANT]
> É fácil criar regras muito  agressivas, portanto, é importante identificar apenas as mensagens que você deseja bloquear usando critérios muito específicos. Além disso, certifique-se de habilitar a auditoria na regra e testar os resultados da regra para garantir que tudo funcione conforme o esperado.

## <a name="use-the-ip-block-list"></a>Usar a Lista de Bloqueios de IP

Quando não for possível usar uma das outras opções para bloquear um *remetente,* só então você deverá usar a Lista de Bloqueios de IP na política de filtro de conexão. Para obter mais informações, consulte [Configurar a política de filtro de conexão](configure-the-connection-filter-policy.md). É importante manter o número mínimo de IPs bloqueados, portanto,  não é recomendável bloquear intervalos de endereços IP inteiros.

Você  deve evitar especialmente adicionar intervalos de endereço IP que pertencem a serviços de consumidor (por exemplo, outlook.com) ou infraestruturas compartilhadas, e também garantir que revise a lista de endereços IP bloqueados como parte da manutenção regular.
