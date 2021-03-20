---
title: Configurar um conector para arquivar dados de Chat ICE
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
description: Os administradores podem configurar um conector para importar e arquivar dados da ferramenta de Chat ICE para o Microsoft 365. Isso permite que você arquive dados de fontes de dados de terceiros no Microsoft 365 para que você possa usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar os dados de terceiros da sua organização.
ms.openlocfilehash: 663b122ec81a3d2d448e8d0abe5da0bdd9dc7313
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904179"
---
# <a name="set-up-a-connector-to-archive-ice-chat-data"></a>Configurar um conector para arquivar dados de Chat ICE

Use um conector nativo no centro de conformidade do Microsoft 365 para importar e arquivar dados de chat de serviços financeiros da ferramenta de colaboração de Chat ICE. Depois de configurar e configurar um conector, ele se conecta ao site seguro FTP (SFTP) de chat seguro da sua organização, converte o conteúdo das mensagens de chat em um formato de mensagem de email e importa esses itens para caixas de correio no Microsoft 365.

Depois que os dados de chat ICE são armazenados em caixas de correio de usuário, você pode aplicar recursos de conformidade do Microsoft 365, como retenção de litígio, Descoberta Eletrônico, arquivamento, auditoria, conformidade de comunicação e políticas de retenção do Microsoft 365 aos dados de Chat ICE. Por exemplo, você pode pesquisar mensagens de Chat ICE usando a pesquisa de conteúdo ou associar a caixa de correio que contém os dados de Chat ICE com um custodiante em um caso de Descoberta Avançada de Descoberta Eletrônico. Usar um conector de Chat ICE para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a permanecer em conformidade com políticas governamentais e regulatórias.

## <a name="overview-of-archiving-ice-chat-data"></a>Visão geral dos dados de chat ICE de arquivamento

A visão geral a seguir explica o processo de uso de um conector para arquivar dados de chat ICE no Microsoft 365.

![Fluxo de trabalho de arquivamento de Chat ICE](../media/ICEChatConnectorWorkflow.png)

1. Sua organização trabalha com o ICE Chat para configurar um site SFTP de Chat ICE. Você também trabalhará com o ICE Chat para configurar o ICE Chat para copiar mensagens de chat para seu site SFTP de Chat ICE.

2. Uma vez a cada 24 horas, as mensagens de chat do ICE Chat são copiadas para seu site do SFTP de Chat ICE.

3. O conector de Chat ICE criado no centro de conformidade do Microsoft 365 conecta-se ao site SFTP de Chat DO ICE todos os dias e transfere as mensagens de chat das 24 horas anteriores para um local seguro de Armazenamento do Azure no Microsoft Cloud. O conector também converte o conteúdo de uma massagens de chat em um formato de mensagem de email.

4. O conector importa itens de mensagem de chat para as caixas de correio de usuários específicos. Uma nova pasta chamada **ICE Chat** é criada nas caixas de correio do usuário e os itens de mensagem de chat são importados para essa pasta. O conector faz usando o valor das *propriedades SenderEmail* e *RecipientEmail.* Cada mensagem de chat contém essas propriedades, que são preenchidas com o endereço de email do remetente e cada destinatário/participante da mensagem de chat.

   Além do mapeamento automático do usuário que usa os valores das propriedades *SenderEmail* e *RecipientEmail* (o que significa que o conector importa uma mensagem de chat para a caixa de correio do remetente e as caixas de correio de cada destinatário), você também pode definir o mapeamento de usuário personalizado carregando um arquivo de mapeamento CSV. Este arquivo de mapeamento contém o *ImId* de Chat ICE e o endereço de caixa de correio correspondente do Microsoft 365 para cada usuário em sua organização. Se você habilitar o mapeamento automático do usuário e fornecer um arquivo de mapeamento personalizado, para cada item de chat, o conector primeiro olhará para o arquivo de mapeamento personalizado. Se ele não encontrar uma conta de usuário válida do Microsoft 365 que corresponda à ImId de Chat ICE de um usuário, o conector usará as propriedades *SenderEmail* e *RecipientEmail* do item de chat para importar o item para as caixas de correio dos participantes do chat. Se o conector não encontrar um usuário válido do Microsoft 365 no arquivo de mapeamento personalizado ou nas propriedades *SenderEmail* e *RecipientEmail,* o item não será importado.

