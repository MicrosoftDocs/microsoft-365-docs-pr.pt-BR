---
title: Configuração do SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection: enabler-strategic
search.appverid: MET150
localization_priority: Priority
description: Configure a compreensão de conteúdo no Projeto Cortex
ms.openlocfilehash: dfbcc8e41a28e3107b58ac6b8d471e3a2a08d036
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087566"
---
# <a name="set-up-sharepoint-syntex"></a>Configuração do SharePoint Syntex

Os administradores podem usar o Centro de administração do Microsoft 365 para configurar o [Microsoft SharePoint Syntex](index.md). 

Considere o seguinte antes de começar:

- Which SharePoint sites will you enable form processing? All of them, some, or select sites?
- Qual será o nome do seu centro de conteúdo padrão?

É possível alterar suas configurações após a configuração inicial no Centro de administração do Microsoft 365.

Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment. For example, you need to make considerations about the following names of:

- Sites do SharePoint que você deseja ativar o processamento de formulários - todos, alguns ou sites selecionados
- Seu centro de conteúdo e o nome do administrador do site principal

## <a name="requirements"></a>Requisitos 

> [!NOTE]
> Você deve ter permissões administrativas globais ou de administrador do SharePoint para poder acessar o Centro de administração do Microsoft 365 e configurar a compreensão de conteúdo.

Como administrador, também é possível fazer alterações nas configurações selecionadas a qualquer momento após a configuração e ao longo das configurações de gerenciamento de compreensão de conteúdo no Centro de Administração do Microsoft 365.

## <a name="to-set-up-sharepoint-syntex"></a>Para configurar o SharePoint Syntex

1. No centro de administração do Microsoft 365, selecione **Configurar** e visualize a seção **Arquivos e conteúdo**.

2. Na seção **Arquivos e conteúdo**, selecione **Automatizar a compreensão de conteúdo**.<br/>

3. Na página **Compreensão automatizada de conteúdo**, clique em **Começar** para percorrer o processo de instalação.<br/>

    > [!div class="mx-imgBorder"]
    > ![Iniciar a instalação](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. On the **Configure Form Processing** page, you can choose if you want to let users be able to create form processing models in specific SharePoint document libraries. A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.
 
     Para **Quais bibliotecas do SharePoint devem exibir a opção para criar um modelo de processamento de formulário**, você pode selecionar:</br>
      - **Todas as bibliotecas do SharePoint** para torná-lo disponível em todas as bibliotecas do SharePoint em sua organização.</br>
      - **Bibliotecas somente em sites selecionados**, e então selecione os sites nos quais você quer disponibilizá-lo ou carregue uma lista de até 50 sites.</br>
      - **Nenhuma biblioteca do SharePoint** se você não deseja torná-lo disponível para nenhum site (você pode alterar isto após a configuração).

   > [!div class="mx-imgBorder"]
   > ![Configurar o processamento de formulário](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > A remoção de um site após a sua insalubridade não afeta os modelos existentes aplicados às bibliotecas naquele site ou a capacidade de aplicar modelos de compreensão de documentos a uma biblioteca. 
    
5. Na página **Criar Centro de Conteúdo**, você pode criar um site de centro de conteúdo do SharePoint, no qual seus usuários poderão criar e gerenciar modelos de compreensão de documentos.

    1. Para **Nome do site**, digite o nome que você quer dar ao site do centro de conteúdo.
    
    1. The **Site address** will show the URL for your site, based on what you selected for the site name. If you want to change it, click **Edit**.

       > [!div class="mx-imgBorder"]
       > ![Criar centro de conteúdo](../media/content-understanding/admin-cu-create-cc.png)</br>

       Selecione **Avançar**.

6. On the **Review and finish** page, you can look at your selected setting and choose to make changes. If you are satisfied with your selections, select **Activate**.

7. Na página de confirmação, clique em **Concluído**.

8. You'll be returned to your **Automate content understanding** page. From this page, you can select **Manage** to make any changes to your configuration settings. 

## <a name="assign-licenses"></a>Atribua licenças

Uma vez configurado o SharePoint Syntex, será necessário atribuir licenças para os usuários que farão uso dos recursos do SharePoint Syntex.

Atribuição de licenças:

1. No Centro de administração do Microsoft 365, em **Usuários**, clique em **Usuários ativos**.

2. Selecione os usuários que você deseja licenciar, e clique **Gerenciar licenças de produtos**.

3. Selecione **Atribuir mais**.

4. Select **SharePoint Syntex**. Under **Apps**, make sure **Common Data Service for SharePoint Syntex**, **SharePoint Syntex**, and **SharePoint Syntex - SPO type** are all selected.

    > [!div class="mx-imgBorder"]
    > ![Licenças do SharePoint Syntex no Centro de administração do Microsoft 365](../media/content-understanding/sharepoint-syntex-licenses.png)

5. Clique em **Salvar alterações**.

## <a name="ai-builder-credits"></a>Créditos do Construtor de IA

If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits. If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.

Você pode estimar a capacidade correta do Construtor de IA com a [calculadora do Construtor de IA](https://powerapps.microsoft.com/ai-builder-calculator).

Vá até o [Centro de administração da Plataforma Power ](https://admin.powerplatform.microsoft.com/resources/capacity) para verificar seus créditos e uso.

## <a name="see-also"></a>Confira também

[Visão geral do modelo de processamento de formulários](https://docs.microsoft.com/ai-builder/form-processing-model-overview).

[Passo a passo: como construir um modelo de compreensão de documentos (vídeo)](https://www.youtube.com/watch?v=DymSHObD-bg)

