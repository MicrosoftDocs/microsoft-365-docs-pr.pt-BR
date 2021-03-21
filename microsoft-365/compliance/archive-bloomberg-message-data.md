---
title: Configurar um conector para arquivar dados da Mensagem bloomberg
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
description: Os administradores podem configurar um conector de dados para importar e arquivar dados da ferramenta de email da Mensagem bloomberg para o Microsoft 365. Isso permite que você arquive dados de fontes de dados de terceiros no Microsoft 365 para que você possa usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar os dados de terceiros da sua organização.
ms.openlocfilehash: c29f8d0c09ce5e84ecf18830df4585f51361995b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919949"
---
# <a name="set-up-a-connector-to-archive-bloomberg-message-data"></a>Configurar um conector para arquivar dados da Mensagem bloomberg

Use um conector de dados no centro de conformidade do Microsoft 365 para importar e arquivar dados de email de serviços financeiros da ferramenta de colaboração [da Mensagem bloomberg.](https://www.bloomberg.com/professional/product/collaboration/) Depois de configurar e configurar um conector, ele se conecta ao site FTP seguro da Bloomberg (SFTP) da sua organização uma vez por dia e importa itens de email para caixas de correio no Microsoft 365.

Depois que os dados da Mensagem da Bloomberg são armazenados em caixas de correio de usuário, você pode aplicar recursos de conformidade do Microsoft 365, como retenção de litígio, pesquisa de conteúdo, arquivamento in-locar, auditoria, conformidade de comunicação e políticas de retenção do Microsoft 365 aos dados da Mensagem bloomberg. Por exemplo, você pode pesquisar emails da Mensagem bloomberg usando a ferramenta de pesquisa de conteúdo ou associar a caixa de correio que contém os dados da Mensagem Bloomberg com um custodiante em um caso de Descoberta Avançada de Descoberta Eletrônico. Usar um conector de Mensagem da Bloomberg para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a manter-se em conformidade com as políticas governamentais e regulatórias.

## <a name="overview-of-archiving-bloomberg-message-data"></a>Visão geral dos dados de mensagem do Bloomberg de arquivamento

A visão geral a seguir explica o processo de uso de um conector para arquivar dados da Mensagem do Bloomberg no Microsoft 365.

![Processo de importação e arquivamento de mensagens da Bloomberg](../media/BloombergMessageArchiving.png)

1. Sua organização trabalha com a Bloomberg para configurar um site do SFTP da Bloomberg. Você também trabalhará com a Bloomberg para configurar a Mensagem bloomberg para copiar mensagens de email para o site do SFTP da Bloomberg.

2. Uma vez a cada 24 horas, as mensagens de email da Mensagem Bloomberg são copiadas para o site do SFTP da Bloomberg.

3. O conector de Mensagem da Bloomberg que você cria no centro de conformidade do Microsoft 365 conecta-se ao site do SFTP da Bloomberg todos os dias e transfere as mensagens de email das 24 horas anteriores para uma área segura de Armazenamento do Azure no Microsoft Cloud.

4. O conector importa os itens de mensagem de email para a caixa de correio de um usuário específico. Uma nova pasta chamada BloombergMessage é criada na caixa de correio do usuário específico e os itens serão importados para ela. 

   O conector faz isso usando o valor da propriedade CorporateEmailAddress. Cada mensagem de email contém essa propriedade, que é preenchida com o endereço de email de cada participante da mensagem de email. Além do mapeamento automático do usuário usando o valor da propriedade *CorporateEmailAddress,* você também pode definir um mapeamento personalizado carregando um arquivo de mapeamento CSV. Este arquivo de mapeamento contém uma UUID da Bloomberg e o endereço de caixa de correio correspondente do Microsoft 365 para cada usuário em sua organização. Se você habilitar o mapeamento automático do usuário e fornecer um mapeamento personalizado, para cada item de email, o conector olhará primeiro para o arquivo de mapeamento personalizado. Se ele não encontrar um usuário válido do Microsoft 365 que corresponda à UUID bloomberg de um usuário, o conector usará a propriedade *CorporateEmailAddress* do item de email. Se o conector não encontrar um usuário válido do Microsoft 365 no arquivo de mapeamento personalizado ou na propriedade *CorporateEmailAddress* do item de email, o item não será importado.

## <a name="before-you-begin"></a>Antes de começar

Algumas das etapas de implementação necessárias para arquivar dados da Mensagem do Bloomberg são externas ao Microsoft 365 e devem ser concluídas antes que você possa criar o conector no centro de conformidade.

- Inscreva-se [em Bloomberg Em Qualquer Lugar](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA). Isso é necessário para que você possa fazer logoff na Bloomberg Em Qualquer Lugar para acessar o site do SFTP da Bloomberg que você precisa configurar e configurar.

- Configurar um site do SFTP da Bloomberg (protocolo de transferência de arquivos seguro). Depois de trabalhar com a Bloomberg para configurar o site do SFTP, os dados da Mensagem da Bloomberg são carregados no site SFTP todos os dias. O conector criado na Etapa 2 conecta-se a esse site SFTP e transfere os dados de email para caixas de correio do Microsoft 365. O SFTP também criptografa os dados da Mensagem Bloomberg que são enviados para caixas de correio durante o processo de transferência.

  Para obter informações sobre o SFTP da Bloomberg (também chamado *de BB-SFTP*):

  - Consulte o documento "Padrões de Conectividade SFTP" em [Suporte à Bloomberg](https://www.bloomberg.com/professional/support/documentation/).

  - Entre [em contato com o suporte ao cliente da Bloomberg.](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc)

   > [!NOTE]
   > Se sua organização já tiver implantado um conector para arquivar dados instantâneos do Bloomberg, você não precisará configurar outro site SFTP. Você pode usar o mesmo site SFTP para o conector de Mensagens da Bloomberg.

- Depois de trabalhar com a Bloomberg para configurar um site SFTP, a Bloomberg fornecerá algumas informações a você depois de responder à mensagem de email de implementação do Bloomberg. Salve uma cópia das informações a seguir. Use-o para configurar um conector na Etapa 3.

  - Código firme, que é uma ID da sua organização e é usado para fazer logoff no site do SFTP da Bloomberg.

  - Senha para seu site do SFTP da Bloomberg

  - URL do site do SFTP da Bloomberg (por exemplo, sftp.bloomberg.com). Além disso, a Bloomberg também pode fornecer um endereço IP correspondente para o site do SFTP da Bloomberg, que também pode ser usado para configurar o conector.

  - Número da porta para o site do SFTP da Bloomberg

- O conector de Mensagem bloomberg pode importar um total de 200.000 itens em um único dia. Se houver mais de 200.000 itens no site do SFTP, nenhum desses itens será importado para o Microsoft 365.

- O usuário que cria um conector de Mensagem do Bloomberg na Etapa 3 (e que baixa as chaves públicas e o endereço IP na Etapa 1) deve receber a função de Exportação de Importação de Caixa de Correio no Exchange Online. Isso é necessário para adicionar conectores na página **Conectores de** dados no centro de conformidade do Microsoft 365. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função Exportar Importação de Caixa de Correio ao grupo de função Gerenciamento da Organização no Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Exportar Importação de Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte as seções Criar grupos de [função](/Exchange/permissions-exo/role-groups#create-role-groups) ou [Modificar](/Exchange/permissions-exo/role-groups#modify-role-groups) grupos de função no artigo "Gerenciar grupos de função no Exchange Online".

## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>Etapa 1: Obter chaves públicas SSH e PGP

A primeira etapa é obter uma cópia das chaves públicas para o Shell Seguro (SSH) e a PGP (Privacidade Muito Boa). Você usa essas chaves na Etapa 2 para configurar o site do SFTP do Bloomberg para permitir que o conector (criado na Etapa 3) se conecte ao site SFTP e transfira os dados de email da Mensagem Bloomberg para caixas de correio do Microsoft 365. Você também obtém um endereço IP nesta etapa, que você usa ao configurar o site do SFTP do Bloomberg.

1. Vá para [ https://compliance.microsoft.com\ ]( https://compliance.microsoft.com) e clique em **Conectores de** dados na nav esquerda.

2. Na página **Conectores de dados** em **Mensagem de Bloomberg,** clique em **Exibir**.

3. Na página **Descrição do produto da mensagem Bloomberg,** clique em **Adicionar conector**

4. Na página **Termos de serviço,** clique em **Aceitar**.

5. No site Adicionar credenciais do **SFTP do Bloomberg** na etapa 1, clique na tecla **Baixar SSH,** baixe a **tecla PGP** e Baixe links de **endereço IP** para salvar uma cópia de cada arquivo no computador local. Esses arquivos contêm os seguintes itens usados para configurar o site do SFTP do Bloomberg na Etapa 2:

   - Chave pública SSH: essa chave é usada para configurar o Secure Shell (SSH) para habilitar um logon remoto seguro quando o conector se conectar ao site do SFTP da Bloomberg.

   - Chave pública PGP: essa chave é usada para configurar a criptografia de dados transferidos do site do SFTP da Bloomberg para o Microsoft 365.

   - Endereço IP: o site do SFTP da Bloomberg está configurado para aceitar uma solicitação de conexão somente a partir desse endereço IP, que é usado pelo conector de Mensagem do Bloomberg que você cria na Etapa 3.

6. Clique **em Cancelar** para fechar o assistente. Você volta para este assistente na Etapa 3 para criar o conector.

## <a name="step-2-configure-the-bloomberg-sftp-site"></a>Etapa 2: Configurar o site do SFTP da Bloomberg

> [!NOTE]
> Como mencionado anteriormente, se você estiver organizando anteriormente um site do SFTP da Bloomberg para arquivar dados instantâneos do Bloomberg, você não precisa configurar outro. Você pode especificar o mesmo site SFTP ao criar o conector na Etapa 3.

A próxima etapa é usar as chaves públicas SSH e PGP e o endereço IP obtido na Etapa 1 para configurar a autenticação SSH e a criptografia PGP para o site do SFTP da Bloomberg. Isso permite que o conector de Mensagem do Bloomberg criado na Etapa 3 se conecte ao site do SFTP da Bloomberg e transfira dados da Mensagem do Bloomberg para o Microsoft 365. Você precisa trabalhar com o suporte ao cliente da Bloomberg para configurar seu site do SFTP da Bloomberg. Entre [em contato com o suporte ao cliente da Bloomberg](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) para assistência.

> [!IMPORTANT]
> A Bloomberg recomenda que você anexe os três arquivos baixados na Etapa 1 a uma mensagem de email e envie-a para a equipe de suporte ao cliente ao trabalhar com eles para configurar seu site do SFTP da Bloomberg.

## <a name="step-3-create-a-bloomberg-message-connector"></a>Etapa 3: Criar um conector de mensagem da Bloomberg

A última etapa é criar um conector de Mensagem do Bloomberg no centro de conformidade do Microsoft 365. O conector usa as informações fornecidas para se conectar ao site do SFTP da Bloomberg e transferir mensagens de email para as caixas de correio de usuário correspondentes no Microsoft 365.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique **em Conectores de dados** na nav esquerda.

2. Na página **Conectores de dados** em **Mensagem de Bloomberg,** clique em **Exibir**.

3. Na página **Descrição do produto da mensagem Bloomberg,** clique em **Adicionar conector**

4. Na página **Termos de serviço,** clique em **Aceitar**.

5. Na página Adicionar credenciais para o **site do SFTP da Bloomberg,** em Etapa 3, insira as informações necessárias nas caixas a seguir e clique em **Próximo**.

      - **Código firme:** A ID da sua organização que é usada como nome de usuário para o site do SFTP da Bloomberg.

      - **Senha:** A senha do site do SFTP bloomberg da sua organização.

      - **URL SFTP:** A URL do site do SFTP da Bloomberg (por exemplo, sftp.bloomberg.com).

      - **Porta SFTP:** O número da porta do site do SFTP da Bloomberg. O conector usa essa porta para se conectar ao site SFTP.

6. Na página **Mapeamento de usuário,** habilita o mapeamento automático do usuário e fornece mapeamento de usuário personalizado conforme necessário

7. Clique **em Próximo,** revise suas configurações e clique em Preparar-se para criar o conector.

8. Vá até a **página Conectores de dados** para ver o andamento do processo de importação do novo conector.

## <a name="known-issues"></a>Problemas conhecidos

- Threading of Bloomberg Message email imported to Microsoft 365 isn't supported. As mensagens individuais enviadas a uma pessoa são importadas, mas não são apresentadas em uma conversa encadeada. A Microsoft está trabalhando para dar suporte ao threading em versões posteriores do conector de dados da Mensagem do Bloomberg.