---
title: Configurar seu serviço EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d74c6ddf-11b0-43ee-b298-8bb0340895f0
description: Este tópico explica como configurar a Proteção do Exchange Online (EOP) da Microsoft. Se você foi direcionado do Assistente de domínios do Office 365, volte para o Assistente de domínios do Office 365 se você não quiser usar o Proteção do Exchange Online. Se você quiser mais informações sobre como configurar conectores, confira Configure mail flow using connectors in Office 365.
ms.openlocfilehash: 135f3ce2d966c2c2918199f4680678031d9dc8d4
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598298"
---
# <a name="set-up-your-eop-service"></a>Configurar seu serviço EOP

Este tópico explica como configurar a Proteção do Exchange Online (EOP) da Microsoft. Se você foi direcionado do Assistente de domínios do Office 365, volte para o Assistente de domínios do Office 365 se você não quiser usar o Proteção do Exchange Online. Se você quiser mais informações sobre como configurar conectores, confira [Configure mail flow using connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

> [!NOTE]
> Este tópico assume que você tenha caixas de correio locais e que você queira protegê-las com a EOP, o que é conhecido como cenário autônomo. Se você deseja hospedar todas as suas caixas de correio na nuvem com o Exchange Online, não precisa concluir todas as etapas deste tópico. Vá para [comparar planos do Exchange Online](https://products.office.com/exchange/compare-microsoft-exchange-online-plans) para inscrever-se e comprar caixas de correio na nuvem. Se você quiser hospedar algumas de suas caixas de correio no local e algumas na nuvem, isso se chama cenário híbrido. Ele requer configurações de fluxo de email mais avançadas. As [implantações híbridas do Exchange Server](https://docs.microsoft.com/exchange/exchange-hybrid) explicam o fluxo de email híbrido e têm links para recursos que mostram como configurá-lo.

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Tempo estimado para a conclusão da tarefa: 1 hora

- Para configurar conectores, você precisa ter uma conta de administrador global do Office 365 ou de administrador da empresa do Exchange (grupo de funções do Gerenciamento de Organização). Para obter informações, consulte [Feature Permissions in EOP](feature-permissions-in-eop.md).

- Se você ainda não se inscreveu na EOP, visite [Proteção do Exchange Online](https://products.office.com/exchange/exchange-email-security-spam-protection) para comprar ou experimentar o serviço.

- Para obter informações sobre os atalhos de teclado que podem se aplicar aos procedimentos deste tópico, consulte [atalhos de teclado para o centro de administração do Exchange no Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Está com problemas? Peça ajuda no fórum do [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>Etapa 1: usar o centro de administração do Microsoft 365 para adicionar e verificar seu domínio

1. No [centro de administração do Microsoft 365](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center), vá para **configuração** para adicionar seu domínio ao serviço.

2. Siga as etapas para adicionar os registros DNS aplicáveis ao seu provedor de hospedagem de DNS, a fim de verificar a propriedade do domínio.

> [!TIP]
> [Adicionar um domínio ao office 365](https://docs.microsoft.com/office365/admin/setup/add-domain) e [criar registros DNS em qualquer provedor de Hospedagem de DNS para o Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) são recursos úteis para fazer referência à medida que você adiciona seu domínio ao serviço e configura o DNS.

## <a name="step-2-add-recipients-and-optionally-enable-dbeb"></a>Etapa 2: Adicionar destinatários e, opcionalmente, habilitar o DBEB

Antes de configurar seu email para entrar e sair do serviço da EOP, recomendamos que adicione seus destinatários ao serviço. Existem várias maneiras de fazer isso, conforme documentado no [Gerenciar usuários de email no EOP](manage-mail-users-in-eop.md). Se desejar habilitar o Bloqueio de Borda Baseado em Diretório (DBEB) para impor a verificação de destinatário dentro do serviço após adicionar seus destinatários, deverá configurar o tipo do seu domínio para Autoritativo. Para obter mais informações sobre o DBEB, consulte [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>Etapa 3: Usar o EAC para configurar o fluxo de emails

Crie conectores no EAC (Centro de administração do Exchange) que permitem o fluxo de emails entre a EOP e os servidores de email locais. Para saber mais detalhes, confira [Set up connectors to route mail between Office 365 and your own email servers](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail).

### <a name="how-do-you-know-this-task-worked"></a>Como saber se essa tarefa funcionou?

Verificar o fluxo de emails entre o serviço e seu ambiente. Para obter mais informações, consulte [testar o fluxo de emails Validando seus conectores do Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>Etapa 4: Permitir acesso SMTP através da porta de entrada 25

Após configurar os conectores, espere 72 horas para permitir a propagação das atualizações dos registros de DNS. Depois, restrinja o tráfego SMTP da porta de entrada 25 no seu firewall ou servidores de mensagens para aceitar mensagens apenas de datacenters da EOP, especificamente dos endereços de IP listados em [Endereços de IP do Exchange Online Protection](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges
). Isso protege seu ambiente local limitando o escopo de mensagens de entrada que você pode receber. Além disso, atualize também quaisquer configurações em seu servidor de mensagens que controlam os endereços IP que podem se conectar para retransmitir mensagens.

> [!TIP]
> Configure o servidor SMTP com um tempo limite de conexão de 60 segundos. Essa configuração é aceitável para a maioria das situações, permitindo um atraso no caso de uma mensagem enviada com um anexo grande, por exemplo.

## <a name="step-5-use-the-shell-to-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Etapa 5: Usar o Shell para se certificar que spam é roteado para a pasta de email de lixo eletrônico de cada usuário

Para garantir que o spam (lixo eletrônico) é roteado corretamente para a pasta de Lixo Eletrônico de cada usuário, é necessário realizar alguns passos de configuração. As etapas são fornecidas [para garantir que o spam seja roteado para a pasta lixo eletrônico de cada usuário](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

Se não quiser mover mensagens para a pasta de Lixo Eletrônico de cada usuário, você pode escolher outra ação editando suas políticas de filtro de conteúdo no centro de administração do Exchange. Para obter mais informações, consulte [Configurar suas políticas de filtro de spam](configure-your-spam-filter-policies.md).

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>Etapa 6: usar o centro de administração do Microsoft 365 para apontar o seu registro MX para o EOP

Siga as etapas de configuração de domínio do Office 365 para atualizar o registro MX do seu domínio, para que haja fluxo da EOP no seu email de entrada. Certifique-se de apontar seu registro MX diretamente para a EOP em vez de ter um serviço de filtragem de terceiros relacionado ao email para a EOP. Para saber mais, você pode consultar novamente [Criar registros DNS para o Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

### <a name="how-do-you-know-this-task-worked"></a>Como saber se essa tarefa funcionou?

Neste ponto, você já verificou se o conector de saída local da entrega de serviço está corretamente configurado bem como se o seu registro MX está apontando para a EOP. Agora, você pode optar por executar os seguintes testes adicionais para verificar se um email será entregue com êxito pelo serviço para o seu ambiente local:

- Verificar o fluxo de emails entre o serviço e seu ambiente. Para obter mais informações, consulte [testar o fluxo de emails Validando seus conectores do Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).

- Envie uma mensagem de email de qualquer conta de email baseado na Web para um destinatário de email de sua organização cujo domínio corresponde ao domínio que você adicionou ao serviço. Confirme a entrega da mensagem para a caixa de correio no local usando o Microsoft Outlook ou outro cliente de email.

- Se você deseja executar um teste de email enviado, envie uma mensagem de email de um usuário de sua organização para uma conta de email baseada na Web e confirme se a mensagem foi recebida.

> [!TIP]
> Quando você tiver concluído a configuração, não precisa executar etapas adicionais para fazer com que a EOP remova spam e malware. A EOP remove spam e malware automaticamente. No entanto, você pode ajustar as configurações na EAC de acordo com as necessidades da empresa. Para obter mais informações, consulte [anti-spam and Anti-Malware Protection in Office 365](anti-spam-and-anti-malware-protection.md). <br/><br/> Agora que o serviço está em execução, recomendamos ler [as práticas recomendadas para configurar o EOP](best-practices-for-configuring-eop.md), que descreve as configurações e as considerações recomendadas para depois de configurar o EOP.
