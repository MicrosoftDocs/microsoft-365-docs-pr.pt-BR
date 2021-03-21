---
title: Como o conteúdo é identificado para recomendações de governança de dados
f1.keywords:
- NOCSH
ms.author: brendonb
author: cabailey
manager: laurawi
ms.date: 1/15/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: O Centro de segurança e o centro de conformidade do Microsoft 365 oferecem recomendações para governança de dados com base na configuração atual da sua organização e permite configurar com apenas alguns cliques. Algumas dessas recomendações detectam conteúdo específico em sua organização e, em seguida, fornecem etapas recomendadas para gerenciar esse conteúdo. Por exemplo, uma recomendação pode detectar itens que contenham conteúdo essencial para os negócios (como privilégio advogado-cliente ou informações do NDA) e permitir que você aplique automaticamente um rótulo de retenção a esses itens para garantir que eles sejam classificados e retidos conforme necessário. Este tópico lista as recomendações de controle de dados que você pode ver e descreve qual conteúdo é detectado para acionar cada um deles.
ms.openlocfilehash: 9a022369fb783a498971c91664fa6532472d8589
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922605"
---
# <a name="how-content-is-identified-for-data-governance-recommendations"></a><span data-ttu-id="22562-106">Como o conteúdo é identificado para recomendações de governança de dados</span><span class="sxs-lookup"><span data-stu-id="22562-106">How content is identified for data-governance recommendations</span></span>

<span data-ttu-id="22562-p102">O Centro de Segurança e de Conformidade do Microsoft 365 fornece recomendações para governança de dados com base na configuração atual da sua organização e permite que você configure as coisas com apenas alguns cliques. Algumas dessas recomendações detectam conteúdo específico em sua organização e, em seguida, fornecem etapas recomendadas para gerenciar esse conteúdo. Por exemplo, uma recomendação pode detectar itens que contenham conteúdo essencial para os negócios (como privilégio advogado-cliente ou informações do NDA) e permitir que você aplique automaticamente um rótulo de retenção a esses itens para garantir que eles sejam classificados e retidos conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="22562-p102">The Microsoft 365 security center and Microsoft 365 compliance center provide recommendations for data governance based on your org's current setup and lets you set things up in a couple clicks. Some of these recommendations detect specific content in your organization and then provide recommended steps for managing that content. For example, a recommendation might detect items that contain business-critical content (such as attorney-client privilege or NDA info), and then let you automatically apply a retention label to those items to ensure that they're classified and retained as needed.</span></span>

<span data-ttu-id="22562-110">Este tópico lista as recomendações de controle de dados que você pode ver e descreve qual conteúdo é detectado para acionar cada um deles.</span><span class="sxs-lookup"><span data-stu-id="22562-110">This topic lists the data-governance recommendations you might see and describes what content is detected to trigger each one.</span></span>

## <a name="clean-up-voicemail"></a><span data-ttu-id="22562-111">Limpar a caixa postal</span><span class="sxs-lookup"><span data-stu-id="22562-111">Clean up voicemail</span></span>

<span data-ttu-id="22562-p103">Essa recomendação é exibida quando as mensagens de e-mail identificadas como o tipo de mensagem "correio de voz" são detectadas nas caixas de correio dos usuários. Saiba mais sobre em [propriedades de mensagem do Exchange](/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange).</span><span class="sxs-lookup"><span data-stu-id="22562-p103">This recommendation appears when email messages identified as the message type 'voicemail' are detected in users' mailboxes. Learn more about [message properties in Exchange](/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange).</span></span>

## <a name="label-attorney-client-privilege-content"></a><span data-ttu-id="22562-114">Etiquetar conteúdo de privilégio advogado-cliente</span><span class="sxs-lookup"><span data-stu-id="22562-114">Label attorney-client privilege content</span></span> 

