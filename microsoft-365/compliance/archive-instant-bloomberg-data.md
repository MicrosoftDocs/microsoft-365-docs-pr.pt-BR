---
title: Configurar um conector para arquivar dados do Instant Bloomberg
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
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: Saiba como os administradores podem configurar e usar um conector de dados para importar e arquivar dados da ferramenta de bate-papo Instant Bloomberg para o Microsoft 365.
ms.openlocfilehash: b7cd35e0613d9c278e8f36efc194de9dc9b5a5f2
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790089"
---
# <a name="set-up-a-connector-to-archive-instant-bloomberg-data"></a>Configurar um conector para arquivar dados do Instant Bloomberg

Use um conector nativo no centro de conformidade do Microsoft 365 para importar e arquivar dados de chat de serviços financeiros da ferramenta de colaboração [Instant Bloomberg.](https://www.bloomberg.com/professional/product/collaboration/) Depois de configurar um conector, ele se conecta ao site de FTP seguro (SFTP) do Bloomberg da sua organização uma vez por dia, converte o conteúdo das mensagens de chat em um formato de mensagem de email e importa esses itens para caixas de correio no Microsoft 365.

Depois que os dados instantâneos do Bloomberg são armazenados nas caixas de correio do usuário, você pode aplicar recursos de conformidade do Microsoft 365, como Retenção de Litígio, Pesquisa de Conteúdo, Arquivamento do In-Place, Auditoria, Conformidade de Comunicação e políticas de retenção do Microsoft 365 aos dados do Instant Bloomberg. Por exemplo, você pode pesquisar mensagens de chat instantâneas da Bloomberg usando a Pesquisa de Conteúdo ou associar a caixa de correio que contém os dados do Instant Bloomberg com um custodiante em um caso de Descoberta Eletrônico Avançada. Usar um conector instant Bloomberg para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a manter a conformidade com políticas governamentais e regulatórias.

## <a name="overview-of-archiving-instant-bloomberg-data"></a>Visão geral do arquivamento de dados instantâneos da Bloomberg

A visão geral a seguir explica o processo de uso de um conector para arquivar dados de chat instant Bloomberg no Microsoft 365. 

![Processo instantâneo de importação e arquivamento da Bloomberg](../media/InstantBloombergDataArchiving.png)

1. Sua organização trabalha com a Bloomberg para configurar um site do Bloomberg SFTP. Você também trabalhará com a Bloomberg para configurar o Instant Bloomberg para copiar mensagens de chat para seu site do Bloomberg SFTP.

2. Uma vez a cada 24 horas, as mensagens de chat do Instant Bloomberg são copiadas para o site da Bloomberg SFTP.

3. O conector instantâneo do Bloomberg criado no centro de conformidade do Microsoft 365 conecta-se ao site do SFTP da Bloomberg todos os dias e transfere as mensagens de chat das últimas 24 horas para uma área de Armazenamento do Azure segura no Microsoft Cloud. O conector também converte o conteúdo de um chat em um formato de mensagem de email.

4. O conector importa os itens de mensagem de chat para a caixa de correio de um usuário específico. Uma nova pasta chamada InstantBloomberg é criada na caixa de correio do usuário específico e os itens serão importados para ela. O conector faz isso usando o valor da *propriedade CorporateEmailAddress.* Cada mensagem de chat contém essa propriedade, que é preenchida com o endereço de email de cada participante da mensagem de chat. Além do mapeamento automático de usuário usando o valor da propriedade *CorporateEmailAddress,* você também pode definir um mapeamento personalizado carregando um arquivo de mapeamento CSV. Esse arquivo de mapeamento deve conter uma UUID da Bloomberg e o endereço de caixa de correio correspondente do Microsoft 365 para cada usuário. Se você habilitar o mapeamento automático de usuários e fornecer um mapeamento personalizado, para cada item de chat, o conector primeiro procurará o arquivo de mapeamento personalizado. Se não encontrar um usuário válido do Microsoft 365 que corresponda à UUID do Bloomberg de um usuário, o conector usará a propriedade *CorporateEmailAddress* do item de chat. Se o conector não encontrar um usuário válido do Microsoft 365 no arquivo de mapeamento personalizado ou na propriedade *CorporateEmailAddress* do item de chat, o item não será importado.

## <a name="before-you-begin"></a>Antes de começar

Algumas das etapas de implementação necessárias para arquivar dados do Instant Bloomberg são externas ao Microsoft 365 e devem ser concluídas antes que você possa criar o conector no centro de conformidade.

- Assine o [Bloomberg em Qualquer Lugar.](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA) Isso é necessário para que você possa entrar na Bloomberg Anywhere para acessar o site da Bloomberg SFTP que você precisa configurar e configurar.

- Configurar um site do Bloomberg SFTP (protocolo de transferência de arquivos seguro). Depois de trabalhar com a Bloomberg para configurar o site SFTP, os dados do Instant Bloomberg são carregados no site SFTP todos os dias. O conector criado na Etapa 2 conecta-se a esse site SFTP e transfere os dados de chat para as caixas de correio do Microsoft 365. A SFTP também criptografa os dados de bate-papo instant Bloomberg enviados às caixas de correio durante o processo de transferência.

  Para obter informações sobre o Bloomberg SFTP (também *chamado de BB-SFTP*):

  - Consulte o documento "Padrões de Conectividade SFTP" no [Suporte da Bloomberg.](https://www.bloomberg.com/professional/support/documentation/)

  - Entre [em contato com o suporte ao cliente da Bloomberg.](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc)

  Depois de trabalhar com a Bloomberg para configurar um site SFTP, a Bloomberg fornecerá algumas informações a você depois de responder à mensagem de email de implementação da Bloomberg. Salve uma cópia das informações a seguir. Use-o para configurar um conector na Etapa 3.

  - Código de empresa, que é uma ID da sua organização e é usado para entrar no site do Bloomberg SFTP.

  - Senha para seu site do Bloomberg SFTP

  - URL do site do Bloomberg SFTP (por exemplo, sftp.bloomberg.com)

  - Número da porta do site do Bloomberg SFTP

- O conector instant Bloomberg pode importar um total de 200.000 itens em um único dia. Se houver mais de 200.000 itens no site SFTP, nenhum desses itens será importado para o Microsoft 365.

- O usuário que cria um conector Instant Bloomberg na Etapa 3 (e que baixa as chaves públicas e o endereço IP na Etapa 1) deve receber a função Importar Exportar Caixa de Correio no Exchange Online. Isso é necessário para adicionar conectores na página Conectores **de dados** no centro de conformidade do Microsoft 365. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função Importar Exportar Caixa de Correio ao grupo de função Gerenciamento da Organização no Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Importar Exportar Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) as [seções](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) Criar grupos de função ou Modificar grupos de função no artigo "Gerenciar grupos de função no Exchange Online".

## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>Etapa 1: Obter chaves públicas SSH e PGP

A primeira etapa é obter uma cópia das chaves públicas para o Shell Seguro (SSH) e o PGP (Privacidade Bastante Boa). Use essas chaves na Etapa 2 para configurar o site do Bloomberg SFTP para permitir que o conector (criado na Etapa 3) se conecte ao site SFTP e transfira os dados de chat instant Bloomberg para caixas de correio do Microsoft 365. Você também obtém um endereço IP nesta etapa, que você usa ao configurar o site do Bloomberg SFTP.

1. Vá para <https://compliance.microsoft.com> e clique em **Conectores de dados** instant  >  **Bloomberg**.

2. Na página **de descrição do produto Instant Bloomberg,** clique em **Adicionar conector**

3. Na página **Termos de serviço,** clique em **Aceitar**.

4. No site Add **credentials for Bloomberg SFTP,** na etapa 1, clique na chave SSH de **Download,** baixe a chave **PGP** e baixe os links de endereço **IP** para salvar uma cópia de cada arquivo no computador local. Esses arquivos contêm os seguintes itens que são usados para configurar o site da Bloomberg SFTP na Etapa 2:

   - Chave pública SSH: essa chave é usada para configurar o Shell seguro (SSH) para habilitar um logon remoto seguro quando o conector se conectar ao site do Bloomberg SFTP.

   - Chave pública PGP: essa chave é usada para configurar a criptografia de dados transferidos do site do Bloomberg SFTP para o Microsoft 365.

   - Endereço IP: O site do Bloomberg SFTP está configurado para aceitar uma solicitação de conexão somente deste endereço IP, que é usado pelo conector Instant Bloomberg criado na Etapa 3. 

5. Clique **em Cancelar** para fechar o assistente. Você volta para este assistente na Etapa 3 para criar o conector.

## <a name="step-2-configure-the-bloomberg-sftp-site"></a>Etapa 2: Configurar o site do Bloomberg SFTP

A próxima etapa é usar as chaves públicas SSH e PGP e o endereço IP obtido na Etapa 1 para configurar a autenticação SSH e a criptografia PGP para o site do Bloomberg SFTP. Isso permite que o conector instantâneo da Bloomberg criado na Etapa 3 se conecte ao site do Bloomberg SFTP e transfira dados do Instant Bloomberg para o Microsoft 365. Você precisa trabalhar com o suporte ao cliente da Bloomberg para configurar seu site do Bloomberg SFTP. Entre em [contato com o suporte ao cliente da Bloomberg](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) para assistência. 

> [!IMPORTANT]
> A Bloomberg recomenda que você anexe os três arquivos baixados na Etapa 1 a uma mensagem de email e envie-os à equipe de atendimento ao cliente ao trabalhar com eles para configurar seu site do Bloomberg SFTP.

## <a name="step-3-create-an-instant-bloomberg-connector"></a>Etapa 3: Criar um conector instant Bloomberg

A última etapa é criar um conector instant Bloomberg no centro de conformidade do Microsoft 365. O conector usa as informações que você fornece para se conectar ao site da Bloomberg SFTP e transferir mensagens de chat para as caixas de correio de usuário correspondentes no Microsoft 365.

1. Vá para <https://compliance.microsoft.com> e clique em **Conectores de dados** instant  >  **Bloomberg**.

2. Na página **de descrição do produto Instant Bloomberg,** clique em **Adicionar conector**

3. Na página **Termos de serviço,** clique em **Aceitar**.

4. Na página Adicionar credenciais para o site do **Bloomberg SFTP,** em Etapa 3, insira as informações necessárias nas caixas a seguir e clique em **Próximo.**

    - **Código da empresa:** A ID da sua organização que é usada como o nome de usuário do site da Bloomberg SFTP.

    - **Senha:** Senha para o site da Bloomberg SFTP.

    - **URL SFTP:** A URL do site da Bloomberg SFTP (por exemplo, sftp.bloomberg.com).

    - **Porta SFTP:** O número da porta do site do Bloomberg SFTP. O conector usa essa porta para se conectar ao site SFTP.

5. Na página **Selecionar tipos de dados a serem importados,** selecione os tipos de dados necessários a serem importados além das **Mensagens**

6. Na página **Mapeamento de usuários,** habilita o mapeamento automático de usuário e fornece mapeamento de usuário personalizado conforme necessário

   > [!NOTE]
   > O conector importa os itens de mensagem de chat para a caixa de correio de um usuário específico. Uma nova pasta chamada **InstantBloomberg** é criada na caixa de correio do usuário específico e os itens serão importados para ela. O conector usa o valor da *propriedade CorporateEmailAddress.* Cada mensagem de chat contém essa propriedade, e a propriedade é preenchida com o endereço de email de cada participante da mensagem de chat. Além do mapeamento automático de usuário usando o valor da propriedade *CorporateEmailAddress,* você também pode definir o mapeamento personalizado carregando um arquivo de mapeamento CSV. O arquivo de mapeamento deve conter a UUID da Bloomberg e o endereço de caixa de correio do Microsoft 365 correspondente para cada usuário. Se você habilitar o mapeamento automático de usuário e fornecer um mapeamento personalizado, para cada item de chat, o conector primeiro procurará o arquivo de mapeamento personalizado. Se não encontrar um usuário válido do Microsoft 365 que corresponda à UUID do Bloomberg de um usuário, o conector usará a propriedade *CorporateEmailAddress* do item de chat. Se o conector não encontrar um usuário válido do Microsoft 365 no arquivo de mapeamento personalizado ou na propriedade *CorporateEmailAddress* do item de chat, o item não será importado.

7. Clique **em Próximo,** revise suas configurações e clique em **Preparar** para criar o conector.

8. Vá para a **página Conectores de dados** para ver o progresso do processo de importação do novo conector.
