---
title: Configurar um conector para arquivar dados do WhatsApp no Microsoft 365
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
description: Os administradores podem configurar um conector teleMessage para importar e arquivar dados do WhatsApp no Microsoft 365. Isso permite que você arquive dados de fontes de dados de terceiros no Microsoft 365 para que você possa usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar os dados de terceiros da sua organização.
ms.openlocfilehash: 446845b95df7cf460eeb554d72c076b6221f7edc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923389"
---
# <a name="set-up-a-connector-to-archive-whatsapp-data"></a>Configurar um conector para arquivar dados do WhatsApp

Use o conector teleMessage no centro de conformidade do Microsoft 365 para importar e arquivar chamadas, chats, anexos, arquivos e mensagens excluídas do WhatsApp. Depois de configurar e configurar um conector, ele se conecta à conta teleMessage da sua organização uma vez por dia e importa a comunicação móvel de funcionários usando o Arquivo Mortor de Telefone do WhatsApp teleMessage ou o Arquivo Mortor de Nuvem do WhatsApp para caixas de correio no Microsoft 365.

Depois que os dados do WhatsApp são armazenados em caixas de correio de usuário, você pode aplicar recursos de conformidade do Microsoft 365, como Retenção de Litígio, Pesquisa de Conteúdo e políticas de retenção do Microsoft 365 aos dados do WhatsApp. Por exemplo, você pode pesquisar mensagens do WhatsApp usando a Pesquisa de Conteúdo ou associar a caixa de correio que contém mensagens do WhatsApp a um custodiante em um caso de Descoberta Avançada. O uso de um conector do WhatsApp para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a se manter em conformidade com políticas governamentais e regulatórias.

## <a name="overview-of-archiving-whatsapp-data"></a>Visão geral do arquivamento de dados do WhatsApp

A visão geral a seguir explica o processo de uso de um conector para arquivar dados do WhatsApp no Microsoft 365.

![Fluxo de trabalho de arquivamento do WhatsApp](../media/WhatsAppConnectorWorkflow.png)

1. Sua organização trabalha com TeleMessage para configurar um conector de Arquivamento do WhatsApp. Para obter mais informações, consulte [WhatsApp Archiver](https://www.telemessage.com/office365-activation-for-whatsapp-archiver).

2. Uma vez a cada 24 horas, os dados do WhatsApp da sua organização são copiados para o site teleMessage.

3. O conector do WhatsApp criado no centro de conformidade do Microsoft 365 conecta-se ao site de TeleMessage todos os dias e transfere dados do WhatsApp das 24 horas anteriores para um local seguro de Armazenamento do Azure no Microsoft Cloud. O conector também converte os dados de conteúdo do WhatsApp em um formato de mensagem de email.

4. O conector importa dados do WhatsApp para a caixa de correio de um usuário específico. Uma nova pasta chamada **WhatsApp Archiver** é criada na caixa de correio do usuário específico e os itens são importados para ela. O conector faz esse mapeamento usando o valor da *propriedade endereço email do* usuário. Cada mensagem do WhatsApp contém essa propriedade, que é preenchida com o endereço de email de cada participante da mensagem.

   Além do mapeamento automático do usuário  usando o valor da propriedade endereço email do usuário, você também pode implementar o mapeamento personalizado carregando um arquivo de mapeamento CSV. Este arquivo de mapeamento contém o número de telefone celular e o endereço de email correspondente do Microsoft 365 para usuários em sua organização. Se você habilitar o mapeamento automático do usuário e o mapeamento personalizado, para cada item do WhatsApp, o conector primeiro olhará para o arquivo de mapeamento personalizado. Se ele não encontrar um usuário válido do Microsoft 365 que corresponda ao número de telefone celular de um usuário, o conector usará os valores na propriedade endereço de email do item que está tentando importar. Se o conector não encontrar um usuário válido do Microsoft 365 no arquivo de mapeamento personalizado ou na propriedade endereço de email do item WhatsApp, o item não será importado.

## <a name="before-you-begin"></a>Antes de começar

Algumas das etapas de implementação necessárias para arquivar dados de comunicação do WhatsApp são externas ao Microsoft 365 e devem ser concluídas antes que você possa criar o conector no centro de conformidade.

- Order the [WhatsApp Archiver service from TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) and get a valid administration account for your organization. Você precisará entrar nessa conta quando criar o conector no centro de conformidade.

- Registre todos os usuários que exigem arquivamento do WhatsApp na conta teleMessage. Ao registrar usuários, certifique-se de usar o mesmo endereço de email usado para sua conta do Microsoft 365.

- Instale o aplicativo Desactivador de [Telefone do WhatsApp teleMessage](https://www.telemessage.com/mobile-archiver/whatsapp-phone-archiver-2/) nos telefones celulares de seus funcionários e ative-o. Como alternativa, você pode instalar os aplicativos de WhatsApp ou WhatsApp Business regulares nos telefones celulares de seus funcionários e ativar o serviço WhatsApp Cloud Archiver, digitalizando um código QR no site do TeleMessage. Para obter mais informações, consulte [WhatsApp Cloud Archiver](https://www.telemessage.com/mobile-archiver/whatsapp-archiver/whatsapp-cloud-archiver/).

- O usuário que cria um conector de Rede verizon deve receber a função de Exportação de Importação de Caixa de Correio no Exchange Online. Isso é necessário para adicionar conectores na página **Conectores de** dados no centro de conformidade do Microsoft 365. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função Exportar Importação de Caixa de Correio ao grupo de função Gerenciamento da Organização no Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Exportar Importação de Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte as seções Criar grupos de [função](/Exchange/permissions-exo/role-groups#create-role-groups) ou [Modificar](/Exchange/permissions-exo/role-groups#modify-role-groups) grupos de função no artigo "Gerenciar grupos de função no Exchange Online".

## <a name="create-a-whatsapp-archiver-connector"></a>Criar um conector de arquivamento do WhatsApp

Depois de concluir os pré-requisitos descritos na seção anterior, você pode criar o conector do WhatsApp no centro de conformidade do Microsoft 365. O conector usa as informações fornecidas para se conectar ao site do TeleMessage e transferir os dados do WhatsApp para as caixas de correio de usuário correspondentes no Microsoft 365.

1. Vá até [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique em **Conectores de dados** do  >  **WhatsApp Archiver**.

2. Na página Descrição do produto do **WhatsApp Archiver,** clique em **Adicionar conector**

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