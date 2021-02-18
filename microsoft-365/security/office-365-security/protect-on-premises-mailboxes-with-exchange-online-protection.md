---
title: Proteger caixas de correio locais na China com o EOP autônomo
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
- GEU150
- GMA150
- GPA150
- MET150
ms.assetid: c5e95951-da67-4ec7-92c5-982abd477e69
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Os administradores na China que usam o Office 365 operado pela 21Vianet podem aprender a usar o Exchange Online Protection (EOP) autônomo para proteger suas caixas de correio locais.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f4f27fa9237d76422e936555c9872b83655d7b6b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289420"
---
# <a name="protect-on-premises-mailboxes-in-china-with-standalone-eop"></a>Proteger caixas de correio locais na China com o EOP autônomo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Este artigo se aplica somente ao Office 365 operado pela 21Vianet na China.

Mesmo que você planeje hospedar algumas ou todas as suas caixas de correio no local, ainda poderá proteger as caixas de correio com o Exchange Online Protection (EOP). Para configurar conectores, sua conta deve ser um administrador global ou um Administrador da Empresa do Exchange (o grupo de funções Gerenciamento da Organização). Para saber mais sobre como as permissões do Office 365 se relacionam com permissões do Exchange, confira Atribuir funções de administrador no [Office 365 operado pela 21Vianet.](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-21vianet&preserve-view=true) Se todas as suas caixas de correio do Exchange estão no local, siga estas etapas para configurar seu serviço EOP.

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>Etapa 1: Usar o centro de administração do Microsoft 365 para adicionar e verificar seu domínio

1. No centro de administração do Microsoft 365, navegue até a Instalação para adicionar seu domínio ao serviço.

2. Siga as etapas no portal para adicionar os registros DNS aplicáveis ao seu provedor de hospedagem de DNS para verificar a propriedade do domínio.

