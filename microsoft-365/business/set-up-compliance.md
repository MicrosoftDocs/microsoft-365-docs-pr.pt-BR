---
title: Aumentar a proteção contra ameaças do Microsoft 365 Business Premium
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Configurar recursos de conformidade para evitar a perda de dados e ajudar a manter suas informações confidenciais e de seus clientes seguras.
ms.openlocfilehash: 2c95ad3f36df28af2c68cd11192bcfe92dfe29e3
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841164"
---
# <a name="set-up-compliance-features"></a><span data-ttu-id="bf6b8-103">Configure os recursos de conformidade</span><span class="sxs-lookup"><span data-stu-id="bf6b8-103">Set up compliance features</span></span>

<span data-ttu-id="bf6b8-104">O Microsoft 365 Business Premium vem com recursos para proteger seus dados e dispositivos e ajudar você a manter suas informações confidenciais e de seus clientes seguras.</span><span class="sxs-lookup"><span data-stu-id="bf6b8-104">Your Microsoft 365 Business Premium comes with features to protect your data and devices, and help you keep your and your customers' sensitive information secure.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="bf6b8-105">Configurar recursos de DLP</span><span class="sxs-lookup"><span data-stu-id="bf6b8-105">Set up DLP features</span></span>

<span data-ttu-id="bf6b8-106">Consulte [Criar uma política de DLP a](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template) partir de um modelo para ver um exemplo de como configurar uma política para proteger contra a perda de dados pessoais.</span><span class="sxs-lookup"><span data-stu-id="bf6b8-106">See [Create a DLP policy from a template](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template) for an example on how to set up a policy to protect against protect loss of personal data.</span></span> 
  
