---
title: Aumentar a proteção contra ameaças para o Microsoft 365 Business
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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
description: Configurar recursos de conformidade para evitar a perda de dados e rotular dados confidenciais.
ms.openlocfilehash: a0ba2fa6dbe7c786d577ad7098c1790f569f5acc
ms.sourcegitcommit: 255e8194bb5767a9983d54d16e79d628732a1d97
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/11/2019
ms.locfileid: "37453898"
---
# <a name="set-up-compliance-features"></a><span data-ttu-id="2ff83-103">Configurar recursos de conformidade</span><span class="sxs-lookup"><span data-stu-id="2ff83-103">Set up compliance features</span></span>

<span data-ttu-id="2ff83-104">Seu Microsoft 365 Business vem com recursos para proteger seus dados e dispositivos, e ajudar você a manter seu e as informações confidenciais de seus clientes seguras.</span><span class="sxs-lookup"><span data-stu-id="2ff83-104">Your Microsoft 365 Business comes with features to protect your data and devices, and help you keep yours and your customers' sensitive information secure.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="2ff83-105">Configurar recursos de DLP</span><span class="sxs-lookup"><span data-stu-id="2ff83-105">Set up DLP features</span></span>

<span data-ttu-id="2ff83-106">Consulte [criar uma política de DLP a partir de um modelo](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) para obter um exemplo de como configurar uma política para proteção contra informações de identificação pessoal (PII).</span><span class="sxs-lookup"><span data-stu-id="2ff83-106">See [Create a DLP policy from a template](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) for an example on how to set up a policy to protect against personally identifiable information (PII).</span></span> 
  
<span data-ttu-id="2ff83-107">A DLP vem com vários modelos de política prontos para uso para várias localidades diferentes.</span><span class="sxs-lookup"><span data-stu-id="2ff83-107">DLP comes with many ready-to-use policy templates for many different locales.</span></span> <span data-ttu-id="2ff83-108">Por exemplo, dados financeiros da Austrália, ato de informações pessoais do Canadá, dados financeiros dos EUA, etc. Veja o [que os modelos de política de DLP incluem](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) para uma lista completa.</span><span class="sxs-lookup"><span data-stu-id="2ff83-108">For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, etc. See [What the DLP policy templates include](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) for a full list.</span></span> <span data-ttu-id="2ff83-109">Todos esses modelos podem ser habilitados de forma semelhante ao exemplo de modelo PII.</span><span class="sxs-lookup"><span data-stu-id="2ff83-109">All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="2ff83-110">Configurar a retenção de email com o arquivamento do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2ff83-110">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="2ff83-111">Os recursos de licença de **arquivamento do Exchange Online** ajudam a manter os padrões de conformidade e regulamentação ao preservar o conteúdo de email para descoberta eletrônica.</span><span class="sxs-lookup"><span data-stu-id="2ff83-111">**Exchange Online Archiving** license features help maintain compliance and regulatory standards by preserving email content for eDiscovery.</span></span> <span data-ttu-id="2ff83-112">Isso também ajuda a reduzir o risco no caso de uma ação judicial e oferece uma maneira de recuperar dados após uma violação de segurança ou quando você precisa recuperar itens excluídos.</span><span class="sxs-lookup"><span data-stu-id="2ff83-112">It also helps reduce your risk in the event of a lawsuit and provides a way to recover data after a security breach, or when you need to recover deleted items.</span></span> <span data-ttu-id="2ff83-113">Você pode usar a retenção de litígio para preservar todo o conteúdo de um usuário ou usar políticas de retenção para personalizar o que você deseja preservar.</span><span class="sxs-lookup"><span data-stu-id="2ff83-113">You can use litigation hold to preserve all of a user's content, or use retention policies to customize what you want to preserve.</span></span>
  
<span data-ttu-id="2ff83-114">**Retenção de litígio:** Você pode preservar todo o conteúdo da caixa de correio, incluindo itens excluídos, colocando a caixa de correio de um usuário em retenção de litígio.</span><span class="sxs-lookup"><span data-stu-id="2ff83-114">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="2ff83-115">Para colocar uma caixa de correio em retenção de litígio, no centro de administração:</span><span class="sxs-lookup"><span data-stu-id="2ff83-115">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="2ff83-116">No painel de navegação à esquerda, vá para usuários **ativos**do **usuário** \> .</span><span class="sxs-lookup"><span data-stu-id="2ff83-116">In the left nav, go to **Users** \> **Active users**.</span></span>
    
