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
description: Os administradores podem aprender a configurar o Exchange Online Protection (EOP) autônomo para proteger ambientes de email locais.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 42952259da4086c4e147fb1a69fc081659dcc7e2
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166202"
---
# <a name="set-up-your-standalone-eop-service"></a>Configurar seu serviço EOP autônomo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
-  [Proteção do Exchange Online autônoma](https://go.microsoft.com/fwlink/?linkid=2148611)

Este tópico explica como configurar o Exchange Online Protection (EOP) autônomo. Se você foi direcionado do Assistente de domínios do Office 365, volte para o Assistente de domínios do Office 365 se você não quiser usar o Proteção do Exchange Online. Se você quiser mais informações sobre como configurar conectores, confira [Configure mail flow using connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

> [!NOTE]
> Este tópico assume que você tenha caixas de correio locais e que você queira protegê-las com a EOP, o que é conhecido como cenário autônomo. Se você quiser hospedar todas as suas caixas de correio na nuvem com o Exchange Online, não será necessário concluir todas as etapas deste artigo. Vá para [Comparar planos do Exchange Online para](https://products.office.com/exchange/compare-microsoft-exchange-online-plans) se inscrever e comprar caixas de correio na nuvem.
>
> Se você quiser hospedar algumas de suas caixas de correio no local e algumas na nuvem, isso se chama cenário híbrido. Ele requer configurações de fluxo de email mais avançadas. [As implantações híbridas do Exchange Server](https://docs.microsoft.com/exchange/exchange-hybrid) explicam o fluxo de emails híbrido e têm links para recursos que mostram como configurar o email.

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Tempo estimado para a conclusão da tarefa: 1 hora

- Você precisa ter permissões no Exchange Online Protection antes de poder fazer os procedimentos neste artigo. Especificamente, você precisa da função Domínios Remotos e **Aceitos,** que é  atribuída aos grupos de função Gerenciamento da Organização **(administradores** globais) e Administrador de Fluxo de Emails por padrão. Para obter mais informações, [consulte Permissões no EOP](feature-permissions-in-eop.md) autônomo e use o EAC modificar a lista de [membros em grupos de função.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Se você ainda não se inscreveu na EOP, visite [Proteção do Exchange Online](https://products.office.com/exchange/exchange-email-security-spam-protection) para comprar ou experimentar o serviço.

- Para obter informações sobre atalhos de teclado que podem se aplicar aos procedimentos neste artigo, consulte [Atalhos](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)de teclado para o Centro de administração do Exchange no Exchange Online .

> [!TIP]
> Está com problemas? Peça ajuda no fórum [Proteção do Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=285351).

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>Etapa 1: Usar o Centro de administração do Microsoft 365 para adicionar e verificar seu domínio

1. No Centro [de administração do Microsoft 365,](https://docs.microsoft.com/microsoft-365/admin/admin-overview/about-the-admin-center)vá para a Instalação para adicionar seu domínio ao serviço. 

2. Siga as etapas para adicionar os registros DNS aplicáveis ao seu provedor de hospedagem de DNS, a fim de verificar a propriedade do domínio.

> [!TIP]
> Adicionar um domínio ao [Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) e criar registros DNS em qualquer provedor de hospedagem DNS para [o Office 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) são recursos úteis para fazer referência à medida que você adiciona seu domínio ao serviço e configura o DNS.

## <a name="step-2-add-recipients-and-optionally-enable-dbeb"></a>Etapa 2: Adicionar destinatários e, opcionalmente, habilitar o DBEB

Antes de configurar seu email para entrar e sair do serviço da EOP, recomendamos que adicione seus destinatários ao serviço. Existem várias maneiras de fazer isso, conforme documentado no [Gerenciar usuários de email no EOP](manage-mail-users-in-eop.md). Se desejar habilitar o Bloqueio de Borda Baseado em Diretório (DBEB) para impor a verificação de destinatário dentro do serviço após adicionar seus destinatários, deverá configurar o tipo do seu domínio para Autoritativo. Para obter mais informações sobre o DBEB, consulte [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>Etapa 3: Usar o EAC para configurar o fluxo de emails

Crie conectores no EAC (Centro de administração do Exchange) que permitem o fluxo de emails entre a EOP e os servidores de email locais. Para obter instruções detalhadas, confira Configurar conectores para [rotear emails entre o Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail)e seus próprios servidores de email.

### <a name="how-do-you-know-this-task-worked"></a>Como saber se essa tarefa funcionou?

Verifique o fluxo de emails entre o serviço e seu ambiente. Para saber mais, confira [Testar o fluxo de emails validando os conectores do Microsoft 365.](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>Etapa 4: Permitir acesso SMTP através da porta de entrada 25

Depois de configurar conectores, aguarde 72 horas para permitir a propagação de suas atualizações de registro DNS. Depois, restrinja o tráfego SMTP da porta de entrada 25 no seu firewall ou servidores de mensagens para aceitar mensagens apenas de datacenters da EOP, especificamente dos endereços de IP listados em [Endereços de IP do Exchange Online Protection](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges). Isso protege seu ambiente local limitando o escopo de mensagens de entrada que você pode receber. Além disso, atualize também quaisquer configurações em seu servidor de mensagens que controlam os endereços IP que podem se conectar para retransmitir mensagens.

> [!TIP]
> Configure o servidor SMTP com um tempo limite de conexão de 60 segundos. Essa configuração é aceitável para a maioria das situações, permitindo algum atraso no caso de uma mensagem enviada com um anexo grande, por exemplo.

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Etapa 5: Certifique-se de que o spam seja roteado para a pasta Lixo Eletrônico de cada usuário

Para garantir que o spam (lixo eletrônico) é roteado corretamente para a pasta de Lixo Eletrônico de cada usuário, é necessário realizar alguns passos de configuração. As etapas são fornecidas em Configurar o EOP autônomo para entregar spam à pasta Lixo Eletrônico [em ambientes híbridos.](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)

Se você não quiser mover mensagens para a pasta Lixo Eletrônico de cada usuário, poderá escolher outra ação editando suas políticas anti-spam. Para obter mais informações, consulte [Configure as políticas de anti-spam no Office 365](configure-your-spam-filter-policies.md).

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>Etapa 6: Usar o centro de administração do Microsoft 365 para apontar seu registro MX para o EOP

Siga as etapas de configuração de domínio para atualizar seu registro MX para seu domínio, para que seu email de entrada flua pelo EOP. Certifique-se de apontar seu registro MX diretamente para a EOP em vez de ter um serviço de filtragem de terceiros relacionado ao email para a EOP. Para saber mais, você pode consultar novamente [Criar registros DNS para o Office 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

> [!NOTE]
> Se você deve apontar seu registro MX para outro servidor ou serviço que fica na frente do EOP, consulte Filtragem aprimorada para conectores [no Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

### <a name="how-do-you-know-this-task-worked"></a>Como saber se essa tarefa funcionou?

Neste ponto, você já verificou se o conector de saída local da entrega de serviço está corretamente configurado bem como se o seu registro MX está apontando para a EOP. Agora, você pode optar por executar os seguintes testes adicionais para verificar se um email será entregue com êxito pelo serviço para o seu ambiente local:

- Verifique o fluxo de emails entre o serviço e seu ambiente. Para saber mais, confira [Testar o fluxo de emails validando os conectores do Microsoft 365.](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)

- Envie uma mensagem de email de qualquer conta de email baseado na Web para um destinatário de email de sua organização cujo domínio corresponde ao domínio que você adicionou ao serviço. Confirme a entrega da mensagem para a caixa de correio no local usando o Microsoft Outlook ou outro cliente de email.

- Se você deseja executar um teste de email enviado, envie uma mensagem de email de um usuário de sua organização para uma conta de email baseada na Web e confirme se a mensagem foi recebida.

> [!TIP]
> Quando você tiver concluído a configuração, não precisa executar etapas adicionais para fazer com que a EOP remova spam e malware. A EOP remove spam e malware automaticamente. No entanto, você pode ajustar suas configurações com base em seus requisitos de negócios. Para saber mais, confira [Proteção anti-spam e anti-malware no Office 365](anti-spam-and-anti-malware-protection.md) e configurar a inteligência contra [spoof.](learn-about-spoof-intelligence.md)
>
> Agora que seu serviço está em execução, recomendamos a leitura das práticas recomendadas para configurar o [EOP,](best-practices-for-configuring-eop.md)que descreve as configurações e considerações recomendadas para depois de configurar o EOP.
