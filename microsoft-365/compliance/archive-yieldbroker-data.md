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
description: Os administradores podem configurar um conector para importar e arquivar dados da Yieldbroker da Globalnet para o Microsoft 365. Esse conector permite arquivar dados de fontes de dados de terceiros no Microsoft 365. Depois de arquivar esses dados, você pode usar recursos de conformidade como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar dados de terceiros.
ms.openlocfilehash: 34ce7686e6fdf418257265d707eda7eed3cab026
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740318"
---
# <a name="set-up-a-connector-to-archive-yieldbroker-data"></a>Configurar um conector para arquivar dados do Yieldbroker

Use um conector Globalnet no centro de conformidade do Microsoft 365 para importar e arquivar dados do Yieldbroker para as caixas de correio do usuário em sua organização do Microsoft 365. A Globalnet fornece um conector [Yieldbroker](https://globanet.com/yieldbroker/) configurado para capturar itens da fonte de dados de terceiros e importá-los para o Microsoft 365. O conector converte o conteúdo de Yieldbroker em um formato de mensagem de email e importa esses itens para a caixa de correio do usuário no Microsoft 365.

Depois que Yieldbroker é armazenado em caixas de correio de usuário, você pode aplicar recursos de conformidade do Microsoft 365, como Retenção de Litígio, Descoberta e políticas de retenção e rótulos de retenção. Usar um conector yieldbroker para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a manter a conformidade com políticas governamentais e regulamentar.

## <a name="overview-of-archiving-yieldbroker-data"></a>Visão geral dos dados do Yieldbroker de arquivamento

A visão geral a seguir explica o processo de uso de um conector para arquivar os dados do Yieldbroker no Microsoft 365.

![Fluxo de trabalho de arquivamento para dados yieldbroker](../media/YieldbrokerConnectorWorkflow.png)

1. Sua organização trabalha com o Yieldbroker para configurar um site da Yieldbroker.

2. Uma vez a cada 24 horas, os itens yieldbroker são copiados para o site Globalnet Merge1. O conector também converte o conteúdo em um formato de mensagem de email.

3. O conector Yieldbroker criado no centro de conformidade do Microsoft 365 conecta-se ao site Globalnet Merge1 todos os dias e transfere as mensagens para um local seguro de Armazenamento do Azure na nuvem da Microsoft.

4. O conector importa os itens convertidos Yieldbroker para as caixas de correio de usuários específicos usando o valor da propriedade *Email* do mapeamento automático de usuário, conforme descrito na [Etapa 3.](#step-3-map-users-and-complete-the-connector-setup) Uma subpasta na pasta Caixa de Entrada chamada **Yieldbroker** é criada nas caixas de correio do usuário e os itens são importados para essa pasta. O conector determina para qual caixa de correio os itens serão importados usando o valor da *propriedade Email.* Cada Yieldbroker contém essa propriedade, que é preenchida com o endereço de email de cada participante do item.

## <a name="before-you-begin"></a>Antes de começar

- Crie uma conta Globalnet Merge1 para conectores da Microsoft. Para criar uma conta, entre em contato com o Suporte [ao Cliente Globalnet.](https://globanet.com/contact-us/) Você precisa entrar nessa conta ao criar o conector na Etapa 1.

- O usuário que cria o conector Yieldbroker na Etapa 1 (e o conclui na Etapa 3) deve ser atribuído à função Importar Exportar Caixa de Correio no Exchange Online. Essa função é necessária para adicionar conectores à página Conectores de dados no centro de conformidade do Microsoft 365. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função Importar Exportar Caixa de Correio ao grupo de função Gerenciamento da Organização no Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Importar Exportar Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) as [seções](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) Criar grupos de função ou Modificar grupos de função no artigo "Gerenciar grupos de função no Exchange Online".

## <a name="step-1-set-up-the-yieldbroker-connector"></a>Etapa 1: Configurar o conector Yieldbroker

A primeira etapa é  acessar a página Conectores de Dados no centro de conformidade do Microsoft 365 e criar um conector para o Yieldbroker.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique em **Conectores de dados** &gt; **Yieldbroker**.

2. Na página **Descrição do produto Yieldbroker,** clique **em Adicionar novo conector.**

3. Na página **Termos de serviço,** clique em **Aceitar**.

4. Insira um nome exclusivo que identifique o conector e clique em **Próximo.**

5. Entre em sua conta Merge1 para configurar o conector.

## <a name="step-2-configure-the-yieldbroker-connector-on-the-globanet-merge1-site"></a>Etapa 2: Configurar o conector Yieldbroker no site Globalnet Merge1

A segunda etapa é configurar o conector Yieldbroker no site Merge1. Para obter informações sobre como configurar o Yieldbroker, consulte [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Yieldbroker%20User%20Guide%20.pdf).

Depois que você clicar em Salvar  **& Concluir,** a página de mapeamento do usuário no assistente de conector no centro de conformidade do Microsoft 365 será exibida.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Etapa 3: Mapear usuários e concluir a configuração do conector

Para mapear usuários e concluir a configuração do conector, siga estas etapas:

1. Na página **Mapear usuários do Yieldbroker para usuários do Microsoft 365,** habilita o mapeamento automático de usuários. Os itens Yieldbroker incluem uma propriedade chamada *Email*, que contém endereços de email para usuários em sua organização. Se o conector puder associar esse endereço a um usuário do Microsoft 365, os itens serão importados para a caixa de correio desse usuário.

2. Clique **em Avançar,** revise suas configurações e vá para a página Conectores de dados para ver o progresso do processo de importação do novo conector. 

## <a name="step-4-monitor-the-yieldbroker-connector"></a>Etapa 4: Monitorar o conector Yieldbroker

Depois de criar o conector Yieldbroker, você pode exibir o status do conector no centro de conformidade do Microsoft 365.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique **em Conectores de dados** na barra de entrada esquerda.

2. Clique na **guia Conectores** e selecione o conector **Yieldbroker** para exibir a página do flyout, que contém as propriedades e informações sobre o conector.

3. Em **Status do Conector com origem,** clique no link Baixar **log** para abrir (ou salvar) o log de status do conector. Esse log contém dados que foram importados para a nuvem da Microsoft.

## <a name="known-issues"></a>Problemas conhecidos

- No momento, não há suporte para a importação de anexos ou itens maiores do que 10 MB. O suporte para itens maiores estará disponível posteriormente.
