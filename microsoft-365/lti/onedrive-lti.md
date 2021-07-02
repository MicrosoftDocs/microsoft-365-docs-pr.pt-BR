---
title: Usar Microsoft OneDrive Learning interoperabilidade de ferramentas
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Crie e grade atribuições, crie e crie e crie conteúdo do curso e colabore em arquivos em tempo real com o novo aplicativo de interoperabilidade de ferramentas Microsoft OneDrive Learning ferramentas.
ms.openlocfilehash: 985a316bac689b9bc6c53ab65782d548fcad0db8
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256930"
---
# <a name="integrate-microsoft-onedrive-lti-with-canvas"></a><span data-ttu-id="fc1fe-103">Integrar Microsoft OneDrive LTI com Canvas</span><span class="sxs-lookup"><span data-stu-id="fc1fe-103">Integrate Microsoft OneDrive LTI with Canvas</span></span>

<span data-ttu-id="fc1fe-104">A integração Microsoft OneDrive LTI com o Canvas é um processo de duas etapas.</span><span class="sxs-lookup"><span data-stu-id="fc1fe-104">Integrating Microsoft OneDrive LTI with Canvas is a two step process.</span></span> <span data-ttu-id="fc1fe-105">A primeira etapa habilita Microsoft OneDrive em Canvas, e a segunda etapa disponibiliza o Microsoft OneDrive LTI nos cursos do Canvas.</span><span class="sxs-lookup"><span data-stu-id="fc1fe-105">The first step enables Microsoft OneDrive in Canvas, and the second step makes the Microsoft OneDrive LTI available within Canvas courses.</span></span>

## <a name="recommended-browser-settings"></a><span data-ttu-id="fc1fe-106">Configurações recomendadas do navegador</span><span class="sxs-lookup"><span data-stu-id="fc1fe-106">Recommended browser settings</span></span>

- <span data-ttu-id="fc1fe-107">Os cookies devem ser habilitados para Microsoft OneDrive.</span><span class="sxs-lookup"><span data-stu-id="fc1fe-107">Cookies should be enabled for Microsoft OneDrive.</span></span>
- <span data-ttu-id="fc1fe-108">Pop-ups não devem ser bloqueados para Microsoft OneDrive.</span><span class="sxs-lookup"><span data-stu-id="fc1fe-108">Popups should not be blocked for Microsoft OneDrive.</span></span>

> [!NOTE]
> - <span data-ttu-id="fc1fe-109">Os cookies não estão habilitados por padrão no modo de navegação anônima do Chrome e precisarão ser habilitados.</span><span class="sxs-lookup"><span data-stu-id="fc1fe-109">Cookies are not enabled by default in the Chrome browser incognito mode, and will need to be enabled.</span></span>
> - <span data-ttu-id="fc1fe-110">Microsoft OneDrive LTI funciona no modo privado no Microsoft Edge navegador.</span><span class="sxs-lookup"><span data-stu-id="fc1fe-110">Microsoft OneDrive LTI works in the private mode in Microsoft Edge browser.</span></span> <span data-ttu-id="fc1fe-111">Verifique se você não bloqueou cookies (que estão habilitados por padrão).</span><span class="sxs-lookup"><span data-stu-id="fc1fe-111">Ensure that you have not blocked cookies (which are enabled by default).</span></span>

## <a name="enable-microsoft-onedrive-lti-in-canvas"></a><span data-ttu-id="fc1fe-112">Habilitar Microsoft OneDrive LTI no Canvas</span><span class="sxs-lookup"><span data-stu-id="fc1fe-112">Enable Microsoft OneDrive LTI in Canvas</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fc1fe-113">A pessoa que executa essa integração deve ser um administrador do Canvas e um administrador do Microsoft 365 locatário.</span><span class="sxs-lookup"><span data-stu-id="fc1fe-113">The person who performs this integration should be an administrator of Canvas and an administrator of the Microsoft 365 tenant.</span></span>