<span data-ttu-id="22562-115">Esta recomendação é exibida quando os seguintes critérios são atendidos.</span><span class="sxs-lookup"><span data-stu-id="22562-115">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="22562-116">Qualquer combinação dessas palavras-chave for detectada no corpo da mensagem de email:</span><span class="sxs-lookup"><span data-stu-id="22562-116">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="22562-117">ACP</span><span class="sxs-lookup"><span data-stu-id="22562-117">ACP</span></span>
    - <span data-ttu-id="22562-118">Privilégio advogado cliente</span><span class="sxs-lookup"><span data-stu-id="22562-118">Attorney Client Privilege</span></span>
    - <span data-ttu-id="22562-119">Privilégio advogado-cliente</span><span class="sxs-lookup"><span data-stu-id="22562-119">Attorney-Client Privilege</span></span>
    - <span data-ttu-id="22562-120">Advogado-cliente privilegiados</span><span class="sxs-lookup"><span data-stu-id="22562-120">Attorney-Client Privileged</span></span>

- <span data-ttu-id="22562-121">Qualquer combinação dessas palavras-chave é detectada em arquivos do SharePoint ou no OneDrive:</span><span class="sxs-lookup"><span data-stu-id="22562-121">Any combination of these keywords are detected in SharePoint or OneDrive files:</span></span>
    - <span data-ttu-id="22562-122">ACP</span><span class="sxs-lookup"><span data-stu-id="22562-122">ACP</span></span>
    - <span data-ttu-id="22562-123">Advogado cliente privilégio \*</span><span class="sxs-lookup"><span data-stu-id="22562-123">Attorney Client Privilege\*</span></span>
    - <span data-ttu-id="22562-124">Privilégio AC</span><span class="sxs-lookup"><span data-stu-id="22562-124">AC Privilege</span></span>

## <a name="retain-audio-files"></a><span data-ttu-id="22562-125">Manter os arquivos de áudio</span><span class="sxs-lookup"><span data-stu-id="22562-125">Retain audio files</span></span>

<span data-ttu-id="22562-126">Esta recomendação é exibida quando qualquer um dos seguintes tipos de arquivo é detectado no SharePoint ou OneDrive.</span><span class="sxs-lookup"><span data-stu-id="22562-126">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="22562-127">.MP3</span><span class="sxs-lookup"><span data-stu-id="22562-127">.MP3</span></span>
- <span data-ttu-id="22562-128">.WMA</span><span class="sxs-lookup"><span data-stu-id="22562-128">.WMA</span></span>
- <span data-ttu-id="22562-129">.WAV</span><span class="sxs-lookup"><span data-stu-id="22562-129">.WAV</span></span>
- <span data-ttu-id="22562-130">.RA</span><span class="sxs-lookup"><span data-stu-id="22562-130">.RA</span></span>
- <span data-ttu-id="22562-131">.RAM</span><span class="sxs-lookup"><span data-stu-id="22562-131">.RAM</span></span>
- <span data-ttu-id="22562-132">.RM</span><span class="sxs-lookup"><span data-stu-id="22562-132">.RM</span></span>
- <span data-ttu-id="22562-133">.MID</span><span class="sxs-lookup"><span data-stu-id="22562-133">.MID</span></span>
- <span data-ttu-id="22562-134">.OGG</span><span class="sxs-lookup"><span data-stu-id="22562-134">.OGG</span></span>
- <span data-ttu-id="22562-135">.AIFF</span><span class="sxs-lookup"><span data-stu-id="22562-135">.AIFF</span></span>
- <span data-ttu-id="22562-136">.PCM</span><span class="sxs-lookup"><span data-stu-id="22562-136">.PCM</span></span>
- <span data-ttu-id="22562-137">.AAC</span><span class="sxs-lookup"><span data-stu-id="22562-137">.AAC</span></span>
- <span data-ttu-id="22562-138">.FLAC</span><span class="sxs-lookup"><span data-stu-id="22562-138">.FLAC</span></span>
- <span data-ttu-id="22562-139">.ALAC</span><span class="sxs-lookup"><span data-stu-id="22562-139">.ALAC</span></span>

## <a name="retain-cad-files"></a><span data-ttu-id="22562-140">Manter os arquivos do CAD</span><span class="sxs-lookup"><span data-stu-id="22562-140">Retain CAD files</span></span>

