---
title: Configurar um conector de DataParser Desarmado para arquivar dados em Microsoft 365
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
description: Saiba como configurar e usar um conector 17a-4 De DataParser da Orquestra 17a-4 para importar e arquivar dados de orquestra em Microsoft 365.
ms.openlocfilehash: da947c80a296aa4fee8ccabb9bb82eecc1d9b103
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/23/2021
ms.locfileid: "53096907"
---
# <a name="set-up-a-connector-to-archive-symphony-data-preview"></a>Configurar um conector para arquivar dados de orquestra (visualização)

Use [o DataParser](https://www.17a-4.com/Symphony-dataparser/) de 17a-4 LLC para importar e arquivar dados de comunicações da Orquestra Desinfônica para caixas de correio de usuário em sua organização Microsoft 365. O DataParser inclui um conector Defônico configurado para capturar itens de uma fonte de dados de terceiros e importar esses itens para Microsoft 365. O conector De dataParser de orquestração converte dados de orquestra em um formato de mensagem de email e importa esses itens para caixas de correio de usuário em Microsoft 365.

Depois que os dados de Orquestra são armazenados em caixas de correio de usuário, você pode aplicar Microsoft 365 de conformidade, como Retenção de Litígio, Descoberta Eletrônico, políticas de retenção e rótulos de retenção e conformidade de comunicação. O uso de um conector Defônico para importar e arquivar dados em Microsoft 365 pode ajudar sua organização a permanecer em conformidade com políticas governamentais e regulatórias.

## <a name="overview-of-archiving-symphony-data"></a>Visão geral dos dados de arquivamento do Orquestra de Arquivamento

A visão geral a seguir explica o processo de uso de um conector de dados para arquivar dados da Orquestra Microsoft 365.

![Fluxo de trabalho de arquivamento para dados De 17a-4](../media/SymphonyDataParserConnectorWorkflow.png)

1. Sua organização trabalha com o 17a-4 para configurar e configurar o DataParser Da Orquestra.

2. Em uma base regular, os itens de Orquestra são coletados pelo DataParser. O DataParser também converte o conteúdo de uma mensagem em um formato de mensagem de email.

3. O conector De dataParser de orquestra que você cria no Centro de conformidade do Microsoft 365 conecta-se ao DataParser e transfere as mensagens para um local seguro do Azure Armazenamento na nuvem da Microsoft.

4. Uma subpasta na pasta Caixa de Entrada chamada **Dados** Defônicos é criada nas caixas de correio do usuário, e os itens Defônicos são importados para essa pasta. O conector determina para qual caixa de correio importar itens usando o valor da *propriedade Email.* Cada item Da Orquestra Contém essa propriedade, que é preenchida com o endereço de email de cada participante.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar um conector

- Crie uma conta DataParser para conectores da Microsoft. Para fazer isso, entre em [contato com 17a-4 LLC](https://www.17a-4.com/contact/). Você precisa entrar nessa conta ao criar o conector na Etapa 1.

- O usuário que cria o conector De DataParser da Orquestra Na Etapa 1 (e o conclui na Etapa 3) deve ser atribuído à função de Exportação de Importação de Importação de Caixa de Correio no Exchange Online. Essa função é necessária para adicionar conectores na página **Conectores de** dados no Centro de conformidade do Microsoft 365. Por padrão, essa função não é atribuída a um grupo de funções no Exchange Online. Você pode adicionar a função Exportar Importação de Importação de Caixa de Correio ao grupo de função Gerenciamento da Organização Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Exportar Importação de Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte as seções Criar grupos de [função](/Exchange/permissions-exo/role-groups#create-role-groups) ou [Modificar](/Exchange/permissions-exo/role-groups#modify-role-groups) grupos de função no artigo "Gerenciar grupos de funções em Exchange Online".

## <a name="step-1-set-up-a-symphony-dataparser-connector"></a>Etapa 1: Configurar um conector De DataParser Desinfônico

A primeira etapa é acessar a página Conectores de dados no Centro de conformidade do Microsoft 365 e criar um conector 17a-4 para dados de Orquestra.

1. Vá para <https://compliance.microsoft.com> e clique em **Conectores de dados**  >  **DataParser de Orquestra.**

2. Na página Descrição do produto **Do DataParser,** clique em **Adicionar conector**.

3. Na página **Termos de serviço,** clique em **Aceitar**.

4. Insira um nome exclusivo que identifique o conector e clique em **Próximo**.

5. Entre em sua conta do 17a-4 e conclua as etapas no assistente de conexão Do DataParser Da Orquestra.

## <a name="step-2-configure-the-symphony-dataparser-connector"></a>Etapa 2: Configurar o conector De dataParser de orquestra

Trabalhe com o Suporte 17a-4 para configurar o conector De DataParser Da Orquestra.

## <a name="step-3-map-users"></a>Etapa 3: Mapear usuários

O conector De DataParser da Orquestra Desemparsada mapeará automaticamente os usuários para seus endereços de email Microsoft 365 antes de importar dados para Microsoft 365.

## <a name="step-4-monitor-the-symphony-dataparser-connector"></a>Etapa 4: Monitorar o conector De DataParser Da Orquestra

Depois de criar um conector De DataParser Desinfônico, você pode exibir o status do conector no Centro de conformidade do Microsoft 365.

1. Vá para <https://compliance.microsoft.com> e clique **em Conectores de dados** na nav esquerda.

2. Clique na **guia Conectores** e selecione o conector do DataParser de Sinfônico que você criou para exibir a página de sobrevoo, que contém as propriedades e informações sobre o conector.

3. Em **Status do conector com origem**, clique no link Baixar **log** para abrir (ou salvar) o log de status do conector. Esse log contém dados que foram importados para a nuvem da Microsoft.

## <a name="known-issues"></a>Problemas conhecidos

Neste momento, não há suporte para importação de anexos ou itens maiores que 10 MB. O suporte para itens maiores estará disponível posteriormente.
