---
title: Adicionar responsáveis a uma ocorrência de descoberta eletrônica avançada
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Saiba como usar a ferramenta de gerenciamento de responsáveis interna na descoberta eletrônica avançada para coordenar seus fluxos de trabalho e identificar fontes de dados relevantes em um caso.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9468fb889e9115b3652d1dba8a6c6632bb367fe3
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740338"
---
# <a name="add-custodians-to-an-advanced-ediscovery-case"></a>Adicionar responsáveis a uma ocorrência de descoberta eletrônica avançada

Use a ferramenta interna de gerenciamento de responsáveis em descoberta eletrônica avançada para coordenar seus fluxos de trabalho em torno do gerenciamento de responsáveis e pela identificação de fontes de dados relevantes, custodial, associadas a um caso. Quando você adiciona um profissional, o sistema pode identificar e colocar automaticamente uma retenção em sua caixa de correio do Exchange e na conta do OneDrive for Business. Durante o processo de descoberta de sua investigação, você também pode identificar outras fontes de dados (como caixas de correio, sites ou equipes) que um acessado ou contribuíram. Nessa situação, você pode usar a ferramenta de gerenciamento de responsáveis para associar essas fontes de dados a um determinado funcionário. Depois de adicionar os responsáveis a um caso e associar outra fonte de dados a eles, você pode preservar rapidamente os dados e Pesquisar os dados do custodial.

Você pode adicionar e gerenciar os responsáveis em casos de descoberta eletrônica avançada em quatro etapas:

1. Identificar os responsáveis.

2. Escolha os locais de dados dos responsáveis.

3. Definir configurações de retenção.

