---
title: Configurar um conector para arquivar Redtail falar dados no Microsoft 365
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
description: Os administradores podem configurar um conector para importar e arquivar Redtail falar dados do Globanet para o Microsoft 365. Esse conector permite que você arquive dados de fontes de dados de terceiros no Microsoft 365. Após o arquivamento desses dados, você pode usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar dados de terceiros.
ms.openlocfilehash: 546298288e69746856a1250cc4b87643dd479c91
ms.sourcegitcommit: a3215cc22faa47e935d22300c481e47ab2680b44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2020
ms.locfileid: "49722926"
---
# <a name="set-up-a-connector-to-archive-redtail-speak-data-preview"></a>Configurar um conector para arquivar dados de fala Redtail (visualização)

Use um conector Globanet no centro de conformidade da Microsoft 365 para importar e arquivar dados das caixas de correio do Redtail falar com o usuário na sua organização do Microsoft 365. O Globanet fornece um conector de [fala do Redtail](https://globanet.com/redtail/) que é configurado para capturar itens do servidor SFTP da sua organização onde os itens são recebidos do Redtail. O conector converte o conteúdo de Redtail fala para um formato de mensagem de email e, em seguida, importa esses itens para a caixa de correio do usuário no Microsoft 365.

Depois que os dados de fala do Redtail são armazenados nas caixas de correio do usuário, você pode aplicar recursos de conformidade da Microsoft 365, como retenção de litígio, descoberta eletrônica, políticas de retenção e rótulos de retenção. O uso de um conector de fala do Redtail para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a se manter em conformidade com as políticas governamentais e regulamentares.

## <a name="overview-of-archiving-the-redtail-speak-data"></a>Visão geral do arquivamento dos dados de fala do Redtail

A visão geral a seguir explica o processo de usar um conector para arquivar os dados de fala do Redtail no Microsoft 365.

![Fluxo de trabalho de arquivamento para dados de fala do Redtail](../media/RedtailSpeakConnectorWorkflow.png)

1. Sua organização funciona com o Redtail fala para configurar e configurar um gateway SMTP onde as mensagens diárias são encaminhadas de Redtail fala para seu servidor de organizações SFTP.

2. Uma vez a cada 24 horas, os itens de fala Redtail são copiados para o site do Globanet Merge1. O conector também converte os itens de fala Redtail em um formato de mensagem de email.

3. O conector de fala do Redtail que você cria no centro de conformidade da Microsoft 365 conecta-se ao site do Globanet Merge1 todos os dias e transfere as mensagens para um local seguro de armazenamento do Azure na nuvem da Microsoft.

4. O conector importa os itens convertidos de fala Redtail para as caixas de correio de usuários específicos usando o valor da propriedade *email* do mapeamento de usuário automático, conforme descrito na [etapa 3](#step-3-map-users-and-complete-the-connector-setup). Uma subpasta na pasta caixa de entrada chamada **Redtail Speak** é criada nas caixas de correio do usuário e os itens são importados para essa pasta. O conector determina qual caixa de correio para a qual importar itens usando o valor da propriedade *email* . Cada item de fala do Redtail contém essa propriedade, que é preenchida com o endereço de email de cada participante do item.

## <a name="before-you-begin"></a>Antes de começar

- Crie uma conta do Merge1 do Globanet para conectores da Microsoft. Para criar uma conta, entre em contato com o [suporte ao cliente Globanet](https://globanet.com/contact-us/). Você precisa entrar nessa conta ao criar o conector na etapa 1.

- Na etapa, você precisa especificar o servidor SFTP da sua organização. Isso é necessário para que o Globanet Merge1 possa contatá-lo para coletar dados de fala do Redtail via SFTP.

- O usuário que cria o conector de Redtail Speak conporter na etapa 1 (e conclui-lo na etapa 3) deve ser atribuído à função de exportação de importação de caixa de correio no Exchange Online. Essa função é necessária para adicionar conectores na página conectores de dados no centro de conformidade da Microsoft 365. Por padrão, essa função não é atribuída a nenhum grupo de função no Exchange Online. Você pode adicionar a função de exportação de importação de caixa de correio ao grupo de funções Gerenciamento da organização no Exchange Online. Ou você pode criar um grupo de função, atribua a função de exportação de importação de caixa de correio e, em seguida, adicione os usuários apropriados como membros. Para obter mais informações, consulte as seções [criar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) ou [modificar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) no artigo "gerenciar grupos de função no Exchange Online".

## <a name="step-1-set-up-the-redtail-speak-connector"></a>Etapa 1: configurar o conector de fala do Redtail

A primeira etapa é acessar a página **conectores de dados** no centro de conformidade da Microsoft 365 e criar um conector para os dados de fala do Redtail.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique em **conectores de dados** &gt; **Redtail falar**.

2. Na página de descrição do produto **Redtail Speak** , clique em **Adicionar novo conector**.

3. Na página **termos de serviço** , clique em **aceitar**.

4. Insira um nome exclusivo que identifique o conector e clique em **Avançar**.

5. Entre em sua conta do Merge1 para configurar o conector.

## <a name="step-2-configure-the-redtail-speak-connector-on-the-globanet-merge1-site"></a>Etapa 2: configurar o conector de fala do Redtail no site do Globanet Merge1

A segunda etapa é configurar o conector de fala do Redtail no site Merge1. Para obter informações sobre como configurar o conector de fala do Redtail, consulte [Merge1 de terceiros conectores do usuário](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Redtail%20Speak%20User%20Guide%20.pdf).

Depois de clicar em **salvar & concluir**, a página **mapeamento de usuário** no assistente de conector no centro de conformidade da Microsoft 365 é exibida.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Etapa 3: mapear usuários e concluir a configuração do conector

Para mapear usuários e concluir a configuração do conector, siga estas etapas:

1. Na página **mapear Redtail falar usuários para usuários do Microsoft 365** , habilite o mapeamento automático do usuário. Os itens de fala do Redtail incluem uma propriedade chamada *email*, que contém endereços de email para usuários em sua organização. Se o conector puder associar esse endereço a um usuário do Microsoft 365, os itens serão importados para a caixa de correio desse usuário.

2. Clique em **Avançar**, revise suas configurações e vá para a página **conectores de dados** para ver o andamento do processo de importação para o novo conector.

## <a name="step-4-monitor-the-redtail-speak-connector"></a>Etapa 4: monitorar o conector de fala do Redtail

Depois de criar o conector de fala do Redtail, você pode visualizar o status do conector no centro de conformidade da Microsoft 365.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique em **conectores de dados** no painel de navegação esquerdo.

2. Clique na guia **conectores** e selecione o conector de **fala do Redtail** para exibir a página do menu suspenso. Esta página exibe as propriedades e as informações sobre o conector.

3. Em **status do conector com origem**, clique no link **baixar log** para abrir (ou salvar) o log de status do conector. Esse log contém dados que foram importados para a nuvem da Microsoft.

## <a name="known-issues"></a>Problemas conhecidos

- No momento, não há suporte para importar anexos ou itens com mais de 10 MB. O suporte para itens maiores estará disponível em uma data posterior.
