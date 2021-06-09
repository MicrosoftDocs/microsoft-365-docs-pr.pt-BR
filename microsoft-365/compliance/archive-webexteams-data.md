---
title: Configurar um conector para webex Teams dados em Microsoft 365
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
description: Os administradores podem configurar um conector para importar e arquivar dados do conector webex Teams Da Veritas em Microsoft 365. Esse conector permite que você arquive dados de fontes de dados de terceiros no Microsoft 365 para que você possa usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar os dados de terceiros da sua organização.
ms.openlocfilehash: 654ca53fd4cd7c6091ff74360545ba335f753ffd
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163891"
---
# <a name="set-up-a-connector-to-archive-webex-teams-data"></a>Configurar um conector para arquivar dados Teams Webex

Use um conector Veritas no centro de conformidade Microsoft 365 para importar e arquivar dados do Webex Teams caixas de correio de usuários em sua organização Microsoft 365. A Veritas fornece um conector [webex Teams](https://globanet.com/webex-teams/) que está configurado para capturar itens de comunicação do Webex Teams e importá-los para Microsoft 365. O conector converte conteúdo do webex Teams, como chats 1:1, conversas em grupo, conversas de canal e anexos da conta webex da sua organização Teams, para um formato de mensagem de email e importa esses itens para a caixa de correio do usuário no Microsoft 365.

Depois que os dados Teams Webex são armazenados em caixas de correio de usuário, você pode aplicar Microsoft 365 de conformidade, como Retenção de Litígio, Descoberta Eletrônico, políticas de retenção e rótulos de retenção e conformidade de comunicação. Usar um conector de Teams Webex para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a se manter em conformidade com políticas governamentais e regulatórias.

## <a name="overview-of-archiving-webex-teams-data"></a>Visão geral do arquivamento de dados webex Teams dados

A visão geral a seguir explica o processo de uso de um conector para arquivar dados Teams Webex em Microsoft 365.

![Fluxo de trabalho de arquivamento para dados Teams Webex](../media/WebexTeamsConnectorWorkflow.png)

1. Sua organização trabalha com webex Teams configurar e configurar um site webex Teams site.

2. Uma vez a cada 24 horas, os Teams Webex são copiados para o site Veritas Merge1. O conector também converte os itens webex Teams em um formato de mensagem de email.

3. O conector Teams Webex que você cria no centro de conformidade do Microsoft 365, conecta-se à Mesclagem de Veritas1 todos os dias e transfere os itens Teams Webex para um local seguro do Azure Armazenamento na nuvem da Microsoft.

4. O conector importa itens para as caixas de correio de usuários específicos usando o valor da propriedade *Email* do mapeamento automático do usuário, conforme descrito [na Etapa 3](#step-3-map-users-and-complete-the-connector-setup). Uma subpasta na pasta Caixa de Entrada chamada **Webex Teams** é criada nas caixas de correio do usuário e os itens são importados para essa pasta. O conector faz isso usando o valor da *propriedade Email.* Cada item Teams Webex contém essa propriedade, que é preenchida com o endereço de email de cada participante do item.

## <a name="before-you-begin"></a>Antes de começar

- Crie uma conta Veritas Merge1 para conectores da Microsoft. Para criar essa conta, entre em contato com [o Suporte ao Cliente veritas.](https://globanet.com/ms-connectors-contact) Você entrará nessa conta quando criar o conector na Etapa 1.

- Crie um aplicativo para [https://developer.webex.com/](https://developer.webex.com) buscar dados da sua conta do Webex Teams. Para obter instruções passo a passo sobre como criar o aplicativo, consulte [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf)

   Ao criar esse aplicativo, a plataforma Webex gera um conjunto de credenciais exclusivas. Essas credenciais são usadas na Etapa 2 quando você configura o conector de Teams Webex no site da Mesclagem Global1.

- O usuário que cria o conector webex Teams na Etapa 1 (e o conclui na Etapa 3) deve ser atribuído à função De exportação de importação de caixa de correio no Exchange Online. Essa função é necessária para adicionar conectores na página **Conectores** de dados no Microsoft 365 de conformidade. Por padrão, essa função não é atribuída a um grupo de funções no Exchange Online. Você pode adicionar a função Exportar Importação de Importação de Caixa de Correio ao grupo de função Gerenciamento da Organização Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Exportar Importação de Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte as seções Criar grupos de [função](/Exchange/permissions-exo/role-groups#create-role-groups) ou [Modificar](/Exchange/permissions-exo/role-groups#modify-role-groups) grupos de função no artigo "Gerenciar grupos de funções em Exchange Online".

## <a name="step-1-set-up-the-webex-teams-connector"></a>Etapa 1: Configurar o conector de Teams Webex

A primeira etapa é obter acesso aos **Conectores** de Dados e configurar o conector [webex Teams.](https://globanet.com/webex-teams/)

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique em **Conectores de dados**  >  **webex Teams**.

2. Na página **Descrição do Teams Webex,** clique **em Adicionar conector**.

3. Na página **Termos de serviço,** clique em **Aceitar**.

4. Insira um nome exclusivo que identifique o conector e clique em **Próximo**.

5. Entre na sua conta Merge1 para configurar o conector.

## <a name="step-2-configure-the-webex-teams-connector-on-the-veritas-merge1-site"></a>Etapa 2: Configurar o conector de Teams Webex no site Veritas Merge1

A segunda etapa é configurar o conector webex Teams no site Merge1. Para obter informações sobre como configurar o conector de Teams Webex, consulte [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf).

Depois de clicar em Salvar &  **Concluir**, a página de mapeamento do usuário no assistente de conector no Microsoft 365 de conformidade será exibida.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Etapa 3: mapear usuários e concluir a configuração do conector

Para mapear usuários e concluir a instalação do conector no centro de conformidade Microsoft 365, siga estas etapas:

1. Na página **Mapear webex Teams usuários para Microsoft 365** usuários, habilita o mapeamento automático do usuário. Os itens Teams Webex incluem uma propriedade chamada *Email*, que contém endereços de email para usuários em sua organização. Se o conector puder associar esse endereço a um Microsoft 365 usuário, os itens serão importados para a caixa de correio desse usuário.

2. Clique **em Avançar**, revise suas configurações e vá para a página Conectores de dados para ver o andamento do processo de importação do novo conector. 

## <a name="step-4-monitor-the-webex-teams-connector"></a>Etapa 4: Monitorar o conector de Teams Webex

Depois de criar o conector webex Teams, você poderá exibir o status do conector no centro de conformidade Microsoft 365 web.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique **em Conectores de dados** na nav esquerda.

2. Clique na **guia Conectores** e selecione o conector de Teams **Webex** para exibir a página de sobrevoo. Esta página contém as propriedades e informações sobre o conector.

3. Em **Status do conector com origem**, clique no link Baixar **log** para abrir (ou salvar) o log de status do conector. Esse log contém informações sobre os dados que foram importados para a nuvem da Microsoft.

## <a name="known-issues"></a>Problemas conhecidos

- Neste momento, não há suporte para importação de anexos ou itens maiores que 10 MB. O suporte para itens maiores estará disponível posteriormente.