---
title: Introdução à classificação de dados (visualização)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: O painel de classificação de dados permite visualizar a quantidade de dados confidenciais encontrados e classificados em sua organização.
ms.openlocfilehash: 76c1199fa3842428900db197f15728c116f778b9
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42076372"
---
# <a name="data-classification-overview-preview"></a><span data-ttu-id="30f01-103">Visão geral da classificação de dados (visualização)</span><span class="sxs-lookup"><span data-stu-id="30f01-103">Data classification overview (preview)</span></span>

<span data-ttu-id="30f01-104">Como administrador de conformidade ou administrador do Microsoft 365, você pode avaliar e marcar o conteúdo da sua organização para controlar o seu destino, protegê-lo independentemente de onde ele estiver e garantir que ele seja preservado e excluído de acordo com as necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="30f01-104">As a Microsoft 365 administrator or compliance administrator, you can evaluate and then tag content in your organization in order to control where it goes, protect it no matter where it is and to ensure that it is preserved and deleted according your your organizations needs.</span></span> <span data-ttu-id="30f01-105">Isso é feito através da aplicação de [rótulos de confidencialidade](sensitivity-labels.md), [rótoulos de retenção](labels.md) classificação de tipos de informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="30f01-105">You do this through the application of [sensitivity labels](sensitivity-labels.md), [retention labels](labels.md), and sensitive information type classification.</span></span> <span data-ttu-id="30f01-106">Há várias maneiras de fazer a descoberta, a avaliação e a marcação, mas o resultado final é que você pode acabar tendo um número muito grande de documentos e emails marcados e classificados com um ou ambos os rótulos.</span><span class="sxs-lookup"><span data-stu-id="30f01-106">There are various ways to do the discovery, evaluation and tagging, but the end result is that you may have very large numbers of documents and emails that are tagged and classified with one or both of these labels.</span></span> <span data-ttu-id="30f01-107">Depois de criar seus rótulos de retenção e rótulos de confidencialidade, você vai querer saber como eles estão sendo usados em seu locatário e o que está sendo feito com esses itens.</span><span class="sxs-lookup"><span data-stu-id="30f01-107">After you apply  your retention labels and sensitivity labels, you’ll want to see how the labels are being used across your tenant and what is being done with those items.</span></span> <span data-ttu-id="30f01-108">A página classificação de dados dá visibilidade ao corpo do conteúdo, especificamente:</span><span class="sxs-lookup"><span data-stu-id="30f01-108">The data classification page provides visibility into that body of content, specifically:</span></span>

- <span data-ttu-id="30f01-109">o número de itens que foram classificados como um tipo de informação confidencial e quais são essas classificações</span><span class="sxs-lookup"><span data-stu-id="30f01-109">the number items that have been classified as a sensitive information type and what those classifications are</span></span>
- <span data-ttu-id="30f01-110">os principais rótulos de confidencialidade aplicados tanto no Microsoft 365 quanto na Proteção de Informações do Azure</span><span class="sxs-lookup"><span data-stu-id="30f01-110">the top applied sensitivity labels in both Microsoft 365 and Azure Information Protection</span></span>
- <span data-ttu-id="30f01-111">os principais rótulos de retenção aplicados</span><span class="sxs-lookup"><span data-stu-id="30f01-111">the top applied retention labels</span></span>
- <span data-ttu-id="30f01-112">um resumo das atividades que os usuários estão executando no conteúdo confidencial</span><span class="sxs-lookup"><span data-stu-id="30f01-112">a summary of activities that users are taking on your sensitive content</span></span>
- <span data-ttu-id="30f01-113">os locais onde estão os seus dados confidenciais e retidos</span><span class="sxs-lookup"><span data-stu-id="30f01-113">the locations of your sensitive and retained data</span></span>

<span data-ttu-id="30f01-114">Você pode encontrar a classificação de dados no **Centro de conformidade do Microsoft 365** ou no **Centro de segurança do Microsoft 365** > **Classificação**  >  \*\* Classificação de Dados\*\*.</span><span class="sxs-lookup"><span data-stu-id="30f01-114">You can find data classification in the **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Classification** > **Data Classification**.</span></span>

## <a name="sensitive-information-types-used-most-in-your-content"></a><span data-ttu-id="30f01-115">Tipos de informações confidenciais mais usados no seu conteúdo</span><span class="sxs-lookup"><span data-stu-id="30f01-115">Sensitive information types used most in your content</span></span>

