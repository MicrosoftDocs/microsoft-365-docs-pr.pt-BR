---
title: Bloquear spam no EOP autônomo
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
ms.reviewer: andypunt
manager: dansimp
ms.date: 2/25/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: da21c0b6-e8f0-4cc8-af2e-5029a9433d59
ms.collection:
- M365-security-compliance
description: Aprenda a configurar o filtro antispam do Office 365 para bloquear spam de e-mail e impedir mensagens falsas negativas.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 16bb5530384dba360483eba3a8e05fbfdf3fe895
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035575"
---
# <a name="customize-the-anti-spam-filter-with-these-settings"></a>Personalizar o filtro antispam com estas configurações

O administrador pode usar várias configurações de filtro de spam para ajudar a impedir o envio de spam para a caixa de entrada de um usuário. Use as opções listadas aqui para melhorar o filtro de spam e evitar mensagens de falso negativo. Nesse contexto, um falso negativo se refere a mensagens de spam ou lixo eletrônico enviadas para a caixa de entrada de um usuário.

## <a name="block-ip-addresses-with-a-connection-filter"></a>Bloquear um endereço IP com um filtro de conexão

Personalize o filtro de spam adicionando o endereço IP do remetente à lista de bloqueio de IP do filtro de conexão:

1. Obtenha os cabeçalhos da mensagem que você deseja bloquear em seu cliente de email, como o Outlook ou o Outlook na Web (anteriormente conhecido como Outlook Web App), conforme descrito em [Exibir cabeçalhos de mensagens da Internet no Outlook](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c).

