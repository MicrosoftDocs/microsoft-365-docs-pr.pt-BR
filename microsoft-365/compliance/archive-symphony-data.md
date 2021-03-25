---
title: Configurar um conector para arquivar dados de orquestra no Microsoft 365
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
description: Os administradores podem configurar um conector para importar e arquivar dados da Veritas Symphony para o Microsoft 365. Esse conector permite arquivar dados de fontes de dados de terceiros no Microsoft 365. Depois de arquivar esses dados, você pode usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar dados de terceiros.
ms.openlocfilehash: b3ddb6826f7ef68808a819ee1d860b020efea98a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163970"
---
# <a name="set-up-a-connector-to-archive-symphony-data"></a>Configurar um conector para arquivar dados de orquestra

Use um conector Veritas no centro de conformidade do Microsoft 365 para importar e arquivar dados de orquestra para caixas de correio de usuário em sua organização do Microsoft 365. A Orquestra é uma plataforma de mensagens e colaboração usada no setor de serviços financeiros. A Veritas [](https://globanet.com/symphony) fornece um conector de dados Dols no centro de conformidade do Microsoft 365 que você pode configurar para capturar itens da fonte de dados de terceiros (regularmente) e, em seguida, importar esses itens para caixas de correio do usuário. O conector converte o conteúdo de um item da conta Da Orquestra Em um formato de mensagem de email e importa o item para uma caixa de correio no Microsoft 365.

Depois que as comunicações de Orquestra são armazenadas em caixas de correio de usuário, você pode aplicar recursos de conformidade do Microsoft 365, como Retenção de Litígio, Descoberta Eletrônica, políticas de retenção e rótulos de retenção e conformidade de comunicação. O uso de um conector Desarmônico para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a se manter em conformidade com políticas governamentais e regulatórias.

## <a name="overview-of-archiving-symphony-data"></a>Visão geral dos dados de arquivamento do Orquestra de Arquivamento

A visão geral a seguir explica o processo de uso de um conector de dados para arquivar comunicações da Orquestra No Microsoft 365.

![Fluxo de trabalho de arquivamento de orquestra](../media/SymphonyConnectorWorkflow.png)

1. Sua organização trabalha com a Orquestra Sinfônica para configurar e configurar um site Defônico.

2. Uma vez a cada 24 horas, as mensagens de chat da Orquestra Sinfônica são copiadas para o site Veritas Merge1. O conector também converte o conteúdo de uma mensagem de chat em um formato de mensagem de email.

3. O conector de orquestração que você cria no centro de conformidade do Microsoft 365, conecta-se ao site Veritas Merge1 todos os dias e transfere as mensagens para um local de Armazenamento seguro do Azure na nuvem da Microsoft.

4. O conector importa os itens de mensagem convertidos para as caixas de correio de usuários específicos usando o valor da propriedade *Email* do mapeamento automático do usuário, conforme descrito na Etapa 3. Uma nova subpasta na pasta Caixa de Entrada chamada **Symphony** é criada nas caixas de correio do usuário e os itens de mensagem são importados para essa pasta. O conector determina para qual caixa de correio importar itens usando o valor da *propriedade Email.* Cada mensagem de chat contém essa propriedade, que é preenchida com o endereço de email de cada participante.

## <a name="before-you-begin"></a>Antes de começar

- Crie uma conta Veritas Merge1 para conectores da Microsoft. Para criar uma conta, entre em contato com [o Suporte ao Cliente veritas.](https://globanet.com/ms-connectors-contact) Você entrará nessa conta quando criar o conector na Etapa 1.

- O usuário que cria o conector Defônico na Etapa 1 (e o conclui na Etapa 3) deve ser atribuído à função De exportação de importação de caixa de correio no Exchange Online. Essa função é necessária para adicionar conectores na página **Conectores de** dados no centro de conformidade do Microsoft 365. Por padrão, essa função não é atribuída a um grupo de funções no Exchange Online. Você pode adicionar a função Exportar Importação de Caixa de Correio ao grupo de função Gerenciamento da Organização no Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Exportar Importação de Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte as seções Criar grupos de [função](/Exchange/permissions-exo/role-groups#create-role-groups) ou [Modificar](/Exchange/permissions-exo/role-groups#modify-role-groups) grupos de função no artigo "Gerenciar grupos de função no Exchange Online".

## <a name="step-1-set-up-the-symphony-connector"></a>Etapa 1: Configurar o conector de orquestração

A primeira etapa é acessar a página **Conectores** de Dados no centro de conformidade do Microsoft 365 e criar um conector para dados do Orquestra.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique em **Conectores de dados**  >  **Orquestrar.**

2. Na página **Descrição do produto** Da Orquestra, clique **em Adicionar conector**.

3. Na página **Termos de serviço,** clique em **Aceitar**.

4. Insira um nome exclusivo que identifique o conector e clique em **Próximo**.

5. Entre na sua conta Merge1 para configurar o conector.

## <a name="configure-the-symphony-connector-on-the-veritas-merge1-site"></a>Configurar o conector Defônico no site Veritas Merge1

A segunda etapa é configurar o conector Defônico no site Merge1. Para obter informações sobre como configurar o conector Defônico no site Veritas Merge1, consulte [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Symphony%20User%20Guide%20.pdf).

Depois de clicar em Salvar &  **Concluir**, a página de mapeamento do usuário no assistente de conector no centro de conformidade do Microsoft 365 será exibida.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Etapa 3: mapear usuários e concluir a configuração do conector

Para mapear usuários e concluir a configuração do conector no centro de conformidade do Microsoft 365, siga estas etapas:

1. Na página **Mapear usuários externos para usuários do Microsoft 365,** habilita o mapeamento automático do usuário. Os itens Da Orquestra incluem uma propriedade chamada *Email*, que contém endereços de email para usuários em sua organização. Se o conector puder associar esse endereço a um usuário do Microsoft 365, os itens serão importados para a caixa de correio desse usuário.

2. Clique **em Avançar**, revise suas configurações e vá para a página Conectores de dados para ver o andamento do processo de importação do novo conector. 

## <a name="step-4-monitor-the-symphony-connector"></a>Etapa 4: Monitorar o conector de orquestra

Depois de criar o conector Defônico, você pode exibir o status do conector no centro de conformidade do Microsoft 365.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique **em Conectores de dados** na nav esquerda.

2. Clique na **guia Conectores** e selecione o **conector Defletar** para exibir a página de sobrevoo. Esta página contém as propriedades e informações sobre o conector.

3. Em **Status do conector com origem**, clique no link Baixar **log** para abrir (ou salvar) o log de status do conector. Esse log contém informações sobre os dados que foram importados para a nuvem da Microsoft.

## <a name="known-issues"></a>Problemas conhecidos

- Neste momento, não há suporte para importação de anexos ou itens maiores que 10 MB. O suporte para itens maiores estará disponível posteriormente.