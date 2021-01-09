---
title: Configurar um conector para arquivar dados do LinkedIn
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
description: Saiba como os administradores podem & usar um conector nativo para importar dados de uma Página da Empresa do LinkedIn para o Microsoft 365.
ms.openlocfilehash: 9f6cb2c6d5c47559f1fda13b6d03bfed3afe6fa2
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790175"
---
# <a name="set-up-a-connector-to-archive-linkedin-data"></a>Configurar um conector para arquivar dados do LinkedIn

Use um conector no centro de conformidade do Microsoft 365 para importar e arquivar dados de páginas da Empresa do LinkedIn. Depois de configurar um conector, ele se conecta à conta da página específica da Empresa do LinkedIn uma vez a cada 24 horas. O conector converte as mensagens publicadas na página Empresa em uma mensagem de email e importa esses itens para uma caixa de correio no Microsoft 365.

Depois que os dados da página da Empresa do LinkedIn são armazenados em uma caixa de correio, você pode aplicar recursos de conformidade do Microsoft 365, como Retenção de Litígio, Pesquisa de Conteúdo, Arquivamento do In-Place, Auditoria e políticas de retenção do Microsoft 365 aos dados do LinkedIn. Por exemplo, você pode pesquisar esses itens usando a Pesquisa de Conteúdo ou associar a caixa de correio de armazenamento a um custodiante em um caso de Descoberta Eletrônico Avançada. Criar um conector para importar e arquivar dados do LinkedIn no Microsoft 365 pode ajudar sua organização a manter a conformidade com políticas governamentais e regulatórias.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar um conector

- O usuário que cria um conector de Página da Empresa do LinkedIn deve receber a função Importar Exportar Caixa de Correio no Exchange Online. Isso é necessário para adicionar conectores na página Conectores **de dados** no centro de conformidade do Microsoft 365. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função Importar Exportar Caixa de Correio ao grupo de função Gerenciamento da Organização no Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Importar Exportar Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) as [seções](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) Criar grupos de função ou Modificar grupos de função no artigo "Gerenciar grupos de função no Exchange Online".

- Você deve ter as credenciais de entrada (endereço de email ou número de telefone e senha) de uma conta de usuário do LinkedIn que seja um administrador da Página da Empresa do LinkedIn que você deseja arquivar. Use essas credenciais para entrar no LinkedIn ao configurar o conector.

- O conector do LinkedIn pode importar um total de 200.000 itens em um único dia. Se houver mais de 200.000 itens do LinkedIn em um dia, nenhum desses itens será importado para o Microsoft 365.

## <a name="create-a-linkedin-connector"></a>Criar um conector do LinkedIn

1. Vá para <https://compliance.microsoft.com> e clique em **Conectores de dados páginas** da Empresa do  >  **LinkedIn.**

2. Na página do produto das páginas da empresa do **LinkedIn,** clique **em Adicionar conector.**

3. Na página **Termos de serviço,** selecione **Aceitar**.

4. Na página **Entrar com o LinkedIn,** clique **em Entrar com o LinkedIn.**

   A página de login do LinkedIn é exibida.

   ![Página de login do LinkedIn](../media/LinkedInSigninPage.png)

5. Na página de entrada do LinkedIn, insira o endereço de email (ou número de telefone) e a senha da conta do LinkedIn associada à página da empresa que você deseja arquivar e clique em **Entrar.**

   Uma página do assistente é exibida com uma lista de todas as Páginas da Empresa do LinkedIn associadas à conta à qual você se inscreveu. Um conector só pode ser configurado para uma página da empresa. Se sua organização tiver várias Páginas da Empresa do LinkedIn, será preciso criar um conector para cada uma delas.

   ![Uma página com uma lista de Páginas da Empresa do LinkedIn é exibida](../media/LinkedInSelectCompanyPage.png)

6. Selecione a página da empresa da onde você deseja arquivar itens e clique em **Próximo.**

7. Na  página Escolher local de armazenamento, clique na caixa, selecione o endereço de email de uma caixa de correio do Microsoft 365 para a qual os itens do LinkedIn serão importados e clique em **Próximo.** Os itens são importados para a pasta de caixa de entrada nesta caixa de correio.

8. Clique **em Próximo** para revisar as configurações do conector e clique em **Concluir** para concluir a configuração do conector.

Depois de criar o conector, você  pode voltar para a página Conectores de dados  para ver o progresso do processo de importação do novo conector (selecione Atualizar, se necessário, para atualizar a lista de conectores). O valor na coluna **Status** está **aguardando para iniciar.** Leva até 24 horas para que o processo de importação inicial seja iniciado. Após a primeira vez em que o conector é executado e importa os itens do LinkedIn, o conector será executado uma vez a cada 24 horas e importa todos os novos itens criados na Página da Empresa do LinkedIn nas últimas 24 horas.

Para exibir mais detalhes, selecione o conector na lista na página Conectores **de** dados para exibir a página do flyout. Em **Status,** o intervalo de datas exibido indica o filtro de idade selecionado quando o conector foi criado.

## <a name="more-information"></a>Mais informações

Os itens do LinkedIn são importados para a subpasta do LinkedIn na caixa de entrada da caixa de correio de armazenamento no Microsoft 365. Eles aparecem como mensagens de email.
