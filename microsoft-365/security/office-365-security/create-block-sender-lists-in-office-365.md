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
description: Os administradores podem aprender sobre as opções disponíveis e preferenciais para bloquear mensagens de entrada no Proteção do Exchange Online (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c844378a19ba7995cbd616f615e8a84994f9bf26
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624072"
---
# <a name="create-blocked-sender-lists-in-eop"></a>Criar listas de remetentes bloqueados no EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Em organizações Microsoft 365 com caixas de correio em organizações Exchange Online ou autônomas Proteção do Exchange Online (EOP) sem Exchange Online caixas de correio, o EOP oferece várias maneiras de bloquear emails de destinatários indesejados. Essas opções incluem Outlook remetentes bloqueados, listas de remetentes bloqueados ou listas de domínios bloqueados em políticas anti-spam, Exchange regras de fluxo de emails (também conhecidas como regras de transporte) e a Lista de Bloqueios de IP (filtragem de conexão). Coletivamente, você pode pensar nessas opções como listas _de remetentes bloqueados._

O melhor método para bloquear os envios varia no escopo do impacto. Para um único usuário, a solução certa pode ser enviar Outlook Bloqueados. Para muitos usuários, uma das outras opções seria mais apropriada. As opções a seguir são classificadas pelo escopo de impacto e amplitude. A lista vai de estreita a ampla, mas *leia os detalhes para* recomendações completas.

1. Outlook Senders bloqueados (a lista De envios bloqueados armazenada em cada caixa de correio)

2. Listas de remetentes bloqueados ou listas de domínios bloqueados (políticas anti-spam)

3. Regras do fluxo de email

4. A Lista de Bloqueios de IP (filtragem de conexão)

> [!NOTE]
> Embora você possa usar as configurações de bloqueio em toda a organização para resolver falsos negativos (spam perdido), você também deve enviar essas mensagens à Microsoft para análise. Gerenciar falsos negativos usando listas de bloqueio aumenta significativamente sua sobrecarga administrativa. Se você usar listas de bloqueio para desviar o spam perdido, você precisará manter o tópico Relatar mensagens e arquivos para a [Microsoft](report-junk-email-messages-to-microsoft.md) em condições prontas.

Por outro lado, você também tem várias opções para sempre permitir emails de fontes específicas usando _listas de remetentes confiáveis._ Para obter mais informações, confira [Criar listas de remetentes seguros](create-safe-sender-lists-in-office-365.md).

## <a name="email-message-basics"></a>Noções básicas de mensagens de email

Uma mensagem de email SMTP padrão consiste em um *envelope de mensagem* e conteúdo de mensagem. O envelope de mensagem contém informações necessárias para transmitir e entregar a mensagem entre servidores SMTP. O conteúdo da mensagem contém campos de header de mensagem (coletivamente chamado de *header* da mensagem ) e o corpo da mensagem. O envelope de mensagem é descrito no RFC 5321 e o header da mensagem é descrito no RFC 5322. Os destinatários nunca veem o envelope de mensagem real porque ele é gerado pelo processo de transmissão de mensagens e não faz parte da mensagem.

- O endereço (também conhecido como endereço MAIL FROM, remetente P1 ou remetente de envelope) é o endereço de email usado na transmissão `5321.MailFrom` SMTP  da mensagem. Esse endereço de email normalmente é registrado no campo de header **Return-Path** no header da mensagem (embora seja possível que o remetente designe um endereço de email **return-path** diferente). Se a mensagem não puder ser entregue, será o destinatário do relatório de não entrega (também conhecido como NDR ou mensagem de rejeição).

- O (também conhecido como o endereço De ou remetente P2) é o endereço de email no campo de header From e é o endereço de email do remetente exibido em clientes de `5322.From` email.  

Frequentemente, os `5321.MailFrom` `5322.From` endereços e são os mesmos (comunicação de pessoa para pessoa). No entanto, quando o email é enviado em nome de outra pessoa, os endereços podem ser diferentes.

Listas de remetentes bloqueados e listas de domínios bloqueados em políticas anti-spam no EOP inspecionam os `5321.MailFrom` endereços e os `5322.From` endereços. Outlook Remetentes bloqueados só usam o `5322.From` endereço.

## <a name="use-outlook-blocked-senders"></a>Usar Outlook bloqueados

Quando apenas um pequeno número de usuários recebeu emails indesejados, os usuários ou administradores podem adicionar os endereços de email do remetente à lista Remetentes Bloqueados na caixa de correio. Para obter instruções, consulte [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md).

Quando as mensagens são bloqueadas com êxito devido à lista De envios bloqueados de um usuário, o campo de header **X-Forefront-Antispam-Report** conterá o valor `SFV:BLK` .

> [!NOTE]
> Se as mensagens indesejadas são boletins informativos de uma fonte confiável e reconhecível, cancelar a assinatura do email é outra opção para impedir que o usuário receba as mensagens.

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a>Usar listas de remetentes bloqueados ou listas de domínios bloqueados

Quando vários usuários são afetados, o escopo é mais amplo, portanto, a próxima melhor opção é listas de remetentes bloqueados ou listas de domínios bloqueados em políticas anti-spam. As mensagens dos remetentes nas listas são marcadas como **spam** de alta confiança e a ação que você configurou para o veredito de filtro de **spam** de alta confiança é tomada na mensagem. Para saber mais, confira [Configurar políticas anti-spam](configure-your-spam-filter-policies.md).

O limite máximo para essas listas é de aproximadamente 1.000 entradas.

## <a name="use-mail-flow-rules"></a>Usar regras de fluxo de emails

Se você precisar bloquear mensagens enviadas a usuários específicos ou em toda a organização, poderá usar regras de fluxo de emails. As regras de fluxo de emails são mais flexíveis do que bloquear listas de remetentes ou listas de domínios de remetente bloqueados porque também podem procurar palavras-chave ou outras propriedades nas mensagens indesejadas.

Independentemente das condições ou exceções que você usa para identificar as mensagens, configure a ação para definir o nível de confiança de spam (SCL) da mensagem como 9, o que marca a mensagem como **spam** de alta confiança. Para obter mais informações, [consulte Use mail flow rules to set the SCL in messages](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl).

> [!IMPORTANT]
> É fácil criar regras que sejam *muito* agressivas, portanto, é importante que você identifique apenas as mensagens que você deseja bloquear usando critérios muito específicos. Além disso, certifique-se de habilitar a auditoria na regra e testar os resultados da regra para garantir que tudo funcione conforme esperado.

## <a name="use-the-ip-block-list"></a>Usar a lista de bloqueios de IP

Quando não é possível usar uma das outras opções para bloquear um *remetente,* somente então você deve usar a Lista de Bloqueios de IP na política de filtro de conexão. Para obter mais informações, consulte [Configurar a política de filtro de conexão](configure-the-connection-filter-policy.md). É importante manter o número mínimo de IPs bloqueados, portanto,  não é recomendável bloquear intervalos de endereços IP inteiros.

Você  deve especialmente evitar adicionar intervalos de endereços IP que pertencem a serviços de consumidor (por exemplo, outlook.com) ou infraestruturas compartilhadas e também garantir que você revise a lista de endereços IP bloqueados como parte da manutenção regular.
