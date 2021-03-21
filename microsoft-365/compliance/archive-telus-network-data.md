---
title: Configurar um conector para arquivar dados da Rede TELUS no Microsoft 365
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
description: Os administradores podem configurar um conector teleMessage para importar e arquivar dados SMS da Rede TELUS no Microsoft 365. Isso permite que você arquive dados de fontes de dados de terceiros no Microsoft 365 para que você possa usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar os dados de terceiros da sua organização.
ms.openlocfilehash: 543ef817b7a9a2b9bbd2449c12460ca557907728
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925015"
---
# <a name="set-up-a-connector-to-archive-telus-network-data"></a>Configurar um conector para arquivar dados da Rede TELUS

Use o conector teleMessage no centro de conformidade do Microsoft 365 para importar e arquivar dados do Serviço de Mensagens Curtas (SMS) da Rede TELUS da sua organização. Depois de configurar e configurar um conector, ele se conecta à Rede TELUS da sua organização uma vez por dia e importa dados SMS para caixas de correio no Microsoft 365.

Depois que as mensagens SMS são armazenadas em caixas de correio de usuário, você pode aplicar recursos de conformidade do Microsoft 365, como Retenção de Litígio, Pesquisa de Conteúdo e políticas de retenção do Microsoft 365 aos dados do TELUS. Por exemplo, você pode pesquisar mensagens SMS TELUS usando a Pesquisa de Conteúdo ou associar a caixa de correio que contém os dados TELUS a um custodiante em um caso de Descoberta Avançada. Usar um conector de Rede TELUS para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a permanecer em conformidade com políticas governamentais e regulatórias.

## <a name="overview-of-archiving-telus-network-data"></a>Visão geral do arquivamento de dados de Rede TELUS

A visão geral a seguir explica o processo de uso de um conector para arquivar dados da Rede TELUS no Microsoft 365.

![Fluxo de trabalho de arquivamento de rede TELUS](../media/TelusNetworkConnectorWorkflow.png)

1. Sua organização trabalha com TeleMessage e TELUS para configurar um conector de Rede TELUS. Para obter mais informações, consulte [Telus Network Archiver](https://www.telemessage.com/office365-activation-for-telus-network-archiver/).

2. Uma vez a cada 24 horas, as mensagens SMS da Rede TELUS da sua organização são copiadas para o site teleMessage.

3. O conector de Rede TELUS criado no centro de conformidade do Microsoft 365 conecta-se ao site do TeleMessage todos os dias e transfere as mensagens SMS das 24 horas anteriores para um local seguro de Armazenamento do Azure no Microsoft Cloud. O conector também converte o conteúdo das mensagens SMS em um formato de mensagem de email.

4. O conector importa os itens de comunicação móvel para a caixa de correio de um usuário específico. Uma nova pasta chamada **Telus SMS Network Archiver** é criada na caixa de correio do usuário específico e os itens são importados para ele. O conector faz o mapeamento usando o valor da *propriedade endereço email do* usuário. Cada mensagem SMS contém essa propriedade, que é preenchida com o endereço de email de cada participante da mensagem SMS.

   Além do mapeamento automático do usuário  usando o valor da propriedade endereço email do usuário, você também pode implementar o mapeamento personalizado carregando um arquivo de mapeamento CSV. Este arquivo de mapeamento contém o número de telefone celular e o endereço de email correspondente do Microsoft 365 para usuários em sua organização. Se você habilitar o mapeamento automático do usuário e o mapeamento personalizado, para cada item TELUS, o conector primeiro olhará para o arquivo de mapeamento personalizado. Se ele não encontrar um usuário válido do Microsoft 365 que corresponda ao número de telefone celular de um usuário, o conector usará os valores na propriedade endereço de email do item que está tentando importar. Se o conector não encontrar um usuário válido do Microsoft 365 no arquivo de mapeamento personalizado ou na propriedade endereço de email do item TELUS, o item não será importado.

## <a name="before-you-begin"></a>Antes de começar

Algumas das etapas de implementação necessárias para arquivar dados da Rede TELUS são externas ao Microsoft 365 e devem ser concluídas antes que você possa criar um conector no centro de conformidade.

- Peça o [serviço de Arquivamento de Rede TELUS do TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) e obter uma conta de administração válida para sua organização. Você precisará entrar nessa conta quando criar o conector no centro de conformidade.

- Obtenha sua conta de Rede TELUS e detalhes de contato de cobrança para que você possa preencher os formulários de integração do TeleMessage e solicitar o serviço de arquivamento de mensagens do TELUS.

- Registre todos os usuários que exigem o arquivamento da Rede SMS TELUS na conta teleMessage. Ao registrar usuários, certifique-se de usar o mesmo endereço de email usado para sua conta do Microsoft 365.

- Seus funcionários devem ter telefones móveis corporativos e corporativos na rede móvelTELUS. As mensagens de arquivamento no Microsoft 365 não estão disponíveis para dispositivos BYOD ou de propriedade do funcionário.

- O usuário que cria um conector de Rede TELUS deve receber a função de Exportação de Importação de Caixa de Correio no Exchange Online. Isso é necessário para adicionar conectores na página **Conectores de** dados no centro de conformidade do Microsoft 365. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função Exportar Importação de Caixa de Correio ao grupo de função Gerenciamento da Organização no Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Exportar Importação de Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte as seções Criar grupos de [função](/Exchange/permissions-exo/role-groups#create-role-groups) ou [Modificar](/Exchange/permissions-exo/role-groups#modify-role-groups) grupos de função no artigo "Gerenciar grupos de função no Exchange Online".

## <a name="create-a-telus-network-connector"></a>Criar um conector de Rede TELUS

Depois de concluir os pré-requisitos descritos na seção anterior, você pode criar o conector de Rede TELUS no centro de conformidade do Microsoft 365. O conector usa as informações fornecidas para se conectar ao site do TeleMessage e transferir mensagens SMS para as caixas de correio de usuário correspondentes no Microsoft 365.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique em **Conectores de dados rede**  >  **TELUS**.

2. Na página Descrição do produto da **Rede TELUS,** clique em **Adicionar conector**

3. Na página **Termos de serviço,** clique em **Aceitar**.

4. Na página **Logon para TeleMessage,** em Etapa 3, insira as informações necessárias nas caixas a seguir e clique em **Próximo**.

   - **Nome de usuário:** Seu nome de usuário teleMessage.

   - **Senha:** Sua senha teleMessage.

5. Depois que o conector for criado, você poderá fechar a janela pop-up e ir para a próxima página.

6. Na página **Mapeamento de** usuário, habilita o mapeamento automático do usuário e clique em **Próximo**. Caso precise de mapeamento personalizado, carregue um arquivo CSV e clique em **Próximo**.

7. Revise suas configurações e clique em **Concluir** para criar o conector.

8. Vá até a guia Conectores na página **Conectores de** dados para ver o andamento do processo de importação do novo conector.

## <a name="known-issues"></a>Problemas conhecidos

- Neste momento, não há suporte para importação de anexos ou itens maiores que 10 MB. O suporte para itens maiores estará disponível posteriormente.