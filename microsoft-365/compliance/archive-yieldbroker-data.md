---
title: Configurar um conector para arquivar dados do Yieldbroker no Microsoft 365
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
description: Os administradores podem configurar um conector para importar e arquivar dados do Yieldbroker da Veritas para Microsoft 365. Esse conector permite que você arquive dados de fontes de dados de terceiros em Microsoft 365. Depois de arquivar esses dados, você pode usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar dados de terceiros.
ms.openlocfilehash: 1f2ca6850057112cc0a97b08811532961a213e89
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163771"
---
# <a name="set-up-a-connector-to-archive-yieldbroker-data"></a>Configurar um conector para arquivar dados do Yieldbroker

Use um conector Veritas no centro de conformidade Microsoft 365 para importar e arquivar dados do Yieldbroker para caixas de correio de usuário em sua Microsoft 365 organização. A Veritas fornece um conector [yieldbroker](https://globanet.com/yieldbroker/) configurado para capturar itens da fonte de dados de terceiros e importar esses itens para Microsoft 365. O conector converte o conteúdo do Yieldbroker em um formato de mensagem de email e importa esses itens para a caixa de correio do usuário em Microsoft 365.

Depois que o Yieldbroker for armazenado em caixas de correio de usuário, você poderá aplicar Microsoft 365 de conformidade, como Retenção de Litígio, Descoberta Eletrônico, políticas de retenção e rótulos de retenção. Usar um conector do Yieldbroker para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a permanecer em conformidade com políticas governamentais e regulatórias.

## <a name="overview-of-archiving-yieldbroker-data"></a>Visão geral dos dados do Yieldbroker de arquivamento

A visão geral a seguir explica o processo de uso de um conector para arquivar os dados do Yieldbroker Microsoft 365.

![Fluxo de trabalho de arquivamento para dados do Yieldbroker](../media/YieldbrokerConnectorWorkflow.png)

1. Sua organização trabalha com o Yieldbroker para configurar e configurar um site do Yieldbroker.

2. Uma vez a cada 24 horas, os itens do Yieldbroker são copiados para o site Veritas Merge1. O conector também converte o conteúdo em um formato de mensagem de email.

3. O conector do Yieldbroker criado no centro de conformidade do Microsoft 365, conecta-se ao site Veritas Merge1 todos os dias e transfere as mensagens para um local seguro do Azure Armazenamento na nuvem da Microsoft.

4. O conector importa os itens do Yieldbroker convertidos para as caixas de correio de usuários específicos usando o valor da propriedade *Email* do mapeamento automático do usuário, conforme descrito na [Etapa 3](#step-3-map-users-and-complete-the-connector-setup). Uma subpasta na pasta Caixa de Entrada chamada **Yieldbroker** é criada nas caixas de correio do usuário e os itens são importados para essa pasta. O conector determina para qual caixa de correio importar itens usando o valor da *propriedade Email.* Cada Yieldbroker contém essa propriedade, que é preenchida com o endereço de email de cada participante do item.

## <a name="before-you-begin"></a>Antes de começar

- Crie uma conta Veritas Merge1 para conectores da Microsoft. Para criar uma conta, entre em contato com [o Suporte ao Cliente veritas.](https://www.veritas.com/content/support/) Você precisa entrar nessa conta ao criar o conector na Etapa 1.

- O usuário que cria o conector yieldbroker na Etapa 1 (e o conclui na Etapa 3) deve ser atribuído à função De exportação de importação de caixa de correio no Exchange Online. Essa função é necessária para adicionar conectores na página Conectores de dados no Microsoft 365 de conformidade. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função Exportar Importação de Importação de Caixa de Correio ao grupo de função Gerenciamento da Organização Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Exportar Importação de Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte as seções Criar grupos de [função](/Exchange/permissions-exo/role-groups#create-role-groups) ou [Modificar](/Exchange/permissions-exo/role-groups#modify-role-groups) grupos de função no artigo "Gerenciar grupos de funções em Exchange Online".

## <a name="step-1-set-up-the-yieldbroker-connector"></a>Etapa 1: Configurar o conector do Yieldbroker

A primeira etapa é acessar a página **Conectores** de Dados no centro de conformidade Microsoft 365 e criar um conector para o Yieldbroker.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique em **Conectores de dados** &gt; **Yieldbroker**.

2. Na página **Descrição do produto yieldbroker,** clique **em Adicionar novo conector**.

3. Na página **Termos de serviço,** clique em **Aceitar**.

4. Insira um nome exclusivo que identifique o conector e clique em **Próximo**.

5. Entre na sua conta Merge1 para configurar o conector.

## <a name="step-2-configure-the-yieldbroker-connector-on-the-veritas-merge1-site"></a>Etapa 2: Configurar o conector do Yieldbroker no site de Mesclagem de Veritas1

A segunda etapa é configurar o conector yieldbroker no site Merge1. Para obter informações sobre como configurar o Yieldbroker, consulte [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Yieldbroker%20User%20Guide%20.pdf).

Depois de clicar em Salvar &  **Concluir**, a página de mapeamento do usuário no assistente de conector no Microsoft 365 de conformidade será exibida.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Etapa 3: mapear usuários e concluir a configuração do conector

Para mapear usuários e concluir a configuração do conector, siga estas etapas:

1. Na página **Mapear usuários do Yieldbroker para Microsoft 365 usuários,** habilita o mapeamento automático do usuário. Os itens do Yieldbroker incluem uma propriedade chamada *Email*, que contém endereços de email para usuários em sua organização. Se o conector puder associar esse endereço a um Microsoft 365 usuário, os itens serão importados para a caixa de correio desse usuário.

2. Clique **em Avançar,** revise suas configurações e vá até a página **Conectores** de dados para ver o andamento do processo de importação do novo conector.

## <a name="step-4-monitor-the-yieldbroker-connector"></a>Etapa 4: Monitorar o conector do Yieldbroker

Depois de criar o conector yieldbroker, você pode exibir o status do conector no centro de conformidade Microsoft 365 de segurança.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique **em Conectores de dados** na nav esquerda.

2. Clique na **guia Conectores** e selecione o conector **do Yieldbroker** para exibir a página de sobrevoo, que contém as propriedades e informações sobre o conector.

3. Em **Status do conector com origem**, clique no link Baixar **log** para abrir (ou salvar) o log de status do conector. Esse log contém dados que foram importados para a nuvem da Microsoft.

## <a name="known-issues"></a>Problemas conhecidos

- Neste momento, não há suporte para importação de anexos ou itens maiores que 10 MB. O suporte para itens maiores estará disponível posteriormente.