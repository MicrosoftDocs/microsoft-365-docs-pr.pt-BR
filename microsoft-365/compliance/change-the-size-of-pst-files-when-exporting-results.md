---
title: Alterar o tamanho dos arquivos PST ao exportar os resultados da pesquisa de descoberta eletrônica
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: Você pode alterar o tamanho padrão dos arquivos PST que são baixados para o seu computador quando exporta os resultados da pesquisa de descoberta eletrônica.
ms.openlocfilehash: b3bba45ce336b143ed948db384673f0a1a5a456f
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2019
ms.locfileid: "38684930"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a><span data-ttu-id="82b5e-103">Alterar o tamanho dos arquivos PST ao exportar os resultados da pesquisa de descoberta eletrônica</span><span class="sxs-lookup"><span data-stu-id="82b5e-103">Change the size of PST files when exporting eDiscovery search results</span></span>

<span data-ttu-id="82b5e-104">Ao usar a ferramenta de exportação de descoberta eletrônica do Office 365 para exportar os resultados de email de uma pesquisa de descoberta eletrônica das diferentes ferramentas de descoberta eletrônica da Microsoft, o tamanho padrão de um arquivo PST que pode ser exportado é de 10 GB.</span><span class="sxs-lookup"><span data-stu-id="82b5e-104">When you use the Office 365 eDiscovery Export tool to export the email results of an eDiscovery search from the different Microsoft eDiscovery tools, the default size of a PST file that can be exported is 10 GB.</span></span> <span data-ttu-id="82b5e-105">Se você quiser alterar esse tamanho padrão, poderá editar o registro do Windows no computador que você usa para exportar os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="82b5e-105">If you want to change this default size, you can edit the Windows Registry on the computer that you use to export the search results.</span></span> <span data-ttu-id="82b5e-106">Uma razão para fazer isso é que um arquivo PST pode se ajustar em mídia removível, como DVD, CD ou unidade USB.</span><span class="sxs-lookup"><span data-stu-id="82b5e-106">One reason to do this is so a PST file can fit on removable media, such a DVD, a compact disc, or a USB drive.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="82b5e-107">A ferramenta de exportação de descoberta eletrônica do Office 365 é usada para exportar os resultados da pesquisa ao usar a ferramenta de pesquisa de conteúdo no centro de segurança e conformidade, descoberta eletrônica in-loco no Exchange Online e o centro de descoberta eletrônica no SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="82b5e-107">The Office 365 eDiscovery Export tool is used to export the search results when using the Content Search tool in the security and compliance center, In-Place eDiscovery in Exchange Online, and the eDiscovery Center in SharePoint Online.</span></span>
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a><span data-ttu-id="82b5e-108">Criar uma configuração de registro para alterar o tamanho dos arquivos PST ao exportar os resultados da pesquisa de descoberta eletrônica</span><span class="sxs-lookup"><span data-stu-id="82b5e-108">Create a registry setting to change the size of PST files when you export eDiscovery search results</span></span>

<span data-ttu-id="82b5e-109">Execute o procedimento a seguir no computador que você usará para exportar os resultados de uma pesquisa de descoberta eletrônica.</span><span class="sxs-lookup"><span data-stu-id="82b5e-109">Perform the following procedure on the computer that you'll use to export the results of an eDiscovery search.</span></span>
  
1. <span data-ttu-id="82b5e-110">Feche a ferramenta de exportação de descoberta eletrônica do Office 365 se ela estiver aberta.</span><span class="sxs-lookup"><span data-stu-id="82b5e-110">Close the Office 365 eDiscovery Export tool if it's open.</span></span> 
    
