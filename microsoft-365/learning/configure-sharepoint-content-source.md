---
title: 'Em breve: Configure SharePoint como uma fonte de conteúdo de aprendizagem para o Microsoft Viva Learning (Visualização)'
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 04/30/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: Saiba como configurar o SharePoint como uma fonte de conteúdo de aprendizagem para o Microsoft Viva Learning (Visualização).
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: fc702f57b75b78ab523226ba7d8a8eb6505f2975
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244112"
---
# <a name="coming-soon-configure-sharepoint-as-a-learning-content-source-for-microsoft-viva-learning-preview"></a><span data-ttu-id="b738a-103">Em breve: Configure SharePoint como uma fonte de conteúdo de aprendizagem para o Microsoft Viva Learning (Visualização)</span><span class="sxs-lookup"><span data-stu-id="b738a-103">Coming soon: Configure SharePoint as a learning content source for Microsoft Viva Learning (Preview)</span></span>

> [!NOTE]
> <span data-ttu-id="b738a-104">As informações neste artigo se relacionam a um produto de visualização que pode ser substancialmente modificado antes de ser lançado comercialmente.</span><span class="sxs-lookup"><span data-stu-id="b738a-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> 

<span data-ttu-id="b738a-105">Você pode configurar SharePoint como uma fonte de conteúdo de aprendizagem para disponibilizar o conteúdo da sua organização no Viva Learning (Visualização).</span><span class="sxs-lookup"><span data-stu-id="b738a-105">You can configure SharePoint as a learning content source to make your organization's own content available in Viva Learning (Preview).</span></span>

## <a name="overview"></a><span data-ttu-id="b738a-106">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="b738a-106">Overview</span></span>

<span data-ttu-id="b738a-107">O administrador de conhecimento (ou administrador global) fornece uma URL de site para onde o Serviço de Aprendizagem pode criar um local centralizado vazio, o Repositório de Conteúdo do Aplicativo de Aprendizagem, na forma de uma lista SharePoint estruturada.</span><span class="sxs-lookup"><span data-stu-id="b738a-107">The knowledge admin (or global administrator) provides a site URL to where the Learning Service can create an empty centralized location—the Learning App Content Repository—in the form of a structured SharePoint list.</span></span> <span data-ttu-id="b738a-108">Essa lista pode ser usada pela sua organização para abrigar links para pastas SharePoint que contêm conteúdo de aprendizagem.</span><span class="sxs-lookup"><span data-stu-id="b738a-108">This list can be used by your organization to house links to cross-company SharePoint folders that contain learning content.</span></span> <span data-ttu-id="b738a-109">Os administradores são responsáveis por coletar e fazer a curadoria de uma lista de URLs para pastas.</span><span class="sxs-lookup"><span data-stu-id="b738a-109">Admins are responsible for collecting and curating a list of URLs for folders.</span></span> <span data-ttu-id="b738a-110">Essas pastas só devem incluir conteúdo que pode ser disponibilizado no Viva Learning (Visualização).</span><span class="sxs-lookup"><span data-stu-id="b738a-110">These folders should only include content that can be made available in Viva Learning (Preview).</span></span>

<span data-ttu-id="b738a-111">O Viva Learning (Visualização) dá suporte aos seguintes tipos de documento:</span><span class="sxs-lookup"><span data-stu-id="b738a-111">Viva Learning (Preview) supports the following document types:</span></span>

- <span data-ttu-id="b738a-112">Word, PowerPoint, Excel, PDF</span><span class="sxs-lookup"><span data-stu-id="b738a-112">Word, PowerPoint, Excel, PDF</span></span>
- <span data-ttu-id="b738a-113">Áudio (.m4a)</span><span class="sxs-lookup"><span data-stu-id="b738a-113">Audio (.m4a)</span></span>
- <span data-ttu-id="b738a-114">Vídeo (.mov, .mp4, .avi)</span><span class="sxs-lookup"><span data-stu-id="b738a-114">Video (.mov, .mp4, .avi)</span></span>

