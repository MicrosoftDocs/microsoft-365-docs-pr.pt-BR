---
title: Configurar um conector para arquivar dados de chat ICE
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
description: Os administradores podem configurar um conector para importar e arquivar dados da ferramenta de Chat ICE no Microsoft 365. Isso permite arquivar dados de fontes de dados de terceiros no Microsoft 365 para que você possa usar recursos de conformidade como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar dados de terceiros da sua organização.
ms.openlocfilehash: 79a18017ce7aa3c646fa6c7230bde4b001ddc4c8
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790165"
---
# <a name="set-up-a-connector-to-archive-ice-chat-data"></a>Configurar um conector para arquivar dados de chat ICE

Use um conector nativo no centro de conformidade do Microsoft 365 para importar e arquivar dados de chat de serviços financeiros da ferramenta de colaboração do ICE Chat. Depois de configurar um conector, ele se conecta ao site de segurança FTP (SFTP) de Chat ICE da sua organização uma vez por dia, converte o conteúdo das mensagens de chat em um formato de mensagem de email e, em seguida, importa esses itens para caixas de correio no Microsoft 365.

Depois que os dados de chat ICE são armazenados em caixas de correio do usuário, você pode aplicar recursos de conformidade do Microsoft 365, como retenção de litígio, Descoberta e Arquivamento, auditoria, conformidade de comunicação e políticas de retenção do Microsoft 365 aos dados do ICE Chat. Por exemplo, você pode pesquisar mensagens de Chat ICE usando a pesquisa de conteúdo ou associar a caixa de correio que contém os dados de Chat ICE com um custodiante em um caso de Descoberta Eletrônico Avançada. Usar um conector de Chat ICE para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a manter a conformidade com políticas governamentais e regulatórias.

## <a name="overview-of-archiving-ice-chat-data"></a>Visão geral de arquivamento de dados de chat ICE

A visão geral a seguir explica o processo de uso de um conector para arquivar dados de chat ICE no Microsoft 365.

![Fluxo de trabalho de arquivamento de chat ICE](../media/ICEChatConnectorWorkflow.png)

1. Sua organização trabalha com o ICE Chat para configurar um site do ICE Chat SFTP. Você também trabalhará com o ICE Chat para configurar o ICE Chat para copiar mensagens de chat para seu site do ICE Chat SFTP.

2. Uma vez a cada 24 horas, as mensagens de chat do ICE Chat são copiadas para o seu site do ICE Chat SFTP.

3. O conector de Chat ICE que você cria no centro de conformidade do Microsoft 365 conecta-se ao site SFTP do ICE Chat todos os dias e transfere as mensagens de chat das 24 horas anteriores para um local seguro de Armazenamento do Azure no Microsoft Cloud. O conector também converte o conteúdo de um chat em um formato de mensagem de email.

4. O conector importa itens de mensagem de chat para as caixas de correio de usuários específicos. Uma nova pasta chamada **ICE Chat** é criada nas caixas de correio do usuário e os itens de mensagem de chat são importados para essa pasta. O conector usa o valor das propriedades *SenderEmail* e *RecipientEmail.* Cada mensagem de chat contém essas propriedades, que são preenchidas com o endereço de email do remetente e cada destinatário/participante da mensagem de chat.

   Além do mapeamento automático de usuário que usa os valores das propriedades *SenderEmail* e *RecipientEmail* (o que significa que o conector importa uma mensagem de chat para a caixa de correio do remetente e as caixas de correio de cada destinatário), você também pode definir o mapeamento de usuário personalizado carregando um arquivo de mapeamento CSV. Esse arquivo de mapeamento contém a *ImId* do Chat ICE e o endereço de caixa de correio correspondente do Microsoft 365 para cada usuário em sua organização. Se você habilitar o mapeamento automático de usuário e fornecer um arquivo de mapeamento personalizado, para cada item de chat, o conector primeiro olhará para o arquivo de mapeamento personalizado. Se não encontrar uma conta de usuário válida do Microsoft 365 que corresponda à ImId de chat ICE de um usuário, o conector usará as propriedades *SenderEmail* e *RecipientEmail* do item de chat para importar o item para as caixas de correio dos participantes do chat. Se o conector não encontrar um usuário válido do Microsoft 365 no arquivo de mapeamento personalizado ou nas propriedades *SenderEmail* e *RecipientEmail,* o item não será importado.