1. <span data-ttu-id="fc1fe-114">Entre no portal de <a href="https://onedrivelti.microsoft.com/admin" target="_blank">registro Microsoft OneDrive LTI</a></span><span class="sxs-lookup"><span data-stu-id="fc1fe-114">Sign into the <a href="https://onedrivelti.microsoft.com/admin" target="_blank">Microsoft OneDrive LTI Registration Portal</a></span></span>
1. <span data-ttu-id="fc1fe-115">Selecione o **botão Consentimento do** Administrador e aceite as permissões.</span><span class="sxs-lookup"><span data-stu-id="fc1fe-115">Select the **Admin Consent** button and accept the permissions.</span></span>
1. <span data-ttu-id="fc1fe-116">Selecione o **botão Criar novo Locatário LTI.**</span><span class="sxs-lookup"><span data-stu-id="fc1fe-116">Select the **Create new LTI Tenant** button.</span></span> <span data-ttu-id="fc1fe-117">Na página Registro LTI, selecione **Tela** no menu suspenso e insira a URL base da sua instância do Canvas.</span><span class="sxs-lookup"><span data-stu-id="fc1fe-117">On the LTI Registration page select **Canvas** in the dropdown and enter the base URL of your Canvas instance.</span></span>

> [!NOTE]
> <span data-ttu-id="fc1fe-118">Se sua instância do Canvas for, por exemplo, https://contoso.test.instructure.com ]( https://contoso.test.instructure.com) , a URL completa deverá ser inserida.</span><span class="sxs-lookup"><span data-stu-id="fc1fe-118">If your Canvas instance is, for example, https://contoso.test.instructure.com](https://contoso.test.instructure.com), then the complete URL should be entered.</span></span>

:::image type="content" source="media/OneDrive-LTI-07.png" alt-text="A página de administração do locatário LTI, com um campo suspenso para escolher a plataforma de consumidor LTI e um campo de texto de URL.":::

4. <span data-ttu-id="fc1fe-120">Copie o JSON selecionando o botão **Copiar** (um ícone à direita que mostra duas páginas uma sobre a outra).</span><span class="sxs-lookup"><span data-stu-id="fc1fe-120">Copy the JSON by selecting the **Copy** button (an icon on the right that shows two pages on top of one another).</span></span> <span data-ttu-id="fc1fe-121">Isso será usado para gerar a chave no Canvas.</span><span class="sxs-lookup"><span data-stu-id="fc1fe-121">This will be used to generate the key in Canvas.</span></span>

:::image type="content" source="media/OneDrive-LTI-08.png" alt-text="Uma imagem mostrando o botão de cópia que copiará o texto JSON exibido e o disponibiliza para geração de chaves no Canvas.":::

5. <span data-ttu-id="fc1fe-123">Entre em sua instância do Canvas como administrador e selecione **Chaves** do Desenvolvedor no menu no lado esquerdo da página.</span><span class="sxs-lookup"><span data-stu-id="fc1fe-123">Sign into your Canvas instance as the administrator and select **Developer Keys** from the menu on the left side of the page.</span></span> <span data-ttu-id="fc1fe-124">No menu suspenso, crie uma chave de desenvolvedor escolhendo **a tecla LTI** na listada no canto superior direito da página.</span><span class="sxs-lookup"><span data-stu-id="fc1fe-124">From the dropdown, create a developer key by choosing **LTI Key** from the dropdown on the upper right of the page.</span></span>

:::image type="content" source="media/OneDrive-LTI-14.png" alt-text="Uma captura de tela mostrando a barra de navegação à esquerda com chaves do desenvolvedor selecionadas e a entrada da chave LTI selecionada em uma lista listada à direita da página.":::

