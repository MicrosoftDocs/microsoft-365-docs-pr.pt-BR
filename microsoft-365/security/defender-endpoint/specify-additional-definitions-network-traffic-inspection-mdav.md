---
title: Especificar conjuntos de definições adicionais para inspeção de tráfego de rede para Microsoft Defender Antivírus
description: Especifique conjuntos de definições adicionais para inspeção de tráfego de rede para Microsoft Defender Antivírus.
keywords: Microsoft Defender Antivírus, antimalware, segurança, defensor, inspeção de tráfego de rede
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
ms.openlocfilehash: 82568df0a6ad2225fd31b4c0fa4a654710f1e98b
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300102"
---
# <a name="specify-additional-definition-sets-for-network-traffic-inspection"></a><span data-ttu-id="1aa5e-104">Especificar conjuntos de definições adicionais para inspeção de tráfego de rede</span><span class="sxs-lookup"><span data-stu-id="1aa5e-104">Specify additional definition sets for network traffic inspection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1aa5e-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="1aa5e-105">**Applies to:**</span></span>

- [<span data-ttu-id="1aa5e-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="1aa5e-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="1aa5e-107">Você pode especificar conjuntos de definições adicionais para inspeção de tráfego de rede usando a Política de Grupo.</span><span class="sxs-lookup"><span data-stu-id="1aa5e-107">You can specify additional definition sets for network traffic inspection using Group Policy.</span></span>

## <a name="use-group-policy-to-specify-additional-definition-sets-for-network-traffic-inspection"></a><span data-ttu-id="1aa5e-108">Usar a Política de Grupo para especificar conjuntos de definições adicionais para inspeção de tráfego de rede</span><span class="sxs-lookup"><span data-stu-id="1aa5e-108">Use Group Policy to specify additional definition sets for network traffic inspection</span></span>

1. <span data-ttu-id="1aa5e-109">No ponto de extremidade de gerenciamento da Política de Grupo, abra o Console de Gerenciamento de Política [de Grupo.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="1aa5e-109">On your Group Policy management endpoint, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="1aa5e-110">Vá para **Windows Componentes**  >  **Microsoft Defender Antivírus**  >  **Sistema de Inspeção de Rede.**</span><span class="sxs-lookup"><span data-stu-id="1aa5e-110">Go to **Windows Components** > **Microsoft Defender Antivirus** > **Network Inspection System**.</span></span> 

3. <span data-ttu-id="1aa5e-111">Selecione **Especificar conjuntos de definições adicionais para inspeção de tráfego de rede.**</span><span class="sxs-lookup"><span data-stu-id="1aa5e-111">Select **Specify additional definition sets for network traffic inspection**.</span></span> <span data-ttu-id="1aa5e-112">Por padrão, essa política é definida como **Não configurada**.</span><span class="sxs-lookup"><span data-stu-id="1aa5e-112">By default, this policy is set to **Not configured**.</span></span> 

4. <span data-ttu-id="1aa5e-113">Para editar a política, selecione o **link de configuração de política de** edição.</span><span class="sxs-lookup"><span data-stu-id="1aa5e-113">To edit the policy, select the **edit policy setting** link.</span></span>

5. <span data-ttu-id="1aa5e-114">Selecione **Habilitado** e, em seguida, na seção **Opções,** selecione **Mostrar...**.</span><span class="sxs-lookup"><span data-stu-id="1aa5e-114">Select **Enabled**, and then in the **Options** section, select **Show...**.</span></span>

6. <span data-ttu-id="1aa5e-115">Adicione entradas à lista e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="1aa5e-115">Add entries to the list, and then select **OK**.</span></span> 

   <span data-ttu-id="1aa5e-116">Cada entrada deve ser listada como um par de valores de nome, onde o nome é uma representação de cadeia de caracteres de um GUID de conjunto de definições.</span><span class="sxs-lookup"><span data-stu-id="1aa5e-116">Each entry must be listed as a name-value pair, where the name is a string representation of a definition set GUID.</span></span> <span data-ttu-id="1aa5e-117">Como exemplo, o GUID do conjunto de definições para habilitar a inteligência de segurança de teste é definido como: `{b54b6ac9-a737-498e-9120-6616ad3bf590}` .</span><span class="sxs-lookup"><span data-stu-id="1aa5e-117">As an example, the definition set GUID to enable test security intelligence is defined as: `{b54b6ac9-a737-498e-9120-6616ad3bf590}`.</span></span> <span data-ttu-id="1aa5e-118">O valor não é usado, portanto, recomendamos defini-lo como `0` .</span><span class="sxs-lookup"><span data-stu-id="1aa5e-118">The value is not used, so we recommend setting it to `0`.</span></span> 

7. <span data-ttu-id="1aa5e-119">Selecione **OK** e, em seguida, implante seu Objeto de Política de Grupo atualizado.</span><span class="sxs-lookup"><span data-stu-id="1aa5e-119">Select **OK**, and then deploy your updated Group Policy Object.</span></span> <span data-ttu-id="1aa5e-120">Consulte [Console de Gerenciamento de Política de Grupo](/windows/win32/srvnodes/group-policy).</span><span class="sxs-lookup"><span data-stu-id="1aa5e-120">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy).</span></span>

> [!TIP]
> <span data-ttu-id="1aa5e-121">Você está usando Objetos de Política de Grupo no local?</span><span class="sxs-lookup"><span data-stu-id="1aa5e-121">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="1aa5e-122">Veja como eles se traduzem na nuvem.</span><span class="sxs-lookup"><span data-stu-id="1aa5e-122">See how they translate in the cloud.</span></span> <span data-ttu-id="1aa5e-123">[Analisar seus objetos de política de grupo local usando a análise da](/mem/intune/configuration/group-policy-analytics)Política de Grupo em Microsoft Endpoint Manager - Visualização .</span><span class="sxs-lookup"><span data-stu-id="1aa5e-123">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="1aa5e-124">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="1aa5e-124">Related articles</span></span>

- [<span data-ttu-id="1aa5e-125">Microsoft Defender Antivirus no Windows 10</span><span class="sxs-lookup"><span data-stu-id="1aa5e-125">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
 
- [<span data-ttu-id="1aa5e-126">Ativar proteção fornecida pela nuvem</span><span class="sxs-lookup"><span data-stu-id="1aa5e-126">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)

- [<span data-ttu-id="1aa5e-127">Como criar e implantar políticas antimalware: serviço de proteção na nuvem</span><span class="sxs-lookup"><span data-stu-id="1aa5e-127">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)