<span data-ttu-id="22562-141">Esta recomendação é exibida quando qualquer um dos seguintes tipos de arquivo é detectado no SharePoint ou OneDrive.</span><span class="sxs-lookup"><span data-stu-id="22562-141">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="22562-142">.3DXML</span><span class="sxs-lookup"><span data-stu-id="22562-142">.3DXML</span></span>
- <span data-ttu-id="22562-143">.ACIS</span><span class="sxs-lookup"><span data-stu-id="22562-143">.ACIS</span></span>
- <span data-ttu-id="22562-144">.ARC</span><span class="sxs-lookup"><span data-stu-id="22562-144">.ARC</span></span>
- <span data-ttu-id="22562-145">.ASM</span><span class="sxs-lookup"><span data-stu-id="22562-145">.ASM</span></span>
- <span data-ttu-id="22562-146">.CAT\*</span><span class="sxs-lookup"><span data-stu-id="22562-146">.CAT\*</span></span>
- <span data-ttu-id="22562-147">.CGR</span><span class="sxs-lookup"><span data-stu-id="22562-147">.CGR</span></span>
- <span data-ttu-id="22562-148">.DW</span><span class="sxs-lookup"><span data-stu-id="22562-148">.DW\*</span></span>
- <span data-ttu-id="22562-149">.DX</span><span class="sxs-lookup"><span data-stu-id="22562-149">.DX\*</span></span>
- <span data-ttu-id="22562-150">.EDRW</span><span class="sxs-lookup"><span data-stu-id="22562-150">.EDRW</span></span>
- <span data-ttu-id="22562-151">.IAM</span><span class="sxs-lookup"><span data-stu-id="22562-151">.IAM</span></span>
- <span data-ttu-id="22562-152">.IGES</span><span class="sxs-lookup"><span data-stu-id="22562-152">.IGES</span></span>
- <span data-ttu-id="22562-153">.IGS</span><span class="sxs-lookup"><span data-stu-id="22562-153">.IGS</span></span>
- <span data-ttu-id="22562-154">.IPT</span><span class="sxs-lookup"><span data-stu-id="22562-154">.IPT</span></span>
- <span data-ttu-id="22562-155">.JT</span><span class="sxs-lookup"><span data-stu-id="22562-155">.JT</span></span>
- <span data-ttu-id="22562-156">.MF1</span><span class="sxs-lookup"><span data-stu-id="22562-156">.MF1</span></span>
- <span data-ttu-id="22562-157">.NEU</span><span class="sxs-lookup"><span data-stu-id="22562-157">.NEU</span></span>
- <span data-ttu-id="22562-158">.NOMINAL</span><span class="sxs-lookup"><span data-stu-id="22562-158">.PAR</span></span>
- <span data-ttu-id="22562-159">.PKG</span><span class="sxs-lookup"><span data-stu-id="22562-159">.PKG</span></span>
- <span data-ttu-id="22562-160">.PRC</span><span class="sxs-lookup"><span data-stu-id="22562-160">.PRC</span></span>
- <span data-ttu-id="22562-161">.PRT</span><span class="sxs-lookup"><span data-stu-id="22562-161">.PRT</span></span>
- <span data-ttu-id="22562-162">.PSM</span><span class="sxs-lookup"><span data-stu-id="22562-162">.PSM</span></span>
- <span data-ttu-id="22562-163">.PWD</span><span class="sxs-lookup"><span data-stu-id="22562-163">.PWD</span></span>
- <span data-ttu-id="22562-164">.SLD\*</span><span class="sxs-lookup"><span data-stu-id="22562-164">.SLD\*</span></span>
- <span data-ttu-id="22562-165">.STEP</span><span class="sxs-lookup"><span data-stu-id="22562-165">.STEP</span></span>
- <span data-ttu-id="22562-166">.STL</span><span class="sxs-lookup"><span data-stu-id="22562-166">.STL</span></span>
- <span data-ttu-id="22562-167">.STP</span><span class="sxs-lookup"><span data-stu-id="22562-167">.STP</span></span>
- <span data-ttu-id="22562-168">.U3D</span><span class="sxs-lookup"><span data-stu-id="22562-168">.U3D</span></span>
- <span data-ttu-id="22562-169">.UNV</span><span class="sxs-lookup"><span data-stu-id="22562-169">.UNV</span></span>
- <span data-ttu-id="22562-170">.VRML</span><span class="sxs-lookup"><span data-stu-id="22562-170">.VRML</span></span>
- <span data-ttu-id="22562-171">.WRL</span><span class="sxs-lookup"><span data-stu-id="22562-171">.WRL</span></span>
- <span data-ttu-id="22562-172">.X_\*</span><span class="sxs-lookup"><span data-stu-id="22562-172">.X_\*</span></span>
- <span data-ttu-id="22562-173">.XAS</span><span class="sxs-lookup"><span data-stu-id="22562-173">.XAS</span></span>
- <span data-ttu-id="22562-174">.XMT\*</span><span class="sxs-lookup"><span data-stu-id="22562-174">.XMT\*</span></span>
- <span data-ttu-id="22562-175">.XPR</span><span class="sxs-lookup"><span data-stu-id="22562-175">.XPR</span></span>

