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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender sobre as configurações e filtros antispam que ajudarão a evitar spam na proteção do Exchange Online (EOP).
ms.openlocfilehash: d7c58fd4751bc7d92d5dfa3cadcfb7b24a3fc465
ms.sourcegitcommit: 4cfb8a9c3675d0aefcabd690273e2af85f2e38b0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44211411"
---
# <a name="anti-spam-protection-in-eop"></a>Proteção antispam no EOP

> [!NOTE]
> Este tópico destina-se a administradores. Para os tópicos do usuário final, confira [visão geral do filtro de lixo eletrônico](https://support.Microsoft.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) e [saiba mais sobre lixo eletrônico e phishing](https://support.Microsoft.com/article/86c1d76f-4d5a-4967-9647-35665dc17c31).

Nas organizações do Microsoft 365 com caixas de correio em organizações do Exchange Online ou do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, as mensagens de email são automaticamente protegidas contra spam (lixo eletrônico) por EOP.

O mapa de segurança de email da Microsoft envolve uma abordagem de vários produtos sem correspondência. A tecnologia antispam e anti-phishing do EOP é aplicada em nossas plataformas de email para fornecer aos usuários as últimas ferramentas antispam e anti-phishing e as inovações em toda a rede. O objetivo do EOP é oferecer um serviço de email abrangente e útil que ajuda a detectar e proteger os usuários contra lixo eletrônico, ameaças de email fraudulentas (phishing) e malware.

Como o uso de email cresceu, isso tem abuso de email. O lixo eletrônico não monitorado pode obstruir as caixas de entrada e redes, impactar a satisfação do usuário e dificultar a eficácia de comunicações de email legítimas. É por isso que a Microsoft continua a investir em tecnologias antispam. Em suma, ele começa com a contém e filtra o lixo eletrônico.

## <a name="anti-spam-technologies-in-eop"></a>Tecnologias antispam no EOP

Para ajudar a reduzir o lixo eletrônico, o EOP inclui proteção de lixo eletrônico que usa tecnologias de filtragem de spam proprietárias para identificar e separar lixo eletrônico de emails legítimos. EOP filtragem de spam aprende de ameaças conhecidas contra spam e phishing e comentários de usuários da nossa plataforma de consumidores, Outlook.com. Comentários contínuos dos usuários do EOP no programa de classificação de lixo eletrônico ajuda a garantir que as tecnologias do EOP sejam continuamente treinadas e aprimoradas.

As configurações antispam no EOP são feitas das seguintes tecnologias:

- **Filtragem de conexão**: identifica servidores de origem de email bons e ruins no início da conexão de email de entrada por meio da lista de IPs permitidos, da lista de IPs bloqueados e da *lista segura* (uma lista dinâmica, mas não editável de remetentes confiáveis mantidos pela Microsoft). Você define essas configurações na política de filtro de conexão. Saiba mais em [Configurar filtragem de conexão](configure-the-connection-filter-policy.md).

  > [!NOTE]
  > O spoof Intelligence usa a filtragem de conexão para criar listas de permissões e bloqueios de remetentes que estão falsificando seu domínio de email. Para obter mais informações, consulte [saiba mais sobre o spoof Intelligence no Microsoft 365](learn-about-spoof-intelligence.md).

- **Filtragem de spam (filtragem de conteúdo)**: o EOP usa a filtragem de spam verdicts **spam**, **spam de alta confiança**, **email em massa**, **email de phishing** e email de **phishing de alta confiança** para classificar mensagens. É possível configurar as ações a serem executadas com base nesses verdicts, e você pode configurar as opções de notificação de usuário final para mensagens que foram colocadas em quarentena em vez de entregues. Para obter mais informações, consulte [Configure anti-spam Policies in Microsoft 365](configure-your-spam-filter-policies.md).

  > [!NOTE]
  > Por padrão, a filtragem de spam é configurada para enviar mensagens que foram marcadas como spam para a pasta lixo eletrônico do destinatário. No entanto, em ambientes híbridos onde o EOP protege as caixas de correio locais do Exchange, você precisa configurar duas regras de fluxo de emails (também conhecidas como regras de transporte) em sua organização do Exchange local para reconhecer os cabeçalhos de spam do EOP que são adicionados às mensagens. Para obter detalhes, confira [Configurar a EOP autônoma para enviar spam à pasta Lixo Eletrônico em ambientes híbridos](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

- **Filtragem de spam de saída**: o EOP também verifica se os usuários não enviam spam, seja no conteúdo da mensagem de saída ou excedem os limites de mensagens de saída. Para obter mais informações, consulte [Configure Outbound spam Filtering in Microsoft 365](configure-the-outbound-spam-policy.md).

- **Spoof Intelligence**: para obter mais informações, consulte [saiba mais sobre o spoof intelligence no Microsoft 365](learn-about-spoof-intelligence.md).

## <a name="manage-errors-in-spam-filtering"></a>Gerenciar erros na filtragem de spam

É possível que boas mensagens possam ser identificadas como spam (também conhecidos como falsos positivos) ou que o spam possa ser entregue na caixa de entrada. Você pode usar as sugestões nas seções a seguir para descobrir o que aconteceu e ajudar a evitar que isso aconteça no futuro.

Veja a seguir algumas práticas recomendadas que se aplicam a qualquer um dos cenários:

- Sempre envie mensagens incorretamente classificadas para a Microsoft. Para mais informações, confira [Relatar mensagens e arquivos à Microsoft](report-junk-email-messages-to-microsoft.md).

- **Examinar os cabeçalhos de mensagens**antispam: esses valores informarão por que uma mensagem foi marcada como spam ou por que ela ignorou a filtragem de spam. Para obter mais informações, consulte [Cabeçalhos de mensagem antispam](anti-spam-message-headers.md).

- **Aponte seu registro MX para a Microsoft 365**: para que o EOP forneça a melhor proteção, sempre recomendamos que você envie emails para a Microsoft 365 primeiro. Para obter instruções, consulte [criar registros DNS em qualquer provedor de Hospedagem de DNS para o Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

  Se o registro MX apontar para algum outro local (por exemplo, uma solução antispam de terceiros ou um dispositivo), é difícil para o EOP fornecer uma filtragem de spam precisa. Neste cenário, você precisa configurar a filtragem avançada para conectores (também conhecido como _lista de ignorados_). Para obter instruções, consulte [filtragem avançada para conectores no Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

- **Usar autenticação de email**: se você for um domínio de email, poderá usar o DNS para ajudar a garantir que as mensagens de remetentes desse domínio sejam legítimas. Para ajudar a evitar spam e falsificação indesejada no EOP, use todos os seguintes métodos de autenticação de email:

  - **SPF**: a estrutura da política do remetente verifica o endereço IP de origem da mensagem em relação ao proprietário do domínio de envio. Para obter uma breve introdução ao SPF e para configurá-lo rapidamente, consulte [Configurar o SPF para ajudar a evitar a falsificação](set-up-spf-in-office-365-to-help-prevent-spoofing.md). Para compreender melhor como o Microsoft 365 usa a SPF, para solucionar problemas ou para implantações fora do padrão, como as implantações híbridas, comece com [Como o Microsoft 365 usa a estrutura de política do remetente (SPF) para evitar a falsificação](how-office-365-uses-spf-to-prevent-spoofing.md).

  - **DKIM**: DomainKeys identificado mail adiciona uma assinatura digital ao cabeçalho da mensagem de mensagens enviadas do seu domínio. Para saber mais, confira [usar DKIM para validar emails de saída enviados do seu domínio personalizado no Microsoft 365](use-dkim-to-validate-outbound-email.md).

  - **DMARC**: autenticação, geração de relatórios e conformidade de mensagens baseadas em domínio ajuda os sistemas de email de destino a determinar o que fazer com as mensagens que falham no SPF ou no DKIM verifica e fornece outro nível de confiança para seus parceiros de email. Para obter mais informações, consulte [usar o DMARC para validar emails no Microsoft 365](use-dmarc-to-validate-email.md).

- **Verifique as configurações de email em massa**: o limite de nível de conformidade em massa (BCL) configurado em políticas antispam determina se o email em massa (também conhecido como _email cinza_) está marcado como spam. A configuração somente do PowerShell _MarkAsSpamBulkMail_ que está ativada por padrão também contribui para os resultados. Para obter mais informações, consulte [Configure anti-spam Policies in Microsoft 365](configure-your-spam-filter-policies.md).

### <a name="prevent-the-delivery-of-spam-to-the-inbox"></a>Impedir a entrega de spam para a caixa de entrada

- **Verifique suas configurações de organização**: Tome as configurações que permitem que as mensagens ignorem a filtragem de spam (por exemplo, se você adicionar seu próprio domínio à lista de domínios permitidos em políticas antispam). Para nossas configurações recomendadas, consulte [configurações recomendadas para o EOP e o Microsoft 365 ATP Security](recommended-settings-for-eop-and-office365-atp.md) e [criar listas de remetentes seguros](create-safe-sender-lists-in-office-365.md).

- **Verifique se a regra de lixo eletrônico está habilitada na caixa de correio do usuário**: ela está habilitada por padrão, mas se estiver desabilitada, as mensagens marcadas como lixo eletrônico não poderão ser movidas para a pasta lixo eletrônico. Para obter mais informações, consulte [Configurar definições de lixo eletrônico em caixas de correio do Exchange Online no Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Use as listas de remetentes bloqueados disponíveis**: para saber mais, confira [criar listas de remetentes bloqueados](create-block-sender-lists-in-office-365.md).

- **Cancelar assinatura de email em massa** Se a mensagem foi algo de que o usuário se inscreveu (boletins informativos, comunicados de produto etc.) e contém um link de cancelamento de assinatura de uma fonte respeitável, peça para que ele simplesmente cancele a assinatura.

- **EOP autônomo: criar regras de fluxo de emails no Exchange local para filtragem de spam do EOP verdicts**: em ambientes autônomos do EOP onde o EOP protege as caixas de correio locais do Exchange, você precisa configurar as regras de fluxo de emails (também conhecidas como regras de transporte) no Exchange local para traduzir os EOP de filtragem de spam do veredicto, de forma Para obter detalhes, confira [Configurar a EOP autônoma para enviar spam à pasta Lixo Eletrônico em ambientes híbridos](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

### <a name="prevent-good-email-from-being-identified-as-spam"></a>Impedir que bons emails sejam identificados como spam

Veja algumas etapas que você pode executar para ajudar a evitar positivos falsos:

- **Verifique as configurações do filtro de lixo eletrônico do Outlook do usuário**:

  - **Verifique se o filtro de lixo eletrônico do Outlook está desabilitado**: quando o filtro de lixo eletrônico do Outlook está definido como o valor padrão **sem filtragem automática**, o Outlook não tenta classificar massages como spam.  Quando ele é definido como **baixo** ou **alto**, o filtro de lixo eletrônico do Outlook usa sua própria tecnologia de Filtro SmartScreen para identificar e mover spam para a pasta lixo eletrônico, para que você possa obter falsos positivos. Observe que a Microsoft parou de produzir atualizações de definição de spam para os filtros SmartScreen no Exchange e no Outlook em novembro de 2016. As definições existentes de spam do SmartScreen foram deixadas no local, mas sua eficácia provavelmente será prejudicada ao longo do tempo.

  - **Verifique se a configuração ' somente listas de confiança ' do Outlook está desabilitada**: quando essa configuração está habilitada, somente as mensagens de remetentes na lista de remetentes confiáveis do usuário ou na lista de destinatários confiáveis são entregues na caixa de entrada; os emails de todas as outras pessoas são automaticamente movidos para a pasta lixo eletrônico.

  Para obter mais informações sobre essas configurações, consulte [definir configurações de lixo eletrônico em caixas de correio do Exchange Online no Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Use as listas de remetentes seguros disponíveis**: para saber mais, confira [criar listas de remetentes seguros](create-safe-sender-lists-in-office-365.md).

- **Verifique se os usuários estão dentro dos limites de envio e recebimento** , conforme descrito em [recebendo e enviando limites](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits) na descrição do serviço do Exchange Online.

- **EOP autônomo: usar a sincronização de diretórios**: se você usar o EOP autônomo para ajudar a proteger sua organização local do Exchange, você deve sincronizar as configurações de usuário com o serviço usando a sincronização de diretórios. Isso garante que as listas de Remetentes confiáveis dos seus usuários sejam respeitadas pelo EOP. Para obter mais informações, consulte [Usar a sincronização de diretório para gerenciar usuários de e-mail](manage-mail-users-in-eop.md#use-directory-synchronization-to-manage-mail-users).

## <a name="anti-spam-legislation"></a>Legislação antispam

Na Microsoft, acreditamos que o desenvolvimento de novas tecnologias e autoregulamentação requer o suporte da política governamental efetiva e estruturas legais. A proliferação mundial de spam tem spurred vários órgãos legislativos para regulamentar emails comerciais. Muitos países agora têm leis de combate de spam em vigor. Os Estados Unidos têm leis federais e estaduais que regem o spam, e essa abordagem complementar está ajudando a curtailr spam e, ao mesmo tempo, permitindo o e-commerce legítimo para o Prosper. O Act CAN-SPAM expande as ferramentas disponíveis para moderar mensagens de email fraudulentas e enganosas.
