---
title: Configurar um conector para arquivar dados do ServiceNow no Microsoft 365
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
description: Os administradores podem configurar um conector para importar e arquivar dados do ServiceNow do Globanet para o Microsoft 365. Esse conector permite que você arquive dados de fontes de dados de terceiros no Microsoft 365. Após o arquivamento desses dados, você pode usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar dados de terceiros.
ms.openlocfilehash: 4139e66cc1554b7a7306c6076fd8475fe47f5cf5
ms.sourcegitcommit: a3215cc22faa47e935d22300c481e47ab2680b44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2020
ms.locfileid: "49722919"
---
# <a name="set-up-a-connector-to-archive-servicenow-data-preview"></a>Configurar um conector para arquivar dados do ServiceNow (visualização)

Use um conector Globanet no centro de conformidade da Microsoft 365 para importar e arquivar dados da plataforma do ServiceNow para caixas de correio do usuário na sua organização do Microsoft 365. O Globanet fornece um conector do [ServiceNow](https://globanet.com/servicenow/) que captura itens da fonte de dados de terceiros e importa esses itens para o Microsoft 365. O conector converte o conteúdo, como mensagens dinâmicas, anexos e postagens do ServiceNow em um formato de mensagem de email e, em seguida, importa esses itens para caixas de correio do usuário no Microsoft 365.

Após os dados do ServiceNow serem armazenados nas caixas de correio do usuário, você pode aplicar recursos de conformidade do Microsoft 365, como retenção de litígio, descoberta eletrônica, políticas de retenção e rótulos de retenção. O uso de um conector do ServiceNow para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a se manter em conformidade com as políticas governamentais e regulamentares.

## <a name="overview-of-archiving-servicenow-data"></a>Visão geral do arquivamento de dados do ServiceNow

A visão geral a seguir explica o processo de usar um conector para arquivar os dados do ServiceNow no Microsoft 365.

![Fluxo de trabalho de arquivamento para dados do ServiceNow](../media/ServiceNowConnectorWorkflow.png)

1. Sua organização funciona com o ServiceNow para configurar e configurar um site do ServiceNow.

2. Uma vez a cada 24 horas, os itens do ServiceNow são copiados para o site do Globanet Merge1. O conector também converte itens do ServiceNow em um formato de mensagem de email.

3. O conector do ServiceNow que você cria no centro de conformidade da Microsoft 365 conecta-se ao site do Globanet Merge1 todos os dias e transfere o conteúdo do ServiceNow para um local seguro de armazenamento do Azure na nuvem da Microsoft.

4. O conector importa os itens convertidos para as caixas de correio de usuários específicos usando o valor da propriedade *email* do mapeamento de usuário automático, conforme descrito na [etapa 3](#step-3-map-users-and-complete-the-connector-setup). Uma subpasta na pasta caixa de entrada chamada **ServiceNow** é criada nas caixas de correio do usuário e os itens são importados para essa pasta. O conector determina qual caixa de correio para a qual importar itens usando o valor da propriedade *email* . Cada item do ServiceNow contém essa propriedade, que é preenchida com o endereço de email de cada participante do item.

## <a name="before-you-begin"></a>Antes de começar

- Crie uma conta do Merge1 para conectores da Microsoft. Para criar uma conta, entre em contato com o [suporte ao cliente Globanet](https://globanet.com/contact-us/). Você precisa entrar nessa conta ao criar o conector na etapa 1.

- Criar um aplicativo do ServiceNow para buscar dados de sua conta do ServiceNow. Para obter instruções passo a passo sobre como criar o aplicativo, consulte [Merge1 do usuário de conectores de terceiros](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20ServiceNow%20User%20Guide%20.pdf).

- O usuário que cria o conector do ServiceNow na etapa 1 (e conclui-lo na etapa 3) deve ser atribuído à função de exportação de importação de caixa de correio no Exchange Online. Essa função é necessária para adicionar conectores na página **conectores de dados** no centro de conformidade da Microsoft 365. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função de exportação de importação de caixa de correio ao grupo de funções Gerenciamento da organização no Exchange Online. Ou você pode criar um grupo de função, atribua a função de exportação de importação de caixa de correio e, em seguida, adicione os usuários apropriados como membros. Para obter mais informações, consulte as seções [criar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) ou [modificar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) no artigo "gerenciar grupos de função no Exchange Online".

## <a name="step-1-set-up-the-servicenow-connector"></a>Etapa 1: configurar o conector do ServiceNow

A primeira etapa é acessar a página **conectores de dados** no centro de conformidade da Microsoft 365 e criar um conector para os dados do ServiceNow.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique em **conectores de dados** do  >  **ServiceNow**.

2. Na página de descrição do produto do **ServiceNow** , clique em **Adicionar conector**.

3. Na página **termos de serviço** , clique em **aceitar**.

4. Insira um nome exclusivo que identifique o conector e clique em **Avançar**.

5. Entre em sua conta do Merge1 para configurar o conector.

## <a name="step-2-configure-the-servicenow-on-the-globanet-merge1-site"></a>Etapa 2: configurar o ServiceNow no site do Globanet Merge1

A segunda etapa é configurar o conector do ServiceNow no site do Globanet Merge1. Para obter informações sobre como configurar o conector do ServiceNow, consulte [Merge1 do usuário de conectores de terceiros](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20ServiceNow%20User%20Guide%20.pdf).

Depois de clicar em **salvar & concluir,** a página **mapeamento de usuário** no assistente de conector no centro de conformidade da Microsoft 365 é exibida.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Etapa 3: mapear usuários e concluir a configuração do conector

Para mapear usuários e concluir a configuração do conector no centro de conformidade do Microsoft 365, siga estas etapas:

1. Na página **mapear usuários do ServiceNow para usuários do Microsoft 365** , habilite o mapeamento automático do usuário. Os itens do ServiceNow incluem uma propriedade chamada *email*, que contém endereços de email para usuários em sua organização. Se o conector puder associar esse endereço a um usuário do Microsoft 365, os itens serão importados para a caixa de correio desse usuário.

2. Clique em **Avançar**, revise suas configurações e vá para a página **conectores de dados** para ver o andamento do processo de importação para o novo conector.

## <a name="step-4-monitor-the-servicenow-connector"></a>Etapa 4: monitorar o conector do ServiceNow

Depois de criar o conector do ServiceNow, você pode visualizar o status do conector no centro de conformidade da Microsoft 365.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique em **conectores de dados** no painel de navegação esquerdo.

2. Clique na guia **conectores** e selecione o conector do **ServiceNow** para exibir a página do menu suspenso, que contém as propriedades e informações sobre o conector.

3. Em **status do conector com origem**, clique no link **baixar log** para abrir (ou salvar) o log de status do conector. Esse log contém dados que foram importados para a nuvem da Microsoft.

## <a name="known-issues"></a>Problemas conhecidos

- No momento, não há suporte para importar anexos ou itens com mais de 10 MB. O suporte para itens maiores estará disponível em uma data posterior.
