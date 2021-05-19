---
title: Configurar seu serviço EOP autônomo
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
ms.assetid: d74c6ddf-11b0-43ee-b298-8bb0340895f0
description: Os administradores podem aprender a configurar o Proteção do Exchange Online autônomo (EOP) para proteger ambientes de email locais.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 63504dd2d729674fd84eff2fd5548c8d077cd1f1
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538970"
---
# <a name="set-up-your-standalone-eop-service"></a>Configurar seu serviço EOP autônomo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
-  [Proteção do Exchange Online autônomo](exchange-online-protection-overview.md)

Este tópico explica como configurar o EOP (Proteção do Exchange Online autônomo). Se você foi direcionado do Assistente de domínios do Office 365, volte para o Assistente de domínios do Office 365 se você não quiser usar o Proteção do Exchange Online. Se você quiser mais informações sobre como configurar conectores, confira [Configure mail flow using connectors in Office 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

> [!NOTE]
> Este tópico assume que você tenha caixas de correio locais e que você queira protegê-las com a EOP, o que é conhecido como cenário autônomo. Se você deseja hospedar todas as suas caixas de correio na nuvem com Exchange Online, não precisa concluir todas as etapas deste artigo. Vá para [Comparar Exchange Online planos para](https://products.office.com/exchange/compare-microsoft-exchange-online-plans) se inscrever e comprar caixas de correio de nuvem.
>
> Se você quiser hospedar algumas de suas caixas de correio no local e algumas na nuvem, isso se chama cenário híbrido. Ele requer configurações de fluxo de email mais avançadas. [Exchange Server implantações híbridas](/exchange/exchange-hybrid) explicam o fluxo de emails híbridos e têm links para recursos que mostram como defini-lo.

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Tempo estimado para a conclusão da tarefa: 1 hora

- Você precisa ter permissões atribuídas Proteção do Exchange Online antes de poder fazer os procedimentos neste artigo. Especificamente, você precisa da função **Domínios Remotos e Aceitos,** que é atribuída ao Gerenciamento da Organização **(administradores** globais) e grupos de função de administrador de email **Flow** por padrão. Para obter mais informações, consulte [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Se você ainda não se inscreveu na EOP, visite [Proteção do Exchange Online](https://products.office.com/exchange/exchange-email-security-spam-protection) para comprar ou experimentar o serviço.

- Para obter informações sobre atalhos de teclado que podem ser aplicados aos procedimentos deste artigo, consulte [Atalhos](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)de teclado para o centro de administração Exchange no Exchange Online .

> [!TIP]
> Está com problemas? Peça ajuda no fórum [Proteção do Exchange Online](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE).

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>Etapa 1: usar o Microsoft 365 de administração para adicionar e verificar seu domínio

1. No centro [Microsoft 365 de administração](../../admin/admin-overview/about-the-admin-center.md), vá para **Instalação** para adicionar seu domínio ao serviço.

2. Siga as etapas para adicionar os registros DNS aplicáveis ao seu provedor de hospedagem de DNS, a fim de verificar a propriedade do domínio.

> [!TIP]
> [Adicione um domínio](../../admin/setup/add-domain.md) ao Office 365 e Crie registros DNS em qualquer provedor de hospedagem [DNS](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) para Office 365 são recursos úteis para fazer referência à medida que você adiciona seu domínio ao serviço e configura o DNS.

## <a name="step-2-add-recipients-and-optionally-enable-dbeb"></a>Etapa 2: Adicionar destinatários e, opcionalmente, habilitar o DBEB

Antes de configurar seu email para entrar e sair do serviço da EOP, recomendamos que adicione seus destinatários ao serviço. Existem várias maneiras de fazer isso, conforme documentado no [Gerenciar usuários de email no EOP](manage-mail-users-in-eop.md). Se desejar habilitar o Bloqueio de Borda Baseado em Diretório (DBEB) para impor a verificação de destinatário dentro do serviço após adicionar seus destinatários, deverá configurar o tipo do seu domínio para Autoritativo. Para obter mais informações sobre o DBEB, consulte [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>Etapa 3: Usar o EAC para configurar o fluxo de emails

Crie conectores no EAC (Centro de administração do Exchange) que permitem o fluxo de emails entre a EOP e os servidores de email locais. Para obter instruções [detalhadas, consulte Set up connectors to route mail between Microsoft 365 and your own email servers](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail).

### <a name="how-do-you-know-this-worked"></a>Como saber se funcionou?

Verifique o fluxo de emails entre o serviço e seu ambiente. Para obter mais informações, consulte [Test mail flow by validting your Microsoft 365 connectors](/exchange/mail-flow-best-practices/test-mail-flow).

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>Etapa 4: Permitir acesso SMTP através da porta de entrada 25

Depois de configurar conectores, aguarde 72 horas para permitir a propagação das atualizações do registro DNS. Depois, restrinja o tráfego SMTP da porta de entrada 25 no seu firewall ou servidores de mensagens para aceitar mensagens apenas de datacenters da EOP, especificamente dos endereços de IP listados em [Endereços de IP do Exchange Online Protection](../../enterprise/urls-and-ip-address-ranges.md). Isso protege seu ambiente local limitando o escopo de mensagens de entrada que você pode receber. Além disso, atualize também quaisquer configurações em seu servidor de mensagens que controlam os endereços IP que podem se conectar para retransmitir mensagens.

> [!TIP]
> Configure o servidor SMTP com um tempo limite de conexão de 60 segundos. Essa configuração é aceitável para a maioria das situações, permitindo algum atraso no caso de uma mensagem enviada com um anexo grande, por exemplo.

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Etapa 5: garantir que o spam seja roteado para a pasta Lixo Eletrônico de cada usuário

Para garantir que o spam (lixo eletrônico) é roteado corretamente para a pasta de Lixo Eletrônico de cada usuário, é necessário realizar alguns passos de configuração. As etapas são fornecidas em [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

Se você não quiser mover mensagens para a pasta Lixo Eletrônico de cada usuário, poderá escolher outra ação editando suas políticas anti-spam. Para obter mais informações, consulte [Configure as políticas de anti-spam no Office 365](configure-your-spam-filter-policies.md).

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>Etapa 6: usar o centro de administração Microsoft 365 para apontar seu registro MX para o EOP

Siga as etapas de configuração de domínio para atualizar seu registro MX para seu domínio, para que seu email de entrada flua através do EOP. Certifique-se de apontar seu registro MX diretamente para a EOP em vez de ter um serviço de filtragem de terceiros relacionado ao email para a EOP. Para saber mais, você pode consultar novamente [Criar registros DNS para o Office 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).

> [!NOTE]
> Se você deve apontar seu registro MX para outro servidor ou serviço que fique na frente do EOP, consulte [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

### <a name="how-do-you-know-this-task-worked"></a>Como saber se essa tarefa funcionou?

Neste ponto, você já verificou se o conector de saída local da entrega de serviço está corretamente configurado bem como se o seu registro MX está apontando para a EOP. Agora, você pode optar por executar os seguintes testes adicionais para verificar se um email será entregue com êxito pelo serviço para o seu ambiente local:

- Verifique o fluxo de emails entre o serviço e seu ambiente. Para obter mais informações, consulte [Test mail flow by validting your Microsoft 365 connectors](/exchange/mail-flow-best-practices/test-mail-flow).

- Envie uma mensagem de email de qualquer conta de email baseado na Web para um destinatário de email de sua organização cujo domínio corresponde ao domínio que você adicionou ao serviço. Confirme a entrega da mensagem para a caixa de correio no local usando o Microsoft Outlook ou outro cliente de email.

- Se você deseja executar um teste de email enviado, envie uma mensagem de email de um usuário de sua organização para uma conta de email baseada na Web e confirme se a mensagem foi recebida.

> [!TIP]
> Quando você tiver concluído a configuração, não precisa executar etapas adicionais para fazer com que a EOP remova spam e malware. A EOP remove spam e malware automaticamente. No entanto, você pode ajustar suas configurações com base em seus requisitos de negócios. Para obter mais informações, consulte [Anti-spam e anti-malware protection in EOP](anti-spam-and-anti-malware-protection.md) and [Anti-phishing protection in Microsoft 365](anti-phishing-protection.md).
>
> Agora que seu serviço está em execução, recomendamos ler Práticas recomendadas para configurar [o EOP](best-practices-for-configuring-eop.md), que descreve as configurações e considerações recomendadas para depois de configurar o EOP.