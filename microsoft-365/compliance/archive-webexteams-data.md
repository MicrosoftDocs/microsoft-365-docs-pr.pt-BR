---
title: Configurar um conector para dados do Webex Teams no Microsoft 365
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
description: Os administradores podem configurar um conector para importar e arquivar dados do conector do Teams da Webex da Globalnet no Microsoft 365. Esse conector permite arquivar dados de fontes de dados de terceiros no Microsoft 365 para que você possa usar recursos de conformidade como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar dados de terceiros da sua organização.
ms.openlocfilehash: e116b02a53538f7eff4188b670fa6b42b873a9e9
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620217"
---
# <a name="set-up-a-connector-to-archive-webex-teams-data"></a>Configurar um conector para arquivar dados do Webex Teams

Use um conector Globalnet no centro de conformidade do Microsoft 365 para importar e arquivar dados do Webex Teams para as caixas de correio do usuário em sua organização do Microsoft 365. A Globalnet fornece um conector [webex teams](https://globanet.com/webex-teams/) configurado para capturar itens de comunicação do Webex Teams e importá-los para o Microsoft 365. O conector converte conteúdo do Webex Teams, como chats 1:1, conversas em grupo, conversas de canal e anexos da conta do Teams da Webex da sua organização, para um formato de mensagem de email e importa esses itens para a caixa de correio do usuário no Microsoft 365.

Depois que os dados do Webex Teams são armazenados em caixas de correio do usuário, você pode aplicar recursos de conformidade do Microsoft 365, como Retenção de Litígio, Descoberta Eletrônico, políticas de retenção e rótulos de retenção e conformidade de comunicação. Usar um conector do Teams da Webex para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a manter a conformidade com políticas governamentais e regulatórias.

## <a name="overview-of-archiving-webex-teams-data"></a>Visão geral dos dados de arquivamento do Webex Teams

A visão geral a seguir explica o processo de uso de um conector para arquivar dados do Webex Teams no Microsoft 365.

![Fluxo de trabalho de arquivamento para dados do Webex Teams](../media/WebexTeamsConnectorWorkflow.png)

1. Sua organização trabalha com o Webex Teams para configurar e configurar um site do Teams da Webex.

2. Uma vez a cada 24 horas, os itens do Webex Teams são copiados para o site Globalnet Merge1. O conector também converte os itens do Webex Teams em um formato de mensagem de email.

3. O conector do Webex Teams que você cria no centro de conformidade do Microsoft 365, conecta-se à Globalnet Merge1 todos os dias e transfere os itens do Webex Teams para um local seguro de Armazenamento do Azure na nuvem da Microsoft.

4. O conector importa itens para as caixas de correio de usuários específicos usando o valor da propriedade *Email* do mapeamento automático de usuário, conforme descrito na [Etapa 3.](#step-3-map-users-and-complete-the-connector-setup) Uma subpasta na pasta Caixa de Entrada chamada **Webex Teams** é criada nas caixas de correio do usuário, e os itens são importados para essa pasta. O conector faz isso usando o valor da *propriedade Email.* Cada item do Teams da Webex contém essa propriedade, que é preenchida com o endereço de email de cada participante do item.

## <a name="before-you-begin"></a>Antes de começar

- Crie uma conta Globalnet Merge1 para conectores da Microsoft. Para criar essa conta, entre em contato com o Suporte [ao Cliente Globalnet.](https://globanet.com/ms-connectors-contact) Você entrará nessa conta quando criar o conector na Etapa 1.

- Crie um aplicativo para [https://developer.webex.com/](https://developer.webex.com) buscar dados da sua conta do Webex Teams. Para obter instruções passo a passo sobre como criar o aplicativo, consulte [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf)

   Quando você cria esse aplicativo, a plataforma Webex gera um conjunto de credenciais exclusivas. Essas credenciais são usadas na Etapa 2 quando você configura o conector do Webex Teams no site Global Merge1.

- O usuário que cria o conector do Webex Teams na Etapa 1 (e o conclui na Etapa 3) deve ser atribuído à função Importar Exportar Caixa de Correio no Exchange Online. Essa função é necessária para adicionar conectores à página Conectores **de** dados no centro de conformidade do Microsoft 365. Por padrão, essa função não é atribuída a um grupo de funções no Exchange Online. Você pode adicionar a função Importar Exportar Caixa de Correio ao grupo de função Gerenciamento da Organização no Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Importar Exportar Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) as [seções](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) Criar grupos de função ou Modificar grupos de função no artigo "Gerenciar grupos de função no Exchange Online".

## <a name="step-1-set-up-the-webex-teams-connector"></a>Etapa 1: Configurar o conector do Webex Teams

A primeira etapa é obter acesso aos Conectores **de** Dados e configurar o conector [do Webex Teams.](https://globanet.com/webex-teams/)

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique em **Conectores de dados** do  >  **Webex Teams.**

2. Na página de **descrição do produto Webex Teams,** clique **em Adicionar conector.**

3. Na página **Termos de serviço,** clique em **Aceitar**.

4. Insira um nome exclusivo que identifique o conector e clique em **Próximo.**

5. Entre em sua conta Merge1 para configurar o conector.

## <a name="step-2-configure-the-webex-teams-connector-on-the-globanet-merge1-site"></a>Etapa 2: Configurar o conector do Webex Teams no site Globalnet Merge1

A segunda etapa é configurar o conector do Webex Teams no site Merge1. Para obter informações sobre como configurar o conector do Webex Teams, consulte [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf).

Depois que você clicar em Salvar  **& Concluir,** a página de mapeamento do usuário no assistente de conector no centro de conformidade do Microsoft 365 será exibida.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Etapa 3: Mapear usuários e concluir a configuração do conector

Para mapear usuários e concluir a configuração do conector no centro de conformidade do Microsoft 365, siga estas etapas:

1. Na página Mapear usuários do Microsoft Webex Teams para usuários do **Microsoft 365,** habilita o mapeamento automático de usuários. Os itens do Teams da Webex incluem uma propriedade chamada *Email*, que contém endereços de email para usuários em sua organização. Se o conector puder associar esse endereço a um usuário do Microsoft 365, os itens serão importados para a caixa de correio desse usuário.

2. Clique **em Avançar,** revise suas configurações  e vá para a página Conectores de dados para ver o progresso do processo de importação do novo conector.

## <a name="step-4-monitor-the-webex-teams-connector"></a>Etapa 4: Monitorar o conector do Webex Teams

Depois de criar o conector do Webex Teams, você pode exibir o status do conector no centro de conformidade do Microsoft 365.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique **em Conectores de dados** na barra de entrada esquerda.

2. Clique na **guia Conectores e** selecione o conector do **Webex Teams** para exibir a página do flyout. Esta página contém as propriedades e informações sobre o conector.

3. Em **Status do Conector com origem,** clique no link Baixar **log** para abrir (ou salvar) o log de status do conector. Esse log contém informações sobre os dados que foram importados para a nuvem da Microsoft.

## <a name="known-issues"></a>Problemas conhecidos

- No momento, não há suporte para a importação de anexos ou itens maiores do que 10 MB. O suporte para itens maiores estará disponível posteriormente.
