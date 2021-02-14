---
title: Alterar o tamanho dos arquivos PST ao exportar os resultados da pesquisa de Descobertas eDiscovery
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
description: Você pode alterar o tamanho padrão dos arquivos PST que são baixados para o seu computador quando você exporta os resultados da pesquisa de Descoberta eDiscovery.
ms.openlocfilehash: eb5fcce037ff5e3444b42c996b4a32d818edd29d
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2020
ms.locfileid: "43942914"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a><span data-ttu-id="57fca-103">Alterar o tamanho dos arquivos PST ao exportar os resultados da pesquisa de Descobertas eDiscovery</span><span class="sxs-lookup"><span data-stu-id="57fca-103">Change the size of PST files when exporting eDiscovery search results</span></span>

<span data-ttu-id="57fca-104">Quando você usa a ferramenta Exportação de Descobertas Eletrônicos para exportar os resultados de email de uma pesquisa de Descoberta Eletrônico das diferentes ferramentas de Descoberta Eletrônico da Microsoft, o tamanho padrão de um arquivo PST que pode ser exportado é de 10 GB.</span><span class="sxs-lookup"><span data-stu-id="57fca-104">When you use the eDiscovery Export tool to export the email results of an eDiscovery search from the different Microsoft eDiscovery tools, the default size of a PST file that can be exported is 10 GB.</span></span> <span data-ttu-id="57fca-105">Se quiser alterar esse tamanho padrão, você pode editar o Registro do Windows no computador usado para exportar os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="57fca-105">If you want to change this default size, you can edit the Windows Registry on the computer that you use to export the search results.</span></span> <span data-ttu-id="57fca-106">Um motivo para fazer isso é para que um arquivo PST possa caber em mídia removível, como um DVD, um disco compacto ou uma unidade USB.</span><span class="sxs-lookup"><span data-stu-id="57fca-106">One reason to do this is so a PST file can fit on removable media, such a DVD, a compact disc, or a USB drive.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="57fca-107">A ferramenta Exportação de Descobertas e Descobertas é usada para exportar os resultados da pesquisa ao usar a ferramenta Pesquisa de Conteúdo no Centro de Conformidade de & de Segurança, In-Place eDiscovery no Exchange Online e no Centro de Descobertas No SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="57fca-107">The eDiscovery Export tool is used to export the search results when using the Content Search tool in the Security & Compliance Center, In-Place eDiscovery in Exchange Online, and the eDiscovery Center in SharePoint Online.</span></span>
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a><span data-ttu-id="57fca-108">Criar uma configuração do Registro para alterar o tamanho dos arquivos PST quando você exporta os resultados da pesquisa de Descoberta</span><span class="sxs-lookup"><span data-stu-id="57fca-108">Create a registry setting to change the size of PST files when you export eDiscovery search results</span></span>

<span data-ttu-id="57fca-109">Execute o procedimento a seguir no computador que você usará para exportar os resultados de uma pesquisa de Descoberta e.</span><span class="sxs-lookup"><span data-stu-id="57fca-109">Perform the following procedure on the computer that you'll use to export the results of an eDiscovery search.</span></span>
  
1. <span data-ttu-id="57fca-110">Feche a ferramenta exportação de descoberta de ediscovery se ela estiver aberta.</span><span class="sxs-lookup"><span data-stu-id="57fca-110">Close the eDiscovery Export tool if it's open.</span></span> 
    
