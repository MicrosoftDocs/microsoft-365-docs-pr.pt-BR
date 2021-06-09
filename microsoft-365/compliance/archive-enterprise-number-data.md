---
title: Configurar um conector para arquivar dados do Arquivo Mortor de Números Enterprise TeleMessage
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
description: Os administradores podem configurar um conector para importar e arquivar dados SMS MMS e do TeleMessage Enterprise Arquivo Mortor de Números. Isso permite que você arquive dados de fontes de dados de terceiros no Microsoft 365 para que você possa usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar os dados de terceiros da sua organização.
ms.openlocfilehash: 1615aaed21eca6d0c8c22343e19c1ea93b693aaa
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822197"
---
# <a name="set-up-a-connector-to-archive-enterprise-number-data"></a>Configurar um conector para arquivar dados Enterprise Número

Use um conector de TeleMessage no centro de conformidade do Microsoft 365 para importar e arquivar mensagens do Serviço de Mensagens Curtas (SMS) e mmS (Serviço de Mensagens Multimídia), mensagens de chat, gravações de chamada de voz e logs de chamada de voz do Enterprise Number Archiver. Depois de configurar e configurar um conector, ele se conecta à conta teleMessage da sua organização uma vez por dia e importa os dados de comunicação móvel dos funcionários usando o Arquivo Mortor de Números do TeleMess Enterprise age para caixas de correio em Microsoft 365.

Depois que os dados do conector de Arquivo de Número do TeleMessage Enterprise são armazenados em caixas de correio de usuário, você pode aplicar recursos de conformidade do Microsoft 365, como Retenção de Litígio, Pesquisa de Conteúdo, Arquivamento de In-Place, Auditoria, Conformidade de Comunicação e políticas de retenção Microsoft 365 para Enterprise dados do Arquivo de Números. Por exemplo, você pode pesquisar o Arquivo de Número Enterprise TeleMessage SMS, MMS e Chamada de Voz usando a Pesquisa de Conteúdo ou associar a caixa de correio que contém os dados do conector do arquivo mortor de números do Enterprise a um custodiante em um caso Advanced eDiscovery. Usar um conector Enterprise Desarmador de Números para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a permanecer em conformidade com políticas governamentais e regulatórias.

## <a name="overview-of-archiving-enterprise-number-data"></a>Visão geral do arquivamento Enterprise dados de número

A visão geral a seguir explica o processo de uso de um conector para arquivar Enterprise dados de rede em Microsoft 365.

![Enterprise Fluxo de trabalho de arquivamento de números](../media/EnterpriseNumberConnectorWorkflow.png)