2. Procure o endereço IP após a marca CIP no cabeçalho X-Forefront-Antispam-Report usando o [Analisador de cabeçalho de mensagem](https://testconnectivity.microsoft.com/?tabid=mha) ou manualmente.

3. Adicione o endereço IP à Lista de IP Bloqueados executando as etapas em "Usar o EAC para editar a política de filtro de conexão padrão" em [Configurar a política de filtro de conexão](configure-the-connection-filter-policy.md).

### <a name="block-bulk-mail-with-mail-flow-rules-transport-rules-or-the-spam-filter"></a>Bloquear emails em massa com regras de fluxo de emails (também conhecida como regras de transporte) ou filtro de spam

O spam é, em sua maioria, correio em massa, por exemplo, boletins ou promoções? Você pode personalizar o filtro de spam se [Usar regras de fluxo de e-mail para configurar a filtragem de e-mail em massa](use-transport-rules-to-configure-bulk-email-filtering.md) ou ativar a **Configuração de email** em massa nas configurações de [Filtro de spam avançado (ASF) do filtro de spam no Office 365](advanced-spam-filtering-asf-options.md). No centro de administração do Exchange, clique em **Filtro de** \> **conteúdo de proteção** e clique duas vezes na política de filtro que deseja ajustar. Clique em **Ações de spam e e-mail em massa** para ajustar as configurações, como mostrado aqui.

![Definir o filtro de email em massa no Exchange Online](../../media/a45095c2-269d-45b8-a76c-999b5e78da68.png)

### <a name="block-email-spam-using-spam-filter-block-lists"></a>Bloquear spam usando listas de bloqueio de filtro de spam

[Configure suas políticas anti-spam no Office 365](configure-your-spam-filter-policies.md) para adicionar o endereço do remetente à lista de remetentes bloqueados ou domínio à lista de domínios bloqueados no filtro de spam. Os e-mails de um remetente ou domínio em uma lista de bloqueio de filtro de spam serão marcados como spam.

## <a name="email-users-can-also-help-ensure-that-false-negative-and-email-spam-is-blocked-with-spam-filter"></a>Os usuários de email também podem ajudar a garantir que os falsos negativos e spams sejam bloqueados com o filtro de spam

Será útil para os seus esforços anti-spam para prevenir falsos negativos e lixo eletrônico se você pedir aos seus usuários para adicionar o endereço do remetente do spam à lista de remetentes bloqueados no [Outlook](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) ou no [Outlook na Web](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d). No Outlook na web, comece clicando em **Configurações** \> **Opções** \> **Bloquear ou permitir** e adicione o endereço à lista de **Remetentes bloqueados**, conforme mostrado aqui.

![Bloquear um remetente no Outlook na web](../../media/fdf51381-2527-4819-ac2a-5dff84d2a36d.png)

> [!NOTE]
> Para obter informações mais detalhadas das listas de remetentes seguros, consulte [Criar listas de remetentes seguros no Office 365.](create-safe-sender-lists-in-office-365.md).

## <a name="eop-only-customers-set-up-directory-synchronization"></a>Clientes somente EOP: configurar a sincronização de diretório

Isso o ajudará a evitar os emails marcados incorretamente como spam se você sincronizar as configurações de usuário com o serviço por meio da sincronização de diretórios, a fim de garantir que os remetentes bloqueados sejam respeitados. Para saber mais, consulte "Usar a sincronização de diretórios para gerenciar usuários de email" em Gerenciar usuários de email no EOP.

## <a name="eop-only-customers-who-are-not-using-directory-synchronization"></a>Clientes somente de EOP que não estão usando a sincronização de diretórios

O serviço do EOP foi projetado para respeitar os remetentes confiáveis e bloqueados do usuário, se as informações tiverem sido compartilhadas com o serviço. Se você é um cliente de EOP que usa o Outlook, mas não tem a sincronização de diretórios configurada para sincronizar seus usuários no Office 365, ainda é possível impedir a entrega das mensagens na caixa de entrada dos usuários usando remetentes bloqueados. No entanto, talvez seja necessário configurar algumas regras de fluxo de email do Exchange nas seguintes situações:

- Se uma mensagem passar pela filtragem de spam normal no EOP e, em seguida, for entregue a um servidor local do Exchange e o EOP atribuir um veredito de spam SCL 1-4 (não spam), a lista local de remetentes bloqueados dos usuários substituirá o veredito do filtro de spam do EOP e a entregará à sua pasta Lixo Eletrônico.

- Se uma mensagem no EOP recebe um SCL -1 de uma regra de fluxo de email do Exchange, ou porque o endereço IP ou domínio está em sua lista de permissões, o SCL será propagado para o servidor local do Exchange usando conectores. Nesse caso, a lista de remetentes bloqueados do usuário não será aplicada. Para alterar isso, crie uma regra de fluxo de email local que define o SCL como 0. Isso fará com que o Outlook aplique a lista de remetentes bloqueados do local do usuário.

### <a name="to-set-up-a-mail-flow-rule-to-stop-messages-from-being-delivered-to-your-users-inbox-by-using-the-blocked-senders-list"></a>Para configurar uma regra de fluxo de email para impedir que as mensagens sejam entregues na caixa de entrada dos usuários usando a lista de remetentes bloqueados

1. Abra o Shell de Gerenciamento do Exchange em seu servidor local. Para saber como abrir o Shell em sua organização local do Exchange, consulte [Abrir o Shell de Gerenciamento do Exchange](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell).

2. Execute o comando a seguir para encaminhar mensagens de spam com conteúdo filtrado para a pasta Lixo Eletrônico a fim de atualizar o SCL em toda mensagem marcada com SCL -1:

   ```powershell
   New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SCL:-1" -SetSCL 0
   ```

   Como o SCL é 0 em seu servidor local do Exchange, mensagens marcadas como não sendo spam serão entregues às caixas de entrada dos usuários, mas ainda poderão ser enviadas para o lixo eletrônico pela lista de remetentes bloqueados local dos usuários. Se você estiver usando a quarentena de spam no EOP, ainda será possível que os remetentes na lista de confiança do usuário sejam identificados como spam e enviados para quarentena. Se você estiver usando a pasta Lixo Eletrônico na caixa de correio local, isso permitirá a entrega de mensagens de remetentes confiáveis na Caixa de Entrada.

> [!WARNING]
> Se você usar uma regra de fluxo de email para alterar o valor do SCL para 0 (ou para qualquer valor diferente de -1), todas as opções de lixo eletrônico do Outlook serão aplicadas à mensagem. Isso significa que as listas confiáveis e bloqueadas serão cumpridas, mas também significa que as mensagens que não têm endereços nas listas bloqueadas ou confiáveis serão possivelmente marcadas como lixo eletrônico pelo processamento do filtro de lixo eletrônico no lado do cliente. Se você quiser que o Outlook processe as listas bloqueadas e confiáveis, mas não use o filtro de lixo eletrônico no lado do cliente, defina a opção "Sem Filtragem Automática" nas Opções de Lixo Eletrônico do Outlook. "Sem Filtragem Automática" é a opção padrão nas versões mais recentes do Outlook, mas você deve confirmar se essa configuração está presente, a fim de garantir que o filtro de lixo eletrônico do lado do cliente não seja aplicado às mensagens. Como administrador, você pode impor a desativação da filtragem de Lixo Eletrônico do Outlook seguindo as instruções em [Outlook: configuração de política para desativar a IU de lixo eletrônico e o mecanismo de filtragem](https://support.microsoft.com/kb/2180568).

## <a name="see-also"></a>Confira também

[Proteção Anti-spam de E-mails da Microsoft](anti-spam-protection.md)

[Impedir falsos positivos marcados como spam usando uma lista confiável ou outras técnicas](prevent-email-from-being-marked-as-spam.md)
