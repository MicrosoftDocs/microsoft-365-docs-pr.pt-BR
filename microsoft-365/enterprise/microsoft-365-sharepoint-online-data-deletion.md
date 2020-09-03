---
title: Exclusão de dados do SharePoint Online da Microsoft 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
f1.keywords:
- NOCSH
description: Saiba como a exclusão de dados funciona no SharePoint Online, como onde o conteúdo excluído é armazenado e por quanto tempo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e914e84f3679483e5030b7f2a06913cb052e5411
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332719"
---
# <a name="sharepoint-online-data-deletion-in-microsoft-365"></a><span data-ttu-id="69bce-103">Exclusão de dados do SharePoint Online no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="69bce-103">SharePoint Online Data Deletion in Microsoft 365</span></span>

<span data-ttu-id="69bce-104">O SharePoint Online armazena objetos como código abstrato em bancos de dados de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="69bce-104">SharePoint Online stores objects as abstracted code within application databases.</span></span> <span data-ttu-id="69bce-105">Quando um usuário carrega um arquivo no SharePoint Online, esse arquivo é desmontado e traduzido no código do aplicativo e armazenado em várias tabelas em vários bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="69bce-105">When a user uploads a file to SharePoint Online, that file is disassembled and translated into application code and stored in multiple tables across multiple databases.</span></span> <span data-ttu-id="69bce-106">No SharePoint Online, todo o conteúdo que um cliente carrega é dividido em partes, criptografadas (potencialmente com várias chaves AES de 256 bits) e distribuídas no datacenter.</span><span class="sxs-lookup"><span data-stu-id="69bce-106">In SharePoint Online, all content that a customer uploads is broken into chunks, encrypted (potentially with multiple AES 256-bit keys), and distributed across the datacenter.</span></span> <span data-ttu-id="69bce-107">Para obter detalhes específicos sobre o processo de fragmentação e criptografia, consulte [Encryption in the Microsoft Cloud](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-in-the-microsoft-cloud-overview).</span><span class="sxs-lookup"><span data-stu-id="69bce-107">For specific details about the chunking and encryption process, see [Encryption in the Microsoft Cloud](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-in-the-microsoft-cloud-overview).</span></span> 

<span data-ttu-id="69bce-108">No SharePoint Online, os itens são mantidos por 93 dias a partir do momento em que você os exclui do local original.</span><span class="sxs-lookup"><span data-stu-id="69bce-108">In SharePoint Online, items are retained for 93 days from the time you delete them from their original location.</span></span> <span data-ttu-id="69bce-109">Eles permanecem na lixeira do site o horário inteiro, a menos que alguém os exclua ou esvazia essa lixeira.</span><span class="sxs-lookup"><span data-stu-id="69bce-109">They stay in the site Recycle Bin the entire time, unless someone deletes them from there or empties that Recycle Bin.</span></span> <span data-ttu-id="69bce-110">Nesse caso, os itens vão para a lixeira do conjunto de sites, onde eles permanecem no restante dos 93 dias.</span><span class="sxs-lookup"><span data-stu-id="69bce-110">In that case, the items go to the site collection Recycle Bin, where they stay for the remainder of the 93 days.</span></span> <span data-ttu-id="69bce-111">Para obter informações sobre como restaurar itens excluídos, consulte [restaurar itens na lixeira de um site do SharePoint](https://support.office.com/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
) e [restaurar itens excluídos da](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b)lixeira do conjunto de sites.</span><span class="sxs-lookup"><span data-stu-id="69bce-111">For info about restoring deleted items, see [Restore items in the Recycle Bin of a SharePoint site](https://support.office.com/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
) and [Restore deleted items from the site collection recycle bin](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b).</span></span> <span data-ttu-id="69bce-112">O tempo de retenção da lixeira não é configurável no SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="69bce-112">The Recycle Bin retention time is not configurable in SharePoint Online.</span></span>

<span data-ttu-id="69bce-113">Ao excluir um conjunto de sites, você também está excluindo a hierarquia de sites na coleção e todos os conteúdos dentro deles:</span><span class="sxs-lookup"><span data-stu-id="69bce-113">When you delete a site collection, you're also deleting the hierarchy of sites in the collection, and all content within them:</span></span>

- <span data-ttu-id="69bce-114">Documentos e bibliotecas de documentos</span><span class="sxs-lookup"><span data-stu-id="69bce-114">Documents and document libraries</span></span>
- <span data-ttu-id="69bce-115">Lista e dados de lista</span><span class="sxs-lookup"><span data-stu-id="69bce-115">Lists and list data</span></span>
- <span data-ttu-id="69bce-116">Definições de configuração do site</span><span class="sxs-lookup"><span data-stu-id="69bce-116">Site configuration settings</span></span>
- <span data-ttu-id="69bce-117">Informações de função e segurança relacionadas ao site ou seus subsites</span><span class="sxs-lookup"><span data-stu-id="69bce-117">Role and security information that is related to the site or its subsites</span></span>
- <span data-ttu-id="69bce-118">Subsites do site de nível superior, seu conteúdo e informações de usuário</span><span class="sxs-lookup"><span data-stu-id="69bce-118">Subsites of the top-level website, their contents, and user information</span></span>

<span data-ttu-id="69bce-119">Se você excluir acidentalmente um conjunto de sites, ele poderá ser restaurado por um administrador global ou do SharePoint usando o centro de administração do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="69bce-119">If you accidentally delete a site collection, it can be restored by a global or SharePoint admin using the SharePoint admin center.</span></span>

<span data-ttu-id="69bce-120">Os conjuntos de sites excluídos são mantidos por 93 dias.</span><span class="sxs-lookup"><span data-stu-id="69bce-120">Deleted site collections are retained for 93 days.</span></span> <span data-ttu-id="69bce-121">Após 93 dias, sites e todo o conteúdo e as configurações serão excluídos permanentemente, incluindo listas, bibliotecas, páginas e subsites.</span><span class="sxs-lookup"><span data-stu-id="69bce-121">After 93 days, sites and all their content and settings are permanently deleted, including lists, libraries, pages, and any subsites.</span></span>

<span data-ttu-id="69bce-122">A exclusão fixa ocorre quando um usuário limpa itens excluídos da lixeira do conjunto de sites, quando os períodos de retenção e backup expiram ou quando um administrador exclui permanentemente um conjunto de sites usando o [cmdlet Remove-SPODeletedSite](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="69bce-122">Hard deletion occurs when a user purges deleted items from the site collection Recycle Bin, when the retention and backup periods expire, or when an administrator permanently deletes a site collection using the [Remove-SPODeletedSite cmdlet](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps).</span></span> <span data-ttu-id="69bce-123">Quando um usuário exclui (permanentemente exclui ou limpa) o conteúdo do SharePoint Online, todas as chaves de criptografia dos blocos excluídos também são excluídas.</span><span class="sxs-lookup"><span data-stu-id="69bce-123">When a user hard deletes (permanently deletes, or purges) content from SharePoint Online, all encryption keys for the deleted chunks are also deleted.</span></span> <span data-ttu-id="69bce-124">Os blocos nos discos que armazenaram anteriormente os fragmentos excluídos são marcados como não usados e estão disponíveis para reutilização.</span><span class="sxs-lookup"><span data-stu-id="69bce-124">The blocks on the disks that previously stored the deleted chunks are marked as unused and available for re-use.</span></span>