<span data-ttu-id="b738a-115">Para obter mais informações, [consulte SharePoint limites](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits?redirectSourcePath=%252farticle%252fSharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span><span class="sxs-lookup"><span data-stu-id="b738a-115">For more information, see [SharePoint limits](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits?redirectSourcePath=%252farticle%252fSharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span> 

## <a name="permissions"></a><span data-ttu-id="b738a-116">Permissões</span><span class="sxs-lookup"><span data-stu-id="b738a-116">Permissions</span></span>

<span data-ttu-id="b738a-117">As URLs da pasta da biblioteca de documentos podem ser coletadas de qualquer SharePoint site na organização.</span><span class="sxs-lookup"><span data-stu-id="b738a-117">Document library folder URLs can be collected from any SharePoint site in the organization.</span></span> <span data-ttu-id="b738a-118">O Viva Learning (Visualização) segue todas as permissões de conteúdo existentes.</span><span class="sxs-lookup"><span data-stu-id="b738a-118">Viva Learning (Preview) follows all existing content permissions.</span></span> <span data-ttu-id="b738a-119">Portanto, somente o conteúdo para o qual um usuário tem permissão para acessar é pesquisável e visível no Viva Learning (Visualização).</span><span class="sxs-lookup"><span data-stu-id="b738a-119">Therefore, only content for which a user has permission to access is searchable and visible within Viva Learning (Preview).</span></span> <span data-ttu-id="b738a-120">Qualquer conteúdo dentro dessas pastas será pesquisável, mas somente o conteúdo para o qual o funcionário individual tem permissões pode ser usado.</span><span class="sxs-lookup"><span data-stu-id="b738a-120">Any content within these folders will be searchable, but only content to which the individual employee has permissions can be used.</span></span>

<span data-ttu-id="b738a-121">A exclusão de conteúdo do repositório da sua organização não é suportada no momento.</span><span class="sxs-lookup"><span data-stu-id="b738a-121">Content deletion from your organization’s repository is not currently supported.</span></span>

<span data-ttu-id="b738a-122">Para remover conteúdo não intencionalmente à superfície, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="b738a-122">To remove unintentionally surfaced content, follow these steps:</span></span>

1.  <span data-ttu-id="b738a-123">Para restringir o acesso à biblioteca de documentos, selecione a opção **Mostrar ações** e selecione **Gerenciar acesso**.</span><span class="sxs-lookup"><span data-stu-id="b738a-123">To restrict access to the document library, select the **Show actions** option, and then select **Manage access**.</span></span>
     
     ![Página da biblioteca de documentos SharePoint mostrar a opção Mostrar ações com Gerenciar acesso com alta qualificação.](../media/learning/learning-sharepoint-permissions2.png)

2.  <span data-ttu-id="b738a-125">Exclua o documento original na biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="b738a-125">Delete the original document within the document library.</span></span>

<span data-ttu-id="b738a-126">Para obter mais informações, consulte [Sharing and permissions in the SharePoint modern experience](/sharepoint/modern-experience-sharing-permissions).</span><span class="sxs-lookup"><span data-stu-id="b738a-126">For more information, see [Sharing and permissions in the SharePoint modern experience](/sharepoint/modern-experience-sharing-permissions).</span></span> 

## <a name="learning-service"></a><span data-ttu-id="b738a-127">Serviço de Aprendizagem</span><span class="sxs-lookup"><span data-stu-id="b738a-127">Learning Service</span></span>

<span data-ttu-id="b738a-128">O Serviço de Aprendizagem usa as URLs de pasta fornecidas para obter metadados de todo o conteúdo armazenado nessas pastas.</span><span class="sxs-lookup"><span data-stu-id="b738a-128">The Learning Service uses the provided folder URLs to get metadata from all content stored in those folders.</span></span> <span data-ttu-id="b738a-129">Dentro de 24 horas após fornecer a URL da pasta no repositório centralizado, os funcionários podem pesquisar e usar o conteúdo da sua organização no Viva Learning (Visualização).</span><span class="sxs-lookup"><span data-stu-id="b738a-129">Within 24 hours of supplying the folder URL in the centralized repository, employees can search for and use your organization’s content within Viva Learning (Preview).</span></span> <span data-ttu-id="b738a-130">Todas as alterações no conteúdo, incluindo metadados e permissões atualizadas, também serão aplicadas no Serviço de Aprendizagem dentro de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="b738a-130">All changes to content, including updated metadata and permissions, will also be applied in the Learning Service within 24 hours.</span></span>

## <a name="configure-sharepoint-as-a-source"></a><span data-ttu-id="b738a-131">Configurar SharePoint como fonte</span><span class="sxs-lookup"><span data-stu-id="b738a-131">Configure SharePoint as a source</span></span>

<span data-ttu-id="b738a-132">Você deve ser um administrador Microsoft 365 global, SharePoint administrador ou administrador de conhecimento para executar essas tarefas.</span><span class="sxs-lookup"><span data-stu-id="b738a-132">You must be a Microsoft 365 global administrator, SharePoint administrator, or knowledge admin to perform these tasks.</span></span>

<span data-ttu-id="b738a-133">Para configurar SharePoint como fontes de conteúdo de aprendizagem no Viva Learning (Visualização), siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="b738a-133">To configure SharePoint as a learning content sources in for Viva Learning (Preview), follow these steps:</span></span>

1.  <span data-ttu-id="b738a-134">Na navegação à esquerda do centro de administração Microsoft 365, acesse **Configurações**  >  **Org.**</span><span class="sxs-lookup"><span data-stu-id="b738a-134">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>
 
2.  <span data-ttu-id="b738a-135">Na página **Configurações da** Organização, na guia **Serviços,** selecione **Viva Learning (Visualização)**.</span><span class="sxs-lookup"><span data-stu-id="b738a-135">On the **Org settings** page, on the **Services** tab, select **Viva Learning (Preview)**.</span></span>

     ![Configurações página no centro de administração Microsoft 365 mostrando o Viva Learning listado.](../media/learning/learning-sharepoint-configure1.png)

3.  <span data-ttu-id="b738a-137">No painel **Viva Learning (Visualização),** em SharePoint, fornece a URL do site para o site SharePoint onde você deseja que o Viva Learning (Visualização) crie um repositório centralizado.</span><span class="sxs-lookup"><span data-stu-id="b738a-137">On the **Viva Learning (Preview)** panel, under SharePoint, provides the site URL to the SharePoint site where you want Viva Learning (Preview) to create a centralized repository.</span></span>

     ![Painel de aprendizagem no Microsoft 365 de administração mostrando SharePoint selecionado.](../media/learning/learning-sharepoint-configure2.png)

4.  <span data-ttu-id="b738a-139">Uma SharePoint é criada automaticamente no site SharePoint fornecido.</span><span class="sxs-lookup"><span data-stu-id="b738a-139">A SharePoint list is created automatically within the provided SharePoint site.</span></span>

     ![Lista de SharePoint recém-criada no site SharePoint site.](../media/learning/learning-sharepoint-configure3.png)

     <span data-ttu-id="b738a-141">Na navegação à esquerda do site SharePoint, selecione Conteúdo do **site**  >  **Aprendendo Repositório de Conteúdo do Aplicativo.**</span><span class="sxs-lookup"><span data-stu-id="b738a-141">In the left navigation of the SharePoint site, select **Site contents** > **Learning App Content Repository**.</span></span> 

     ![SharePoint lista mostrando a navegação de conteúdo do site e a seção Repositório de Conteúdo do Aplicativo de Aprendizagem.](../media/learning/learning-sharepoint-configure4.png) 

5. <span data-ttu-id="b738a-143">Na página **Repositório de Conteúdo do Aplicativo** de Aprendizagem, preencha a lista de SharePoint com URLs para as pastas de conteúdo de aprendizagem.</span><span class="sxs-lookup"><span data-stu-id="b738a-143">On the **Learning App Content Repository** page, populate the SharePoint list with URLs to the learning content folders.</span></span>

   1. <span data-ttu-id="b738a-144">Selecione **Novo** para exibir o **painel Novo item.**</span><span class="sxs-lookup"><span data-stu-id="b738a-144">Select **New** to view the **New item** panel.</span></span> 

       ![Aprendendo a página repositório de conteúdo em SharePoint mostrando a opção Nova.](../media/learning/learning-sharepoint-configure5.png)
 
   2. <span data-ttu-id="b738a-146">No painel **Novo item,** no campo **Título,** adicione um nome de diretório de sua escolha.</span><span class="sxs-lookup"><span data-stu-id="b738a-146">On the **New item** panel, in the **Title** field, add a directory name of your choice.</span></span> <span data-ttu-id="b738a-147">No campo **URL da pasta,** adicione a URL à pasta de conteúdo de aprendizagem.</span><span class="sxs-lookup"><span data-stu-id="b738a-147">In the **Folder URL** field, add the URL to the learning content folder.</span></span> <span data-ttu-id="b738a-148">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b738a-148">Select **Save**.</span></span>

       ![Novo painel de itens em SharePoint mostrando os campos url de título e pasta.](../media/learning/learning-sharepoint-configure6.png)

   3. <span data-ttu-id="b738a-150">A **página Repositório de Conteúdo do Aplicativo** de Aprendizagem é atualizada com o novo conteúdo de aprendizado.</span><span class="sxs-lookup"><span data-stu-id="b738a-150">The **Learning App Content Repository** page is updated with the new learning content.</span></span>

       ![Aprendendo a página repositório de conteúdo em SharePoint mostrando as informações atualizadas.](../media/learning/learning-sharepoint-configure7.png)

> [!NOTE]
> <span data-ttu-id="b738a-152">Para permitir um acesso mais amplo ao Repositório de Conteúdo do Aplicativo de Aprendizagem, um link para a lista em breve estará disponível na interface do Viva Learning (Visualização), onde os usuários podem solicitar acesso e, finalmente, ajudar a preencher a lista.</span><span class="sxs-lookup"><span data-stu-id="b738a-152">To allow for broader access to the Learning App Content Repository, a link to the list soon will be available in the Viva Learning (Preview) interface where users can request access and ultimately help populate the list.</span></span> <span data-ttu-id="b738a-153">Os proprietários de sites e administradores globais serão necessários para conceder acesso à lista.</span><span class="sxs-lookup"><span data-stu-id="b738a-153">Site owners and global administrators will be required to grant access to the list.</span></span> <span data-ttu-id="b738a-154">O Access é específico apenas da lista e não se aplica ao site onde a lista está armazenada.</span><span class="sxs-lookup"><span data-stu-id="b738a-154">Access is specific to the list only and does not apply to the site where the list is stored.</span></span> <span data-ttu-id="b738a-155">Para obter mais informações, consulte Fornecer o conteúdo [da sua própria](#provide-your-own-organizations-content) organização posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="b738a-155">For more information, see [Provide your own organization's content](#provide-your-own-organizations-content) later in this article.</span></span>

### <a name="folder-url-document-library-curation"></a><span data-ttu-id="b738a-156">Curação da biblioteca de documentos da URL da pasta</span><span class="sxs-lookup"><span data-stu-id="b738a-156">Folder URL document library curation</span></span>

<span data-ttu-id="b738a-157">Os metadados padrão (como data modificada, criada por, nome do documento, tipo de conteúdo e nome da organização) são automaticamente retirados para o Viva Learning (Visualização) pela API do Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="b738a-157">Default metadata (such as modified date, created by, document name, content type, and organization name) is automatically pulled into Viva Learning (Preview) by the Microsoft Graph API.</span></span>
 
<span data-ttu-id="b738a-158">Para melhorar a relevância geral da descoberta e da pesquisa do conteúdo, recomendamos adicionar uma coluna **Descrição.**</span><span class="sxs-lookup"><span data-stu-id="b738a-158">To improve overall discovery and search relevance of the content, we recommend adding a **Description** column.</span></span>

<span data-ttu-id="b738a-159">Para adicionar uma **coluna Descrição** à página da biblioteca de documentos, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="b738a-159">To add a **Description** column to the document library page, follow these steps:</span></span>

1.  <span data-ttu-id="b738a-160">Na página **Documentos,** selecione **Adicionar coluna**.</span><span class="sxs-lookup"><span data-stu-id="b738a-160">On the **Documents** page, select **Add column**.</span></span>

2. <span data-ttu-id="b738a-161">Selecione a **opção Mostrar ações** e selecione Linha única de **texto**.</span><span class="sxs-lookup"><span data-stu-id="b738a-161">Select the **Show actions** option, and then select **Single line of text**.</span></span>

     ![Página Documentos em SharePoint mostrando as opções Mostrar ações com linha única de texto realçada.](../media/learning/learning-sharepoint-curation1.png)

3. <span data-ttu-id="b738a-163">No painel **Criar uma coluna,** no campo **Nome,** adicione um nome descritivo para a coluna.</span><span class="sxs-lookup"><span data-stu-id="b738a-163">On the **Create a column** panel, in the **Name** field, add a descriptive name for the column.</span></span> <span data-ttu-id="b738a-164">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b738a-164">Select **Save**.</span></span>

     ![Crie um painel de colunas em SharePoint mostrando o Nome e outros campos.](../media/learning/learning-sharepoint-curation2.png)
 
4. <span data-ttu-id="b738a-166">Na página **Documentos,** na coluna **Descrição,** adicione descrições personalizadas para cada item.</span><span class="sxs-lookup"><span data-stu-id="b738a-166">On the **Documents** page, in the **Description** column, add custom descriptions for each item.</span></span> <span data-ttu-id="b738a-167">Se nenhuma descrição for fornecida, o Viva Learning (Visualização) fornecerá uma mensagem padrão que realça o conteúdo como sendo de sua própria SharePoint biblioteca.</span><span class="sxs-lookup"><span data-stu-id="b738a-167">If no description is supplied, Viva Learning (Preview) will provide a default message that highlights the content as being from your own SharePoint library.</span></span> 

     ![Página Documentos em SharePoint mostrando as descrições na coluna Descrição.](../media/learning/learning-sharepoint-curation3.png)
 
### <a name="provide-your-own-organizations-content"></a><span data-ttu-id="b738a-169">Fornecer o conteúdo de sua própria organização</span><span class="sxs-lookup"><span data-stu-id="b738a-169">Provide your own organization's content</span></span>

<span data-ttu-id="b738a-170">Os administradores de conhecimento podem acessar o Repositório de Conteúdo de Aplicativos de Aprendizagem da sua organização em SharePoint, onde eles podem fornecer referências a bibliotecas de documentos entre organizações.</span><span class="sxs-lookup"><span data-stu-id="b738a-170">Knowledge admins can access their organization’s Learning App Content Repository in SharePoint, where they can provide references to cross-organization document libraries.</span></span> <span data-ttu-id="b738a-171">O conteúdo dentro dessas bibliotecas será então visualizado como conteúdo de aprendizagem no Viva Learning (Visualização).</span><span class="sxs-lookup"><span data-stu-id="b738a-171">Content within these libraries will be then surfaced as learning content in Viva Learning (Preview).</span></span>

1. <span data-ttu-id="b738a-172">No Viva Learning (Visualização), selecione **Mais opções** (**...**) e selecione **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="b738a-172">In Viva Learning (Preview), select **More options** (**...**), and then select **Settings**.</span></span>

     ![SharePoint página da biblioteca mostrando a opção Mais opções e Configurações.](../media/learning/learning-sharepoint-library-1.png)
     
2. <span data-ttu-id="b738a-174">Em **Configurações**, selecione **Permissões**.</span><span class="sxs-lookup"><span data-stu-id="b738a-174">Under **Settings**, select **Permissions**.</span></span>

     ![Configurações página de opção no SharePoint mostrando as opções Permissões e Verificar acesso.](../media/learning/learning-sharepoint-library-2.png)

3. <span data-ttu-id="b738a-176">Selecione **Verificar o acesso** para se conectar à biblioteca centralizada da sua organização.</span><span class="sxs-lookup"><span data-stu-id="b738a-176">Select **Check access** to connect to your organization’s centralized library.</span></span>
     
