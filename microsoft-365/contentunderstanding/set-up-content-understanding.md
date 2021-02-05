---
title: Configuração do SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: ssquires
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
search.appverid: MET150
localization_priority: Priority
description: Configure a compreensão de conteúdo no Projeto Cortex
ms.openlocfilehash: 0e5b48bab343f887a1438386bfa4f7915126ccd7
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094704"
---
# <a name="set-up-sharepoint-syntex"></a>Configuração do SharePoint Syntex

Os administradores podem usar o Centro de administração do Microsoft 365 para configurar o [Microsoft SharePoint Syntex](index.md). 

Considere o seguinte antes de começar:

- Em quais sites do Microsoft Office SharePoint Online você habilitará o processamento de formulários? Todos, alguns ou sites selecionados?
- Como você nomeará seu centro de conteúdo padrão?

É possível alterar suas configurações após a configuração inicial no Centro de administração do Microsoft 365.

Antes da configuração, certifique-se de planejar a melhor maneira de estabelecer e configurar a compreensão de conteúdo no seu ambiente. Por exemplo, você precisa tomar as seguintes decisões:

- Os sites do Microsoft Office SharePoint Online nos quais você deseja habilitar o processamento de formulários - todos, alguns ou sites selecionados
- O nome e os administradores do seu centro de conteúdo

## <a name="requirements"></a>Requisitos 

> [!NOTE]
> Você precisa ter permissões administrativas globais ou de administrador do SharePoint para poder acessar o Centro de administração do Microsoft 365 e configurar o SharePoint Syntex.

Como administrador, também é possível fazer alterações nas configurações selecionadas a qualquer momento após a configuração e ao longo das configurações de gerenciamento de compreensão de conteúdo no Centro de Administração do Microsoft 365.

## <a name="to-set-up-sharepoint-syntex"></a>Para configurar o SharePoint Syntex

1. No centro de administração do Microsoft 365, selecione **Configurar** e visualize a seção **Arquivos e conteúdo**.

2. Na seção **Arquivos e conteúdo**, selecione **Automatizar a compreensão de conteúdo**.<br/>

3. Na página **Compreensão automatizada de conteúdo**, clique em **Começar** para percorrer o processo de instalação.<br/>

    > [!div class="mx-imgBorder"]
    > ![Iniciar a instalação](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. Na página **Configurar Processamento de Formulário**, você pode escolher se quer permitir que os usuários sejam capazes de criar modelos de processamento de formulários em bibliotecas específicas de documentos do SharePoint. Uma opção de menu estará disponível na faixa de opções da biblioteca de documentos para **Criar um modelo de processamento de formulário** nas bibliotecas de documentos do SharePoint nas quais ele está ativado.
 
     Para **Quais bibliotecas do SharePoint devem exibir a opção para criar um modelo de processamento de formulário**, você pode selecionar:</br>
      - **Bibliotecas em todos os sites do Microsoft Office SharePoint Online** para torná-lo disponível para todas as bibliotecas do SharePoint em sua organização.</br>
      - **Bibliotecas em sites selecionados do Microsoft Office SharePoint Online** e, a seguir, selecione os sites nos quais deseja disponibilizá-las ou carregue uma lista de até 50 sites.</br>
      - **Nenhuma biblioteca do SharePoint** se você não deseja torná-lo disponível para nenhum site (você pode alterar isto após a configuração).

   > [!div class="mx-imgBorder"]
   > ![Configurar o processamento de formulário](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > A remoção de um site após a sua insalubridade não afeta os modelos existentes aplicados às bibliotecas naquele site ou a capacidade de aplicar modelos de compreensão de documentos a uma biblioteca. 
    
5. Na página **Criar Centro de Conteúdo**, você pode criar um site de centro de conteúdo do SharePoint, no qual seus usuários poderão criar e gerenciar modelos de compreensão de documentos.

    1. Para **Nome do site**, digite o nome que você quer dar ao site do centro de conteúdo.
    
    1. O **Endereço do site** mostrará o URL do seu site, baseado no que você selecionou para o nome do site. Se você desejar mudá-lo, clique em **Editar**.

       > [!div class="mx-imgBorder"]
       > ![Criar centro de conteúdo](../media/content-understanding/admin-cu-create-cc.png)</br>

       Selecione **Avançar**.

6. Na página **Revisão e acabamento**, você pode olhar para a configuração selecionada e escolher fazer alterações. Se estiver satisfeito com as suas seleções, selecione **Ativar**.

7. Na página de confirmação, clique em **Concluído**.

8. Você retornará à sua página **Compreensão automatizada de conteúdo**. A partir desta página, é possível selecionar **Gerenciar** para fazer quaisquer alterações em suas configurações. 

## <a name="assign-licenses"></a>Atribua licenças

Uma vez configurado o SharePoint Syntex, será necessário atribuir licenças para os usuários que farão uso dos recursos do SharePoint Syntex.

Atribuição de licenças:

1. No Centro de administração do Microsoft 365, em **Usuários**, clique em **Usuários ativos**.

2. Selecione os usuários que você deseja licenciar, e clique **Gerenciar licenças de produtos**.

3. Selecione **Atribuir mais**.

4. Selecione **SharePoint Syntex**. Em **Aplicativos**, certifique-se de que **Common Data Service para o SharePoint Syntex**, **SharePoint Syntex** e **SharePoint Syntex - tipo de SPO** estão todos selecionados.

    > [!div class="mx-imgBorder"]
    > ![Licenças do SharePoint Syntex no Centro de administração do Microsoft 365](../media/content-understanding/sharepoint-syntex-licenses.png)

5. Clique em **Salvar alterações**.

## <a name="ai-builder-credits"></a>Créditos do Construtor de IA

Se você tiver 300 ou mais licenças do SharePoint Syntex para o SharePoint Syntex na sua organização, você receberá um milhão de créditos do Construtor de IA. Se você tiver menos de 300 licenças, você deve comprar créditos do Construtor de IA para usar o processamento de formulários.

Você pode estimar a capacidade correta do Construtor de IA com a [calculadora do Construtor de IA](https://powerapps.microsoft.com/ai-builder-calculator).

Vá até o [Centro de administração da Plataforma Power ](https://admin.powerplatform.microsoft.com/resources/capacity) para verificar seus créditos e uso.

## <a name="see-also"></a>Confira também

[Visão geral do modelo de processamento de formulários](https://docs.microsoft.com/ai-builder/form-processing-model-overview).

[Passo a passo: como construir um modelo de compreensão de documentos (vídeo)](https://www.youtube.com/watch?v=DymSHObD-bg)
