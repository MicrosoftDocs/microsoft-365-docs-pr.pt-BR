---
title: Localize a experiência do usuário
description: Como localizar dispositivos para usuários
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 20456ce837be60b707569ae07d4fb00b695b3a98
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445919"
---
# <a name="localize-the-user-experience"></a><span data-ttu-id="40abf-104">Localize a experiência do usuário</span><span class="sxs-lookup"><span data-stu-id="40abf-104">Localize the user experience</span></span>

<span data-ttu-id="40abf-105">Os usuários de dispositivos da Área de Trabalho Gerenciada da Microsoft podem selecionar o idioma de sua escolha durante o processo de instalação (a "experiência fora da caixa") ou posteriormente.</span><span class="sxs-lookup"><span data-stu-id="40abf-105">Users of Microsoft Managed Desktop devices can select the language of their choice either during the setup process (the "out of box experience") or afterwards.</span></span>

## <a name="during-setup-the-out-of-box-experience"></a><span data-ttu-id="40abf-106">Durante a instalação (a "experiência fora da caixa")</span><span class="sxs-lookup"><span data-stu-id="40abf-106">During setup (the "out of box experience")</span></span>

<span data-ttu-id="40abf-107">Durante o processo de conclusão da instalação, os usuários podem selecionar o idioma de sua escolha.</span><span class="sxs-lookup"><span data-stu-id="40abf-107">During the process of completing setup, users can select the language of their choice.</span></span> <span data-ttu-id="40abf-108">Essa seleção afeta esses atributos:</span><span class="sxs-lookup"><span data-stu-id="40abf-108">This selection affects these attributes:</span></span>

- <span data-ttu-id="40abf-109">Recursos de idioma do Windows 10:</span><span class="sxs-lookup"><span data-stu-id="40abf-109">Windows 10 language features:</span></span>
    - <span data-ttu-id="40abf-110">Idioma de exibição</span><span class="sxs-lookup"><span data-stu-id="40abf-110">Display language</span></span>
    - <span data-ttu-id="40abf-111">Idioma do teclado</span><span class="sxs-lookup"><span data-stu-id="40abf-111">Keyboard language</span></span>
    - <span data-ttu-id="40abf-112">Recursos relacionados ao idioma sob demanda</span><span class="sxs-lookup"><span data-stu-id="40abf-112">Language-related Features on Demand</span></span>

- <span data-ttu-id="40abf-113">Recursos de idioma do Microsoft 365 Apps for Enterprise:</span><span class="sxs-lookup"><span data-stu-id="40abf-113">Microsoft 365 Apps for Enterprise language features:</span></span>
    - <span data-ttu-id="40abf-114">Idioma de exibição</span><span class="sxs-lookup"><span data-stu-id="40abf-114">Display language</span></span>
    - <span data-ttu-id="40abf-115">Revisa e ferramentas de autoria</span><span class="sxs-lookup"><span data-stu-id="40abf-115">Proofing and authoring tools</span></span>

> [!NOTE]
> <span data-ttu-id="40abf-116">Os usuários só podem obter recursos relacionados ao idioma sob demanda selecionando o idioma durante o processo de instalação.</span><span class="sxs-lookup"><span data-stu-id="40abf-116">Users can only get language-related Features On Demand by selecting the language during the setup process.</span></span>

## <a name="after-completing-setup"></a><span data-ttu-id="40abf-117">Depois de concluir a instalação</span><span class="sxs-lookup"><span data-stu-id="40abf-117">After completing setup</span></span>

<span data-ttu-id="40abf-118">Os usuários podem selecionar o idioma de sua escolha para o Windows 10 e o Microsoft 365 Apps para Empresas a qualquer momento após a conclusão do processo de instalação.</span><span class="sxs-lookup"><span data-stu-id="40abf-118">Users can select the language of their choice for Windows 10 and Microsoft 365 Apps for Enterprise anytime after the setup process is complete.</span></span> <span data-ttu-id="40abf-119">Especificamente:</span><span class="sxs-lookup"><span data-stu-id="40abf-119">Specifically:</span></span>

- <span data-ttu-id="40abf-120">Recursos de idioma do Windows 10:</span><span class="sxs-lookup"><span data-stu-id="40abf-120">Windows 10 language features:</span></span>
    - <span data-ttu-id="40abf-121">Idioma de exibição</span><span class="sxs-lookup"><span data-stu-id="40abf-121">Display language</span></span>
    - <span data-ttu-id="40abf-122">Idioma do teclado</span><span class="sxs-lookup"><span data-stu-id="40abf-122">Keyboard language</span></span>

