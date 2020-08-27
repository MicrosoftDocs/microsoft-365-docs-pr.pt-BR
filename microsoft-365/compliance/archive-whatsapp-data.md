---
title: Configurar um conector para arquivar dados de WhatsApp no Microsoft 365
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
ROBOTS: NOINDEX, NOFOLLOW
description: Os administradores podem configurar um conector de Telemensagem para importar e arquivar dados de WhatsApp no Microsoft 365. Isso permite que você arquive dados de fontes de dados de terceiros no Microsoft 365 para que possa usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar os dados de terceiros da sua organização.
ms.openlocfilehash: 73916cc760f2d5c08f226a5692ba89bc58777076
ms.sourcegitcommit: b144e8ba1ab0c40fa7e0e8e893b5cb44aa2d8243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2020
ms.locfileid: "47282689"
---
# <a name="set-up-a-connector-to-archive-whatsapp-data-preview"></a>Configurar um conector para arquivar dados de WhatsApp (visualização)

Use o conector de Telemensagem no centro de conformidade da Microsoft 365 para importar e arquivar chamadas, chats, anexos, arquivos e mensagens excluídas do WhatsApp. Depois de configurar e configurar um conector, ele se conecta à conta de Telemensagem de sua organização uma vez por dia e importa a comunicação móvel de funcionários usando o WhatsApp Phone Archiver ou telemessage WhatsApp Cloud Archiver para caixas de correio no Microsoft 365.

Depois que os dados do WhatsApp são armazenados nas caixas de correio do usuário, você pode aplicar recursos de conformidade do Microsoft 365, como retenção de litígio, pesquisa de conteúdo e políticas de retenção da Microsoft 365 a Verizon Data. Por exemplo, você pode pesquisar mensagens do WhatsApp usando a pesquisa de conteúdo ou associar a caixa de correio que contém as mensagens do WhatsApp a um funcionário em uma ocorrência de descoberta eletrônica avançada. O uso de um conector WhatsApp para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a se manter em conformidade com as políticas governamentais e regulamentares.

## <a name="overview-of-archiving-whatsapp-data"></a>Visão geral do arquivamento de dados do WhatsApp

A visão geral a seguir explica o processo de usar um conector para arquivar dados do WhatsApp no Microsoft 365.

![Fluxo de trabalho de arquivamento do WhatsApp](../media/WhatsAppConnectorWorkflow.png)