6. <span data-ttu-id="fc1fe-126">Na página Configurar, no **menu** suspenso Método, selecione Colar **JSON** como o método e colar o texto JSON que você copiou na Etapa 5 no campo de texto que aparece.</span><span class="sxs-lookup"><span data-stu-id="fc1fe-126">On the Configure page, in the **Method** dropdown, select **Paste JSON** as the method and paste the JSON text you copied in Step 5 in the text field that appears.</span></span>
7. <span data-ttu-id="fc1fe-127">Salve a chave e ela se tornará disponível no Canvas em um **estado** Off.</span><span class="sxs-lookup"><span data-stu-id="fc1fe-127">Save the key, and it becomes available in Canvas in an **Off** state.</span></span> <span data-ttu-id="fc1fe-128">A tecla **Ligar e** copiar a chave dada na coluna **Detalhes** a ser usada na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="fc1fe-128">Turn the key **On** and copy the key given in the **Details** column to be used in the next step.</span></span>

:::image type="content" source="media/OneDrive-LTI-19.png" alt-text="A página Canvas com a chave definida em um estado off. Ele precisará ser ligado e a chave precisará ser copiada da coluna de detalhes nesta página.":::

8. <span data-ttu-id="fc1fe-130">Retorne ao portal Microsoft OneDrive registro LTI e colar a chave no campo **ID do Cliente canvas.**</span><span class="sxs-lookup"><span data-stu-id="fc1fe-130">Return to the Microsoft OneDrive LTI Registration portal and paste the key in the **Canvas Client ID** field.</span></span> <span data-ttu-id="fc1fe-131">Selecione **Próximo** quando estiver pronto.</span><span class="sxs-lookup"><span data-stu-id="fc1fe-131">Select **Next** when you're ready.</span></span>

:::image type="content" source="media/OneDrive-LTI-20.png" alt-text="A página de registro do locatário LTI, que mostra o texto JSON e a caixa de texto na qual a chave deve ser copiada.":::

9. <span data-ttu-id="fc1fe-133">Revise e salve suas alterações.</span><span class="sxs-lookup"><span data-stu-id="fc1fe-133">Review and save your changes.</span></span> <span data-ttu-id="fc1fe-134">Uma mensagem será exibida no registro bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="fc1fe-134">A message will be displayed on successful registration.</span></span>
10. <span data-ttu-id="fc1fe-135">Os detalhes do registro também podem ser revisados selecionando o botão **Exibir Locatários LTI** na home page.</span><span class="sxs-lookup"><span data-stu-id="fc1fe-135">Your registration details can also be reviewed by selecting the **View LTI Tenants** button on the home page.</span></span>

## <a name="enable-microsoft-onedrive-lti-in-canvas-courses"></a><span data-ttu-id="fc1fe-136">Habilitar Microsoft OneDrive LTI em Cursos de Tela</span><span class="sxs-lookup"><span data-stu-id="fc1fe-136">Enable Microsoft OneDrive LTI in Canvas Courses</span></span>

<span data-ttu-id="fc1fe-137">Um administrador do Canvas pode habilitar Microsoft OneDrive LTI para todos os cursos.</span><span class="sxs-lookup"><span data-stu-id="fc1fe-137">A Canvas administrator can enable Microsoft OneDrive LTI for all courses.</span></span> <span data-ttu-id="fc1fe-138">Se Microsoft OneDrive LTI for necessário em um curso específico (e não todos os cursos), o educador do curso precisará seguir as mesmas etapas dentro das configurações do curso.</span><span class="sxs-lookup"><span data-stu-id="fc1fe-138">If Microsoft OneDrive LTI is needed in a specific course (and not all courses), the course educator needs to follow the same steps within the course settings.</span></span>

