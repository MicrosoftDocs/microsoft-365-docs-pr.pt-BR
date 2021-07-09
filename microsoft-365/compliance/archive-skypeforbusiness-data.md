---
title: Configurar um conector para arquivar Skype for Business dados no Microsoft 365
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
description: Saiba como configurar e usar um conector no Centro de conformidade do Microsoft 365 para importar e arquivar dados de Skype for Business para Microsoft 365.
ms.openlocfilehash: 4a66ee19530860bd482168297a8c935153442fee
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339449"
---
# <a name="set-up-a-connector-to-archive-skype-for-business-data"></a>Configurar um conector para arquivar Skype for Business dados

Use um conector Veritas no Centro de conformidade do Microsoft 365 para importar e arquivar dados da plataforma Skype for Business para caixas de correio de usuário em sua Microsoft 365 organização. A Veritas fornece um [conector Skype for Business](https://www.veritas.com/en/au/insights/merge1/skype-for-business) que é configurado para capturar itens da fonte de dados de terceiros (regularmente) e importar esses itens para Microsoft 365. O conector converte o conteúdo, como mensagens entre usuários, chats persistentes e mensagens de conferência do Skype for Business para um formato de mensagem de email e importa esses itens para a caixa de correio do usuário no Microsoft 365.

Depois Skype for Business dados são armazenados em caixas de correio de usuário, você pode aplicar Microsoft 365 de conformidade, como Retenção de Litígio, Descoberta Eletrônico, políticas de retenção e rótulos de retenção. Usar um conector Skype for Business para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a se manter em conformidade com políticas governamentais e regulatórias.

## <a name="overview-of-archiving-skype-for-business-data"></a>Visão geral do arquivamento Skype for Business dados

A visão geral a seguir explica o processo de uso de um conector para arquivar os Skype for Business dados no Microsoft 365.

![Fluxo de trabalho de arquivamento para Skype for Business dados](../media/SkypeforBusinessConnectorWorkflow.png)

1. Sua organização trabalha com Skype for Business para configurar e configurar um Skype for Business site.

2. Uma vez a cada 24 horas, Skype for Business itens são copiados para o site Veritas Merge1. O conector também converte Skype for Business em um formato de mensagem de email.

3. O conector Skype for Business que você cria no Centro de conformidade do Microsoft 365, conecta-se ao site do Veritas Merge1 todos os dias e transfere o conteúdo Skype for Business para um local seguro do Azure Armazenamento na nuvem da Microsoft.

4. O conector importa os itens convertidos para as caixas de correio de usuários específicos usando o valor da propriedade *Email* do mapeamento automático do usuário, conforme descrito [na Etapa 3](#step-3-map-users-and-complete-the-connector-setup). Uma subpasta na pasta Caixa de Entrada chamada **Skype for Business** é criada nas caixas de correio do usuário e os itens são importados para essa pasta. O conector faz isso usando o valor da *propriedade Email.* Cada Skype for Business contém essa propriedade, que é preenchida com o endereço de email de cada participante do item.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar um conector

- Crie uma conta Merge1 para conectores da Microsoft. Para fazer isso, entre em contato [com o Suporte ao Cliente veritas.](https://www.veritas.com/form/requestacall/ms-connectors-contact.html) Você precisa entrar nessa conta ao criar o conector na Etapa 1.

- O usuário que cria o conector Skype for Business na Etapa 1 (e o conclui na Etapa 3) deve ser atribuído à função de Exportação de Importação de Caixa de Correio no Exchange Online. Essa função é necessária para adicionar conectores na página **Conectores de** dados no Centro de conformidade do Microsoft 365. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função Exportar Importação de Importação de Caixa de Correio ao grupo de função Gerenciamento da Organização Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Exportar Importação de Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte as seções Criar grupos de [função](/Exchange/permissions-exo/role-groups#create-role-groups) ou [Modificar](/Exchange/permissions-exo/role-groups#modify-role-groups) grupos de função no artigo "Gerenciar grupos de funções em Exchange Online".

## <a name="step-1-set-up-the-skype-for-business-connector"></a>Etapa 1: Configurar o Skype for Business conector

A primeira etapa é acessar a página **Conectores** de Dados no Centro de conformidade do Microsoft 365 e criar um conector para Skype for Business dados.

1. Vá até <https://compliance.microsoft.com> e clique **em Conectores de dados**  >  **Skype for Business**.

2. Na página **Skype for Business** descrição do produto, clique **em Adicionar conector**.

3. Na página **Termos de serviço,** clique em **Aceitar**.

4. Insira um nome exclusivo que identifique o conector e clique em **Próximo**.

5. Entre na sua conta Merge1 para configurar o conector.

## <a name="step-2-configure-the-skype-for-business-on-the-veritas-merge1-site"></a>Etapa 2: Configurar o Skype for Business no site Mesclagem de Veritas1

A segunda etapa é configurar o conector Skype for Business no site Veritas Merge1. Para obter informações sobre como configurar o conector Skype for Business, consulte [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Skype%20for%20Business%20%20User%20Guide.pdf).

Depois de clicar em Salvar &  **Concluir**, a página de mapeamento do usuário no assistente de conector no Centro de conformidade do Microsoft 365 será exibida.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Etapa 3: mapear usuários e concluir a configuração do conector

Para mapear usuários e concluir a instalação do conector no Centro de conformidade do Microsoft 365, siga estas etapas:

1. Na página **Mapear Skype for Business usuários para Microsoft 365 usuários,** habilita o mapeamento automático do usuário. Os Skype for Business incluem uma propriedade chamada *Email*, que contém endereços de email para usuários em sua organização. Se o conector puder associar esse endereço a um Microsoft 365 usuário, os itens serão importados para a caixa de correio desse usuário.

2. Clique **em Avançar**, revise suas configurações e vá para a página Conectores de dados para ver o andamento do processo de importação do novo conector. 

## <a name="step-4-monitor-the-skype-for-business-connector"></a>Etapa 4: Monitorar o Skype for Business conector

Depois de criar o conector Skype for Business, você poderá exibir o status do conector no Centro de conformidade do Microsoft 365.

1. Vá para <https://compliance.microsoft.com/> e clique **em Conectores de dados** na nav esquerda.

2. Clique na **guia Conectores** e selecione o conector **Skype for Business** para exibir a página de sobrevoo, que contém as propriedades e informações sobre o conector.

3. Em **Status do conector com origem**, clique no link Baixar **log** para abrir (ou salvar) o log de status do conector. Esse log contém dados que foram importados para a nuvem da Microsoft.

## <a name="known-issues"></a>Problemas conhecidos

- Neste momento, não há suporte para importação de anexos ou itens maiores que 10 MB. O suporte para itens maiores estará disponível posteriormente.
