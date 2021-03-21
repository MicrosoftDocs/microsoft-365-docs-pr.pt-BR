---
title: Configurar um conector para arquivar dados do Arquivo Mortor de Números corporativos da TeleMessage
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
description: Os administradores podem configurar um conector para importar e arquivar dados SMS e MMS do Arquivo Mortor de Números Corporativos da TeleMessage. Isso permite que você arquive dados de fontes de dados de terceiros no Microsoft 365 para que você possa usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar os dados de terceiros da sua organização.
ms.openlocfilehash: 1322cafad94c8b2163c38e3c988feefc4ff1221a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921741"
---
# <a name="set-up-a-connector-to-archive-enterprise-number-data"></a>Configurar um conector para arquivar dados do Número da Empresa

Use um conector teleMessage no centro de conformidade do Microsoft 365 para importar e arquivar mensagens SMS (Serviço de Mensagens Curtas) e MMS (Serviço de Mensagens Multimídia), mensagens de chat, gravações de chamada de voz e logs de chamada de voz do Enterprise Number Archiver. Depois de configurar e configurar um conector, ele se conecta à conta teleMessage da sua organização uma vez por dia e importa os dados de comunicação móvel dos funcionários usando o Arquivo Mortor de Números corporativos teleMessage para caixas de correio no Microsoft 365.

Depois que os dados do conector de Arquivamento de Número empresarial da TeleMessage são armazenados em caixas de correio de usuário, você pode aplicar recursos de conformidade do Microsoft 365, como Retenção de Litígio, Pesquisa de Conteúdo, Arquivamento de In-Place, Auditoria, Conformidade de Comunicação e políticas de retenção do Microsoft 365 aos dados do Arquivo de Números corporativos. Por exemplo, você pode pesquisar o SMS, MMS e Chamada de Voz do Arquivo de Números corporativos da TeleMessage usando a Pesquisa de Conteúdo ou associar a caixa de correio que contém os dados do conector do Arquivo Mortor de Número da Empresa com um custodiante em um caso de Descoberta Avançada. O uso de um conector de Arquivamento de Números corporativos para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a manter-se em conformidade com políticas governamentais e regulatórias.

## <a name="overview-of-archiving-enterprise-number-data"></a>Visão geral dos dados do Número da Empresa de arquivamento

A visão geral a seguir explica o processo de uso de um conector para arquivar dados da Rede Empresarial no Microsoft 365.

![Fluxo de trabalho de arquivamento de Número da Empresa](../media/EnterpriseNumberConnectorWorkflow.png)

1. Sua organização trabalha com o TeleMessage para configurar um conector de Arquivamento de Números corporativos. Para obter mais detalhes, consulte [aqui](https://www.telemessage.com/office365-activation-for-enterprise-number-archiver/).

2. O conector de Arquivamento de Número da Empresa que você cria no centro de conformidade do Microsoft 365 conecta-se ao site do TeleMessage todos os dias e transfere as mensagens de email das 24 horas anteriores para uma área segura de Armazenamento do Azure no Microsoft Cloud.

3. O conector importa os itens de comunicação móvel para a caixa de correio de um usuário específico. Uma nova pasta chamada Enterprise Number Archiver é criada na caixa de correio do usuário específico e os itens são importados para ela. O conector faz o mapeamento usando o valor da *propriedade endereço email do* usuário. Cada mensagem de email contém essa propriedade, que é preenchida com o endereço de email de cada participante da mensagem de email. Além do mapeamento automático do usuário usando o valor da propriedade endereço *email* do usuário, você também pode definir um mapeamento personalizado carregando um arquivo de mapeamento CSV. Esse arquivo de mapeamento deve conter o Número móvel do usuário e o endereço de caixa de correio correspondente do Microsoft 365 para cada usuário. Se você habilitar o mapeamento automático do usuário e fornecer um mapeamento personalizado, para cada item de email, o conector procurará primeiro o arquivo de mapeamento personalizado. Se ele não encontrar um usuário válido do Microsoft 365 que corresponda ao número móvel de um usuário, o conector usará a propriedade endereço de email do usuário do item de email. Se o conector não encontrar um usuário válido do Microsoft 365 no arquivo de mapeamento personalizado ou na propriedade de endereço de *email* do usuário do item de email, o item não será importado.

## <a name="before-you-begin"></a>Antes de começar

Algumas das etapas de implementação necessárias para arquivar dados do Enterprise Number Archiver são externas ao Microsoft 365 e devem ser concluídas antes que você possa criar o conector no centro de conformidade.

- Peça o serviço De arquivamento de números corporativos [do TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) e obter uma conta de administração válida para sua organização. Você precisará entrar nessa conta quando criar o conector no centro de conformidade.

- Registre todos os usuários que exigem o arquivamento da Rede SMS/MMS do Número da Empresa na conta teleMessage. Ao registrar usuários, certifique-se de usar o mesmo endereço de email usado para sua conta do Microsoft 365.

- Instale e ative o aplicativo Arquivador de Números corporativos da TeleMessage nos telefones celulares de seus funcionários.

- O usuário que cria um conector de Arquivamento de Número da Empresa deve receber a função de Exportação de Importação de Caixa de Correio no Exchange Online. Isso é necessário para adicionar conectores na página **Conectores de** dados no centro de conformidade do Microsoft 365. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função Exportar Importação de Caixa de Correio ao grupo de função Gerenciamento da Organização no Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Exportar Importação de Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte as seções Criar grupos de [função](/Exchange/permissions-exo/role-groups#create-role-groups) ou [Modificar](/Exchange/permissions-exo/role-groups#modify-role-groups) grupos de função no artigo "Gerenciar grupos de função no Exchange Online".

## <a name="create-an-enterprise-number-archiver-connector"></a>Criar um conector de arquivamento de números corporativos

Depois de concluir os pré-requisitos descritos na seção anterior, você pode criar um conector de Arquivamento de Números corporativos no centro de conformidade do Microsoft 365. O conector usa as informações fornecidas para se conectar ao site teleMessage e transferir mensagens SMS, MMS e chamadas de voz para as caixas de correio de usuário correspondentes no Microsoft 365.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique em Conectores de dados Arquivo mortor de números  \> **corporativos.**

2. Na página **Descrição do produto do** Arquivo de Número da Empresa, clique em **Adicionar conector**

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