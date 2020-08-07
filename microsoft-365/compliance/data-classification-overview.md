---
title: Começar a usar a classificação de dados
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
ms.openlocfilehash: 3198a1981ed7d4d5428452b55aeb22b234712354
ms.sourcegitcommit: b812771805c8b9e92b64deb1928e265e60d80405
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2020
ms.locfileid: "46588213"
---
# <a name="know-your-data---data-classification-overview"></a><span data-ttu-id="1bc11-103">Conheça seus dados - visão geral da classificação de dados</span><span class="sxs-lookup"><span data-stu-id="1bc11-103">Know your data - data classification overview</span></span>

<span data-ttu-id="1bc11-104">Como administrador de conformidade ou administrador do Microsoft 365, você pode avaliar e marcar o conteúdo da sua organização para controlar o seu destino, protegê-lo independentemente de onde ele estiver e garantir que ele seja preservado e excluído de acordo com as necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="1bc11-104">As a Microsoft 365 administrator or compliance administrator, you can evaluate and then tag content in your organization in order to control where it goes, protect it no matter where it is and to ensure that it is preserved and deleted according to your organizations needs.</span></span> <span data-ttu-id="1bc11-105">Isso é feito através da aplicação de [rótulos de confidencialidade](sensitivity-labels.md), [rótoulos de retenção](retention.md#retention-labels) classificação de tipos de informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="1bc11-105">You do this through the application of [sensitivity labels](sensitivity-labels.md), [retention labels](retention.md#retention-labels), and sensitive information type classification.</span></span> <span data-ttu-id="1bc11-106">Há várias maneiras de fazer a descoberta, a avaliação e a marcação, mas o resultado final é que você pode acabar tendo um número muito grande de documentos e emails marcados e classificados com um ou ambos os rótulos.</span><span class="sxs-lookup"><span data-stu-id="1bc11-106">There are various ways to do the discovery, evaluation and tagging, but the end result is that you may have very large number of documents and emails that are tagged and classified with one or both of these labels.</span></span> <span data-ttu-id="1bc11-107">Depois de criar seus rótulos de retenção e rótulos de confidencialidade, você vai querer saber como eles estão sendo usados em seu locatário e o que está sendo feito com esses itens.</span><span class="sxs-lookup"><span data-stu-id="1bc11-107">After you apply your retention labels and sensitivity labels, you'll want to see how the labels are being used across your tenant and what is being done with those items.</span></span> <span data-ttu-id="1bc11-108">A página classificação de dados dá visibilidade ao corpo do conteúdo, especificamente:</span><span class="sxs-lookup"><span data-stu-id="1bc11-108">The data classification page provides visibility into that body of content, specifically:</span></span>

- <span data-ttu-id="1bc11-109">o número de itens que foram classificados como um tipo de informação confidencial e quais são essas classificações</span><span class="sxs-lookup"><span data-stu-id="1bc11-109">the number items that have been classified as a sensitive information type and what those classifications are</span></span>
- <span data-ttu-id="1bc11-110">os principais rótulos de confidencialidade aplicados tanto no Microsoft 365 quanto na Proteção de Informações do Azure</span><span class="sxs-lookup"><span data-stu-id="1bc11-110">the top applied sensitivity labels in both Microsoft 365 and Azure Information Protection</span></span>
- <span data-ttu-id="1bc11-111">os principais rótulos de retenção aplicados</span><span class="sxs-lookup"><span data-stu-id="1bc11-111">the top applied retention labels</span></span>
- <span data-ttu-id="1bc11-112">um resumo das atividades que os usuários estão executando no conteúdo confidencial</span><span class="sxs-lookup"><span data-stu-id="1bc11-112">a summary of activities that users are taking on your sensitive content</span></span>
- <span data-ttu-id="1bc11-113">os locais onde estão os seus dados confidenciais e retidos</span><span class="sxs-lookup"><span data-stu-id="1bc11-113">the locations of your sensitive and retained data</span></span>

<span data-ttu-id="1bc11-114">Você também gerencia esses recursos na página de classificação de dados:</span><span class="sxs-lookup"><span data-stu-id="1bc11-114">You also manage these features on the data classification page:</span></span>
- [<span data-ttu-id="1bc11-115">classificadores treináveis</span><span class="sxs-lookup"><span data-stu-id="1bc11-115">trainable classifiers</span></span>](classifier-getting-started-with.md)
- [<span data-ttu-id="1bc11-116">tipos de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="1bc11-116">sensitive information types</span></span>](what-the-sensitive-information-types-look-for.md)

<span data-ttu-id="1bc11-117">Você pode encontrar a classificação de dados no **Centro de conformidade do Microsoft 365** ou no **Centro de segurança do Microsoft 365** > **Classificação**  >  \*\* Classificação de Dados\*\*.</span><span class="sxs-lookup"><span data-stu-id="1bc11-117">You can find data classification in the **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Classification** > **Data Classification**.</span></span>

<span data-ttu-id="1bc11-118">Faça um tour em vídeo de nossos recursos de classificação de dados.</span><span class="sxs-lookup"><span data-stu-id="1bc11-118">Take a video tour of our data classification features.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vx8x]

