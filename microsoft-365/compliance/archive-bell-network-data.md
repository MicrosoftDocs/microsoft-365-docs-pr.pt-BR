---
title: Configurar um conector para arquivar dados de rede SMS/MMS da Sino
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
description: Os administradores podem configurar um conector teleMessage para importar e arquivar dados SMS e MMS da Rede Sino. Isso permite arquivar dados de fontes de dados de terceiros no Microsoft 365 para que você possa usar recursos de conformidade como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar dados de terceiros da sua organização.
ms.openlocfilehash: d615488e5f6441efd828a6b91c187e7a8f5ca2c8
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620472"
---
# <a name="set-up-a-connector-to-archive-bell-network-data"></a>Configurar um conector para arquivar dados da Rede Sino

Use um conector teleMessage no centro de conformidade do Microsoft 365 para importar e arquivar mensagens SMS e MMS da Rede Sino. Depois de configurar um conector, ele se conecta à Rede Sinos da sua organização uma vez por dia e importa mensagens SMS e MMS para caixas de correio no Microsoft 365.

Depois que as mensagens SMS e MMS são armazenadas nas caixas de correio do usuário, você pode aplicar recursos de conformidade do Microsoft 365, como Retenção de Litígio, Pesquisa de Conteúdo e políticas de retenção do Microsoft 365 aos dados da Rede Sino. Por exemplo, você pode pesquisar SMS da Rede Sino/MMS usando a Pesquisa de Conteúdo ou associar a caixa de correio que contém os dados do conector da Rede Sino com um custodiante em um caso de Descoberta Eletrônico Avançada. Usar um conector da Rede Sinos para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a manter a conformidade com políticas governamentais e regulatórias.

## <a name="overview-of-archiving-bell-network-data"></a>Visão geral dos dados de arquivamento da Rede Sino

A visão geral a seguir explica o processo de uso de um conector para arquivar dados da Rede Sinos no Microsoft 365.

![Fluxo de trabalho de arquivamento da Rede sino](../media/BellNetworkConnectorWorkflow.png)

1. Sua organização trabalha com TeleMessage e Sino para configurar um conector da Rede Sinos. Para obter mais informações, consulte [o Arquivo Morto da Rede Sino.](https://www.telemessage.com/office365-activation-for-bell-network-archiver)

2. Uma vez a cada 24 horas, as mensagens SMS e MMS da Rede Sinos da sua organização são copiadas para o site teleMessage.

3. O conector da Rede Sinos que você cria no centro de conformidade do Microsoft 365 conecta-se ao site da TeleMessage todos os dias e transfere as mensagens SMS e MMS das últimas 24 horas para um local seguro de Armazenamento do Azure no Microsoft Cloud. O conector também converte o conteúdo de mensagens SMS e MMS em um formato de mensagem de email.

4. O conector importa os itens de comunicação móvel para a caixa de correio de usuários específicos. Uma nova pasta chamada Sms da **Sino/Arquivo** Morto de Rede MMS é criada na caixa de correio de um usuário específico e os itens são importados para ela. O conector faz esse mapeamento usando o valor da *propriedade de endereço de email do* usuário. Cada mensagem SMS e MMS contém essa propriedade, que é preenchida com o endereço de email de cada participante da mensagem.

   Além do mapeamento automático de usuário usando o valor da propriedade de endereço de *Email* do Usuário, você também pode definir um mapeamento personalizado carregando um arquivo de mapeamento CSV. Esse arquivo de mapeamento contém o número de telefone celular e o endereço de email do Microsoft 365 correspondente para usuários em sua organização. Se você habilitar o mapeamento automático de usuário e o mapeamento personalizado, para cada item da Rede sino, o conector primeiro analisa o arquivo de mapeamento personalizado. Se não encontrar um usuário válido do Microsoft 365 que corresponda ao número de telefone celular de um usuário, o conector usará os valores na propriedade de endereço de email do item que está tentando importar. Se o conector não encontrar um usuário válido do Microsoft 365 no arquivo de mapeamento personalizado ou na propriedade de endereço de email do item Da Rede Sino, o item não será importado.

## <a name="before-you-begin"></a>Antes de começar

Algumas das etapas de implementação necessárias para arquivar dados da Rede de Sinos são externas ao Microsoft 365 e devem ser concluídas antes que você possa criar um conector no centro de conformidade.

- Solicitar o serviço Arquivo Mortor de Rede [Sino da TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) e obter uma conta de administração válida para sua organização. Você precisará entrar nessa conta ao criar o conector no centro de conformidade.

- Obtenha sua conta da Rede de Sinos e detalhes do contato de cobrança para que você possa preencher os formulários de integração da TeleMessage e solicitar o serviço de arquivamento de mensagens da Sino.

- Registre todos os usuários que exigem o arquivamento da Rede Sms da Sino/MMS na conta TeleMessage. Ao registrar usuários, certifique-se de usar o mesmo endereço de email usado para a conta do Microsoft 365.

- Seus funcionários devem ter telefones celulares de propriedade corporativa e de propriedade corporativa na rede móvel Sino. O arquivamento de mensagens no Microsoft 365 não está disponível para dispositivos de propriedade do funcionário ou "Traga seus próprios dispositivos (BYOD).

- O usuário que cria um conector de Rede Sinos deve receber a função Importar Exportar Caixa de Correio no Exchange Online. Isso é necessário para adicionar conectores na página Conectores **de dados** no centro de conformidade do Microsoft 365. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função Importar Exportar Caixa de Correio ao grupo de função Gerenciamento da Organização no Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Importar Exportar Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) as [seções](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) Criar grupos de função ou Modificar grupos de função no artigo "Gerenciar grupos de função no Exchange Online".

## <a name="create-a-bell-network-connector"></a>Criar um conector de Rede sino

A última etapa é criar um conector da Rede Sinos no centro de conformidade do Microsoft 365. O conector usa as informações que você fornece para se conectar ao site teleMessage e transferir mensagens SMS/MMS para as caixas de correio do usuário correspondentes no Microsoft 365.

1. Vá até [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique em **Conectores de dados** Sms de  >  **Sino/Arquivo Morto de Rede MMS.**

2. Na página **de descrição do produto Da** Rede Sino, clique em Adicionar **conector**

3. Na página **Termos de serviço,** clique em **Aceitar**.

4. Na página **Login para TeleMessage,** em Etapa 3, insira as informações necessárias nas caixas a seguir e clique em **Próximo.**

   - **Nome de usuário:** Seu nome de usuário da TeleMessage.

   - **Senha:** Sua senha da TeleMessage.

5. Depois que o conector é criado, você pode fechar a janela pop-up e ir para a próxima página.

6. Na página **Mapeamento de usuários,** habilita o mapeamento automático de usuários. Para habilitar o mapeamento personalizado, carregue um arquivo CSV que contenha as informações de mapeamento do usuário e clique em **Próximo.**

7. Revise suas configurações e clique em **Concluir** para criar o conector.

8. Vá para a **guia Conectores** na página **Conectores** de dados no centro de conformidade para ver o progresso do processo de importação do novo conector.

## <a name="known-issues"></a>Problemas conhecidos

- No momento, não há suporte para a importação de anexos ou itens maiores do que 10 MB. O suporte para itens maiores estará disponível posteriormente.
