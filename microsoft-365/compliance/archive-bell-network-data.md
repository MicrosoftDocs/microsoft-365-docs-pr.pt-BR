---
title: Configurar um conector para arquivar dados da Rede SMS/MMS do Bell
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
description: Os administradores podem configurar um conector teleMessage para importar e arquivar dados SMS e MMS da Rede sino. Isso permite que você arquive dados de fontes de dados de terceiros no Microsoft 365 para que você possa usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar os dados de terceiros da sua organização.
ms.openlocfilehash: 7cfdb4556c19261b7e377df72ebe96b9cf20c992
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822209"
---
# <a name="set-up-a-connector-to-archive-bell-network-data"></a>Configurar um conector para arquivar dados da Rede do Sino

Use um conector teleMessage no centro de conformidade Microsoft 365 para importar e arquivar mensagens do Serviço de Mensagens Curtas (SMS) e mms do Serviço de Mensagens Multimídia (MMS) da Rede do Sino. Depois de configurar e configurar um conector, ele se conecta à Rede sino da sua organização uma vez por dia e importa mensagens SMS MMS para caixas de correio em Microsoft 365.

Depois que as mensagens SMS e MMS são armazenadas em caixas de correio de usuário, você pode aplicar recursos de conformidade Microsoft 365 como Retenção de Litígio, Pesquisa de Conteúdo e políticas de retenção Microsoft 365 a dados da Rede Do Sino. Por exemplo, você pode pesquisar o Sino Network SMS/MMS usando a Pesquisa de Conteúdo ou associar a caixa de correio que contém os dados do conector da Rede do Sino com um custodiante em um caso Advanced eDiscovery. Usar um conector de Rede do Sino para importar e arquivar dados em Microsoft 365 pode ajudar sua organização a permanecer em conformidade com políticas governamentais e regulatórias.

## <a name="overview-of-archiving-bell-network-data"></a>Visão geral dos dados do Bell Network de arquivamento

A visão geral a seguir explica o processo de uso de um conector para arquivar dados da Rede sino no Microsoft 365.

![Fluxo de trabalho de arquivamento do Bell Network](../media/BellNetworkConnectorWorkflow.png)