> [!TIP]
> Adicione seu domínio e usuários ao Office 365 operado pela [21Vianet](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain?view=o365-21vianet&preserve-view=true) e crie registros DNS para [o Office 365](https://docs.microsoft.com/microsoft-365/admin/services-in-china/create-dns-records-when-you-manage-your-dns-records?view=o365-21vianet&preserve-view=true) quando você gerencia seus registros DNS e são recursos úteis para fazer referência à medida que você adiciona seu domínio ao serviço e configura o DNS.

### <a name="step-2-add-recipients-and-configure-the-domain-type"></a>Etapa 2: Adicionar destinatários e configurar o tipo de domínio

Antes de configurar seu email para entrar e sair do serviço da EOP, recomendamos que adicione seus destinatários ao serviço. Existem várias maneiras de fazer isso, conforme documentado no [Gerenciar usuários de email no EOP](manage-mail-users-in-eop.md). Se desejar habilitar o Bloqueio de Borda Baseado em Diretório (DBEB) para impor a verificação de destinatário dentro do serviço após adicionar seus destinatários, deverá configurar o tipo do seu domínio para Autoritativo. Para obter mais informações sobre DBEB, consulte Usar Bloqueio de Borda Baseado em Diretório [para rejeitar mensagens enviadas a destinatários inválidos.](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>Etapa 3: Usar o EAC para configurar o fluxo de emails

Crie conectores no EAC (Centro de administração do Exchange) que permitem o fluxo de emails entre a EOP e os servidores de email locais. Para obter instruções detalhadas, confira [Configurar o fluxo de emails usando conectores no Office 365.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)

 Como saber se essa tarefa funcionou?

 Confira [Testar o fluxo de emails validando seus conectores do Office 365.](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>Etapa 4: Permitir acesso SMTP através da porta de entrada 25

Após configurar os conectores, espere 72 horas para permitir a propagação das atualizações dos registros de DNS. Depois disso, restrinja o tráfego SMTP de porta de entrada 25 em seu firewall ou servidores de email para aceitar emails somente dos datacenters do EOP, especificamente dos endereços IP listados em URLs e intervalos de endereços IP para [o Office 365.](../../enterprise/managing-office-365-endpoints.md) Isso protege seu ambiente local limitando o escopo de mensagens de entrada que você pode receber. Além disso, atualize também quaisquer configurações em seu servidor de mensagens que controlam os endereços IP que podem se conectar para retransmitir mensagens.

> [!TIP]
> Configure o servidor SMTP com um tempo limite de conexão de 60 segundos. Essa configuração é aceita na maioria das situações, o que fornece um pequeno atraso no caso de uma mensagem enviada com um anexo grande, por exemplo.

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Etapa 5: Certifique-se de que o spam seja roteado para a pasta Lixo Eletrônico de cada usuário

Para garantir que o spam (lixo eletrônico) é roteado corretamente para a pasta de Lixo Eletrônico de cada usuário, é necessário realizar alguns passos de configuração. As etapas são fornecidas em Configurar o EOP autônomo para entregar spam à pasta Lixo Eletrônico [em ambientes híbridos.](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md) Se você não quiser mover mensagens para a pasta Lixo Eletrônico de cada usuário, poderá escolher outra ação editando suas políticas anti-spam (também conhecidas como políticas de filtro de conteúdo). Para obter mais informações, consulte [Configure as políticas de anti-spam no Office 365](configure-your-spam-filter-policies.md).

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>Etapa 6: Usar o centro de administração do Microsoft 365 para apontar seu registro MX para o EOP

Siga as etapas de configuração de domínio do Office 365 para atualizar o registro MX do seu domínio, para que haja fluxo da EOP no seu email de entrada. Para obter mais informações, você pode referenciar novamente Criar registros DNS para [o Office 365 ao gerenciar seus registros DNS.](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider?view=o365-21vianet&preserve-view=true)

Como saber se essa tarefa funcionou?

 Confira [Testar o fluxo de emails validando seus conectores do Office 365.](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)

Neste ponto, você já verificou se o conector de saída local da entrega de serviço está corretamente configurado bem como se o seu registro MX está apontando para a EOP. Agora, você pode optar por executar os seguintes testes adicionais para verificar se um email será entregue com êxito pelo serviço para o seu ambiente local:

- No Analisador de Conectividade Remota, clique na guia **Office 365** e execute o teste **Email SMTP de Entrada** localizado em **Testes de Email da Internet**.

- Envie uma mensagem de email de qualquer conta de email baseado na Web para um destinatário de email de sua organização cujo domínio corresponde ao domínio que você adicionou ao serviço. Confirme a entrega da mensagem para a caixa de correio no local usando o Microsoft Outlook ou outro cliente de email.

- Se você deseja executar um teste de email enviado, envie uma mensagem de email de um usuário de sua organização para uma conta de email baseada na Web e confirme se a mensagem foi recebida.

## <a name="less-common-a-hybrid-setup-with-mailboxes-on-premises-and-in-the-cloud"></a>Menos comum: uma configuração híbrida com caixas de correio locais e na nuvem

Se você tiver caixas de correio do Exchange no local e uma ou mais caixas de correio na nuvem no Exchange Online, você terá uma configuração *híbrida.* Em uma configuração híbrida, recursos como compartilhamento de calendário de livre/ocupado e roteamento de email funcionam juntos em seus ambientes locais e na nuvem. Você pode ter uma configuração híbrida enquanto faz a transição de caixas de correio para o Exchange Online. Um ambiente híbrido é definido de forma diferente da proteção autônoma do EOP.

Você pode escolher um cenário híbrido para aproveitar os emails baseados em nuvem para a maioria dos seus funcionários. Você pode fazer isso enquanto também hospeda algumas caixas de correio no local; por exemplo, para seu departamento jurídico.

Uma configuração híbrida pode ser complexa, mas tem muitos benefícios. Para saber mais sobre como configurar cenários híbridos com o Exchange, consulte [Implantações híbridas do Exchange Server.](https://docs.microsoft.com/Exchange/exchange-hybrid)
