---
title: Solucionar problemas de instalação do Microsoft Defender ATP para Mac
description: Solucionar problemas de instalação no Microsoft Defender ATP para Mac.
keywords: microsoft, defender, atp, mac, install
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 888bffdb85adeb7af58504439c1c31c7232cd73b
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187620"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="24f71-104">Solucionar problemas de instalação do Microsoft Defender para Ponto de Extremidade para Mac</span><span class="sxs-lookup"><span data-stu-id="24f71-104">Troubleshoot installation issues for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="24f71-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="24f71-105">**Applies to:**</span></span>

- [<span data-ttu-id="24f71-106">Microsoft Defender para Ponto de Extremidade para Mac</span><span class="sxs-lookup"><span data-stu-id="24f71-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="24f71-107">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="24f71-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="24f71-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="24f71-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="24f71-109">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="24f71-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="24f71-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="24f71-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="installation-failed"></a><span data-ttu-id="24f71-111">Falha na instalação</span><span class="sxs-lookup"><span data-stu-id="24f71-111">Installation failed</span></span>

<span data-ttu-id="24f71-112">Para instalação manual, a página Resumo do assistente de instalação diz: "Ocorreu um erro durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="24f71-112">For manual installation, the Summary page of the installation wizard says, "An error occurred during installation.</span></span> <span data-ttu-id="24f71-113">O Instalador encontrou um erro que causou a falha da instalação.</span><span class="sxs-lookup"><span data-stu-id="24f71-113">The Installer encountered an error that caused the installation to fail.</span></span> <span data-ttu-id="24f71-114">Entre em contato com o fabricante do software para assistência."</span><span class="sxs-lookup"><span data-stu-id="24f71-114">Contact the software manufacturer for assistance."</span></span> <span data-ttu-id="24f71-115">Para implantações MDM, ele também é exibido como uma falha de instalação genérica.</span><span class="sxs-lookup"><span data-stu-id="24f71-115">For MDM deployments, it displays as a generic installation failure as well.</span></span>

<span data-ttu-id="24f71-116">Embora não seja exibido um erro exato para o usuário final, manteremos um arquivo de log com o progresso da instalação em `/Library/Logs/Microsoft/mdatp/install.log` .</span><span class="sxs-lookup"><span data-stu-id="24f71-116">While we do not display an exact error to the end user, we keep a log file with installation progress in `/Library/Logs/Microsoft/mdatp/install.log`.</span></span> <span data-ttu-id="24f71-117">Cada sessão de instalação é anexada a esse arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="24f71-117">Each installation session appends to this log file.</span></span> <span data-ttu-id="24f71-118">Você só pode `sed` usar para saída da última sessão de instalação:</span><span class="sxs-lookup"><span data-stu-id="24f71-118">You can use `sed` to output the last installation session only:</span></span>

```bash
sed -n 'H; /^preinstall com.microsoft.wdav begin/h; ${g;p;}' /Library/Logs/Microsoft/mdatp/install.log
```
```Output
preinstall com.microsoft.wdav begin [2020-03-11 13:08:49 -0700] 804
INSTALLER_SECURE_TEMP=/Library/InstallerSandboxes/.PKInstallSandboxManager/CB509765-70FC-4679-866D-8A14AD3F13CC.activeSandbox/89FA879B-971B-42BF-B4EA-7F5BB7CB5695
correlation id=CB509765-70FC-4679-866D-8A14AD3F13CC
[ERROR] Downgrade from 100.88.54 to 100.87.80 is not permitted
preinstall com.microsoft.wdav end [2020-03-11 13:08:49 -0700] 804 => 1
```

<span data-ttu-id="24f71-119">Neste exemplo, o motivo real é prefixado com `[ERROR]` .</span><span class="sxs-lookup"><span data-stu-id="24f71-119">In this example, the actual reason is prefixed with `[ERROR]`.</span></span>
<span data-ttu-id="24f71-120">A instalação falhou porque não há suporte para uma rebaixamento entre essas versões.</span><span class="sxs-lookup"><span data-stu-id="24f71-120">The installation failed because a downgrade between these versions is not supported.</span></span>

## <a name="mdatp-install-log-missing-or-not-updated"></a><span data-ttu-id="24f71-121">Log de instalação MDATP ausente ou não atualizado</span><span class="sxs-lookup"><span data-stu-id="24f71-121">MDATP install log missing or not updated</span></span>

<span data-ttu-id="24f71-122">Em casos raros, a instalação não deixa nenhum rastreamento no arquivo /Library/Logs/Microsoft/mdatp/install.log do MDATP.</span><span class="sxs-lookup"><span data-stu-id="24f71-122">In rare cases, installation leaves no trace in MDATP's /Library/Logs/Microsoft/mdatp/install.log file.</span></span>
<span data-ttu-id="24f71-123">Você pode verificar se ocorreu uma instalação e analisar possíveis erros consultando logs macOS (isso é útil na implantação do MDM, quando não há interface do usuário do cliente).</span><span class="sxs-lookup"><span data-stu-id="24f71-123">You can verify that an installation happened and analyze possible errors by querying macOS logs (this is helpful in MDM deployment, when there is no client UI).</span></span> <span data-ttu-id="24f71-124">Recomendamos que você use uma janela de tempo estreita para executar uma consulta e filtre pelo nome do processo de registro em log, pois haverá uma grande quantidade de informações.</span><span class="sxs-lookup"><span data-stu-id="24f71-124">We recommend that you use a narrow time window to run a query, and that you filter by the logging process name, as there will be a huge amount of information.</span></span>

```bash
grep '^2020-03-11 13:08' /var/log/install.log
```
```Output
log show --start '2020-03-11 13:00:00' --end '2020-03-11 13:08:50' --info --debug --source --predicate 'processImagePath CONTAINS[C] "install"' --style syslog
```
