---
title: Configurar um conector para arquivar dados do Instant Bloomberg
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Os administradores podem configurar um conector nativo para importar dados da ferramenta de chat do Bloomberg para o Office 365. Isso permite que você arquive dados de fontes de dados de terceiros no Office 365 para que possa usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar os dados de terceiros da sua organização.
ms.openlocfilehash: 55b0acf6a2643fed4a994604e92e4c0e218da5d9
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40807746"
---
# <a name="set-up-a-connector-to-archive-instant-bloomberg-data"></a>Configurar um conector para arquivar dados do Instant Bloomberg

Use um conector nativo no centro de conformidade & segurança no Office 365 para importar e arquivar dados de chat de serviços financeiros da ferramenta de colaboração do [Bloomberg](https://www.bloomberg.com/professional/product/collaboration/) . Depois de configurar e configurar um conector, ele se conecta ao site da sua organização (SFTP) uma vez a cada dia, converte o conteúdo de mensagens de chat em um formato de mensagem de email e, em seguida, importa esses itens para caixas de correio no Office 365.

Depois que os dados do Bloomberg instantâneos são armazenados nas caixas de correio do usuário, você pode aplicar recursos de conformidade do Office 365, como retenção de litígio, pesquisa de conteúdo, arquivamento in-loco, auditoria, [conformidade de comunicação](communication-compliance.md)e políticas de retenção do Office 365 a dados do Bloomberg. Por exemplo, você pode pesquisar mensagens de chat do Bloomberg instantâneas usando a pesquisa de conteúdo ou associar a caixa de correio que contém os dados do Bloomberg instantâneos a um funcionário em uma caixa de descoberta eletrônica avançada. O uso de um conector de Bloomberg instantâneo para importar e arquivar dados no Office 365 pode ajudar sua organização a se manter em conformidade com as políticas governamentais e regulamentares.

## <a name="overview-of-archiving-instant-bloomberg-data"></a>Visão geral do arquivamento de dados instantâneos do Bloomberg

A visão geral a seguir explica o processo de uso de um conector para arquivar dados de chat instantânea do Bloomberg no Office 365. 

![Processo de importação e arquivamento do Bloomberg instantâneo](media/InstantBloombergDataArchiving.png)

1. Sua organização trabalha com o Bloomberg para configurar um site do Bloomberg SFTP. Você também trabalhará com o Bloomberg para configurar o Bloomberg para copiar mensagens de chat para seu site do Bloomberg SFTP.

2. Uma vez a cada 24 horas, as mensagens de bate-papo do Bloomberg imediato são copiadas para o site Bloomberg SFTP.
    
3. O conector de Bloomberg instantâneo que você cria no centro de conformidade & segurança se conecta ao site do Bloomberg SFTP todos os dias e transfere as mensagens de chat das últimas 24 horas para uma área de armazenamento do Azure segura na nuvem da Microsoft. O conector também converte o conteúdo de um massage de chat em um formato de mensagem de email.
    
4. O conector importa os itens de mensagem de chat para a caixa de correio de um usuário específico ou para uma caixa de correio alternativa. O conector faz usando o valor da propriedade *CorporateEmailAddress* . Cada mensagem de chat contém essa propriedade, que é preenchida com o endereço de email de cada participante da mensagem de chat. Se um item é importado para uma caixa de correio de usuário específica ou para a caixa de correio alternativa com base nos seguintes critérios:
    
    a. **Itens que têm um valor na propriedade CorporateEmailAddress que corresponde a uma conta de usuário do Office 365:** Se o conector puder associar o endereço de email na propriedade *CorporateEmailAddress* a uma conta de usuário específica no Office 365, o item será copiado para a pasta caixa de entrada na caixa de correio do Office 365 do usuário.
    
    b. **Itens que têm um valor na propriedade CorporateEmailAddress que não corresponde a uma conta de usuário do Office 365:** Se o conector não puder associar um endereço de email na propriedade *CorporateEmailAddress* a uma conta de usuário específica no Office 365, o item será copiado para a pasta caixa de entrada de uma caixa de correio alternativa "catch-all" no Office 365.

## <a name="before-you-begin"></a>Antes de começar

Muitas das etapas de implementação necessárias para arquivar dados instantâneos do Bloomberg são externas para o Office 365 e devem ser concluídas para que você possa criar o conector no centro de conformidade de & de segurança.

- Sua organização deve dar o consentimento para permitir que o serviço de importação do Office 365 acesse dados de caixa de correio em sua organização. Para concordar com essa solicitação, [acesse esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), entre com as credenciais de um administrador global do Office 365 e aceite a solicitação. Você precisa concluir esta etapa para poder criar com êxito o conector do Bloomberg instantâneo na etapa 3.

- Inscreva-se no [Bloomberg em qualquer lugar](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA). Isso é necessário para que você possa fazer logon no Bloomberg em qualquer lugar para acessar o site do Bloomberg SFTP que você precisa configurar e configurar.

- Configurar um site Bloomberg SFTP (protocolo de transferência segura de arquivos). Depois de trabalhar com o Bloomberg para configurar o site SFTP, os dados do Bloomberg imediato são carregados para o site do SFTP todos os dias. O conector que você cria na etapa 2 se conecta a esse site SFTP e transfere os dados de chat para caixas de correio do Office 365. O SFTP também criptografa os dados de chat do Bloomberg que são enviados para as caixas de correio do Office 365 durante o processo de transferência.

    Para obter informações sobre o Bloomberg SFTP (também chamado *de BB-SFTP*):

    - Consulte o documento "padrões de conectividade SFTP" no [suporte do Bloomberg](https://www.bloomberg.com/professional/support/documentation/).
    
    - Contatar o [suporte ao cliente do Bloomberg](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc).

    Depois de trabalhar com o Bloomberg para configurar um site SFTP, o Bloomberg fornecerá algumas informações depois que você responder à mensagem de email de implementação do Bloomberg. Salve uma cópia das informações a seguir. Você pode usá-lo para configurar um conector na etapa 3.

    - O código da empresa, que é uma ID da sua organização e é usado para fazer logon no site do Bloomberg SFTP.

    - Senha para seu site do Bloomberg SFTP

    - URL para o site do Bloomberg SFTP (por exemplo, sftp.bloomberg.com)

    - Número de porta para o site Bloomberg SFTP

- O usuário que cria um conector de Bloomberg instantâneo na etapa 3 (e quem baixa as chaves públicas e o endereço IP na etapa 1) deve receber a função de exportação de importação de caixa de correio no Exchange Online. Isso é necessário para acessar a página **arquivar dados** de terceiros no centro de conformidade de & de segurança. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função de exportação de importação de caixa de correio ao grupo de funções Gerenciamento da organização no Exchange Online. Ou você pode criar um grupo de função, atribua a função de exportação de importação de caixa de correio e, em seguida, adicione os usuários apropriados como membros. Para obter mais informações, consulte as seções [criar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) ou [modificar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) no artigo "gerenciar grupos de função no Exchange Online".

## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>Etapa 1: obter as chaves públicas SSH e PGP

A primeira etapa é obter uma cópia das chaves públicas para SSH (Secure Shell) e PGP (boa privacidade). Use essas chaves na etapa 2 para configurar o site do Bloomberg SFTP para permitir que o conector (que você criou na etapa 3) se conecte ao site SFTP e transfira os dados de chat do Bloomberg para o Office 365 caixas de correio. Você também obtém um endereço IP nesta etapa, que você usa ao configurar o site do Bloomberg SFTP.

1. Vá para <https://protection.office.com> e, em seguida, clique em importação > de **governança \> de informações****arquivar dados de terceiros**.

2. Na página **arquivar dados de terceiros** , clique em **Adicionar um conector**e, em seguida, clique em **Bloomberg instantâneo**.

3. Na página **termos de serviço** , clique em **aceitar**.

4. No **site adicionar credenciais para Bloomberg SFTP** , em etapa 1, clique na **chave de download SSH**, **baixar a chave PGP**e baixar links de **endereço IP** para salvar uma cópia de cada arquivo no computador local. Esses arquivos contêm os seguintes itens que são usados para configurar o site do Bloomberg SFTP na etapa 2:

   - Chave pública SSH: essa chave é usada para configurar o Secure Shell (SSH) para habilitar um logon remoto seguro quando o conector se conecta ao site do Bloomberg SFTP.

   - Chave pública do PGP: essa chave é usada para configurar a criptografia de dados que são transferidos do site Bloomberg SFTP para o Office 365.

   - Endereço IP: o site do Bloomberg SFTP é configurado para aceitar uma solicitação de conexão apenas desse endereço IP, que é usado pelo conector do Bloomberg instantâneo criado na etapa 3. 

5. Clique em **Cancelar** para fechar o assistente. Você volta para este assistente na etapa 3 para criar o conector.

## <a name="step-2-configure-the-bloomberg-sftp-site"></a>Etapa 2: configurar o site do Bloomberg SFTP

A próxima etapa é usar as chaves públicas SSH e PGP e o endereço IP obtido na etapa 1 para configurar a autenticação SSH e a criptografia PGP para o site Bloomberg SFTP. Isso permite que o conector do Bloomberg instantâneo criado na etapa 3 se conecte ao site Bloomberg SFTP e transfira dados de Bloomberg instantâneos para o Office 365. Você precisa trabalhar com o suporte ao cliente Bloomberg para configurar seu site do Bloomberg SFTP. Entre em contato com o [suporte ao cliente Bloomberg](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) para obter assistência. 

> [!IMPORTANT]
> O Bloomberg recomenda que você anexe os três arquivos baixados na etapa 1 a uma mensagem de email e envie-o à sua equipe de suporte ao cliente ao trabalhar com eles para configurar seu site do Bloomberg SFTP.

## <a name="step-3-create-an-instant-bloomberg-connector"></a>Etapa 3: criar um conector de Bloomberg instantâneo

A última etapa é criar um conector de Bloomberg instantâneo no centro de conformidade de & de segurança. O conector usa as informações que você fornece para se conectar ao site do Bloomberg SFTP e transferir mensagens de chat para as caixas de correio de usuário correspondentes no Office 365. 

1. Vá para <https://protection.office.com> e, em seguida, clique em importação > de **governança \> de informações****arquivar dados de terceiros**.

2. Na página **arquivar dados de terceiros** , clique em **Adicionar um conector**e, em seguida, clique em **Bloomberg instantâneo**.

3. Na página **termos de serviço** , clique em **aceitar**.

4. Na página **Adicionar credenciais para o site do Bloomberg SFTP** , em etapa 3, insira as informações necessárias nas caixas a seguir e clique em **Avançar**.

    - **Código da empresa:** A ID da sua organização e usada como o nome de usuário para o site Bloomberg SFTP.

    - **Senha:** Senha para o site do Bloomberg SFTP

    - **URL de SFTP:** A URL para o site do Bloomberg SFTP (por exemplo, sftp.bloomberg.com).

    - **Porta SFTP:** O número da porta para o site Bloomberg SFTP. O conector usa essa porta para se conectar ao site SFTP.

5. Na página de **caixa de correio alternativa** , digite o endereço de email de uma caixa de correio que é usada para armazenar as mensagens de chat do Bloomberg instantâneo que não estão associados a uma caixa de correio de usuário em sua organização.

   > [!NOTE]
   > Cada mensagem de chat em todas as conversas no Bloomberg instantâneo inclui uma propriedade chamada *CorporateEmailAddress*, que contém o endereço de email da sua organização para o participante do chat. Durante o processo de importação, o conector tenta importar mensagens de chat para uma caixa de correio de usuário no Office 365 que tenha os mesmos endereços de email que correspondem ao da propriedade *CorporateEmailAddress* . Se não houver uma caixa de correio do Office 365 com o mesmo endereço da propriedade *CorporateEmailAddress* , o conector importa a mensagem de chat para a caixa de correio alternativa que você especificar nessa página.

6. Clique em **Avançar**, revise suas configurações e clique em **preparar** para criar o conector.

7. Vá para a página **arquivar dados** de terceiros para ver o andamento do processo de importação para o novo conector.
