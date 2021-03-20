---
title: Configurar um conector para arquivar dados de fala de cauda vermelha no Microsoft 365
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
description: Os administradores podem configurar um conector para importar e arquivar dados de Fala de cauda vermelha da Globalnet para o Microsoft 365. Esse conector permite arquivar dados de fontes de dados de terceiros no Microsoft 365. Depois de arquivar esses dados, você pode usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar dados de terceiros.
ms.openlocfilehash: 89b90fd29e089bf61632b22b38e6e10335fda2a8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906055"
---
# <a name="set-up-a-connector-to-archive-redtail-speak-data"></a>Configurar um conector para arquivar dados do Redtail Speak

Use um conector Globalnet no centro de conformidade do Microsoft 365 para importar e arquivar dados do Redtail Fale com caixas de correio de usuário em sua organização do Microsoft 365. A Globalnet fornece um conector [de](https://globanet.com/redtail/) Fala de Cauda Vermelha configurado para capturar itens do servidor SFTP da sua organização, onde os itens são recebidos do Redtail. O conector converte o conteúdo do Redtail Speak em um formato de mensagem de email e importa esses itens para a caixa de correio do usuário no Microsoft 365.

Depois que os dados do Redtail Speak são armazenados em caixas de correio de usuário, você pode aplicar recursos de conformidade do Microsoft 365, como Retenção de Litígio, Descoberta Eletrônico, políticas de retenção e rótulos de retenção. Usar um conector redtail Speak para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a manter-se em conformidade com políticas governamentais e regulatórias.

## <a name="overview-of-archiving-the-redtail-speak-data"></a>Visão geral do arquivamento dos dados do Redtail Speak

A visão geral a seguir explica o processo de uso de um conector para arquivar os dados do Redtail Speak no Microsoft 365.

![Fluxo de trabalho de arquivamento para dados do Redtail Speak](../media/RedtailSpeakConnectorWorkflow.png)

1. Sua organização trabalha com o Redtail Speak para configurar e configurar um gateway SMTP onde as mensagens são encaminhadas do Redtail Speak para o servidor SFTP da sua organização diariamente.

2. Uma vez a cada 24 horas, os itens Redtail Speak são copiados para o site Globalnet Merge1. O conector também converte os itens Redtail Speak em um formato de mensagem de email.

3. O conector de Redtail Speak que você cria no centro de conformidade do Microsoft 365 conecta-se ao site Globalnet Merge1 todos os dias e transfere as mensagens para um local de Armazenamento seguro do Azure na nuvem da Microsoft.

4. O conector importa os itens Redtail Speak convertidos para as caixas de correio de usuários específicos usando o valor da propriedade *Email* do mapeamento automático do usuário, conforme descrito na [Etapa 3](#step-3-map-users-and-complete-the-connector-setup). Uma subpasta na pasta Caixa de Entrada chamada **Redtail Speak** é criada nas caixas de correio do usuário e os itens são importados para essa pasta. O conector determina para qual caixa de correio importar itens usando o valor da *propriedade Email.* Cada item de Redtail Speak contém essa propriedade, que é preenchida com o endereço de email de cada participante do item.

## <a name="before-you-begin"></a>Antes de começar

- Crie uma conta Globalnet Merge1 para conectores da Microsoft. Para criar uma conta, contate [Globalnet Customer Support](https://globanet.com/contact-us/). Você precisa entrar nessa conta ao criar o conector na Etapa 1.

- Na Etapa 2, você precisa especificar o servidor SFTP da sua organização. Esta etapa é necessária para que a Globalnet Merge1 possa contatá-la para coletar dados de Redtail Speak via SFTP.

- O usuário que cria o conector Redtail Speak Importer na Etapa 1 (e o conclui na Etapa 3) deve ser atribuído à função de Exportação de Importação de Caixa de Correio no Exchange Online. Essa função é necessária para adicionar conectores na página Conectores de dados no centro de conformidade do Microsoft 365. Essa função não é atribuída a nenhum grupo de funções no Exchange Online por padrão. Você pode adicionar a função Exportar Importação de Caixa de Correio ao grupo de função Gerenciamento da Organização no Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Exportar Importação de Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte as seções Criar grupos de [função](/Exchange/permissions-exo/role-groups#create-role-groups) ou [Modificar](/Exchange/permissions-exo/role-groups#modify-role-groups) grupos de função no artigo "Gerenciar grupos de função no Exchange Online".

## <a name="step-1-set-up-the-redtail-speak-connector"></a>Etapa 1: Configurar o conector de Fala do Redtail

A primeira etapa é acessar a página **Conectores** de Dados no centro de conformidade do Microsoft 365 e criar um conector para os dados do Redtail Speak.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e selecione **Conectores de dados** &gt; **Redtail Speak**.

2. Na página Descrição do produto **Redtail Speak,** selecione **Adicionar novo conector**.

3. Na página **Termos de serviço,** selecione **Aceitar**.

4. Insira um nome exclusivo que identifique o conector e selecione **Next**.

5. Entre na sua conta Merge1 para configurar o conector.

## <a name="step-2-configure-the-redtail-speak-connector-on-the-globanet-merge1-site"></a>Etapa 2: Configurar o conector de Fala de Redtail no site Globalnet Merge1

A segunda etapa é configurar o conector de Fala do Redtail no site Merge1. Para obter informações sobre como configurar o conector de Fala do Redtail, consulte [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Redtail%20Speak%20User%20Guide%20.pdf).

Depois de selecionar Salvar &  **Concluir,** a página de mapeamento do usuário no assistente de conector no centro de conformidade do Microsoft 365 será exibida.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Etapa 3: mapear usuários e concluir a configuração do conector

Para mapear usuários e concluir a configuração do conector, siga estas etapas:

1. Na página **Map Redtail Speak users to Microsoft 365 users** page, enable automatic user mapping. Os itens Redtail Speak incluem uma propriedade chamada *Email*, que contém endereços de email para usuários em sua organização. Se o conector puder associar esse endereço a um usuário do Microsoft 365, os itens serão importados para a caixa de correio desse usuário.

2. Selecione **Avançar**, revise suas configurações e vá para a página **Conectores** de dados para ver o andamento do processo de importação do novo conector.

## <a name="step-4-monitor-the-redtail-speak-connector"></a>Etapa 4: Monitorar o conector de Fala de Cauda Vermelha

Depois de criar o conector Redtail Speak, você pode exibir o status do conector no centro de conformidade do Microsoft 365.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e selecione **Conectores de dados** na nav esquerda.

2. Selecione a **guia Conectores** e selecione o conector de Fala **do Redtail** para exibir a página de sobrevoo. Esta página exibe propriedades e informações sobre o conector.

3. Em **Status do conector com origem,** selecione o link Baixar **log** para abrir (ou salvar) o log de status do conector. Esse log contém dados que foram importados para a nuvem da Microsoft.

## <a name="known-issues"></a>Problemas conhecidos

- Neste momento, não há suporte para importação de anexos ou itens maiores que 10 MB. O suporte para itens maiores estará disponível posteriormente.