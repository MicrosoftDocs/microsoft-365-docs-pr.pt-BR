---
title: Configurar um conector para arquivar dados de Salesforce Archive no Microsoft 365
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
description: Os administradores podem configurar um conector para importar e arquivar dados de Salesforce Archive da Globalnet para o Microsoft 365. Esse conector permite arquivar dados de fontes de dados de terceiros no Microsoft 365. Depois de arquivar esses dados, você pode usar recursos de conformidade como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar dados de terceiros.
ms.openlocfilehash: 518eb38756d86812a8b3d41e4bc2cd46d5a23386
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740308"
---
# <a name="set-up-a-connector-to-archive-salesforce-chatter-data"></a>Configurar um conector para arquivar dados de Salesforce Archive

Use um conector Globalnet no centro de conformidade do Microsoft 365 para importar e arquivar dados da plataforma Salesforce Platform para as caixas de correio do usuário em sua organização do Microsoft 365. A Globalnet fornece um conector [Salesforce Connector](http://globanet.com/chatter/) que captura itens da fonte de dados de terceiros e importa esses itens para o Microsoft 365. O conector converte o conteúdo como chats, anexos e postagens da Salesforce Connector em um formato de mensagem de email e importa esses itens para a caixa de correio do usuário no Microsoft 365.

Depois que os dados da Salesforce Litigation são armazenados nas caixas de correio do usuário, você pode aplicar recursos de conformidade do Microsoft 365, como Retenção de Litígio, Descoberta Eletrônico, políticas de retenção e rótulos de retenção. O uso de um conector salesforce Connector para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a manter a conformidade com políticas governamentais e regulatórias.

## <a name="overview-of-archiving-salesforce-chatter-data"></a>Visão geral do arquivamento de dados de Salesforce Archforce

A visão geral a seguir explica o processo de uso de um conector para arquivar os dados de Salesforce Archive no Microsoft 365.

![Fluxo de trabalho de arquivamento para dados de Salesforce Archiving](../media/SalesforceChatterConnectorWorkflow.png)

1. Sua organização trabalha com Salesforce Chatter para configurar e configurar um site salesforce Também funciona.

2. Uma vez a cada 24 horas, os itens de Salesforce Copied são copiados para o site Globalnet Merge1. O conector também salesforce items to an email message format.

3. O conector Salesforce Connector que você cria no centro de conformidade do Microsoft 365, conecta-se ao site Globalnet Merge1 todos os dias e transfere o conteúdo da Empresa para um local seguro de Armazenamento do Azure na nuvem da Microsoft.

4. O conector importa os itens convertidos para as caixas de correio de usuários específicos usando o valor da propriedade *Email* do mapeamento automático de usuário, conforme descrito na [Etapa 3.](#step-3-map-users-and-complete-the-connector-setup) Uma subpasta na pasta Caixa de Entrada chamada **Salesforce Também** é criada nas caixas de correio do usuário, e os itens são importados para essa pasta. O conector determina para qual caixa de correio os itens serão importados usando o valor da *propriedade Email.* Cada item Demão contém essa propriedade, que é preenchida com o endereço de email de todos os participantes do item.

## <a name="before-you-begin"></a>Antes de começar

- Crie uma conta Merge1 para conectores da Microsoft. Para criar uma conta, entre em contato com o Suporte [ao Cliente Globalnet.](https://globanet.com/contact-us/) Você precisa entrar nessa conta ao criar o conector na Etapa 1.

- Crie um aplicativo salesforce e adquira um token em [https://salesforce.com](https://salesforce.com) . Você precisará entrar na conta da Salesforce como administrador e obter um token pessoal de usuário para importar dados. Além disso, os gatilhos precisam ser publicados no site Desconversar para capturar atualizações, exclusões e edições. Esses gatilhos criarão uma postagem em um canal e Merge1 capturará as informações do canal. Para obter instruções passo a passo sobre como criar o aplicativo e adquirir o token, consulte [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20SalesForce%20Chatter%20User%20Guide%20.pdf).

- O usuário que cria o conector Salesforce Connector na Etapa 1 (e o conclui na Etapa 3) deve ser atribuído à função Importar Exportar Caixa de Correio no Exchange Online. Essa função é necessária para adicionar conectores na página Conectores **de dados** no centro de conformidade do Microsoft 365. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função Importar Exportar Caixa de Correio ao grupo de função Gerenciamento da Organização no Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Importar Exportar Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) as [seções](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) Criar grupos de função ou Modificar grupos de função no artigo "Gerenciar grupos de função no Exchange Online".

## <a name="step-1-set-up-the-salesforce-chatter-connector"></a>Etapa 1: Configurar o conector Salesforce Connector

A primeira etapa é  acessar a página Conectores de Dados no centro de conformidade do Microsoft 365 e criar um conector para os dados de Partida.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique em **Conectores de dados**  >  **Salesforce Connector**.

2. Na página de descrição do produto **Salesforce Connector,** clique **em Adicionar conector.**

3. Na página **Termos de serviço,** clique em **Aceitar**.

4. Insira um nome exclusivo que identifique o conector e clique em **Próximo.**

5. Entre em sua conta Merge1 para configurar o conector.

## <a name="step-2-configure-the-salesforce-chatter-on-the-globanet-merge1-site"></a>Etapa 2: Configurar o Salesforce Merge no site Globalnet Merge1

A segunda etapa é configurar o conector Salesforce Connector no site Globalnet Merge1. Para obter informações sobre como configurar o conector Salesforce Connector, consulte [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20SalesForce%20Chatter%20User%20Guide%20.pdf).

Depois que você clicar em  **Salvar & Concluir,** a página de mapeamento do usuário no assistente de conector no centro de conformidade do Microsoft 365 será exibida.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Etapa 3: Mapear usuários e concluir a configuração do conector

Para mapear usuários e concluir a configuração do conector no centro de conformidade do Microsoft 365, siga estas etapas:

1. Na página Mapear usuários do Salesforce Users para usuários do **Microsoft 365,** habilita o mapeamento automático de usuários. Os itens salesforce Descritivos incluem uma propriedade chamada *Email*, que contém endereços de email para usuários em sua organização. Se o conector puder associar esse endereço a um usuário do Microsoft 365, os itens serão importados para a caixa de correio desse usuário.

2. clique **em Avançar,** revise suas configurações  e vá para a página Conectores de dados para ver o progresso do processo de importação do novo conector.

## <a name="step-4-monitor-the-salesforce-chatter-connector"></a>Etapa 4: Monitorar o conector salesforce Connector

Depois de criar o conector Salesforce Connector, você pode exibir o status do conector no centro de conformidade do Microsoft 365.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique **em Conectores de dados** na barra de entrada esquerda.

2. clique na **guia Conectores** e clique no conector **Salesforce Connector** para exibir a página do flyout, que contém as propriedades e informações sobre o conector.

3. Em **Status do Conector com origem,** clique no link Baixar **log** para abrir (ou salvar) o log de status do conector. Esse log contém dados que foram importados para a nuvem da Microsoft.

## <a name="known-issues"></a>Problemas conhecidos

- No momento, não há suporte para a importação de anexos ou itens maiores do que 10 MB. O suporte para itens maiores estará disponível posteriormente.
