---
title: Alterar o tamanho dos arquivos PST ao exportar resultados da pesquisa de Descobertas Digitais
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: Você pode alterar o tamanho padrão dos arquivos PST baixados para o computador quando você exporta os resultados da pesquisa de Descobertas Digitais.
ms.openlocfilehash: eb5fcce037ff5e3444b42c996b4a32d818edd29d
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2020
ms.locfileid: "43942914"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a><span data-ttu-id="a008e-103">Alterar o tamanho dos arquivos PST ao exportar resultados da pesquisa de Descobertas Digitais</span><span class="sxs-lookup"><span data-stu-id="a008e-103">Change the size of PST files when exporting eDiscovery search results</span></span>

<span data-ttu-id="a008e-104">Quando você usa a ferramenta Exportação de Descoberta Eletrônico para exportar os resultados de email de uma pesquisa de Descoberta Eletrônico das diferentes ferramentas de Descoberta Eletrônico da Microsoft, o tamanho padrão de um arquivo PST que pode ser exportado é de 10 GB.</span><span class="sxs-lookup"><span data-stu-id="a008e-104">When you use the eDiscovery Export tool to export the email results of an eDiscovery search from the different Microsoft eDiscovery tools, the default size of a PST file that can be exported is 10 GB.</span></span> <span data-ttu-id="a008e-105">Se você quiser alterar esse tamanho padrão, poderá editar o registro Windows no computador que você usa para exportar os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a008e-105">If you want to change this default size, you can edit the Windows Registry on the computer that you use to export the search results.</span></span> <span data-ttu-id="a008e-106">Um motivo para fazer isso é para que um arquivo PST possa caber em mídia removível, como um DVD, um disco compacto ou uma unidade USB.</span><span class="sxs-lookup"><span data-stu-id="a008e-106">One reason to do this is so a PST file can fit on removable media, such a DVD, a compact disc, or a USB drive.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a008e-107">A ferramenta Exportação de Descoberta Virtual é usada para exportar os resultados da pesquisa ao usar a ferramenta Pesquisa de Conteúdo no Centro de Conformidade e Segurança do &, In-Place Descoberta Virtual no Exchange Online e o Centro de Descoberta Virtual no SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a008e-107">The eDiscovery Export tool is used to export the search results when using the Content Search tool in the Security & Compliance Center, In-Place eDiscovery in Exchange Online, and the eDiscovery Center in SharePoint Online.</span></span>
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a><span data-ttu-id="a008e-108">Criar uma configuração do Registro para alterar o tamanho dos arquivos PST quando você exportar resultados da pesquisa de Descoberta e</span><span class="sxs-lookup"><span data-stu-id="a008e-108">Create a registry setting to change the size of PST files when you export eDiscovery search results</span></span>

<span data-ttu-id="a008e-109">Execute o procedimento a seguir no computador que você usará para exportar os resultados de uma pesquisa de Descoberta e.</span><span class="sxs-lookup"><span data-stu-id="a008e-109">Perform the following procedure on the computer that you'll use to export the results of an eDiscovery search.</span></span>
  
1. <span data-ttu-id="a008e-110">Feche a ferramenta Exportação de Descoberta Digital se estiver aberta.</span><span class="sxs-lookup"><span data-stu-id="a008e-110">Close the eDiscovery Export tool if it's open.</span></span> 
    
