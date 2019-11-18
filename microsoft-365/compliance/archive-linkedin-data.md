---
title: Configurar um conector para arquivar dados do LinkedIn no Office 365 (versão prévia)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Os administradores podem configurar um conector nativo para importar dados de uma página da empresa do LinkedIn para o Office 365. Isso permite que você arquive dados de fontes de dados de terceiros no Office 365 para que possa usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar a conformidade dos dados de terceiros da sua organização.
ms.openlocfilehash: 1117eb6b7c756519ad07cafc52a635d65999d9e0
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2019
ms.locfileid: "38684929"
---
# <a name="set-up-a-connector-to-archive-linkedin-data-in-office-365-preview"></a>Configurar um conector para arquivar dados do LinkedIn no Office 365 (versão prévia)

O recurso conector para arquivar dados das páginas da empresa do LinkedIn no Office 365 está em visualização.

Use um conector nativo no centro de conformidade & segurança no Office 365 para importar e arquivar dados das páginas da empresa do LinkedIn. Depois de configurar e configurar um conector, ele se conecta à conta da página específica da empresa do LinkedIn uma vez a cada 24 horas. O conector converte as mensagens postadas na página da empresa em uma mensagem de email e, em seguida, importa esses itens para uma caixa de correio no Office 365.

Depois que os dados da página da empresa do LinkedIn são armazenados em uma caixa de correio, você pode aplicar recursos de conformidade do Office 365, como retenção de litígio, pesquisa de conteúdo, arquivamento in-loco, auditoria e políticas de retenção do Office 365 a dados do LinkedIn. Por exemplo, você pode pesquisar esses itens usando a pesquisa de conteúdo ou associar a caixa de correio de armazenamento a um funcionário em uma caixa de descoberta eletrônica avançada. A criação de um conector para importar e arquivar dados do LinkedIn no Office 365 pode ajudar sua organização a se manter em conformidade com as políticas governamentais e regulamentares.

## <a name="before-you--begin"></a>Antes de começar

- Sua organização deve dar o consentimento para permitir que o serviço de importação do Office 365 acesse dados de caixa de correio em sua organização. Para concordar com essa solicitação, [acesse esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), entre com as credenciais de um administrador global do Office 365 e aceite a solicitação.

- O usuário que cria um conector de página da empresa do LinkedIn deve receber a função de exportação de importação de caixa de correio no Exchange Online. Isso é necessário para acessar a página **arquivar dados** de terceiros no centro de conformidade de & de segurança. Por padrão, essa função não é atribuída a nenhum grupo de função no Exchange Online. Você pode adicionar a função de exportação de importação de caixa de correio ao grupo de funções Gerenciamento da organização no Exchange Online. Ou você pode criar um grupo de função, atribua a função de exportação de importação de caixa de correio e, em seguida, adicione os usuários apropriados como membros. Para obter mais informações, consulte as seções [criar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) ou [modificar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) no artigo "gerenciar grupos de função no Exchange Online".

- Você deve ter as credenciais de entrada (endereço de email ou número de telefone e senha) de uma conta de usuário do LinkedIn que seja um administrador para a página da empresa do LinkedIn que você deseja arquivar. Use essas credenciais para entrar no LinkedIn ao configurar o conector.

## <a name="create-a-linkedin-connector"></a>Criar um conector do LinkedIn

1. Vá para <https://protection.office.com> e clique em **importação de \> governança de dados** e clique em **arquivar dados de terceiros**.

2. Na página **arquivar dados de terceiros** , clique em **Adicionar um conector**e, em seguida, clique em **LinkedIn**.

3. Na página **termos de serviço** , clique em **aceitar**.

4. Na página **entrar com o LinkedIn** , clique em **entrar com LinkedIn**.

   A página de entrada do LinkedIn é exibida.

   ![Página de entrada do LinkedIn](media/LinkedInSigninPage.png)

5. Na página de entrada do LinkedIn, insira o endereço de email (ou número de telefone) e a senha da conta do LinkedIn associada à página da empresa que você deseja arquivar e clique em **entrar**.

   Uma página de assistente é exibida com uma lista de todas as páginas da empresa do LinkedIn associadas à conta na qual você entrou no. Um conector só pode ser configurado para uma página da empresa. Se sua organização tiver várias páginas da empresa do LinkedIn, você precisará criar um conector para cada uma delas.

   ![Uma página com uma lista de páginas da empresa do LinkedIn é exibida](media/LinkedInSelectCompanyPage.png)

6. Selecione a página da empresa da qual você deseja arquivar itens e clique em **Avançar**.

7. Na página **definir filtros** , você pode aplicar um filtro para importar inicialmente os itens que tenham uma determinada idade. Selecione uma idade e clique em **Avançar**.

8. Na página **definir conta de armazenamento** , digite o endereço de email de uma caixa de correio do Office 365 à qual os itens do LinkedIn serão importados e clique em **Avançar**. Os itens são importados para a pasta caixa de entrada nesta caixa de correio.

9. Revise as configurações do conector e clique em **salvar** para concluir a configuração do conector.

Depois de criar o conector, você pode voltar para a página **arquivar dados** de terceiros (clique em **Atualizar** se necessário para atualizar a lista de conectores) um modo de exibição do novo conector. O valor na coluna **status** está **aguardando para iniciar**. É necessário ter até 24 horas para que o processo inicial de importação seja iniciado. Após a primeira vez que o conector é executado e importa os itens do LinkedIn, o conector é executado uma vez a cada 24 horas e importa os novos itens que são criados na página da empresa do LinkedIn nas últimas 24 horas.

Para exibir mais detalhes, clique no conector na lista na página de dados de terceiros de **arquivamento** para exibir a página de menu. Em **status**, o intervalo de datas exibido indica o filtro de idade que foi selecionado quando o conector foi criado. 

## <a name="more-information"></a>Mais informações

- Os itens do LinkedIn são importados para a pasta caixa de entrada na caixa de correio de armazenamento no Office 365. Eles aparecem como mensagens de email. O nome de exibição do remetente da mensagem é o nome da página da empresa do LinkedIn. O endereço de email real do remetente é o endereço de email da caixa de correio de armazenamento. O nome da página da empresa também é acrescentado à linha de assunto. 

- Devido ao comportamento anterior, você pode pesquisar as propriedades `from` ou `subject` email ao usar uma ferramenta de descoberta eletrônica da Microsoft para pesquisar itens do LinkedIn que são arquivados no Office 365. Por exemplo, se o nome da página da empresa for "página da empresa contoso", então você poderá usar uma das seguintes *Propriedades:* pares de valores na consulta de pesquisa de palavra-chave:
   
   > de: "página da empresa contoso"

    Ou

   > Assunto: "página da empresa contoso"

- Para facilitar a localização ou o gerenciamento de itens do LinkedIn importados para o Office 365, o proprietário da caixa de correio de armazenamento (ou qualquer pessoa que tenha atribuído a permissão FullAccess) pode configurar uma regra de caixa de entrada para mover os itens de uma página da empresa do LinkedIn para uma pasta específica. Isso é útil se a caixa de correio de armazenamento é usada para arquivar itens importados de diferentes fontes de dados de terceiros. Por exemplo, você pode criar uma regra de caixa de entrada que move todos os itens que contêm o nome de uma página específica da empresa do LinkedIn no campo assunto para uma pasta específica.