## <a name="before-you-begin"></a>Antes de começar

Algumas das etapas de implementação necessárias para arquivar dados de Chat ICE são externas ao Microsoft 365 e devem ser concluídas antes que você possa criar o conector no centro de conformidade.

- O Chat ICE cobra aos clientes uma taxa de conformidade externa. Sua organização deve entrar em contato com o grupo de vendas do ICE Chat para discutir e assinar o contrato de serviços de dados de chat ICE, que você pode obter em [https://www.theice.com/publicdocs/agreements/ICE\_Data\_Services\_Agreement.pdf](https://www.theice.com/publicdocs/agreements/ICE\_Data\_Services\_Agreement.pdf) . Este contrato é entre o ICE Chat e sua organização e não envolve a Microsoft. Depois de configurar um site do ICE Chat SFTP na Etapa 2, o ICE Chat fornece as credenciais de FTP diretamente para sua organização. Em seguida, você que forneceria essas credenciais à Microsoft ao configurar o conector na Etapa 3.

- Você deve configurar um site SFTP de Chat ICE antes de criar o conector na Etapa 3. Depois de trabalhar com o ICE Chat para configurar o site SFTP, os dados do ICE Chat são carregados no site SFTP todos os dias. O conector criado na Etapa 3 conecta-se a esse site SFTP e transfere os dados de chat para as caixas de correio do Microsoft 365. A SFTP também criptografa os dados de Chat ICE que são enviados para caixas de correio durante o processo de transferência.

- O conector de Chat ICE pode importar um total de 200.000 itens em um único dia. Se houver mais de 200.000 itens no site SFTP, nenhum desses itens será importado para o Microsoft 365.

- O administrador que cria o conector de Chat ICE na Etapa 3 (e que baixa as chaves públicas e o endereço IP na Etapa 1) deve receber a função Importar Exportar Caixa de Correio no Exchange Online. Essa função é necessária para adicionar conectores na página Conectores **de dados** no centro de conformidade do Microsoft 365. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função Importar Exportar Caixa de Correio ao grupo de função Gerenciamento da Organização no Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Importar Exportar Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) as [seções](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) Criar grupos de função ou Modificar grupos de função no artigo "Gerenciar grupos de função no Exchange Online".

## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>Etapa 1: Obter chaves públicas SSH e PGP

A primeira etapa é obter uma cópia das chaves públicas para o Shell Seguro (SSH) e o PGP (Privacidade Bastante Boa). Use essas chaves na Etapa 2 para configurar o site SFTP de Chat ICE para permitir que o conector (criado na Etapa 3) se conecte ao site SFTP e transfira os dados do Chat ICE para as caixas de correio do Microsoft 365. Você também obterá um endereço IP nesta etapa, que você usará ao configurar o site SFTP de Chat ICE.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique **em Conectores de dados** na barra de entrada esquerda.

2. Na página **Conectores de dados** em **Chat ICE,** clique em **Exibir**.

3. Na página **chat ICE,** clique **em Adicionar conector**.

4. Na página **Termos de serviço,** clique em **Aceitar**.