## <a name="retain-image-files"></a><span data-ttu-id="22562-176">Manter os arquivos de imagem</span><span class="sxs-lookup"><span data-stu-id="22562-176">Retain image files</span></span>

<span data-ttu-id="22562-177">Esta recomendação é exibida quando qualquer um dos seguintes tipos de arquivo é detectado no SharePoint ou OneDrive.</span><span class="sxs-lookup"><span data-stu-id="22562-177">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="22562-178">.JPEG</span><span class="sxs-lookup"><span data-stu-id="22562-178">.JPEG</span></span>
- <span data-ttu-id="22562-179">.GIF</span><span class="sxs-lookup"><span data-stu-id="22562-179">.GIF</span></span>
- <span data-ttu-id="22562-180">.TIF\*</span><span class="sxs-lookup"><span data-stu-id="22562-180">.TIF\*</span></span>
- <span data-ttu-id="22562-181">.BMP</span><span class="sxs-lookup"><span data-stu-id="22562-181">.BMP</span></span>
- <span data-ttu-id="22562-182">.PNG</span><span class="sxs-lookup"><span data-stu-id="22562-182">.PNG</span></span>
- <span data-ttu-id="22562-183">.RAW</span><span class="sxs-lookup"><span data-stu-id="22562-183">.RAW</span></span>
- <span data-ttu-id="22562-184">.PSD</span><span class="sxs-lookup"><span data-stu-id="22562-184">.PSD</span></span>
- <span data-ttu-id="22562-185">.PSP</span><span class="sxs-lookup"><span data-stu-id="22562-185">.PSP</span></span>
- <span data-ttu-id="22562-186">.JPG</span><span class="sxs-lookup"><span data-stu-id="22562-186">.JPG</span></span>
- <span data-ttu-id="22562-187">.EXIF</span><span class="sxs-lookup"><span data-stu-id="22562-187">.EXIF</span></span>
- <span data-ttu-id="22562-188">.PPM</span><span class="sxs-lookup"><span data-stu-id="22562-188">.PPM</span></span>
- <span data-ttu-id="22562-189">.PGM</span><span class="sxs-lookup"><span data-stu-id="22562-189">.PGM</span></span>
- <span data-ttu-id="22562-190">.PBM</span><span class="sxs-lookup"><span data-stu-id="22562-190">.PBM</span></span>
- <span data-ttu-id="22562-191">.PNM</span><span class="sxs-lookup"><span data-stu-id="22562-191">.PNM</span></span>
- <span data-ttu-id="22562-192">.WEBP</span><span class="sxs-lookup"><span data-stu-id="22562-192">.WEBP</span></span>

## <a name="retain-nda-content"></a><span data-ttu-id="22562-193">Reter o conteúdo NDA</span><span class="sxs-lookup"><span data-stu-id="22562-193">Retain NDA content</span></span> 

<span data-ttu-id="22562-194">Esta recomendação é exibida quando os seguintes critérios são atendidos.</span><span class="sxs-lookup"><span data-stu-id="22562-194">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="22562-195">Qualquer combinação dessas palavras-chave for detectada no corpo da mensagem de email:</span><span class="sxs-lookup"><span data-stu-id="22562-195">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="22562-196">NDA</span><span class="sxs-lookup"><span data-stu-id="22562-196">NDA</span></span>
    - <span data-ttu-id="22562-197">"Contrato de confidencialidade"</span><span class="sxs-lookup"><span data-stu-id="22562-197">"Non-Disclosure Agreement"</span></span>
    - <span data-ttu-id="22562-198">"Contrato de confidencialidade"</span><span class="sxs-lookup"><span data-stu-id="22562-198">"Non Disclosure Agreement"</span></span>