- <span data-ttu-id="40abf-123">Recursos de idioma do Microsoft 365 Apps for Enterprise:</span><span class="sxs-lookup"><span data-stu-id="40abf-123">Microsoft 365 Apps for Enterprise language features:</span></span>
    - <span data-ttu-id="40abf-124">Idioma de exibição</span><span class="sxs-lookup"><span data-stu-id="40abf-124">Display language</span></span>
    - <span data-ttu-id="40abf-125">Revisa e ferramentas de autoria</span><span class="sxs-lookup"><span data-stu-id="40abf-125">Proofing and authoring tools</span></span>

<span data-ttu-id="40abf-126">Para disponibilizar os idiomas com suporte para o Microsoft 365 Apps for Enterprise para os usuários, adicione os usuários ao grupo Moderno **Workplace-Office-Language_Packs.** [](#supported-languages)</span><span class="sxs-lookup"><span data-stu-id="40abf-126">To make the [Supported languages](#supported-languages) for Microsoft 365 Apps for Enterprise available for your users to install, add the users to the **Modern Workplace-Office-Language_Packs** group.</span></span> <span data-ttu-id="40abf-127">Os idiomas estarão disponíveis no Portal da Empresa do Intune.</span><span class="sxs-lookup"><span data-stu-id="40abf-127">The languages will be available in the Intune Company Portal.</span></span>


## <a name="supported-languages"></a><span data-ttu-id="40abf-128">Idiomas compatíveis</span><span class="sxs-lookup"><span data-stu-id="40abf-128">Supported languages</span></span>

<span data-ttu-id="40abf-129">Para novos dispositivos, o fabricante deve fornecer imagens de dispositivo que incluam os idiomas necessários.</span><span class="sxs-lookup"><span data-stu-id="40abf-129">For new devices, your manufacturer must provide device images that include the languages you require.</span></span> <span data-ttu-id="40abf-130">Se a imagem do fabricante incluir idiomas diferentes daqueles fornecidos na lista de idiomas com suporte, ele ainda terá suporte do serviço.</span><span class="sxs-lookup"><span data-stu-id="40abf-130">If your manufacturer's image includes languages other than those provided in the supported languages list it is still supported by the service.</span></span>

<span data-ttu-id="40abf-131">Se você estiver reutilando dispositivos existentes, talvez seja necessário trabalhar com seu representante de conta da Microsoft para obter imagens apropriadas.</span><span class="sxs-lookup"><span data-stu-id="40abf-131">If you are reusing existing devices, you might need to work with your Microsoft account representative to obtain appropriate images.</span></span> <span data-ttu-id="40abf-132">Para obter mais informações, consulte [Imagens do dispositivo](../service-description/device-images.md).</span><span class="sxs-lookup"><span data-stu-id="40abf-132">For more information, see [Device images](../service-description/device-images.md).</span></span>

<span data-ttu-id="40abf-133">A [imagem universal](../service-description/device-images.md#universal-image) fornecida pela Área de Trabalho Gerenciada da Microsoft inclui esses idiomas e para o Windows 10:</span><span class="sxs-lookup"><span data-stu-id="40abf-133">The [universal image](../service-description/device-images.md#universal-image) provided by Microsoft Managed Desktop includes these languages and for Windows 10:</span></span>

- <span data-ttu-id="40abf-134">Inglês (US, GB, AU, CA, IN)</span><span class="sxs-lookup"><span data-stu-id="40abf-134">English (US, GB, AU, CA, IN)</span></span>
- <span data-ttu-id="40abf-135">Espanhol (Espanha, México)</span><span class="sxs-lookup"><span data-stu-id="40abf-135">Spanish (Spain, Mexico)</span></span>
- <span data-ttu-id="40abf-136">Japonês</span><span class="sxs-lookup"><span data-stu-id="40abf-136">Japanese</span></span>
- <span data-ttu-id="40abf-137">Francês (França, Canadá)</span><span class="sxs-lookup"><span data-stu-id="40abf-137">French (France, Canada)</span></span>
- <span data-ttu-id="40abf-138">Alemão</span><span class="sxs-lookup"><span data-stu-id="40abf-138">German</span></span>
- <span data-ttu-id="40abf-139">Português (Brasil)</span><span class="sxs-lookup"><span data-stu-id="40abf-139">Portuguese (Brazil)</span></span>
- <span data-ttu-id="40abf-140">Italiano</span><span class="sxs-lookup"><span data-stu-id="40abf-140">Italian</span></span>
- <span data-ttu-id="40abf-141">Chinese Simplified</span><span class="sxs-lookup"><span data-stu-id="40abf-141">Chinese Simplified</span></span>
- <span data-ttu-id="40abf-142">Holandês</span><span class="sxs-lookup"><span data-stu-id="40abf-142">Dutch</span></span>  
- <span data-ttu-id="40abf-143">Sueco</span><span class="sxs-lookup"><span data-stu-id="40abf-143">Swedish</span></span>
- <span data-ttu-id="40abf-144">Dinamarquês</span><span class="sxs-lookup"><span data-stu-id="40abf-144">Danish</span></span>  
- <span data-ttu-id="40abf-145">Finlandês</span><span class="sxs-lookup"><span data-stu-id="40abf-145">Finnish</span></span> 
- <span data-ttu-id="40abf-146">Russo</span><span class="sxs-lookup"><span data-stu-id="40abf-146">Russian</span></span> 
- <span data-ttu-id="40abf-147">Norueguês (Bokmål)</span><span class="sxs-lookup"><span data-stu-id="40abf-147">Norwegian (Bokmal)</span></span>
- <span data-ttu-id="40abf-148">Coreano</span><span class="sxs-lookup"><span data-stu-id="40abf-148">Korean</span></span>
- <span data-ttu-id="40abf-149">Chinese Traditional</span><span class="sxs-lookup"><span data-stu-id="40abf-149">Chinese Traditional</span></span>
- <span data-ttu-id="40abf-150">Polonês</span><span class="sxs-lookup"><span data-stu-id="40abf-150">Polish</span></span>
- <span data-ttu-id="40abf-151">Turco</span><span class="sxs-lookup"><span data-stu-id="40abf-151">Turkish</span></span>
- <span data-ttu-id="40abf-152">Árabe</span><span class="sxs-lookup"><span data-stu-id="40abf-152">Arabic</span></span>
- <span data-ttu-id="40abf-153">Hebraico</span><span class="sxs-lookup"><span data-stu-id="40abf-153">Hebrew</span></span>
- <span data-ttu-id="40abf-154">Português (Portugal)</span><span class="sxs-lookup"><span data-stu-id="40abf-154">Portuguese (Portugal)</span></span>
- <span data-ttu-id="40abf-155">Tcheco</span><span class="sxs-lookup"><span data-stu-id="40abf-155">Czech</span></span>
- <span data-ttu-id="40abf-156">Húngaro</span><span class="sxs-lookup"><span data-stu-id="40abf-156">Hungarian</span></span>
- <span data-ttu-id="40abf-157">Tailandês</span><span class="sxs-lookup"><span data-stu-id="40abf-157">Thai</span></span>
- <span data-ttu-id="40abf-158">Indonésio</span><span class="sxs-lookup"><span data-stu-id="40abf-158">Indonesian</span></span>
- <span data-ttu-id="40abf-159">Grego</span><span class="sxs-lookup"><span data-stu-id="40abf-159">Greek</span></span>
- <span data-ttu-id="40abf-160">Eslovaco</span><span class="sxs-lookup"><span data-stu-id="40abf-160">Slovak</span></span>
- <span data-ttu-id="40abf-161">Vietnamita</span><span class="sxs-lookup"><span data-stu-id="40abf-161">Vietnamese</span></span>
- <span data-ttu-id="40abf-162">Esloveno</span><span class="sxs-lookup"><span data-stu-id="40abf-162">Slovenian</span></span>
- <span data-ttu-id="40abf-163">Croata</span><span class="sxs-lookup"><span data-stu-id="40abf-163">Croatian</span></span>
- <span data-ttu-id="40abf-164">Romeno</span><span class="sxs-lookup"><span data-stu-id="40abf-164">Romanian</span></span>
- <span data-ttu-id="40abf-165">Lituano</span><span class="sxs-lookup"><span data-stu-id="40abf-165">Lithuanian</span></span>
- <span data-ttu-id="40abf-166">Búlgaro</span><span class="sxs-lookup"><span data-stu-id="40abf-166">Bulgarian</span></span>
- <span data-ttu-id="40abf-167">Sérvio (alfabeto latino)</span><span class="sxs-lookup"><span data-stu-id="40abf-167">Serbian (Latin alphabet)</span></span>
- <span data-ttu-id="40abf-168">Letão</span><span class="sxs-lookup"><span data-stu-id="40abf-168">Latvian</span></span>
- <span data-ttu-id="40abf-169">Ucraniano</span><span class="sxs-lookup"><span data-stu-id="40abf-169">Ukrainian</span></span>
- <span data-ttu-id="40abf-170">Estoniano</span><span class="sxs-lookup"><span data-stu-id="40abf-170">Estonian</span></span>

<span data-ttu-id="40abf-171">O Microsoft 365 Apps for Enterprise pode dar suporte a uma lista ligeiramente diferente.</span><span class="sxs-lookup"><span data-stu-id="40abf-171">Microsoft 365 Apps for Enterprise might support a slightly different list.</span></span>

<span data-ttu-id="40abf-172">Se os usuários precisarem de um idioma diferente dos listados aqui, arquivar uma solicitação de [suporte](../working-with-managed-desktop/admin-support.md) usando o [portal administrador](access-admin-portal.md).</span><span class="sxs-lookup"><span data-stu-id="40abf-172">If your users need a language other than the ones listed here, file a [support request](../working-with-managed-desktop/admin-support.md) by using the [Admin portal](access-admin-portal.md).</span></span>

## <a name="languages-for-support-and-operations"></a><span data-ttu-id="40abf-173">Idiomas para suporte e operações</span><span class="sxs-lookup"><span data-stu-id="40abf-173">Languages for support and operations</span></span>

### <a name="user-support"></a><span data-ttu-id="40abf-174">Suporte ao usuário</span><span class="sxs-lookup"><span data-stu-id="40abf-174">User support</span></span>
<span data-ttu-id="40abf-175">A Área de Trabalho Gerenciada da Microsoft oferece suporte somente em inglês.</span><span class="sxs-lookup"><span data-stu-id="40abf-175">Microsoft Managed Desktop provides support only in English.</span></span> <span data-ttu-id="40abf-176">Se os usuários escolherem outro idioma no aplicativo Obter Ajuda, eles receberão suporte dos canais de suporte gerais da Microsoft, em vez de suportar diretamente da Área de Trabalho Gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="40abf-176">If users choose another language in the Get Help app, they will get support from the general Microsoft support channels, rather than support directly from Microsoft Managed Desktop.</span></span> <span data-ttu-id="40abf-177">Para obter mais informações, consulte [Obter ajuda para usuários](../working-with-managed-desktop/end-user-support.md).</span><span class="sxs-lookup"><span data-stu-id="40abf-177">For more information, see [Getting help for users](../working-with-managed-desktop/end-user-support.md).</span></span>

<span data-ttu-id="40abf-178">Se os usuários precisarem de suporte em outros idiomas, você precisará fornecer isso por meio de fontes de suporte que não são da Microsoft ou de sua própria organização.</span><span class="sxs-lookup"><span data-stu-id="40abf-178">If your users need support in other languages, you'll have to provide that through non-Microsoft support sources or from your own organization.</span></span>

### <a name="admin-support-and-operations"></a><span data-ttu-id="40abf-179">Suporte e operações do administrador</span><span class="sxs-lookup"><span data-stu-id="40abf-179">Admin support and operations</span></span>
<span data-ttu-id="40abf-180">A Área de Trabalho Gerenciada da Microsoft fornece suporte ao administrador somente em inglês.</span><span class="sxs-lookup"><span data-stu-id="40abf-180">Microsoft Managed Desktop provides admin support only in English.</span></span> <span data-ttu-id="40abf-181">Isso inclui o portal de administração e todas as comunicações com as Operações de Área de Trabalho Gerenciadas da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="40abf-181">This includes the Admin portal and all communications with Microsoft Managed Desktop Operations.</span></span> <span data-ttu-id="40abf-182">Você deve presumir que todas as interações e interfaces relacionadas ao administrador estarão em inglês, a menos que especificado de outra forma.</span><span class="sxs-lookup"><span data-stu-id="40abf-182">You should assume that all admin-related interactions and interfaces will be in English, unless specified otherwise.</span></span>