<span data-ttu-id="bf6b8-107">A DLP vem com muitos modelos de política prontos para uso para muitas localidades diferentes.</span><span class="sxs-lookup"><span data-stu-id="bf6b8-107">DLP comes with many ready-to-use policy templates for many different locales.</span></span> <span data-ttu-id="bf6b8-108">Por exemplo, Dados Financeiros da Austrália, Ato de Informações Pessoais do Canadá, Dados Financeiros dos EUA e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="bf6b8-108">For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, and so on.</span></span> <span data-ttu-id="bf6b8-109">Veja [o que os modelos de política de DLP incluem](https://docs.microsoft.com/microsoft-365/compliance/what-the-dlp-policy-templates-include) para uma lista completa.</span><span class="sxs-lookup"><span data-stu-id="bf6b8-109">See [What the DLP policy templates include](https://docs.microsoft.com/microsoft-365/compliance/what-the-dlp-policy-templates-include) for a full list.</span></span> <span data-ttu-id="bf6b8-110">Todos esses modelos podem ser habilitados de forma semelhante ao exemplo de modelo de PII.</span><span class="sxs-lookup"><span data-stu-id="bf6b8-110">All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="bf6b8-111">Configurar a retenção de email com o Arquivamento do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="bf6b8-111">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="bf6b8-112">**Os recursos de licença** do Arquivamento do Exchange Online ajudam a manter os padrões de conformidade e regulamentação, preservando o conteúdo de email para a Descoberta Eletrônico.</span><span class="sxs-lookup"><span data-stu-id="bf6b8-112">**Exchange Online Archiving** license features help maintain compliance and regulatory standards by preserving email content for eDiscovery.</span></span> <span data-ttu-id="bf6b8-113">Ele também ajuda a reduzir o risco se houver um processo e fornece uma maneira de recuperar dados após uma violação de segurança ou quando você precisa recuperar itens excluídos.</span><span class="sxs-lookup"><span data-stu-id="bf6b8-113">It also helps reduce your risk if there is a lawsuit, and provides a way to recover data after a security breach or when you need to recover deleted items.</span></span> <span data-ttu-id="bf6b8-114">Você pode usar a retenção de litígio para preservar todo o conteúdo de um usuário ou usar políticas de retenção para personalizar o que você deseja preservar.</span><span class="sxs-lookup"><span data-stu-id="bf6b8-114">You can use litigation hold to preserve all of a user's content, or use retention policies to customize what you want to preserve.</span></span>
  
<span data-ttu-id="bf6b8-115">**Hold de litígio:** Você pode preservar todo o conteúdo da caixa de correio, incluindo itens excluídos, colocando toda a caixa de correio do usuário em espera de litígio.</span><span class="sxs-lookup"><span data-stu-id="bf6b8-115">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="bf6b8-116">Para colocar uma caixa de correio em espera de litígio, no Centro de administração:</span><span class="sxs-lookup"><span data-stu-id="bf6b8-116">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="bf6b8-117">In the left nav, go to **Users** \> **Active users**.</span><span class="sxs-lookup"><span data-stu-id="bf6b8-117">In the left nav, go to **Users** \> **Active users**.</span></span>
    
2. <span data-ttu-id="bf6b8-118">Selecione um usuário cuja caixa de correio você deseja colocar em espera de litígio.</span><span class="sxs-lookup"><span data-stu-id="bf6b8-118">Select a user whose mailbox you want to place on litigation hold.</span></span> <span data-ttu-id="bf6b8-119">No painel do usuário, **expanda configurações de** email e, ao lado de **Mais configurações,** escolha **Editar propriedades do Exchange.**</span><span class="sxs-lookup"><span data-stu-id="bf6b8-119">In the user pane, expand **Mail settings**, and next to **More settings**, choose **Edit Exchange properties**.</span></span>
    
3. <span data-ttu-id="bf6b8-120">Na página da caixa de correio para o usuário, escolha \*\* recursos de caixa de correio \*\* no **nav** esquerdo e, em seguida, escolha o link Habilitar em responsabilidade **de litígio**.</span><span class="sxs-lookup"><span data-stu-id="bf6b8-120">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span></span>
    
4. <span data-ttu-id="bf6b8-121">Na caixa **de diálogo de** espera de litígio, você pode especificar a duração da espera de litígio no campo de duração de espera **de** litígio.</span><span class="sxs-lookup"><span data-stu-id="bf6b8-121">In the **litigation hold** dialog box, you can specify the litigation hold duration in the **Litigation hold duration** field.</span></span> <span data-ttu-id="bf6b8-122">Deixe o campo vazio se quiser colocar uma espera infinita.</span><span class="sxs-lookup"><span data-stu-id="bf6b8-122">Leave the field empty if you want to place an infinite hold.</span></span> <span data-ttu-id="bf6b8-123">Você também pode adicionar anotações e direcionar o proprietário da caixa de correio a um site que talvez seja preciso explicar mais sobre a espera de litígio.</span><span class="sxs-lookup"><span data-stu-id="bf6b8-123">You can also add notes and direct the mailbox owner to a website you might have to explain more about the litigation hold.</span></span> <span data-ttu-id="bf6b8-124">\>**Salvar**.</span><span class="sxs-lookup"><span data-stu-id="bf6b8-124">\> **Save**.</span></span>
    
<span data-ttu-id="bf6b8-125">**Retenção:** Você pode habilitar políticas de retenção personalizadas, por exemplo, para preservar por um período específico de tempo ou excluir o conteúdo permanentemente no final do período de retenção.</span><span class="sxs-lookup"><span data-stu-id="bf6b8-125">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="bf6b8-126">Para saber mais, consulte [Visão geral das políticas de retenção.](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)</span><span class="sxs-lookup"><span data-stu-id="bf6b8-126">To learn more, see [Overview of retention policies](https://docs.microsoft.com/microsoft-365/compliance/retention-policies).</span></span>

## <a name="set-up-sensitivity-labels"></a><span data-ttu-id="bf6b8-127">Configurar rótulos de sensibilidade</span><span class="sxs-lookup"><span data-stu-id="bf6b8-127">Set up Sensitivity labels</span></span>

<span data-ttu-id="bf6b8-128">Os rótulos de sensibilidade vêm com o Plano 1 da Proteção de Informações do Azure (AIP) e ajudam a classificar e, opcionalmente, proteger seus documentos e emails aplicando rótulos.</span><span class="sxs-lookup"><span data-stu-id="bf6b8-128">Sensitivity labels come with Azure Information Protection (AIP) Plan 1, and help you classify, and optionally protect your documents and emails, by applying labels.</span></span> <span data-ttu-id="bf6b8-129">Os rótulos podem ser aplicados automaticamente por administradores que definem regras e condições, manualmente por usuários ou usando uma combinação na qual os usuários têm recomendações.</span><span class="sxs-lookup"><span data-stu-id="bf6b8-129">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or by using a combination where users are given recommendations.</span></span>

<span data-ttu-id="bf6b8-130">Para configurar rótulos de sensibilidade, veja [o vídeo criar e gerenciar rótulos de sensibilidade.](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9)</span><span class="sxs-lookup"><span data-stu-id="bf6b8-130">To set up Sensitivity labels, view [create and manage sensitivity labels](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>



### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="bf6b8-131">Instalar o cliente da Proteção de Informações do Azure manualmente</span><span class="sxs-lookup"><span data-stu-id="bf6b8-131">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="bf6b8-132">Para instalar manualmente o cliente AIP:</span><span class="sxs-lookup"><span data-stu-id="bf6b8-132">To manually install the AIP client:</span></span>

1. <span data-ttu-id="bf6b8-133">Baixe **AzinfoProtection_UL.exe** centro [de download da Microsoft.](https://www.microsoft.com/download/details.aspx?id=53018)</span><span class="sxs-lookup"><span data-stu-id="bf6b8-133">Download **AzinfoProtection_UL.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="bf6b8-134">Você pode verificar se a instalação funcionou visualizando  um documento do Word e verificando se a opção Sensibilidade está disponível na **guia** Página Home.</span><span class="sxs-lookup"><span data-stu-id="bf6b8-134">You can verify that the installation worked by viewing a Word document and making sure that the **Sensitivity** option is available on the **Home** tab.</span></span>
<br/><span data-ttu-id="bf6b8-135">![Guia de proteção em um documento do Word.](../media/word-sensitivity.png)</span><span class="sxs-lookup"><span data-stu-id="bf6b8-135">![Protection tab drop-down in a Word document.](../media/word-sensitivity.png)</span></span>

<span data-ttu-id="bf6b8-136">Para obter mais informações, consulte [Instalar o cliente.](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3)</span><span class="sxs-lookup"><span data-stu-id="bf6b8-136">For more information, see [Install the client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span></span>
