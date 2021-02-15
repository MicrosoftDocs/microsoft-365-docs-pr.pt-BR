---
title: Configurar um conector para arquivar dados do Pivot no Microsoft 365
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
description: Os administradores podem configurar um conector para importar e arquivar dados de Pivô da Globalnet no Microsoft 365. Esse conector permite arquivar dados de fontes de dados de terceiros no Microsoft 365 para que você possa usar recursos de conformidade como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar dados de terceiros da sua organização.
ms.openlocfilehash: 23badcb2a8d2873f03b86499ccfd4c9a96b81090
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620368"
---
# <a name="set-up-a-connector-to-archive-pivot-data"></a>Configurar um conector para arquivar dados de pivô

Use um conector Globalnet no centro de conformidade do Microsoft 365 para importar e arquivar dados da plataforma Pivot para as caixas de correio do usuário em sua organização do Microsoft 365. A Globalnet fornece [](https://globanet.com/pivot/) um conector de pivô configurado para capturar itens da fonte de dados de terceiros (regularmente) e, em seguida, importar esses itens para o Microsoft 365. Pivot é uma plataforma de mensagens instantâneas que permite a colaboração com participantes do mercado financeiro. O conector converte itens como mensagens de chat, de contas Dinâmicas de um usuário para um formato de mensagem de email e importa esses itens para as caixas de correio do usuário no Microsoft 365.

Depois que os dados de Pivô são armazenados em caixas de correio do usuário, você pode aplicar recursos de conformidade do Microsoft 365, como Retenção de Litígio, Descoberta Eletrônico, políticas de retenção e rótulos de retenção e conformidade de comunicação. Usar um conector Pivot para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a manter a conformidade com políticas governamentais e regulatórias.

## <a name="overview-of-archiving-pivot-data"></a>Visão geral dos dados de pivô de arquivamento

A visão geral a seguir explica o processo de uso de um conector para arquivar os dados de pivô no Microsoft 365.

![Fluxo de trabalho de arquivamento para dados de pivô](../media/PivotConnectorWorkflow.png)

1. Sua organização trabalha com Pivot para configurar e configurar um site de origem de pivô.

2. Uma vez a cada 24 horas, os itens de pivô são copiados para o site Globalnet Merge1. O conector também converte os itens de pivô em um formato de mensagem de email.

3. O conector pivot que você cria no centro de conformidade do Microsoft 365, se conecta ao site Globalnet Merge1 todos os dias e transfere os itens de pivô para um local seguro de Armazenamento do Azure na nuvem da Microsoft.

4. O conector importa os itens de pivô para as caixas de correio de usuários específicos usando o valor da propriedade *Email* do mapeamento automático de usuário, conforme descrito na [Etapa 3.](#step-3-map-users-and-complete-the-connector-setup) Uma subpasta na pasta Caixa de Entrada chamada **Pivot** é criada nas caixas de correio do usuário e os itens são importados para essa pasta. O conector faz isso usando o valor da *propriedade Email.* Cada item de pivô contém essa propriedade, que é preenchida com o endereço de email de cada participante do item.

## <a name="before-you-begin"></a>Antes de começar

- Crie uma conta Globalnet Merge1 para conectores da Microsoft. Para criar essa conta, entre em contato com o Suporte [ao Cliente Globalnet.](https://globanet.com/ms-connectors-contact/) Você entrará nessa conta quando criar o conector na Etapa 1.

- O usuário que cria o conector de pivô na Etapa 1 (e o conclui na Etapa 3) deve ser atribuído à função Importar Exportar Caixa de Correio no Exchange Online. Essa função é necessária para adicionar conectores na página Conectores de dados no centro de conformidade do Microsoft 365. Por padrão, essa função não é atribuída a um grupo de funções no Exchange Online. Você pode adicionar a função Importar Exportar Caixa de Correio ao grupo de função Gerenciamento da Organização no Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Importar Exportar Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) as [seções](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) Criar grupos de função ou Modificar grupos de função no artigo "Gerenciar grupos de função no Exchange Online".

## <a name="step-1-set-up-the-pivot-connector"></a>Etapa 1: Configurar o conector de pivô

A primeira etapa é  acessar a página Conectores de Dados no centro de conformidade da Microsoft e criar um conector para dados de pivô.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique em **Conectores de dados**  >  **pivot**.

2. Na página **de descrição** do produto Pivot, clique **em Adicionar conector.**

3. Na página **Termos de serviço,** clique em **Aceitar**.

4. Insira um nome exclusivo que identifique o conector e clique em **Próximo.**

5. Entre em sua conta Merge1 para configurar o conector.

## <a name="step-2-configure-the-pivot-connector-on-the-globanet-merge1-site"></a>Etapa 2: Configurar o conector de pivô no site Globalnet Merge1

A segunda etapa é configurar o conector de pivô no site Merge1. Para obter informações sobre como configurar o conector de pivô no site Globalnet Merge1, consulte [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Pivot%20User%20Guide%20.pdf).

Depois que você clicar em Salvar  **& Concluir,** a página de mapeamento do usuário no assistente de conector no centro de conformidade do Microsoft 365 será exibida.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Etapa 3: Mapear usuários e concluir a configuração do conector

Para mapear usuários e concluir a configuração do conector no centro de conformidade do Microsoft 356, siga estas etapas:

1. Na página **Mapear usuários do Pivot para usuários do Microsoft 365,** habilita o mapeamento automático de usuários. Os itens de pivô incluem uma propriedade chamada *Email*, que contém endereços de email para usuários em sua organização. Se o conector puder associar esse endereço a um usuário do Microsoft 365, os itens serão importados para a caixa de correio desse usuário.

2. Clique **em Avançar,** revise suas configurações e vá para a página Conectores de dados para ver o progresso do processo de importação do novo conector. 

## <a name="step-4-monitor-the-pivot-connector"></a>Etapa 4: Monitorar o conector de pivô

Depois de criar o conector de pivô, você pode exibir o status do conector no centro de conformidade do Microsoft 365.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique **em Conectores de dados** na barra de entrada esquerda.

2. Clique na **guia Conectores** e selecione o **conector de** pivô para exibir a página do flyout. Esta página contém as propriedades e informações sobre o conector.

3. Em **Status do Conector com origem,** clique no link Baixar **log** para abrir (ou salvar) o log de status do conector. Esse log contém dados que foram importados para a nuvem da Microsoft.

## <a name="known-issues"></a>Problemas conhecidos

- No momento, não há suporte para a importação de anexos ou itens maiores do que 10 MB. O suporte para itens maiores estará disponível posteriormente.
