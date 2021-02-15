---
title: Adicionar custodiantes a uma ocorrência de Descoberta Avançada
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
description: Saiba como usar a ferramenta de gerenciamento custodiante integrado na Descoberta eDiscovery Avançada para coordenar seus fluxos de trabalho e identificar fontes de dados relevantes em um caso.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9468fb889e9115b3652d1dba8a6c6632bb367fe3
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740338"
---
# <a name="add-custodians-to-an-advanced-ediscovery-case"></a>Adicionar custodiantes a uma ocorrência de Descoberta Avançada

Use a ferramenta de gerenciamento custodiante integrado na Descoberta Avançada para coordenar seus fluxos de trabalho em torno do gerenciamento de custodiantes e identificação de fontes de dados custodiantes relevantes associadas a uma ocorrência. Quando você adiciona um custodiante, o sistema pode identificar e colocar em espera automaticamente a caixa de correio do Exchange e a conta do OneDrive for Business. Durante o processo de descoberta de sua investigação, você também pode identificar outras fontes de dados (como caixas de correio, sites ou Teams) para as quais um custodiante acessou ou contribuiu. Nessa situação, você pode usar a ferramenta de gerenciamento custodiante para associar essas fontes de dados a um custodiante específico. Depois de adicionar custodiantes a uma ocorrência e associar outra fonte de dados a eles, você pode rapidamente preservar dados e pesquisar os dados custodiantes.

Você pode adicionar e gerenciar custodiantes em casos de Descoberta Avançada em quatro etapas:

1. Identifique os custodiantes.

2. Escolha locais de dados custodiante.

3. Definir configurações de espera.

