---
title: Configurar um conector para arquivar dados móveis do Android
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
description: Os administradores podem configurar um conector teleMessage para importar e arquivar SMS, MMS e chamadas de voz de telefones celulares Android. Isso permite arquivar dados de fontes de dados de terceiros no Microsoft 365 para que você possa usar recursos de conformidade como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar dados de terceiros da sua organização.
ms.openlocfilehash: 5837d5247ca7ac82389d2781110883058ca98bb7
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620526"
---
# <a name="set-up-a-connector-to-archive-android-mobile-data"></a>Configurar um conector para arquivar dados móveis do Android

Use um conector teleMessage no centro de conformidade do Microsoft 365 para importar e arquivar SMS, MMS, chamadas de voz e logs de chamadas de celulares Android. Depois de configurar um conector, ele se conecta à conta teleMessage da sua organização uma vez por dia e importa a comunicação móvel de funcionários usando o Arquivo Morto Android teleMessage para caixas de correio no Microsoft 365.

Depois que os dados de telefones celulares Android são armazenados em caixas de correio do usuário, você pode aplicar recursos de conformidade do Microsoft 365, como Retenção de Litígio, Pesquisa de Conteúdo e políticas de retenção do Microsoft 365 aos dados do Arquivador do Android. Por exemplo, você pode pesquisar a comunicação móvel do Android Archiver usando a Pesquisa de Conteúdo ou associar a caixa de correio que contém os dados do conector do Arquivo Morto Android com um custodiante em um caso de Descoberta Eletrônico Avançada. Usar um conector do Android Archiver para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a manter a conformidade com políticas governamentais e regulatórias.

## <a name="overview-of-archiving-android-mobile-data"></a>Visão geral do arquivamento de dados móveis do Android

A visão geral a seguir explica o processo de uso de um conector para arquivar dados móveis do Android no Microsoft 365.

![Fluxo de trabalho do conector do Arquivar Android](../media/AndroidArchiverConnectorWorkflow.png)

1. Sua organização trabalha com a TeleMessage para configurar um conector do Arquivo Morto Android. Para obter mais informações, consulte [Android Archiver](https://www.telemessage.com/office365-activation-for-android-archiver/).

2. A cada 24 horas, SMS, MMS, chamadas de voz e logs de chamadas de telefones celulares Android da sua organização são copiados para o site TeleMessage.

3. O conector do Android Archiver criado no centro de conformidade do Microsoft 365 conecta-se ao site da TeleMessage todos os dias e transfere os dados do Android das 24 horas anteriores para um local seguro de Armazenamento do Azure no Microsoft Cloud. O conector também converte os dados do Android em um formato de mensagem de email.

4. O conector importa os itens de comunicação móvel para a caixa de correio de um usuário específico. Uma nova pasta chamada Arquivo Morto Android é criada na caixa de correio do usuário específico e os itens são importados para ela. O conector faz o mapeamento usando o valor da *propriedade de endereço de email do* usuário. Cada mensagem de email contém essa propriedade, que é preenchida com o endereço de email de cada participante da mensagem de email. Além do mapeamento automático de usuário usando o valor da propriedade de endereço de *Email* do Usuário, você também pode definir um mapeamento personalizado carregando um arquivo de mapeamento CSV. Esse arquivo de mapeamento deve conter o número de celular do usuário e o endereço de caixa de correio correspondente do Microsoft 365 para cada usuário. Se você habilitar o mapeamento automático de usuários e fornecer um mapeamento personalizado, para cada item de email, o conector primeiro procurará o arquivo de mapeamento personalizado. Se não encontrar um usuário válido do Microsoft 365 que corresponda ao número de celular de um usuário, o conector usará a propriedade de endereço de email do usuário do item de email. Se o conector não encontrar um usuário válido do Microsoft 365 no arquivo de mapeamento personalizado ou na propriedade de endereço de *email* do usuário do item de email, o item não será importado.

## <a name="before-you-begin"></a>Antes de começar

Algumas das etapas de implementação necessárias para arquivar dados de comunicação do Android são externas ao Microsoft 365 e devem ser concluídas antes que você possa criar o conector no centro de conformidade.

- Order the [Android Archiver service from TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) and get a valid administration account for your organization. Você precisará entrar nessa conta ao criar o conector.

- Registre todos os usuários que exigem o serviço De arquivamento do Android na conta teleMessage. Ao registrar usuários, certifique-se de usar o mesmo endereço de email usado para a conta do Microsoft 365.

- Instale e ative o aplicativo TeleMessage Android Archiver nos telefones celulares dos funcionários.

- O usuário que cria um conector do Arquivo Morto Android deve receber a função Importar Exportar Caixa de Correio no Exchange Online. Isso é necessário para adicionar conectores na página Conectores **de dados** no centro de conformidade do Microsoft 365. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função Importar Exportar Caixa de Correio ao grupo de função Gerenciamento da Organização no Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Importar Exportar Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) as [seções](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) Criar grupos de função ou Modificar grupos de função no artigo "Gerenciar grupos de função no Exchange Online".

## <a name="create-an-android-archiver-connector"></a>Criar um conector de arquivamento do Android

A última etapa é criar um conector do Arquivo Morto Android no centro de conformidade do Microsoft 365. O conector usa as informações que você fornece para se conectar ao site teleMessage e transferir a comunicação do Android para as caixas de correio do usuário correspondentes no Microsoft 365.

1. Vá até [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique em **Conectores de dados do** Android  >  **Archiver.**

2. Na página de **descrição do produto Android Archiver,** clique **em Adicionar conector.**

3. Na página **Termos de serviço,** clique em **Aceitar**.

4. Na página **Login para TeleMessage,** em Etapa 3, insira as informações necessárias nas caixas a seguir e clique em **Próximo.**

   - **Nome de usuário:** Seu nome de usuário da TeleMessage.

   - **Senha:** Sua senha da TeleMessage.

5. Depois que o conector for criado, feche a janela pop-up e clique em **Próximo.**

6. Na página **mapeamento de usuários,** habilita o mapeamento automático de usuário e clique em **Próximo.** Caso precise de mapeamento personalizado, carregue um arquivo CSV e clique em **Próximo.**

7. Revise suas configurações e clique em **Concluir** para criar o conector.

8. Vá até a guia Conectores na **página Conectores** de dados para ver o progresso do processo de importação do novo conector.

## <a name="known-issues"></a>Problemas conhecidos

- No momento, não há suporte para a importação de anexos ou itens maiores do que 10 MB. O suporte para itens maiores estará disponível posteriormente.
