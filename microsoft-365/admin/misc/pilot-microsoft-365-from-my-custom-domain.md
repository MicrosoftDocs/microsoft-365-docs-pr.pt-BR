---
title: Piloto do Microsoft 365 a partir do meu domínio personalizado
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365
ms.custom: ''
search.appverid:
- BCS160
- MET150
- MOE150
description: Aprenda a usar o recurso de email piloto do meu domínio personalizado para uma caixa de correio do Microsoft 365 usando apenas duas contas de teste.
ms.openlocfilehash: bfcb2bda4d560ab629ddebed88ac1d55e6224c05
ms.sourcegitcommit: 5f980a9eb5aca61cf3662ef0bc65dec215e21656
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/20/2020
ms.locfileid: "45186035"
---
# <a name="pilot-microsoft-365-from-my-custom-domain"></a>Piloto do Microsoft 365 a partir do meu domínio personalizado

Você pode usar o Microsoft 365 piloto com estes requisitos e limitações:

- Seu provedor de email atual deve fornecer encaminhamento de email.

- Você deve gerenciar seus registros DNS do Microsoft 365 em seu provedor de host DNS, em vez de ter o Microsoft 365 gerenciando esses registros para você.

    Para saber mais, confira [Adicionar registros DNS para conectar seu domínio](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

- As informações de disponibilidade para os usuários no outro servidor de email não estão disponíveis.

- Os administradores não podem administrar todas as contas de usuário a partir de um único local.

- Os usuários podem não conseguir usar a filtragem de spam do Microsoft 365.

## <a name="set-up-a-microsoft-365-pilot"></a>Configurar um piloto do Microsoft 365

Siga estas etapas para configurar um piloto do Microsoft 365:

### <a name="step-1-sign-in-to-the-microsoft-365-admin-center"></a>Etapa 1: Entre no centro de administração do Microsoft 365

1. Entre no [centro de administração do Microsoft 365](https://admin.microsoft.com) com sua conta corporativa ou de estudante.

2. No painel de navegação à esquerda, selecione **Configurações** > **Domínios**.

### <a name="step-2-verify-that-you-own-the-domain-you-want-to-use"></a>Etapa 2: Verifique se você é o proprietário do domínio que deseja usar.

1. Na página **Domínios**, selecione **Adicionar domínio**.

2. Digite o nome do domínio na caixa, selecione**Usar este domínio**, e então selecione **Continuar**.

3. Selecione os serviços que você deseja testar com seu domínio, como email e mensagens instantâneas.

5. Na página**Verificar domínio**, siga as instruções passo a passo, depois selecione **Verificar**.

    Leva entre alguns minutos e até 72 horas para que as alterações de DNS entrem em vigor.

    Você será solicitado a modificar seus registros de DNS quando a verificação for bem-sucedida.

### <a name="step-3-mark-the-domain-as-shared-in-exchange-online"></a>Etapa 3: Marque o domínio como compartilhado no Exchange Online

1. No centro de administração do Exchange, na seção **Fluxo de emails**, selecione **Domínios aceitos**e, em seguida, selecione o domínio que você deseja modificar.

2. Clique duas vezes para abrir a janela, e então selecione **Retransmissão Interna**. 

3. Selecione **Salvar**.

    Esta configuração pode exigir alguns minutos para entrar em vigor.

### <a name="step-4-unblock-the-existing-email-server-optional"></a>Etapa 4: Desbloqueie o servidor de email existente (opcional)

O Microsoft 365 usa a Proteção do Exchange Online (EOP) para a proteção contra spam. EOP pode bloquear o seu servidor de email existente se detectar um alto volume de spam sendo encaminhado pelo seu servidor de email atual. Se você confia na proteção contra spam do seu outro provedor de email, poderá desbloquear o servidor no Microsoft 365.

> [!NOTE]
> Desbloquear o seu servidor de email existente permite que qualquer spam recebido pelo seu servidor original chegue nas caixas de correio do Microsoft 365. Assim, você não poderá avaliar o quão bem a Microsoft 365 evita spam.

1. No painel de navegação do centro de administração do Exchange, selecione **Proteção** e, em seguida, selecione **Filtro de conexão**.

2. Na **Lista de IP Permitidos**, selecione**+**, e adicione o endereço IP do servidor de email do seu provedor de email atual. 

### <a name="step-5-create-user-accounts-and-set-the-primary-reply-to-address"></a>Etapa 5: Crie contas de usuário e definir o endereço principal para resposta 

1. No Centro de administração do Microsoft 365, barra de navegação à esquerda, selecione **Usuários** > **Usuários Ativos**.

2. Crie duas contas de teste adicionando dois usuários existentes.

    Para cada conta, selecione **+ Adicionar um usuário**, e preencha as informações necessárias, incluindo o método de senha que você deseja testar.

    Para garantir que o email de um usuário permaneça o mesmo, o campo ** Nome de usuário** deve corresponder ao endereço de email atual do usuário.

3. Escolha a licença apropriada, clique em **Avançar** e, em seguida clique em **Terminar de adicionar**. 

4. Ao lado de **Nome de usuário**, selecione seu nome de domínio personalizado na lista suspensa. 

5. Selecione **Criar** > **Fechar**.

### <a name="step-6-update-dns-records-at-your-dns-hosting-provider"></a>Etapa 6: Atualize os registros DNS em seu provedor de hospedagem DNS

Entre no site do seu provedor de hospedagem DNS e siga as instruções em [Adicionar registros DNS para conectar seu domínio](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

**Faça as duas exceções a seguir:**

- Não crie um novo registro MX ou altere seu registro MX existente.

- Se você já tiver um registro SPF (Sender Policy Framework) para o seu provedor de email anterior, em vez de criar um novo registro SPF (TXT) para o Exchange Online, adicione "include:spf.protection.outlook.com" ao registro TXT atual.

    Por exemplo, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".

    Se você não tiver um registro SPF, modifique o recomendado pela Microsoft 365 para incluir o domínio do seu provedor de email atual e, então, adicione spf.protection.outlook.com. Isso autoriza as mensagens de saída de ambos os sistemas de email.

### <a name="step-7-set-up-email-forwarding-at-your-current-provider"></a>Etapa 7: Configure o encaminhamento de email em seu provedor atual

No seu provedor de email atual, configure o encaminhamento de emails das contas dos usuários para o seu domínio onmicrosoft.com:

- Encaminhar a caixa de correio do Usuário A para usera@yourcompany.onmicrosoft.com

- Encaminhar a caixa de correio do Usuário B para userb@yourcompany.onmicrosoft.com

Quando você concluir esta etapa, todos os emails enviados para usera@yourcompany.com e userb@yourcompany.com estarão disponíveis no Microsoft 365.

> [!NOTE]
> Entre em contato com seu provedor de email atual para saber as etapas exatas para configurar o encaminhamento de emails.<br/>
> Não é necessário manter uma cópia das mensagens no provedor de email atual.<br/>
> A maioria dos provedores encaminham emails deixando o Endereço de resposta do remetente intacto, para que as respostas sejam encaminhadas para o remetente original.

### <a name="step-8-test-mail-flow"></a>Etapa 8: Teste o fluxo de emails

1. Entre no Outlook Web App usando as credenciais do Usuário A.

2. Realize estes testes:

    - Teste o email local da Microsoft enviando um email, por exemplo, para o usuário B. O email é entregue imediatamente. Neste cenário, a mensagem não é roteada para a caixa de correio do usuário B, no seu servidor original, porque a caixa de correio do Microsoft 365 é local.

    - Faça um teste enviando um email para um usuário do sistema de email existente, por exemplo, para o usuário C. O email é enviado para a caixa de correio do usuário C no seu servidor de email original.

    - Verifique se o encaminhamento está configurado corretamente a partir de conta externa ou de uma conta de email de funcionário no sistema de email existente. Por exemplo, a partir da conta do servidor original para o usuário C, ou uma conta do Hotmail, envie um email para o usuário A e verifique se chegará à caixa de correio do Microsoft 365 do usuário A.

### <a name="step-9-move-mailbox-contents"></a>Etapa 9: Mova o conteúdo da caixa de correio

Como você está movendo apenas dois usuários de teste, e o usuário A e o usuário B estão usando o Outlook, você pode mover o email abrindo o arquivo .PST antigo no novo perfil do Outlook e copiar as mensagens, os itens do calendário, os contatos e assim por diante. Para obter mais informações, confira [Importar emails, contatos e calendário de um arquivo .pst do Outlook](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac).

Depois de importá-los para os locais apropriados na caixa de correio do Microsoft 365, os itens podem ser acessados em qualquer dispositivo, em qualquer lugar.

Quando mais caixas de correio estiverem envolvidas ou se os funcionários não estiverem usando o Outlook, você poderá usar as ferramentas de migração disponíveis no centro de administração do Exchange. Para começar, vá para o centro de administração do Exchange e siga as instruções em [Migrar Email de um Servidor IMAP para as Caixas de Correio do Exchange Online - precisamos de um novo recurso de artigo].