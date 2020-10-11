---
title: Configurar um conector para arquivar dados do Jive no Microsoft 365
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
description: Os administradores podem configurar um conector para importar e arquivar dados do Jive do Globanet no Microsoft 365. Esse conector permite que você arquive dados de fontes de dados de terceiros no Microsoft 365 para que possa usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar os dados de terceiros da sua organização.
ms.openlocfilehash: d04a211e97ddce18165fe62e46f76303b4590524
ms.sourcegitcommit: ae3aa7f29be16d08950cf23cad489bc069aa8617
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48409081"
---
# <a name="set-up-a-connector-to-archive-jive-data-preview"></a>Configurar um conector para arquivar dados do Jive (visualização)

Use um conector Globanet no centro de conformidade da Microsoft 365 para importar e arquivar dados da plataforma de colaboração para caixas de correio do usuário na sua organização do Microsoft 365. O Globanet fornece um conector [Jive](https://globanet.com/jive/) que é configurado para capturar itens da fonte de dados de terceiros (em uma base regular) e, em seguida, importar esses itens para o Microsoft 365. O conector converte conteúdo como mensagens de email, chats e anexos de uma conta do Jive de um usuário em um formato de mensagem de email e, em seguida, importa esses itens para a caixa de correio do usuário no Microsoft 365.

Depois que os dados do Jive são armazenados nas caixas de correio do usuário, você pode aplicar recursos de conformidade do Microsoft 365, como retenção de litígio, eDiscovery, políticas de retenção e rótulos de retenção e conformidade de comunicação. O uso de um conector Jive para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a se manter em conformidade com as políticas governamentais e regulamentares.

## <a name="overview-of-archiving-jive-data"></a>Visão geral do arquivamento de dados do Jive

A visão geral a seguir explica o processo de usar um conector para arquivar os dados do Jive no Microsoft 365.

![Fluxo de trabalho de arquivamento para dados do Jive](../media/JiveConnectorWorkflow.png)

1. Sua organização trabalha com o Jive para configurar e configurar um site jive.

2. Uma vez a cada 24 horas, os itens do Jive são copiados para o site do Globanet Merge1. O conector também converte o conteúdo de itens do jive em um formato de mensagem de email.

3. O conector do Jive que você criou no centro de conformidade da Microsoft 365 conecta-se ao site do Globanet Merge1 todos os dias e transfere o conteúdo para um local seguro de armazenamento do Azure na nuvem da Microsoft.

4. O conector importa os itens convertidos para as caixas de correio de usuários específicos usando o valor da propriedade *email* do mapeamento de usuário automático, conforme descrito na [etapa 3](#step-3-map-users-and-complete-the-connector-setup). Uma nova subpasta na pasta caixa de entrada chamada **Jive** é criada nas caixas de correio do usuário e os itens são importados para essa pasta. O conector faz isso usando o valor da propriedade *email* . Cada item do Jive contém essa propriedade, que é preenchida com o endereço de email de cada participante do item.

## <a name="before-you-begin"></a>Antes de começar

- Crie uma conta do Merge1 do Globanet para conectores da Microsoft. Para fazer isso, entre em contato com o [suporte ao cliente globanet](https://globanet.com/ms-connectors-contact/). Você precisa entrar nessa conta ao criar o conector na etapa 1.

- O usuário que cria o conector do Jive na etapa 1 (e conclui-lo na etapa 3) deve ser atribuído à função de exportação de importação de caixa de correio no Exchange Online. Essa função é necessária para adicionar conectores na página **conectores de dados** no centro de conformidade da Microsoft 365. Por padrão, essa função não é atribuída a nenhum grupo de função no Exchange Online. Você pode adicionar a função de exportação de importação de caixa de correio ao grupo de funções Gerenciamento da organização no Exchange Online. Ou você pode criar um grupo de função, atribua a função de exportação de importação de caixa de correio e, em seguida, adicione os usuários apropriados como membros. Para obter mais informações, consulte as seções [criar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) ou [modificar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) no artigo "gerenciar grupos de função no Exchange Online".

## <a name="step-1-set-up-the-jive-connector"></a>Etapa 1: configurar o conector do Jive

A primeira etapa é acessar a página **conectores de dados** no centro de conformidade da Microsoft 365 e criar um conector para dados do jive.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique em **conectores de dados**  >  **Jive**.

2. Na página de descrição do produto **Jive** , clique em **Adicionar conector**.

3. Na página **termos de serviço** , clique em **aceitar**.

4. Insira um nome exclusivo que identifique o conector e clique em **Avançar**.

5. Entre em sua conta do Merge1 para configurar o conector.

## <a name="step-2-configure-the-jive-connector"></a>Etapa 2: configurar o conector do Jive

A segunda etapa é configurar o conector do Jive no site do Merge1. Para obter informações sobre como configurar o conector do Jive, consulte [Merge1 do usuário de conectores de terceiros](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Jive%20User%20Guide.pdf).

Após clicar em **salvar & concluir**, você será direcionado para o centro de conformidade da Microsoft 365, para a página **mapeamento de usuário** no assistente de conector.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Etapa 3: mapear usuários e concluir a configuração do conector

Para mapear usuários e concluir a configuração do conector no centro de conformidade do Microsoft 365, siga as etapas abaixo:

1. Na página **mapear usuários do Jive para usuários do Microsoft 365** , habilite o mapeamento automático do usuário. Os itens do Jive incluem uma propriedade chamada *email*, que contém endereços de email para usuários em sua organização. Se o conector puder associar esse endereço a um usuário do Microsoft 365, os itens serão importados para a caixa de correio desse usuário.

2. Na página **consentimento do administrador** , clique em **fornecer consentimento**. Você será redirecionado para o site da Microsoft. Clique em **aceitar** para fornecer o consentimento.

   Sua organização deve dar o consentimento para permitir que o serviço de importação do Office 365 acesse dados de caixa de correio em sua organização. Para fornecer o consentimento do administrador, você deve estar conectado com as credenciais de um administrador global do Microsoft 365 e aceitar a solicitação de consentimento. Se você não estiver conectado como um administrador global, poderá ir para [esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) e entrar usando as credenciais de administrador global para aceitar a solicitação.

3. Clique em **Avançar**, revise suas configurações e vá para a página **conectores de dados** para ver o andamento do processo de importação para o novo conector.

## <a name="step-4-monitor-the-jive-connector"></a>Etapa 4: monitorar o conector do Jive

Depois de criar o conector do Jive, você pode visualizar o status do conector no centro de conformidade da Microsoft 365.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique em **conectores de dados** no painel de navegação esquerdo.

2. Clique na guia **conectores** e selecione o conector do **Jive** para exibir a página do menu suspenso, que contém as propriedades e informações sobre o conector.

3. Em **status do conector com origem**, clique no link **baixar log** para abrir (ou salvar) o log de status do conector. Esse log contém informações sobre os dados que foram importados para a nuvem da Microsoft.

## <a name="known-issues"></a>Problemas conhecidos

- No momento, não há suporte para importar anexos ou itens com mais de 10 MB. O suporte para itens maiores estará disponível em uma data posterior.
