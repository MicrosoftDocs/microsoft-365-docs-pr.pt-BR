---
title: Configurar um conector para arquivar dados serviceNow no Microsoft 365
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
description: Os administradores podem configurar um conector para importar e arquivar dados serviceNow da Veritas para o Microsoft 365. Esse conector permite arquivar dados de fontes de dados de terceiros no Microsoft 365. Depois de arquivar esses dados, você pode usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar dados de terceiros.
ms.openlocfilehash: 8f1f56f79d3cdd0e198f03d948837249d3e0ff3b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164031"
---
# <a name="set-up-a-connector-to-archive-servicenow-data"></a>Configurar um conector para arquivar dados serviceNow

Use um conector Veritas no centro de conformidade do Microsoft 365 para importar e arquivar dados da plataforma ServiceNow para caixas de correio de usuário em sua organização do Microsoft 365. A Veritas fornece um [conector ServiceNow](https://globanet.com/servicenow/) que captura itens da fonte de dados de terceiros e importa esses itens para o Microsoft 365. O conector converte o conteúdo, como mensagens ao vivo, anexos e postagens do ServiceNow em um formato de mensagem de email e importa esses itens para caixas de correio de usuário no Microsoft 365.

Depois que os dados serviceNow são armazenados em caixas de correio de usuário, você pode aplicar recursos de conformidade do Microsoft 365, como Retenção de Litígio, Descoberta Eletrônico, políticas de retenção e rótulos de retenção. O uso de um conector ServiceNow para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a permanecer em conformidade com políticas governamentais e regulatórias.

## <a name="overview-of-archiving-servicenow-data"></a>Visão geral dos dados servicenow de arquivamento

A visão geral a seguir explica o processo de uso de um conector para arquivar os dados serviceNow no Microsoft 365.

![Fluxo de trabalho de arquivamento para dados ServiceNow](../media/ServiceNowConnectorWorkflow.png)

1. Sua organização trabalha com ServiceNow para configurar e configurar um site ServiceNow.

2. Uma vez a cada 24 horas, os itens ServiceNow são copiados para o site Veritas Merge1. O conector também converte itens ServiceNow em um formato de mensagem de email.

3. O conector ServiceNow criado no centro de conformidade do Microsoft 365 conecta-se ao site Veritas Merge1 todos os dias e transfere o conteúdo serviceNow para um local seguro de Armazenamento do Azure na nuvem da Microsoft.

4. O conector importa os itens convertidos para as caixas de correio de usuários específicos usando o valor da propriedade *Email* do mapeamento automático do usuário, conforme descrito [na Etapa 3](#step-3-map-users-and-complete-the-connector-setup). Uma subpasta na pasta Caixa de Entrada chamada **ServiceNow** é criada nas caixas de correio do usuário e os itens são importados para essa pasta. O conector determina para qual caixa de correio importar itens usando o valor da *propriedade Email.* Cada item ServiceNow contém essa propriedade, que é preenchida com o endereço de email de cada participante do item.

## <a name="before-you-begin"></a>Antes de começar

- Crie uma conta Merge1 para conectores da Microsoft. Para criar uma conta, entre em contato com [o Suporte ao Cliente veritas.](https://www.veritas.com/content/support/) Você precisa entrar nessa conta ao criar o conector na Etapa 1.

- Crie um aplicativo ServiceNow para buscar dados da sua conta ServiceNow. Para obter instruções passo a passo sobre como criar o aplicativo, consulte [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20ServiceNow%20User%20Guide%20.pdf).

- O usuário que cria o conector ServiceNow na Etapa 1 (e o conclui na Etapa 3) deve ser atribuído à função De exportação de importação de caixa de correio no Exchange Online. Essa função é necessária para adicionar conectores na página **Conectores de** dados no centro de conformidade do Microsoft 365. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função Exportar Importação de Caixa de Correio ao grupo de função Gerenciamento da Organização no Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Exportar Importação de Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte as seções Criar grupos de [função](/Exchange/permissions-exo/role-groups#create-role-groups) ou [Modificar](/Exchange/permissions-exo/role-groups#modify-role-groups) grupos de função no artigo "Gerenciar grupos de função no Exchange Online".

## <a name="step-1-set-up-the-servicenow-connector"></a>Etapa 1: Configurar o conector ServiceNow

A primeira etapa é acessar a página **Conectores** de Dados no centro de conformidade do Microsoft 365 e criar um conector para dados serviceNow.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique em **Conectores de dados**  >  **ServiceNow**.

2. Na página Descrição do produto **ServiceNow,** clique em **Adicionar conector**.

3. Na página **Termos de serviço,** clique em **Aceitar**.

4. Insira um nome exclusivo que identifique o conector e clique em **Próximo**.

5. Entre na sua conta Merge1 para configurar o conector.

## <a name="step-2-configure-the-servicenow-on-the-veritas-merge1-site"></a>Etapa 2: Configurar o ServiceNow no site Veritas Merge1

A segunda etapa é configurar o conector ServiceNow no site Veritas Merge1. Para obter informações sobre como configurar o conector ServiceNow, consulte [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20ServiceNow%20User%20Guide%20.pdf).

Depois de clicar em Salvar  **& Concluir,** a página de mapeamento do usuário no assistente de conector no centro de conformidade do Microsoft 365 será exibida.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Etapa 3: mapear usuários e concluir a configuração do conector

Para mapear usuários e concluir a configuração do conector no centro de conformidade do Microsoft 365, siga estas etapas:

1. Na página **Mapear usuários serviceNow para usuários do Microsoft 365,** habilita o mapeamento automático do usuário. Os itens ServiceNow incluem uma propriedade chamada *Email*, que contém endereços de email para usuários em sua organização. Se o conector puder associar esse endereço a um usuário do Microsoft 365, os itens serão importados para a caixa de correio desse usuário.

2. Clique **em Avançar**, revise suas configurações e vá para a página Conectores de dados para ver o andamento do processo de importação do novo conector. 

## <a name="step-4-monitor-the-servicenow-connector"></a>Etapa 4: Monitorar o conector ServiceNow

Depois de criar o conector ServiceNow, você poderá exibir o status do conector no centro de conformidade do Microsoft 365.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique **em Conectores de dados** na nav esquerda.

2. Clique na **guia Conectores** e selecione o conector **ServiceNow** para exibir a página de sobrevoo, que contém as propriedades e informações sobre o conector.

3. Em **Status do conector com origem**, clique no link Baixar **log** para abrir (ou salvar) o log de status do conector. Esse log contém dados que foram importados para a nuvem da Microsoft.

## <a name="known-issues"></a>Problemas conhecidos

- Neste momento, não há suporte para importação de anexos ou itens maiores que 10 MB. O suporte para itens maiores estará disponível posteriormente.