<span data-ttu-id="30f01-116">O Microsoft 365 vem com várias definições de tipos de informações confidenciais, tal como um item contendo um número de seguridade social ou um número de cartão de crédito.</span><span class="sxs-lookup"><span data-stu-id="30f01-116">Microsoft 365 comes with many definitions of sensitive information types, such as an item containing a social security number or a credit card number.</span></span> <span data-ttu-id="30f01-117">Para obter mais informações sobre os tipos de informações confidenciais, confira [O que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="30f01-117">For more information on sensitive information types, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>

<span data-ttu-id="30f01-118">O cartão do tipo de informações confidenciais mostra os principais tipos de informações confidenciais que foram encontrados e rotulados em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="30f01-118">The sensitive information type card shows the top sensitive information types that have been found and labeled across your organization.</span></span>

![principais tipos de informações confidenciais ](../media/data-classification-sens-info-types-card.png)

<span data-ttu-id="30f01-120">Para saber quantos itens estão em uma determinada categoria de classificação, passe o mouse sobre a barra para determinar a categoria.</span><span class="sxs-lookup"><span data-stu-id="30f01-120">To find out how many items are in any given classification category, hover over the bar for the category.</span></span>

![detalhe do hover exibindo os principais tipos de informações confidenciais  ](../media/data-classification-sens-info-types-hover.png)

> [!NOTE]
> <span data-ttu-id="30f01-122">Se o cartão exibir a mensagem «não foram encontrados dados com informações confidenciais».</span><span class="sxs-lookup"><span data-stu-id="30f01-122">If the card displays the message "No data found with sensitive information".</span></span> <span data-ttu-id="30f01-123">Isso significa que não há nenhum item em sua organização que tenha sido classificado como sendo um tipo de informação confidencial ou nenhum item que tenha sido rastreado.</span><span class="sxs-lookup"><span data-stu-id="30f01-123">It means that there are no items in your organization that have been classified as being a sensitive information type or no items that have been crawled.</span></span> <span data-ttu-id="30f01-124">Para começar a usar os rótulos, confira:</span><span class="sxs-lookup"><span data-stu-id="30f01-124">To get started with labels, see:</span></span>
>- [<span data-ttu-id="30f01-125">Rótulos de confidencialidade </span><span class="sxs-lookup"><span data-stu-id="30f01-125">Sensitivity labels</span></span>](sensitivity-labels.md)
>- [<span data-ttu-id="30f01-126">Rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="30f01-126">Retention labels</span></span>](labels.md)
>- [<span data-ttu-id="30f01-127">O que os tipos de informação confidencial procuram</span><span class="sxs-lookup"><span data-stu-id="30f01-127">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

## <a name="top-sensitivity-labels-applied-to-content"></a><span data-ttu-id="30f01-128">Principais rótulos de confidencialidade aplicados ao conteúdo</span><span class="sxs-lookup"><span data-stu-id="30f01-128">Top sensitivity labels applied to content</span></span>

<span data-ttu-id="30f01-129">Quando você aplica um rótulo de confidencialidade a um item ou através do Microsoft 365 ou da proteção de informações do Azure (AIP), ocorrem duas coisas:</span><span class="sxs-lookup"><span data-stu-id="30f01-129">When you apply a sensitivity label to an item either through Microsoft 365 or Azure Information Protection (AIP), two things happen:</span></span>

- <span data-ttu-id="30f01-130">uma marca que indica o valor do item para a sua organização, inserida no documento, e o acompanhará onde quer que esse item vá</span><span class="sxs-lookup"><span data-stu-id="30f01-130">a tag that indicates the value of the item to your org is embedded in the document and will follow it everywhere it goes</span></span>
- <span data-ttu-id="30f01-131">a presença da marca ativa vários comportamentos de proteção, como uma marca d' água obrigatória ou a criptografia.</span><span class="sxs-lookup"><span data-stu-id="30f01-131">the presence of the tag enables various protective behaviors, such as mandatory watermarking or encryption.</span></span> <span data-ttu-id="30f01-132">Com a proteção de ponto de extremidade habilitada, você pode até mesmo impedir que um item saia de seu controle organizacional.</span><span class="sxs-lookup"><span data-stu-id="30f01-132">With end point protection enabled you can even prevent an item from leaving your organizational control.</span></span>

<span data-ttu-id="30f01-133">Para obter mais informações sobre rótulos de confidencialidade, confira: [Saiba mais sobre rótulos de confidencialidade](sensitivity-labels.md)</span><span class="sxs-lookup"><span data-stu-id="30f01-133">For more information on sensitivity labels, see: [Learn about sensitivity labels](sensitivity-labels.md)</span></span>

<span data-ttu-id="30f01-134">Os rótulos de confidencialidade devem ser habilitados para arquivos que estão no SharePoint e no OneDrive para que os dados correspondentes apareçam na página de classificação de dados.</span><span class="sxs-lookup"><span data-stu-id="30f01-134">Sensitivity labels must be enabled for files that are in SharePoint and OneDrive in order for the corresponding data to surface in the data classification page.</span></span> <span data-ttu-id="30f01-135">Para saber mais, confira [Habilitar rótulos de confidencialidade para arquivos do Office no SharePoint e no OneDrive (visualização pública)](sensitivity-labels-sharepoint-onedrive-files.md)</span><span class="sxs-lookup"><span data-stu-id="30f01-135">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

<span data-ttu-id="30f01-136">O cartão de identificação de confidencialidade mostra o número de itens (email ou documento) por nível de confidencialidade.</span><span class="sxs-lookup"><span data-stu-id="30f01-136">The sensitivity label card shows the number of items (email or document) by sensitivity level.</span></span>

![Captura da tela do espaço reservado que mostra a análise de conteúdo por classificação de rótulo de confidencialidade](../media/data-classification-top-sensitivity-labels-applied.png)

> [!NOTE]
> <span data-ttu-id="30f01-138">Se você ainda não criou ou publicou qualquer rótulo de confidencialidade ou se nenhum conteúdo tiver um rótulo de confidencialidade aplicado, esse cartão exibirá a mensagem "nenhum rótulo de confidencialidade detectado".</span><span class="sxs-lookup"><span data-stu-id="30f01-138">If you haven't created or published any sensitivity labels or no content has had a sensitivity label applied, this card will display the message "No sensitivity labels detected".</span></span> <span data-ttu-id="30f01-139">Para começar a usar os rótulos, confira:</span><span class="sxs-lookup"><span data-stu-id="30f01-139">To get started with labels, see:</span></span>
>- <span data-ttu-id="30f01-140">[rótulos de confidencialidade](sensitivity-labels.md) ou para AIP [Configurar a política de proteção de informações do Azure](https://docs.microsoft.com/azure/information-protection/configure-policy) </span><span class="sxs-lookup"><span data-stu-id="30f01-140">[sensitivity labels](sensitivity-labels.md) or for AIP [Configure the Azure information protection policy](https://docs.microsoft.com/azure/information-protection/configure-policy)</span></span>

## <a name="top-retention-labels-applied-to-content"></a><span data-ttu-id="30f01-141">Principais rótulos de retenção aplicados ao conteúdo</span><span class="sxs-lookup"><span data-stu-id="30f01-141">Top retention labels applied to content</span></span>

<span data-ttu-id="30f01-142">Os rótulos de retenção são usados para manejar a disposição do conteúdo de sua organização.</span><span class="sxs-lookup"><span data-stu-id="30f01-142">Retention labels are used to manage the disposition of content in your organization.</span></span> <span data-ttu-id="30f01-143">Quando aplicados, eles podem ser usados para controlar quanto tempo um documento será mantido antes da exclusão, se ele deve ser revisado antes da exclusão, quando o período de retenção expira ou se ele deve ser marcado como um registro que nunca pode ser excluído.</span><span class="sxs-lookup"><span data-stu-id="30f01-143">When applied, they can be used to control how long a document will be kept before deletion, whether it should be reviewed prior to deletion, when it's retention period expires, or whether it should be marked as a record which can never be deleted.</span></span> <span data-ttu-id="30f01-144">Para mais informações, confira a [Visão geral dos rótulos de retenção](labels.md).</span><span class="sxs-lookup"><span data-stu-id="30f01-144">For more information see, [Overview of retention labels](labels.md).</span></span>

<span data-ttu-id="30f01-145">O cartão dos principais rótulos de retenção aplicados mostra quantos itens têm um determinado rótulo de retenção.</span><span class="sxs-lookup"><span data-stu-id="30f01-145">The top applied retention labels card shows you how many items have a given retention label.</span></span>

![Captura de tela do espaço reservado mostrando os principais rótulos de retenção aplicados](../media/data-classification-top-retention-labels-applied.png)

> [!NOTE]
> <span data-ttu-id="30f01-147">Se este cartão exibir a mensagem "Nenhum rótulo de retenção detectado", isso significa que você não criou ou publicou qualquer rótulo de retenção ou que nenhum conteúdo teve qualquer rótulo de retenção aplicado.  </span><span class="sxs-lookup"><span data-stu-id="30f01-147">If this card displays the message, "No retention labels detected, it means you haven't created or published any retention  labels or no content has had a retention label applied.</span></span> <span data-ttu-id="30f01-148">Para começar a usar os rótulos de retenção, confira:</span><span class="sxs-lookup"><span data-stu-id="30f01-148">To get started with retention labels, see:</span></span>
>- [<span data-ttu-id="30f01-149">Visão geral de rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="30f01-149">Overview of retention labels</span></span>](labels.md)

## <a name="top-activities-detected"></a><span data-ttu-id="30f01-150">Atividades detectadas mais comuns</span><span class="sxs-lookup"><span data-stu-id="30f01-150">Top activities detected</span></span>

<span data-ttu-id="30f01-151">Este cartão fornece um resumo rápido das ações mais comuns que os usuários realizam com os itens rotulados como confidenciais.</span><span class="sxs-lookup"><span data-stu-id="30f01-151">This card provides a quick summary of the most common actions that users are taking on the sensitivity labeled items.</span></span> <span data-ttu-id="30f01-152">Você pode usar o [Explorador de atividades](data-classification-activity-explorer.md) para detalhar as oito diferentes atividades que o Microsoft 365 acompanha no conteúdo rotulado e o conteúdo localizado em pontos de extremidade do Windows 10.</span><span class="sxs-lookup"><span data-stu-id="30f01-152">You can use the [Activity explorer](data-classification-activity-explorer.md) to drill deep down on eight different activities that Microsoft 365 tracks on labeled content and content that is located on Windows 10 endpoints.</span></span>

> [!NOTE]
> <span data-ttu-id="30f01-153">Se esse cartão exibir a mensagem "Nenhuma atividade detectada", isso significa que não há nenhuma atividade nos arquivos ou que a auditoria de usuário e administradores não foi ativada.</span><span class="sxs-lookup"><span data-stu-id="30f01-153">If this card displays the message, "No activity detected" it means that there's been no activity on the files or that user and admin auditing isn't turned on.</span></span> <span data-ttu-id="30f01-154">Para ativar os logs de auditoria, confira:</span><span class="sxs-lookup"><span data-stu-id="30f01-154">To turn the audit logs on , see:</span></span>
>- <span data-ttu-id="30f01-155">[Pesquisar o log de auditoria no centro de conformidade e Segurança](search-the-audit-log-in-security-and-compliance.md) </span><span class="sxs-lookup"><span data-stu-id="30f01-155">[Search the audit log in security & compliance center](search-the-audit-log-in-security-and-compliance.md)</span></span>

## <a name="sensitivity-and-retention-labeled-data-by-location"></a><span data-ttu-id="30f01-156">Dados com rótulos de confidencialidade e retenção por local</span><span class="sxs-lookup"><span data-stu-id="30f01-156">Sensitivity and retention labeled data by location</span></span>

<span data-ttu-id="30f01-157">O objetivo do relatório de classificação de dados é fornecer visibilidade sobre o número de itens que têm o rótulo, bem como a sua localização.</span><span class="sxs-lookup"><span data-stu-id="30f01-157">The point of the data classification reporting is to provide visibility into the number of items that have which label as well as their location.</span></span> <span data-ttu-id="30f01-158">Esses cartões permitem saber quantos itens rotulados estão no Exchange, no SharePoint, OneDrive, etc.</span><span class="sxs-lookup"><span data-stu-id="30f01-158">These cards let you know how many labeled items the are in Exchange, SharePoint, and OneDrive etc.</span></span>

> [!NOTE]
> <span data-ttu-id="30f01-159">Se este cartão exibir a mensagem "Nenhum local detectado", isso significa que você não criou ou publicou qualquer rótulo de confidencialidade ou que nenhum conteúdo teve qualquer rótulo de retenção aplicado.  </span><span class="sxs-lookup"><span data-stu-id="30f01-159">If this card displays the message, "No locations detected, it means you haven't created or published any sensitivity labels or no content has had a retention label applied.</span></span> <span data-ttu-id="30f01-160">Para começar a usar os rótulos de confidencialidade, confira:</span><span class="sxs-lookup"><span data-stu-id="30f01-160">To get started with sensitivity labels, see:</span></span>
>- [<span data-ttu-id="30f01-161">Rótulos de confidencialidade </span><span class="sxs-lookup"><span data-stu-id="30f01-161">Sensitivity labels</span></span>](sensitivity-labels.md)

## <a name="see-also"></a><span data-ttu-id="30f01-162">Confira também</span><span class="sxs-lookup"><span data-stu-id="30f01-162">See also</span></span>

- [<span data-ttu-id="30f01-163">Exibir atividade do rótulo (visualização)</span><span class="sxs-lookup"><span data-stu-id="30f01-163">View label activity (preview)</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="30f01-164">Exibir conteúdo rotulado (visualização)</span><span class="sxs-lookup"><span data-stu-id="30f01-164">View labeled content (preview)</span></span>](data-classification-content-explorer.md)
- [<span data-ttu-id="30f01-165">Rótulos de confidencialidade </span><span class="sxs-lookup"><span data-stu-id="30f01-165">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="30f01-166">Rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="30f01-166">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="30f01-167">O que os tipos de informação confidencial procuram</span><span class="sxs-lookup"><span data-stu-id="30f01-167">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="30f01-168">Visão geral de políticas de retenção</span><span class="sxs-lookup"><span data-stu-id="30f01-168">Overview of retention policies</span></span>](retention-policies.md)