1. Sua organização trabalha com o TeleMessage para configurar um conector Enterprise Arquivo Mortor de Números. Para obter mais detalhes, consulte [aqui](https://www.telemessage.com/office365-activation-for-enterprise-number-archiver/).

2. O conector Enterprise de Arquivo de Números que você cria no centro de conformidade do Microsoft 365 conecta-se ao site do TeleMessage todos os dias e transfere as mensagens de email das 24 horas anteriores para uma área segura do Azure Armazenamento no Microsoft Cloud.

3. O conector importa os itens de comunicação móvel para a caixa de correio de um usuário específico. Uma nova pasta chamada Enterprise Arquivo Mortor de Números é criada na caixa de correio do usuário específico e os itens são importados para ela. O conector faz o mapeamento usando o valor da *propriedade endereço email do* usuário. Cada mensagem de email contém essa propriedade, que é preenchida com o endereço de email de cada participante da mensagem de email. Além do mapeamento automático do usuário usando o valor da propriedade endereço *email* do usuário, você também pode definir um mapeamento personalizado carregando um arquivo de mapeamento CSV. Esse arquivo de mapeamento deve conter o Número móvel do usuário e o endereço Microsoft 365 caixa de correio correspondente para cada usuário. Se você habilitar o mapeamento automático do usuário e fornecer um mapeamento personalizado, para cada item de email, o conector procurará primeiro o arquivo de mapeamento personalizado. Se ele não encontrar um usuário Microsoft 365 que corresponda ao número móvel de um usuário, o conector usará a propriedade endereço de email do usuário do item de email. Se o conector não encontrar um usuário Microsoft 365 no arquivo de mapeamento personalizado ou na propriedade de endereço de *email* do usuário do item de email, o item não será importado.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar um conector

Algumas das etapas de implementação necessárias para arquivar Enterprise dados do Arquivo Mortor de Números são externos Microsoft 365 e devem ser concluídas antes que você possa criar o conector no centro de conformidade.

- Peça o Enterprise de Arquivo de Números [do TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) e obter uma conta de administração válida para sua organização. Você precisará entrar nessa conta quando criar o conector no centro de conformidade.

- Registre todos os usuários que exigem Enterprise número SMS/arquivamento de rede MMS na conta teleMessage. Ao registrar usuários, certifique-se de usar o mesmo endereço de email usado para sua conta Microsoft 365.

- Instale e ative o aplicativo Enterprise arquivo mortor de números do TeleMessage nos telefones celulares de seus funcionários.

- O usuário que cria um conector Enterprise arquivo mortor de números deve receber a função De exportação de importação de caixa de correio Exchange Online. Isso é necessário para adicionar conectores na página **Conectores** de dados no Microsoft 365 de conformidade. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função Exportar Importação de Importação de Caixa de Correio ao grupo de função Gerenciamento da Organização Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Exportar Importação de Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte as seções Criar grupos de [função](/Exchange/permissions-exo/role-groups#create-role-groups) ou [Modificar](/Exchange/permissions-exo/role-groups#modify-role-groups) grupos de função no artigo "Gerenciar grupos de funções em Exchange Online".

- Esse conector de dados está disponível em GCC ambientes na nuvem Microsoft 365 Us Government. Aplicativos e serviços de terceiros podem envolver o armazenamento, a transmissão e o processamento dos dados do cliente da sua organização em sistemas de terceiros que estão fora da infraestrutura do Microsoft 365 e, portanto, não são cobertos pelos compromissos de conformidade e proteção de dados do Microsoft 365. A Microsoft não faz nenhuma representação de que o uso desse produto para se conectar a aplicativos de terceiros implica que esses aplicativos de terceiros são compatíveis com FEDRAMP.

## <a name="create-an-enterprise-number-archiver-connector"></a>Criar um conector Enterprise de arquivo mortor de números

Depois de concluir os pré-requisitos descritos na seção anterior, você poderá criar um conector Enterprise Arquivo Mortor de Números no Microsoft 365 de conformidade. O conector usa as informações fornecidas para se conectar ao site do TeleMessage e transferir mensagens SMS, MMS e chamadas de voz para as caixas de correio de usuário correspondentes no Microsoft 365.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique em **Conectores de dados Enterprise** Arquivo \> **Mortor de Números.**

2. Na página **Enterprise descrição** do produto do Arquivador de Números, clique em **Adicionar conector**

3. Na página **Termos de serviço,** clique em **Aceitar**.

4. Na página **Logon para TeleMessage,** em Etapa 3, insira as informações necessárias nas caixas a seguir e clique em **Próximo**.

   - **Nome de usuário:** Seu nome de usuário teleMessage.

   - **Senha:** Sua senha teleMessage.

5. Depois que o conector for criado, você poderá fechar a janela pop-up e ir para a próxima página.

6. Na página **Mapeamento de** usuário, habilita o mapeamento automático do usuário. Para habilitar o mapeamento personalizado, carregue um arquivo CSV que contém as informações de mapeamento do usuário e clique em **Próximo**.

7. Revise suas configurações e clique em **Concluir** para criar o conector.

8. Vá até a guia Conectores na página **Conectores de** dados para ver o andamento do processo de importação do novo conector.

## <a name="known-issues"></a>Problemas conhecidos

- Neste momento, não há suporte para importação de anexos ou itens maiores que 10 MB. O suporte para itens maiores estará disponível posteriormente.