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
ms.service: O365-seccomp
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
ms.assetid: d74c6ddf-11b0-43ee-b298-8bb0340895f0
description: Os administradores podem aprender como configurar o proteção do Exchange Online (EOP) autônomo para proteger ambientes de email locais.
ms.openlocfilehash: ca95f7dce30e8e751e293bf4e5de9caf0c845d29
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760489"
---
# <a name="set-up-your-standalone-eop-service"></a>Configurar seu serviço EOP autônomo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Este tópico explica como configurar o proteção do Exchange Online autônomo (EOP). Se você foi direcionado do Assistente de domínios do Office 365, volte para o Assistente de domínios do Office 365 se você não quiser usar o Proteção do Exchange Online. Se você quiser mais informações sobre como configurar conectores, confira [Configure mail flow using connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

> [!NOTE]
> Este tópico assume que você tenha caixas de correio locais e que você queira protegê-las com a EOP, o que é conhecido como cenário autônomo. Se você deseja hospedar todas as suas caixas de correio na nuvem com o Exchange Online, não é necessário concluir todas as etapas neste artigo. Vá para [comparar planos do Exchange Online](https://products.office.com/exchange/compare-microsoft-exchange-online-plans) para inscrever-se e comprar caixas de correio na nuvem.
>
> Se você quiser hospedar algumas de suas caixas de correio no local e algumas na nuvem, isso se chama cenário híbrido. Ele requer configurações de fluxo de email mais avançadas. As [implantações híbridas do Exchange Server](https://docs.microsoft.com/exchange/exchange-hybrid) explicam o fluxo de email híbrido e têm links para recursos que mostram como configurá-lo.

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Tempo estimado para a conclusão da tarefa: 1 hora

- Você precisa receber permissões na proteção do Exchange Online antes de poder executar os procedimentos deste artigo. Especificamente, você precisa da função de **domínios remotos e aceitos** , que é atribuída aos grupos de funções **Gerenciamento de organização** (administradores globais) e **administrador de fluxo de emails** por padrão. Para obter mais informações, consulte [permissões em EOP autônomos](feature-permissions-in-eop.md) e [use o Eat modificar a lista de membros nos grupos de função](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Se você ainda não se inscreveu na EOP, visite [Proteção do Exchange Online](https://products.office.com/exchange/exchange-email-security-spam-protection) para comprar ou experimentar o serviço.

- Para obter informações sobre os atalhos de teclado que podem se aplicar aos procedimentos deste artigo, consulte [atalhos de teclado para o centro de administração do Exchange no Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Está com problemas? Peça ajuda no fórum [Proteção do Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=285351).

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>Etapa 1: usar o centro de administração do Microsoft 365 para adicionar e verificar seu domínio

1. No [centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/admin-overview/about-the-admin-center), vá para **configuração** para adicionar seu domínio ao serviço.

2. Siga as etapas para adicionar os registros DNS aplicáveis ao seu provedor de hospedagem de DNS, a fim de verificar a propriedade do domínio.

> [!TIP]
> [Adicionar um domínio ao office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) e [criar registros DNS em qualquer provedor de Hospedagem de DNS para o Office 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) são recursos úteis para fazer referência à medida que você adiciona seu domínio ao serviço e configura o DNS.

## <a name="step-2-add-recipients-and-optionally-enable-dbeb"></a>Etapa 2: Adicionar destinatários e, opcionalmente, habilitar o DBEB

Antes de configurar seu email para entrar e sair do serviço da EOP, recomendamos que adicione seus destinatários ao serviço. Existem várias maneiras de fazer isso, conforme documentado no [Gerenciar usuários de email no EOP](manage-mail-users-in-eop.md). Se desejar habilitar o Bloqueio de Borda Baseado em Diretório (DBEB) para impor a verificação de destinatário dentro do serviço após adicionar seus destinatários, deverá configurar o tipo do seu domínio para Autoritativo. Para obter mais informações sobre o DBEB, consulte [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>Etapa 3: Usar o EAC para configurar o fluxo de emails

Crie conectores no EAC (Centro de administração do Exchange) que permitem o fluxo de emails entre a EOP e os servidores de email locais. Para obter instruções detalhadas, consulte [set up Connectors to Route mail between Microsoft 365 e seus próprios servidores de email](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail).

### <a name="how-do-you-know-this-task-worked"></a>Como saber se essa tarefa funcionou?

Verificar o fluxo de emails entre o serviço e seu ambiente. Para obter mais informações, consulte [testar o fluxo de emails, Validando seus conectores do Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>Etapa 4: Permitir acesso SMTP através da porta de entrada 25

Depois de configurar os conectores, aguarde 72 horas para permitir a propagação de suas atualizações de registro DNS. Depois, restrinja o tráfego SMTP da porta de entrada 25 no seu firewall ou servidores de mensagens para aceitar mensagens apenas de datacenters da EOP, especificamente dos endereços de IP listados em [Endereços de IP do Exchange Online Protection](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges). Isso protege seu ambiente local limitando o escopo de mensagens de entrada que você pode receber. Além disso, atualize também quaisquer configurações em seu servidor de mensagens que controlam os endereços IP que podem se conectar para retransmitir mensagens.

> [!TIP]
> Configure o servidor SMTP com um tempo limite de conexão de 60 segundos. Essa configuração é aceitável para a maioria das situações, permitindo um atraso no caso de uma mensagem enviada com um anexo grande, por exemplo.

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Etapa 5: garantir que o spam seja roteado para a pasta de lixo eletrônico de cada usuário

Para garantir que o spam (lixo eletrônico) é roteado corretamente para a pasta de Lixo Eletrônico de cada usuário, é necessário realizar alguns passos de configuração. As etapas são fornecidas em [Configurar o EOP autônomo para fornecer spam para a pasta lixo eletrônico em ambientes híbridos](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

Se não quiser mover mensagens para a pasta de lixo eletrônico de cada usuário, você pode escolher outra ação editando suas políticas antispam. Para obter mais informações, consulte [Configure as políticas de anti-spam no Office 365](configure-your-spam-filter-policies.md).

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>Etapa 6: usar o centro de administração do Microsoft 365 para apontar o seu registro MX para o EOP

Siga as etapas de configuração do domínio para atualizar seu registro MX para o seu domínio, de forma que seus emails de entrada fluam pelo EOP. Certifique-se de apontar seu registro MX diretamente para a EOP em vez de ter um serviço de filtragem de terceiros relacionado ao email para a EOP. Para saber mais, você pode consultar novamente [Criar registros DNS para o Office 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

> [!NOTE]
> Se for necessário apontar o seu registro MX para outro servidor ou serviço que esteja na frente do EOP, confira [filtragem avançada para conectores no Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

### <a name="how-do-you-know-this-task-worked"></a>Como saber se essa tarefa funcionou?

Neste ponto, você já verificou se o conector de saída local da entrega de serviço está corretamente configurado bem como se o seu registro MX está apontando para a EOP. Agora, você pode optar por executar os seguintes testes adicionais para verificar se um email será entregue com êxito pelo serviço para o seu ambiente local:

- Verificar o fluxo de emails entre o serviço e seu ambiente. Para obter mais informações, consulte [testar o fluxo de emails, Validando seus conectores do Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).

- Envie uma mensagem de email de qualquer conta de email baseado na Web para um destinatário de email de sua organização cujo domínio corresponde ao domínio que você adicionou ao serviço. Confirme a entrega da mensagem para a caixa de correio no local usando o Microsoft Outlook ou outro cliente de email.

- Se você deseja executar um teste de email enviado, envie uma mensagem de email de um usuário de sua organização para uma conta de email baseada na Web e confirme se a mensagem foi recebida.

> [!TIP]
> Quando você tiver concluído a configuração, não precisa executar etapas adicionais para fazer com que a EOP remova spam e malware. A EOP remove spam e malware automaticamente. No entanto, você pode ajustar suas configurações com base em seus requisitos de negócios. Para obter mais informações, consulte [anti-spam and Anti-Malware Protection in Office 365](anti-spam-and-anti-malware-protection.md) e [Configure spoof Intelligence](learn-about-spoof-intelligence.md).
>
> Agora que o serviço está em execução, recomendamos ler [as práticas recomendadas para configurar o EOP](best-practices-for-configuring-eop.md), que descreve as configurações e as considerações recomendadas para depois de configurar o EOP.
