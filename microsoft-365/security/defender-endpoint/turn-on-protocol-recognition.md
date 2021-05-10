---
title: Ativar o reconhecimento de protocolo para Microsoft Defender Antivírus
description: Ativar o reconhecimento de protocolo para Microsoft Defender Antivírus.
keywords: Microsoft Defender Antivírus, antimalware, segurança, defensor, reconhecimento de protocolo
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
ms.openlocfilehash: 890303a15618a0318db0421c9c80f270583e19bf
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52296462"
---
# <a name="turn-on-protocol-recognition"></a><span data-ttu-id="f8b01-104">Ativar o reconhecimento de protocolo</span><span class="sxs-lookup"><span data-stu-id="f8b01-104">Turn on protocol recognition</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f8b01-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="f8b01-105">**Applies to:**</span></span>

- [<span data-ttu-id="f8b01-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="f8b01-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="f8b01-107">Essa configuração de política permite configurar o reconhecimento de protocolo para proteção de rede contra explorações de vulnerabilidades conhecidas.</span><span class="sxs-lookup"><span data-stu-id="f8b01-107">This policy setting allows you to configure protocol recognition for network protection against exploits of known vulnerabilities.</span></span> <span data-ttu-id="f8b01-108">Se você habilitar ou não definir essa configuração, o reconhecimento de protocolo será habilitado.</span><span class="sxs-lookup"><span data-stu-id="f8b01-108">If you enable or do not configure this setting, protocol recognition will be enabled.</span></span> <span data-ttu-id="f8b01-109">Se você desabilitar essa configuração, o reconhecimento de protocolo será desabilitado.</span><span class="sxs-lookup"><span data-stu-id="f8b01-109">If you disable this setting, protocol recognition will be disabled.</span></span>

## <a name="use-group-policy-to-configure-protocol-recognition"></a><span data-ttu-id="f8b01-110">Usar a Política de Grupo para configurar o reconhecimento de protocolo</span><span class="sxs-lookup"><span data-stu-id="f8b01-110">Use Group Policy to configure protocol recognition</span></span>

1. <span data-ttu-id="f8b01-111">No ponto de extremidade de gerenciamento da Política de Grupo, abra o Console de Gerenciamento de Política [de Grupo.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="f8b01-111">On your Group Policy management endpoint, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="f8b01-112">Vá para **Configuração do** Computador  >  **Modelos Administrativos Windows**  >  **Componentes**  >  **Microsoft Defender Antivírus**  >  Sistema **de** Inspeção de Rede .</span><span class="sxs-lookup"><span data-stu-id="f8b01-112">Go to **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Network Inspection System**.</span></span> 

3. <span data-ttu-id="f8b01-113">Selecione **reconhecimento de protocolo**.</span><span class="sxs-lookup"><span data-stu-id="f8b01-113">Select **protocol recognition**.</span></span> <span data-ttu-id="f8b01-114">Por padrão, essa diretiva está habilitada.</span><span class="sxs-lookup"><span data-stu-id="f8b01-114">By default, this policy is enabled.</span></span> <span data-ttu-id="f8b01-115">Se definido **Não configurado,** a aposentadoria de definição será habilitada.</span><span class="sxs-lookup"><span data-stu-id="f8b01-115">If set **Not configured**, definition retirement is enabled.</span></span> 

4. <span data-ttu-id="f8b01-116">Para editar a política, selecione o **link de configuração de política de** edição.</span><span class="sxs-lookup"><span data-stu-id="f8b01-116">To edit the policy, select the **edit policy setting** link.</span></span>

5. <span data-ttu-id="f8b01-117">Selecione **Habilitado** e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f8b01-117">Select **Enabled**, and then select **OK**.</span></span>

6. <span data-ttu-id="f8b01-118">Implante seu objeto de Política de Grupo atualizado.</span><span class="sxs-lookup"><span data-stu-id="f8b01-118">Deploy your updated Group Policy Object.</span></span> <span data-ttu-id="f8b01-119">Consulte [Console de Gerenciamento de Política de Grupo](/windows/win32/srvnodes/group-policy).</span><span class="sxs-lookup"><span data-stu-id="f8b01-119">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy).</span></span>

> [!TIP]
> <span data-ttu-id="f8b01-120">Você está usando Objetos de Política de Grupo no local?</span><span class="sxs-lookup"><span data-stu-id="f8b01-120">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="f8b01-121">Veja como eles se traduzem na nuvem.</span><span class="sxs-lookup"><span data-stu-id="f8b01-121">See how they translate in the cloud.</span></span> <span data-ttu-id="f8b01-122">[Analisar seus objetos de política de grupo local usando a análise da](/mem/intune/configuration/group-policy-analytics)Política de Grupo em Microsoft Endpoint Manager - Visualização .</span><span class="sxs-lookup"><span data-stu-id="f8b01-122">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="f8b01-123">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="f8b01-123">Related articles</span></span>

- [<span data-ttu-id="f8b01-124">Microsoft Defender Antivirus no Windows 10</span><span class="sxs-lookup"><span data-stu-id="f8b01-124">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
 
- [<span data-ttu-id="f8b01-125">Ativar proteção fornecida pela nuvem</span><span class="sxs-lookup"><span data-stu-id="f8b01-125">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)

- [<span data-ttu-id="f8b01-126">Como criar e implantar políticas antimalware: serviço de proteção na nuvem</span><span class="sxs-lookup"><span data-stu-id="f8b01-126">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)