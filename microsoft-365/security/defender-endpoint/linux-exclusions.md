---
title: Configurar e validar exclusões do Microsoft Defender para Ponto de Extremidade no Linux
description: Fornecer e validar exclusões para o Microsoft Defender para Ponto de Extremidade no Linux. As exclusões podem ser definidas para arquivos, pastas e processos.
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, exclusões, verificações, antivírus
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: bd506caa041af2585778fb3ecd7a40562463b17e
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346409"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="0b0f3-105">Configurar e validar exclusões do Microsoft Defender para Ponto de Extremidade no Linux</span><span class="sxs-lookup"><span data-stu-id="0b0f3-105">Configure and validate exclusions for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0b0f3-106">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="0b0f3-106">**Applies to:**</span></span>

- [<span data-ttu-id="0b0f3-107">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="0b0f3-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0b0f3-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0b0f3-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0b0f3-109">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="0b0f3-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0b0f3-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="0b0f3-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="0b0f3-111">Este artigo fornece informações sobre como definir exclusões que se aplicam a verificações sob demanda e proteção e monitoramento em tempo real.</span><span class="sxs-lookup"><span data-stu-id="0b0f3-111">This article provides information on how to define exclusions that apply to on-demand scans, and real-time protection and monitoring.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0b0f3-112">As exclusões descritas neste artigo não se aplicam a outros Recursos do Defender para Ponto de Extremidade no Linux, incluindo detecção e resposta de ponto de extremidade (EDR).</span><span class="sxs-lookup"><span data-stu-id="0b0f3-112">The exclusions described in this article don't apply to other Defender for Endpoint on Linux capabilities, including endpoint detection and response (EDR).</span></span> <span data-ttu-id="0b0f3-113">Os arquivos que você excluir usando os métodos descritos neste artigo ainda podem disparar EDR alertas e outras detecções.</span><span class="sxs-lookup"><span data-stu-id="0b0f3-113">Files that you exclude using the methods described in this article can still trigger EDR alerts and other detections.</span></span>

<span data-ttu-id="0b0f3-114">Você pode excluir determinados arquivos, pastas, processos e arquivos abertos por processo do Defender para Ponto de Extremidade em verificações do Linux.</span><span class="sxs-lookup"><span data-stu-id="0b0f3-114">You can exclude certain files, folders, processes, and process-opened files from Defender for Endpoint on Linux scans.</span></span>

<span data-ttu-id="0b0f3-115">As exclusões podem ser úteis para evitar detecções incorretas em arquivos ou softwares exclusivos ou personalizados para sua organização.</span><span class="sxs-lookup"><span data-stu-id="0b0f3-115">Exclusions can be useful to avoid incorrect detections on files or software that are unique or customized to your organization.</span></span> <span data-ttu-id="0b0f3-116">Eles também podem ser úteis para atenuar problemas de desempenho causados pelo Defender para Ponto de Extremidade no Linux.</span><span class="sxs-lookup"><span data-stu-id="0b0f3-116">They can also be useful for mitigating performance issues caused by Defender for Endpoint on Linux.</span></span>

> [!WARNING]
> <span data-ttu-id="0b0f3-117">Definir exclusões reduz a proteção oferecida pelo Defender para Ponto de Extremidade no Linux.</span><span class="sxs-lookup"><span data-stu-id="0b0f3-117">Defining exclusions lowers the protection offered by Defender for Endpoint on Linux.</span></span> <span data-ttu-id="0b0f3-118">Você sempre deve avaliar os riscos associados à implementação de exclusões, e você deve excluir apenas arquivos que você tem certeza de que não são mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="0b0f3-118">You should always evaluate the risks that are associated with implementing exclusions, and you should only exclude files that you are confident are not malicious.</span></span>

## <a name="supported-exclusion-types"></a><span data-ttu-id="0b0f3-119">Tipos de exclusão com suporte</span><span class="sxs-lookup"><span data-stu-id="0b0f3-119">Supported exclusion types</span></span>

<span data-ttu-id="0b0f3-120">A tabela a seguir mostra os tipos de exclusão suportados pelo Defender para Ponto de Extremidade no Linux.</span><span class="sxs-lookup"><span data-stu-id="0b0f3-120">The follow table shows the exclusion types supported by Defender for Endpoint on Linux.</span></span>

<span data-ttu-id="0b0f3-121">Exclusão</span><span class="sxs-lookup"><span data-stu-id="0b0f3-121">Exclusion</span></span> | <span data-ttu-id="0b0f3-122">Definição</span><span class="sxs-lookup"><span data-stu-id="0b0f3-122">Definition</span></span> | <span data-ttu-id="0b0f3-123">Exemplos</span><span class="sxs-lookup"><span data-stu-id="0b0f3-123">Examples</span></span>
---|---|---
<span data-ttu-id="0b0f3-124">Extensão de arquivo</span><span class="sxs-lookup"><span data-stu-id="0b0f3-124">File extension</span></span> | <span data-ttu-id="0b0f3-125">Todos os arquivos com a extensão, em qualquer lugar do dispositivo</span><span class="sxs-lookup"><span data-stu-id="0b0f3-125">All files with the extension, anywhere on the device</span></span> | `.test`
<span data-ttu-id="0b0f3-126">File</span><span class="sxs-lookup"><span data-stu-id="0b0f3-126">File</span></span> | <span data-ttu-id="0b0f3-127">Um arquivo específico identificado pelo caminho completo</span><span class="sxs-lookup"><span data-stu-id="0b0f3-127">A specific file identified by the full path</span></span> | `/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
<span data-ttu-id="0b0f3-128">Pasta</span><span class="sxs-lookup"><span data-stu-id="0b0f3-128">Folder</span></span> | <span data-ttu-id="0b0f3-129">Todos os arquivos na pasta especificada (recursivamente)</span><span class="sxs-lookup"><span data-stu-id="0b0f3-129">All files under the specified folder (recursively)</span></span> | `/var/log/`<br/>`/var/*/`
<span data-ttu-id="0b0f3-130">Processo</span><span class="sxs-lookup"><span data-stu-id="0b0f3-130">Process</span></span> | <span data-ttu-id="0b0f3-131">Um processo específico (especificado pelo caminho completo ou nome do arquivo) e todos os arquivos abertos por ele</span><span class="sxs-lookup"><span data-stu-id="0b0f3-131">A specific process (specified either by the full path or file name) and all files opened by it</span></span> | `/bin/cat`<br/>`cat`<br/>`c?t`

> [!IMPORTANT]
> <span data-ttu-id="0b0f3-132">Os caminhos acima devem ser links rígidos, não links simbólicos, para serem excluídos com êxito.</span><span class="sxs-lookup"><span data-stu-id="0b0f3-132">The paths above must be hard links, not symbolic links, in order to be successfully excluded.</span></span> <span data-ttu-id="0b0f3-133">Você pode verificar se um caminho é um link simbólico executando `file <path-name>` .</span><span class="sxs-lookup"><span data-stu-id="0b0f3-133">You can check if a path is a symbolic link by running `file <path-name>`.</span></span>

<span data-ttu-id="0b0f3-134">As exclusões de arquivo, pasta e processo suportam os seguintes caracteres curinga:</span><span class="sxs-lookup"><span data-stu-id="0b0f3-134">File, folder, and process exclusions support the following wildcards:</span></span>

<span data-ttu-id="0b0f3-135">Curinga</span><span class="sxs-lookup"><span data-stu-id="0b0f3-135">Wildcard</span></span> | <span data-ttu-id="0b0f3-136">Descrição</span><span class="sxs-lookup"><span data-stu-id="0b0f3-136">Description</span></span> | <span data-ttu-id="0b0f3-137">Exemplo</span><span class="sxs-lookup"><span data-stu-id="0b0f3-137">Example</span></span> | <span data-ttu-id="0b0f3-138">Matches</span><span class="sxs-lookup"><span data-stu-id="0b0f3-138">Matches</span></span> | <span data-ttu-id="0b0f3-139">Não se iguala</span><span class="sxs-lookup"><span data-stu-id="0b0f3-139">Does not match</span></span>
---|---|---|---|---
\* |    <span data-ttu-id="0b0f3-140">Corresponde a qualquer número de caracteres, incluindo nenhum (observe que quando esse caractere curinga é usado dentro de um caminho, ele substituirá apenas uma pasta)</span><span class="sxs-lookup"><span data-stu-id="0b0f3-140">Matches any number of any characters including none (note that when this wildcard is used inside a path it will substitute only one folder)</span></span> | `/var/\*/\*.log` | `/var/log/system.log` | `/var/log/nested/system.log`
<span data-ttu-id="0b0f3-141">?</span><span class="sxs-lookup"><span data-stu-id="0b0f3-141">?</span></span> | <span data-ttu-id="0b0f3-142">Corresponde a qualquer caractere único</span><span class="sxs-lookup"><span data-stu-id="0b0f3-142">Matches any single character</span></span> | `file?.log` | `file1.log`<br/>`file2.log` | `file123.log`

## <a name="how-to-configure-the-list-of-exclusions"></a><span data-ttu-id="0b0f3-143">Como configurar a lista de exclusões</span><span class="sxs-lookup"><span data-stu-id="0b0f3-143">How to configure the list of exclusions</span></span>

### <a name="from-the-management-console"></a><span data-ttu-id="0b0f3-144">No console de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="0b0f3-144">From the management console</span></span>

<span data-ttu-id="0b0f3-145">Para obter mais informações sobre como configurar exclusões de Puppet, Ansible ou outro console de gerenciamento, consulte [Set preferences for Defender for Endpoint on Linux](linux-preferences.md).</span><span class="sxs-lookup"><span data-stu-id="0b0f3-145">For more information on how to configure exclusions from Puppet, Ansible, or another management console, see [Set preferences for Defender for Endpoint on Linux](linux-preferences.md).</span></span>

### <a name="from-the-command-line"></a><span data-ttu-id="0b0f3-146">Da linha de comando</span><span class="sxs-lookup"><span data-stu-id="0b0f3-146">From the command line</span></span>

<span data-ttu-id="0b0f3-147">Execute o seguinte comando para ver as opções disponíveis para gerenciar exclusões:</span><span class="sxs-lookup"><span data-stu-id="0b0f3-147">Run the following command to see the available switches for managing exclusions:</span></span>

```bash
mdatp exclusion
```

> [!TIP]
> <span data-ttu-id="0b0f3-148">Ao configurar exclusões com caracteres curinga, coloque o parâmetro entre aspas duplas para evitar a duplicação.</span><span class="sxs-lookup"><span data-stu-id="0b0f3-148">When configuring exclusions with wildcards, enclose the parameter in double-quotes to prevent globbing.</span></span>

<span data-ttu-id="0b0f3-149">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="0b0f3-149">Examples:</span></span>

- <span data-ttu-id="0b0f3-150">Adicione uma exclusão para uma extensão de arquivo:</span><span class="sxs-lookup"><span data-stu-id="0b0f3-150">Add an exclusion for a file extension:</span></span>

    ```bash
    mdatp exclusion extension add --name .txt
    ```
    ```Output
    Extension exclusion configured successfully
    ```

- <span data-ttu-id="0b0f3-151">Adicione uma exclusão para um arquivo:</span><span class="sxs-lookup"><span data-stu-id="0b0f3-151">Add an exclusion for a file:</span></span>

    ```bash
    mdatp exclusion file add --path /var/log/dummy.log
    ```
    ```Output
    File exclusion configured successfully
    ```

- <span data-ttu-id="0b0f3-152">Adicione uma exclusão para uma pasta:</span><span class="sxs-lookup"><span data-stu-id="0b0f3-152">Add an exclusion for a folder:</span></span>

    ```bash
    mdatp exclusion folder add --path /var/log/
    ```
    ```Output
    Folder exclusion configured successfully
    ```

- <span data-ttu-id="0b0f3-153">Adicione uma exclusão para uma pasta com um caractere curinga:</span><span class="sxs-lookup"><span data-stu-id="0b0f3-153">Add an exclusion for a folder with a wildcard in it:</span></span>

    ```bash
    mdatp exclusion folder add --path "/var/*/"
    ```

    > [!NOTE]
    > <span data-ttu-id="0b0f3-154">Isso excluirá apenas caminhos um nível abaixo */var/*, mas não pastas que estão mais profundamente aninhadas; por exemplo, */var/this-subfolder/but-not-this-subfolder*.</span><span class="sxs-lookup"><span data-stu-id="0b0f3-154">This will only exclude paths one level below */var/*, but not folders which are more deeply nested; for example, */var/this-subfolder/but-not-this-subfolder*.</span></span>
    
    ```bash
    mdatp exclusion folder add --path "/var/"
    ```
    > [!NOTE]
    > <span data-ttu-id="0b0f3-155">Isso excluirá todos os caminhos cujos pais *são /var/*; por exemplo, */var/this-subfolder/and-this-subfolder-as-well*.</span><span class="sxs-lookup"><span data-stu-id="0b0f3-155">This will exclude all paths whose parent is */var/*; for example, */var/this-subfolder/and-this-subfolder-as-well*.</span></span>

    ```Output
    Folder exclusion configured successfully
    ```

- <span data-ttu-id="0b0f3-156">Adicione uma exclusão para um processo:</span><span class="sxs-lookup"><span data-stu-id="0b0f3-156">Add an exclusion for a process:</span></span>

    ```bash
    mdatp exclusion process add --name cat
    ```
    ```Output    
    Process exclusion configured successfully
    ```

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a><span data-ttu-id="0b0f3-157">Validar listas de exclusões com o arquivo de teste EICAR</span><span class="sxs-lookup"><span data-stu-id="0b0f3-157">Validate exclusions lists with the EICAR test file</span></span>

<span data-ttu-id="0b0f3-158">Você pode validar que suas listas de exclusão estão funcionando usando `curl` para baixar um arquivo de teste.</span><span class="sxs-lookup"><span data-stu-id="0b0f3-158">You can validate that your exclusion lists are working by using `curl` to download a test file.</span></span>

<span data-ttu-id="0b0f3-159">No trecho Bash a seguir, substitua por um arquivo que esteja em conformidade `test.txt` com suas regras de exclusão.</span><span class="sxs-lookup"><span data-stu-id="0b0f3-159">In the following Bash snippet, replace `test.txt` with a file that conforms to your exclusion rules.</span></span> <span data-ttu-id="0b0f3-160">Por exemplo, se você excluiu a `.testing` extensão, substitua `test.txt` por `test.testing` .</span><span class="sxs-lookup"><span data-stu-id="0b0f3-160">For example, if you have excluded the `.testing` extension, replace `test.txt` with `test.testing`.</span></span> <span data-ttu-id="0b0f3-161">Se você estiver testando um caminho, certifique-se de executar o comando nesse caminho.</span><span class="sxs-lookup"><span data-stu-id="0b0f3-161">If you are testing a path, ensure that you run the command within that path.</span></span>

```bash
curl -o test.txt https://www.eicar.org/download/eicar.com.txt
```

<span data-ttu-id="0b0f3-162">Se o Defender for Endpoint no Linux relata malware, a regra não está funcionando.</span><span class="sxs-lookup"><span data-stu-id="0b0f3-162">If Defender for Endpoint on Linux reports malware, then the rule is not working.</span></span> <span data-ttu-id="0b0f3-163">Se não houver nenhum relatório de malware e o arquivo baixado existir, a exclusão está funcionando.</span><span class="sxs-lookup"><span data-stu-id="0b0f3-163">If there is no report of malware, and the downloaded file exists, then the exclusion is working.</span></span> <span data-ttu-id="0b0f3-164">Você pode abrir o arquivo para confirmar se o conteúdo é igual ao descrito no site do arquivo de teste [EICAR.](http://2016.eicar.org/86-0-Intended-use.html)</span><span class="sxs-lookup"><span data-stu-id="0b0f3-164">You can open the file to confirm that the contents are the same as what is described on the [EICAR test file website](http://2016.eicar.org/86-0-Intended-use.html).</span></span>

<span data-ttu-id="0b0f3-165">Se você não tiver acesso à Internet, poderá criar seu próprio arquivo de teste EICAR.</span><span class="sxs-lookup"><span data-stu-id="0b0f3-165">If you do not have Internet access, you can create your own EICAR test file.</span></span> <span data-ttu-id="0b0f3-166">Escreva a cadeia de caracteres EICAR em um novo arquivo de texto com o seguinte comando Bash:</span><span class="sxs-lookup"><span data-stu-id="0b0f3-166">Write the EICAR string to a new text file with the following Bash command:</span></span>

```bash
echo 'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*' > test.txt
```

<span data-ttu-id="0b0f3-167">Você também pode copiar a cadeia de caracteres em um arquivo de texto em branco e tentar salvá-la com o nome do arquivo ou na pasta que você está tentando excluir.</span><span class="sxs-lookup"><span data-stu-id="0b0f3-167">You can also copy the string into a blank text file and attempt to save it with the file name or in the folder you are attempting to exclude.</span></span>

## <a name="allow-threats"></a><span data-ttu-id="0b0f3-168">Permitir ameaças</span><span class="sxs-lookup"><span data-stu-id="0b0f3-168">Allow threats</span></span>

<span data-ttu-id="0b0f3-169">Além de excluir determinado conteúdo de ser verificado, você também pode configurar o produto para não detectar algumas classes de ameaças (identificadas pelo nome da ameaça).</span><span class="sxs-lookup"><span data-stu-id="0b0f3-169">In addition to excluding certain content from being scanned, you can also configure the product not to detect some classes of threats (identified by the threat name).</span></span> <span data-ttu-id="0b0f3-170">Você deve ter cuidado ao usar essa funcionalidade, pois ela pode deixar seu dispositivo desprotegido.</span><span class="sxs-lookup"><span data-stu-id="0b0f3-170">You should exercise caution when using this functionality, as it can leave your device unprotected.</span></span>

<span data-ttu-id="0b0f3-171">Para adicionar um nome de ameaça à lista permitida, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="0b0f3-171">To add a threat name to the allowed list, execute the following command:</span></span>

```bash
mdatp threat allowed add --name [threat-name]
```

<span data-ttu-id="0b0f3-172">O nome da ameaça associado a uma detecção em seu dispositivo pode ser obtido usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="0b0f3-172">The threat name associated with a detection on your device can be obtained using the following command:</span></span>

```bash
mdatp threat list
```

<span data-ttu-id="0b0f3-173">Por exemplo, para adicionar (o nome de ameaça associado à detecção EICAR) à lista de `EICAR-Test-File (not a virus)` permissão, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="0b0f3-173">For example, to add `EICAR-Test-File (not a virus)` (the threat name associated with the EICAR detection) to the allowed list, execute the following command:</span></span>

```bash
mdatp threat allowed add --name "EICAR-Test-File (not a virus)"
```
