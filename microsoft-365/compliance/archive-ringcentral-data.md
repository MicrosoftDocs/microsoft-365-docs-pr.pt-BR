---
title: Configurar um conector para arquivar dados RingCentral em Microsoft 365
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
description: Os administradores podem configurar um conector para importar e arquivar dados RingCentral da Veritas para Microsoft 365. Esse conector permite que você arquive dados de fontes de dados de terceiros em Microsoft 365. Depois de arquivar esses dados, você pode usar recursos de conformidade, como retenção legal, descoberta e políticas de retenção para gerenciar dados de terceiros.
ms.openlocfilehash: b5e98df50b0610c9fb583a8521c7a6d6fdb48e44
ms.sourcegitcommit: 8c6a5db0dab99a82a69dd8a0a7c56af1cb825931
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2021
ms.locfileid: "53276852"
---
# <a name="set-up-a-connector-to-archive-ringcentral-data-preview"></a>Configurar um conector para arquivar dados RingCentral (visualização)

Use um conector Veritas no Centro de conformidade do Microsoft 365 para importar e arquivar dados da plataforma RingCentral para caixas de correio de usuário em sua Microsoft 365 organização. A Veritas fornece um conector [RingCentral](https://www.veritas.com/insights/merge1/ringcentral) configurado para capturar itens da fonte de dados de terceiros e importar esses itens para Microsoft 365. O conector converte conteúdo como chats, anexos, tarefas, anotações e postagens do RingCentral em um formato de mensagem de email e, em seguida, importa esses itens para as caixas de correio do usuário em Microsoft 365.

Depois que os dados RingCentral são armazenados em caixas de correio de usuário, você pode aplicar Microsoft 365 de conformidade, como Retenção de Litígio, Descoberta Eletrônico, políticas de retenção e rótulos de retenção. Usar um conector RingCentral para importar e arquivar dados em Microsoft 365 pode ajudar sua organização a permanecer em conformidade com políticas governamentais e regulatórias.

## <a name="overview-of-archiving-ringcentral-data"></a>Visão geral dos dados RingCentral de arquivamento

A visão geral a seguir explica o processo de uso de um conector para arquivar os dados RingCentral em Microsoft 365.

![Fluxo de trabalho de arquivamento para dados RingCentral](../media/RingCentralConnectorWorkflow.png)

1. Sua organização trabalha com RingCentral para configurar e configurar um site RingCentral.

2. Uma vez a cada 24 horas, os itens RingCentral são copiados para o site Veritas Merge1. O conector também converte itens RingCentral em um formato de mensagem de email.

3. O conector RingCentral criado no Centro de conformidade do Microsoft 365, conecta-se ao site Veritas Merge1 todos os dias e transfere o conteúdo RingCentral para um local seguro do Azure Armazenamento na nuvem da Microsoft.

4. O conector importa os itens convertidos para as caixas de correio de usuários específicos usando o valor da propriedade *Email* do mapeamento automático do usuário, conforme descrito [na Etapa 3](#step-3-map-users-and-complete-the-connector-setup). Uma subpasta na pasta Caixa de Entrada chamada **RingCentral** é criada nas caixas de correio do usuário e os itens são importados para essa pasta. O conector determina para qual caixa de correio importar itens usando o valor da *propriedade Email.* Cada item RingCentral contém essa propriedade, que é preenchida com o endereço de email de cada participante do item.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar um conector

- Crie uma conta Merge1 para conectores da Microsoft. Para criar essa conta, entre em contato com [o Suporte ao Cliente veritas.](https://www.veritas.com/form/requestacall/ms-connectors-contact) Você precisa entrar nessa conta ao criar o conector na Etapa 1.

- Crie um aplicativo RingCentral para buscar dados da sua conta RingCentral. Para obter instruções passo a passo sobre como criar o aplicativo, consulte [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20RingCentral%20User%20Guide.pdf).

- O usuário que cria o conector RingCentral na Etapa 1 (e o conclui na Etapa 3) deve ser atribuído à função De exportação de importação de caixa de correio no Exchange Online. Essa função é necessária para adicionar conectores na página **Conectores de** dados no Centro de conformidade do Microsoft 365. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função Exportar Importação de Importação de Caixa de Correio ao grupo de função Gerenciamento da Organização Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Exportar Importação de Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte as seções Criar grupos de [função](/Exchange/permissions-exo/role-groups#create-role-groups) ou [Modificar](/Exchange/permissions-exo/role-groups#modify-role-groups) grupos de função no artigo "Gerenciar grupos de funções em Exchange Online".

## <a name="step-1-set-up-the-ringcentral-connector"></a>Etapa 1: Configurar o conector RingCentral

A primeira etapa é acessar a página **Conectores** de Dados no Centro de conformidade do Microsoft 365 e criar um conector para dados RingCentral.

1. Vá para <https://compliance.microsoft.com> e clique em **Conectores de dados**  >  **RingCentral**.

2. Na página **Descrição do produto RingCentral,** clique em **Adicionar conector**.

3. Na página **Termos de serviço,** clique em **Aceitar**.

4. Insira um nome exclusivo que identifique o conector e clique em **Próximo**.

5. Entre na sua conta Merge1 para configurar o conector.

## <a name="step-2-configure-the-ringcentral-on-the-veritas-merge1-site"></a>Etapa 2: Configurar o RingCentral no site de Mesclagem de Veritas1

A segunda etapa é configurar o conector RingCentral no site Veritas Merge1. Para obter informações sobre como configurar o conector RingCentral, consulte [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20RingCentral%20User%20Guide.pdf).

Depois de clicar em Salvar &  **Concluir,** a página de mapeamento do usuário no assistente de conector no Centro de conformidade do Microsoft 365 será exibida.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Etapa 3: mapear usuários e concluir a configuração do conector

Para mapear usuários e concluir a instalação do conector no Centro de conformidade do Microsoft 365, siga estas etapas:

1. Na página **Mapear usuários RingCentral para Microsoft 365 usuários,** habilita o mapeamento automático do usuário. Os itens RingCentral incluem uma propriedade chamada *Email*, que contém endereços de email para usuários em sua organização. Se o conector puder associar esse endereço a um Microsoft 365 usuário, os itens serão importados para a caixa de correio desse usuário.

2. Clique **em Avançar**, revise suas configurações e vá para a página Conectores de dados para ver o andamento do processo de importação do novo conector. 

## <a name="step-4-monitor-the-ringcentral-connector"></a>Etapa 4: Monitorar o conector RingCentral

Depois de criar o conector RingCentral, você poderá exibir o status do conector no Centro de conformidade do Microsoft 365.

1. Vá para <https://compliance.microsoft.com/> e clique **em Conectores de dados** na nav esquerda.

2. Clique na **guia Conectores** e selecione o conector **RingCentral** para exibir a página de sobrevoo, que contém as propriedades e informações sobre o conector.

3. Em **Status do conector com origem**, clique no link Baixar **log** para abrir (ou salvar) o log de status do conector. Esse log contém dados que foram importados para a nuvem da Microsoft.

## <a name="known-issues"></a>Problemas conhecidos

- Neste momento, não há suporte para importação de anexos ou itens maiores que 10 MB. O suporte para itens maiores estará disponível posteriormente.
