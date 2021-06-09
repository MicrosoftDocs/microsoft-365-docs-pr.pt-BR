---
title: Configurar um conector para arquivar o Local de Trabalho a partir de dados do Facebook Microsoft 365
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
description: Os administradores podem configurar um conector para importar e arquivar dados do Workplace do Facebook, que é arquivado no site Merge1 da Veritas, para Microsoft 365. Configurar um conector exige que você trabalhe com a Veritas Esse conector permite arquivar dados de fontes de dados de terceiros no Microsoft 365 para que você possa usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar dados de terceiros da sua organização.
ms.openlocfilehash: 25221b1d71fe106f0f6dcf9c629414aeb0de8709
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163820"
---
# <a name="set-up-a-connector-to-archive-workplace-from-facebook-data"></a>Configurar um conector para arquivar o local de trabalho a partir de dados do Facebook

Use um conector Veritas no centro de conformidade Microsoft 365 para importar e arquivar dados do Workplace do Facebook para as caixas de correio do usuário em sua Microsoft 365 organização. A Veritas fornece um workplace do conector do [Facebook](https://globanet.com/workplace/) configurado para capturar itens da fonte de dados de terceiros (regularmente) e importar esses itens para Microsoft 365. O conector converte o conteúdo como chats, anexos, postagens e vídeos do Workplace em um formato de mensagem de email e importa esses itens para caixas de correio de usuário em Microsoft 365.

Depois que os dados de local de trabalho são armazenados em caixas de correio de usuário, você pode aplicar Microsoft 365 de conformidade, como Retenção de Litígio, Descoberta Eletrônico, políticas de retenção e rótulos de retenção e conformidade de comunicação. Usar o Workplace from Facebook connector to import and archive data in Microsoft 365 can help your organization stay compliance with government and regulatory policies.

## <a name="overview-of-archiving-workplace-from-facebook-data"></a>Visão geral do arquivamento do Local de Trabalho a partir de dados do Facebook

A visão geral a seguir explica o processo de uso de um conector para arquivar dados de local de trabalho em Microsoft 365.

![Fluxo de trabalho de arquivamento para o Local de Trabalho a partir de dados do Facebook](../media/WorkplaceConnectorWorkflow.png)

1. Sua organização trabalha com o Workplace a partir do Facebook para configurar e configurar um site do Workplace.

2. Uma vez a cada 24 horas, os itens do Workplace são copiados para o site Veritas Merge1. O conector também converte o conteúdo desses itens em um formato de mensagem de email.

3. O workplace from Facebook connector that you create in the Microsoft 365 compliance center, connects to the Veritas Merge1 every day, and transfers the Workplace items to a secure Azure Armazenamento location in the Microsoft cloud.

4. O conector importa os itens convertidos para as caixas de correio de usuários específicos usando o valor da propriedade *Email* do mapeamento automático do usuário, conforme descrito na Etapa 3. Uma subpasta na pasta Caixa de Entrada chamada **Workplace from Facebook** é criada e os itens workplace são importados para essa pasta. O conector faz isso usando o valor da *propriedade Email.* Cada item workplace contém essa propriedade, que é preenchida com o endereço de email de cada participante de chat ou postagem.

## <a name="before-you-begin"></a>Antes de começar

- Crie uma conta Veritas Merge1 para conectores da Microsoft. Para criar essa conta, entre em contato com [o Suporte ao Cliente veritas.](https://globanet.com/ms-connectors-contact) Você entrará nessa conta quando criar o conector na Etapa 1.

- Crie uma integração personalizada para recuperar dados do Workplace por meio de APIs para fins https://my.workplace.com/work/admin/apps/ de conformidade e Descoberta.

   Ao criar a integração, a plataforma Workplace gera um conjunto de credenciais exclusivas usadas para gerar tokens usados para autenticação. Esses tokens são usados no Assistente de configuração do Conector do Facebook no Workplace na Etapa 2. Para obter instruções passo a passo sobre como criar os aplicativos, consulte [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf).

- O usuário que cria o Workplace a partir do conector do Facebook na Etapa 1 (e o conclui na Etapa 3) deve ser atribuído à função de Exportação de Importação de Caixa de Correio no Exchange Online. Essa função é necessária para adicionar conectores na página **Conectores** de dados no Microsoft 365 de conformidade. Por padrão, essa função não é atribuída a um grupo de funções no Exchange Online. Você pode adicionar a função Exportar Importação de Importação de Caixa de Correio ao grupo de função Gerenciamento da Organização Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Exportar Importação de Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte as seções Criar grupos de [função](/Exchange/permissions-exo/role-groups#create-role-groups) ou [Modificar](/Exchange/permissions-exo/role-groups#modify-role-groups) grupos de função no artigo "Gerenciar grupos de funções em Exchange Online".

## <a name="step-1-set-up-the-workplace-from-facebook-connector"></a>Etapa 1: Configurar o Local de Trabalho a partir do conector do Facebook

A primeira etapa é acessar a página **Conectores** de Dados no centro de conformidade Microsoft 365 e criar um conector para dados do local de trabalho.

1. Vá até [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique em **Conectores de** dados  >  **Local de trabalho do Facebook**.

2. Na página **Local de Trabalho a partir da descrição** do produto do Facebook, clique em Adicionar **conector**.

3. Na página **Termos de serviço,** clique em **Aceitar**.

4. Insira um nome exclusivo que identifique o conector e clique em **Próximo**.

5. Entre na sua conta Merge1 para configurar o conector.

## <a name="step-2-configure-the-workplace-from-facebook-connector-on-the-veritas-merge1-site"></a>Etapa 2: Configurar o Local de Trabalho a partir do conector do Facebook no site Veritas Merge1

A segunda etapa é configurar o Workplace a partir do conector do Facebook no site Merge1. Para obter informações sobre como configurar o Workplace a partir do conector do Facebook, consulte [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf).

Depois de clicar em Salvar &  **Concluir**, a página de mapeamento do usuário no assistente de conector no Microsoft 365 de conformidade será exibida.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Etapa 3: mapear usuários e concluir a configuração do conector

Para mapear usuários e concluir a instalação do conector no centro de conformidade Microsoft 365, siga estas etapas:

1. Na página **Mapear usuários externos para Microsoft 365 usuários,** habilita o mapeamento automático do usuário. Os itens workplace incluem uma propriedade chamada *Email* que contém endereços de email para usuários em sua organização. Se o conector puder associar esse endereço a um Microsoft 365 usuário, os itens serão importados para a caixa de correio desse usuário.

2. Clique **em Avançar**, revise suas configurações e vá para a página Conectores de dados para ver o andamento do processo de importação do novo conector. 

## <a name="step-4-monitor-the-workplace-from-facebook-connector"></a>Etapa 4: Monitorar o Local de Trabalho a partir do conector do Facebook

Depois de criar o Workplace a partir do conector do Facebook, você poderá exibir o status do conector no centro Microsoft 365 conformidade.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique **em Conectores de dados** na nav esquerda.

2. Clique na **guia Conectores** e selecione o local de trabalho no **conector do Facebook** para exibir a página de sobrevoo. Esta página contém as propriedades e informações sobre o conector.

3. Em **Status do conector com origem**, clique no link Baixar **log** para abrir (ou salvar) o log de status do conector. Esse log contém informações sobre os dados que foram importados para a nuvem da Microsoft.

## <a name="known-issues"></a>Problemas conhecidos

- Neste momento, não há suporte para importação de anexos ou itens maiores que 10 MB. O suporte para itens maiores estará disponível posteriormente.