4. Revise os responsáveis e conclua o processo.

   [![Guia fontes na caixa ](../media/AeD-Sources-Tab.png) de descoberta eletrônica avançada](../media/AeD-Sources-Tab.png#lightbox)

## <a name="make-sure-you-have-the-necessary-permissions"></a>Verifique se você tem as permissões necessárias

Para adicionar os responsáveis a um caso, você deve ser membro do grupo de função Gerenciador de descoberta eletrônica. Isso fornece as permissões necessárias para adicionar os responsáveis a um caso e colocar uma retenção nas fontes de dados do custodial. Para obter mais informações, confira [Atribuir permissões de descoberta eletrônica](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions).

## <a name="step-1-identify-custodians"></a>Etapa 1: identificar os responsáveis

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e entre com uma conta de usuário que tenha recebido as permissões de descoberta eletrônica apropriadas.

2. No painel de navegação esquerdo do centro de conformidade da Microsoft 365, clique em **Mostrar tudo** e, em seguida, clique em **descoberta eletrônica > avançado**.

3. Na página **descoberta eletrônica avançada** , clique na guia **ocorrências** e, em seguida, selecione o caso para o qual você deseja adicionar os responsáveis.

4. Clique na guia **fontes de dados** e, em seguida, clique em **Adicionar fonte de dados**  >  **Adicionar novos responsáveis**.

5. Adicione um ou mais usuários em sua organização como responsáveis pelo caso digitando a primeira parte do nome ou alias de uma pessoa. Depois de encontrar a pessoa correta, selecione seu nome para adicioná-la à lista.

## <a name="step-2-choose-custodian-data-locations"></a>Etapa 2: escolher locais de dados de responsáveis

Após selecionar os responsáveis, o sistema tentará automaticamente identificar e verificar esses usuários e suas fontes de dados. Após adicionar os responsáveis à lista, a ferramenta inclui automaticamente a caixa de correio principal e a conta do OneDrive para cada um dos responsáveis. Você pode optar por não incluir essas fontes de dados ao adicionar os responsáveis à ocorrência.

Além da conta de caixa de correio e do OneDrive de um funcionário, você também pode associar outros locais de dados a um funcionário, como o site do SharePoint ou uma equipe do Microsoft a quem é membro. Isso permite preservar, coletar, analisar e revisar o conteúdo em outras fontes de dados associadas aos responsáveis da ocorrência.

Para desmarcar a caixa de correio principal e a conta do OneDrive para um responsáveis:

1. Expanda os responsáveis para exibir os locais de dados principais que foram associados automaticamente a cada um dos responsáveis.

2. Selecione **limpar** ao lado de **caixa de correio** ou **onedrive** para remover a caixa de correio ou a conta do onedrive de um dos responsáveis de ser associada como um local de dados para esses responsáveis.

   ![Configurar locais para associar a um funcionário](../media/ConfigureCustodianLocations.png)

Para associar outras caixas de correio, sites, equipes ou grupos do Yammer a um determinado funcionário:

1. Expanda um funcionário para exibir os seguintes serviços para associar locais de dados aos responsáveis. Clique em **Editar** ao lado de um serviço para adicionar um local de dados.

   - **Exchange**: Use para associar outras caixas de correio aos responsáveis. Digite na caixa de pesquisa o nome ou alias (um mínimo de três caracteres) de caixas de correio de usuário ou grupos de distribuição. Selecione as caixas de correio a serem atribuídas aos responsáveis e clique em **Adicionar**.

   - **SharePoint**: Use para associar sites do SharePoint aos responsáveis. Selecione um site na lista ou pesquise um site digitando uma URL na caixa de pesquisa. Selecione os sites a serem atribuídos aos responsáveis e clique em **Adicionar**.

   - **Teams**: Use para atribuir ao Microsoft Teams os responsáveis é membro do no momento. Selecione as equipes que serão atribuídas aos responsáveis e clique em **Adicionar**. Após adicionar uma equipe, o sistema identifica e localiza automaticamente o site do SharePoint e a caixa de correio de grupo associados a essa equipe e os atribui aos responsáveis.

   - **Yammer**: Use para atribuir os grupos do Yammer aos quais o responsáveis é membro no momento. Selecione os grupos a serem atribuídos aos responsáveis e clique em **Adicionar**. Após adicionar uma equipe, o sistema identifica e localiza automaticamente o site do SharePoint e a caixa de correio de grupo associados a esse grupo e os atribui aos responsáveis.

   > [!NOTE]
   > Você pode usar os seletores de local do **Exchange** e **do SharePoint** para associar outras equipes ou grupos do Yammer (que um funcionário não é membro de) a um funcionário. Para fazer isso, você precisa adicionar a caixa de correio e o site associados a cada equipe ou grupo do Yammer.

2. Você pode exibir o número total de caixas de correio, sites, equipes e grupos do Yammer atribuídos a cada um deles expandindo cada um dos responsáveis na tabela. Quando você tiver finalizado os locais de dados atribuídos para cada um dos responsáveis, essas associações serão mantidas e usadas durante os estágios de coleta, processamento e revisão no fluxo de trabalho de descoberta eletrônica avançada.

3. Após adicionar os responsáveis e configurar seus locais de dados, clique em **Avançar** para ir para a página **configurações de retenção** .  

## <a name="step-3-configure-hold-settings"></a>Etapa 3: definir as configurações de retenção

 Depois de finalizar os responsáveis e seus locais de dados, você pode colocar alguns ou todos os responsáveis por retenção. Quando você coloca um bloqueador, todo o conteúdo de todos os locais de conteúdo associados aos responsáveis é preservado até que você remova a retenção ou libere os responsáveis da retenção. Em alguns casos, talvez você queira adicionar os responsáveis por um caso sem colocá-los em espera.

Para colocar os responsáveis e as fontes de dados em retenção:

1. Na página **configurações de retenção** , você pode aplicar uma retenção a responsáveis individuais marcando a caixa de seleção na coluna **isenção** .

   Como alternativa, você pode colocar todos os responsáveis por retenção, selecionando a caixa de seleção **reter** na parte superior da coluna.

2. Verifique as seleções de retenção de responsáveis e clique em **Avançar**.

   > [!NOTE]
   > Se você não colocar uma retenção em um local, os responsáveis e as fontes de dados associadas serão adicionados ao caso, mas o conteúdo dessas fontes de dados não será preservado pela retenção associada ao caso.

## <a name="step-4-review-the-custodians-and-complete-the-process"></a>Etapa 4: revise os responsáveis e conclua o processo

Antes de realmente adicionar os responsáveis ao caso, você pode revisar a lista de responsáveis, os locais de dados atribuídos a eles e as configurações de retenção.

1. Verifique e revise todas as configurações de fontes de dados e a configuração de retenção associada a cada um dos responsáveis na tabela. Se necessário, volte para a página **identificar responsáveis** ou **manter as configurações** para fazer qualquer alteração.

2. Clique em **Enviar** para adicionar os responsáveis e seus locais de dados ao caso e aplicar todas as configurações de retenção do custodial.

   Os novos responsáveis são adicionados ao caso e exibidos na guia fontes de **dados** .

   [![Responsáveis listados na guia ](../media/DataSourcesTab.png) fontes de dados](../media/DataSourcesTab.png#lightbox)
