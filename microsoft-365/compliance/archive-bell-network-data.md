---
title: Configurar um conector para arquivar dados de rede SMS/MMS da Bell
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
description: Os administradores podem configurar um conector de Telemensagem para importar e arquivar dados SMS e MMS da rede Bell. Isso permite que você arquive dados de fontes de dados de terceiros no Microsoft 365 para que possa usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar os dados de terceiros da sua organização.
ms.openlocfilehash: d615488e5f6441efd828a6b91c187e7a8f5ca2c8
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620472"
---
# <a name="set-up-a-connector-to-archive-bell-network-data"></a>Configurar um conector para arquivar dados de rede Bell

Use um conector de Telemensagem no centro de conformidade da Microsoft 365 para importar e arquivar mensagens de serviço de mensagens curtas (SMS) e Multimedia Messaging Service (MMS) da rede Bell. Depois de configurar e configurar um conector, ele se conecta à rede de Bell da sua organização uma vez por dia e importa as mensagens SMS e MMS para caixas de correio no Microsoft 365.

Depois que as mensagens SMS e MMS são armazenadas nas caixas de correio do usuário, você pode aplicar recursos de conformidade do Microsoft 365, como retenção de litígio, pesquisa de conteúdo e políticas de retenção da Microsoft 365 para Bell dados de rede. Por exemplo, você pode pesquisar a rede de Bell SMS/MMS usando a pesquisa de conteúdo ou associar a caixa de correio que contém os dados do Bell Network Connector com um funcionário em uma caixa de descoberta eletrônica avançada. O uso de um conector de rede Bell para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a se manter em conformidade com as políticas governamentais e regulamentares.

## <a name="overview-of-archiving-bell-network-data"></a>Visão geral do arquivamento de dados de rede Bell

A visão geral a seguir explica o processo de usar um conector para arquivar dados de rede Bell no Microsoft 365.

![Fluxo de trabalho de arquivamento de rede Bell](../media/BellNetworkConnectorWorkflow.png)

1. Sua organização funciona com telemessage e Bell para configurar um conector de rede Bell. Para obter mais informações, consulte [Bell Network archiverr](https://www.telemessage.com/office365-activation-for-bell-network-archiver).

2. Uma vez a cada 24 horas, as mensagens SMS e MMS da rede de Bell da sua organização são copiadas para o site de Telemensagem.

3. O conector de rede Bell que você cria no centro de conformidade da Microsoft 365 se conecta ao site de Telemensagem todos os dias e transfere as mensagens SMS e MMS das últimas 24 horas para um local seguro de armazenamento do Azure na nuvem da Microsoft. O conector também converte o conteúdo de mensagens SMS e MMS em um formato de mensagem de email.

4. O conector importa os itens de comunicação móvel para a caixa de correio de usuários específicos. Uma nova pasta chamada **Bell SMS/MMS Network Archiver** é criada na caixa de correio de um usuário específico e os itens são importados para ela. O conector faz esse mapeamento usando o valor da propriedade de *endereço de email do usuário* . Cada mensagem SMS e MMS contém essa propriedade, que é preenchida com o endereço de email de cada participante da mensagem.

   Além do mapeamento automático de usuários usando o valor da propriedade de *endereço de email do usuário* , você também pode definir um mapeamento personalizado carregando um arquivo de mapeamento CSV. Este arquivo de mapeamento contém o número de telefone celular e o endereço de email correspondente do Microsoft 365 para usuários em sua organização. Se você habilitar o mapeamento de usuário automático e o mapeamento personalizado, para cada item de rede Bell, o conector procurará primeiro no arquivo de mapeamento personalizado. Se não encontrar um usuário válido do Microsoft 365 que corresponda ao número de telefone celular de um usuário, o conector usará os valores na propriedade de endereço de email do item que está tentando importar. Se o conector não localizar um usuário válido do Microsoft 365 no arquivo de mapeamento personalizado ou na propriedade de endereço de email do item de rede Bell, o item não será importado.

## <a name="before-you-begin"></a>Antes de começar

Algumas das etapas de implementação necessárias para arquivar dados de rede Bell são externas para o Microsoft 365 e devem ser concluídas para que você possa criar um conector no centro de conformidade.

- Solicite o [serviço de arquivador de rede Bell de Telemensagem](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) e obtenha uma conta de administração válida para sua organização. Você precisará entrar nessa conta quando criar o conector no centro de conformidade.

- Obtenha os detalhes do contato de facturação e conta de rede da Bell para que você possa preencher os formulários de integração de Telemensagem e solicitar o serviço de arquivamento de mensagens de Bell.

- Registre todos os usuários que exigem o arquivamento de rede SMS/MMS de Bell na conta de Telemensagem. Ao registrar usuários, certifique-se de usar o mesmo endereço de email usado para a conta do Microsoft 365.

- Seus funcionários devem ter telefones celulares de propriedade corporativa e responsáveis corporativos na rede móvel Bell. O arquivamento de mensagens no Microsoft 365 não está disponível para funcionários de propriedade ou "Traga seus próprios dispositivos (BYOD).

- O usuário que cria um conector de rede Bell deve ser atribuído à função de exportação de importação de caixa de correio no Exchange Online. Isso é necessário para adicionar conectores na página **conectores de dados** no centro de conformidade do Microsoft 365. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função de exportação de importação de caixa de correio ao grupo de funções Gerenciamento da organização no Exchange Online. Ou você pode criar um grupo de função, atribua a função de exportação de importação de caixa de correio e, em seguida, adicione os usuários apropriados como membros. Para obter mais informações, consulte as seções [criar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) ou [modificar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) no artigo "gerenciar grupos de função no Exchange Online".

## <a name="create-a-bell-network-connector"></a>Criar um conector de rede Bell

A última etapa é criar um conector de rede Bell no centro de conformidade da Microsoft 365. O conector usa as informações que você fornece para se conectar ao site de Telemensagem e transferir mensagens SMS/MMS para as caixas de caixa de correio de usuário correspondentes no Microsoft 365.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique em **conectores de dados**  >  **Bell SMS/MMS Network Archiver**.

2. Na página de descrição do produto de **rede Bell** , clique em **Adicionar conector**

3. Na página **termos de serviço** , clique em **aceitar**.

4. Na página **logon na Telemensagem** , em etapa 3, insira as informações necessárias nas caixas a seguir e clique em **Avançar**.

   - **Nome de usuário:** O nome de usuário de sua mensagem.

   - **Senha:** Sua senha de Telemensagem.

5. Depois que o conector é criado, você pode fechar a janela pop-up e ir para a próxima página.

6. Na página **mapeamento de usuário** , habilite o mapeamento de usuário automático. Para habilitar o mapeamento personalizado, carregue um arquivo CSV que contenha as informações de mapeamento do usuário e clique em **Avançar**.

7. Revise suas configurações e clique em **concluir** para criar o conector.

8. Vá até a guia **conectores** na página **conectores de dados** no centro de conformidade para ver o andamento do processo de importação para o novo conector.

## <a name="known-issues"></a>Problemas conhecidos

- No momento, não há suporte para importar anexos ou itens com mais de 10 MB. O suporte para itens maiores estará disponível em uma data posterior.
