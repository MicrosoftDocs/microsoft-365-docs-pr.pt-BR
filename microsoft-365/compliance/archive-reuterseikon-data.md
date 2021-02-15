---
title: Configurar um conector para arquivar dados eikon do Reuters no Microsoft 365
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
description: Os administradores podem configurar um conector para importar e arquivar dados Eikon da Globalnet no Microsoft 365. Esse conector permite arquivar dados de fontes de dados de terceiros no Microsoft 365. Depois de arquivar esses dados, você pode usar recursos de conformidade como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar dados de terceiros.
ms.openlocfilehash: f790317fb8ed8f94601d7915b484015c4cdf6088
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620358"
---
# <a name="set-up-a-connector-to-archive-reuters-eikon-data"></a>Configurar um conector para arquivar dados eikon de Reuters

Use um conector Globalnet no centro de conformidade do Microsoft 365 para importar e arquivar dados da plataforma Reuters Eikon para caixas de correio de usuário em sua organização do Microsoft 365. A Globalnet fornece um conector Eikon da [Reuters](https://globanet.com/eikon/) configurado para capturar itens da fonte de dados de terceiros (regularmente) e importar esses itens para o Microsoft 365. O conector converte o conteúdo, como mensagens de pessoa para pessoa, chats em grupo, anexos e avisos de isenção de responsabilidade de uma conta do Reuters Eikon do usuário para um formato de mensagem de email e importa esses itens para a caixa de correio do usuário no Microsoft 365.

Depois que os dados eikon da Reuters são armazenados em caixas de correio do usuário, você pode aplicar recursos de conformidade do Microsoft 365, como Retenção de Litígio, Descoberta Eletrônico, políticas de retenção e rótulos de retenção e conformidade de comunicação. Usar um conector Eikon da Reuters para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a manter a conformidade com políticas governamentais e regulamentares.

## <a name="overview-of-archiving-reuters-eikon-data"></a>Visão geral dos dados eikon do Reuters de arquivamento

A visão geral a seguir explica o processo de uso de um conector para arquivar dados eikon da Reuters no Microsoft 365.

![Fluxo de trabalho de arquivamento para dados Eikon da Reuters](../media/ReutersEikonConnectorWorkflow.png)

1. Sua organização trabalha com Reuters Eikon para configurar um site Eikon da Reuters.

2. Uma vez a cada 24 horas, os itens Eikon da Reuters são copiados para o site Globalnet Merge1. O conector também converte itens Eikon de Reuters em um formato de mensagem de email.

3. O conector Reuters Eikon criado no centro de conformidade do Microsoft 365 conecta-se ao site Globalnet Merge1 todos os dias e transfere o conteúdo para um local seguro de Armazenamento do Azure na nuvem da Microsoft.

4. O conector importa itens para as caixas de correio de usuários específicos usando o valor da propriedade *Email* do mapeamento automático de usuário, conforme descrito na [Etapa 3.](#step-3-map-users-and-complete-the-connector-setup) Uma subpasta na pasta Caixa de Entrada chamada **Reuters Eikon** é criada nas caixas de correio do usuário e os itens são importados para essa pasta. O conector determina para qual caixa de correio os itens serão importados usando o valor da *propriedade Email.* Cada item Eikon reuters contém essa propriedade, que é preenchida com o endereço de email de cada participante do item.

## <a name="before-you-begin"></a>Antes de começar

- Crie uma conta Globalnet Merge1 para conectores da Microsoft. Para criar uma conta, entre em contato com o Suporte [ao Cliente Globalnet.](https://globanet.com/ms-connectors-contact) Você entrará nessa conta quando criar o conector na Etapa 1.

- O usuário que cria o conector Reuters Eikon na Etapa 1 (e o conclui na Etapa 3) deve ser atribuído à função Importar Exportar Caixa de Correio no Exchange Online. Essa função é necessária para adicionar conectores na página Conectores **de dados** no centro de conformidade do Microsoft 365. Por padrão, essa função não é atribuída a um grupo de funções no Exchange Online. Você pode adicionar a função Importar Exportar Caixa de Correio ao grupo de função Gerenciamento da Organização no Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Importar Exportar Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) as [seções](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) Criar grupos de função ou Modificar grupos de função no artigo "Gerenciar grupos de função no Exchange Online".

## <a name="step-1-set-up-the-reuters-eikon-connector"></a>Etapa 1: Configurar o conector Eikon do Reuters

A primeira etapa é  acessar a página Conectores de Dados no centro de conformidade do Microsoft 365 e criar um conector para os dados eikon da Reuters.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique em **Conectores de dados**  >  **Reuters Eikon**.

2. Na página **Descrição do produto Eikon da Reuters,** clique **em Adicionar conector.**

3. Na página **Termos de serviço,** clique em **Aceitar**.

4. Insira um nome exclusivo que identifique o conector e clique em **Próximo.**

5. Entre em sua conta Merge1 para configurar o conector.

## <a name="step-2-configure-the-reuters-eikon-connector-on-the-globanet-merge1-site"></a>Etapa 2: Configurar o conector Eikon da Reuters no site Globalnet Merge1

A segunda etapa é configurar o conector Reuters Eikon no site Merge1. Para obter informações sobre como configurar o conector Reuters Eikon no site Globalnet Merge1, consulte [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Reuters%20Eikon%20User%20Guide%20.pdf).

Depois que você clicar em Salvar  **& Concluir,** a página de mapeamento do usuário no assistente de conector no centro de conformidade do Microsoft 365 será exibida.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Etapa 3: Mapear usuários e concluir a configuração do conector

Para mapear usuários e concluir a configuração do conector no centro de conformidade do Microsoft 365, siga estas etapas:

1. Na página **Mapear usuários externos para usuários do Microsoft 365,** habilita o mapeamento automático de usuários. Os itens Eikon da Reuters incluem uma propriedade chamada *Email*, que contém endereços de email para usuários em sua organização. Se o conector puder associar esse endereço a um usuário do Microsoft 365, os itens serão importados para a caixa de correio desse usuário.

2. Clique **em Avançar,** revise suas configurações  e vá para a página Conectores de dados para ver o progresso do processo de importação do novo conector.

## <a name="step-4-monitor-the-reuters-eikon-connector"></a>Etapa 4: Monitorar o conector Eikon do Reuters

Depois de criar o conector Eikon da Reuters, você pode exibir o status do conector no centro de conformidade do Microsoft 365.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique **em Conectores de dados** na barra de entrada esquerda.

2. Clique na **guia Conectores** e selecione o conector **Reuters Eikon** para exibir a página do flyout. Esta página contém as propriedades e informações sobre o conector.

3. Em **Status do Conector com origem,** clique no link Baixar **log** para abrir (ou salvar) o log de status do conector. Esse log contém informações sobre os dados que foram importados para a nuvem da Microsoft.

## <a name="known-issues"></a>Problemas conhecidos

- No momento, não há suporte para a importação de anexos ou itens maiores do que 10 MB. O suporte para itens maiores estará disponível posteriormente.
