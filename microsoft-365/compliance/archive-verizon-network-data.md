---
title: Configurar um conector para arquivar dados da Rede Verizon no Microsoft 365
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
description: Os administradores podem configurar um conector teleMessage para importar e arquivar dados SMS e MMS da Rede Verizon no Microsoft 365. Isso permite que você arquive dados de fontes de dados de terceiros no Microsoft 365 para que você possa usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar os dados de terceiros da sua organização.
ms.openlocfilehash: d73b501fccac9f0f400a267a158379271f0f0d14
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924287"
---
# <a name="set-up-a-connector-to-archive-verizon-network-data"></a>Configurar um conector para arquivar dados da Rede Verizon

Use o conector teleMessage no centro de conformidade do Microsoft 365 para importar e arquivar dados do Serviço de Mensagens Curtas (SMS) e mms do Serviço de Mensagens Multimídia (MMS) da Rede Verizon. Depois de configurar e configurar um conector, ele se conecta à Rede Verizon da sua organização uma vez por dia e importa dados SMS e MMS para caixas de correio no Microsoft 365.

Depois que os dados do conector de Rede verizon são armazenados em caixas de correio de usuário, você pode aplicar recursos de conformidade do Microsoft 365, como Retenção de Litígio, Pesquisa de Conteúdo e políticas de retenção do Microsoft 365 aos dados do Verizon. Por exemplo, você pode pesquisar mensagens SMS e MMS da Verizon usando a Pesquisa de Conteúdo ou associar a caixa de correio que contém dados da Rede Verizon com um custodiante em um caso de Descoberta Avançada de Descoberta Eletrônico. O uso de um conector de Rede verizon para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a se manter em conformidade com políticas governamentais e regulatórias.

## <a name="overview-of-archiving-verizon-network-data"></a>Visão geral dos dados da Rede Verizon de arquivamento

A visão geral a seguir explica o processo de uso de um conector para arquivar dados da Rede Verizon no Microsoft 365.

![Fluxo de trabalho de arquivamento de rede verizon](../media/VerizonNetworkConnectorWorkflow.png)

1. Sua organização trabalha com TeleMessage e Verizon para configurar um conector de Rede verizon. Para obter mais informações, [consulte Verizon Network Archiver](https://www.telemessage.com/office365-activation-for-verizon-network-archiver/).

2. Uma vez a cada 24 horas, mensagens SMS e MMS da Rede Verizon da sua organização são copiadas para o site teleMessage.

3. O conector de Rede do Verizon que você cria no centro de conformidade do Microsoft 365 conecta-se ao site do TeleMessage todos os dias e transfere as mensagens SMS e MMS das 24 horas anteriores para um local seguro de Armazenamento do Azure no Microsoft Cloud. O conector também converte o conteúdo de mensagens SMS e MMS em um formato de mensagem de email.

4. O conector importa os itens de comunicação móvel para a caixa de correio de um usuário específico. Uma nova pasta chamada **Verizon SMS/MMS Network Archiver** é criada na caixa de correio do usuário específico e os itens são importados para ela. O conector faz esse mapeamento usando o valor da *propriedade endereço email do* usuário. Cada mensagem SMS e MMS contém essa propriedade, que é preenchida com o endereço de email de cada participante da mensagem.

   Além do mapeamento automático do usuário  usando o valor da propriedade endereço email do usuário, você também pode implementar o mapeamento personalizado carregando um arquivo de mapeamento CSV. Este arquivo de mapeamento contém o número de telefone celular e o endereço de email correspondente do Microsoft 365 para usuários em sua organização. Se você habilitar o mapeamento automático do usuário e o mapeamento personalizado, para cada item da Verizon, o conector primeiro olhará para o arquivo de mapeamento personalizado. Se ele não encontrar um usuário válido do Microsoft 365 que corresponda ao número de telefone celular de um usuário, o conector usará os valores na propriedade endereço de email do item que está tentando importar. Se o conector não encontrar um usuário válido do Microsoft 365 no arquivo de mapeamento personalizado ou na propriedade endereço de email do item Verizon, o item não será importado.

## <a name="before-you-begin"></a>Antes de começar

Algumas das etapas de implementação necessárias para arquivar dados da Rede Verizon são externas ao Microsoft 365 e devem ser concluídas antes de você poder criar um conector no centro de conformidade.

- Order the [Verizon Network Archiver service from TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) and get a valid administration account for your organization. Você precisará entrar nessa conta quando criar o conector no centro de conformidade.

- Obtenha sua conta da Rede verizon e detalhes de contato de cobrança para que você possa preencher os formulários de integração do TeleMessage e solicitar o serviço de arquivamento de mensagens da Verizon.

- Registre todos os usuários que exigem arquivamento SMS e MMS da Verizon na conta teleMessage. Ao registrar usuários, certifique-se de usar o mesmo endereço de email usado para sua conta do Microsoft 365.

- Seus funcionários devem ter telefones móveis corporativos e corporativos na rede móvel Verizon. As mensagens de arquivamento no Microsoft 365 não estão disponíveis para dispositivos BYOD ou de propriedade do funcionário.

- O usuário que cria um conector de Rede verizon deve receber a função de Exportação de Importação de Caixa de Correio no Exchange Online. Isso é necessário para adicionar conectores na página **Conectores de** dados no centro de conformidade do Microsoft 365. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função Exportar Importação de Caixa de Correio ao grupo de função Gerenciamento da Organização no Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Exportar Importação de Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte as seções Criar grupos de [função](/Exchange/permissions-exo/role-groups#create-role-groups) ou [Modificar](/Exchange/permissions-exo/role-groups#modify-role-groups) grupos de função no artigo "Gerenciar grupos de função no Exchange Online".

## <a name="create-a-verizon-network-connector"></a>Criar um conector de rede verizon

Depois de concluir os pré-requisitos descritos na seção anterior, você pode criar o conector de Rede verizon no centro de conformidade do Microsoft 365. O conector usa as informações fornecidas para se conectar ao site teleMessage e transferir mensagens SMS e MMS para as caixas de correio de usuário correspondentes no Microsoft 365.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique em **Conectores de dados** Rede  >  **Verizon**.

2. Na página **Descrição do produto da Rede Verizon,** clique em **Adicionar conector**

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