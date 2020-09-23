---
title: Configurar um conector para arquivar dados de mensagem do Bloomberg
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
description: Os administradores podem configurar um conector de dados para importar e arquivar dados da ferramenta de email de mensagem do Bloomberg para o Microsoft 365. Isso permite que você arquive dados de fontes de dados de terceiros no Microsoft 365 para que possa usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar os dados de terceiros da sua organização.
ms.openlocfilehash: cc14bd9d76e04fe3e285f63b5dce9dbb1f680794
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200224"
---
# <a name="set-up-a-connector-to-archive-bloomberg-message-data"></a>Configurar um conector para arquivar dados de mensagem do Bloomberg

Use um conector de dados no centro de conformidade da Microsoft 365 para importar e arquivar dados de email de serviços financeiros da ferramenta de colaboração de [mensagens do Bloomberg](https://www.bloomberg.com/professional/product/collaboration/) . Depois de configurar e configurar um conector, ele se conecta ao site do Bloomberg Secure FTP (SFTP) de sua organização uma vez a cada dia e importa itens de email para caixas de correio no Microsoft 365.

Depois que o Bloomberg Message data é armazenado nas caixas de correio do usuário, você pode aplicar recursos de conformidade do Microsoft 365, como retenção de litígio, pesquisa de conteúdo, arquivamento in-loco, auditoria, conformidade de comunicação e políticas de retenção da Microsoft 365 para dados de mensagem do Bloomberg. Por exemplo, você pode pesquisar emails de mensagens do Bloomberg usando a ferramenta de pesquisa de conteúdo ou associar a caixa de correio que contém os dados de mensagem do Bloomberg a um funcionário em uma caixa de descoberta eletrônica avançada. O uso de um conector de mensagens do Bloomberg para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a se manter em conformidade com as políticas governamentais e regulamentares.

## <a name="overview-of-archiving-bloomberg-message-data"></a>Visão geral do arquivamento de dados de mensagem do Bloomberg

A visão geral a seguir explica o processo de usar um conector para arquivar dados de mensagem do Bloomberg no Microsoft 365.

![Processo de importação e arquivamento de mensagens do Bloomberg](../media/BloombergMessageArchiving.png)

1. Sua organização trabalha com o Bloomberg para configurar um site do Bloomberg SFTP. Você também trabalhará com o Bloomberg para configurar o Bloomberg para copiar mensagens de email no site do Bloomberg SFTP.

2. Uma vez a cada 24 horas, as mensagens de email da mensagem do Bloomberg são copiadas para o site Bloomberg SFTP.

3. O conector de mensagens do Bloomberg que você cria no centro de conformidade da Microsoft 365 conecta-se ao site do Bloomberg SFTP todos os dias e transfere as mensagens de email das últimas 24 horas para uma área de armazenamento do Azure segura na nuvem da Microsoft.

4. O conector importa os itens de mensagem de email para a caixa de correio de um usuário específico. Uma nova pasta chamada BloombergMessage será criada na caixa de correio do usuário específico e os itens serão importados para ela. 

   O conector faz isso usando o valor da propriedade CorporateEmailAddress. Cada mensagem de email contém essa propriedade, que é preenchida com o endereço de email de cada participante da mensagem de email. Além do mapeamento automático de usuários usando o valor da propriedade *CorporateEmailAddress* , você também pode definir um mapeamento personalizado carregando um arquivo de mapeamento CSV. Este arquivo de mapeamento contém um Bloomberg UUID e o endereço de caixa de correio do Microsoft 365 correspondente para cada usuário da sua organização. Se você habilitar o mapeamento automático de usuários e fornecer um mapeamento personalizado, para cada item de email, o conector examinará primeiro o arquivo de mapeamento personalizado. Se não encontrar um usuário válido do Microsoft 365 que corresponda ao UUID do Bloomberg de um usuário, o conector usará a propriedade *CorporateEmailAddress* do item de email. Se o conector não localizar um usuário válido do Microsoft 365 no arquivo de mapeamento personalizado ou na propriedade *CorporateEmailAddress* do item de email, o item não será importado.

## <a name="before-you-begin"></a>Antes de começar

Algumas das etapas de implementação necessárias para arquivar dados de mensagem do Bloomberg são externas para o Microsoft 365 e devem ser concluídas para que você possa criar o conector no centro de conformidade.

- Sua organização deve dar o consentimento para permitir que o serviço de importação do Office 365 acesse dados de caixa de correio em sua organização. Para concordar com essa solicitação, [acesse esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), entre com as credenciais de um administrador global do Office 365 e aceite a solicitação. Você precisa concluir esta etapa para poder criar com êxito o conector de mensagens do Bloomberg na etapa 3.

- Inscreva-se no [Bloomberg em qualquer lugar](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA). Isso é necessário para que você possa fazer logon no Bloomberg em qualquer lugar para acessar o site do Bloomberg SFTP que você precisa configurar e configurar.

- Configurar um site Bloomberg SFTP (protocolo de transferência segura de arquivos). Depois de trabalhar com o Bloomberg para configurar o site SFTP, os dados da mensagem do Bloomberg são carregados no site do SFTP todos os dias. O conector que você cria na etapa 2 se conecta a esse site SFTP e transfere os dados de email para caixas de correio do Microsoft 365. O SFTP também criptografa os dados de mensagem do Bloomberg que são enviados para caixas de correio durante o processo de transferência.

  Para obter informações sobre o Bloomberg SFTP (também chamado *de BB-SFTP*):

  - Consulte o documento "padrões de conectividade SFTP" no [suporte do Bloomberg](https://www.bloomberg.com/professional/support/documentation/).

  - Contatar o [suporte ao cliente do Bloomberg](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc).

   > [!NOTE]
   > Se sua organização já implantou um conector para arquivar dados instantâneos do Bloomberg, você não precisa configurar outro site SFTP. Você pode usar o mesmo site SFTP para o Bloomberg Message Connector.

- Depois de trabalhar com o Bloomberg para configurar um site SFTP, o Bloomberg fornecerá algumas informações depois que você responder à mensagem de email de implementação do Bloomberg. Salve uma cópia das informações a seguir. Você pode usá-lo para configurar um conector na etapa 3.

  - O código da empresa, que é uma ID da sua organização e é usado para fazer logon no site do Bloomberg SFTP.

  - Senha para seu site do Bloomberg SFTP

  - URL para o site do Bloomberg SFTP (por exemplo, sftp.bloomberg.com). Além disso, o Bloomberg também pode fornecer um endereço IP correspondente para o site do Bloomberg SFTP, que também pode ser usado para configurar o conector.

  - Número de porta para o site Bloomberg SFTP

- O usuário que cria um conector de mensagens do Bloomberg na etapa 3 (e quem baixa as chaves públicas e o endereço IP na etapa 1) deve receber a função de exportação de importação de caixa de correio no Exchange Online. Isso é necessário para adicionar conectores na página **conectores de dados** no centro de conformidade do Microsoft 365. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função de exportação de importação de caixa de correio ao grupo de funções Gerenciamento da organização no Exchange Online. Ou você pode criar um grupo de função, atribua a função de exportação de importação de caixa de correio e, em seguida, adicione os usuários apropriados como membros. Para obter mais informações, consulte as seções [criar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) ou [modificar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) no artigo "gerenciar grupos de função no Exchange Online".


## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>Etapa 1: obter as chaves públicas SSH e PGP

A primeira etapa é obter uma cópia das chaves públicas para SSH (Secure Shell) e PGP (boa privacidade). Use essas chaves na etapa 2 para configurar o site do Bloomberg SFTP para permitir que o conector (que você criou na etapa 3) se conecte ao site SFTP e transfira os dados de email de mensagem do Bloomberg para as caixas de correio do Microsoft 365. Você também obtém um endereço IP nesta etapa, que você usa ao configurar o site do Bloomberg SFTP.

1. Vá para [ https://compliance.microsoft.com\ ] ( https://compliance.microsoft.com) e clique em **conectores de dados** no painel de navegação esquerdo.

2. Na página **conectores de dados** sob **mensagem do Bloomberg**, clique em **Exibir**.

3. Na página descrição do produto de **mensagem do Bloomberg** , clique em **Adicionar conector**

4. Na página **termos de serviço** , clique em **aceitar**.

5. No **site adicionar credenciais para Bloomberg SFTP** , em etapa 1, clique na **chave de download SSH**, **baixar a chave PGP**e baixar links de **endereço IP** para salvar uma cópia de cada arquivo no computador local. Esses arquivos contêm os seguintes itens que são usados para configurar o site do Bloomberg SFTP na etapa 2:

   - Chave pública SSH: essa chave é usada para configurar o Secure Shell (SSH) para habilitar um logon remoto seguro quando o conector se conecta ao site do Bloomberg SFTP.

   - Chave pública do PGP: essa chave é usada para configurar a criptografia de dados que são transferidos do site do Bloomberg SFTP para o Microsoft 365.

   - Endereço IP: o site do Bloomberg SFTP é configurado para aceitar uma solicitação de conexão apenas desse endereço IP, que é usado pelo conector de mensagens do Bloomberg que você criou na etapa 3.

6. Clique em **Cancelar** para fechar o assistente. Você volta para este assistente na etapa 3 para criar o conector.

## <a name="step-2-configure-the-bloomberg-sftp-site"></a>Etapa 2: configurar o site do Bloomberg SFTP

> [!NOTE]
> Conforme mencionado anteriormente, se você for a organização configurou anteriormente um site do Bloomberg SFTP para arquivar dados de Bloomberg instantâneos, não será necessário configurar outro. Você pode especificar o mesmo site SFTP ao criar o conector na etapa 3.

A próxima etapa é usar as chaves públicas SSH e PGP e o endereço IP obtido na etapa 1 para configurar a autenticação SSH e a criptografia PGP para o site Bloomberg SFTP. Isso permite que o conector de mensagens do Bloomberg que você criou na etapa 3 se conecte ao site Bloomberg SFTP e transfira dados de mensagem do Bloomberg para o Microsoft 365. Você precisa trabalhar com o suporte ao cliente Bloomberg para configurar seu site do Bloomberg SFTP. Entre em contato com o [suporte ao cliente Bloomberg](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) para obter assistência.

> [!IMPORTANT]
> O Bloomberg recomenda que você anexe os três arquivos baixados na etapa 1 a uma mensagem de email e envie-o à sua equipe de suporte ao cliente ao trabalhar com eles para configurar seu site do Bloomberg SFTP.

## <a name="step-3-create-a-bloomberg-message-connector"></a>Etapa 3: criar um conector de mensagens do Bloomberg

A última etapa é criar um conector de mensagens do Bloomberg no centro de conformidade da Microsoft 365. O conector usa as informações que você fornece para se conectar ao site do Bloomberg SFTP e transferir mensagens de email para as caixas de correio de usuário correspondentes no Microsoft 365.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique em **conectores de dados** no painel de navegação esquerdo.

2. Na página **conectores de dados** sob **mensagem do Bloomberg**, clique em **Exibir**.

3. Na página descrição do produto de **mensagem do Bloomberg** , clique em **Adicionar conector**

4. Na página **termos de serviço** , clique em **aceitar**.

5. Na página **Adicionar credenciais para o site do Bloomberg SFTP** , em etapa 3, insira as informações necessárias nas caixas a seguir e clique em **Avançar**.

      - **Código da empresa:** A ID da sua organização que é usada como o nome de usuário para o site do Bloomberg SFTP.

      - **Senha:** A senha do site do Bloomberg SFTP da sua organização.

      - **URL de SFTP:** A URL do site do Bloomberg SFTP (por exemplo, sftp.bloomberg.com).

      - **Porta SFTP:** O número da porta do site Bloomberg SFTP. O conector usa essa porta para se conectar ao site SFTP.

6. Na página de **mapeamento do usuário** , habilite o mapeamento automático de usuários e forneça mapeamento de usuário personalizado conforme necessário

7. Clique em **Avançar**, revise suas configurações e clique em preparar para criar o conector.

8. Vá para a página **conectores de dados** para ver o andamento do processo de importação para o novo conector.

## <a name="known-issues"></a>Problemas conhecidos

- Não há suporte para o encadeamento de emails de mensagem do Bloomberg para o Microsoft 365. Mensagens individuais enviadas a uma pessoa são importadas, mas não são apresentadas em uma conversa encadeada. A Microsoft está trabalhando para dar suporte ao encadeamento em versões posteriores do conector de dados de mensagem do Bloomberg.