- <span data-ttu-id="22562-199">Qualquer combinação dessas palavras-chave é detectada em arquivos .PDF ou .DOC no SharePoint ou no OneDrive:</span><span class="sxs-lookup"><span data-stu-id="22562-199">Any combination of these keywords are detected in .PDF or .DOC files in SharePoint or OneDrive:</span></span>
    - <span data-ttu-id="22562-200">NDA</span><span class="sxs-lookup"><span data-stu-id="22562-200">NDA</span></span>
    - <span data-ttu-id="22562-201">Contrato de não divulgação</span><span class="sxs-lookup"><span data-stu-id="22562-201">Non Disclosure Agreement</span></span>

## <a name="retain-software-development-files"></a><span data-ttu-id="22562-202">Manter os arquivos de desenvolvimento de software</span><span class="sxs-lookup"><span data-stu-id="22562-202">Retain software development files</span></span>

<span data-ttu-id="22562-203">Esta recomendação é exibida quando qualquer um dos seguintes tipos de arquivo é detectado no SharePoint ou OneDrive.</span><span class="sxs-lookup"><span data-stu-id="22562-203">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="22562-204">.ASAX</span><span class="sxs-lookup"><span data-stu-id="22562-204">.ASAX</span></span>
- <span data-ttu-id="22562-205">.ASM</span><span class="sxs-lookup"><span data-stu-id="22562-205">.ASM</span></span>
- <span data-ttu-id="22562-206">.ASP\*</span><span class="sxs-lookup"><span data-stu-id="22562-206">.ASP\*</span></span>
- <span data-ttu-id="22562-207">.BAT</span><span class="sxs-lookup"><span data-stu-id="22562-207">.BAT</span></span>
- <span data-ttu-id="22562-208">.CONFIG</span><span class="sxs-lookup"><span data-stu-id="22562-208">.CONFIG</span></span>
- <span data-ttu-id="22562-209">.CS</span><span class="sxs-lookup"><span data-stu-id="22562-209">.CS</span></span>
- <span data-ttu-id="22562-210">.CSS</span><span class="sxs-lookup"><span data-stu-id="22562-210">.CSS</span></span>
- <span data-ttu-id="22562-211">.DISCO</span><span class="sxs-lookup"><span data-stu-id="22562-211">.DISCO</span></span>
- <span data-ttu-id="22562-212">.HTM\*</span><span class="sxs-lookup"><span data-stu-id="22562-212">.HTM\*</span></span>
- <span data-ttu-id="22562-213">.INC</span><span class="sxs-lookup"><span data-stu-id="22562-213">.INC</span></span>
- <span data-ttu-id="22562-214">.JAD</span><span class="sxs-lookup"><span data-stu-id="22562-214">.JAD</span></span>
- <span data-ttu-id="22562-215">.JAVA</span><span class="sxs-lookup"><span data-stu-id="22562-215">.JAVA</span></span>
- <span data-ttu-id="22562-216">.JS\*</span><span class="sxs-lookup"><span data-stu-id="22562-216">.JS\*</span></span>
- <span data-ttu-id="22562-217">.LIB</span><span class="sxs-lookup"><span data-stu-id="22562-217">.LIB</span></span>
- <span data-ttu-id="22562-218">.O</span><span class="sxs-lookup"><span data-stu-id="22562-218">.O</span></span>
- <span data-ttu-id="22562-219">.PHP</span><span class="sxs-lookup"><span data-stu-id="22562-219">.PHP</span></span>
- <span data-ttu-id="22562-220">.RC</span><span class="sxs-lookup"><span data-stu-id="22562-220">.RC</span></span>
- <span data-ttu-id="22562-221">.RESX</span><span class="sxs-lookup"><span data-stu-id="22562-221">.RESX</span></span>
- <span data-ttu-id="22562-222">.RPT</span><span class="sxs-lookup"><span data-stu-id="22562-222">.RPT</span></span>
- <span data-ttu-id="22562-223">.RSS</span><span class="sxs-lookup"><span data-stu-id="22562-223">.RSS</span></span>
- <span data-ttu-id="22562-224">.SCPT</span><span class="sxs-lookup"><span data-stu-id="22562-224">.SCPT</span></span>
- <span data-ttu-id="22562-225">.SRC</span><span class="sxs-lookup"><span data-stu-id="22562-225">.SRC</span></span>
- <span data-ttu-id="22562-226">.VB\*</span><span class="sxs-lookup"><span data-stu-id="22562-226">.VB\*</span></span>
- <span data-ttu-id="22562-227">.WSF</span><span class="sxs-lookup"><span data-stu-id="22562-227">.WSF</span></span>
- <span data-ttu-id="22562-228">. XCODEPROJ</span><span class="sxs-lookup"><span data-stu-id="22562-228">.XCODEPROJ</span></span>
- <span data-ttu-id="22562-229">.XML</span><span class="sxs-lookup"><span data-stu-id="22562-229">.XML</span></span>
- <span data-ttu-id="22562-230">.XSD</span><span class="sxs-lookup"><span data-stu-id="22562-230">.XSD</span></span>
- <span data-ttu-id="22562-231">.XSL\*</span><span class="sxs-lookup"><span data-stu-id="22562-231">.XSL\*</span></span>