<span data-ttu-id="1bc11-119">A classificação de dados verificará seu conteúdo confidencial e conteúdo rotulado antes de criar quaisquer políticas.</span><span class="sxs-lookup"><span data-stu-id="1bc11-119">Data classification will scan your sensitive content and labeled content before you create any policies.</span></span> <span data-ttu-id="1bc11-120">Isso se chama **gerenciamento de alterações zero**.</span><span class="sxs-lookup"><span data-stu-id="1bc11-120">This is called **zero change management**.</span></span> <span data-ttu-id="1bc11-121">Isso permite que você veja o impacto de que todos os rótulos de retenção e sensibilidade estão tendo no ambiente e capacitam você a começar a avaliar a proteção e as necessidades de políticas de governança.</span><span class="sxs-lookup"><span data-stu-id="1bc11-121">This lets you see the impact that all the retention and sensitivity labels are having in your environment and empower you to start assessing your protection and governance policy needs.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1bc11-122">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="1bc11-122">Prerequisites</span></span>

<span data-ttu-id="1bc11-123">Toda conta que acessa e usa a classificação de dados deve ter uma licença atribuída a partir de uma destas assinaturas:</span><span class="sxs-lookup"><span data-stu-id="1bc11-123">Every account that accesses and uses data classification must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="1bc11-124">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="1bc11-124">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="1bc11-125">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="1bc11-125">Office 365 (E5)</span></span>
- <span data-ttu-id="1bc11-126">Complemento de Conformidade Avançada (E5)</span><span class="sxs-lookup"><span data-stu-id="1bc11-126">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="1bc11-127">Complemento Avançado de Inteligência contra Ameaças (E5)</span><span class="sxs-lookup"><span data-stu-id="1bc11-127">Advanced Threat Intelligence (E5) add-on</span></span>

### <a name="permissions"></a><span data-ttu-id="1bc11-128">Permissões</span><span class="sxs-lookup"><span data-stu-id="1bc11-128">Permissions</span></span>

 <span data-ttu-id="1bc11-129">Para obter acesso à página de classificação de dados, é necessário atribuir uma associação a uma conta para uma dessas funções ou grupos de funções.</span><span class="sxs-lookup"><span data-stu-id="1bc11-129">In order to get access to the data classification page, an account must be assigned membership in any one of these roles or role groups.</span></span>

