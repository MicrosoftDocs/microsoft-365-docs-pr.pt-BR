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
description: Os administradores podem configurar um conector teleMessage para importar e arquivar sms, MMS e chamadas de voz de celulares Android. Isso permite que você arquive dados de fontes de dados de terceiros no Microsoft 365 para que você possa usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar os dados de terceiros da sua organização.
ms.openlocfilehash: d0c0043f598d81ae314d39e839111fd0aaad1150
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919979"
---
# <a name="set-up-a-connector-to-archive-android-mobile-data"></a>Configurar um conector para arquivar dados móveis do Android

Use um conector teleMessage no centro de conformidade do Microsoft 365 para importar e arquivar SMS, MMS, chamadas de voz e logs de chamadas de celulares Android. Depois de configurar e configurar um conector, ele se conecta à conta teleMessage da sua organização uma vez por dia e importa a comunicação móvel de funcionários usando o Arquivo Mortor Android teleMessage para caixas de correio no Microsoft 365.

Depois que os dados de telefones celulares Android são armazenados em caixas de correio de usuário, você pode aplicar recursos de conformidade do Microsoft 365, como Retenção de Litígio, Pesquisa de Conteúdo e políticas de retenção do Microsoft 365 aos dados do Android Archiver. Por exemplo, você pode pesquisar a comunicação móvel do Android Archiver usando a Pesquisa de Conteúdo ou associar a caixa de correio que contém os dados do conector do Android Archiver com um custodiante em um caso de Descoberta Avançada de Descoberta Eletrônico. Usar um conector do Android Archiver para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a se manter em conformidade com políticas governamentais e regulatórias.

## <a name="overview-of-archiving-android-mobile-data"></a>Visão geral do arquivamento de dados móveis do Android

A visão geral a seguir explica o processo de uso de um conector para arquivar dados móveis do Android no Microsoft 365.

![Fluxo de trabalho do conector do Android Archiver](../media/AndroidArchiverConnectorWorkflow.png)

1. Sua organização trabalha com TeleMessage para configurar um conector de Arquivamento Android. Para obter mais informações, consulte [Android Archiver](https://www.telemessage.com/office365-activation-for-android-archiver/).

2. Uma vez a cada 24 horas, SMS, MMS, chamadas de voz e logs de chamadas dos celulares Android da sua organização são copiados para o site do TeleMessage.

3. O conector do Android Archiver criado no centro de conformidade do Microsoft 365 conecta-se ao site do TeleMessage todos os dias e transfere os dados do Android das 24 horas anteriores para um local seguro de Armazenamento do Azure no Microsoft Cloud. O conector também converte os dados do Android em um formato de mensagem de email.

4. O conector importa os itens de comunicação móvel para a caixa de correio de um usuário específico. Uma nova pasta chamada Android Archiver é criada na caixa de correio do usuário específico e os itens são importados para ela. O conector faz o mapeamento usando o valor da *propriedade endereço email do* usuário. Cada mensagem de email contém essa propriedade, que é preenchida com o endereço de email de cada participante da mensagem de email. Além do mapeamento automático do usuário usando o valor da propriedade endereço *email* do usuário, você também pode definir um mapeamento personalizado carregando um arquivo de mapeamento CSV. Esse arquivo de mapeamento deve conter o Número móvel do usuário e o endereço de caixa de correio correspondente do Microsoft 365 para cada usuário. Se você habilitar o mapeamento automático do usuário e fornecer um mapeamento personalizado, para cada item de email, o conector procurará primeiro o arquivo de mapeamento personalizado. Se ele não encontrar um usuário válido do Microsoft 365 que corresponda ao número móvel de um usuário, o conector usará a propriedade endereço de email do usuário do item de email. Se o conector não encontrar um usuário válido do Microsoft 365 no arquivo de mapeamento personalizado ou na propriedade de endereço de *email* do usuário do item de email, o item não será importado.

## <a name="before-you-begin"></a>Antes de começar

Algumas das etapas de implementação necessárias para arquivar dados de comunicação do Android são externas ao Microsoft 365 e devem ser concluídas antes que você possa criar o conector no centro de conformidade.

- Peça o [serviço de Arquivamento Android do TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) e obter uma conta de administração válida para sua organização. Você precisará entrar nessa conta quando criar o conector.

- Registre todos os usuários que exigem o serviço de Arquivamento Android na conta teleMessage. Ao registrar usuários, certifique-se de usar o mesmo endereço de email usado para sua conta do Microsoft 365.

- Instale e ative o aplicativo Arquivar Android teleMessage nos telefones celulares de seus funcionários.

- O usuário que cria um conector de Arquivamento android deve receber a função de Exportação de Importação de Caixa de Correio no Exchange Online. Isso é necessário para adicionar conectores na página **Conectores de** dados no centro de conformidade do Microsoft 365. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função Exportar Importação de Caixa de Correio ao grupo de função Gerenciamento da Organização no Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Exportar Importação de Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte as seções Criar grupos de [função](/Exchange/permissions-exo/role-groups#create-role-groups) ou [Modificar](/Exchange/permissions-exo/role-groups#modify-role-groups) grupos de função no artigo "Gerenciar grupos de função no Exchange Online".

## <a name="create-an-android-archiver-connector"></a>Criar um conector de arquivamento do Android

A última etapa é criar um conector de Arquivamento android no centro de conformidade do Microsoft 365. O conector usa as informações fornecidas para se conectar ao site teleMessage e transferir a comunicação do Android para as caixas de correio de usuário correspondentes no Microsoft 365.

1. Vá até [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique em **Conectores de dados** do Android  >  **Archiver**.

2. Na página Descrição do produto do **Android Archiver,** clique **em Adicionar conector**.

3. Na página **Termos de serviço,** clique em **Aceitar**.

4. Na página **Logon para TeleMessage,** em Etapa 3, insira as informações necessárias nas caixas a seguir e clique em **Próximo**.

   - **Nome de usuário:** Seu nome de usuário teleMessage.

   - **Senha:** Sua senha teleMessage.

5. Depois que o conector for criado, feche a janela pop-up e clique em **Próximo**.

6. Na página **Mapeamento de** usuário, habilita o mapeamento automático do usuário e clique em **Próximo**. Caso precise de mapeamento personalizado, carregue um arquivo CSV e clique em **Próximo**.

7. Revise suas configurações e clique em **Concluir** para criar o conector.

8. Vá até a guia Conectores na página **Conectores de** dados para ver o andamento do processo de importação do novo conector.

## <a name="known-issues"></a>Problemas conhecidos

- Neste momento, não há suporte para importação de anexos ou itens maiores que 10 MB. O suporte para itens maiores estará disponível posteriormente.