## <a name="retain-video-files"></a><span data-ttu-id="22562-232">Manter os arquivos de vídeo</span><span class="sxs-lookup"><span data-stu-id="22562-232">Retain video files</span></span>

<span data-ttu-id="22562-233">Esta recomendação é exibida quando qualquer um dos seguintes tipos de arquivo é detectado no SharePoint ou OneDrive.</span><span class="sxs-lookup"><span data-stu-id="22562-233">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="22562-234">.AVCHD</span><span class="sxs-lookup"><span data-stu-id="22562-234">.AVCHD</span></span>
- <span data-ttu-id="22562-235">.AVI</span><span class="sxs-lookup"><span data-stu-id="22562-235">.AVI</span></span>
- <span data-ttu-id="22562-236">.FLV</span><span class="sxs-lookup"><span data-stu-id="22562-236">.FLV</span></span>
- <span data-ttu-id="22562-237">.MOV</span><span class="sxs-lookup"><span data-stu-id="22562-237">.MOV</span></span>
- <span data-ttu-id="22562-238">.MP2V</span><span class="sxs-lookup"><span data-stu-id="22562-238">.MP2V</span></span>
- <span data-ttu-id="22562-239">.MP4</span><span class="sxs-lookup"><span data-stu-id="22562-239">.MP4</span></span>
- <span data-ttu-id="22562-240">.MP4V</span><span class="sxs-lookup"><span data-stu-id="22562-240">.MP4V</span></span>
- <span data-ttu-id="22562-241">.MPE</span><span class="sxs-lookup"><span data-stu-id="22562-241">.MPE</span></span>
- <span data-ttu-id="22562-242">.MPEG</span><span class="sxs-lookup"><span data-stu-id="22562-242">.MPEG</span></span>
- <span data-ttu-id="22562-243">.MPEG1</span><span class="sxs-lookup"><span data-stu-id="22562-243">.MPEG1</span></span>
- <span data-ttu-id="22562-244">.MPEG2</span><span class="sxs-lookup"><span data-stu-id="22562-244">.MPEG2</span></span>
- <span data-ttu-id="22562-245">.MPEG4</span><span class="sxs-lookup"><span data-stu-id="22562-245">.MPEG4</span></span>
- <span data-ttu-id="22562-246">.MPG</span><span class="sxs-lookup"><span data-stu-id="22562-246">.MPG</span></span>
- <span data-ttu-id="22562-247">.MPG2</span><span class="sxs-lookup"><span data-stu-id="22562-247">.MPG2</span></span>
- <span data-ttu-id="22562-248">.MPG4</span><span class="sxs-lookup"><span data-stu-id="22562-248">.MPG4</span></span>
- <span data-ttu-id="22562-249">.WMV</span><span class="sxs-lookup"><span data-stu-id="22562-249">.WMV</span></span>
- <span data-ttu-id="22562-250">.XMV</span><span class="sxs-lookup"><span data-stu-id="22562-250">.XMV</span></span>