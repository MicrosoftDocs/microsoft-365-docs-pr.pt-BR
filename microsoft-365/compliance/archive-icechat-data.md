---
title: Configurar um conector para arquivar dados de chat de gelo
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Os administradores podem configurar um conector para importar e arquivar dados da ferramenta de chat ICE para o Microsoft 365. Isso permite que você arquive dados de fontes de dados de terceiros no Microsoft 365 para que possa usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar os dados de terceiros da sua organização.
ms.openlocfilehash: cd56e98aadc2b7328b733939ecc8951413309ba5
ms.sourcegitcommit: ae3aa7f29be16d08950cf23cad489bc069aa8617
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48408761"
---
# <a name="set-up-a-connector-to-archive-ice-chat-data"></a>Configurar um conector para arquivar dados de chat de gelo

Use um conector nativo no centro de conformidade da Microsoft 365 para importar e arquivar dados de chat de serviços financeiros da ferramenta de colaboração de chat ICE. Após a configuração e a configuração de um conector, ele se conecta ao site de FTP seguro da sua organização uma vez a cada dia, converte o conteúdo de mensagens de chat em um formato de mensagem de email e, em seguida, importa esses itens para caixas de correio no Microsoft 365.

Depois que os dados de chat de gelo são armazenados nas caixas de correio do usuário, você pode aplicar recursos de conformidade da Microsoft 365, como retenção de litígio, descoberta eletrônica, arquivamento, auditoria, conformidade de comunicação e políticas de retenção da Microsoft 365 para dados de chat de gelo. Por exemplo, você pode pesquisar mensagens de chat de gelo usando a pesquisa de conteúdo ou associar a caixa de correio que contém os dados de chat de gelo a um funcionário em uma caixa de descoberta eletrônica avançada. O uso de um conector de chat de gelo para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a se manter em conformidade com as políticas governamentais e normativas.

## <a name="overview-of-archiving-ice-chat-data"></a>Visão geral dos dados de chat do ICE de arquivamento

A visão geral a seguir explica o processo de usar um conector para arquivar dados de chat de gelo no Microsoft 365.

![Fluxo de trabalho de arquivamento de chat ICE](../media/ICEChatConnectorWorkflow.png)

1. Sua organização trabalha com o chat ICE para configurar um site de bate-papo do ICE do gelo. Você também trabalhará com o chat ICE para configurar o bate-papo ICE para copiar mensagens de chat para seu site de chat do ICE.

2. Uma vez a cada 24 horas, as mensagens de bate-papo de gelo são copiadas para seu site de chat do ICE.

3. O conector de chat de gelo que você cria no centro de conformidade da Microsoft 365 conecta-se ao site do ICE do chat SFTP todos os dias e transfere as mensagens de chat das últimas 24 horas para um local seguro de armazenamento do Azure na nuvem da Microsoft. O conector também converte o conteúdo de um massage de chat em um formato de mensagem de email.

4. O conector importa itens de mensagem de chat para as caixas de correio de usuários específicos. Uma nova pasta chamada **chat de gelo** é criada nas caixas de correio do usuário e os itens da mensagem de chat são importados para essa pasta. O conector faz usando o valor das propriedades *SenderEmail* e *RecipientEmail* . Cada mensagem de chat contém essas propriedades, que são preenchidas com o endereço de email do remetente e todos os destinatários/participantes da mensagem de chat.

   Além do mapeamento automático de usuários que usa os valores da propriedade *SenderEmail* e *RecipientEmail* (o que significa que o conector importa uma mensagem de chat para a caixa de correio do remetente e as caixas de correio de cada destinatário), você também pode definir o mapeamento de usuários personalizados carregando um arquivo de mapeamento CSV. Este arquivo de mapeamento contém o *ImId* de bate-papo Ice e o endereço de caixa de correio do Microsoft 365 correspondente para todos os usuários da sua organização. Se você habilitar o mapeamento automático de usuários e fornecer um arquivo de mapeamento personalizado, para cada item de chat, o conector examinará primeiro o arquivo de mapeamento personalizado. Se não encontrar uma conta de usuário válida da Microsoft 365 que corresponda ao ImId de chat do gelo de um usuário, o conector usará as propriedades *SenderEmail* e *RecipientEmail* do item de chat para importar o item para as caixas de correio dos participantes do chat. Se o conector não localizar um usuário válido do Microsoft 365 no arquivo de mapeamento personalizado ou nas propriedades *SenderEmail* e *RecipientEmail* , o item não será importado.

