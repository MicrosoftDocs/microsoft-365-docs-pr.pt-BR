---
title: Configurar exclusões para Microsoft Defender Antivírus verificações
description: Você pode excluir arquivos (incluindo arquivos modificados por processos especificados) e pastas de serem verificados por Microsoft Defender Antivírus. Valide suas exclusões com o PowerShell.
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.technology: mde
ms.audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 7065aa7cd1975b2f5a38e79da8618ba3efdcdac5
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275115"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a><span data-ttu-id="853b2-104">Configurar e validar exclusões para Microsoft Defender Antivírus verificações</span><span class="sxs-lookup"><span data-stu-id="853b2-104">Configure and validate exclusions for Microsoft Defender Antivirus scans</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="853b2-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="853b2-105">**Applies to:**</span></span>

- [<span data-ttu-id="853b2-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="853b2-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="853b2-107">Você pode excluir determinados arquivos, pastas, processos e arquivos abertos por processo de Microsoft Defender Antivírus verificações.</span><span class="sxs-lookup"><span data-stu-id="853b2-107">You can exclude certain files, folders, processes, and process-opened files from Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="853b2-108">Essas exclusões se aplicam [](run-scan-microsoft-defender-antivirus.md)a [verificações agendadas,](scheduled-catch-up-scans-microsoft-defender-antivirus.md)verificações sob demanda e proteção e monitoramento sempre em [tempo real.](configure-real-time-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="853b2-108">Such exclusions apply to [scheduled scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md), [on-demand scans](run-scan-microsoft-defender-antivirus.md), and [always-on real-time protection and monitoring](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="853b2-109">As exclusões para arquivos abertos pelo processo só se aplicam à proteção em tempo real.</span><span class="sxs-lookup"><span data-stu-id="853b2-109">Exclusions for process-opened files only apply to real-time protection.</span></span>

## <a name="configure-and-validate-exclusions"></a><span data-ttu-id="853b2-110">Configurar e validar exclusões</span><span class="sxs-lookup"><span data-stu-id="853b2-110">Configure and validate exclusions</span></span>

<span data-ttu-id="853b2-111">Para configurar e validar exclusões, consulte o seguinte:</span><span class="sxs-lookup"><span data-stu-id="853b2-111">To configure and validate exclusions, see the following:</span></span>

- <span data-ttu-id="853b2-112">[Configure e valide exclusões com base no nome do arquivo, extensão e local da pasta.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="853b2-112">[Configure and validate exclusions based on file name, extension, and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="853b2-113">Você pode excluir arquivos de Microsoft Defender Antivírus com base em sua extensão de arquivo, nome de arquivo ou local.</span><span class="sxs-lookup"><span data-stu-id="853b2-113">You can exclude files from Microsoft Defender Antivirus scans based on their file extension, file name, or location.</span></span>

- <span data-ttu-id="853b2-114">[Configurar e validar exclusões para arquivos abertos por processos](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="853b2-114">[Configure and validate exclusions for files opened by processes](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="853b2-115">Você pode excluir arquivos de verificações que foram abertas por um processo específico.</span><span class="sxs-lookup"><span data-stu-id="853b2-115">You can exclude files from scans that have been opened by a specific process.</span></span>

## <a name="recommendations-for-defining-exclusions"></a><span data-ttu-id="853b2-116">Recomendações para definir exclusões</span><span class="sxs-lookup"><span data-stu-id="853b2-116">Recommendations for defining exclusions</span></span>

> [!IMPORTANT]
> <span data-ttu-id="853b2-117">Microsoft Defender Antivírus inclui muitas exclusões automáticas com base em comportamentos conhecidos do sistema operacional e arquivos de gerenciamento típicos, como aqueles usados no gerenciamento empresarial, gerenciamento de banco de dados e outros cenários e situações empresariais.</span><span class="sxs-lookup"><span data-stu-id="853b2-117">Microsoft Defender Antivirus includes many automatic exclusions based on known operating system behaviors and typical management files, such as those used in enterprise management, database management, and other enterprise scenarios and situations.</span></span>  
> 
> <span data-ttu-id="853b2-118">Definir exclusões reduz a proteção oferecida por Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="853b2-118">Defining exclusions lowers the protection offered by Microsoft Defender Antivirus.</span></span> <span data-ttu-id="853b2-119">Você sempre deve avaliar os riscos associados à implementação de exclusões, e você deve excluir apenas arquivos que você tem certeza de que não são mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="853b2-119">You should always evaluate the risks that are associated with implementing exclusions, and you should only exclude files that you are confident are not malicious.</span></span>

<span data-ttu-id="853b2-120">Lembre-se dos seguintes pontos ao definir exclusões:</span><span class="sxs-lookup"><span data-stu-id="853b2-120">Keep the following points in mind when you are defining exclusions:</span></span>  

- <span data-ttu-id="853b2-121">As exclusões são tecnicamente uma lacuna de proteção.</span><span class="sxs-lookup"><span data-stu-id="853b2-121">Exclusions are technically a protection gap.</span></span> <span data-ttu-id="853b2-122">Sempre considere mitigações ao definir exclusões.</span><span class="sxs-lookup"><span data-stu-id="853b2-122">Always consider mitigations when defining exclusions.</span></span> <span data-ttu-id="853b2-123">Outras mitigações podem ser tão simples quanto garantir que o local excluído tenha as listas de controle de acesso (ACLs) apropriadas, a política de auditoria, seja processada por um software atualizado, etc.</span><span class="sxs-lookup"><span data-stu-id="853b2-123">Other mitigations could be as simple as making sure the excluded location has the appropriate access-control lists (ACLs), audit policy, is processed by an up-to-date software, etc.</span></span>

- <span data-ttu-id="853b2-124">Revise as exclusões periodicamente.</span><span class="sxs-lookup"><span data-stu-id="853b2-124">Review the exclusions periodically.</span></span> <span data-ttu-id="853b2-125">Verifique novamente e reaplicação das mitigações como parte do processo de revisão.</span><span class="sxs-lookup"><span data-stu-id="853b2-125">Recheck and re-enforce the mitigations as part of the review process.</span></span>

- <span data-ttu-id="853b2-126">O ideal é evitar a definição de exclusões que pretendem ser proativas.</span><span class="sxs-lookup"><span data-stu-id="853b2-126">Ideally, avoid defining exclusions intending to be proactive.</span></span> <span data-ttu-id="853b2-127">Por exemplo, não exclua algo apenas porque você acha que pode ser um problema no futuro.</span><span class="sxs-lookup"><span data-stu-id="853b2-127">For instance, don't exclude something just because you think it might be a problem in the future.</span></span> <span data-ttu-id="853b2-128">Use exclusões apenas para problemas específicos, como aqueles relacionados ao desempenho ou à compatibilidade de aplicativos que as exclusões podem atenuar.</span><span class="sxs-lookup"><span data-stu-id="853b2-128">Use exclusions only for specific issues, such as those pertaining to performance or application compatibility that exclusions could mitigate.</span></span>

- <span data-ttu-id="853b2-129">Audite as alterações na lista de exclusão.</span><span class="sxs-lookup"><span data-stu-id="853b2-129">Audit the exclusion list changes.</span></span> <span data-ttu-id="853b2-130">O administrador de segurança deve preservar o contexto suficiente em torno do motivo pelo qual uma determinada exclusão foi adicionada.</span><span class="sxs-lookup"><span data-stu-id="853b2-130">The security admin should preserve enough context around why a certain exclusion was added.</span></span> <span data-ttu-id="853b2-131">Você deve ser capaz de fornecer resposta com um raciocínio específico sobre o motivo pelo qual um determinado caminho foi excluído.</span><span class="sxs-lookup"><span data-stu-id="853b2-131">You should be able to provide answer with specific reasoning as to why a certain path was excluded.</span></span>

## <a name="related-articles"></a><span data-ttu-id="853b2-132">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="853b2-132">Related articles</span></span>

- [<span data-ttu-id="853b2-133">Microsoft Defender Antivírus exclusões no Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="853b2-133">Microsoft Defender Antivirus exclusions on Windows Server 2016</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="853b2-134">Erros comuns a evitar ao definir exclusões</span><span class="sxs-lookup"><span data-stu-id="853b2-134">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
