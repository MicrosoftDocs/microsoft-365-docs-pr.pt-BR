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
ms.openlocfilehash: 6287e7c56f79b09a79c75d7e8b8273dbd5569057
ms.sourcegitcommit: 634abe8a237e27dfe82376e6ef32280aab5d4a27
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2020
ms.locfileid: "45005885"
---
# <a name="microsoft-threat-protection-preview-features"></a><span data-ttu-id="d6293-104">Recursos de prévia da proteção contra ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="d6293-104">Microsoft Threat Protection preview features</span></span>

<span data-ttu-id="d6293-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="d6293-105">**Applies to:**</span></span>
- <span data-ttu-id="d6293-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="d6293-106">Microsoft Threat Protection</span></span>


<span data-ttu-id="d6293-107">O serviço de proteção contra ameaças da Microsoft é atualizado constantemente para incluir novos recursos e aprimoramentos de recursos.</span><span class="sxs-lookup"><span data-stu-id="d6293-107">The Microsoft Threat Protection service is constantly being updated to include new feature enhancements and capabilities.</span></span>

<span data-ttu-id="d6293-108">Saiba mais sobre os novos recursos da versão prévia da proteção contra ameaças da Microsoft e esteja entre os primeiros a experimentar os recursos futuros, ativando a experiência de visualização.</span><span class="sxs-lookup"><span data-stu-id="d6293-108">Learn about new features in the Microsoft Threat Protection preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

<span data-ttu-id="d6293-109">Para saber mais sobre os novos recursos que estão disponíveis ao público em geral, confira [novidades da Proteção contra Ameaças da Microsoft](whats-new.md).</span><span class="sxs-lookup"><span data-stu-id="d6293-109">For more information on new capabilities that are generally available, see [What's new in Microsoft Threat Protection](whats-new.md).</span></span>

## <a name="turn-on-preview-features"></a><span data-ttu-id="d6293-110">Ativar recursos de visualização</span><span class="sxs-lookup"><span data-stu-id="d6293-110">Turn on preview features</span></span>
<span data-ttu-id="d6293-111">Você terá acesso aos próximos recursos nos quais pode fornecer comentários para ajudar a melhorar a experiência geral antes que os recursos estejam disponíveis.</span><span class="sxs-lookup"><span data-stu-id="d6293-111">You'll have access to upcoming features which you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="d6293-112">Ative a configuração de experiência de visualização para estar entre o primeiro a experimentar os recursos futuros.</span><span class="sxs-lookup"><span data-stu-id="d6293-112">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="d6293-113">No painel de navegação, selecione **configurações**.</span><span class="sxs-lookup"><span data-stu-id="d6293-113">In the navigation pane, select **Settings**.</span></span>

2. <span data-ttu-id="d6293-114">Selecione **proteção contra ameaças da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="d6293-114">Select **Microsoft Threat Protection**.</span></span>


3. <span data-ttu-id="d6293-115">Selecionar **recursos**  >  **de visualização ative os recursos de visualização**.</span><span class="sxs-lookup"><span data-stu-id="d6293-115">Select **Preview features** > **Turn on preview features**.</span></span> 

3. <span data-ttu-id="d6293-116">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d6293-116">Select **Save**.</span></span>

<span data-ttu-id="d6293-117">Você saberá que os recursos de visualização estão ativados ao ver que a caixa de seleção **ativar recursos de visualização** está marcada.</span><span class="sxs-lookup"><span data-stu-id="d6293-117">You'll know you have preview features turned on when you see that the **Turn on preview features** check box is selected.</span></span> 

## <a name="preview-features"></a><span data-ttu-id="d6293-118">Visualização prévia de recursos</span><span class="sxs-lookup"><span data-stu-id="d6293-118">Preview features</span></span>
<span data-ttu-id="d6293-119">Os seguintes recursos e aprimoramentos estão disponíveis atualmente na visualização:</span><span class="sxs-lookup"><span data-stu-id="d6293-119">The following features and enhancements are currently available on preview:</span></span>

- <span data-ttu-id="d6293-120">**[Tabelas de identidade e aplicativo](advanced-hunting-schema-tables.md)** — obtenha visibilidade em eventos de autenticação, consultas do Active Directory e atividades relacionadas a aplicativos com as tabelas [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)e [AppFileEvents](advanced-hunting-appfileevents-table.md) no esquema de caça avançada.</span><span class="sxs-lookup"><span data-stu-id="d6293-120">**[Identity and app tables](advanced-hunting-schema-tables.md)** — get visibility into authentication events, Active Directory queries, and app-related activity with the [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md), and [AppFileEvents](advanced-hunting-appfileevents-table.md) tables in the advanced hunting schema.</span></span>

- <span data-ttu-id="d6293-121">**[Ir](advanced-hunting-go-hunt.md)** para a busca, dinamizar rapidamente da investigação de um incidente para inspecionar um evento específico, um usuário, um dispositivo ou outros tipos de entidade usando recursos de [busca avançada](advanced-hunting-overview.md) baseados em consulta.</span><span class="sxs-lookup"><span data-stu-id="d6293-121">**[Go hunt](advanced-hunting-go-hunt.md)** — quickly pivot from investigating an incident to inspecting a specific event, a user, a device, or other entity types using query-based [advanced hunting](advanced-hunting-overview.md) capabilities.</span></span>

- <span data-ttu-id="d6293-122">**[Função fileprofile ()](advanced-hunting-fileprofile-function.md)** — use em suas consultas de [busca avançada](advanced-hunting-overview.md) para incorporar informações de arquivo abrangentes.</span><span class="sxs-lookup"><span data-stu-id="d6293-122">**[FileProfile() function](advanced-hunting-fileprofile-function.md)** — use in your [advanced hunting](advanced-hunting-overview.md) queries to incorporate comprehensive file information.</span></span>
