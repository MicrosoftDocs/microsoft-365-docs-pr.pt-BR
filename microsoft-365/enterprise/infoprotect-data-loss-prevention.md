---
title: 'Etapa 5: Configurar a Prevenção de Perda de Dados do Office 365'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Compreender e implantar a Prevenção de Perda de Dados do Office 365 no Microsoft 365.
ms.openlocfilehash: 43ebfb39202e407fe6dc7bb4c8e0fe8f906f7a6d
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370158"
---
# <a name="step-5-configure-office-365-data-loss-prevention"></a><span data-ttu-id="383b7-103">Etapa 5: Configurar a Prevenção de Perda de Dados do Office 365</span><span class="sxs-lookup"><span data-stu-id="383b7-103">Step 5: Configure Office 365 Data Loss Prevention</span></span>

<span data-ttu-id="383b7-104">*Esta etapa é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="383b7-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fase 6: proteção de informações](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="383b7-106">Com políticas de prevenção de perda de dados (DLP) na Central de Conformidade e Segurança do Office 365, você pode identificar, monitorar e proteger automaticamente informações confidenciais no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="383b7-106">With data loss prevention (DLP) policies in the Office 365 Security & Compliance center, you can identify, monitor, and automatically protect sensitive information across Microsoft 365.</span></span> <span data-ttu-id="383b7-107">Com políticas de DLP, você pode:</span><span class="sxs-lookup"><span data-stu-id="383b7-107">With DLP policies, you can:</span></span>

- <span data-ttu-id="383b7-108">Identificar informações confidenciais em vários locais, como no Exchange Online, SharePoint Online, OneDrive for Business e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="383b7-108">Identify sensitive information across many locations, such as Exchange Online, SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>
- <span data-ttu-id="383b7-109">Evitar o compartilhamento acidental de informações confidenciais, bloqueando o acesso a um documento ou bloqueando o email que o contém.</span><span class="sxs-lookup"><span data-stu-id="383b7-109">Prevent the accidental sharing of sensitive information by blocking access to a document or blocking the email that contains it.</span></span>
- <span data-ttu-id="383b7-110">Monitorar e proteger informações confidenciais nas versões para área de trabalho do Excel, PowerPoint e Word.</span><span class="sxs-lookup"><span data-stu-id="383b7-110">Monitor and protect sensitive information in the desktop versions of Excel, PowerPoint, and Word.</span></span>
- <span data-ttu-id="383b7-111">Ajudar os usuários a aprender como permanecer em conformidade sem interromper o fluxo de trabalho com notificações de emails e dicas de políticas.</span><span class="sxs-lookup"><span data-stu-id="383b7-111">Help users learn how to stay compliant without interrupting their workflow with email notifications and policy tips.</span></span> 
- <span data-ttu-id="383b7-112">Visualizar relatórios de DLP que mostrem conteúdo que corresponda às políticas de DLP da sua organização.</span><span class="sxs-lookup"><span data-stu-id="383b7-112">View DLP reports showing content that matches your organization's DLP policies.</span></span>

<span data-ttu-id="383b7-113">Uma política de DLP especifica:</span><span class="sxs-lookup"><span data-stu-id="383b7-113">A DLP policy specifies:</span></span>

- <span data-ttu-id="383b7-114">**Onde:** Locais como os sites do Exchange Online, SharePoint Online e OneDrive for Business, bem como bate-papos e canais do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="383b7-114">**Where:** Locations such as Exchange Online, SharePoint Online, and OneDrive for Business sites, as well as Microsoft Teams chats and channels.</span></span>
- <span data-ttu-id="383b7-115">**Quando:** Condições que o conteúdo deve cumprir em uma regra de política específica.</span><span class="sxs-lookup"><span data-stu-id="383b7-115">**When:** Conditions the content must match within a specific policy rule.</span></span>
- <span data-ttu-id="383b7-116">**Como:** Ações dentro dessa regra de política de correspondência a serem aplicadas automaticamente às condições correspondentes.</span><span class="sxs-lookup"><span data-stu-id="383b7-116">**How:** Actions within that matching policy rule to take automatically for the matching conditions.</span></span>

<span data-ttu-id="383b7-117">Em outras palavras:</span><span class="sxs-lookup"><span data-stu-id="383b7-117">In other words:</span></span>

- <span data-ttu-id="383b7-118">Para um documento neste local (onde), se o conteúdo corresponder às condições de uma regra (quando), então executar automaticamente as ações especificadas na regra (como).</span><span class="sxs-lookup"><span data-stu-id="383b7-118">For a document in this location (where), if the content matches the conditions of a rule (when), then automatically take the actions specified in the rule (how).</span></span>

<span data-ttu-id="383b7-119">Para determinar o conjunto de políticas de DLP que você precisa, você deve analisar seus documentos e os tipos de dados dentro deles que precisam de proteção contra perda de dados.</span><span class="sxs-lookup"><span data-stu-id="383b7-119">To determine the set of DLP policies you need, you must analyze your documents and the types of data within them that need protection from data loss.</span></span> <span data-ttu-id="383b7-120">Por exemplo, se você é uma organização financeira nos Estados Unidos da América, deve criar uma política de DLP que evite que documentos com números de seguridade social sejam compartilhados fora da organização ou enviados por email para locais fora da organização.</span><span class="sxs-lookup"><span data-stu-id="383b7-120">For example, if you are a financial organization in the United States of America, you would create a DLP policy that prevents documents with social security numbers from being shared outside the organization or sent in email to locations outside the organization.</span></span>

<span data-ttu-id="383b7-121">Em seguida, você configura e testa as políticas com os locais de teste para garantir o comportamento correto da DLP e minimizar falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="383b7-121">Next, you configure and test the policies with test locations to ensure the correct DLP behavior and to minimize false positives.</span></span>

<span data-ttu-id="383b7-122">Por fim, você o apresenta à sua organização, informando os funcionários sobre as novas políticas e o comportamento desejado e ampliando o escopo dos locais.</span><span class="sxs-lookup"><span data-stu-id="383b7-122">Finally, you roll it out to your organization by informing the employees of the new policies and their desired behavior and widening the scope of the locations.</span></span>

<span data-ttu-id="383b7-123">Para mais informações, confira [Introdução às recomendações de política de DLP](https://docs.microsoft.com/office365/securitycompliance/get-started-with-dlp-policy-recommendations).</span><span class="sxs-lookup"><span data-stu-id="383b7-123">For more information, see [Get started with DLP policy recommendations](https://docs.microsoft.com/office365/securitycompliance/get-started-with-dlp-policy-recommendations).</span></span>

<span data-ttu-id="383b7-124">Como um ponto de verificação provisório, confira o [Critério de saída](infoprotect-exit-criteria.md#crit-infoprotect-step5) correspondente desta etapa.</span><span class="sxs-lookup"><span data-stu-id="383b7-124">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step5) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="383b7-125">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="383b7-125">Next step</span></span>

|||
|:-------|:-----|
|![Etapa 6](./media/stepnumbers/Step6.png)|[<span data-ttu-id="383b7-127">Configurar criptografia de email</span><span class="sxs-lookup"><span data-stu-id="383b7-127">Configure email encryption</span></span>](infoprotect-email-encryption.md)|