2. <span data-ttu-id="a008e-111">Salve o texto a seguir em um arquivo de Registro de Janela usando um sufixo de nome de arquivo de .reg; por exemplo, PstExportSize.reg.</span><span class="sxs-lookup"><span data-stu-id="a008e-111">Save the following text to a Window registry file by using a filename suffix of .reg; for example, PstExportSize.reg.</span></span> 
    
    ```text
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    <span data-ttu-id="a008e-112">No exemplo acima, o valor é definido como  `PstSizeLimitInBytes` 1.073.741.824 bytes ou aproximadamente 1 GB.</span><span class="sxs-lookup"><span data-stu-id="a008e-112">In the example above, the  `PstSizeLimitInBytes` value is set to 1,073,741,824 bytes or approximately 1 GB.</span></span> <span data-ttu-id="a008e-113">Aqui estão alguns outros valores de exemplo para a  `PstSizeLimitInBytes` configuração.</span><span class="sxs-lookup"><span data-stu-id="a008e-113">Here are some other sample values for the  `PstSizeLimitInBytes` setting.</span></span> 
    
    |<span data-ttu-id="a008e-114">**Tamanho em GB (aprox.)**</span><span class="sxs-lookup"><span data-stu-id="a008e-114">**Size in GB (approx.)**</span></span>|<span data-ttu-id="a008e-115">**Tamanho em bytes**</span><span class="sxs-lookup"><span data-stu-id="a008e-115">**Size in bytes**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="a008e-116">0,7 GB (700 MB)</span><span class="sxs-lookup"><span data-stu-id="a008e-116">0.7 GB (700 MB)</span></span>  <br/> |<span data-ttu-id="a008e-117">751619277</span><span class="sxs-lookup"><span data-stu-id="a008e-117">751619277</span></span>  <br/> |
    |<span data-ttu-id="a008e-118">2 GB</span><span class="sxs-lookup"><span data-stu-id="a008e-118">2 GB</span></span>  <br/> |<span data-ttu-id="a008e-119">2147483648</span><span class="sxs-lookup"><span data-stu-id="a008e-119">2147483648</span></span>  <br/> |
    |<span data-ttu-id="a008e-120">4 GB</span><span class="sxs-lookup"><span data-stu-id="a008e-120">4 GB</span></span>  <br/> |<span data-ttu-id="a008e-121">4294967296</span><span class="sxs-lookup"><span data-stu-id="a008e-121">4294967296</span></span>  <br/> |
    |<span data-ttu-id="a008e-122">8 GB</span><span class="sxs-lookup"><span data-stu-id="a008e-122">8 GB</span></span>  <br/> |<span data-ttu-id="a008e-123">8589934592</span><span class="sxs-lookup"><span data-stu-id="a008e-123">8589934592</span></span>  <br/> |
   
3. <span data-ttu-id="a008e-124">Altere o valor para o tamanho máximo desejado de um arquivo PST quando você exportar os resultados da pesquisa e `PstSizeLimitInBytes` salve o arquivo.</span><span class="sxs-lookup"><span data-stu-id="a008e-124">Change the `PstSizeLimitInBytes` value to the desired maximum size of a PST file when you export search results, and then save the file.</span></span> 
    
4. <span data-ttu-id="a008e-125">No Windows Explorer, clique ou clique duas vezes no arquivo .reg que você criou nas etapas anteriores.</span><span class="sxs-lookup"><span data-stu-id="a008e-125">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
5. <span data-ttu-id="a008e-126">Na janela Controle de Acesso para Usuário, clique em **Sim** para permitir que o Editor do Registro faça a alteração.</span><span class="sxs-lookup"><span data-stu-id="a008e-126">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
6. <span data-ttu-id="a008e-127">Quando solicitado a continuar, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="a008e-127">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="a008e-128">O Editor do Registro exibe uma mensagem dizendo que a configuração foi adicionada com êxito ao Registro.</span><span class="sxs-lookup"><span data-stu-id="a008e-128">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
    
7. <span data-ttu-id="a008e-129">Você pode repetir as etapas 3 a 6 para alterar o valor da  `PstSizeLimitInBytes` configuração do Registro.</span><span class="sxs-lookup"><span data-stu-id="a008e-129">You can repeat steps 3 - 6 to change the value for the  `PstSizeLimitInBytes` registry setting.</span></span> 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a><span data-ttu-id="a008e-130">Perguntas frequentes sobre como alterar o tamanho padrão de arquivos PST quando você exporta resultados de pesquisa de Descoberta e</span><span class="sxs-lookup"><span data-stu-id="a008e-130">Frequently asked questions about changing the default size of PST files when you export eDiscovery search results</span></span>

 <span data-ttu-id="a008e-131">**Por que o tamanho padrão é 10 GB?**</span><span class="sxs-lookup"><span data-stu-id="a008e-131">**Why is the default size 10 GB?**</span></span>
  
<span data-ttu-id="a008e-132">O tamanho padrão de 10 GB foi baseado nos comentários do cliente; 10 GB é um bom equilíbrio entre a quantidade ideal de conteúdo em um único PST e com uma chance mínima de corrupção de arquivo.</span><span class="sxs-lookup"><span data-stu-id="a008e-132">The default size of 10 GB was based on customer feedback; 10 GB is a good balance between the optimal amount of content in a single PST and with a minimum chance of file corruption.</span></span>
  
 <span data-ttu-id="a008e-133">**Devo aumentar ou diminuir o tamanho padrão de arquivos PST?**</span><span class="sxs-lookup"><span data-stu-id="a008e-133">**Should I increase or decrease the default size of PST files?**</span></span>
  
<span data-ttu-id="a008e-134">Os clientes tendem a diminuir o limite de tamanho para que os resultados da pesquisa se encaixem em mídia removível que eles possam enviar fisicamente para outros locais em sua organização.</span><span class="sxs-lookup"><span data-stu-id="a008e-134">Customers tend to decrease the size limit so that the search results will fit on removable media that they can physically ship to other locations in their organization.</span></span> <span data-ttu-id="a008e-135">Não recomendamos que você aumente o tamanho padrão porque arquivos PST maiores do que 10 GB podem ter problemas de corrupção.</span><span class="sxs-lookup"><span data-stu-id="a008e-135">We don't recommend that you increase the default size because PST files larger than 10 GB might have corruption issues.</span></span>
  
 <span data-ttu-id="a008e-136">**Em qual computador devo fazer isso?**</span><span class="sxs-lookup"><span data-stu-id="a008e-136">**What computer do I have to do this on?**</span></span>
  
<span data-ttu-id="a008e-137">Você precisa alterar a configuração do Registro em qualquer computador local em que você execute a ferramenta Exportar Descoberta e.</span><span class="sxs-lookup"><span data-stu-id="a008e-137">You need to change the registry setting on any local computer that you run the eDiscovery Export tool on.</span></span>
  
 <span data-ttu-id="a008e-138">**Depois de alterar essa configuração, preciso reiniciar o computador?**</span><span class="sxs-lookup"><span data-stu-id="a008e-138">**After I change this setting, do I have to reboot the computer?**</span></span>
  
<span data-ttu-id="a008e-139">Não, você não precisa reiniciar o computador.</span><span class="sxs-lookup"><span data-stu-id="a008e-139">No, you don't have to reboot the computer.</span></span> <span data-ttu-id="a008e-140">Mas, se a ferramenta Exportação de Descoberta Digital estiver em execução, você terá que fechar e reinicie-a depois de alterar essa configuração.</span><span class="sxs-lookup"><span data-stu-id="a008e-140">But, if the eDiscovery Export tool is running, you'll have to close it and the restart it after you change this setting.</span></span>
  
 <span data-ttu-id="a008e-141">**Uma chave existente do Registro é editada ou uma nova chave é criada?**</span><span class="sxs-lookup"><span data-stu-id="a008e-141">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="a008e-142">Uma nova chave do Registro é criada na primeira vez que você executar o arquivo .reg criado neste procedimento.</span><span class="sxs-lookup"><span data-stu-id="a008e-142">A new registry key is created the first time you run the .reg file that you created in this procedure.</span></span> <span data-ttu-id="a008e-143">Em seguida, a configuração é editada sempre que você alterar e reprisar o arquivo de edição .reg.</span><span class="sxs-lookup"><span data-stu-id="a008e-143">Then the setting is edited each time you change and rerun the .reg edit file.</span></span>
