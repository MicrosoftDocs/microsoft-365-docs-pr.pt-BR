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
description: Saiba como os administradores podem configurar e usar um conector de dados para importar e arquivar dados da ferramenta de chat Instantânea do Bloomberg para o Microsoft 365.
ms.openlocfilehash: 6a7f05f592da1b0413d2d40f364f67e7120168b9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904169"
---
# <a name="set-up-a-connector-to-archive-instant-bloomberg-data"></a>Configurar um conector para arquivar dados do Instant Bloomberg

Use um conector nativo no centro de conformidade do Microsoft 365 para importar e arquivar dados de chat de serviços financeiros da ferramenta de colaboração [Instantânea do Bloomberg.](https://www.bloomberg.com/professional/product/collaboration/) Depois de configurar e configurar um conector, ele se conecta ao site FTP seguro (SFTP) da sua organização uma vez por dia, converte o conteúdo das mensagens de chat em um formato de mensagem de email e importa esses itens para caixas de correio no Microsoft 365.

Depois que os dados instantâneos da Bloomberg são armazenados em caixas de correio de usuário, você pode aplicar recursos de conformidade do Microsoft 365, como Retenção de Litígio, Pesquisa de Conteúdo, Arquivamento de In-Place, Auditoria, Conformidade de Comunicação e políticas de retenção do Microsoft 365 aos dados instantâneos do Bloomberg. Por exemplo, você pode pesquisar mensagens de chat instantâneas da Bloomberg usando a Pesquisa de Conteúdo ou associar a caixa de correio que contém os dados instantâneos do Bloomberg com um custodiante em um caso de Descoberta Avançada de Descoberta Eletrônico. Usar um conector Instantâneo da Bloomberg para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a permanecer em conformidade com políticas governamentais e regulatórias.

## <a name="overview-of-archiving-instant-bloomberg-data"></a>Visão geral dos dados instantâneos do Bloomberg de arquivamento

A visão geral a seguir explica o processo de uso de um conector para arquivar dados de chat instantâneos do Bloomberg no Microsoft 365. 

![Processo de importação e arquivamento instantâneo da Bloomberg](../media/InstantBloombergDataArchiving.png)

1. Sua organização trabalha com a Bloomberg para configurar um site do SFTP da Bloomberg. Você também trabalhará com a Bloomberg para configurar o Bloomberg Instantâneo para copiar mensagens de chat para seu site do SFTP da Bloomberg.

2. Uma vez a cada 24 horas, as mensagens de chat do Instant Bloomberg são copiadas para o site do SFTP da Bloomberg.

3. O conector Instantâneo da Bloomberg que você cria no centro de conformidade do Microsoft 365 conecta-se ao site do SFTP da Bloomberg todos os dias e transfere as mensagens de chat das 24 horas anteriores para uma área segura de Armazenamento do Azure no Microsoft Cloud. O conector também converte o conteúdo de uma massagens de chat em um formato de mensagem de email.

4. O conector importa os itens de mensagem de chat para a caixa de correio de um usuário específico. Uma nova pasta chamada InstantBloomberg é criada na caixa de correio do usuário específico e os itens serão importados para ela. O conector faz isso usando o valor da *propriedade CorporateEmailAddress.* Cada mensagem de chat contém essa propriedade, que é preenchida com o endereço de email de cada participante da mensagem de chat. Além do mapeamento automático do usuário usando o valor da propriedade *CorporateEmailAddress,* você também pode definir um mapeamento personalizado carregando um arquivo de mapeamento CSV. Esse arquivo de mapeamento deve conter uma UUID da Bloomberg e o endereço de caixa de correio correspondente do Microsoft 365 para cada usuário. Se você habilitar o mapeamento automático do usuário e fornecer um mapeamento personalizado, para cada item de chat, o conector procurará primeiro o arquivo de mapeamento personalizado. Se ele não encontrar um usuário válido do Microsoft 365 que corresponda à UUID bloomberg de um usuário, o conector usará a propriedade *CorporateEmailAddress* do item de chat. Se o conector não encontrar um usuário válido do Microsoft 365 no arquivo de mapeamento personalizado ou na propriedade *CorporateEmailAddress* do item de chat, o item não será importado.

## <a name="before-you-begin"></a>Antes de começar

Algumas das etapas de implementação necessárias para arquivar dados instantâneos do Bloomberg são externas ao Microsoft 365 e devem ser concluídas antes que você possa criar o conector no centro de conformidade.

- Inscreva-se [em Bloomberg Em Qualquer Lugar](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA). Isso é necessário para que você possa fazer logoff na Bloomberg Em Qualquer Lugar para acessar o site do SFTP da Bloomberg que você precisa configurar e configurar.

- Configurar um site do SFTP da Bloomberg (protocolo de transferência de arquivos seguro). Depois de trabalhar com a Bloomberg para configurar o site do SFTP, os dados do Instant Bloomberg são carregados no site do SFTP todos os dias. O conector criado na Etapa 2 conecta-se a esse site SFTP e transfere os dados de chat para caixas de correio do Microsoft 365. O SFTP também criptografa os dados de chat instantâneos do Bloomberg que são enviados para caixas de correio durante o processo de transferência.

  Para obter informações sobre o SFTP da Bloomberg (também chamado *de BB-SFTP*):

  - Consulte o documento "Padrões de Conectividade SFTP" em [Suporte à Bloomberg](https://www.bloomberg.com/professional/support/documentation/).

  - Entre [em contato com o suporte ao cliente da Bloomberg.](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc)

  Depois de trabalhar com a Bloomberg para configurar um site SFTP, a Bloomberg fornecerá algumas informações a você depois de responder à mensagem de email de implementação do Bloomberg. Salve uma cópia das informações a seguir. Use-o para configurar um conector na Etapa 3.

  - Código firme, que é uma ID da sua organização e é usado para fazer logoff no site do SFTP da Bloomberg.

  - Senha para seu site do SFTP da Bloomberg

  - URL do site do SFTP da Bloomberg (por exemplo, sftp.bloomberg.com)

  - Número da porta para o site do SFTP da Bloomberg

- O conector Instantâneo bloomberg pode importar um total de 200.000 itens em um único dia. Se houver mais de 200.000 itens no site do SFTP, nenhum desses itens será importado para o Microsoft 365.

- O usuário que cria um conector Bloomberg Instantâneo na Etapa 3 (e que baixa as chaves públicas e o endereço IP na Etapa 1) deve receber a função De importação de importação de caixa de correio no Exchange Online. Isso é necessário para adicionar conectores na página **Conectores de** dados no centro de conformidade do Microsoft 365. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função Exportar Importação de Caixa de Correio ao grupo de função Gerenciamento da Organização no Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Exportar Importação de Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte as seções Criar grupos de [função](/Exchange/permissions-exo/role-groups#create-role-groups) ou [Modificar](/Exchange/permissions-exo/role-groups#modify-role-groups) grupos de função no artigo "Gerenciar grupos de função no Exchange Online".

## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>Etapa 1: Obter chaves públicas SSH e PGP

A primeira etapa é obter uma cópia das chaves públicas para o Shell Seguro (SSH) e a PGP (Privacidade Muito Boa). Você usa essas chaves na Etapa 2 para configurar o site do SFTP da Bloomberg para permitir que o conector (criado na Etapa 3) se conecte ao site SFTP e transfira os dados de chat instantâneos do Bloomberg para caixas de correio do Microsoft 365. Você também obtém um endereço IP nesta etapa, que você usa ao configurar o site do SFTP do Bloomberg.

1. Vá até <https://compliance.microsoft.com> e clique em **Conectores de dados**  >  **Instantâneas bloomberg**.

2. Na página Descrição instantânea do produto **Da Bloomberg,** clique em **Adicionar conector**

3. Na página **Termos de serviço,** clique em **Aceitar**.

4. No site Adicionar credenciais do **SFTP do Bloomberg** na etapa 1, clique na tecla **Baixar SSH,** baixe a **tecla PGP** e Baixe links de **endereço IP** para salvar uma cópia de cada arquivo no computador local. Esses arquivos contêm os seguintes itens usados para configurar o site do SFTP do Bloomberg na Etapa 2:

   - Chave pública SSH: essa chave é usada para configurar o Secure Shell (SSH) para habilitar um logon remoto seguro quando o conector se conectar ao site do SFTP da Bloomberg.

   - Chave pública PGP: essa chave é usada para configurar a criptografia de dados transferidos do site do SFTP da Bloomberg para o Microsoft 365.

   - Endereço IP: o site do SFTP da Bloomberg está configurado para aceitar uma solicitação de conexão somente deste endereço IP, que é usado pelo conector Instantâneo do Bloomberg criado na Etapa 3. 

5. Clique **em Cancelar** para fechar o assistente. Você volta para este assistente na Etapa 3 para criar o conector.

## <a name="step-2-configure-the-bloomberg-sftp-site"></a>Etapa 2: Configurar o site do SFTP da Bloomberg

A próxima etapa é usar as chaves públicas SSH e PGP e o endereço IP obtido na Etapa 1 para configurar a autenticação SSH e a criptografia PGP para o site do SFTP da Bloomberg. Isso permite que o conector Instantâneo do Bloomberg criado na Etapa 3 se conecte ao site do SFTP da Bloomberg e transfira dados instantâneos do Bloomberg para o Microsoft 365. Você precisa trabalhar com o suporte ao cliente da Bloomberg para configurar seu site do SFTP da Bloomberg. Entre [em contato com o suporte ao cliente da Bloomberg](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) para assistência. 

> [!IMPORTANT]
> A Bloomberg recomenda que você anexe os três arquivos baixados na Etapa 1 a uma mensagem de email e envie-a para a equipe de suporte ao cliente ao trabalhar com eles para configurar seu site do SFTP da Bloomberg.

## <a name="step-3-create-an-instant-bloomberg-connector"></a>Etapa 3: Criar um conector Instantâneo do Bloomberg

A última etapa é criar um conector Instantâneo da Bloomberg no centro de conformidade do Microsoft 365. O conector usa as informações fornecidas para se conectar ao site do SFTP da Bloomberg e transferir mensagens de chat para as caixas de correio de usuário correspondentes no Microsoft 365.

1. Vá até <https://compliance.microsoft.com> e clique em **Conectores de dados**  >  **Instantâneas bloomberg**.

2. Na página Descrição instantânea do produto **Da Bloomberg,** clique em **Adicionar conector**

3. Na página **Termos de serviço,** clique em **Aceitar**.

4. Na página Adicionar credenciais para o **site do SFTP da Bloomberg,** em Etapa 3, insira as informações necessárias nas caixas a seguir e clique em **Próximo**.

    - **Código firme:** A ID da sua organização que é usada como nome de usuário para o site do SFTP da Bloomberg.

    - **Senha:** Senha para site do SFTP da Bloomberg.

    - **URL SFTP:** A URL do site do SFTP da Bloomberg (por exemplo, sftp.bloomberg.com).

    - **Porta SFTP:** O número da porta para o site do SFTP da Bloomberg. O conector usa essa porta para se conectar ao site SFTP.

5. Na página **Selecionar tipos de dados a serem importados,** selecione os tipos de dados necessários a serem importados além de **Mensagens**

6. Na página **Mapeamento de usuário,** habilita o mapeamento automático do usuário e fornece mapeamento de usuário personalizado conforme necessário

   > [!NOTE]
   > O conector importa os itens de mensagem de chat para a caixa de correio de um usuário específico. Uma nova pasta chamada **InstantBloomberg** é criada na caixa de correio do usuário específico e os itens serão importados para ela. O conector faz usando o valor da *propriedade CorporateEmailAddress.* Cada mensagem de chat contém essa propriedade e a propriedade é preenchida com o endereço de email de cada participante da mensagem de chat. Além do mapeamento automático do usuário usando o valor da propriedade *CorporateEmailAddress,* você também pode definir o mapeamento personalizado carregando um arquivo de mapeamento CSV. O arquivo de mapeamento deve conter o UUID do Bloomberg e o endereço de caixa de correio correspondente do Microsoft 365 para cada usuário. Se você habilitar o mapeamento automático do usuário e fornecer um mapeamento personalizado, para cada item de chat, o conector procurará primeiro o arquivo de mapeamento personalizado. Se ele não encontrar um usuário válido do Microsoft 365 que corresponda à UUID bloomberg de um usuário, o conector usará a propriedade *CorporateEmailAddress* do item de chat. Se o conector não encontrar um usuário válido do Microsoft 365 no arquivo de mapeamento personalizado ou na propriedade *CorporateEmailAddress* do item de chat, o item não será importado.

7. Clique **em Próximo,** revise suas configurações e clique em **Preparar-se** para criar o conector.

8. Vá até a **página Conectores de dados** para ver o andamento do processo de importação do novo conector.