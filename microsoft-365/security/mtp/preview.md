---
title: Recursos de visualização no Microsoft Threat Protection
description: Saiba mais sobre os novos recursos no Microsoft 365 Security
keywords: visualização, nova, M365 Security, Security, 365, Capabilities
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: b0703aa14bee3d14d1c3ff4fe46ea9d72de73ce2
ms.sourcegitcommit: eee4f651bd51d5aedd64e42d02bfed8ccb9be4cd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2020
ms.locfileid: "44515862"
---
# <a name="microsoft-threat-protection-preview-features"></a><span data-ttu-id="ee6f9-104">Recursos de prévia da proteção contra ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="ee6f9-104">Microsoft Threat Protection preview features</span></span>

<span data-ttu-id="ee6f9-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="ee6f9-105">**Applies to:**</span></span>
- <span data-ttu-id="ee6f9-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="ee6f9-106">Microsoft Threat Protection</span></span>


<span data-ttu-id="ee6f9-107">O serviço de proteção contra ameaças da Microsoft é atualizado constantemente para incluir novos recursos e aprimoramentos de recursos.</span><span class="sxs-lookup"><span data-stu-id="ee6f9-107">The Microsoft Threat Protection service is constantly being updated to include new feature enhancements and capabilities.</span></span>

<span data-ttu-id="ee6f9-108">Saiba mais sobre os novos recursos da versão prévia da proteção contra ameaças da Microsoft e esteja entre os primeiros a experimentar os recursos futuros, ativando a experiência de visualização.</span><span class="sxs-lookup"><span data-stu-id="ee6f9-108">Learn about new features in the Microsoft Threat Protection preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

<span data-ttu-id="ee6f9-109">Para saber mais sobre os novos recursos que estão disponíveis ao público em geral, confira [novidades da Proteção contra Ameaças da Microsoft](whats-new.md).</span><span class="sxs-lookup"><span data-stu-id="ee6f9-109">For more information on new capabilities that are generally available, see [What's new in Microsoft Threat Protection](whats-new.md).</span></span>

## <a name="turn-on-preview-features"></a><span data-ttu-id="ee6f9-110">Ativar recursos de visualização</span><span class="sxs-lookup"><span data-stu-id="ee6f9-110">Turn on preview features</span></span>
<span data-ttu-id="ee6f9-111">Você terá acesso aos próximos recursos nos quais pode fornecer comentários para ajudar a melhorar a experiência geral antes que os recursos estejam disponíveis.</span><span class="sxs-lookup"><span data-stu-id="ee6f9-111">You'll have access to upcoming features which you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="ee6f9-112">Ative a configuração de experiência de visualização para estar entre o primeiro a experimentar os recursos futuros.</span><span class="sxs-lookup"><span data-stu-id="ee6f9-112">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="ee6f9-113">No painel de navegação, selecione **configurações**.</span><span class="sxs-lookup"><span data-stu-id="ee6f9-113">In the navigation pane, select **Settings**.</span></span>

2. <span data-ttu-id="ee6f9-114">Selecione **proteção contra ameaças da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="ee6f9-114">Select **Microsoft Threat Protection**.</span></span>


3. <span data-ttu-id="ee6f9-115">Selecionar **recursos**  >  **de visualização ative os recursos de visualização**.</span><span class="sxs-lookup"><span data-stu-id="ee6f9-115">Select **Preview features** > **Turn on preview features**.</span></span> 

3. <span data-ttu-id="ee6f9-116">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ee6f9-116">Select **Save**.</span></span>

<span data-ttu-id="ee6f9-117">Você saberá que os recursos de visualização estão ativados ao ver que a caixa de seleção **ativar recursos de visualização** está marcada.</span><span class="sxs-lookup"><span data-stu-id="ee6f9-117">You'll know you have preview features turned on when you see that the **Turn on preview features** check box is selected.</span></span> 

## <a name="preview-features"></a><span data-ttu-id="ee6f9-118">Visualização prévia de recursos</span><span class="sxs-lookup"><span data-stu-id="ee6f9-118">Preview features</span></span>
<span data-ttu-id="ee6f9-119">Os seguintes recursos e aprimoramentos estão disponíveis atualmente na visualização:</span><span class="sxs-lookup"><span data-stu-id="ee6f9-119">The following features and enhancements are currently available on preview:</span></span>

- <span data-ttu-id="ee6f9-120">**[Tabelas de identidade e aplicativo](advanced-hunting-schema-tables.md)** — obtenha visibilidade em eventos de autenticação, consultas do Active Directory e atividades relacionadas a aplicativos com as tabelas [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)e [AppFileEvents](advanced-hunting-appfileevents-table.md) no esquema de caça avançada.</span><span class="sxs-lookup"><span data-stu-id="ee6f9-120">**[Identity and app tables](advanced-hunting-schema-tables.md)** — get visibility into authentication events, Active Directory queries, and app-related activity with the [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md), and [AppFileEvents](advanced-hunting-appfileevents-table.md) tables in the advanced hunting schema.</span></span>

- <span data-ttu-id="ee6f9-121">**[Tabela EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md)** — Use esta tabela para criar consultas de [busca avançada](advanced-hunting-overview.md) que verificam ações executadas nos emails depois de serem entregues às caixas de correio de destinatários.</span><span class="sxs-lookup"><span data-stu-id="ee6f9-121">**[EmailPostDeliveryEvents table](advanced-hunting-emailpostdeliveryevents-table.md)** — use this table to create [advanced hunting](advanced-hunting-overview.md) queries that check for actions taken on emails after they have been delivered to recipient mailboxes.</span></span>

- <span data-ttu-id="ee6f9-122">**[Função fileprofile ()](advanced-hunting-fileprofile-function.md)** — use em suas consultas de [busca avançada](advanced-hunting-overview.md) para incorporar informações de arquivo abrangentes.</span><span class="sxs-lookup"><span data-stu-id="ee6f9-122">**[FileProfile() function](advanced-hunting-fileprofile-function.md)** — use in your [advanced hunting](advanced-hunting-overview.md) queries to incorporate comprehensive file information.</span></span>
