---
title: Configurar um conector para arquivar dados de mensagens da Bloomberg
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
description: Os administradores podem configurar um conector de dados para importar e arquivar dados da ferramenta de email Mensagem do Bloomberg para o Microsoft 365. Isso permite arquivar dados de fontes de dados de terceiros no Microsoft 365 para que você possa usar recursos de conformidade como retenção legal, Pesquisa de Conteúdo e políticas de retenção para gerenciar dados de terceiros da sua organização.
ms.openlocfilehash: f9b082dace9301f5a664078e9028c646ffa28483
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790111"
---
# <a name="set-up-a-connector-to-archive-bloomberg-message-data"></a>Configurar um conector para arquivar dados de mensagens da Bloomberg

Use um conector de dados no centro de conformidade do Microsoft 365 para importar e arquivar dados de email de serviços financeiros da ferramenta de colaboração de mensagens [do Bloomberg.](https://www.bloomberg.com/professional/product/collaboration/) Depois de configurar um conector, ele se conecta ao site de segurança FTP (SFTP) da Bloomberg da sua organização uma vez por dia e importa itens de email para caixas de correio no Microsoft 365.

Depois que os dados da Mensagem do Bloomberg são armazenados nas caixas de correio do usuário, você pode aplicar recursos de conformidade do Microsoft 365, como retenção de litígio, pesquisa de conteúdo, arquivamento in-loque, auditoria, conformidade de comunicação e políticas de retenção do Microsoft 365 aos dados da Mensagem do Bloomberg. Por exemplo, você pode pesquisar emails da Bloomberg Message usando a ferramenta de pesquisa de conteúdo ou associar a caixa de correio que contém os dados da Mensagem do Bloomberg com um custodiante em um caso de Descoberta Eletrônico Avançada. Usar um conector de Mensagens do Bloomberg para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a manter a conformidade com políticas governamentais e regulamentar.

## <a name="overview-of-archiving-bloomberg-message-data"></a>Visão geral do arquivamento de dados de mensagens do Bloomberg

A visão geral a seguir explica o processo de uso de um conector para arquivar dados de Mensagens da Bloomberg no Microsoft 365.

![Processo de importação e arquivamento de mensagens da Bloomberg](../media/BloombergMessageArchiving.png)

1. Sua organização trabalha com a Bloomberg para configurar um site do Bloomberg SFTP. Você também trabalhará com a Bloomberg para configurar a Bloomberg Message para copiar mensagens de email para o site da Bloomberg SFTP.

2. Uma vez a cada 24 horas, as mensagens de email da Bloomberg Message são copiadas para o site da Bloomberg SFTP.

3. O conector de Mensagens do Bloomberg que você cria no centro de conformidade do Microsoft 365 conecta-se ao site do Bloomberg SFTP todos os dias e transfere as mensagens de email das últimas 24 horas para uma área de armazenamento do Azure segura no Microsoft Cloud.

4. O conector importa os itens de mensagem de email para a caixa de correio de um usuário específico. Uma nova pasta chamada BloombergMessage é criada na caixa de correio do usuário específico e os itens serão importados para ela. 

   O conector faz isso usando o valor da propriedade CorporateEmailAddress. Cada mensagem de email contém essa propriedade, que é preenchida com o endereço de email de cada participante da mensagem de email. Além do mapeamento automático de usuário usando o valor da propriedade *CorporateEmailAddress,* você também pode definir um mapeamento personalizado carregando um arquivo de mapeamento CSV. Esse arquivo de mapeamento contém uma UUID da Bloomberg e o endereço de caixa de correio correspondente do Microsoft 365 para cada usuário em sua organização. Se você habilitar o mapeamento automático de usuário e fornecer um mapeamento personalizado, para cada item de email, o conector primeiro irá olhar para o arquivo de mapeamento personalizado. Se não encontrar um usuário válido do Microsoft 365 que corresponda à UUID do Bloomberg de um usuário, o conector usará a propriedade *CorporateEmailAddress* do item de email. Se o conector não encontrar um usuário válido do Microsoft 365 no arquivo de mapeamento personalizado ou na propriedade *CorporateEmailAddress* do item de email, o item não será importado.

## <a name="before-you-begin"></a>Antes de começar

Algumas das etapas de implementação necessárias para arquivar dados de Mensagens da Bloomberg são externas ao Microsoft 365 e devem ser concluídas antes que você possa criar o conector no centro de conformidade.

- Assine o [Bloomberg em Qualquer Lugar.](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA) Isso é necessário para que você possa entrar na Bloomberg Anywhere para acessar o site da Bloomberg SFTP que você precisa configurar e configurar.

- Configurar um site do Bloomberg SFTP (protocolo de transferência de arquivos seguro). Depois de trabalhar com a Bloomberg para configurar o site SFTP, os dados do Bloomberg Message são carregados no site SFTP todos os dias. O conector criado na Etapa 2 conecta-se a esse site SFTP e transfere os dados de email para as caixas de correio do Microsoft 365. A SFTP também criptografa os dados da Mensagem da Bloomberg que são enviados para caixas de correio durante o processo de transferência.

  Para obter informações sobre o Bloomberg SFTP (também *chamado de BB-SFTP*):

  - Consulte o documento "Padrões de Conectividade SFTP" no [Suporte da Bloomberg.](https://www.bloomberg.com/professional/support/documentation/)

  - Entre [em contato com o suporte ao cliente da Bloomberg.](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc)

   > [!NOTE]
   > Se sua organização já implantou um conector para arquivar dados do Instant Bloomberg, você não precisa configurar outro site SFTP. Você pode usar o mesmo site SFTP para o conector de mensagens da Bloomberg.

- Depois de trabalhar com a Bloomberg para configurar um site SFTP, a Bloomberg fornecerá algumas informações a você depois de responder à mensagem de email de implementação da Bloomberg. Salve uma cópia das informações a seguir. Use-o para configurar um conector na Etapa 3.

  - Código de empresa, que é uma ID da sua organização e é usado para entrar no site do Bloomberg SFTP.

  - Senha para seu site do Bloomberg SFTP

  - URL para o site da Bloomberg SFTP (por exemplo, sftp.bloomberg.com). Além disso, a Bloomberg também pode fornecer um endereço IP correspondente para o site da Bloomberg SFTP, que também pode ser usado para configurar o conector.

  - Número da porta do site do Bloomberg SFTP

- O conector de Mensagens do Bloomberg pode importar um total de 200.000 itens em um único dia. Se houver mais de 200.000 itens no site SFTP, nenhum desses itens será importado para o Microsoft 365.

- O usuário que cria um conector de Mensagem do Bloomberg na Etapa 3 (e que baixa as chaves públicas e o endereço IP na Etapa 1) deve receber a função Importar Exportar Caixa de Correio no Exchange Online. Isso é necessário para adicionar conectores na página Conectores **de dados** no centro de conformidade do Microsoft 365. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função Importar Exportar Caixa de Correio ao grupo de função Gerenciamento da Organização no Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Importar Exportar Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) as [seções](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) Criar grupos de função ou Modificar grupos de função no artigo "Gerenciar grupos de função no Exchange Online".

## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>Etapa 1: Obter chaves públicas SSH e PGP

A primeira etapa é obter uma cópia das chaves públicas para o Shell Seguro (SSH) e o PGP (Privacidade Bastante Boa). Use essas chaves na Etapa 2 para configurar o site do Bloomberg SFTP para permitir que o conector (criado na Etapa 3) se conecte ao site SFTP e transfira os dados de email da Bloomberg Message para as caixas de correio do Microsoft 365. Você também obtém um endereço IP nesta etapa, que você usa ao configurar o site do Bloomberg SFTP.

1. Vá para [ https://compliance.microsoft.com\ ]( https://compliance.microsoft.com) e clique em **Conectores de dados** na barra de entrada esquerda.

2. Na página **Conectores de dados** em **Mensagem do Bloomberg,** clique em **Exibir.**

3. Na página de **descrição do produto Da Bloomberg Message,** clique **em Adicionar conector**

4. Na página **Termos de serviço,** clique em **Aceitar**.

5. No site Add **credentials for Bloomberg SFTP,** na etapa 1, clique na chave SSH de **Download,** baixe a chave **PGP** e baixe os links de endereço **IP** para salvar uma cópia de cada arquivo no computador local. Esses arquivos contêm os seguintes itens que são usados para configurar o site da Bloomberg SFTP na Etapa 2:

   - Chave pública SSH: essa chave é usada para configurar o Shell seguro (SSH) para habilitar um logon remoto seguro quando o conector se conectar ao site do Bloomberg SFTP.

   - Chave pública PGP: essa chave é usada para configurar a criptografia de dados transferidos do site do Bloomberg SFTP para o Microsoft 365.

   - Endereço IP: O site da Bloomberg SFTP está configurado para aceitar uma solicitação de conexão somente deste endereço IP, que é usado pelo conector de mensagens do Bloomberg que você cria na Etapa 3.

6. Clique **em Cancelar** para fechar o assistente. Você volta para este assistente na Etapa 3 para criar o conector.

## <a name="step-2-configure-the-bloomberg-sftp-site"></a>Etapa 2: Configurar o site do Bloomberg SFTP

> [!NOTE]
> Conforme mencionado anteriormente, se a sua organização já tiver definido um site do Bloomberg SFTP para arquivar dados do Instant Bloomberg, não será preciso configurar outro. Você pode especificar o mesmo site SFTP ao criar o conector na Etapa 3.

A próxima etapa é usar as chaves públicas SSH e PGP e o endereço IP obtido na Etapa 1 para configurar a autenticação SSH e a criptografia PGP para o site do Bloomberg SFTP. Isso permite que o conector de Mensagem do Bloomberg criado na Etapa 3 se conecte ao site do Bloomberg SFTP e transfira dados de Mensagem do Bloomberg para o Microsoft 365. Você precisa trabalhar com o suporte ao cliente da Bloomberg para configurar seu site do Bloomberg SFTP. Entre em [contato com o suporte ao cliente da Bloomberg](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) para assistência.

> [!IMPORTANT]
> A Bloomberg recomenda que você anexe os três arquivos baixados na Etapa 1 a uma mensagem de email e envie-os à equipe de atendimento ao cliente ao trabalhar com eles para configurar seu site do Bloomberg SFTP.

## <a name="step-3-create-a-bloomberg-message-connector"></a>Etapa 3: Criar um conector de mensagens do Bloomberg

A última etapa é criar um conector de mensagens do Bloomberg no centro de conformidade do Microsoft 365. O conector usa as informações que você fornece para se conectar ao site da Bloomberg SFTP e transferir mensagens de email para as caixas de correio de usuário correspondentes no Microsoft 365.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique **em Conectores de dados** na barra de entrada esquerda.

2. Na página **Conectores de dados** em **Mensagem do Bloomberg,** clique em **Exibir.**

3. Na página de **descrição do produto Da Bloomberg Message,** clique **em Adicionar conector**

4. Na página **Termos de serviço,** clique em **Aceitar**.

5. Na página Adicionar credenciais para o site do **Bloomberg SFTP,** em Etapa 3, insira as informações necessárias nas caixas a seguir e clique em **Próximo.**

      - **Código da empresa:** A ID da sua organização que é usada como o nome de usuário do site da Bloomberg SFTP.

      - **Senha:** A senha do site da Bloomberg SFTP da sua organização.

      - **URL SFTP:** A URL do site da Bloomberg SFTP (por exemplo, sftp.bloomberg.com).

      - **Porta SFTP:** O número da porta do site da Bloomberg SFTP. O conector usa essa porta para se conectar ao site SFTP.

6. Na página **Mapeamento de usuários,** habilita o mapeamento automático de usuário e fornece mapeamento de usuário personalizado conforme necessário

7. Clique **em Próximo,** revise suas configurações e clique em Preparar para criar o conector.

8. Vá para a **página Conectores de dados** para ver o progresso do processo de importação do novo conector.

## <a name="known-issues"></a>Problemas conhecidos

- Threading of Bloomberg Message email imported to Microsoft 365 isn't supported. As mensagens individuais enviadas a uma pessoa são importadas, mas não são apresentadas em uma conversa encadeada. A Microsoft está trabalhando para dar suporte ao threading em versões posteriores do conector de dados da Mensagem do Bloomberg.
