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
ms.date: 05/07/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 66b2e882a0f6de21e27dabb3a4bfe2fe113bcb32
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52296463"
---
# <a name="turn-on-definition-retirement"></a><span data-ttu-id="271ef-104">Ativar a aposentadoria de definição</span><span class="sxs-lookup"><span data-stu-id="271ef-104">Turn on definition retirement</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="271ef-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="271ef-105">**Applies to:**</span></span>

- [<span data-ttu-id="271ef-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="271ef-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="271ef-107">Você pode configurar a aposentadoria de definição usando a Política de Grupo.</span><span class="sxs-lookup"><span data-stu-id="271ef-107">You can configure definition retirement using Group Policy.</span></span> <span data-ttu-id="271ef-108">A aposentadoria de definição verifica se um computador tem as atualizações de segurança necessárias para protegê-lo contra uma vulnerabilidade específica.</span><span class="sxs-lookup"><span data-stu-id="271ef-108">Definition retirement checks to see if a computer has the required security updates necessary to protect it against a particular vulnerability.</span></span> <span data-ttu-id="271ef-109">Se o sistema não estiver vulnerável à exploração detectada por uma definição, essa definição será "retirada".</span><span class="sxs-lookup"><span data-stu-id="271ef-109">If the system is not vulnerable to the exploit detected by a definition, then that definition is "retired".</span></span> <span data-ttu-id="271ef-110">Se toda a inteligência de segurança de um determinado protocolo for retirada, esse protocolo não será mais analisado.</span><span class="sxs-lookup"><span data-stu-id="271ef-110">If all security intelligence for a given protocol are retired then that protocol is no longer parsed.</span></span> <span data-ttu-id="271ef-111">Habilenciar esse recurso ajuda a melhorar o desempenho.</span><span class="sxs-lookup"><span data-stu-id="271ef-111">Enabling this feature helps to improve performance.</span></span> <span data-ttu-id="271ef-112">Em um computador atualizado com todas as atualizações de segurança mais recentes, a proteção de rede não terá impacto no desempenho da rede.</span><span class="sxs-lookup"><span data-stu-id="271ef-112">On a computer that is up-to-date with all the latest security updates, network protection will have no impact on network performance.</span></span>

## <a name="use-group-policy-to-configure-definition-retirement"></a><span data-ttu-id="271ef-113">Usar a Política de Grupo para configurar a aposentadoria de definição</span><span class="sxs-lookup"><span data-stu-id="271ef-113">Use Group Policy to configure definition retirement</span></span>

1. <span data-ttu-id="271ef-114">No ponto de extremidade de gerenciamento da Política de Grupo, abra o Console de Gerenciamento de Política [de Grupo.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="271ef-114">On your Group Policy management endpoint, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="271ef-115">Vá para **Configuração do** Computador  >  **Modelos Administrativos Windows**  >  **Componentes**  >  **Microsoft Defender Antivírus**  >  Sistema **de** Inspeção de Rede .</span><span class="sxs-lookup"><span data-stu-id="271ef-115">Go to **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Network Inspection System**.</span></span> 

3. <span data-ttu-id="271ef-116">Selecione **Ativar a aposentadoria de definição**.</span><span class="sxs-lookup"><span data-stu-id="271ef-116">Select **Turn on definition retirement**.</span></span> <span data-ttu-id="271ef-117">Por padrão, essa diretiva está habilitada.</span><span class="sxs-lookup"><span data-stu-id="271ef-117">By default, this policy is enabled.</span></span> <span data-ttu-id="271ef-118">Se definido **Não configurado,** a aposentadoria de definição será habilitada.</span><span class="sxs-lookup"><span data-stu-id="271ef-118">If set **Not configured**, definition retirement is enabled.</span></span> 

4. <span data-ttu-id="271ef-119">Para editar a política, selecione o **link de configuração de política de** edição.</span><span class="sxs-lookup"><span data-stu-id="271ef-119">To edit the policy, select the **edit policy setting** link.</span></span>

5. <span data-ttu-id="271ef-120">Selecione **Habilitado** e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="271ef-120">Select **Enabled**, and then select **OK**.</span></span>

6. <span data-ttu-id="271ef-121">Implante seu objeto de Política de Grupo atualizado.</span><span class="sxs-lookup"><span data-stu-id="271ef-121">Deploy your updated Group Policy Object.</span></span> <span data-ttu-id="271ef-122">Consulte [Console de Gerenciamento de Política de Grupo](/windows/win32/srvnodes/group-policy).</span><span class="sxs-lookup"><span data-stu-id="271ef-122">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy).</span></span>

> [!TIP]
> <span data-ttu-id="271ef-123">Você está usando Objetos de Política de Grupo no local?</span><span class="sxs-lookup"><span data-stu-id="271ef-123">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="271ef-124">Veja como eles se traduzem na nuvem.</span><span class="sxs-lookup"><span data-stu-id="271ef-124">See how they translate in the cloud.</span></span> <span data-ttu-id="271ef-125">[Analisar seus objetos de política de grupo local usando a análise da](/mem/intune/configuration/group-policy-analytics)Política de Grupo em Microsoft Endpoint Manager - Visualização .</span><span class="sxs-lookup"><span data-stu-id="271ef-125">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="271ef-126">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="271ef-126">Related articles</span></span>

- [<span data-ttu-id="271ef-127">Microsoft Defender Antivirus no Windows 10</span><span class="sxs-lookup"><span data-stu-id="271ef-127">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
 
- [<span data-ttu-id="271ef-128">Ativar proteção fornecida pela nuvem</span><span class="sxs-lookup"><span data-stu-id="271ef-128">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)

- [<span data-ttu-id="271ef-129">Como criar e implantar políticas antimalware: serviço de proteção na nuvem</span><span class="sxs-lookup"><span data-stu-id="271ef-129">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)