<span data-ttu-id="1bc11-130">**Grupos de funções do Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="1bc11-130">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="1bc11-131">Administrador global</span><span class="sxs-lookup"><span data-stu-id="1bc11-131">Global administrator</span></span>
- <span data-ttu-id="1bc11-132">Administrador de conformidade</span><span class="sxs-lookup"><span data-stu-id="1bc11-132">Compliance administrator</span></span>
- <span data-ttu-id="1bc11-133">Administrador de segurança</span><span class="sxs-lookup"><span data-stu-id="1bc11-133">Security administrator</span></span>
- <span data-ttu-id="1bc11-134">Administrador de dados de conformidade</span><span class="sxs-lookup"><span data-stu-id="1bc11-134">Compliance data administrator</span></span>

## <a name="sensitive-information-types-used-most-in-your-content"></a><span data-ttu-id="1bc11-135">Tipos de informações confidenciais mais usados no seu conteúdo</span><span class="sxs-lookup"><span data-stu-id="1bc11-135">Sensitive information types used most in your content</span></span>

<span data-ttu-id="1bc11-136">O Microsoft 365 vem com várias definições de tipos de informações confidenciais, tal como um item contendo um número de seguridade social ou um número de cartão de crédito.</span><span class="sxs-lookup"><span data-stu-id="1bc11-136">Microsoft 365 comes with many definitions of sensitive information types, such as an item containing a social security number or a credit card number.</span></span> <span data-ttu-id="1bc11-137">Para obter mais informações sobre os tipos de informações confidenciais, confira [Definições da entidade de tipo de informações confidenciais](sensitive-information-type-entity-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="1bc11-137">For more information on sensitive information types, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span></span>

<span data-ttu-id="1bc11-138">O cartão do tipo de informações confidenciais mostra os principais tipos de informações confidenciais que foram encontrados e rotulados em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="1bc11-138">The sensitive information type card shows the top sensitive information types that have been found and labeled across your organization.</span></span>

![principais tipos de informações confidenciais ](../media/data-classification-sens-info-types-card.png)

<span data-ttu-id="1bc11-140">Para saber quantos itens estão em uma determinada categoria de classificação, passe o mouse sobre a barra para determinar a categoria.</span><span class="sxs-lookup"><span data-stu-id="1bc11-140">To find out how many items are in any given classification category, hover over the bar for the category.</span></span>

![detalhe do hover exibindo os principais tipos de informações confidenciais  ](../media/data-classification-sens-info-types-hover.png)

> [!NOTE]
> <span data-ttu-id="1bc11-142">Se o cartão exibir a mensagem «não foram encontrados dados com informações confidenciais».</span><span class="sxs-lookup"><span data-stu-id="1bc11-142">If the card displays the message "No data found with sensitive information".</span></span> <span data-ttu-id="1bc11-143">Isso significa que não há nenhum item em sua organização que tenha sido classificado como sendo um tipo de informação confidencial ou nenhum item que tenha sido rastreado.</span><span class="sxs-lookup"><span data-stu-id="1bc11-143">It means that there are no items in your organization that have been classified as being a sensitive information type or no items that have been crawled.</span></span> <span data-ttu-id="1bc11-144">Para começar a usar os rótulos, confira:</span><span class="sxs-lookup"><span data-stu-id="1bc11-144">To get started with labels, see:</span></span>
>- [<span data-ttu-id="1bc11-145">Introdução ao rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="1bc11-145">Get started with sensitivity labels</span></span>](get-started-with-sensitivity-labels.md)
>- [<span data-ttu-id="1bc11-146">Introdução às políticas de retenção e rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="1bc11-146">Get started with retention policies and retention labels</span></span>](get-started-with-retention.md)
>- [<span data-ttu-id="1bc11-147">Definições da entidade do tipo de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="1bc11-147">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

## <a name="top-sensitivity-labels-applied-to-content"></a><span data-ttu-id="1bc11-148">Principais rótulos de confidencialidade aplicados ao conteúdo</span><span class="sxs-lookup"><span data-stu-id="1bc11-148">Top sensitivity labels applied to content</span></span>

<span data-ttu-id="1bc11-149">Quando você aplica um rótulo de confidencialidade a um item ou através do Microsoft 365 ou da proteção de informações do Azure (AIP), ocorrem duas coisas:</span><span class="sxs-lookup"><span data-stu-id="1bc11-149">When you apply a sensitivity label to an item either through Microsoft 365 or Azure Information Protection (AIP), two things happen:</span></span>

- <span data-ttu-id="1bc11-150">uma marca que indica o valor do item para a sua organização, inserida no documento, e o acompanhará onde quer que esse item vá</span><span class="sxs-lookup"><span data-stu-id="1bc11-150">a tag that indicates the value of the item to your org is embedded in the document and will follow it everywhere it goes</span></span>
- <span data-ttu-id="1bc11-151">a presença da marca ativa vários comportamentos de proteção, como uma marca d' água obrigatória ou a criptografia.</span><span class="sxs-lookup"><span data-stu-id="1bc11-151">the presence of the tag enables various protective behaviors, such as mandatory watermarking or encryption.</span></span> <span data-ttu-id="1bc11-152">Com a proteção de ponto de extremidade habilitada, você pode até mesmo impedir que um item saia de seu controle organizacional.</span><span class="sxs-lookup"><span data-stu-id="1bc11-152">With end point protection enabled you can even prevent an item from leaving your organizational control.</span></span>

<span data-ttu-id="1bc11-153">Para obter mais informações sobre rótulos de confidencialidade, confira: [Saiba mais sobre rótulos de confidencialidade](sensitivity-labels.md)</span><span class="sxs-lookup"><span data-stu-id="1bc11-153">For more information on sensitivity labels, see: [Learn about sensitivity labels](sensitivity-labels.md)</span></span>

<span data-ttu-id="1bc11-154">Os rótulos de confidencialidade devem ser habilitados para arquivos que estão no SharePoint e no OneDrive para que os dados correspondentes apareçam na página de classificação de dados.</span><span class="sxs-lookup"><span data-stu-id="1bc11-154">Sensitivity labels must be enabled for files that are in SharePoint and OneDrive in order for the corresponding data to surface in the data classification page.</span></span> <span data-ttu-id="1bc11-155">Para obter mais informações, confira [Habilitar rótulos de confidencialidade para arquivos do Office no Microsoft Office SharePoint Online e OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span><span class="sxs-lookup"><span data-stu-id="1bc11-155">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

<span data-ttu-id="1bc11-156">O cartão de identificação de confidencialidade mostra o número de itens (email ou documento) por nível de confidencialidade.</span><span class="sxs-lookup"><span data-stu-id="1bc11-156">The sensitivity label card shows the number of items (email or document) by sensitivity level.</span></span>

![Captura da tela do espaço reservado que mostra a análise de conteúdo por classificação de rótulo de confidencialidade](../media/data-classification-top-sensitivity-labels-applied.png)

> [!NOTE]
> <span data-ttu-id="1bc11-158">Se você ainda não criou ou publicou qualquer rótulo de confidencialidade ou se nenhum conteúdo tiver um rótulo de confidencialidade aplicado, esse cartão exibirá a mensagem "nenhum rótulo de confidencialidade detectado".</span><span class="sxs-lookup"><span data-stu-id="1bc11-158">If you haven't created or published any sensitivity labels or no content has had a sensitivity label applied, this card will display the message "No sensitivity labels detected".</span></span> <span data-ttu-id="1bc11-159">Para começar a usar os rótulos de confidencialidade, confira:</span><span class="sxs-lookup"><span data-stu-id="1bc11-159">To get started with sensitivity labels, see:</span></span>
>- <span data-ttu-id="1bc11-160">[Introdução aos rótulos de confidencialidade](get-started-with-sensitivity-labels.md) ou para AIP [Configurar a política de proteção de informações do Azure](https://docs.microsoft.com/azure/information-protection/configure-policy)</span><span class="sxs-lookup"><span data-stu-id="1bc11-160">[Get started with sensitivity labels](get-started-with-sensitivity-labels.md) or for AIP [Configure the Azure information protection policy](https://docs.microsoft.com/azure/information-protection/configure-policy)</span></span>

## <a name="top-retention-labels-applied-to-content"></a><span data-ttu-id="1bc11-161">Principais rótulos de retenção aplicados ao conteúdo</span><span class="sxs-lookup"><span data-stu-id="1bc11-161">Top retention labels applied to content</span></span>

<span data-ttu-id="1bc11-162">Os rótulos de retenção são usados para manejar a retenção e disposição do conteúdo de sua organização.</span><span class="sxs-lookup"><span data-stu-id="1bc11-162">Retention labels are used to manage the retention and disposition of content in your organization.</span></span> <span data-ttu-id="1bc11-163">Quando aplicados, eles podem ser usados para controlar como um documento será mantido antes da exclusão, se ele deve ser revisado antes da exclusão, quando o período de retenção expira e se ele deve ser marcado como um registro.</span><span class="sxs-lookup"><span data-stu-id="1bc11-163">When applied, they can be used to control how an item will be kept before deletion, whether it should be reviewed prior to deletion, when its retention period expires, and whether it should be marked as a record.</span></span> <span data-ttu-id="1bc11-164">Para obter mais informações, consulte [saiba mais sobre políticas e rótulos de retenção](retention.md).</span><span class="sxs-lookup"><span data-stu-id="1bc11-164">For more information, see [Learn about retention policies and retention labels](retention.md).</span></span>

<span data-ttu-id="1bc11-165">O cartão dos principais rótulos de retenção aplicados mostra quantos itens têm um determinado rótulo de retenção.</span><span class="sxs-lookup"><span data-stu-id="1bc11-165">The top applied retention labels card shows you how many items have a given retention label.</span></span>

![Captura de tela do espaço reservado mostrando os principais rótulos de retenção aplicados](../media/data-classification-top-retention-labels-applied.png)

> [!NOTE]
> <span data-ttu-id="1bc11-167">Se este cartão exibir a mensagem "Nenhum rótulo de retenção detectado", isso significa que você não criou ou publicou qualquer rótulo de retenção ou que nenhum conteúdo teve qualquer rótulo de retenção aplicado.  </span><span class="sxs-lookup"><span data-stu-id="1bc11-167">If this card displays the message, "No retention labels detected", it means you haven't created or published any retention labels or no content has had a retention label applied.</span></span> <span data-ttu-id="1bc11-168">Para começar a usar os rótulos de retenção, confira:</span><span class="sxs-lookup"><span data-stu-id="1bc11-168">To get started with retention labels, see:</span></span>
>- [<span data-ttu-id="1bc11-169">Introdução às políticas de retenção e rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="1bc11-169">Get started with retention policies and retention labels</span></span>](get-started-with-retention.md)

## <a name="top-activities-detected"></a><span data-ttu-id="1bc11-170">Atividades detectadas mais comuns</span><span class="sxs-lookup"><span data-stu-id="1bc11-170">Top activities detected</span></span>

<span data-ttu-id="1bc11-171">Este cartão fornece um resumo rápido das ações mais comuns que os usuários realizam com os itens rotulados como confidenciais.</span><span class="sxs-lookup"><span data-stu-id="1bc11-171">This card provides a quick summary of the most common actions that users are taking on the sensitivity labeled items.</span></span> <span data-ttu-id="1bc11-172">Você pode usar o [Explorador de atividades](data-classification-activity-explorer.md) para detalhar as oito diferentes atividades que o Microsoft 365 acompanha no conteúdo rotulado e o conteúdo localizado em pontos de extremidade do Windows 10.</span><span class="sxs-lookup"><span data-stu-id="1bc11-172">You can use the [Activity explorer](data-classification-activity-explorer.md) to drill deep down on eight different activities that Microsoft 365 tracks on labeled content and content that is located on Windows 10 endpoints.</span></span>

> [!NOTE]
> <span data-ttu-id="1bc11-173">Se esse cartão exibir a mensagem "Nenhuma atividade detectada", isso significa que não há nenhuma atividade nos arquivos ou que a auditoria de usuário e administradores não foi ativada.</span><span class="sxs-lookup"><span data-stu-id="1bc11-173">If this card displays the message, "No activity detected" it means that there's been no activity on the files or that user and admin auditing isn't turned on.</span></span> <span data-ttu-id="1bc11-174">Para ativar os logs de auditoria, confira:</span><span class="sxs-lookup"><span data-stu-id="1bc11-174">To turn the audit logs on , see:</span></span>
>- <span data-ttu-id="1bc11-175">[Pesquisar o log de auditoria no centro de conformidade e Segurança](search-the-audit-log-in-security-and-compliance.md) </span><span class="sxs-lookup"><span data-stu-id="1bc11-175">[Search the audit log in security & compliance center](search-the-audit-log-in-security-and-compliance.md)</span></span>

## <a name="sensitivity-and-retention-labeled-data-by-location"></a><span data-ttu-id="1bc11-176">Dados com rótulos de confidencialidade e retenção por local</span><span class="sxs-lookup"><span data-stu-id="1bc11-176">Sensitivity and retention labeled data by location</span></span>

<span data-ttu-id="1bc11-177">O objetivo do relatório de classificação de dados é fornecer visibilidade sobre o número de itens que têm o rótulo, bem como a sua localização.</span><span class="sxs-lookup"><span data-stu-id="1bc11-177">The point of the data classification reporting is to provide visibility into the number of items that have which label as well as their location.</span></span> <span data-ttu-id="1bc11-178">Esses cartões permitem saber quantos itens rotulados estão no Exchange, no SharePoint, OneDrive, etc.</span><span class="sxs-lookup"><span data-stu-id="1bc11-178">These cards let you know how many labeled items the are in Exchange, SharePoint, and OneDrive etc.</span></span>

> [!NOTE]
> <span data-ttu-id="1bc11-179">Se este cartão exibir a mensagem "Nenhum local detectado", isso significa que você não criou ou publicou qualquer rótulo de confidencialidade ou que nenhum conteúdo teve qualquer rótulo de retenção aplicado.  </span><span class="sxs-lookup"><span data-stu-id="1bc11-179">If this card displays the message, "No locations detected, it means you haven't created or published any sensitivity labels or no content has had a retention label applied.</span></span> <span data-ttu-id="1bc11-180">Para começar a usar os rótulos de confidencialidade, confira:</span><span class="sxs-lookup"><span data-stu-id="1bc11-180">To get started with sensitivity labels, see:</span></span>
>- [<span data-ttu-id="1bc11-181">Rótulos de confidencialidade </span><span class="sxs-lookup"><span data-stu-id="1bc11-181">Sensitivity labels</span></span>](sensitivity-labels.md)

## <a name="see-also"></a><span data-ttu-id="1bc11-182">Confira também</span><span class="sxs-lookup"><span data-stu-id="1bc11-182">See also</span></span>

- [<span data-ttu-id="1bc11-183">Exibir atividade do rótulo</span><span class="sxs-lookup"><span data-stu-id="1bc11-183">View label activity</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="1bc11-184">Exibir conteúdo rotulado</span><span class="sxs-lookup"><span data-stu-id="1bc11-184">View labeled content</span></span>](data-classification-content-explorer.md)
- [<span data-ttu-id="1bc11-185">Saiba mais sobre rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="1bc11-185">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="1bc11-186">Saiba mais sobre as políticas de retenção e os rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="1bc11-186">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="1bc11-187">Definições da entidade do tipo de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="1bc11-187">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="1bc11-188">Introdução aos classificadores treináveis (visualização)</span><span class="sxs-lookup"><span data-stu-id="1bc11-188">Getting started with trainable classifiers (preview)</span></span>](classifier-getting-started-with.md)
