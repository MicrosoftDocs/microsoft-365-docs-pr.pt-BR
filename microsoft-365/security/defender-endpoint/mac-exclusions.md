---
title: Configurar e validar exclusões do Microsoft Defender ATP para Mac
description: Fornecer e validar exclusões para o Microsoft Defender ATP para Mac. As exclusões podem ser definidas para arquivos, pastas e processos.
keywords: microsoft, defender, atp, mac, exclusões, verificações, antivírus
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
ms.openlocfilehash: 2281fccfb97d38dbdc218799b087290433deff30
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764152"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="a1fed-105">Configurar e validar exclusões do Microsoft Defender para Ponto de Extremidade no macOS</span><span class="sxs-lookup"><span data-stu-id="a1fed-105">Configure and validate exclusions for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a1fed-106">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="a1fed-106">**Applies to:**</span></span>
- [<span data-ttu-id="a1fed-107">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="a1fed-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a1fed-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a1fed-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a1fed-109">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="a1fed-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a1fed-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="a1fed-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="a1fed-111">Este artigo fornece informações sobre como definir exclusões que se aplicam a verificações sob demanda e proteção e monitoramento em tempo real.</span><span class="sxs-lookup"><span data-stu-id="a1fed-111">This article provides information on how to define exclusions that apply to on-demand scans, and real-time protection and monitoring.</span></span>

>[!IMPORTANT]
><span data-ttu-id="a1fed-112">As exclusões descritas neste artigo não se aplicam a outros recursos do Defender for Endpoint no Mac, incluindo a detecção e a resposta do ponto de extremidade (EDR).</span><span class="sxs-lookup"><span data-stu-id="a1fed-112">The exclusions described in this article don't apply to other Defender for Endpoint on Mac capabilities, including endpoint detection and response (EDR).</span></span> <span data-ttu-id="a1fed-113">Os arquivos excluídos usando os métodos descritos neste artigo ainda podem disparar alertas de EDR e outras detecções.</span><span class="sxs-lookup"><span data-stu-id="a1fed-113">Files that you exclude using the methods described in this article can still trigger EDR alerts and other detections.</span></span>

<span data-ttu-id="a1fed-114">Você pode excluir determinados arquivos, pastas, processos e arquivos abertos por processo do Defender para Ponto de Extremidade em verificações do Mac.</span><span class="sxs-lookup"><span data-stu-id="a1fed-114">You can exclude certain files, folders, processes, and process-opened files from Defender for Endpoint on Mac scans.</span></span>

<span data-ttu-id="a1fed-115">As exclusões podem ser úteis para evitar detecções incorretas em arquivos ou softwares exclusivos ou personalizados para sua organização.</span><span class="sxs-lookup"><span data-stu-id="a1fed-115">Exclusions can be useful to avoid incorrect detections on files or software that are unique or customized to your organization.</span></span> <span data-ttu-id="a1fed-116">Eles também podem ser úteis para reduzir problemas de desempenho causados pelo Defender para Ponto de Extremidade no Mac.</span><span class="sxs-lookup"><span data-stu-id="a1fed-116">They can also be useful for mitigating performance issues caused by Defender for Endpoint on Mac.</span></span>

>[!WARNING]
><span data-ttu-id="a1fed-117">Definir exclusões reduz a proteção oferecida pelo Defender para Ponto de Extremidade no Mac.</span><span class="sxs-lookup"><span data-stu-id="a1fed-117">Defining exclusions lowers the protection offered by Defender for Endpoint on Mac.</span></span> <span data-ttu-id="a1fed-118">Você sempre deve avaliar os riscos associados à implementação de exclusões, e você deve excluir apenas arquivos que você tem certeza de que não são mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="a1fed-118">You should always evaluate the risks that are associated with implementing exclusions, and you should only exclude files that you are confident are not malicious.</span></span>

## <a name="supported-exclusion-types"></a><span data-ttu-id="a1fed-119">Tipos de exclusão com suporte</span><span class="sxs-lookup"><span data-stu-id="a1fed-119">Supported exclusion types</span></span>

<span data-ttu-id="a1fed-120">A tabela a seguir mostra os tipos de exclusão suportados pelo Defender para Ponto de Extremidade no Mac.</span><span class="sxs-lookup"><span data-stu-id="a1fed-120">The follow table shows the exclusion types supported by Defender for Endpoint on Mac.</span></span>

<span data-ttu-id="a1fed-121">Exclusão</span><span class="sxs-lookup"><span data-stu-id="a1fed-121">Exclusion</span></span> | <span data-ttu-id="a1fed-122">Definição</span><span class="sxs-lookup"><span data-stu-id="a1fed-122">Definition</span></span> | <span data-ttu-id="a1fed-123">Exemplos</span><span class="sxs-lookup"><span data-stu-id="a1fed-123">Examples</span></span>
---|---|---
<span data-ttu-id="a1fed-124">Extensão de arquivo</span><span class="sxs-lookup"><span data-stu-id="a1fed-124">File extension</span></span> | <span data-ttu-id="a1fed-125">Todos os arquivos com a extensão, em qualquer lugar no computador</span><span class="sxs-lookup"><span data-stu-id="a1fed-125">All files with the extension, anywhere on the machine</span></span> | `.test`
<span data-ttu-id="a1fed-126">File</span><span class="sxs-lookup"><span data-stu-id="a1fed-126">File</span></span> | <span data-ttu-id="a1fed-127">Um arquivo específico identificado pelo caminho completo</span><span class="sxs-lookup"><span data-stu-id="a1fed-127">A specific file identified by the full path</span></span> | `/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
<span data-ttu-id="a1fed-128">Folder</span><span class="sxs-lookup"><span data-stu-id="a1fed-128">Folder</span></span> | <span data-ttu-id="a1fed-129">Todos os arquivos na pasta especificada (recursivamente)</span><span class="sxs-lookup"><span data-stu-id="a1fed-129">All files under the specified folder (recursively)</span></span> | `/var/log/`<br/>`/var/*/`
<span data-ttu-id="a1fed-130">Processo</span><span class="sxs-lookup"><span data-stu-id="a1fed-130">Process</span></span> | <span data-ttu-id="a1fed-131">Um processo específico (especificado pelo caminho completo ou nome do arquivo) e todos os arquivos abertos por ele</span><span class="sxs-lookup"><span data-stu-id="a1fed-131">A specific process (specified either by the full path or file name) and all files opened by it</span></span> | `/bin/cat`<br/>`cat`<br/>`c?t`

<span data-ttu-id="a1fed-132">As exclusões de arquivo, pasta e processo suportam os seguintes caracteres curinga:</span><span class="sxs-lookup"><span data-stu-id="a1fed-132">File, folder, and process exclusions support the following wildcards:</span></span>

<span data-ttu-id="a1fed-133">Curinga</span><span class="sxs-lookup"><span data-stu-id="a1fed-133">Wildcard</span></span> | <span data-ttu-id="a1fed-134">Descrição</span><span class="sxs-lookup"><span data-stu-id="a1fed-134">Description</span></span> | <span data-ttu-id="a1fed-135">Exemplo</span><span class="sxs-lookup"><span data-stu-id="a1fed-135">Example</span></span> | <span data-ttu-id="a1fed-136">Matches</span><span class="sxs-lookup"><span data-stu-id="a1fed-136">Matches</span></span> | <span data-ttu-id="a1fed-137">Não se iguala</span><span class="sxs-lookup"><span data-stu-id="a1fed-137">Does not match</span></span>
---|---|---|---|---
\* |    <span data-ttu-id="a1fed-138">Corresponde a qualquer número de caracteres, incluindo nenhum (observe que quando esse caractere curinga é usado dentro de um caminho, ele substituirá apenas uma pasta)</span><span class="sxs-lookup"><span data-stu-id="a1fed-138">Matches any number of any characters including none (note that when this wildcard is used inside a path it will substitute only one folder)</span></span> | `/var/*/*.log` | `/var/log/system.log` | `/var/log/nested/system.log`
<span data-ttu-id="a1fed-139">?</span><span class="sxs-lookup"><span data-stu-id="a1fed-139">?</span></span> | <span data-ttu-id="a1fed-140">Corresponde a qualquer caractere único</span><span class="sxs-lookup"><span data-stu-id="a1fed-140">Matches any single character</span></span> | `file?.log` | `file1.log`<br/>`file2.log` | `file123.log`

>[!NOTE]
><span data-ttu-id="a1fed-141">O produto tenta resolver firmlinks ao avaliar exclusões.</span><span class="sxs-lookup"><span data-stu-id="a1fed-141">The product attempts to resolve firmlinks when evaluating exclusions.</span></span> <span data-ttu-id="a1fed-142">A resolução de firmlink não funciona quando a exclusão contém caracteres curinga ou o arquivo de destino (no `Data` volume) não existe.</span><span class="sxs-lookup"><span data-stu-id="a1fed-142">Firmlink resolution does not work when the exclusion contains wildcards or the target file (on the `Data` volume) does not exist.</span></span>

## <a name="how-to-configure-the-list-of-exclusions"></a><span data-ttu-id="a1fed-143">Como configurar a lista de exclusões</span><span class="sxs-lookup"><span data-stu-id="a1fed-143">How to configure the list of exclusions</span></span>

### <a name="from-the-management-console"></a><span data-ttu-id="a1fed-144">No console de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="a1fed-144">From the management console</span></span>

<span data-ttu-id="a1fed-145">Para obter mais informações sobre como configurar exclusões de JAMF, Intune ou outro console de gerenciamento, consulte [Set preferences for Defender for Endpoint on Mac](mac-preferences.md).</span><span class="sxs-lookup"><span data-stu-id="a1fed-145">For more information on how to configure exclusions from JAMF, Intune, or another management console, see [Set preferences for Defender for Endpoint on Mac](mac-preferences.md).</span></span>

### <a name="from-the-user-interface"></a><span data-ttu-id="a1fed-146">Na interface do usuário</span><span class="sxs-lookup"><span data-stu-id="a1fed-146">From the user interface</span></span>

<span data-ttu-id="a1fed-147">Abra o aplicativo Defender para Ponto de Extremidade e navegue até **Gerenciar** configurações Adicionar ou Remover Exclusão... , conforme  >  mostrado na captura de tela a seguir:</span><span class="sxs-lookup"><span data-stu-id="a1fed-147">Open the Defender for Endpoint application and navigate to **Manage settings** > **Add or Remove Exclusion...**, as shown in the following screenshot:</span></span>

![Gerenciar captura de tela de exclusões](images/mdatp-37-exclusions.png)

<span data-ttu-id="a1fed-149">Selecione o tipo de exclusão que deseja adicionar e siga os prompts.</span><span class="sxs-lookup"><span data-stu-id="a1fed-149">Select the type of exclusion that you wish to add and follow the prompts.</span></span>

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a><span data-ttu-id="a1fed-150">Validar listas de exclusões com o arquivo de teste EICAR</span><span class="sxs-lookup"><span data-stu-id="a1fed-150">Validate exclusions lists with the EICAR test file</span></span>

<span data-ttu-id="a1fed-151">Você pode validar que suas listas de exclusão estão funcionando usando `curl` para baixar um arquivo de teste.</span><span class="sxs-lookup"><span data-stu-id="a1fed-151">You can validate that your exclusion lists are working by using `curl` to download a test file.</span></span>

<span data-ttu-id="a1fed-152">No trecho Bash a seguir, substitua por um arquivo que esteja em conformidade `test.txt` com suas regras de exclusão.</span><span class="sxs-lookup"><span data-stu-id="a1fed-152">In the following Bash snippet, replace `test.txt` with a file that conforms to your exclusion rules.</span></span> <span data-ttu-id="a1fed-153">Por exemplo, se você excluiu a `.testing` extensão, substitua `test.txt` por `test.testing` .</span><span class="sxs-lookup"><span data-stu-id="a1fed-153">For example, if you have excluded the `.testing` extension, replace `test.txt` with `test.testing`.</span></span> <span data-ttu-id="a1fed-154">Se você estiver testando um caminho, certifique-se de executar o comando nesse caminho.</span><span class="sxs-lookup"><span data-stu-id="a1fed-154">If you are testing a path, ensure that you run the command within that path.</span></span>

```bash
curl -o test.txt https://www.eicar.org/download/eicar.com.txt
```

<span data-ttu-id="a1fed-155">Se o Defender for Endpoint no Mac relata malware, a regra não está funcionando.</span><span class="sxs-lookup"><span data-stu-id="a1fed-155">If Defender for Endpoint on Mac reports malware, then the rule is not working.</span></span> <span data-ttu-id="a1fed-156">Se não houver nenhum relatório de malware e o arquivo baixado existir, a exclusão está funcionando.</span><span class="sxs-lookup"><span data-stu-id="a1fed-156">If there is no report of malware, and the downloaded file exists, then the exclusion is working.</span></span> <span data-ttu-id="a1fed-157">Você pode abrir o arquivo para confirmar se o conteúdo é igual ao descrito no site do arquivo de teste [EICAR.](http://2016.eicar.org/86-0-Intended-use.html)</span><span class="sxs-lookup"><span data-stu-id="a1fed-157">You can open the file to confirm that the contents are the same as what is described on the [EICAR test file website](http://2016.eicar.org/86-0-Intended-use.html).</span></span>

<span data-ttu-id="a1fed-158">Se você não tiver acesso à Internet, poderá criar seu próprio arquivo de teste EICAR.</span><span class="sxs-lookup"><span data-stu-id="a1fed-158">If you do not have Internet access, you can create your own EICAR test file.</span></span> <span data-ttu-id="a1fed-159">Escreva a cadeia de caracteres EICAR em um novo arquivo de texto com o seguinte comando Bash:</span><span class="sxs-lookup"><span data-stu-id="a1fed-159">Write the EICAR string to a new text file with the following Bash command:</span></span>

```bash
echo 'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*' > test.txt
```

<span data-ttu-id="a1fed-160">Você também pode copiar a cadeia de caracteres em um arquivo de texto em branco e tentar salvá-la com o nome do arquivo ou na pasta que você está tentando excluir.</span><span class="sxs-lookup"><span data-stu-id="a1fed-160">You can also copy the string into a blank text file and attempt to save it with the file name or in the folder you are attempting to exclude.</span></span>

## <a name="allow-threats"></a><span data-ttu-id="a1fed-161">Permitir ameaças</span><span class="sxs-lookup"><span data-stu-id="a1fed-161">Allow threats</span></span>

<span data-ttu-id="a1fed-162">Além de excluir determinado conteúdo de ser verificado, você também pode configurar o produto para não detectar algumas classes de ameaças (identificadas pelo nome da ameaça).</span><span class="sxs-lookup"><span data-stu-id="a1fed-162">In addition to excluding certain content from being scanned, you can also configure the product not to detect some classes of threats (identified by the threat name).</span></span> <span data-ttu-id="a1fed-163">Você deve ter cuidado ao usar essa funcionalidade, pois ela pode deixar seu dispositivo desprotegido.</span><span class="sxs-lookup"><span data-stu-id="a1fed-163">You should exercise caution when using this functionality, as it can leave your device unprotected.</span></span>

<span data-ttu-id="a1fed-164">Para adicionar um nome de ameaça à lista permitida, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="a1fed-164">To add a threat name to the allowed list, execute the following command:</span></span>

```bash
mdatp threat allowed add --name [threat-name]
```

<span data-ttu-id="a1fed-165">O nome da ameaça associado a uma detecção em seu dispositivo pode ser obtido usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="a1fed-165">The threat name associated with a detection on your device can be obtained using the following command:</span></span>

```bash
mdatp threat list
```

<span data-ttu-id="a1fed-166">Por exemplo, para adicionar (o nome de ameaça associado à detecção EICAR) à lista de `EICAR-Test-File (not a virus)` permissão, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="a1fed-166">For example, to add `EICAR-Test-File (not a virus)` (the threat name associated with the EICAR detection) to the allowed list, execute the following command:</span></span>

```bash
mdatp threat allowed add --name "EICAR-Test-File (not a virus)"
```