5. Na página Adicionar credenciais para o **site do ICE Chat SFTP** na etapa 1, clique na chave SSH de **Download,** na chave **PGP** e baixe os links de endereço **IP** para salvar uma cópia de cada arquivo no computador local. Esses arquivos contêm os seguintes itens que são usados para configurar o site do ICE Chat SFTP na Etapa 2:

   - Chave pública SSH: essa chave é usada para configurar o SSH Seguro para habilitar um logon remoto seguro quando o conector se conecta ao site SFTP de Chat ICE.

   - Chave pública PGP: essa chave é usada para configurar a criptografia de dados transferidos do site SFTP de Chat ICE para o Microsoft 365.

   - Endereço IP: O site SFTP de Chat ICE está configurado para aceitar uma solicitação de conexão somente deste endereço IP, que é usado pelo conector de Chat ICE criado na Etapa 3.

6. Clique **em Cancelar** para fechar o assistente. Você volta para este assistente na Etapa 3 para criar o conector.

## <a name="step-2-configure-the-ice-chat-sftp-site"></a>Etapa 2: Configurar o site do ICE Chat SFTP

A próxima etapa é usar as chaves públicas SSH e PGP e o endereço IP obtido na Etapa 1 para configurar a autenticação SSH e a criptografia PGP para o site ice Chat SFTP. Isso permite que o conector de Chat ICE criado na Etapa 3 se conecte ao site SFTP de Chat ICE e transfira dados do ICE Chat para o Microsoft 365. Você precisa trabalhar com o suporte ao cliente do ICE Chat para configurar seu site do ICE Chat SFTP.

## <a name="step-3-create-an-ice-chat-connector"></a>Etapa 3: Criar um conector de Chat ICE

A última etapa é criar um conector de Chat ICE no centro de conformidade do Microsoft 365. O conector usa as informações que você fornece para se conectar ao site do ICE Chat SFTP e transferir mensagens de chat para as caixas de correio do usuário correspondentes no Microsoft 365.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique **em Conectores de dados** na barra de entrada esquerda.

2. Na página **Conectores de dados** em **Chat ICE,** clique em **Exibir**.

3. Na página **chat ICE,** clique **em Adicionar conector**.

4. Na página **Termos de serviço,** clique em **Aceitar**.

5. Na página Adicionar credenciais para o **site do ICE Chat SFTP,** em Etapa 3, insira as informações necessárias nas caixas a seguir e clique em **Validar conexão.**

   - **Código da empresa:** A ID da sua organização, que é usada como o nome de usuário para o site SFTP de Chat ICE.

   - **Senha:** A senha do seu site ice Chat SFTP.

   - **URL SFTP:** A URL do site ice chat SFTP (por exemplo, sftp.theice.com).

   - **Porta SFTP:** O número da porta para o site do ICE Chat SFTP. O conector usa essa porta para se conectar ao site SFTP.

6. Depois que a conexão for validada, clique em **Próximo.**

7. Na página Mapear usuários externos para usuários do **Microsoft 365,** habilita o mapeamento automático de usuários e fornece mapeamento de usuário personalizado conforme necessário. Você pode baixar uma cópia do arquivo CSV de mapeamento de usuário nesta página. Você pode adicionar os mapeamentos de usuário ao arquivo e, em seguida, carregue-o.

   > [!NOTE]
   > Conforme explicado anteriormente, o arquivo CSV de mapeamento personalizado contém a IMID do Chat ICE e o endereço de caixa de correio correspondente do Microsoft 365 para cada usuário. Se você habilitar o mapeamento automático de usuário e fornecer um mapeamento personalizado, para cada item de chat, o conector primeiro procurará o arquivo de mapeamento personalizado. Se não encontrar um usuário válido do Microsoft 365 que corresponda à imid de chat ICE de um usuário, o conector importa o item para as caixas de correio dos usuários especificados nas propriedades *SenderEmail* e *RecipientEmail* do item de chat. Se o conector não encontrar um usuário válido do Microsoft 365 por mapeamento automático ou personalizado, o item não será importado.

8. Clique **em Próximo,** revise suas configurações e clique em **Concluir** para criar o conector.

9. Vá para a **página Conectores de dados** para ver o progresso do processo de importação do novo conector.
