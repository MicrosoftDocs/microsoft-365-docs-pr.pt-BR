---
title: Configurar um conector para arquivar dados de Reuniões de Zoom no Microsoft 365
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
description: Os administradores podem configurar um conector para importar e arquivar dados de Reuniões globanet Zoom para o Microsoft 365. Isso permite que você arquive dados de fontes de dados de terceiros no Microsoft 365 para que você possa usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar os dados de terceiros da sua organização.
ms.openlocfilehash: a8f6ab0a629054457a3a0dc7cbbe74c051820058
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923357"
---
# <a name="set-up-a-connector-to-archive-zoom-meetings-data"></a>Configurar um conector para arquivar dados de Reuniões de Zoom

Use um conector Globalnet no centro de conformidade do Microsoft 365 para importar e arquivar dados de Reuniões de Zoom para caixas de correio de usuário em sua organização do Microsoft 365. A Globalnet fornece um [conector de](https://globanet.com/zoom/) Reuniões de Zoom configurado para capturar itens da fonte de dados de terceiros (regularmente) e importar esses itens para o Microsoft 365. O conector converte o conteúdo das reuniões (incluindo chats, arquivos gravados e metadados) da conta Reuniões de Zoom para um formato de mensagem de email e importa esses itens para caixas de correio de usuário no Microsoft 365.

Depois que os dados de Reuniões de Zoom são armazenados em caixas de correio de usuário, você pode aplicar recursos de conformidade do Microsoft 365, como Retenção de Litígio, Descoberta Eletrônico, políticas de retenção e rótulos de retenção e conformidade de comunicação. Usar um conector de Reuniões de Zoom para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a permanecer em conformidade com políticas governamentais e regulatórias.

## <a name="overview-of-archiving-zoom-meetings-data"></a>Visão geral dos dados de Reuniões de Zoom de arquivamento

A visão geral a seguir explica o processo de uso de um conector para arquivar dados de Reuniões de Zoom no Microsoft 365.

![Fluxo de trabalho de arquivamento de Reuniões de Zoom](../media/ZoomMeetingsConnectorWorkflow.png)

1. Sua organização trabalha com Reuniões de Zoom para configurar e configurar um site de Reuniões de Zoom.

2. Uma vez a cada 24 horas, os itens de reunião de Reuniões de Zoom são copiados para o site Globalnet Merge1. O conector também converte o conteúdo das reuniões em um formato de mensagem de email.

3. O conector reuniões de zoom que você cria no centro de conformidade do Microsoft 365, conecta-se à Globalnet Merge1 todos os dias e transfere as mensagens de reunião para um local seguro de Armazenamento do Azure na nuvem da Microsoft.

4. O conector importa os itens de reunião convertidos para as caixas de correio de usuários específicos usando o valor da propriedade *Email* e o mapeamento automático do usuário, conforme descrito na Etapa 3. Uma nova subpasta na pasta Caixa de Entrada chamada Reuniões de **Zoom** é criada em caixas de correio de usuário e os itens de reunião são importados para essa pasta. O conector faz isso usando o valor da *propriedade Email.* Cada item de reunião contém essa propriedade, que é preenchida com o endereço de email de cada participante da reunião.

## <a name="before-you-begin"></a>Antes de começar

- Crie uma conta Globalnet Merge1 para conectores da Microsoft. Para criar essa conta, contate [Globalnet Customer Support](https://globanet.com/ms-connectors-contact). Você entrará nessa conta quando criar o conector na Etapa 1.

- Obtenha o nome de usuário e a senha da conta Zoom Business ou Zoom Enterprise da sua organização. Você precisará entrar nessa conta na Etapa 2 quando configurar o conector de Reuniões de Zoom.

- Crie os seguintes aplicativos no [Marketplace zoom](https://marketplace.zoom.us):

  - Aplicativo OAuth

  - Aplicativo JWT

  Depois de criar esses aplicativos, a plataforma Zoom gera um conjunto de credenciais exclusivas usadas para gerar os tokens. Esses tokens são usados para autenticar o conector quando ele se conecta à sua conta zoom e copia itens para o site Merge1. Você usará esses tokens quando configurar o conector zoom na Etapa 2.

  Para obter instruções passo a passo sobre como criar os aplicativos OAuth e JWT, consulte [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf).

- O usuário que cria o conector reuniões de zoom na Etapa 1 (e o conclui na Etapa 3) deve ser atribuído à função De exportação de importação de caixa de correio no Exchange Online. Essa função é necessária para adicionar conectores na página **Conectores de** dados no centro de conformidade do Microsoft 365. Por padrão, essa função não é atribuída a um grupo de funções no Exchange Online. Você pode adicionar a função Exportar Importação de Caixa de Correio ao grupo de função Gerenciamento da Organização no Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Exportar Importação de Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte as seções Criar grupos de [função](/Exchange/permissions-exo/role-groups#create-role-groups) ou [Modificar](/Exchange/permissions-exo/role-groups#modify-role-groups) grupos de função no artigo "Gerenciar grupos de função no Exchange Online".

## <a name="step-1-set-up-the-zoom-meetings-connector"></a>Etapa 1: Configurar o conector de Reuniões de Zoom

A primeira etapa é acessar os **Conectores** de Dados no centro de conformidade do Microsoft 365 e criar um conector de Reuniões de Zoom.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique em **Conectores de dados Reuniões** de  >  **zoom.**

2. Na página **Descrição do produto Reuniões** de Zoom, clique em Adicionar **conector**.

3. Na página **Termos de serviço,** clique em **Aceitar**.

4. Insira um nome exclusivo que identifique o conector e clique em **Próximo**.

5. Entre na sua conta Merge1 para configurar o conector.

## <a name="step-2-configure-the-zoom-meetings-connector"></a>Etapa 2: Configurar o conector de Reuniões de Zoom

A segunda etapa é configurar o conector de Reuniões de Zoom no site Merge1. Para obter mais informações sobre como configurar o conector de Reuniões de Zoom no site Globalnet Merge1, consulte [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf).

Depois de clicar em Salvar &  **Concluir**, a página de mapeamento do usuário no assistente de conector no centro de conformidade do Microsoft 365 será exibida.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Etapa 3: mapear usuários e concluir a configuração do conector

1. Na página **Mapear usuários externos para usuários do Microsoft 365,** habilita o mapeamento automático do usuário.

   Os itens reuniões de zoom incluem uma propriedade chamada *Email* que contém endereços de email para usuários em sua organização. Se o conector puder associar esse endereço a um usuário do Microsoft 365, os itens serão importados para a caixa de correio desse usuário

2. Clique **em Avançar,** revise suas configurações e vá até a página **Conectores** de dados para ver o andamento do processo de importação do novo conector.

## <a name="step-4-monitor-the-zoom-meetings-connector"></a>Etapa 4: Monitorar o conector de Reuniões de Zoom

Depois de criar o conector reuniões de zoom, você pode exibir o status do conector no centro de conformidade do Microsoft 365.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique **em Conectores de dados** na nav esquerda.

2. Clique na **guia Conectores** e selecione o **conector reuniões** de zoom para exibir a página de sobrevoo. Esta página contém as propriedades e informações sobre o conector.

3. Em **Status do conector com origem**, clique no link Baixar **log** para abrir (ou salvar) o log de status do conector. Esse log contém informações sobre os dados que foram importados para a nuvem da Microsoft.

## <a name="known-issues"></a>Problemas conhecidos

- Neste momento, não há suporte para importação de anexos ou itens maiores que 10 MB. O suporte para itens maiores estará disponível posteriormente.

- Para que o conector de Reuniões de Zoom funcione, você deve habilitar gravações ao configurar Reuniões de Zoom.