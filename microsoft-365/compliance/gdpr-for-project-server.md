---
title: RGPD para Project Server
description: Aprenda a resolver Regulamentações Gerais de Proteção de Dados (RGPD) para o SharePoint Server local.
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
titleSuffix: Microsoft GDPR
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3a7eb291d0da72adf171594aac307ec0ad91829d
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036234"
---
# <a name="gdpr-for-project-server"></a><span data-ttu-id="742c5-103">RGPD para Project Server</span><span class="sxs-lookup"><span data-stu-id="742c5-103">GDPR for Project Server</span></span>

<span data-ttu-id="742c5-p101">O Project Server usa scripts personalizados para exportar e ocultar dados do usuário no Project Web App. O processo básico é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="742c5-p101">Project Server uses custom scripts to export and redact user data in Project Web App. The basic process is:</span></span>

1.  <span data-ttu-id="742c5-106">Encontre os sites do Project Web App em seu farm.</span><span class="sxs-lookup"><span data-stu-id="742c5-106">Find the Project Web App sites in your farm.</span></span>

2.  <span data-ttu-id="742c5-107">Encontre os projetos que contêm o usuário em cada site.</span><span class="sxs-lookup"><span data-stu-id="742c5-107">Find the projects in each site that contain the user.</span></span>

3.  <span data-ttu-id="742c5-108">Exporte e verifique os tipos de dados que você deseja analisar.</span><span class="sxs-lookup"><span data-stu-id="742c5-108">Export and review the types of data that you want to review.</span></span>

4.  <span data-ttu-id="742c5-109">Oculte os dados conforme for necessário.</span><span class="sxs-lookup"><span data-stu-id="742c5-109">Redact data as needed.</span></span>

<span data-ttu-id="742c5-110">Estas etapas são abordadas em detalhes nos seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="742c5-110">These steps are covered in detail in the following articles:</span></span>

- [<span data-ttu-id="742c5-111">Exportar dados do usuário do Project Server</span><span class="sxs-lookup"><span data-stu-id="742c5-111">Export user data from Project Server</span></span>](/Project/export-user-data-from-project-server?toc=/Office365/Enterprise/toc.json)

- [<span data-ttu-id="742c5-112">Excluir dados do usuário do Project Server</span><span class="sxs-lookup"><span data-stu-id="742c5-112">Delete user data from Project Server</span></span>](/Project/delete-user-data-from-project-server?toc=/Office365/Enterprise/toc.json)


<span data-ttu-id="742c5-p102">Observe que o Project Server foi criado a partir do SharePoint Server e que ele registra eventos nos logs de ULS do SharePoint e no banco de dados de uso. Consulte [RGPD para SharePoint Server](gdpr-for-sharepoint-server.md) para ter mais informações.</span><span class="sxs-lookup"><span data-stu-id="742c5-p102">Note that Project Server is built on top of SharePoint Server and logs events to the SharePoint ULS logs and Usage database. See [GDPR for SharePoint Server](gdpr-for-sharepoint-server.md) for more information.</span></span>
