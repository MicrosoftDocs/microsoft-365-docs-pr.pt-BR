---
title: Configurar o SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Configurar a compreensão do conteúdo no Project Cortex
ms.openlocfilehash: f0a26f0044e578928730cf4930f1524e86dff9f3
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294818"
---
# <a name="set-up-sharepoint-syntex"></a>Configurar o SharePoint Syntex

Os administradores podem usar o centro de administração do Microsoft 365 para configurar o e o Microsoft SharePoint Syntex. 

Antes de começar, considere o seguinte:

- Quais sites do SharePoint você habilitará o processamento de formulários? Todos eles, alguns ou selecionar sites?
- Qual será o nome do seu centro de conteúdo e quem é o administrador do site principal?

Você pode alterar suas configurações após a configuração inicial no centro de administração do Microsoft 365.

O conteúdo deste artigo é para a visualização privada do projeto Cortex. [Saiba mais sobre o Project Cortex](https://aka.ms/projectcortex).

Antes da instalação, certifique-se de planejar a melhor maneira de configurar e configurar a compreensão do conteúdo em seu ambiente. Por exemplo, você precisa fazer considerações sobre os seguintes nomes:

- Os sites do SharePoint que você deseja habilitar o processamento de formulários, alguns ou sites selecionados
- Seu centro de conteúdo e o nome do administrador do site principal

## <a name="requirements"></a>Requisitos 

> [!NOTE]
> Você precisa ter permissões de administrador global ou administrador do SharePoint para poder acessar o centro de administração do Microsoft 365 e configurar a compreensão do conteúdo.

Como administrador, você também pode fazer alterações nas configurações selecionadas a qualquer momento após a instalação, e por todo o conteúdo entendendo as configurações de gerenciamento no centro de administração do Microsoft 365.

## <a name="to-set-up-sharepoint-syntex"></a>Para configurar o SharePoint Syntex

1. No centro de administração do Microsoft 365, selecione **configuração**e, em seguida, exiba a seção de **conhecimento organizacional** .

2. Na seção **conhecimento organizacional** , selecione **automatizar a compreensão do conteúdo**.<br/>

    ![Página de configuração de conhecimento organizacional](../media/content-understanding/admin-org-knowledge-options.png)</br>

3. Na página **automatizar o SharePoint Syntex** , clique em **começar** para percorrer o processo de configuração.<br/>

    ![Iniciar a instalação](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. Na página ativar marcação de imagem, escolha se deseja permitir a [marcação de imagem](image-tagging.md).

    ![Captura de tela das opções de marcação de imagem](../media/content-understanding/admin-content-understanding-setup-image-tagging.png)</br>

5. Na página **Configurar processamento de formulário** , você pode escolher se deseja permitir que os usuários possam usar o Construtor ai para criar modelos de processamento de formulário em bibliotecas de documentos específicas do SharePoint. Uma opção de menu estará disponível na faixa de opções da biblioteca de documentos para **criar um modelo de processamento de formulário** em bibliotecas de documentos do SharePoint na qual ele está habilitado.
 
     Para **quais bibliotecas do SharePoint devem mostrar a opção para criar um modelo de processamento de formulário**, você pode selecionar:</br>
      - **Todas as bibliotecas do SharePoint** para torná-lo disponível para todas as bibliotecas do SharePoint em sua organização.</br>
      - **Somente as bibliotecas nos sites selecionados**e, em seguida, selecione os sites nos quais você deseja torná-lo disponível.</br>

   ![Configurar o processamento de formulários](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > Habilitar essa configuração em uma biblioteca de documentos do SharePoint não afeta os modelos existentes aplicados à biblioteca ou a capacidade de aplicar modelos de compreensão de documentos a uma biblioteca. 
    
6. Na página **criar centro de conteúdo** , você pode criar um site do centro de conteúdo do SharePoint no qual os usuários podem criar e gerenciar modelos de compreensão de documentos. </br>
    a. Em **nome do site**, digite o nome que você deseja dar ao site do centro de conteúdo.</br>
    b. O **endereço do site** mostrará a URL do seu site, com base no que você selecionou para o nome do site. Se você quiser alterá-lo, clique em **Editar**.</br>

      ![Criar centro de conteúdo](../media/content-understanding/admin-cu-create-cc.png)</br>

    Selecione **Avançar**.

7. Na página **revisão e término** , você pode examinar a configuração selecionada e optar por fazer alterações. Se estiver satisfeito com suas seleções, selecione **Ativar**.

8. Na página confirmação, clique em **concluído**.

9. Você retornará à página **automatizar o conteúdo de compreensão** . Nessa página, você pode selecionar **gerenciar** para fazer quaisquer alterações nas suas definições de configuração. 

## <a name="assign-licenses"></a>Atribua licenças

Depois de configurar o SharePoint Syntex, você deve atribuir licenças para os usuários que utilizarão o processamento de formulários e os recursos de compreensão do documento.

Para atribuir licenças:

1. No centro de administração do Microsoft 365, em **usuários**, clique em **usuários ativos**.

2. Selecione os usuários que você deseja licenciar e clique em **gerenciar licenças de produto**.

3. Selecione **atribuir mais**.

4. Selecione **serviços de conteúdo inteligente**. Em **aplicativos**, verifique se o **serviço de dados comuns para serviços de conteúdo inteligente** e **serviços de conteúdo inteligente** estão selecionados.

    ![Licenças do Syntex do SharePoint no centro de administração do Microsoft 365](../media/content-understanding/sharepoint-syntex-licenses.png)

5. Clique em **Salvar alterações**.

## <a name="ai-builder-credits"></a>Créditos do Construtor AI

Se você tiver 300 ou mais licenças do Syntex do SharePoint para o SharePoint Syntex em sua organização, serão alocados os créditos do Construtor AI de 1 milhão. Se você tiver menos de 300 licenças, deverá adquirir créditos do Construtor AI para usar o processamento de formulários.

Você pode estimar a capacidade do Construtor AI mais adequada para a [calculadora do ai Builder](https://powerapps.microsoft.com/ai-builder-calculator).

1. Vá para o [centro de administração da plataforma de energia](https://admin.powerplatform.microsoft.com/resources/capacity) para verificar seus créditos e uso.

    > [!NOTE]
    > Habilitar esta configuração em uma biblioteca de documentos do SharePoint não afeta os modelos existentes aplicados à biblioteca ou a capacidade de aplicar modelos de compreensão de documentos a uma biblioteca. 
    
2. Na página **criar centro de conteúdo** , você pode criar um site do centro de conteúdo do SharePoint para o qual os usuários podem criar e gerenciar modelos de compreensão de documentos. </br>
    a. Em **nome do site**, digite o nome desejado para o site do centro de conteúdo.</br>
    b. O **endereço do site** mostra a URL do seu site, com base no nome do site.</br>

    > [!NOTE] 
    > Embora você possa selecionar qualquer idioma suportado, o conteúdo entendendo modelos só pode ser criado para inglês.</br>

      ![Criar centro de conteúdo](../media/content-understanding/admin-cu-create-cc.png)</br>

3. Selecione **Avançar**.

4. Na página **concluir e revisar** , examine a configuração selecionada e escolha fazer alterações. Se estiver satisfeito com suas seleções, selecione **Ativar**.

5. A página **conteúdo Understanding Activated** é exibida, confirmando que o sistema adicionou suas preferências de processamento de formulário e criou o site do centro de conteúdo. Selecione **Concluído**.

6. Você retornará à página **automatizar o conteúdo de compreensão** . Nessa página, você pode selecionar **gerenciar** para fazer quaisquer alterações nas suas definições de configuração. 

## <a name="see-also"></a>Confira também

[Visão geral do modelo de processamento de formulário](https://docs.microsoft.com/ai-builder/form-processing-model-overview)

[Passo a passo: como criar um documento entendendo o modelo (vídeo)](https://www.youtube.com/watch?v=DymSHObD-bg)