## <a name="before-you-begin"></a>Antes de começar

Algumas das etapas de implementação necessárias para arquivar dados do ICE Chat são externas ao Microsoft 365 e devem ser concluídas antes que você possa criar o conector no centro de conformidade.

- O ICE Chat cobra aos clientes uma taxa de conformidade externa. Sua organização deve entrar em contato com o grupo de vendas de Chat ICE para discutir e assinar o contrato de serviços de dados de Chat ICE, que você pode obter em [https://www.theice.com/publicdocs/agreements/ICE\_Data\_Services\_Agreement.pdf](https://www.theice.com/publicdocs/agreements/ICE\_Data\_Services\_Agreement.pdf) . Este contrato é entre o ICE Chat e sua organização e não envolve a Microsoft. Depois de configurar um site SFTP de Chat ICE na Etapa 2, o ICE Chat fornece as credenciais FTP diretamente para sua organização. Em seguida, você que forneceria essas credenciais para a Microsoft ao configurar o conector na Etapa 3.

- Você deve configurar um site SFTP de Chat ICE antes de criar o conector na Etapa 3. Depois de trabalhar com o ICE Chat para configurar o site do SFTP, os dados do ICE Chat são carregados no site do SFTP todos os dias. O conector criado na Etapa 3 se conecta a esse site SFTP e transfere os dados de chat para caixas de correio do Microsoft 365. O SFTP também criptografa os dados de Chat ICE enviados para caixas de correio durante o processo de transferência.

- O conector de Chat ICE pode importar um total de 200.000 itens em um único dia. Se houver mais de 200.000 itens no site do SFTP, nenhum desses itens será importado para o Microsoft 365.

- O administrador que cria o conector de Chat ICE na Etapa 3 (e que baixa as chaves públicas e o endereço IP na Etapa 1) deve receber a função de Exportação de Importação de Caixa de Correio no Exchange Online. Essa função é necessária para adicionar conectores na página **Conectores de** dados no centro de conformidade do Microsoft 365. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função Exportar Importação de Caixa de Correio ao grupo de função Gerenciamento da Organização no Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Exportar Importação de Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte as seções Criar grupos de [função](/Exchange/permissions-exo/role-groups#create-role-groups) ou [Modificar](/Exchange/permissions-exo/role-groups#modify-role-groups) grupos de função no artigo "Gerenciar grupos de função no Exchange Online".

## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>Etapa 1: Obter chaves públicas SSH e PGP

A primeira etapa é obter uma cópia das chaves públicas para o Shell Seguro (SSH) e a PGP (Privacidade Muito Boa). Você usa essas chaves na Etapa 2 para configurar o site SFTP de Chat ICE para permitir que o conector (criado na Etapa 3) se conecte ao site SFTP e transfira os dados de Chat ICE para caixas de correio do Microsoft 365. Você também obterá um endereço IP nesta etapa, que você usará ao configurar o site SFTP de Chat ICE.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique **em Conectores de dados** na nav esquerda.

2. Na página **Conectores de dados** em **Chat ICE,** clique em **Exibir**.

3. Na página **Chat ICE,** clique em **Adicionar conector**.

4. Na página **Termos de serviço,** clique em **Aceitar**.

5. Na página Adicionar credenciais para o **site do SFTP** de Chat DO ICE na etapa 1, clique na tecla **Baixar SSH,** baixe a **tecla PGP** e Baixe links de **endereço IP** para salvar uma cópia de cada arquivo no computador local. Esses arquivos contêm os seguintes itens que são usados para configurar o site SFTP de Chat ICE na Etapa 2:

   - Chave pública SSH: essa chave é usada para configurar o SSH Seguro para habilitar um logon remoto seguro quando o conector se conecta ao site do SFTP de Chat ICE.

   - Chave pública PGP: essa chave é usada para configurar a criptografia de dados que são transferidos do site SFTP de Chat ICE para o Microsoft 365.

   - Endereço IP: o site do SFTP de Chat ICE está configurado para aceitar uma solicitação de conexão somente a partir desse endereço IP, que é usado pelo conector de Chat ICE criado na Etapa 3.

6. Clique **em Cancelar** para fechar o assistente. Você volta para este assistente na Etapa 3 para criar o conector.

## <a name="step-2-configure-the-ice-chat-sftp-site"></a>Etapa 2: Configurar o site do SFTP de Chat ICE

A próxima etapa é usar as chaves públicas SSH e PGP e o endereço IP obtido na Etapa 1 para configurar a autenticação SSH e a criptografia PGP para o site SFTP de Chat ICE. Isso permite que o conector de Chat ICE criado na Etapa 3 se conecte ao site do SFTP de Chat ICE e transfira dados de Chat ICE para o Microsoft 365. Você precisa trabalhar com o suporte ao cliente de Chat ICE para configurar seu site SFTP de Chat ICE.

## <a name="step-3-create-an-ice-chat-connector"></a>Etapa 3: Criar um conector de Chat ICE

A última etapa é criar um conector de Chat ICE no centro de conformidade do Microsoft 365. O conector usa as informações fornecidas para se conectar ao site do SFTP de Chat ICE e transferir mensagens de chat para as caixas de correio de usuário correspondentes no Microsoft 365.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique **em Conectores de dados** na nav esquerda.

2. Na página **Conectores de dados** em **Chat ICE,** clique em **Exibir**.

3. Na página **Chat ICE,** clique em **Adicionar conector**.

4. Na página **Termos de serviço,** clique em **Aceitar**.

5. Na página Adicionar credenciais para O ICE **Chat SFTP,** em Etapa 3, insira as informações necessárias nas caixas a seguir e clique em **Validar conexão**.

   - **Código firme:** A ID da sua organização, que é usada como o nome de usuário para o site SFTP de Chat ICE.

   - **Senha:** A senha do seu site SFTP de Chat ICE.

   - **URL SFTP:** A URL do site SFTP de Chat ICE (por exemplo, sftp.theice.com).

   - **Porta SFTP:** O número da porta para o site SFTP de Chat ICE. O conector usa essa porta para se conectar ao site SFTP.

6. Depois que a conexão for validada, clique em **Next**.

7. Na página Mapear usuários externos para usuários do **Microsoft 365,** habilita o mapeamento automático do usuário e fornece o mapeamento de usuário personalizado conforme necessário. Você pode baixar uma cópia do arquivo CSV de mapeamento do usuário nesta página. Você pode adicionar os mapeamentos de usuário ao arquivo e, em seguida, carregue-o.

   > [!NOTE]
   > Conforme explicado anteriormente, o arquivo CSV de arquivo de mapeamento personalizado contém o imid de Chat ICE e o endereço de caixa de correio correspondente do Microsoft 365 para cada usuário. Se você habilitar o mapeamento automático do usuário e fornecer um mapeamento personalizado, para cada item de chat, o conector procurará primeiro o arquivo de mapeamento personalizado. Se ele não encontrar um usuário válido do Microsoft 365 que corresponda ao imid de Chat ICE de um usuário, o conector importará o item para as caixas de correio para os usuários especificados nas propriedades *SenderEmail* e *RecipientEmail* do item de chat. Se o conector não encontrar um usuário válido do Microsoft 365 pelo mapeamento de usuário automático ou personalizado, o item não será importado.

8. Clique **em Próximo,** revise suas configurações e clique em **Concluir** para criar o conector.

9. Vá até a **página Conectores de dados** para ver o andamento do processo de importação do novo conector.