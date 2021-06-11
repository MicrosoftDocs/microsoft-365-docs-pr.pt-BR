---
title: Ativar a aposentadoria por definição para Microsoft Defender Antivírus
description: Ativar a aposentadoria de definição para Microsoft Defender Antivírus.
keywords: Microsoft Defender Antivírus, antimalware, segurança, defensor, aposentadoria de definição
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 06/10/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 505270d319a78de20bf6fed01b7ca79c9fc2b400
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2021
ms.locfileid: "52903799"
---
# <a name="turn-on-definition-retirement"></a><span data-ttu-id="ec4a9-104">Ativar a aposentadoria de definição</span><span class="sxs-lookup"><span data-stu-id="ec4a9-104">Turn on definition retirement</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ec4a9-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="ec4a9-105">**Applies to:**</span></span>

- [<span data-ttu-id="ec4a9-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="ec4a9-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="ec4a9-107">Você pode configurar a aposentadoria de definição usando a Política de Grupo.</span><span class="sxs-lookup"><span data-stu-id="ec4a9-107">You can configure definition retirement using Group Policy.</span></span> <span data-ttu-id="ec4a9-108">A aposentadoria de definição verifica se um computador tem as atualizações de segurança necessárias para protegê-lo contra uma vulnerabilidade específica.</span><span class="sxs-lookup"><span data-stu-id="ec4a9-108">Definition retirement checks to see if a computer has the required security updates necessary to protect it against a particular vulnerability.</span></span> <span data-ttu-id="ec4a9-109">Se o sistema não estiver vulnerável à exploração detectada por uma definição, essa definição será "retirada".</span><span class="sxs-lookup"><span data-stu-id="ec4a9-109">If the system is not vulnerable to the exploit detected by a definition, then that definition is "retired".</span></span> <span data-ttu-id="ec4a9-110">Se toda a inteligência de segurança de um determinado protocolo for retirada, esse protocolo não será mais analisado.</span><span class="sxs-lookup"><span data-stu-id="ec4a9-110">If all security intelligence for a given protocol are retired then that protocol is no longer parsed.</span></span> <span data-ttu-id="ec4a9-111">Habilenciar esse recurso ajuda a melhorar o desempenho.</span><span class="sxs-lookup"><span data-stu-id="ec4a9-111">Enabling this feature helps to improve performance.</span></span> <span data-ttu-id="ec4a9-112">Em um computador atualizado com todas as atualizações de segurança mais recentes, a proteção de rede não terá impacto no desempenho da rede.</span><span class="sxs-lookup"><span data-stu-id="ec4a9-112">On a computer that is up-to-date with all the latest security updates, network protection will have no impact on network performance.</span></span>

## <a name="use-group-policy-to-configure-definition-retirement"></a><span data-ttu-id="ec4a9-113">Usar a Política de Grupo para configurar a aposentadoria de definição</span><span class="sxs-lookup"><span data-stu-id="ec4a9-113">Use Group Policy to configure definition retirement</span></span>

1. <span data-ttu-id="ec4a9-114">No ponto de extremidade de gerenciamento da Política de Grupo, abra o Console de Gerenciamento de Política [de Grupo.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="ec4a9-114">On your Group Policy management endpoint, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="ec4a9-115">Vá para **Configuração do** Computador  >  **Modelos Administrativos Windows**  >  **Componentes**  >  **Microsoft Defender Antivírus**  >  Sistema **de** Inspeção de Rede .</span><span class="sxs-lookup"><span data-stu-id="ec4a9-115">Go to **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Network Inspection System**.</span></span> 

3. <span data-ttu-id="ec4a9-116">Selecione **Ativar a aposentadoria de definição**.</span><span class="sxs-lookup"><span data-stu-id="ec4a9-116">Select **Turn on definition retirement**.</span></span> <span data-ttu-id="ec4a9-117">Por padrão, essa diretiva está habilitada.</span><span class="sxs-lookup"><span data-stu-id="ec4a9-117">By default, this policy is enabled.</span></span> <span data-ttu-id="ec4a9-118">Se definido **Não configurado,** a aposentadoria de definição será habilitada.</span><span class="sxs-lookup"><span data-stu-id="ec4a9-118">If set **Not configured**, definition retirement is enabled.</span></span> 

4. <span data-ttu-id="ec4a9-119">Para editar a política, selecione o **link de configuração de política de** edição.</span><span class="sxs-lookup"><span data-stu-id="ec4a9-119">To edit the policy, select the **edit policy setting** link.</span></span>

5. <span data-ttu-id="ec4a9-120">Selecione **Habilitado** e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="ec4a9-120">Select **Enabled**, and then select **OK**.</span></span>

6. <span data-ttu-id="ec4a9-121">Implante seu objeto de Política de Grupo atualizado.</span><span class="sxs-lookup"><span data-stu-id="ec4a9-121">Deploy your updated Group Policy Object.</span></span> <span data-ttu-id="ec4a9-122">Consulte [Console de Gerenciamento de Política de Grupo](/windows/win32/srvnodes/group-policy).</span><span class="sxs-lookup"><span data-stu-id="ec4a9-122">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy).</span></span>

> [!TIP]
> <span data-ttu-id="ec4a9-123">Você está usando Objetos de Política de Grupo no local?</span><span class="sxs-lookup"><span data-stu-id="ec4a9-123">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="ec4a9-124">Veja como eles se traduzem na nuvem.</span><span class="sxs-lookup"><span data-stu-id="ec4a9-124">See how they translate in the cloud.</span></span> <span data-ttu-id="ec4a9-125">[Analisar seus objetos de política de grupo local usando a análise da](/mem/intune/configuration/group-policy-analytics)Política de Grupo em Microsoft Endpoint Manager - Visualização .</span><span class="sxs-lookup"><span data-stu-id="ec4a9-125">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