## <a name="before-you-begin"></a>Antes de começar

Algumas das etapas de implementação necessárias para arquivar dados de chat de gelo são externas para o Microsoft 365 e devem ser concluídas para que você possa criar o conector no centro de conformidade.

- Sua organização deve dar o consentimento para permitir que o serviço de importação do Office 365 acesse dados de caixa de correio em sua organização. Para concordar com essa solicitação, [acesse esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), entre com as credenciais de um administrador global do Office 365 e aceite a solicitação. Você deve concluir esta etapa antes de poder criar com êxito o conector de chat ICE na etapa 3.

- O chat de gelo cobra de seus clientes uma taxa de conformidade externa. Sua organização deve entrar em contato com o grupo de vendas de chat de gelo para discutir e para assinar o contrato de serviços de dados de chat de gelo, que você pode obter em [https://www.theice.com/publicdocs/agreements/ICE\_Data\_Services\_Agreement.pdf](https://www.theice.com/publicdocs/agreements/ICE\_Data\_Services\_Agreement.pdf) . Este contrato é entre o chat de gelo e sua organização e não envolve a Microsoft. Depois de configurar um site de chat de gelo do ICE na etapa 2, o chat de gelo fornece as credenciais de FTP diretamente para sua organização. Em seguida, você deve fornecer essas credenciais à Microsoft ao configurar o conector na etapa 3.

- Você deve configurar um site de bate-papo SFTP do ICE antes de criar o conector na etapa 3. Depois de trabalhar com o chat ICE para configurar o site SFTP, os dados de um chat de gelo são carregados no site do SFTP todos os dias. O conector que você cria na etapa 3 se conecta a esse site SFTP e transfere os dados de chat para caixas de correio do Microsoft 365. O SFTP também criptografa os dados de chat de gelo enviados às caixas de correio durante o processo de transferência.

- O administrador que cria o conector de chat ICE na etapa 3 (e quem baixa as chaves públicas e o endereço IP na etapa 1) deve receber a função de exportação de importação de caixa de correio no Exchange Online. Essa função é necessária para adicionar conectores na página **conectores de dados** no centro de conformidade da Microsoft 365. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função de exportação de importação de caixa de correio ao grupo de funções Gerenciamento da organização no Exchange Online. Ou você pode criar um grupo de função, atribua a função de exportação de importação de caixa de correio e, em seguida, adicione os usuários apropriados como membros. Para obter mais informações, consulte as seções [criar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) ou [modificar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) no artigo "gerenciar grupos de função no Exchange Online".

## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>Etapa 1: obter as chaves públicas SSH e PGP

A primeira etapa é obter uma cópia das chaves públicas para SSH (Secure Shell) e PGP (boa privacidade). Você usa essas chaves na etapa 2 para configurar o site de chat do ICE para permitir que o conector (que você criou na etapa 3) se conecte ao site SFTP e transfira os dados de chat ICE para caixas de correio do Microsoft 365. Você também obterá um endereço IP nesta etapa, que você usará ao configurar o site do chat do ICE.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique em **conectores de dados** no painel de navegação esquerdo.

2. Na página **conectores de dados** , em **chat de gelo**, clique em **Exibir**.

3. Na página **chat Ice** , clique em **Adicionar conector**.

4. Na página **termos de serviço** , clique em **aceitar**.

5. Na página **Adicionar credenciais para o site de bate-papo do Ice** em etapa 1, clique na **chave de download SSH**, **baixar a chave PGP**e baixar links de **endereço IP** para salvar uma cópia de cada arquivo no computador local. Esses arquivos contêm os itens a seguir que são usados para configurar o site do chat do ICE na etapa 2:

   - Chave pública SSH: essa chave é usada para configurar o SSH seguro para habilitar um logon remoto seguro quando o conector se conecta ao site do chat do ICE SFTP.

   - Chave pública do PGP: essa chave é usada para configurar a criptografia de dados que são transferidos do site do chat do ICE para o Microsoft 365.

   - Endereço IP: o site de chat de gelo do ICE é configurado para aceitar uma solicitação de conexão apenas desse endereço IP, que é usado pelo conector de chat ICE que você cria na etapa 3.

6. Clique em **Cancelar** para fechar o assistente. Você volta para este assistente na etapa 3 para criar o conector.

## <a name="step-2-configure-the-ice-chat-sftp-site"></a>Etapa 2: configurar o site de chat do ICE do gelo

A próxima etapa é usar as chaves públicas SSH e PGP e o endereço IP obtido na etapa 1 para configurar a autenticação SSH e a criptografia PGP para o site do chat do ICE. Isso permite que o conector de chat que você criou na etapa 3 se conecte ao site de chat do ICE e transferir dados de chat ICE para o Microsoft 365. Você precisa trabalhar com o suporte ao cliente de chat de gelo para configurar seu site de chat do ICE.

## <a name="step-3-create-an-ice-chat-connector"></a>Etapa 3: criar um conector de chat ICE

A última etapa é criar um conector de chat de gelo no centro de conformidade da Microsoft 365. O conector usa as informações que você fornece para se conectar ao site do chat do ICE e transferir mensagens de chat para as caixas de correio de usuário correspondentes no Microsoft 365.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique em **conectores de dados** no painel de navegação esquerdo.

2. Na página **conectores de dados** , em **chat de gelo**, clique em **Exibir**.

3. Na página **chat Ice** , clique em **Adicionar conector**.

4. Na página **termos de serviço** , clique em **aceitar**.

5. Na página **Adicionar credenciais para o site de chat do Ice** , em etapa 3, insira as informações necessárias nas caixas a seguir e clique em **validar conexão**.

   - **Código da empresa:** A ID da sua organização, que é usada como o nome de usuário para o site do chat do ICE.

   - **Senha:** A senha para seu site do chat do ICE.

   - **URL de SFTP:** A URL do site do chat do ICE (por exemplo, sftp.theice.com).

   - **Porta SFTP:** O número da porta para o site do chat de gelo do ICE. O conector usa essa porta para se conectar ao site SFTP.

6. Depois que a conexão for validada, clique em **Avançar**.

7. Na página **mapear usuários externos para usuários do Microsoft 365** , habilite o mapeamento automático de usuários e forneça mapeamento de usuário personalizado, conforme necessário. Você pode baixar uma cópia do arquivo CSV de mapeamento do usuário nessa página. Você pode adicionar os mapeamentos de usuário ao arquivo e carregá-lo.

   > [!NOTE]
   > Como explicado anteriormente, o arquivo CSV de arquivo de mapeamento personalizado contém o Imid de bate-papo ICE e o endereço de caixa de correio do Microsoft 365 correspondente a cada usuário. Se você habilitar o mapeamento automático de usuários e fornecer um mapeamento personalizado, para cada item de chat, o conector examinará primeiro o arquivo de mapeamento personalizado. Se não encontrar um usuário válido do Microsoft 365 que corresponda ao Imid de chat de um usuário, o conector importará o item para as caixas de correio para os usuários especificados nas propriedades *SenderEmail* e *RecipientEmail* do item de chat. Se o conector não localizar um usuário válido do Microsoft 365 por meio do mapeamento de usuário automático ou personalizado, o item não será importado.

8. Clique em **Avançar**, revise suas configurações e clique em **concluir** para criar o conector.

9. Vá para a página **conectores de dados** para ver o andamento do processo de importação para o novo conector.
