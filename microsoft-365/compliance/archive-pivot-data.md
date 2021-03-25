---
title: Configurar um conector para arquivar dados pivot no Microsoft 365
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
description: Os administradores podem configurar um conector para importar e arquivar dados pivot da Veritas no Microsoft 365. Esse conector permite que você arquive dados de fontes de dados de terceiros no Microsoft 365 para que você possa usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar os dados de terceiros da sua organização.
ms.openlocfilehash: 8e88f5166ebcc4d1285a81e041b6d97be46786e3
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164181"
---
# <a name="set-up-a-connector-to-archive-pivot-data"></a>Configurar um conector para arquivar dados pivot

Use um conector Veritas no centro de conformidade do Microsoft 365 para importar e arquivar dados da plataforma Pivot para caixas de correio de usuário em sua organização do Microsoft 365. A Veritas fornece [](https://globanet.com/pivot/) um conector Pivot configurado para capturar itens da fonte de dados de terceiros (regularmente) e depois importar esses itens para o Microsoft 365. Pivot é uma plataforma de mensagens instantâneas que permite a colaboração com participantes do mercado financeiro. O conector converte itens como mensagens de chat, de contas dinâmicas de um usuário para um formato de mensagem de email e importa esses itens para as caixas de correio do usuário no Microsoft 365.

Depois que os dados pivot são armazenados em caixas de correio de usuário, você pode aplicar recursos de conformidade do Microsoft 365, como Retenção de Litígio, Descoberta Eletrônico, políticas de retenção e rótulos de retenção e conformidade de comunicação. O uso de um conector pivot para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a permanecer em conformidade com políticas governamentais e regulatórias.

## <a name="overview-of-archiving-pivot-data"></a>Visão geral dos dados pivôs de arquivamento

A visão geral a seguir explica o processo de uso de um conector para arquivar os dados pivot no Microsoft 365.

![Fluxo de trabalho de arquivamento para dados pivot](../media/PivotConnectorWorkflow.png)

1. Sua organização trabalha com Pivot para configurar e configurar um site de origem dinâmica.

2. Uma vez a cada 24 horas, os itens Pivot são copiados para o site Veritas Merge1. O conector também converte os itens Pivot em um formato de mensagem de email.

3. O conector pivot que você cria no centro de conformidade do Microsoft 365, conecta-se ao site Veritas Merge1 todos os dias e transfere os itens Pivot para um local seguro de Armazenamento do Azure na nuvem da Microsoft.

4. O conector importa os itens Pivot para as caixas de correio de usuários específicos usando o valor da propriedade *Email* do mapeamento automático do usuário, conforme descrito [na Etapa 3](#step-3-map-users-and-complete-the-connector-setup). Uma subpasta na pasta Caixa de Entrada chamada **Pivot** é criada nas caixas de correio do usuário e os itens são importados para essa pasta. O conector faz isso usando o valor da *propriedade Email.* Cada item Pivot contém essa propriedade, que é preenchida com o endereço de email de cada participante do item.

## <a name="before-you-begin"></a>Antes de começar

- Crie uma conta Veritas Merge1 para conectores da Microsoft. Para criar essa conta, entre em contato com [o Suporte ao Cliente veritas.](https://www.veritas.com/content/support/) Você entrará nessa conta quando criar o conector na Etapa 1.

- O usuário que cria o conector pivot na Etapa 1 (e o conclui na Etapa 3) deve ser atribuído à função De exportação de importação de caixa de correio no Exchange Online. Essa função é necessária para adicionar conectores na página Conectores de dados no centro de conformidade do Microsoft 365. Por padrão, essa função não é atribuída a um grupo de funções no Exchange Online. Você pode adicionar a função Exportar Importação de Caixa de Correio ao grupo de função Gerenciamento da Organização no Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Exportar Importação de Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte as seções Criar grupos de [função](/Exchange/permissions-exo/role-groups#create-role-groups) ou [Modificar](/Exchange/permissions-exo/role-groups#modify-role-groups) grupos de função no artigo "Gerenciar grupos de função no Exchange Online".

## <a name="step-1-set-up-the-pivot-connector"></a>Etapa 1: Configurar o conector de pivô

A primeira etapa é acessar a página **Conectores** de Dados no centro de conformidade da Microsoft e criar um conector para dados pivot.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique em **Conectores de dados**  >  **Pivot**.

2. Na página **Descrição** dinâmica do produto, clique **em Adicionar conector**.

3. Na página **Termos de serviço,** clique em **Aceitar**.

4. Insira um nome exclusivo que identifique o conector e clique em **Próximo**.

5. Entre na sua conta Merge1 para configurar o conector.

## <a name="step-2-configure-the-pivot-connector-on-the-veritas-merge1-site"></a>Etapa 2: Configurar o conector de pivô no site Mesclagem de Veritas1

A segunda etapa é configurar o conector pivot no site Merge1. Para obter informações sobre como configurar o conector pivô no site Mesclagem de Veritas1, consulte [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Pivot%20User%20Guide%20.pdf).

Depois de clicar em Salvar &  **Concluir**, a página de mapeamento do usuário no assistente de conector no centro de conformidade do Microsoft 365 será exibida.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Etapa 3: mapear usuários e concluir a configuração do conector

Para mapear usuários e concluir a configuração do conector no centro de conformidade do Microsoft 356, siga estas etapas:

1. Na página **Mapear usuários do Pivot para usuários do Microsoft 365,** habilita o mapeamento automático do usuário. Os itens Pivot incluem uma propriedade chamada *Email*, que contém endereços de email para usuários em sua organização. Se o conector puder associar esse endereço a um usuário do Microsoft 365, os itens serão importados para a caixa de correio desse usuário.

2. Clique **em Avançar,** revise suas configurações e vá até a página **Conectores** de dados para ver o andamento do processo de importação do novo conector.

## <a name="step-4-monitor-the-pivot-connector"></a>Etapa 4: Monitorar o conector de pivô

Depois de criar o conector pivot, você pode exibir o status do conector no centro de conformidade do Microsoft 365.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique **em Conectores de dados** na nav esquerda.

2. Clique na **guia Conectores** e selecione o **conector pivot** para exibir a página de sobrevoo. Esta página contém as propriedades e informações sobre o conector.

3. Em **Status do conector com origem**, clique no link Baixar **log** para abrir (ou salvar) o log de status do conector. Esse log contém dados que foram importados para a nuvem da Microsoft.

## <a name="known-issues"></a>Problemas conhecidos

- Neste momento, não há suporte para importação de anexos ou itens maiores que 10 MB. O suporte para itens maiores estará disponível posteriormente.