1. Sua organização trabalha com TeleMessage e Bell para configurar um conector de Rede do Sino. Para obter mais informações, consulte [Bell Network Archiver](https://www.telemessage.com/office365-activation-for-bell-network-archiver).

2. Em tempo real, SMS e mensagens MMS da Rede sino da sua organização são copiadas para o site teleMessage.

3. O conector de Rede do Sino criado no centro de conformidade do Microsoft 365 conecta-se ao site do TeleMessage todos os dias e transfere as mensagens SMS e MMS das 24 horas anteriores para um local seguro do Azure Armazenamento na nuvem da Microsoft. O conector também converte o conteúdo de mensagens SMS e MMS em um formato de mensagem de email.

4. O conector importa os itens de comunicação móvel para a caixa de correio de usuários específicos. Uma nova pasta chamada **Bell SMS/MMS Network Archiver** é criada na caixa de correio de um usuário específico e os itens são importados para ela. O conector faz esse mapeamento usando o valor da *propriedade endereço email do* usuário. Cada SMS e mensagem MMS contém essa propriedade, que é preenchida com o endereço de email de cada participante da mensagem.

   Além do mapeamento automático do usuário usando o valor da propriedade endereço *email* do usuário, você também pode definir um mapeamento personalizado carregando um arquivo de mapeamento CSV. Este arquivo de mapeamento contém o número de telefone celular e o endereço Microsoft 365 email correspondente para usuários em sua organização. Se você habilitar o mapeamento automático do usuário e o mapeamento personalizado, para cada item da Rede do Sino, o conector primeiro olhará para o arquivo de mapeamento personalizado. Se ele não encontrar um usuário Microsoft 365 que corresponda ao número de telefone celular de um usuário, o conector usará os valores na propriedade endereço de email do item que está tentando importar. Se o conector não encontrar um usuário Microsoft 365 no arquivo de mapeamento personalizado ou na propriedade de endereço de email do item da Rede do Sino, o item não será importado.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar um conector

Algumas das etapas de implementação necessárias para arquivar dados da Rede do Sino são externas Microsoft 365 e devem ser concluídas antes que você possa criar um conector no centro de conformidade.

- Peça o serviço de Arquivamento de Rede de Sino [do TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) e obter uma conta de administração válida para sua organização. Você precisará entrar nessa conta quando criar o conector no centro de conformidade.

- Obtenha seus detalhes de contato de conta e cobrança do Bell Network para que você possa preencher os formulários de integração do TeleMessage e solicitar o serviço de arquivamento de mensagens do Bell.

- Registre todos os usuários que exigem o arquivamento da Rede SMS/MMS do Bell na conta teleMessage. Ao registrar usuários, certifique-se de usar o mesmo endereço de email usado para sua conta Microsoft 365.

- Seus funcionários devem ter telefones móveis corporativos e corporativos na rede móvel da Bell. As mensagens de arquivamento no Microsoft 365 não estão disponíveis para dispositivos de propriedade do funcionário ou "Traga seus próprios dispositivos (BYOD).

- O usuário que cria um conector de Rede do Sino deve receber a função de Exportação de Importação de Caixa de Correio Exchange Online. Isso é necessário para adicionar conectores na página **Conectores** de dados no Microsoft 365 de conformidade. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função Exportar Importação de Importação de Caixa de Correio ao grupo de função Gerenciamento da Organização Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Exportar Importação de Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte as seções Criar grupos de [função](/Exchange/permissions-exo/role-groups#create-role-groups) ou [Modificar](/Exchange/permissions-exo/role-groups#modify-role-groups) grupos de função no artigo "Gerenciar grupos de funções em Exchange Online".

- Esse conector de dados está disponível em GCC ambientes na nuvem Microsoft 365 Us Government. Aplicativos e serviços de terceiros podem envolver o armazenamento, a transmissão e o processamento dos dados do cliente da sua organização em sistemas de terceiros que estão fora da infraestrutura do Microsoft 365 e, portanto, não são cobertos pelos compromissos de conformidade e proteção de dados do Microsoft 365. A Microsoft não faz nenhuma representação de que o uso desse produto para se conectar a aplicativos de terceiros implica que esses aplicativos de terceiros são compatíveis com FEDRAMP.

## <a name="create-a-bell-network-connector"></a>Criar um conector de Rede do Sino

A última etapa é criar um conector de Rede do Sino no Microsoft 365 de conformidade. O conector usa as informações fornecidas para se conectar ao site teleMessage e transferir mensagens SMS/MMS para as caixas de correio de usuário correspondentes no Microsoft 365.

1. Vá até [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique em **Conectores de dados**  >  **Conectores de SMS/MMS Network Archiver**.

2. Na página **Descrição do produto da Rede** do Sino, clique em Adicionar **conector**

3. Na página **Termos de serviço,** clique em **Aceitar**.

4. Na página **Logon para TeleMessage,** em Etapa 3, insira as informações necessárias nas caixas a seguir e clique em **Próximo**.

   - **Nome de usuário:** Seu nome de usuário teleMessage.

   - **Senha:** Sua senha teleMessage.

5. Depois que o conector for criado, você poderá fechar a janela pop-up e ir para a próxima página.

6. Na página **Mapeamento de** usuário, habilita o mapeamento automático do usuário. Para habilitar o mapeamento personalizado, carregue um arquivo CSV que contém as informações de mapeamento do usuário e clique em **Próximo**.

7. Revise suas configurações e clique em **Concluir** para criar o conector.

8. Vá até a **guia Conectores** na página **Conectores** de dados no centro de conformidade para ver o andamento do processo de importação do novo conector.

## <a name="known-issues"></a>Problemas conhecidos

- Neste momento, não há suporte para importação de anexos ou itens maiores que 10 MB. O suporte para itens maiores estará disponível posteriormente.