2. <span data-ttu-id="82b5e-111">Salve o seguinte texto em um arquivo de registro de janela usando um sufixo de nome de arquivo. reg; por exemplo, PstExportSize. reg.</span><span class="sxs-lookup"><span data-stu-id="82b5e-111">Save the following text to a Window registry file by using a filename suffix of .reg; for example, PstExportSize.reg.</span></span> 
    
    ```text
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    <span data-ttu-id="82b5e-112">No exemplo acima, o `PstSizeLimitInBytes` valor é definido como 1.073.741.824 bytes ou aproximadamente 1 GB.</span><span class="sxs-lookup"><span data-stu-id="82b5e-112">In the example above, the  `PstSizeLimitInBytes` value is set to 1,073,741,824 bytes or approximately 1 GB.</span></span> <span data-ttu-id="82b5e-113">Aqui estão alguns outros valores de exemplo para `PstSizeLimitInBytes` a configuração.</span><span class="sxs-lookup"><span data-stu-id="82b5e-113">Here are some other sample values for the  `PstSizeLimitInBytes` setting.</span></span> 
    
    |<span data-ttu-id="82b5e-114">**Tamanho em GB (aprox.)**</span><span class="sxs-lookup"><span data-stu-id="82b5e-114">**Size in GB (approx.)**</span></span>|<span data-ttu-id="82b5e-115">**Tamanho em bytes**</span><span class="sxs-lookup"><span data-stu-id="82b5e-115">**Size in bytes**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="82b5e-116">.7 GB (700 MB)</span><span class="sxs-lookup"><span data-stu-id="82b5e-116">.7 GB (700 MB)</span></span>  <br/> |<span data-ttu-id="82b5e-117">751619277</span><span class="sxs-lookup"><span data-stu-id="82b5e-117">751619277</span></span>  <br/> |
    |<span data-ttu-id="82b5e-118">2 GB</span><span class="sxs-lookup"><span data-stu-id="82b5e-118">2 GB</span></span>  <br/> |<span data-ttu-id="82b5e-119">2147483648</span><span class="sxs-lookup"><span data-stu-id="82b5e-119">2147483648</span></span>  <br/> |
    |<span data-ttu-id="82b5e-120">4 GB</span><span class="sxs-lookup"><span data-stu-id="82b5e-120">4 GB</span></span>  <br/> |<span data-ttu-id="82b5e-121">4294967296</span><span class="sxs-lookup"><span data-stu-id="82b5e-121">4294967296</span></span>  <br/> |
    |<span data-ttu-id="82b5e-122">8 GB</span><span class="sxs-lookup"><span data-stu-id="82b5e-122">8 GB</span></span>  <br/> |<span data-ttu-id="82b5e-123">8589934592</span><span class="sxs-lookup"><span data-stu-id="82b5e-123">8589934592</span></span>  <br/> |
   
3. <span data-ttu-id="82b5e-124">Altere o `PstSizeLimitInBytes` valor para o tamanho máximo desejado de um arquivo PST ao exportar os resultados da pesquisa e salve o arquivo.</span><span class="sxs-lookup"><span data-stu-id="82b5e-124">Change the `PstSizeLimitInBytes` value to the desired maximum size of a PST file when you export search results, and then save the file.</span></span> 
    
4. <span data-ttu-id="82b5e-125">No Windows Explorer, clique ou clique duas vezes no arquivo. reg que você criou nas etapas anteriores.</span><span class="sxs-lookup"><span data-stu-id="82b5e-125">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
5. <span data-ttu-id="82b5e-126">Na janela controle de acesso do usuário, clique em **Sim** para permitir que o editor do Registro faça a alteração.</span><span class="sxs-lookup"><span data-stu-id="82b5e-126">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
6. <span data-ttu-id="82b5e-127">Quando for solicitado a continuar, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="82b5e-127">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="82b5e-128">O editor do registro exibe uma mensagem dizendo que a configuração foi adicionada com êxito ao registro.</span><span class="sxs-lookup"><span data-stu-id="82b5e-128">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
    
7. <span data-ttu-id="82b5e-129">Você pode repetir as etapas 3-6 para alterar o valor da `PstSizeLimitInBytes` configuração do registro.</span><span class="sxs-lookup"><span data-stu-id="82b5e-129">You can repeat steps 3 - 6 to change the value for the  `PstSizeLimitInBytes` registry setting.</span></span> 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a><span data-ttu-id="82b5e-130">Perguntas frequentes sobre como alterar o tamanho padrão de arquivos PST quando você exporta os resultados da pesquisa de descoberta eletrônica</span><span class="sxs-lookup"><span data-stu-id="82b5e-130">Frequently asked questions about changing the default size of PST files when you export eDiscovery search results</span></span>

 <span data-ttu-id="82b5e-131">**Por que o tamanho padrão é de 10 GB?**</span><span class="sxs-lookup"><span data-stu-id="82b5e-131">**Why is the default size 10 GB?**</span></span>
  
<span data-ttu-id="82b5e-132">O tamanho padrão de 10 GB era baseado nos comentários dos clientes; 10 GB é um bom equilíbrio entre a quantidade ideal de conteúdo em um único PST e com uma chance mínima de danos no arquivo.</span><span class="sxs-lookup"><span data-stu-id="82b5e-132">The default size of 10 GB was based on customer feedback; 10 GB is a good balance between the optimal amount of content in a single PST and with a minimum chance of file corruption.</span></span>
  
 <span data-ttu-id="82b5e-133">**Devo aumentar ou diminuir o tamanho padrão dos arquivos PST?**</span><span class="sxs-lookup"><span data-stu-id="82b5e-133">**Should I increase or decrease the default size of PST files?**</span></span>
  
<span data-ttu-id="82b5e-134">Os clientes tendem a reduzir o limite de tamanho para que os resultados da pesquisa caibam em mídia removível que eles podem fornecer fisicamente outros locais na organização.</span><span class="sxs-lookup"><span data-stu-id="82b5e-134">Customers tend to decrease the size limit so that the search results will fit on removable media that they can physically ship other locations in their organization.</span></span> <span data-ttu-id="82b5e-135">Não é recomendável aumentar o tamanho padrão porque os arquivos PST com mais de 10 GB podem ter problemas de corrupção.</span><span class="sxs-lookup"><span data-stu-id="82b5e-135">We don't recommend that you increase the default size because PST files larger than 10 GB might have corruption issues.</span></span>
  
 <span data-ttu-id="82b5e-136">**Em qual computador tenho que fazer isso?**</span><span class="sxs-lookup"><span data-stu-id="82b5e-136">**What computer do I have to do this on?**</span></span>
  
<span data-ttu-id="82b5e-137">Você precisa alterar a configuração do registro em qualquer computador local em que executa a ferramenta de exportação de descoberta eletrônica do Office 365.</span><span class="sxs-lookup"><span data-stu-id="82b5e-137">You need to change the registry setting on any local computer that you run the Office 365 eDiscovery Export tool on.</span></span>
  
 <span data-ttu-id="82b5e-138">**Após alterar essa configuração, preciso reinicializar o computador?**</span><span class="sxs-lookup"><span data-stu-id="82b5e-138">**After I change this setting, do I have to reboot the computer?**</span></span>
  
<span data-ttu-id="82b5e-139">Não, não é necessário reinicializar o computador.</span><span class="sxs-lookup"><span data-stu-id="82b5e-139">No, you don't have to reboot the computer.</span></span> <span data-ttu-id="82b5e-140">Mas, se a ferramenta de exportação de descoberta eletrônica do Office 365 estiver em execução, você terá que fechá-la e reiniciá-la depois de alterar essa configuração.</span><span class="sxs-lookup"><span data-stu-id="82b5e-140">But, if the Office 365 eDiscovery Export tool is running, you'll have to close it and the restart it after you change this setting.</span></span>
  
 <span data-ttu-id="82b5e-141">**Uma chave de registro existente é editada ou faz uma nova chave ser criada?**</span><span class="sxs-lookup"><span data-stu-id="82b5e-141">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="82b5e-142">Uma nova chave de registro é criada na primeira vez que você executa o arquivo. reg que você criou neste procedimento.</span><span class="sxs-lookup"><span data-stu-id="82b5e-142">A new registry key is created the first time you run the .reg file that you created in this procedure.</span></span> <span data-ttu-id="82b5e-143">Em seguida, a configuração será editada sempre que você alterar e executar novamente o arquivo. reg Edit.</span><span class="sxs-lookup"><span data-stu-id="82b5e-143">Then the setting is edited each time you change and re-run the .reg edit file.</span></span>
