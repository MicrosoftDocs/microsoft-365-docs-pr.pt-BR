---
title: Como funcionam os Anexos Seguros da ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.date: 05/17/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Saiba como você pode manter sua organização segura de arquivos mal-intencionados usando anexos seguros de ATP para o Office 365.
ms.openlocfilehash: d13674a5d3e769fc10a1f5fd2fd80a4f07c063de
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201465"
---
# <a name="how-atp-safe-attachments-works"></a><span data-ttu-id="5ad87-103">Como funcionam os Anexos Seguros da ATP</span><span class="sxs-lookup"><span data-stu-id="5ad87-103">How ATP Safe Attachments works</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="5ad87-104">O recurso de anexos seguros de ATP verifica anexos de email de pessoas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="5ad87-104">The ATP Safe Attachments feature checks email attachments for people in your organization.</span></span> <span data-ttu-id="5ad87-105">Quando uma política de anexos seguros de ATP está implementada e alguém abordado por essa política exibe seus emails no Office 365, seus anexos de email são verificados e as ações apropriadas são tomadas, com base nas suas políticas de anexos seguros de ATP.</span><span class="sxs-lookup"><span data-stu-id="5ad87-105">When an ATP Safe Attachments policy is in place and someone covered by that policy views their email in Office 365, their email attachments are checked and appropriate actions are taken, based on your ATP Safe Attachments policies.</span></span> <span data-ttu-id="5ad87-106">Dependendo de como suas políticas estiverem definidas, as pessoas poderão continuar a trabalhar sem ter sido sabendo que foram enviadas arquivos mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="5ad87-106">Depending on how your policies are defined, people can continue working without ever knowing they were sent malicious files.</span></span>
  
<span data-ttu-id="5ad87-107">Aqui estão dois exemplos de anexos seguros de ATP no trabalho.</span><span class="sxs-lookup"><span data-stu-id="5ad87-107">Here are two examples of ATP Safe Attachments at work.</span></span>
  
- <span data-ttu-id="5ad87-108">**Exemplo 1: anexo de email** Suponha que Lee receba uma mensagem de email que tenha um anexo.</span><span class="sxs-lookup"><span data-stu-id="5ad87-108">**Example 1: Email attachment** Suppose that Lee receives an email message that has an attachment.</span></span> <span data-ttu-id="5ad87-109">Não é óbvio para Lee se esse anexo é seguro ou realmente contém malware projetado para roubar as credenciais de usuário de Lee.</span><span class="sxs-lookup"><span data-stu-id="5ad87-109">It is not obvious to Lee whether that attachment is safe or actually contains malware designed to steal Lee's user credentials.</span></span> <span data-ttu-id="5ad87-110">Na organização de Lee, um administrador de segurança definiu uma política de anexos seguros de ATP alguns dias atrás.</span><span class="sxs-lookup"><span data-stu-id="5ad87-110">In Lee's organization, a security administrator defined an ATP Safe Attachments policy a few days ago.</span></span> <span data-ttu-id="5ad87-111">Com o recurso de anexos seguros de ATP, o anexo de email é aberto e testado em um ambiente virtual antes de ser recebido por Lee.</span><span class="sxs-lookup"><span data-stu-id="5ad87-111">With the ATP Safe Attachments feature, the email attachment is opened and tested in a virtual environment before Lee receives it.</span></span> <span data-ttu-id="5ad87-112">Se o anexo for considerado mal-intencionado, ele será removido automaticamente.</span><span class="sxs-lookup"><span data-stu-id="5ad87-112">If the attachment is determined to be malicious, it will be removed automatically.</span></span> <span data-ttu-id="5ad87-113">Se o anexo for seguro, ele será aberto conforme o esperado quando o Lee clicar nele.</span><span class="sxs-lookup"><span data-stu-id="5ad87-113">If the attachment is safe, it will open as expected when Lee clicks on it.</span></span>

- <span data-ttu-id="5ad87-114">**Exemplo 2: arquivo no SharePoint Online** Suponha que Jean recebeu um arquivo e o carregou em uma biblioteca no SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="5ad87-114">**Example 2: File in SharePoint Online** Suppose that Jean received a file and uploaded it into a library in SharePoint Online.</span></span> <span data-ttu-id="5ad87-115">Jean compartilha o link para o arquivo com o restante da equipe, não sabendo que o arquivo é realmente mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="5ad87-115">Jean shares the link to the file with the rest of the team, not knowing that the file is actually malicious.</span></span> <span data-ttu-id="5ad87-116">Felizmente, [a ATP para SharePoint, onedrive e Microsoft Teams](atp-for-spo-odb-and-teams.md) detecta o arquivo mal-intencionado e o bloqueia.</span><span class="sxs-lookup"><span data-stu-id="5ad87-116">Fortunately, [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) detects the malicious file and blocks it.</span></span> <span data-ttu-id="5ad87-117">Alguns dias depois, Chris vai abrir o documento.</span><span class="sxs-lookup"><span data-stu-id="5ad87-117">A few days later, Chris goes to open the document.</span></span> <span data-ttu-id="5ad87-118">Embora Carla possa ver que o arquivo está lá, Carla não pode abrir ou compartilhar, o que protege o computador de Carla e outros do arquivo mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="5ad87-118">Although Chris can see the file is there, Chris cannot open or share it, which protects Chris's computer and others from the malicious file.</span></span>

<span data-ttu-id="5ad87-119">As políticas de anexos seguros de ATP podem ser aplicadas a pessoas ou grupos específicos em sua organização ou a todo o seu domínio.</span><span class="sxs-lookup"><span data-stu-id="5ad87-119">ATP Safe Attachments policies can be applied to specific people or groups in your organization, or to your entire domain.</span></span> <span data-ttu-id="5ad87-120">Além disso, as políticas de anexos seguros de ATP podem ser configuradas para usar anexos de espaço reservado enquanto anexos reais estão sendo verificados.</span><span class="sxs-lookup"><span data-stu-id="5ad87-120">In addition, ATP Safe Attachments policies can be configured to use placeholder attachments while actual attachments are being scanned.</span></span> <span data-ttu-id="5ad87-121">Para saber mais, confira **[configurar as políticas de anexos seguros de ATP no Office 365](set-up-atp-safe-attachments-policies.md)**.</span><span class="sxs-lookup"><span data-stu-id="5ad87-121">To learn more, see **[Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md)**.</span></span>

> [!NOTE]
> <span data-ttu-id="5ad87-122">A verificação de anexos seguros de ATP ocorre na mesma região onde seus dados residem.</span><span class="sxs-lookup"><span data-stu-id="5ad87-122">ATP Safe Attachments scanning takes place in the same region where your data resides.</span></span> <span data-ttu-id="5ad87-123">Para obter mais informações sobre a geografia do Data Center, confira [onde estão seus dados?](https://products.office.com/where-is-your-data-located?geo=All)</span><span class="sxs-lookup"><span data-stu-id="5ad87-123">For more information about data center geography, see [Where is your data located?](https://products.office.com/where-is-your-data-located?geo=All)</span></span> 

