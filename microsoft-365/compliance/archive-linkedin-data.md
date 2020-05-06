---
title: Configurar um conector para arquivar dados do LinkedIn
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Configure um conector para importar dados do LinkedIn para a Microsoft 365, de modo que você possa usar ferramentas de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção.
ms.openlocfilehash: 7d88d366ea19be7d158a04edc7d7fb11dca7bab9
ms.sourcegitcommit: e55e4747d3b838baacab8985aefc24aac245c431
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44043342"
---
# <a name="set-up-a-connector-to-archive-linkedin-data"></a>Configurar um conector para arquivar dados do LinkedIn

Use um conector no centro de conformidade da Microsoft 365 para importar e arquivar dados das páginas da empresa do LinkedIn. Depois de configurar e configurar um conector, ele se conecta à conta da página específica da empresa do LinkedIn uma vez a cada 24 horas. O conector converte as mensagens postadas na página da empresa em uma mensagem de email e, em seguida, importa esses itens para uma caixa de correio no Microsoft 365.

Depois que os dados da página da empresa do LinkedIn são armazenados em uma caixa de correio, você pode aplicar recursos de conformidade do Microsoft 365, como retenção de litígio, pesquisa de conteúdo, arquivamento in-loco, auditoria e políticas de retenção da Microsoft 365 para dados do LinkedIn. Por exemplo, você pode pesquisar esses itens usando a pesquisa de conteúdo ou associar a caixa de correio de armazenamento a um funcionário em uma caixa de descoberta eletrônica avançada. A criação de um conector para importar e arquivar dados do LinkedIn no Microsoft 365 pode ajudar sua organização a se manter em conformidade com as políticas governamentais e regulamentares.

## <a name="before-you--begin"></a>Antes de começar

- Sua organização deve dar o consentimento para permitir que o serviço de importação do Office 365 acesse dados de caixa de correio em sua organização. Para concordar com essa solicitação, [acesse a página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), entre com as credenciais de um administrador global do Microsoft 365 e aceite a solicitação.

- O usuário que cria um conector de página da empresa do LinkedIn deve receber a função de exportação de importação de caixa de correio no Exchange Online. Isso é necessário para adicionar conectores na página **conectores de dados** no centro de conformidade do Microsoft 365. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função de exportação de importação de caixa de correio ao grupo de funções Gerenciamento da organização no Exchange Online. Ou você pode criar um grupo de função, atribua a função de exportação de importação de caixa de correio e, em seguida, adicione os usuários apropriados como membros. Para obter mais informações, consulte as seções [criar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) ou [modificar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) no artigo "gerenciar grupos de função no Exchange Online".

- Você deve ter as credenciais de entrada (endereço de email ou número de telefone e senha) de uma conta de usuário do LinkedIn que seja um administrador para a página da empresa do LinkedIn que você deseja arquivar. Use essas credenciais para entrar no LinkedIn ao configurar o conector.

## <a name="create-a-linkedin-connector"></a>Criar um conector do LinkedIn

1. Vá para <https://compliance.microsoft.com> e clique em **conectores** > de dados**páginas da empresa do LinkedIn**.

2. Na página produtos **da empresa do LinkedIn** , clique em **Adicionar conector**.

3. Na página **termos de serviço** , selecione **aceitar**.

4. Na página **entrar com o LinkedIn** , clique em **entrar com LinkedIn**.

   A página de entrada do LinkedIn é exibida.

   ![Página de entrada do LinkedIn](../media/LinkedInSigninPage.png)

5. Na página de entrada do LinkedIn, insira o endereço de email (ou número de telefone) e a senha da conta do LinkedIn associada à página da empresa que você deseja arquivar e clique em **entrar**.

   Uma página de assistente é exibida com uma lista de todas as páginas da empresa do LinkedIn associadas à conta na qual você entrou no. Um conector só pode ser configurado para uma página da empresa. Se sua organização tiver várias páginas da empresa do LinkedIn, você precisará criar um conector para cada uma delas.

   ![Uma página com uma lista de páginas da empresa do LinkedIn é exibida](../media/LinkedInSelectCompanyPage.png)

6. Selecione a página da empresa da qual você deseja arquivar itens e clique em **Avançar**.

7. Na página **escolher local de armazenamento** , clique na caixa, selecione o endereço de email de uma caixa de correio do Microsoft 365 em que os itens do LinkedIn serão importados e clique em **Avançar**. Os itens são importados para a pasta caixa de entrada nesta caixa de correio.

8. Em **fornecer consentimento do administrador**, clique em **fornecer consentimento** e siga as etapas. Você deve ser um administrador global para fornecer consentimento para o serviço de importação do Office 365 para acessar dados em sua organização.

9. Clique em **Avançar** para revisar as configurações do conector e clique em **concluir** para concluir a configuração do conector.

Depois de criar o conector, você pode voltar para a página **conectores de dados** para ver o andamento do processo de importação para o novo conector (selecione **Atualizar** , se necessário, para atualizar a lista de conectores). O valor na coluna **status** está **aguardando para iniciar**. É necessário ter até 24 horas para que o processo inicial de importação seja iniciado. Após a primeira vez que o conector é executado e importa os itens do LinkedIn, o conector é executado uma vez a cada 24 horas e importa os novos itens que são criados na página da empresa do LinkedIn nas últimas 24 horas.

Para exibir mais detalhes, selecione o conector na lista na página **conectores de dados** para exibir a página do menu de atalho. Em **status**, o intervalo de datas exibido indica o filtro de idade que foi selecionado quando o conector foi criado.

## <a name="more-information"></a>Mais informações

Os itens do LinkedIn são importados para a subpasta do LinkedIn na caixa de entrada da caixa de correio de armazenamento no Microsoft 365. Eles aparecem como mensagens de email.
