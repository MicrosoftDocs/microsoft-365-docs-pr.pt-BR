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
description: Os administradores podem configurar um conector teleMessage para importar e arquivar dados do WhatsApp no Microsoft 365. Isso permite arquivar dados de fontes de dados de terceiros no Microsoft 365 para que você possa usar recursos de conformidade como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar dados de terceiros da sua organização.
ms.openlocfilehash: 573316f262295cce417876ef77510da14b877c67
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620177"
---
# <a name="set-up-a-connector-to-archive-whatsapp-data"></a>Configurar um conector para arquivar dados do WhatsApp

Use o conector TeleMessage no centro de conformidade do Microsoft 365 para importar e arquivar chamadas, chats, anexos, arquivos e mensagens excluídas do WhatsApp. Depois de configurar um conector, ele se conecta à conta teleMessage da sua organização uma vez por dia e importa a comunicação móvel de funcionários usando o Arquivador de Telefonia do WhatsApp da TeleMessage ou o TeleMessage WhatsApp Cloud Archiver para caixas de correio no Microsoft 365.

Depois que os dados do WhatsApp são armazenados nas caixas de correio do usuário, você pode aplicar recursos de conformidade do Microsoft 365, como Retenção de Litígio, Pesquisa de Conteúdo e políticas de retenção do Microsoft 365 aos dados do WhatsApp. Por exemplo, você pode pesquisar mensagens do WhatsApp usando a Pesquisa de Conteúdo ou associar a caixa de correio que contém mensagens do WhatsApp a um custodiante em um caso de Descoberta Eletrônico Avançada. Usar um conector do WhatsApp para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a manter a conformidade com políticas governamentais e regulatórias.

## <a name="overview-of-archiving-whatsapp-data"></a>Visão geral dos dados do WhatsApp de arquivamento

A visão geral a seguir explica o processo de uso de um conector para arquivar dados do WhatsApp no Microsoft 365.

![Fluxo de trabalho de arquivamento do WhatsApp](../media/WhatsAppConnectorWorkflow.png)

1. Sua organização trabalha com a TeleMessage para configurar um conector do WhatsApp Archiver. Para obter mais informações, consulte [WhatsApp Archiver](https://www.telemessage.com/office365-activation-for-whatsapp-archiver).

2. Uma vez a cada 24 horas, os dados do WhatsApp da sua organização são copiados para o site da TeleMessage.

3. O conector do WhatsApp criado no centro de conformidade do Microsoft 365 conecta-se ao site da TeleMessage todos os dias e transfere dados do WhatsApp das 24 horas anteriores para um local seguro de Armazenamento do Azure no Microsoft Cloud. O conector também converte os dados do WhatsApp de conteúdo em um formato de mensagem de email.

4. O conector importa dados do WhatsApp para a caixa de correio de um usuário específico. Uma nova pasta chamada **WhatsApp Archiver** é criada na caixa de correio do usuário específico e os itens são importados para ela. O conector faz esse mapeamento usando o valor da propriedade *de endereço de email do* usuário. Cada mensagem do WhatsApp contém essa propriedade, que é preenchida com o endereço de email de cada participante da mensagem.

   Além do mapeamento automático de usuário usando o valor da propriedade de endereço de *Email* do Usuário, você também pode implementar o mapeamento personalizado carregando um arquivo de mapeamento CSV. Esse arquivo de mapeamento contém o número de telefone celular e o endereço de email do Microsoft 365 correspondente para usuários em sua organização. Se você habilitar o mapeamento automático de usuário e o mapeamento personalizado, para cada item do WhatsApp, o conector primeiro analisa o arquivo de mapeamento personalizado. Se não encontrar um usuário válido do Microsoft 365 que corresponda ao número de telefone celular de um usuário, o conector usará os valores na propriedade de endereço de email do item que está tentando importar. Se o conector não encontrar um usuário válido do Microsoft 365 no arquivo de mapeamento personalizado ou na propriedade de endereço de email do item WhatsApp, o item não será importado.

## <a name="before-you-begin"></a>Antes de começar

Algumas das etapas de implementação necessárias para arquivar dados de comunicação do WhatsApp são externas ao Microsoft 365 e devem ser concluídas antes que você possa criar o conector no centro de conformidade.

- Solicitar o [serviço WhatsApp Archiver da TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) e obter uma conta de administração válida para sua organização. Você precisará entrar nessa conta ao criar o conector no centro de conformidade.

- Registre todos os usuários que exigem arquivamento do WhatsApp na conta teleMessage. Ao registrar usuários, certifique-se de usar o mesmo endereço de email usado para a conta do Microsoft 365.

- Instale o aplicativo TeleMessage [WhatsApp Phone Archiver](https://www.telemessage.com/mobile-archiver/whatsapp-phone-archiver-2/) nos telefones celulares dos funcionários e ative-o. Como alternativa, você pode instalar os aplicativos WhatsApp ou WhatsApp Business regulares nos telefones celulares de seus funcionários e ativar o serviço WhatsApp Cloud Archiver, digitalizando um código QR no site da TeleMessage. Para obter mais informações, consulte [WhatsApp Cloud Archiver](https://www.telemessage.com/mobile-archiver/whatsapp-archiver/whatsapp-cloud-archiver/).

- O usuário que cria um conector de Rede Verizon deve receber a função Importar Exportar Caixa de Correio no Exchange Online. Isso é necessário para adicionar conectores na página Conectores **de dados** no centro de conformidade do Microsoft 365. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função Importar Exportar Caixa de Correio ao grupo de função Gerenciamento da Organização no Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Importar Exportar Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) as [seções](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) Criar grupos de função ou Modificar grupos de função no artigo "Gerenciar grupos de função no Exchange Online".

## <a name="create-a-whatsapp-archiver-connector"></a>Criar um conector do WhatsApp Archiver

Depois de concluir os pré-requisitos descritos na seção anterior, você pode criar o conector do WhatsApp no centro de conformidade do Microsoft 365. O conector usa as informações que você fornece para se conectar ao site da TeleMessage e transferir os dados do WhatsApp para as caixas de correio do usuário correspondentes no Microsoft 365.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique em **Conectores de dados**  >  **whatsApp Archiver**.

2. Na página de **descrição do produto WhatsApp Archiver,** clique em **Adicionar conector**

3. Na página **Termos de serviço,** clique em **Aceitar**.

4. Na página **Login para TeleMessage,** em Etapa 3, insira as informações necessárias nas caixas a seguir e clique em **Próximo.**

   - **Nome de usuário:** Seu nome de usuário da TeleMessage.

   - **Senha:** Sua senha da TeleMessage.

5. Depois que o conector é criado, você pode fechar a janela pop-up e ir para a próxima página.

6. Na página **Mapeamento de usuários,** habilita o mapeamento automático de usuário e clique em **Próximo.** Caso precise de mapeamento personalizado, carregue um arquivo CSV e clique em **Próximo.**

7. Revise suas configurações e clique em **Concluir** para criar o conector.

8. Vá até a guia Conectores na **página Conectores** de dados para ver o progresso do processo de importação do novo conector.

## <a name="known-issues"></a>Problemas conhecidos

- No momento, não há suporte para a importação de anexos ou itens maiores do que 10 MB. O suporte para itens maiores estará disponível posteriormente.
