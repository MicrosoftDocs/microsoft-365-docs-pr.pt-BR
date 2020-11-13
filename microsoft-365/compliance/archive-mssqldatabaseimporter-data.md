---
title: Configurar um conector para arquivar dados do banco de dados MS SQL
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
description: Os administradores podem configurar um conector para importar e arquivar dados do banco de dados MS SQL. Esse conector permite que você arquive dados de fontes de dados de terceiros no Microsoft 365. Após o arquivamento desses dados, você pode usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar dados de terceiros.
ms.openlocfilehash: 6e3a4a79845539745bec233acbfaeff22f4ad4a9
ms.sourcegitcommit: f07442d077eb4357fa5d99d051b035705eb30efa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/12/2020
ms.locfileid: "49002727"
---
# <a name="set-up-a-connector-to-archive-data-from-ms-sql-database-preview"></a>Configurar um conector para arquivar dados do banco de dados MS SQL (versão prévia)

Use um conector Globanet no centro de conformidade da Microsoft 365 para importar e arquivar dados do banco de dados MS SQL para caixas de correio do usuário na sua organização do Microsoft 365. O Globanet fornece um conector do Microsoft SQL Database Importer configurado para capturar itens de um banco de dados usando um arquivo de configuração XML e importar esses itens para o Microsoft 365. O conector converte o conteúdo do banco de dados MS SQL para um formato de mensagem de email e, em seguida, importa esses itens para caixas de correio de usuário no Microsoft 365.

Após o conteúdo do banco de dados MS SQL armazenado nas caixas de correio do usuário, você pode aplicar recursos de conformidade da Microsoft 365, como retenção de litígio, descoberta eletrônica, políticas de retenção e rótulos de retenção. O uso de um conector de banco de dados MS SQL para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a se manter em conformidade com as políticas governamentais e regulamentares.

## <a name="overview-of-archiving-the-ms-sql-data"></a>Visão geral do arquivamento de dados MS SQL

A visão geral a seguir explica o processo de usar um conector para arquivar dados MS SQL no Microsoft 365.

![Fluxo de trabalho de arquivamento para dados MS SQL](../media/MSSQLDatabaseConnectorWorkflow.png)

1. Sua organização funciona com um provedor de banco de dados MS SQL para configurar e configurar um site de banco de dados MS SQL.

2. Uma vez a cada 24 horas, os itens de banco de dados MS SQL são copiados para o site do Globanet Merge1. O conector também converte esse conteúdo em um formato de mensagem de email.

3. O conector de importador de banco de dados MS SQL que você cria no centro de conformidade da Microsoft 365, conecta-se ao site do Globanet Merge1 todos os dias e transfere as mensagens para um local seguro de armazenamento do Azure na nuvem da Microsoft.