4. Revise os custodiantes e conclua o processo.

   [![Guia Fontes no caso de Descoberta Avançada ](../media/AeD-Sources-Tab.png)](../media/AeD-Sources-Tab.png#lightbox)

## <a name="make-sure-you-have-the-necessary-permissions"></a>Certifique-se de que você tenha as permissões necessárias

Para adicionar custodiantes a uma ocorrência, você deve ser um membro do grupo de função gerente de descoberta de ediscovery. Isso fornece as permissões necessárias para adicionar custodiantes a uma ocorrência e colocar em espera as fontes de dados custodial. Para obter mais informações, confira [Atribuir permissões de descoberta eletrônica](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions).

## <a name="step-1-identify-custodians"></a>Etapa 1: identificar os custodiantes

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e entre com uma conta de usuário que recebeu as permissões apropriadas de Descoberta.

2. No painel de navegação esquerdo do centro de conformidade do Microsoft 365, clique em Mostrar tudo e clique em Descoberta > **Avançado.**

3. Na página **Descoberta Avançada, clique**  na guia Ocorrências e selecione a ocorrência à quais você deseja adicionar custodiantes.

4. Clique na **guia Fontes de** dados e clique em Adicionar fonte de **dados** Adicionar  >  **novos custodiantes.**

5. Adicione um ou mais usuários em sua organização como custodiantes à ocorrência digitando a primeira parte do nome ou alias de uma pessoa. Depois de encontrar a pessoa correta, selecione seu nome para adicioná-la à lista.

## <a name="step-2-choose-custodian-data-locations"></a>Etapa 2: Escolher locais de dados custodiante

Depois de selecionar os custodiantes, o sistema tentará identificar e verificar automaticamente esses usuários e suas fontes de dados. Depois de adicionar custodiantes à lista, a ferramenta inclui automaticamente a caixa de correio principal e a conta do OneDrive para cada custodiante. Você pode optar por não incluir essas fontes de dados ao adicionar custodiantes à ocorrência.

Além da caixa de correio de um responsável e da conta do OneDrive, você também pode associar outros locais de dados a um custodiante, como um site do SharePoint ou uma Equipe da Microsoft da qual o custodiante é membro. Isso permite preservar, coletar, analisar e revisar conteúdo em outras fontes de dados associadas aos custodiantes do caso.

Para desmarcar a caixa de correio principal e a conta do OneDrive para um custodiatário:

1. Expanda o custodiante para exibir os locais de dados primários que foram associados automaticamente a cada custodiante.

2. Selecione **Limpar ao** **lado** da Caixa de Correio ou do **OneDrive** para remover a caixa de correio de um responsável ou a conta do OneDrive de serem associadas como um local de dados para esse custodiante.

   ![Configurar locais para associar a um custodiatário](../media/ConfigureCustodianLocations.png)

Para associar outras caixas de correio, sites, equipes ou grupos do Yammer a um custodiante específico:

1. Expanda um custodiante para exibir os seguintes serviços para associar locais de dados ao custodiante. Clique **em Editar** ao lado de um serviço para adicionar um local de dados.

   - **Exchange**: Use para associar outras caixas de correio ao custodiatário. Digite na caixa de pesquisa o nome ou alias (um mínimo de três caracteres) de caixas de correio de usuário ou grupos de distribuição. Selecione as caixas de correio a atribuir ao custodiatário e clique em **Adicionar.**

   - **SharePoint**: use para associar sites do SharePoint ao custodiatário. Selecione um site na lista ou procure um site digitando uma URL na caixa de pesquisa. Selecione os sites para atribuir ao custodiatário e clique em **Adicionar.**

   - **Teams**: use para atribuir ao Microsoft Teams que o custodiatário é membro no momento. Selecione as equipes a atribuir ao custodiatário e clique em **Adicionar.** Depois que você adicionar uma equipe, o sistema identificará automaticamente e localizará o site do SharePoint e a caixa de correio de grupo associada a essa equipe e a atribuirá ao custodiante.

   - **Yammer**: use para atribuir os grupos do Yammer dos que o custodiante é atualmente membro. Selecione os grupos para atribuir ao custodiatário e clique em **Adicionar.** Depois de adicionar uma equipe, o sistema identifica automaticamente e localiza o site do SharePoint e a caixa de correio de grupo associada a esse grupo e os atribui ao custodiante.

   > [!NOTE]
   > Você pode usar os seletores de local do **Exchange** e do **SharePoint** para associar outras equipes ou grupos do Yammer (dos que um custodiante não é membro) a um custodiante. Para fazer isso, você precisa adicionar a caixa de correio e o site associados a cada equipe ou grupo do Yammer.

2. Você pode exibir o número total de caixas de correio, sites, equipes e grupos do Yammer atribuídos a cada custodiante expandindo cada custodiante na tabela. Quando você finalizar os locais de dados atribuídos para cada custodiante, essas associações serão mantidas e usadas durante as etapas de coleta, processamento e revisão no fluxo de trabalho de Descoberta Eletrônico Avançada.

3. Depois de adicionar custodiantes e configurar seus locais de dados, clique em **Next** para ir para a página de configurações **de** Espera.  

## <a name="step-3-configure-hold-settings"></a>Etapa 3: Definir configurações de espera

 Depois de finalizar os custodiantes e seus locais de dados, você pode colocar alguns ou todos os custodiantes em espera. Quando você coloca um custodiante em espera, todo o conteúdo em todos os locais de conteúdo que estão associados ao custodiante é preservado até que você remova a iseção ou libere o custodiante da iserção. Em alguns casos, talvez você queira adicionar custodiantes a uma ocorrência sem colocá-los em espera.

Para colocar os custodiantes e as fontes de dados em espera:

1. Na página **Configurações de** Espera, você pode aplicar uma responsabilidade a custodiantes individuais marcando a caixa de seleção na **coluna** Espera.

   Como alternativa, você pode colocar todos os  custodiantes em espera selecionando a caixa de seleção De espera na parte superior da coluna.

2. Verifique as seleções de espera custodiada e clique em **Próximo.**

   > [!NOTE]
   > Se você não colocar um custodiante em um custodiante, o custodiante e suas fontes de dados associadas serão adicionados à ocorrência, mas o conteúdo nessas fontes de dados não será preservado pela responsabilidade associada à ocorrência.

## <a name="step-4-review-the-custodians-and-complete-the-process"></a>Etapa 4: Revise os custodiantes e conclua o processo

Antes de realmente adicionar os custodiantes à ocorrência, você pode analisar a lista de custodiantes, os locais de dados atribuídos a eles e as configurações de espera.

1. Verifique e revise todas as fontes de dados e a configuração de espera associada a cada custodiante na tabela. Se necessário, volte para as páginas Identificar **custodiante** ou Configurações **de** Espera para fazer qualquer alteração.

2. Clique **em Enviar** para adicionar custodiantes e seus locais de dados à ocorrência e aplicar todas as configurações de espera de custodiante.

   Os novos custodiantes são adicionados à ocorrência e exibidos na **guia Fontes de** dados.

   [![Custodiantes listados na guia Fontes de dados ](../media/DataSourcesTab.png)](../media/DataSourcesTab.png#lightbox)
