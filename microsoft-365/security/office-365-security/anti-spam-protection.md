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
description: Os administradores podem saber mais sobre as configurações e filtros anti-spam que ajudarão a evitar spam no Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2ae2c4f42d42c37f5b7a7df2b6c8306fd390b0af
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175854"
---
# <a name="anti-spam-protection-in-eop"></a>Proteção anti-spam no EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender para Office 365 plano 1 e plano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!NOTE]
> Este tópico destina-se a administradores. Para tópicos do usuário final, consulte [Visão geral do Filtro](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) de Lixo Eletrônico e saiba mais sobre lixo eletrônico e [phishing.](https://support.microsoft.com/office/86c1d76f-4d5a-4967-9647-35665dc17c31)

Nas organizações do Microsoft 365 com caixas de correio no Exchange Online ou em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, as mensagens de email são automaticamente protegidas contra spam (lixo eletrônico) pelo EOP.

O mapa de segurança de email da Microsoft envolve uma abordagem entre produtos incomparável. A tecnologia anti-spam e anti-phishing do EOP é aplicada em nossas plataformas de email para fornecer aos usuários as ferramentas e inovações anti-spam e anti-phishing mais recentes em toda a rede. O objetivo do EOP é oferecer um serviço de email abrangente e a ser possível que ajude a detectar e proteger os usuários contra lixo eletrônico, ameaças de email fraudulentas (phishing) e malware.

À medida que o uso de email cresce, o abuso de email também. O lixo eletrônico não monitorado pode fazer logon em caixas de entrada e redes, afetar a satisfação do usuário e dificultar a eficácia de comunicações legítimas por email. É por isso que a Microsoft continua investindo em tecnologias anti-spam. Resumindo, ele começa por conter e filtrar lixo eletrônico.

> [!TIP]
> As seguintes tecnologias anti-spam são úteis quando você deseja permitir ou bloquear mensagens com base no envelope da mensagem (por exemplo, o domínio do remetente ou o endereço IP de origem da mensagem). Para permitir ou bloquear mensagens com base na carga (por exemplo, URLs na mensagem ou arquivos anexados), você deve usar o portal de Lista de [Bloqueios/Permitir](tenant-allow-block-list.md)Locatários.

## <a name="anti-spam-technologies-in-eop"></a>Tecnologias anti-spam no EOP

Para ajudar a reduzir o lixo eletrônico, o EOP inclui proteção contra lixo eletrônico que usa tecnologias proprietárias de filtragem de spam para identificar e separar lixo eletrônico de emails legítimos. A filtragem de spam do EOP aprende com ameaças conhecidas de spam e phishing e comentários dos usuários de nossa plataforma de consumidor, Outlook.com. Os comentários contínuos dos usuários do EOP no programa de classificação de lixo eletrônico ajudam a garantir que as tecnologias EOP sejam continuamente treinados e melhorados.

As configurações anti-spam no EOP são feitas das seguintes tecnologias:

- Filtragem de **conexão:** identifica os servidores de origem de email bons e ruins logo no início da conexão de email de entrada por meio da Lista de Ip Allow, da Lista de Bloqueios de IP e da lista de confiança *(uma* lista dinâmica, mas não editável, de senders confiáveis mantida pela Microsoft). Você define essas configurações na política de filtro de conexão. Saiba mais em [Configurar filtragem de conexão.](configure-the-connection-filter-policy.md)

  > [!NOTE]
  > A inteligência contra spoof usa a filtragem de conexão para criar listas de autorização e bloqueio de envios que estão fazendo a spoofing do seu domínio de email. Para saber mais, confira Mais informações sobre a inteligência [contra spoof no Microsoft 365.](learn-about-spoof-intelligence.md)

- **Filtragem de** spam (filtragem de conteúdo) : O EOP usa os vereditos de filtragem de spam **Spam**, **Spam** de alta confiança, **Email** em massa, email de **phishing** e email de **phishing** de alta confiança para classificar mensagens. Você pode configurar as ações a tomar com base nesses vereditos e pode configurar as opções de notificação do usuário final para mensagens que foram colocadas em quarentena em vez de entregues. Para saber mais, confira [Configurar políticas anti-spam no Microsoft 365.](configure-your-spam-filter-policies.md)

  > [!NOTE]
  > Por padrão, a filtragem de spam está configurada para enviar mensagens marcadas como spam para a pasta Lixo Eletrônico do destinatário. No entanto, em ambientes híbridos em que o EOP protege caixas de correio locais do Exchange, você precisa configurar duas regras de fluxo de email (também conhecidas como regras de transporte) em sua organização local do Exchange para reconhecer os headers de spam do EOP que são adicionados às mensagens. Para obter detalhes, confira [Configurar a EOP autônoma para enviar spam à pasta Lixo Eletrônico em ambientes híbridos](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

- **Filtragem de spam** de saída: O EOP também verifica se os usuários não enviam spam, seja no conteúdo da mensagem de saída ou excedendo os limites de mensagens de saída. Para obter mais informações, [consulte Configurar a filtragem de spam de saída no Microsoft 365.](configure-the-outbound-spam-policy.md)

- **Inteligência contra spoof**: Para saber mais, confira mais sobre a inteligência [contra spoof no Microsoft 365.](learn-about-spoof-intelligence.md)

## <a name="manage-errors-in-spam-filtering"></a>Gerenciar erros na filtragem de spam

É possível que mensagens boas possam ser identificadas como spam (também conhecidas como falsos positivos) ou que o spam possa ser entregue à Caixa de Entrada. Você pode usar as sugestões nas seções a seguir para descobrir o que aconteceu e ajudar a impedir que isso aconteça no futuro.

Aqui estão algumas práticas recomendadas que se aplicam a qualquer um dos cenários:

- Sempre envie mensagens classificadas injustificadas para a Microsoft. Para mais informações, confira [Relatar mensagens e arquivos à Microsoft](report-junk-email-messages-to-microsoft.md).

- **Examine os headers de mensagem anti-spam:** esses valores vão dizer por que uma mensagem foi marcada como spam ou por que ignorou a filtragem de spam. Para obter mais informações, consulte [Cabeçalhos de mensagem antispam](anti-spam-message-headers.md).

- Aponte seu registro MX para o **Microsoft 365:** para que o EOP forneça a melhor proteção, sempre recomendamos que você envie emails para o Microsoft 365 primeiro. Para obter instruções, consulte [Criar registros DNS em qualquer provedor de hospedagem de DNS para o Microsoft 365.](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)

  Se o registro MX aponta para outro local (por exemplo, uma solução ou dispositivo anti-spam de terceiros), é difícil para o EOP fornecer filtragem de spam precisa. In this scenario, you need to configure Enhanced Filtering for connectors (also known as _skip listing_). Para obter instruções, consulte [Filtragem aprimorada para conectores no Exchange Online.](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

- **Use a autenticação** de email: se você possui um domínio de email, pode usar o DNS para ajudar a garantir que as mensagens de envios nesse domínio sejam legítimas. Para ajudar a evitar spam e spoofing indesejado no EOP, use todos os seguintes métodos de autenticação de email:

  - **SPF**: Sender Policy Framework verifica o endereço IP de origem da mensagem em relação ao proprietário do domínio de envio. Para obter uma introdução rápida ao SPF e configurá-lo rapidamente, consulte Configurar o SPF para ajudar a [evitar a spoofing.](set-up-spf-in-office-365-to-help-prevent-spoofing.md) Para compreender melhor como o Microsoft 365 usa a SPF, para solucionar problemas ou para implantações fora do padrão, como as implantações híbridas, comece com [Como o Microsoft 365 usa a estrutura de política do remetente (SPF) para evitar a falsificação](how-office-365-uses-spf-to-prevent-spoofing.md).

  - **DKIM**: DomainKeys Identified Mail adiciona uma assinatura digital ao header da mensagem de mensagens enviadas do seu domínio. Para saber mais, confira Usar DKIM para validar emails de saída [enviados de seu domínio personalizado no Microsoft 365.](use-dkim-to-validate-outbound-email.md)

  - **DMARC**: Autenticação, Relatórios e Conformidade de Mensagens baseada em domínio ajuda os sistemas de email de destino a determinar o que fazer com mensagens que não são bem-recebidas nas verificações do SPF ou do DKIM e fornece outro nível de confiança para seus parceiros de email. Para saber mais, confira [Usar o DMARC para validar emails no Microsoft 365.](use-dmarc-to-validate-email.md)

- Verifique **suas** configurações de email em massa: o limite de nível de conformidade em massa (BCL) que você configura nas políticas anti-spam determina se o email em massa (também conhecido como email _cinza)_ está marcado como spam. A configuração somente do PowerShell _MarkAsSpamBulkMail_ que está por padrão também contribui para os resultados. Para saber mais, confira [Configurar políticas anti-spam no Microsoft 365.](configure-your-spam-filter-policies.md)

### <a name="prevent-the-delivery-of-spam-to-the-inbox"></a>Impedir a entrega de spam na Caixa de Entrada

- **Verifique as configurações** da sua organização: tome cuidado com as configurações que permitem que as mensagens ignorem a filtragem de spam (por exemplo, se você adicionar seu próprio domínio à lista de domínios permitidos nas políticas anti-spam). Para nossas configurações recomendadas, consulte Configurações recomendadas para o EOP e o Microsoft Defender para segurança do [Office 365](recommended-settings-for-eop-and-office365-atp.md) e criar [listas de remetentes seguros.](create-safe-sender-lists-in-office-365.md)

- Verifique se a regra de lixo eletrônico está habilitada na caixa de correio do **usuário:** ela está habilitada por padrão, mas se estiver desabilitada, as mensagens marcadas como lixo eletrônico não podem ser movidas para a pasta Lixo Eletrônico. Para obter mais informações, consulte [Definir configurações de lixo eletrônico em caixas de correio do Exchange Online no Microsoft 365.](configure-junk-email-settings-on-exo-mailboxes.md)

- **Use as listas de remetentes bloqueados** disponíveis: Para obter informações, consulte [Criar listas de remetentes bloqueados.](create-block-sender-lists-in-office-365.md)

- **Cancelar assinatura de email em massa** Se a mensagem foi algo em que o usuário se inscreveu (boletins informativos, anúncios de produtos etc.) e contém um link de cancelamento de assinatura de uma fonte confiável, considere pedir que ele simplesmente cancele a assinatura.

- EOP autônomo: criar regras de fluxo de emails no Exchange local para vereditos de filtragem de spam do **EOP:** em ambientes EOP autônomos onde o EOP protege caixas de correio locais do Exchange, você precisa configurar regras de fluxo de email (também conhecidas como regras de transporte) no Exchange local para converter o veredito de filtragem de spam do EOP para que a regra de lixo eletrônico possa mover a mensagem para a pasta Lixo Eletrônico. Para obter detalhes, confira [Configurar a EOP autônoma para enviar spam à pasta Lixo Eletrônico em ambientes híbridos](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

### <a name="prevent-good-email-from-being-identified-as-spam"></a>Impedir que emails bons sejam identificados como spam

Aqui estão algumas etapas que você pode seguir para ajudar a evitar falsos positivos:

- **Verifique as configurações do Filtro de Lixo** Eletrônico do Outlook do usuário:

  - **Verifique se** o Filtro de Lixo Eletrônico do Outlook está desabilitado: quando o Filtro de Lixo Eletrônico do Outlook está definido como o valor padrão Nenhuma filtragem **automática,** o Outlook não tenta classificar os spams.  Quando definido como  Baixo ou Alto, o Filtro de Lixo Eletrônico do Outlook usa sua própria tecnologia de filtro SmartScreen para identificar e mover spam para a pasta Lixo Eletrônico, para que você possa obter falsos positivos. Observe que a Microsoft parou de produzir atualizações de definição de spam para os filtros SmartScreen no Exchange e no Outlook em novembro de 2016. As definições de spam do SmartScreen existentes foram deixadas em vigor, mas sua eficácia provavelmente será degradada ao longo do tempo.

  - Verifique se a configuração **"Somente** Listas Seguras" do Outlook está desabilitada: quando essa configuração está habilitada, somente as mensagens dos destinatários na lista de Destinatários Seguros ou na lista de Destinatários Seguros do usuário são entregues na Caixa de Entrada; os emails de todas as outras pessoas são movidos automaticamente para a pasta Lixo Eletrônico.

  Para obter mais informações sobre essas configurações, consulte Definir configurações de lixo eletrônico nas caixas de correio do [Exchange Online no Microsoft 365.](configure-junk-email-settings-on-exo-mailboxes.md)

- **Use as listas de remetentes seguros** disponíveis: Para obter informações, consulte [Criar listas de remetentes seguros.](create-safe-sender-lists-in-office-365.md)

- **Verifique se os usuários estão dentro dos limites de envio** e recebimento, conforme descrito nos limites de recebimento e [envio](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits) na descrição do serviço do Exchange Online.

- **EOP autônomo: use** a sincronização de diretórios: se você usar o EOP autônomo para ajudar a proteger sua organização local do Exchange, sincronize as configurações do usuário com o serviço usando a sincronização de diretórios. Isso garante que as listas de Remetentes confiáveis dos seus usuários sejam respeitadas pelo EOP. Para obter mais informações, consulte [Usar a sincronização de diretório para gerenciar usuários de e-mail](manage-mail-users-in-eop.md#use-directory-synchronization-to-manage-mail-users).

## <a name="anti-spam-legislation"></a>Legislação anti-spam

Na Microsoft, acreditamos que o desenvolvimento de novas tecnologias e auto-regulamentação exige o suporte de uma política governamental eficaz e estruturas legais. A proliferação de spam em todo o mundo tem várias pessoas competentes para regular o email comercial. Muitos países/reções agora têm leis contra spam no local. Os Estados Unidos têm leis federais e estaduais que regem spam, e essa abordagem complementar está ajudando a restringir o spam, permitindo que o comércio eletrônico legítimo seja legal. A Lei CAN-SPAM expande as ferramentas disponíveis para enviar mensagens de email fraudulentas e enganosas.