1. <span data-ttu-id="fc1fe-139">Entre como administrador e vá para **a** seção Configurações.</span><span class="sxs-lookup"><span data-stu-id="fc1fe-139">Sign in as an administrator and go to the **Settings** section.</span></span>
2. <span data-ttu-id="fc1fe-140">Vá até a **seção Aplicativos** e selecione o botão **Exibir Configurações do** Aplicativo.</span><span class="sxs-lookup"><span data-stu-id="fc1fe-140">Go to the **Apps** section and select the **View App Configurations** button.</span></span>
3. <span data-ttu-id="fc1fe-141">Selecione o **botão Adicionar Aplicativo.**</span><span class="sxs-lookup"><span data-stu-id="fc1fe-141">Select the **Add App** button.</span></span>
4. <span data-ttu-id="fc1fe-142">Na lista **suspenso Tipo de** Configuração, escolha a opção Por **ID do** Cliente.</span><span class="sxs-lookup"><span data-stu-id="fc1fe-142">In the **Configuration Type** dropdown, choose the **By Client ID** option.</span></span>
5. <span data-ttu-id="fc1fe-143">Colar o valor da chave de desenvolvedor gerada anteriormente no campo **ID do** Cliente e selecione o **botão Enviar.**</span><span class="sxs-lookup"><span data-stu-id="fc1fe-143">Paste the value of the developer key generated previously in the **Client ID** field, and select the **Submit** button.</span></span>

:::image type="content" source="media/OneDrive-LTI-31.png" alt-text="A página adicionar aplicativo, mostrando a opção Por ID do cliente no menu suspenso Tipo de configuração.":::

## <a name="collaboration-settings-for-microsoft-onedrive-lti-in-canvas-courses"></a><span data-ttu-id="fc1fe-145">Colaboração Configurações para Microsoft OneDrive LTI em Cursos de Tela</span><span class="sxs-lookup"><span data-stu-id="fc1fe-145">Collaboration Settings for Microsoft OneDrive LTI in Canvas Courses</span></span>

> [!NOTE]
> <span data-ttu-id="fc1fe-146">Para que a colaboração funcione para educadores e alunos, você não deve habilitar a configuração de colaboração.</span><span class="sxs-lookup"><span data-stu-id="fc1fe-146">For collaboration to work for educators and students, you shouldn't enable the collaboration setting.</span></span> <span data-ttu-id="fc1fe-147">Para garantir que a configuração não está habilitada, siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="fc1fe-147">To make sure the setting isn't enabled, follow the steps below.</span></span>

1. <span data-ttu-id="fc1fe-148">Entre como administrador e vá para **a** seção Configurações.</span><span class="sxs-lookup"><span data-stu-id="fc1fe-148">Sign in as an admin and go to the **Settings** section.</span></span>
1. <span data-ttu-id="fc1fe-149">Vá para **a seção Opções de** Recursos e vá para a seção **Curso.**</span><span class="sxs-lookup"><span data-stu-id="fc1fe-149">Go to **Feature Options** section, and then go to the **Course** section.</span></span>
1. <span data-ttu-id="fc1fe-150">De definir o recurso Ferramenta de Colaborações **Externas** para não estar habilitado.</span><span class="sxs-lookup"><span data-stu-id="fc1fe-150">Set the **External Collaborations Tool** feature to be not enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="fc1fe-151">A colaboração pode ser atribuída a alunos individuais e a grupos de alunos.</span><span class="sxs-lookup"><span data-stu-id="fc1fe-151">Collaboration can be assigned to individual students and to groups of students.</span></span> <span data-ttu-id="fc1fe-152">A atribuição a alunos individuais funciona por padrão.</span><span class="sxs-lookup"><span data-stu-id="fc1fe-152">Assigning to individual students works by default.</span></span> <span data-ttu-id="fc1fe-153">Para poder atribuir colaboração ao grupo de alunos, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="fc1fe-153">To be able to assign collaboration to group of students, follow these steps:</span></span>

1. <span data-ttu-id="fc1fe-154">Faça logon como administrador e vá para a seção **Chaves do** Desenvolvedor.</span><span class="sxs-lookup"><span data-stu-id="fc1fe-154">Login as admin and go to the **Developer Keys** section.</span></span>
1. <span data-ttu-id="fc1fe-155">Encontre a chave com o valor 17000000000710 e de defini-la como **On**.</span><span class="sxs-lookup"><span data-stu-id="fc1fe-155">Find the key with value 170000000000710 and set it to **On**.</span></span>