2. <span data-ttu-id="2ff83-117">Selecione um usuário cuja caixa de correio você deseja colocar em retenção de litígio e, no painel de usuário, expanda **configurações de email** e ao lado de **mais configurações** escolha **Editar propriedades do Exchange**.</span><span class="sxs-lookup"><span data-stu-id="2ff83-117">Select a user whose mailbox you want to place on litigation hold and in the user pane expand **Mail settings** and next to **More settings** choose **Edit Exchange properties**.</span></span>
    
3. <span data-ttu-id="2ff83-118">Na página caixa de correio do usuário, escolha \* \* recursos de caixa de correio \* \* no painel de navegação esquerdo e, em seguida, escolha o link **habilitar** em **retenção de litígio**.</span><span class="sxs-lookup"><span data-stu-id="2ff83-118">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span></span>
    
4. <span data-ttu-id="2ff83-119">Na caixa de diálogo **retenção de litígio** , é possível especificar a duração da retenção de litígio no campo duração da **retenção de litígio** , deixar o campo vazio se você quiser colocar uma retenção infinita.</span><span class="sxs-lookup"><span data-stu-id="2ff83-119">In the **litigation hold** dialog box you can specify the litigation hold duration in the **Litigation hold duration** field, leave field empty if you want to place an infinite hold.</span></span> <span data-ttu-id="2ff83-120">Você também pode adicionar notas e direcionar o proprietário da caixa de correio para um site que pode ser necessário para explicar mais sobre \> o **salvamento**de litígio.</span><span class="sxs-lookup"><span data-stu-id="2ff83-120">You can also add notes and direct the mail box owner to a website you might have to explain more about the litigation hold \> **Save**.</span></span>
    
<span data-ttu-id="2ff83-121">**Retenção:** Você pode habilitar políticas de retenção personalizadas, por exemplo, para preservar um período específico de tempo ou excluir o conteúdo permanentemente no final do período de retenção.</span><span class="sxs-lookup"><span data-stu-id="2ff83-121">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="2ff83-122">Para saber mais, confira [visão geral das políticas de retenção](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span><span class="sxs-lookup"><span data-stu-id="2ff83-122">To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>

## <a name="set-up-sensitivity-labels"></a><span data-ttu-id="2ff83-123">Configurar rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="2ff83-123">Set up Sensitivity labels</span></span>

<span data-ttu-id="2ff83-124">Os rótulos de confidencialidade vêm com o plano 1 do Windows Information Protection (AIP) e ajudam você a classificar e, opcionalmente, proteger seus documentos e emails, aplicando rótulos.</span><span class="sxs-lookup"><span data-stu-id="2ff83-124">Sensitivity labels come with Azure Information Protection (AIP) Plan 1, and help you classify and optionally, protect your documents and emails, by applying labels.</span></span> <span data-ttu-id="2ff83-125">Os rótulos podem ser aplicados automaticamente por administradores que definem regras e condições, manualmente por usuários ou usando uma combinação em que os usuários recebem recomendações.</span><span class="sxs-lookup"><span data-stu-id="2ff83-125">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or by using a combination where users are given recommendations.</span></span>

<span data-ttu-id="2ff83-126">Para configurar rótulos de sensibilidade, exiba o vídeo [criar e gerenciar rótulos de confidencialidade](https://support.office.com/en-us/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) .</span><span class="sxs-lookup"><span data-stu-id="2ff83-126">To set up Sensitivity labels, view [create and manage sensitivity labels](https://support.office.com/en-us/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>



### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="2ff83-127">Instalar o cliente de proteção de informações do Azure manualmente</span><span class="sxs-lookup"><span data-stu-id="2ff83-127">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="2ff83-128">Para instalar manualmente o cliente AIP:</span><span class="sxs-lookup"><span data-stu-id="2ff83-128">To manually install the AIP client:</span></span>

1. <span data-ttu-id="2ff83-129">Baixe o **AzinfoProtection_UL. exe** do [centro de download da Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).</span><span class="sxs-lookup"><span data-stu-id="2ff83-129">Download **AzinfoProtection_UL.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="2ff83-130">Você pode verificar se a instalação funcionou exibindo um documento do Word e certificando-se de que a opção de **sensibilidade** esteja disponível na guia **página inicial** .</span><span class="sxs-lookup"><span data-stu-id="2ff83-130">You can verify that the installation worked by viewing a Word document and making sure that the **Sensitivity** option is available on the **Home** tab.</span></span>
<br/><span data-ttu-id="2ff83-131">![Menu suspenso proteção de guia em um documento do Word.](media/word-sensitivity.png)</span><span class="sxs-lookup"><span data-stu-id="2ff83-131">![Protection tab drop-down in a Word document.](media/word-sensitivity.png)</span></span>

<span data-ttu-id="2ff83-132">Confira mais informações em [instalar o cliente](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span><span class="sxs-lookup"><span data-stu-id="2ff83-132">For more information see, [Install the client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span></span>
