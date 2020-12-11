---
title: Configurar um conector para arquivar dados delimitados por texto no Microsoft 365
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
description: Os administradores podem configurar um conector para importar e arquivar dados delimitados por texto do Globanet para o Microsoft 365. Esse conector permite que você arquive dados de fontes de dados de terceiros no Microsoft 365. Após o arquivamento desses dados, você pode usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar dados de terceiros.
ms.openlocfilehash: 1c06a1220e597dbf8e278222347a5a5e9c46567e
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619897"
---
# <a name="set-up-a-connector-to-archive-text-delimited-data"></a>Configurar um conector para arquivar dados delimitados por texto

Use um conector Globanet no centro de conformidade da Microsoft 365 para importar e arquivar dados delimitados por texto para caixas de correio de usuários na sua organização do Microsoft 365. O Globanet fornece um [conector delimitado por texto](https://globanet.com/text-delimited) que é configurado para capturar itens de uma fonte de dados de terceiros (em uma base regular) e importá-los para o Microsoft 365. O conector converte o conteúdo da fonte de dados delimitada por texto em um formato de mensagem de email e, em seguida, importa esses itens para a caixa de correio do usuário no Microsoft 365.

Depois que os dados delimitados por texto são armazenados nas caixas de correio do usuário, você pode aplicar recursos de conformidade do Microsoft 365, como retenção de litígio, descoberta eletrônica e políticas de retenção e rótulos de retenção. O uso de um conector de dados delimitado por texto para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a se manter em conformidade com as políticas governamentais e regulamentares.

## <a name="overview-of-archiving-the-text-delimited-data"></a>Visão geral do arquivamento de dados delimitados por texto

A visão geral a seguir explica o processo de usar um conector para arquivar informações de origem delimitadas por texto no Microsoft 365.

![Fluxo de trabalho de arquivamento para dados delimitados por texto](../media/TextDelimitedConnectorWorkflow.png)

1. Sua organização trabalha com a fonte delimitada por texto para configurar e configurar um site delimitado por texto.

2. Uma vez a cada 24 horas, as mensagens de chat da fonte delimitada por texto são copiadas para o site do Globanet Merge1. O conector também converte o conteúdo em um formato de mensagem de email.

3. O conector de texto delimitado que você cria no centro de conformidade da Microsoft 365 conecta-se ao site do Globanet Merge1 todos os dias e transfere as mensagens para um local seguro de armazenamento do Azure na nuvem da Microsoft.

4. O conector importa os itens de mensagem convertidos para as caixas de correio de usuários específicos usando o valor da propriedade *email* do mapeamento de usuário automático, conforme descrito na etapa 3. Uma nova subpasta na pasta caixa de entrada denominada **texto delimitado** é criada nas caixas de correio do usuário e os itens de mensagem são importados para essa pasta. O conector determina qual caixa de correio para a qual importar itens usando o valor da propriedade *email* . Cada mensagem contém essa propriedade, que é preenchida com o endereço de email de cada participante.

## <a name="before-you-begin"></a>Antes de começar

- Crie uma conta do Merge1 do Globanet para conectores da Microsoft. Para criar essa conta, entre em contato com o [suporte ao cliente Globanet](https://globanet.com/ms-connectors-contact). Você entrará nesta conta quando criar o conector na etapa 1.

- O usuário que cria o conector delimitado por texto na etapa 1 (e conclui-lo na etapa 3) deve ser atribuído à função de exportação de importação de caixa de correio no Exchange Online. Essa função é necessária para adicionar conectores na página **conectores de dados** no centro de conformidade da Microsoft 365. Por padrão, essa função não é atribuída a um grupo de função no Exchange Online. Você pode adicionar a função de exportação de importação de caixa de correio ao grupo de funções Gerenciamento da organização no Exchange Online. Ou você pode criar um grupo de função, atribua a função de exportação de importação de caixa de correio e, em seguida, adicione os usuários apropriados como membros. Para obter mais informações, consulte as seções [criar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) ou [modificar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) no artigo "gerenciar grupos de função no Exchange Online".

## <a name="step-1-set-up-the-text-delimited-connector"></a>Etapa 1: configurar o conector delimitado por texto

A primeira etapa é acessar a página **conectores de dados** no centro de conformidade da Microsoft 365 e criar um conector para dados delimitados por texto.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique em **conectores**  >  **de dados delimitados por texto**.

2. Na página descrição do produto **delimitado por texto** , clique em **Adicionar conector**.

3. Na página **termos de serviço** , clique em **aceitar**.

4. Insira um nome exclusivo que identifique o conector e clique em **Avançar**.

5. Entre em sua conta do Merge1 para configurar o conector.

## <a name="step-2-configure-the-text-delimited-connector-on-the-globanet-merge1-site"></a>Etapa 2: configurar o conector delimitado por texto no site do Globanet Merge1

A segunda etapa é configurar o conector delimitado por texto no site do Merge1. Para obter informações sobre como configurar o conector delimitado por texto no site do Globanet Merge1, consulte [Merge1 de terceiros conectores do usuário](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20text-delimited%20User%20Guide%20.pdf).

Depois de clicar em **salvar & concluir**, a página **mapeamento de usuário** no assistente de conector no centro de conformidade da Microsoft 365 é exibida.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Etapa 3: mapear usuários e concluir a configuração do conector

Para mapear usuários e concluir a configuração do conector no centro de conformidade do Microsoft 365, siga estas etapas:

1. Na página **mapear usuários externos para usuários do Microsoft 365** , habilite o mapeamento automático do usuário. Os itens de origem delimitados por texto incluem uma propriedade chamada *email*, que contém endereços de email para usuários em sua organização. Se o conector puder associar esse endereço a um usuário do Microsoft 365, os itens serão importados para a caixa de correio desse usuário.

2. Clique em **Avançar**, revise suas configurações e vá para a página **conectores de dados** para ver o andamento do processo de importação para o novo conector.

## <a name="step-4-monitor-the-text-delimited-connector"></a>Etapa 4: monitorar o conector delimitado por texto

Depois de criar o conector de texto delimitado, você pode visualizar o status do conector no centro de conformidade da Microsoft 365.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique em **conectores de dados** no painel de navegação esquerdo.

2. Clique na guia **conectores** e selecione o conector **delimitado por texto** para exibir a página de submenu. Esta página contém as propriedades e as informações sobre o conector.

3. Em **status do conector com origem**, clique no link **baixar log** para abrir (ou salvar) o log de status do conector. Esse log contém informações sobre os dados que foram importados para a nuvem da Microsoft.

## <a name="known-issues"></a>Problemas conhecidos

- No momento, não há suporte para importar anexos ou itens com mais de 10 MB. O suporte para itens maiores estará disponível em uma data posterior.
