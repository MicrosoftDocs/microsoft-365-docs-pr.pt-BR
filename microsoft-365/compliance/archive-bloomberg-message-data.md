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
description: Os administradores podem configurar um conector de dados para importar e arquivar dados da ferramenta de email da Mensagem bloomberg no Microsoft 365. Isso permite que você arquive dados de fontes de dados de terceiros no Microsoft 365 para que você possa usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar os dados de terceiros da sua organização.
ms.openlocfilehash: 7029b95e4b9ceb91859e2a4b38afb5205e3307b2
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222532"
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

## <a name="before-you-set-up-a-connector"></a>Antes de configurar um conector

Algumas das etapas de implementação necessárias para arquivar dados da Mensagem do Bloomberg são externas ao Microsoft 365 e devem ser concluídas antes que você possa criar o conector no centro de conformidade.

- Para configurar um conector de Mensagem da Bloomberg, você precisa usar chaves e senhas de teclas para PGP (Privacidade Muito Boa) e Shell Seguro (SSH). Essas chaves são usadas para configurar o site do SFTP da Bloomberg e usadas pelo conector para se conectar ao site do SFTP da Bloomberg para importar dados para o Microsoft 365. A chave PGP é usada para configurar a criptografia de dados transferidos do site do SFTP da Bloomberg para o Microsoft 365. A chave SSH é usada para configurar o shell seguro para habilitar um logon remoto seguro quando o conector se conecta ao site do SFTP da Bloomberg.

  Ao configurar um conector, você tem a opção de usar chaves públicas e senhas de chave fornecidas pela Microsoft ou pode usar suas próprias chaves privadas e senhas. Recomendamos que você use as chaves públicas fornecidas pela Microsoft. No entanto, se sua organização já configurou um site do SFTP da Bloomberg usando chaves privadas, então você pode criar um conector usando essas mesmas chaves privadas.

- Inscreva-se [em Bloomberg Em Qualquer Lugar](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA). Isso é necessário para que você possa fazer logoff na Bloomberg Em Qualquer Lugar para acessar o site do SFTP da Bloomberg que você precisa configurar e configurar.