4. O conector importa os itens de banco de dados do MS SQL convertidos para as caixas de correio de usuários específicos usando o valor da propriedade *email* do mapeamento de usuário automático, conforme descrito na [etapa 3](#step-3-map-users-and-complete-the-connector-setup). Uma subpasta na pasta caixa de entrada chamada **MS SQL Database importator** é criada nas caixas de correio do usuário e os itens são importados para essa pasta. O conector determina qual caixa de correio para a qual importar itens usando o valor da propriedade *email* . Cada item do banco de dados MS SQL contém essa propriedade, que é preenchida com o endereço de email de cada participante do item.

## <a name="before-you-begin"></a>Antes de começar

- Crie uma conta do Merge1 do Globanet para conectores da Microsoft. Para criar uma conta, entre em contato com o [suporte ao cliente Globanet](https://globanet.com/contact-us/). Você precisa entrar nessa conta ao criar o conector na etapa 1.

- O usuário que cria o conector de importador de banco de dados MS SQL na etapa 1 (e conclui-lo na etapa 3) deve ser atribuído à função de exportação de importação de caixa de correio no Exchange Online. Essa função é necessária para adicionar conectores na página conectores de dados no centro de conformidade da Microsoft 365. Por padrão, essa função não é atribuída a nenhum grupo de função no Exchange Online. Você pode adicionar a função de exportação de importação de caixa de correio ao grupo de funções Gerenciamento da organização no Exchange Online. Ou você pode criar um grupo de função, atribua a função de exportação de importação de caixa de correio e, em seguida, adicione os usuários apropriados como membros. Para obter mais informações, consulte as seções [criar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) ou [modificar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) no artigo "gerenciar grupos de função no Exchange Online".

## <a name="step-1-set-up-the-ms-sql-database-importer-connector"></a>Etapa 1: configurar o conector do Microsoft SQL Database Importer

A primeira etapa é acessar a página **conectores de dados** no centro de conformidade do Microsoft365 e criar um conector para o banco de dados MS SQL.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique em **conectores de dados**  >  **MS SQL Database Importer**.

2. Na página descrição do produto **importador de banco de dados MS SQL** , clique em **Adicionar novo conector**.

3. Na página **termos de serviço** , clique em **aceitar**.

4. Insira um nome exclusivo que identifique o conector e clique em **Avançar**.

5. Entre em sua conta do Merge1 para configurar o conector.

## <a name="step-2-configure-the-ms-sql-database-importer-connector-on-the-globanet-merge1-site"></a>Etapa 2: configurar o conector do Microsoft SQL Database Importer no site do Globanet Merge1

A segunda etapa é configurar o conector do Microsoft SQL Database Importer no site do Merge1. Para obter informações sobre como configurar o importador de banco de dados MS SQL, consulte [Merge1 de terceiros](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20MS%20SQL%20Database%20Importer%20User%20Guide%20.pdf).

Depois de clicar em **salvar & concluir** , a página **mapeamento de usuário** no assistente de conector no centro de conformidade da Microsoft 365 é exibida.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Etapa 3: mapear usuários e concluir a configuração do conector

Para mapear usuários e concluir a configuração do conector, siga estas etapas:

1. Na página **mapear usuários do banco de dados do MS SQL para usuários do Microsoft 365** , habilite o mapeamento automático do usuário. Os itens do banco de dados MS SQL incluem uma propriedade chamada *email* , que contém endereços de email para usuários em sua organização. Se o conector puder associar esse endereço a um usuário do Microsoft 365, os itens serão importados para a caixa de correio desse usuário.

2. Na página **consentimento do administrador** , clique no botão **fornecer consentimento** . Você será redirecionado para o site da Microsoft. Clique em **aceitar** para fornecer o consentimento.

   Sua organização deve dar o consentimento para permitir que o serviço de importação do Office 365 acesse dados de caixa de correio em sua organização. Para fornecer o consentimento do administrador, você deve estar conectado com as credenciais de um administrador global do Microsoft 365 e aceitar a solicitação de consentimento. Se você não estiver conectado como um administrador global, poderá ir para [esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) e entrar usando as credenciais de administrador global para aceitar a solicitação.

3. Clique em **Avançar** , revise suas configurações e vá para a página **conectores de dados** para ver o andamento do processo de importação para o novo conector.

## <a name="step-4-monitor-the-ms-sql-database-importer-connector"></a>Etapa 4: monitorar o conector do Microsoft SQL Database Importer

Depois de criar o conector de importador de banco de dados MS SQL, você pode visualizar o status do conector no centro de conformidade da Microsoft 365.

1. Vá para <https://compliance.microsoft.com/> e clique em **conectores de dados** no painel de navegação esquerdo.

2. Clique na guia **conectores** e selecione o conector de **importador** de **banco de dados MS SQL** para exibir a página de submenu, que contém as propriedades e informações sobre o conector.

3. Em **status do conector com origem** , clique no link **baixar log** para abrir (ou salvar) o log de status do conector. Esse log contém dados que foram importados para a nuvem da Microsoft.

## <a name="known-issues"></a>Problemas conhecidos

- No momento, não há suporte para importar anexos ou itens com mais de 10 MB. O suporte para itens maiores estará disponível em uma data posterior.