2. <span data-ttu-id="57fca-111">Salve o texto a seguir em um arquivo de registro do Window usando um sufixo de nome de arquivo .reg; por exemplo, PstExportSize.reg.</span><span class="sxs-lookup"><span data-stu-id="57fca-111">Save the following text to a Window registry file by using a filename suffix of .reg; for example, PstExportSize.reg.</span></span> 
    
    ```text
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    <span data-ttu-id="57fca-112">No exemplo acima, o valor é definido como  `PstSizeLimitInBytes` 1.073.741.824 bytes ou aproximadamente 1 GB.</span><span class="sxs-lookup"><span data-stu-id="57fca-112">In the example above, the  `PstSizeLimitInBytes` value is set to 1,073,741,824 bytes or approximately 1 GB.</span></span> <span data-ttu-id="57fca-113">Aqui estão alguns outros valores de exemplo para a  `PstSizeLimitInBytes` configuração.</span><span class="sxs-lookup"><span data-stu-id="57fca-113">Here are some other sample values for the  `PstSizeLimitInBytes` setting.</span></span> 
    
    |<span data-ttu-id="57fca-114">**Tamanho em GB (aproximado).**</span><span class="sxs-lookup"><span data-stu-id="57fca-114">**Size in GB (approx.)**</span></span>|<span data-ttu-id="57fca-115">**Tamanho em bytes**</span><span class="sxs-lookup"><span data-stu-id="57fca-115">**Size in bytes**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="57fca-116">0,7 GB (700 MB)</span><span class="sxs-lookup"><span data-stu-id="57fca-116">0.7 GB (700 MB)</span></span>  <br/> |<span data-ttu-id="57fca-117">751619277</span><span class="sxs-lookup"><span data-stu-id="57fca-117">751619277</span></span>  <br/> |
    |<span data-ttu-id="57fca-118">2 GB</span><span class="sxs-lookup"><span data-stu-id="57fca-118">2 GB</span></span>  <br/> |<span data-ttu-id="57fca-119">2147483648</span><span class="sxs-lookup"><span data-stu-id="57fca-119">2147483648</span></span>  <br/> |
    |<span data-ttu-id="57fca-120">4 GB</span><span class="sxs-lookup"><span data-stu-id="57fca-120">4 GB</span></span>  <br/> |<span data-ttu-id="57fca-121">4294967296</span><span class="sxs-lookup"><span data-stu-id="57fca-121">4294967296</span></span>  <br/> |
    |<span data-ttu-id="57fca-122">8 GB</span><span class="sxs-lookup"><span data-stu-id="57fca-122">8 GB</span></span>  <br/> |<span data-ttu-id="57fca-123">8589934592</span><span class="sxs-lookup"><span data-stu-id="57fca-123">8589934592</span></span>  <br/> |
   
3. <span data-ttu-id="57fca-124">Altere o valor para o tamanho máximo desejado de um arquivo PST quando você exportar os resultados da pesquisa e `PstSizeLimitInBytes` salve o arquivo.</span><span class="sxs-lookup"><span data-stu-id="57fca-124">Change the `PstSizeLimitInBytes` value to the desired maximum size of a PST file when you export search results, and then save the file.</span></span> 
    
4. <span data-ttu-id="57fca-125">No Windows Explorer, clique ou clique duas vezes no arquivo .reg que você criou nas etapas anteriores.</span><span class="sxs-lookup"><span data-stu-id="57fca-125">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
5. <span data-ttu-id="57fca-126">Na janela Controle de Acesso de Usuário, clique **em Sim** para permitir que o Editor do Registro faça a alteração.</span><span class="sxs-lookup"><span data-stu-id="57fca-126">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
6. <span data-ttu-id="57fca-127">Quando solicitado a continuar, clique em **Sim.**</span><span class="sxs-lookup"><span data-stu-id="57fca-127">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="57fca-128">O Editor do Registro exibe uma mensagem dizendo que a configuração foi adicionada com êxito ao Registro.</span><span class="sxs-lookup"><span data-stu-id="57fca-128">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
    
7. <span data-ttu-id="57fca-129">Você pode repetir as etapas 3 a 6 para alterar o valor da  `PstSizeLimitInBytes` configuração do Registro.</span><span class="sxs-lookup"><span data-stu-id="57fca-129">You can repeat steps 3 - 6 to change the value for the  `PstSizeLimitInBytes` registry setting.</span></span> 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a><span data-ttu-id="57fca-130">Perguntas frequentes sobre como alterar o tamanho padrão de arquivos PST quando você exporta os resultados da pesquisa de Descoberta eDiscovery</span><span class="sxs-lookup"><span data-stu-id="57fca-130">Frequently asked questions about changing the default size of PST files when you export eDiscovery search results</span></span>

 <span data-ttu-id="57fca-131">**Por que o tamanho padrão é 10 GB?**</span><span class="sxs-lookup"><span data-stu-id="57fca-131">**Why is the default size 10 GB?**</span></span>
  
<span data-ttu-id="57fca-132">O tamanho padrão de 10 GB foi baseado nos comentários dos clientes; 10 GB é um bom equilíbrio entre a quantidade ideal de conteúdo em um único PST e com uma chance mínima de corrupção de arquivo.</span><span class="sxs-lookup"><span data-stu-id="57fca-132">The default size of 10 GB was based on customer feedback; 10 GB is a good balance between the optimal amount of content in a single PST and with a minimum chance of file corruption.</span></span>
  
 <span data-ttu-id="57fca-133">**Devo aumentar ou diminuir o tamanho padrão dos arquivos PST?**</span><span class="sxs-lookup"><span data-stu-id="57fca-133">**Should I increase or decrease the default size of PST files?**</span></span>
  
<span data-ttu-id="57fca-134">Os clientes tendem a diminuir o limite de tamanho para que os resultados da pesquisa caibam em mídia removível que possam enviar fisicamente para outros locais em sua organização.</span><span class="sxs-lookup"><span data-stu-id="57fca-134">Customers tend to decrease the size limit so that the search results will fit on removable media that they can physically ship to other locations in their organization.</span></span> <span data-ttu-id="57fca-135">Não recomendamos que você aumente o tamanho padrão porque arquivos PST maiores que 10 GB podem ter problemas de corrupção.</span><span class="sxs-lookup"><span data-stu-id="57fca-135">We don't recommend that you increase the default size because PST files larger than 10 GB might have corruption issues.</span></span>
  
 <span data-ttu-id="57fca-136">**Em qual computador preciso fazer isso?**</span><span class="sxs-lookup"><span data-stu-id="57fca-136">**What computer do I have to do this on?**</span></span>
  
<span data-ttu-id="57fca-137">Você precisa alterar a configuração do Registro em qualquer computador local em que executar a ferramenta Exportação de Descobertas.</span><span class="sxs-lookup"><span data-stu-id="57fca-137">You need to change the registry setting on any local computer that you run the eDiscovery Export tool on.</span></span>
  
 <span data-ttu-id="57fca-138">**Depois de alterar essa configuração, preciso reiniciar o computador?**</span><span class="sxs-lookup"><span data-stu-id="57fca-138">**After I change this setting, do I have to reboot the computer?**</span></span>
  
<span data-ttu-id="57fca-139">Não, você não precisa reiniciar o computador.</span><span class="sxs-lookup"><span data-stu-id="57fca-139">No, you don't have to reboot the computer.</span></span> <span data-ttu-id="57fca-140">Porém, se a ferramenta de Exportação de DescobertaScoberta estiver em execução, você terá que fecha-la e reiniciá-la depois de alterar essa configuração.</span><span class="sxs-lookup"><span data-stu-id="57fca-140">But, if the eDiscovery Export tool is running, you'll have to close it and the restart it after you change this setting.</span></span>
  
 <span data-ttu-id="57fca-141">**Uma chave do Registro existente é editada ou uma nova chave é criada?**</span><span class="sxs-lookup"><span data-stu-id="57fca-141">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="57fca-142">Uma nova chave do Registro é criada na primeira vez que você executar o arquivo .reg criado neste procedimento.</span><span class="sxs-lookup"><span data-stu-id="57fca-142">A new registry key is created the first time you run the .reg file that you created in this procedure.</span></span> <span data-ttu-id="57fca-143">Em seguida, a configuração é editada sempre que você altera e rerun o arquivo de edição .reg.</span><span class="sxs-lookup"><span data-stu-id="57fca-143">Then the setting is edited each time you change and rerun the .reg edit file.</span></span>