- Configurar um site do SFTP da Bloomberg (protocolo de transferência de arquivos seguro). Depois de trabalhar com a Bloomberg para configurar o site do SFTP, os dados da Mensagem da Bloomberg são carregados no site SFTP todos os dias. O conector criado na Etapa 2 conecta-se a esse site SFTP e transfere os dados de email para caixas de correio do Microsoft 365. O SFTP também criptografa os dados da Mensagem Bloomberg que são enviados para caixas de correio durante o processo de transferência.

  Para obter informações sobre o SFTP da Bloomberg (também chamado *de BB-SFTP*):

  - Consulte o documento "Padrões de Conectividade SFTP" em [Suporte à Bloomberg](https://www.bloomberg.com/professional/support/documentation/).

  - Entre [em contato com o suporte ao cliente da Bloomberg.](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc)

- Depois de trabalhar com a Bloomberg para configurar um site SFTP, a Bloomberg fornecerá algumas informações a você depois de responder à mensagem de email de implementação do Bloomberg. Salve uma cópia das informações a seguir. Use-o para configurar um conector na Etapa 3.

  - Código firme, que é uma ID da sua organização e é usado para fazer logoff no site do SFTP da Bloomberg.

  - Senha para seu site do SFTP da Bloomberg

  - URL do site do SFTP da Bloomberg (por exemplo, sftp.bloomberg.com). Além disso, a Bloomberg também pode fornecer um endereço IP correspondente para o site do SFTP da Bloomberg, que também pode ser usado para configurar o conector.

  - Número da porta para o site do SFTP da Bloomberg

- O conector de Mensagem bloomberg pode importar um total de 200.000 itens em um único dia. Se houver mais de 200.000 itens no site do SFTP, nenhum desses itens será importado para o Microsoft 365.

- O usuário que cria um conector de Mensagem do Bloomberg na Etapa 3 (e que baixa as chaves públicas e o endereço IP na Etapa 1) deve receber a função de Exportação de Importação de Caixa de Correio no Exchange Online. Isso é necessário para adicionar conectores na página **Conectores de** dados no centro de conformidade do Microsoft 365. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função Exportar Importação de Caixa de Correio ao grupo de função Gerenciamento da Organização no Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Exportar Importação de Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte as seções Criar grupos de [função](/Exchange/permissions-exo/role-groups#create-role-groups) ou [Modificar](/Exchange/permissions-exo/role-groups#modify-role-groups) grupos de função no artigo "Gerenciar grupos de função no Exchange Online".

## <a name="set-up-a-connector-using-public-keys"></a>Configurar um conector usando chaves públicas

As etapas nesta seção mostram como configurar um conector de Mensagem da Bloomberg usando as chaves públicas para PGP (Privacidade Muito Boa) e Shell Seguro (SSH).

### <a name="step-1-obtain-pgp-and-ssh-public-keys"></a>Etapa 1: Obter chaves públicas PGP e SSH

A primeira etapa é obter uma cópia das chaves públicas PGP e SSH. Você usa essas chaves na Etapa 2 para configurar o site do SFTP do Bloomberg para permitir que o conector (criado na Etapa 3) se conecte ao site SFTP e transfira os dados de email da Mensagem Bloomberg para caixas de correio do Microsoft 365. Você também obtém um endereço IP nesta etapa, que você usa ao configurar o site do SFTP do Bloomberg.

1. Vá para <https://compliance.microsoft.com> e clique **em Conectores de dados** na nav esquerda.

2. Na página **Conectores de dados** em **Mensagem de Bloomberg,** clique em **Exibir**.

3. Na página **Descrição do produto da mensagem Bloomberg,** clique em **Adicionar conector**

4. Na página **Termos de serviço,** clique em **Aceitar**.

5. Na página **Adicionar credenciais para fonte de** conteúdo, clique em Quero usar chaves **públicas PGP** e SSH fornecidas pela Microsoft .

   ![Selecione a opção para usar chaves públicas](../media/BloombergMessagePublicKeysOption.png)

6. Na etapa 1, clique na tecla **Baixar SSH,** baixe a tecla **PGP** e Baixe links de **endereço IP** para salvar uma cópia de cada arquivo no computador local.

   ![Links para baixar chaves públicas e endereço IP](../media/BloombergMessagePublicKeyDownloadLinks.png)

   Esses arquivos contêm os seguintes itens usados para configurar o site do SFTP do Bloomberg na Etapa 2:

   - Chave pública PGP: essa chave é usada para configurar a criptografia de dados transferidos do site do SFTP da Bloomberg para o Microsoft 365.

   - Chave pública SSH: essa chave é usada para configurar o shell seguro para habilitar um logon remoto seguro quando o conector se conecta ao site do SFTP da Bloomberg.

   - Endereço IP: o site do SFTP da Bloomberg está configurado para aceitar solicitações de conexão deste endereço IP. O mesmo endereço IP é usado pelo conector de Mensagens do Bloomberg para se conectar ao site SFTP e transferir dados da Mensagem de Bloomberg para o Microsoft 365.

7. Clique **em Cancelar** para fechar o assistente. Você volta para este assistente na Etapa 3 para criar o conector.

### <a name="step-2-configure-the-bloomberg-sftp-site"></a>Etapa 2: Configurar o site do SFTP da Bloomberg

> [!NOTE]
> Se sua organização tiver criado anteriormente um site do SFTP da Bloomberg para arquivar dados instantâneos da Bloomberg usando chaves PGP e SSH públicas, você não precisa configurar outro. Você pode especificar o mesmo site SFTP ao criar o conector na Etapa 3.

A próxima etapa é usar as chaves públicas PGP e SSH e o endereço IP obtido na Etapa 1 para configurar a criptografia PGP e a autenticação SSH para o site do SFTP da Bloomberg. Isso permite que o conector de Mensagem do Bloomberg criado na Etapa 3 se conecte ao site do SFTP da Bloomberg e transfira dados da Mensagem do Bloomberg para o Microsoft 365. Você precisa trabalhar com o suporte ao cliente da Bloomberg para configurar seu site do SFTP da Bloomberg. Entre [em contato com o suporte ao cliente da Bloomberg](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) para assistência.

> [!IMPORTANT]
> A Bloomberg recomenda que você anexe os três arquivos baixados na Etapa 1 a uma mensagem de email e envie-a para a equipe de suporte ao cliente ao trabalhar com eles para configurar seu site do SFTP da Bloomberg.

### <a name="step-3-create-a-bloomberg-message-connector"></a>Etapa 3: Criar um conector de mensagem da Bloomberg

A última etapa é criar um conector de Mensagem do Bloomberg no centro de conformidade do Microsoft 365. O conector usa as informações fornecidas para se conectar ao site do SFTP da Bloomberg e transferir mensagens de email para as caixas de correio de usuário correspondentes no Microsoft 365.

1. Vá para <https://compliance.microsoft.com> e clique **em Conectores de dados** na nav esquerda.

2. Na página **Conectores de dados** em **Mensagem de Bloomberg,** clique em **Exibir**.

3. Na página **Descrição do produto da mensagem Bloomberg,** clique em **Adicionar conector**

4. Na página **Termos de serviço,** clique em **Aceitar**.

5. Na página **Adicionar credenciais para fonte de** conteúdo, clique em Quero usar chaves **públicas PGP** e SSH fornecidas pela Microsoft .

6. Em Etapa 3, insira as informações necessárias nas caixas a seguir e clique em **Validar conexão**.

      - **Nome:** O nome do conector. Ele deve ser exclusivo em sua organização.

      - **Código firme:** A ID da sua organização que é usada como nome de usuário para o site do SFTP da Bloomberg.

      - **Senha:** A senha do site do SFTP bloomberg da sua organização.

      - **URL SFTP:** A URL do site do SFTP da Bloomberg (por exemplo, `sftp.bloomberg.com` ). Você também pode usar um endereço IP para esse valor.

      - **Porta SFTP:** O número da porta do site do SFTP da Bloomberg. O conector usa essa porta para se conectar ao site SFTP.

7. Depois que a conexão for validada com êxito, clique em **Next**.

8. Na página Mapear usuários da Mensagem bloomberg para usuários do **Microsoft 365,** habilita o mapeamento automático do usuário e fornece mapeamento de usuário personalizado conforme necessário.

   > [!NOTE]
   > O conector importa itens de mensagem para a caixa de correio de um usuário específico. Uma nova pasta chamada **BloombergMessage** é criada na caixa de correio do usuário específico e os itens serão importados para ela. O conector faz usando o valor da *propriedade CorporateEmailAddress.* Cada mensagem de chat contém essa propriedade e a propriedade é preenchida com o endereço de email de cada participante da mensagem de chat. Além do mapeamento automático do usuário usando o valor da propriedade *CorporateEmailAddress,* você também pode definir o mapeamento personalizado carregando um arquivo de mapeamento CSV. O arquivo de mapeamento deve conter o UUID do Bloomberg e o endereço de caixa de correio correspondente do Microsoft 365 para cada usuário. Se você habilitar o mapeamento automático do usuário e fornecer um mapeamento personalizado, para cada item de mensagem, o conector procurará primeiro o arquivo de mapeamento personalizado. Se ele não encontrar um usuário válido do Microsoft 365 que corresponda à UUID bloomberg de um usuário, o conector usará a propriedade *CorporateEmailAddress* do item de chat. Se o conector não encontrar um usuário válido do Microsoft 365 no arquivo de mapeamento personalizado ou na propriedade *CorporateEmailAddress* do item de mensagem, o item não será importado.

9. Clique **em Próximo,** revise suas configurações e clique em **Concluir** para criar o conector.

10. Vá até a **página Conectores de dados** para ver o andamento do processo de importação do novo conector. Clique no conector para exibir a página de sobrevoo, que contém informações sobre o conector.

## <a name="set-up-a-connector-using-private-keys"></a>Configurar um conector usando chaves privadas

As etapas nesta seção mostram como configurar um conector de Mensagem da Bloomberg usando chaves privadas PGP e SSH. Essa opção de instalação do conector destina-se a organizações que já configuraram um site do SFTP da Bloomberg usando chaves privadas.

### <a name="step-1-obtain-an-ip-address-to-configure-the-bloomberg-sftp-site"></a>Etapa 1: Obter um endereço IP para configurar o site do SFTP da Bloomberg

> [!NOTE]
> Se sua organização configurou anteriormente um site do SFTP da Bloomberg para arquivar dados instantâneos da Bloomberg usando chaves privadas PGP e SSH, você não precisa configurar outro. Você pode especificar o mesmo site SFTP ao criar o conector na Etapa 2.

Se sua organização tiver usado chaves privadas PGP e SSH para configurar um site do SFTP da Bloomberg, você terá que obter um endereço IP e fornecer o suporte ao cliente da Bloomberg. O site do SFTP da Bloomberg deve ser configurado para aceitar solicitações de conexão deste endereço IP. O mesmo endereço IP é usado pelo conector de Mensagens do Bloomberg para se conectar ao site SFTP e transferir dados da Mensagem de Bloomberg para o Microsoft 365.

Para obter o endereço IP:

1. Vá para <https://compliance.microsoft.com> e clique **em Conectores de dados** na nav esquerda.

2. Na página **Conectores de dados** em **Mensagem de Bloomberg,** clique em **Exibir**.

3. Na página **Descrição do produto da mensagem Bloomberg,** clique em **Adicionar conector**

4. Na página **Termos de serviço,** clique em **Aceitar**.

5. Na página Adicionar credenciais para fonte de conteúdo, clique em Quero usar chaves **privadas** **PGP e SSH.**

6. Na etapa 1, clique em **Baixar endereço IP** para salvar uma cópia do arquivo de endereço IP no computador local.

   ![Baixar o endereço IP](../media/BloombergMessageConnectorIPAddress.png)

7. Clique **em Cancelar** para fechar o assistente. Você volta para este assistente na Etapa 2 para criar o conector.

Você precisa trabalhar com o suporte ao cliente da Bloomberg para configurar seu site do SFTP da Bloomberg para aceitar solicitações de conexão deste endereço IP. Entre [em contato com o suporte ao cliente da Bloomberg](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) para assistência.

### <a name="step-2-create-a-bloomberg-message-connector"></a>Etapa 2: Criar um conector de mensagem da Bloomberg

Após a configuração do site do SFTP da Bloomberg, a próxima etapa é criar um conector de Mensagem da Bloomberg no centro de conformidade do Microsoft 365. O conector usa as informações fornecidas para se conectar ao site do SFTP da Bloomberg e transferir mensagens de email para as caixas de correio de usuário correspondentes no Microsoft 365. Para concluir essa etapa, certifique-se de ter cópias das mesmas chaves privadas e senhas que você usou para configurar seu site do SFTP da Bloomberg.

1. Vá para <https://compliance.microsoft.com> e clique **em Conectores de dados** na nav esquerda.

2. Na página **Conectores de dados** em **Mensagem de Bloomberg,** clique em **Exibir**.

3. Na página **Descrição do produto da mensagem Bloomberg,** clique em **Adicionar conector**

4. Na página **Termos de serviço,** clique em **Aceitar**.

5. Na página Adicionar credenciais para fonte de conteúdo, clique em Quero usar chaves **privadas** **PGP e SSH.**

   ![Selecione a opção para usar chaves privadas](../media/BloombergMessagePrivateKeysOption.png)

6. Em Etapa 3, insira as informações necessárias nas caixas a seguir e clique em **Validar conexão**.

      - **Nome:** O nome do conector. Ele deve ser exclusivo em sua organização.

      - **Código firme:** A ID da sua organização que é usada como nome de usuário para o site do SFTP da Bloomberg.

      - **Senha:** A senha do site do SFTP bloomberg da sua organização.

      - **URL SFTP:** A URL do site do SFTP da Bloomberg (por exemplo, `sftp.bloomberg.com` ). Você também pode usar um endereço IP para esse valor.

      - **Porta SFTP:** O número da porta do site do SFTP da Bloomberg. O conector usa essa porta para se conectar ao site SFTP.

      - **Chave privada PGP:** A chave privada PGP para o site do SFTP da Bloomberg. Certifique-se de incluir todo o valor da chave privada, incluindo as linhas inicial e final do bloco de teclas.

      - **Senha da chave PGP:** A senha da chave privada PGP.

      - **Chave privada SSH:** A chave privada SSH para o site do SFTP da Bloomberg. Certifique-se de incluir todo o valor da chave privada, incluindo as linhas inicial e final do bloco de teclas.

      - **Senha da chave SSH:** A senha da chave privada SSH.

7. Depois que a conexão for validada com êxito, clique em **Next**.

8. Na página Mapear usuários da Mensagem bloomberg para usuários do **Microsoft 365,** habilita o mapeamento automático do usuário e fornece mapeamento de usuário personalizado conforme necessário.

   > [!NOTE]
   > O conector importa itens de mensagem para a caixa de correio de um usuário específico. Uma nova pasta chamada **BloombergMessage** é criada na caixa de correio do usuário específico e os itens serão importados para ela. O conector faz usando o valor da *propriedade CorporateEmailAddress.* Cada mensagem de chat contém essa propriedade e a propriedade é preenchida com o endereço de email de cada participante da mensagem de chat. Além do mapeamento automático do usuário usando o valor da propriedade *CorporateEmailAddress,* você também pode definir o mapeamento personalizado carregando um arquivo de mapeamento CSV. O arquivo de mapeamento deve conter o UUID do Bloomberg e o endereço de caixa de correio correspondente do Microsoft 365 para cada usuário. Se você habilitar o mapeamento automático do usuário e fornecer um mapeamento personalizado, para cada item de mensagem, o conector procurará primeiro o arquivo de mapeamento personalizado. Se ele não encontrar um usuário válido do Microsoft 365 que corresponda à UUID bloomberg de um usuário, o conector usará a propriedade *CorporateEmailAddress* do item de chat. Se o conector não encontrar um usuário válido do Microsoft 365 no arquivo de mapeamento personalizado ou na propriedade *CorporateEmailAddress* do item de mensagem, o item não será importado.

9. Clique **em Próximo,** revise suas configurações e clique em **Concluir** para criar o conector.

10. Vá até a **página Conectores de dados** para ver o andamento do processo de importação do novo conector. Clique no conector para exibir a página de sobrevoo, que contém informações sobre o conector.

## <a name="known-issues"></a>Problemas conhecidos

- Threading of Bloomberg Message email imported to Microsoft 365 isn't supported. As mensagens individuais enviadas a uma pessoa são importadas, mas não são apresentadas em uma conversa encadeada. A Microsoft está trabalhando para dar suporte ao threading em versões posteriores do conector de dados da Mensagem do Bloomberg.
