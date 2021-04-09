---
title: Proteção antispam
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender sobre as configurações e filtros anti-spam que ajudarão a evitar spam no Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: eaff771d6fa0490819ec076b5a9a43ac843cf207
ms.sourcegitcommit: a46532bb422ee51331f478ff50cc5444586bf6a9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2021
ms.locfileid: "51650261"
---
# <a name="anti-spam-protection-in-eop"></a>Proteção anti-spam no EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)

> [!NOTE]
> Este tópico destina-se aos administradores. Para tópicos do usuário final, consulte [Overview of the Junk Email Filter](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) and Learn about junk email and [phishing](https://support.microsoft.com/office/86c1d76f-4d5a-4967-9647-35665dc17c31).

Nas organizações do Microsoft 365 com caixas de correio no Exchange Online ou organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, as mensagens de email são automaticamente protegidas contra spam (lixo eletrônico) pelo EOP.

O roteiro de segurança de email da Microsoft envolve uma abordagem entre produtos inigualável. A tecnologia anti-spam e anti-phishing do EOP é aplicada em nossas plataformas de email para fornecer aos usuários as ferramentas anti-spam e anti-phishing mais recentes e inovações em toda a rede. O objetivo do EOP é oferecer um serviço de email abrangente e usável que ajuda a detectar e proteger os usuários contra lixo eletrônico, ameaças de email fraudulentas (phishing) e malware.

À medida que o uso de email aumentou, o abuso de email também aumentou. O lixo eletrônico não monitorado pode clogar caixas de entrada e redes, afetar a satisfação do usuário e prejudicar a eficácia de comunicações de email legítimas. É por isso que a Microsoft continua a investir em tecnologias anti-spam. Simplificando, ele começa com a contenção e filtragem de lixo eletrônico.

> [!TIP]
> As seguintes tecnologias anti-spam são úteis quando você deseja permitir ou bloquear mensagens com base no envelope da mensagem (por exemplo, o domínio do remetente ou o endereço IP de origem da mensagem). Para permitir ou bloquear mensagens com base na carga (por exemplo, URLs na mensagem ou arquivos anexados), você deve usar o [portal de](tenant-allow-block-list.md)Lista de Locatários.

## <a name="anti-spam-technologies-in-eop"></a>Tecnologias anti-spam no EOP

Para ajudar a reduzir o lixo eletrônico, o EOP inclui a proteção contra lixo eletrônico que usa tecnologias proprietárias de filtragem de spam para identificar e separar lixo eletrônico de emails legítimos. A filtragem de spam do EOP aprende com ameaças conhecidas de spam e phishing e comentários de usuários de nossa plataforma de consumidor, Outlook.com. Os comentários contínuos dos usuários do EOP no programa de classificação de lixo eletrônico ajudam a garantir que as tecnologias do EOP sejam continuamente treinados e aprimorados.

As configurações anti-spam no EOP são feitas das seguintes tecnologias:

- **Filtragem** de conexão : identifica servidores de origem de email bons e ruins no início da conexão de email de entrada por meio da Lista de IDs, lista de bloqueios de IP e a lista segura *(uma* lista dinâmica, mas não editável de envios confiáveis mantidos pela Microsoft). Você configura essas configurações na política de filtro de conexão. Saiba mais em [Configurar filtragem de conexão](configure-the-connection-filter-policy.md).

  > [!NOTE]
  > A inteligência de spoof usa a filtragem de conexão para criar listas de permitir e bloquear os envios que estão fazendo a spoofing do seu domínio de email. Para obter mais informações, consulte Saiba mais sobre a inteligência [de spoof no Microsoft 365](learn-about-spoof-intelligence.md).

- **Filtragem de** spam (filtragem de conteúdo) : O EOP usa os vereditos de filtragem de spam **Spam,** **spam** de alta **confiança,** email em massa, email de **phishing** e email de **phishing** de alta confiança para classificar mensagens. Você pode configurar as ações a tomar com base nesses vereditos e pode configurar as opções de notificação do usuário final para mensagens que foram colocadas em quarentena em vez de entregues. Para obter mais informações, consulte [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).

  > [!NOTE]
  > Por padrão, a filtragem de spam é configurada para enviar mensagens marcadas como spam para a pasta Lixo Eletrônico do destinatário. No entanto, em ambientes híbridos em que o EOP protege caixas de correio locais do Exchange, você precisa configurar duas regras de fluxo de emails (também conhecidas como regras de transporte) em sua organização local do Exchange para reconhecer os headers de spam do EOP adicionados às mensagens. Para obter detalhes, confira [Configurar a EOP autônoma para enviar spam à pasta Lixo Eletrônico em ambientes híbridos](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

- **Filtragem de spam** de saída : O EOP também verifica se os usuários não enviam spam, seja no conteúdo da mensagem de saída ou excedendo os limites de mensagem de saída. Para obter mais informações, consulte [Configure outbound spam filtering in Microsoft 365](configure-the-outbound-spam-policy.md).

- **Spoof intelligence**: Para obter mais informações, consulte Saiba mais sobre a inteligência de [spoof no Microsoft 365](learn-about-spoof-intelligence.md).

## <a name="manage-errors-in-spam-filtering"></a>Gerenciar erros na filtragem de spam

É possível que as boas mensagens possam ser identificadas como spam (também conhecidos como falsos positivos) ou que o spam possa ser entregue à Caixa de Entrada. Você pode usar as sugestões nas seções a seguir para descobrir o que aconteceu e ajudar a impedir que isso aconteça no futuro.

Aqui estão algumas práticas recomendadas que se aplicam a qualquer cenário:

- Sempre envie mensagens mal classificadas para a Microsoft. Para mais informações, confira [Relatar mensagens e arquivos à Microsoft](report-junk-email-messages-to-microsoft.md).

- **Examine os headers de mensagens anti-spam**: esses valores explicarão por que uma mensagem foi marcada como spam ou por que ela ignorou a filtragem de spam. Para obter mais informações, consulte [Cabeçalhos de mensagem antispam](anti-spam-message-headers.md).

- **Aponte seu registro MX para o Microsoft 365**: Para que o EOP forneça a melhor proteção, sempre recomendamos que você tenha emails entregues primeiro ao Microsoft 365. Para obter instruções, consulte [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).

  Se o registro MX aponta para algum outro local (por exemplo, uma solução anti-spam de terceiros ou um dispositivo), é difícil para o EOP fornecer filtragem de spam precisa. Nesse cenário, você precisa configurar a Filtragem Aprimorada para conectores (também conhecido como _lista de ignorar_). Para obter instruções, consulte [Enhanced Filtering for Connectors in Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

- **Usar a autenticação** de email : se você possui um domínio de email, pode usar o DNS para ajudar a garantir que as mensagens dos enviadores nesse domínio sejam legítimas. Para ajudar a evitar spams e fraudes indesejadas no EOP, use todos os seguintes métodos de autenticação de email:

  - **SPF**: A Estrutura de Política do Remetente verifica o endereço IP de origem da mensagem em relação ao proprietário do domínio de envio. Para obter uma introdução rápida ao SPF e configurá-lo rapidamente, consulte Configurar o SPF para ajudar a [evitar a spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md). Para compreender melhor como o Microsoft 365 usa a SPF, para solucionar problemas ou para implantações fora do padrão, como as implantações híbridas, comece com [Como o Microsoft 365 usa a estrutura de política do remetente (SPF) para evitar a falsificação](how-office-365-uses-spf-to-prevent-spoofing.md).

  - **DKIM**: DomainKeys Identified Mail adiciona uma assinatura digital ao header de mensagens enviadas de seu domínio. Para obter informações, [consulte Use DKIM to validate outbound email sent from your custom domain in Microsoft 365](use-dkim-to-validate-outbound-email.md).

  - **DMARC**: Autenticação, Relatórios e Conformidade de Mensagens baseadas em domínio ajuda os sistemas de email de destino a determinar o que fazer com mensagens que falham nas verificações SPF ou DKIM e fornece outro nível de confiança para seus parceiros de email. Para obter mais informações, [consulte Use DMARC to validate email in Microsoft 365](use-dmarc-to-validate-email.md).

- **Verifique suas** configurações de email em massa : O limite bcl (nível de reclamação em massa) que você configura em políticas anti-spam determina se o email em massa (também conhecido como email cinza _)_ está marcado como spam. A configuração somente do PowerShell _MarkAsSpamBulkMail_ que está em por padrão também contribui para os resultados. Para obter mais informações, consulte [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).

### <a name="prevent-the-delivery-of-spam-to-the-inbox"></a>Impedir a entrega de spam na Caixa de Entrada

- **Verifique as** configurações da sua organização: observe as configurações que permitem que as mensagens ignorem a filtragem de spam (por exemplo, se você adicionar seu próprio domínio à lista de domínios permitidos em políticas anti-spam). Para nossas configurações recomendadas, consulte Configurações recomendadas para segurança do EOP e [do Microsoft Defender para Office 365](recommended-settings-for-eop-and-office365.md) e Criar listas de [remetentes seguros.](create-safe-sender-lists-in-office-365.md)

- **Verifique** se a regra de lixo eletrônico está habilitada na caixa de correio do usuário : Ela está habilitada por padrão, mas se estiver desabilitada, as mensagens marcadas como lixo eletrônico não podem ser movidas para a pasta Lixo Eletrônico. Para obter mais informações, consulte [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Use as listas de remetentes bloqueados** disponíveis : Para obter informações, consulte [Create blocked sender lists](create-block-sender-lists-in-office-365.md).

- **Cancelar assinatura de email em massa** Se a mensagem foi algo para o que o usuário se inscreveu (boletins informativos, comunicados de produto, etc.) e contém um link de cancelamento de assinatura de uma fonte confiável, considere pedir que eles simplesmente cancelem a assinatura.

- EOP autônomo: crie regras de fluxo de emails no Exchange local para vereditos de filtragem de spam do **EOP**: em ambientes EOP autônomos em que o EOP protege caixas de correio locais do Exchange, você precisa configurar regras de fluxo de emails (também conhecidas como regras de transporte) no Exchange local para traduzir o veredito de filtragem de spam do EOP para que a regra de lixo eletrônico possa mover a mensagem para a pasta Lixo Eletrônico. Para obter detalhes, confira [Configurar a EOP autônoma para enviar spam à pasta Lixo Eletrônico em ambientes híbridos](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

### <a name="prevent-good-email-from-being-identified-as-spam"></a>Impedir que um bom email seja identificado como spam

Aqui estão algumas etapas que você pode seguir para ajudar a evitar falsos positivos:

- **Verifique as configurações do Filtro de Lixo** Eletrônico do Outlook do usuário:

  - **Verifique se o Filtro de Lixo** Eletrônico do Outlook está desabilitado : Quando o Filtro de Lixo Eletrônico do Outlook é definido como o valor padrão **Sem** filtragem automática, o Outlook não tenta classificar as massagens como spam.  Quando definido como **Baixo** ou **Alto,** o Filtro de Lixo Eletrônico do Outlook usa sua própria tecnologia de filtro SmartScreen para identificar e mover spam para a pasta Lixo Eletrônico, para que você possa obter falsos positivos. Observe que a Microsoft parou de produzir atualizações de definição de spam para os filtros SmartScreen no Exchange e no Outlook em novembro de 2016. As definições de spam do SmartScreen existentes foram deixadas no lugar, mas sua eficácia provavelmente se degrada com o tempo.

  - Verifique se a configuração **Do Outlook "Somente** Listas Seguras" está desabilitada : Quando essa configuração estiver habilitada, somente as mensagens dos destinatários na lista de Destinatários Seguros ou na Lista de Destinatários Seguros do usuário serão entregues na Caixa de Entrada; o email de todos os outros é movido automaticamente para a pasta Lixo Eletrônico.

  Para obter mais informações sobre essas configurações, consulte [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Use as listas de remetentes** seguros disponíveis : Para obter informações, consulte [Create safe sender lists](create-safe-sender-lists-in-office-365.md).

- **Verifique se os usuários estão dentro dos** limites de envio e recebimento, conforme descrito em Recebimento e envio [de](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits) limites na descrição do serviço do Exchange Online.

- **EOP autônomo:** use a sincronização de diretórios : se você usar o EOP autônomo para ajudar a proteger sua organização local do Exchange, você deve sincronizar as configurações do usuário com o serviço usando a sincronização de diretórios. Isso garante que as listas de Remetentes confiáveis dos seus usuários sejam respeitadas pelo EOP. Para obter mais informações, consulte [Usar a sincronização de diretório para gerenciar usuários de e-mail](manage-mail-users-in-eop.md#use-directory-synchronization-to-manage-mail-users).

## <a name="anti-spam-legislation"></a>Legislação anti-spam

Na Microsoft, acreditamos que o desenvolvimento de novas tecnologias e a autorregulação exigem o suporte de políticas governamentais e estruturas legais eficazes. A proliferação de spam em todo o mundo estimulou vários órgãos legislativos a regular emails comerciais. Muitos países agora têm leis de combate a spam. Os Estados Unidos têm leis federais e estaduais que regem o spam, e essa abordagem complementar está ajudando a reduzir o spam enquanto permite que o comércio eletrônico legítimo prospere. A Lei CAN-SPAM expande as ferramentas disponíveis para restringir mensagens de email fraudulentas e ilusórias.