1. Sua organização funciona com telemessage para configurar um conector do Archiver do WhatsApp. Para obter mais informações, consulte [WhatsApp Archiver](https://www.telemessage.com/office365-activation-for-whatsapp-archiver).

2. Uma vez a cada 24 horas, os dados de WhatsApp da sua organização são copiados para o site de Telemensagem.

3. O conector WhatsApp que você cria no centro de conformidade da Microsoft 365 se conecta ao site de Telemensagem todos os dias e transfere os dados do WhatsApp das últimas 24 horas para um local seguro de armazenamento do Azure na nuvem da Microsoft. O conector também converte os dados de WhatsApp de conteúdo em um formato de mensagem de email.

4. O conector importa dados de WhatsApp para a caixa de correio de um usuário específico. Uma nova pasta chamada **WhatsApp Archiver** é criada na caixa de correio do usuário específico e os itens são importados para ela. O conector faz esse mapeamento usando o valor da propriedade de *endereço de email do usuário* . Cada mensagem de WhatsApp contém essa propriedade, que é preenchida com o endereço de email de cada participante da mensagem.

   Além do mapeamento automático de usuários usando o valor da propriedade de *endereço de email do usuário* , você também pode implementar o mapeamento personalizado carregando um arquivo de mapeamento CSV. Este arquivo de mapeamento contém o número de telefone celular e o endereço de email correspondente do Microsoft 365 para usuários em sua organização. Se você habilitar o mapeamento de usuário automático e o mapeamento personalizado, para cada item do WhatsApp, o conector examinará primeiro o arquivo de mapeamento personalizado. Se não encontrar um usuário válido do Microsoft 365 que corresponda ao número de telefone celular de um usuário, o conector usará os valores na propriedade de endereço de email do item que está tentando importar. Se o conector não localizar um usuário válido do Microsoft 365 no arquivo de mapeamento personalizado ou na propriedade de endereço de email do item WhatsApp, o item não será importado.

## <a name="before-you-begin"></a>Antes de começar

Muitas das etapas de implementação necessárias para arquivar dados de comunicação do WhatsApp são externas para o Microsoft 365 e devem ser concluídas para que você possa criar o conector no centro de conformidade.

- Solicite o [serviço Archiver do WhatsApp da telemessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) e obtenha uma conta de administração válida para sua organização. Você precisará entrar nessa conta quando criar o conector no centro de conformidade.

- Registre todos os usuários que exigem arquivamento do WhatsApp na conta de Telemensagem. Ao registrar usuários, certifique-se de usar o mesmo endereço de email usado para a conta do Microsoft 365.

- Instale o [aplicativo WhatsApp Phone Archiver de telefone](https://www.telemessage.com/mobile-archiver/whatsapp-phone-archiver-2/) para telefones celulares de seus funcionários e ative-o. Como alternativa, você pode instalar os aplicativos de negócios WhatsApp ou WhatsApp regulares nos telefones celulares de seus funcionários e ativar o WhatsApp Cloud Archiver Service examinando um código QR no site de Telemensagem. Para obter mais informações, consulte [WhatsApp Cloud archiverr](https://www.telemessage.com/mobile-archiver/whatsapp-archiver/whatsapp-cloud-archiver/).

- Sua organização deve dar o consentimento para permitir que o serviço de importação do Office 365 acesse dados de caixa de correio em sua organização. Você precisará fornecer esse consentimento ao criar o conector. Para concordar com essa solicitação, [acesse esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), entre com as credenciais de um administrador global do Office 365 e aceite a solicitação. Você precisa concluir esta etapa antes de poder criar com êxito o conector de rede Verizon.

- O usuário que cria um conector de rede Verizon deve ser atribuído à função de exportação de importação de caixa de correio no Exchange Online. Isso é necessário para adicionar conectores na página **conectores de dados** no centro de conformidade do Microsoft 365. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função de exportação de importação de caixa de correio ao grupo de funções Gerenciamento da organização no Exchange Online. Ou você pode criar um grupo de função, atribua a função de exportação de importação de caixa de correio e, em seguida, adicione os usuários apropriados como membros. Para obter mais informações, consulte as seções [criar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) ou [modificar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) no artigo "gerenciar grupos de função no Exchange Online".

## <a name="create-a-whatsapp-archiver-connector"></a>Criar um conector Archiver do WhatsApp

Depois de concluir os pré-requisitos descritos na seção anterior, você pode criar o conector WhatsApp no centro de conformidade do Microsoft 365. O conector usa as informações que você fornece para se conectar ao site de Telemensagem e transferir os dados do WhatsApp para as caixas de correio de usuário correspondentes no Microsoft 365.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique em **Data Connectors**  >  **WhatsApp Archiver**.

2. Na página descrição do produto **WhatsApp Archiver** , clique em **Adicionar conector**

3. Na página **termos de serviço** , clique em **aceitar**.

4. Na página **logon na Telemensagem** , em etapa 3, insira as informações necessárias nas caixas a seguir e clique em **Avançar**.

   - **Nome de usuário:** O nome de usuário de sua mensagem.

   - **Senha:** Sua senha de Telemensagem.

5. Depois que o conector é criado, você pode fechar a janela pop-up e ir para a próxima página.

6. Na página **mapeamento de usuário** , habilite mapeamento automático de usuário e clique em **Avançar**. Caso você precise de mapeamento personalizado, carregue um arquivo CSV e clique em **Avançar**.

7. Forneça o consentimento do administrador e clique em **Avançar**.

   Para fornecer o consentimento do administrador, você deve estar conectado com as credenciais de um administrador global do Office 365 e aceitar a solicitação de consentimento. Se você não estiver conectado como um administrador global, poderá ir para [esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) e entrar usando credenciais de administrador global para aceitar a solicitação.

8. Revise suas configurações e clique em **concluir** para criar o conector.

9. Vá até a guia conectores na página **conectores de dados** para ver o andamento do processo de importação para o novo conector.

## <a name="known-issues"></a>Problemas conhecidos

- O conector não importa nenhum item com mais de 10 MB.
