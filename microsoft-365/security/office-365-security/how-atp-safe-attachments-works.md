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
ms.openlocfilehash: a0d5923ccac525b23aa2ef6b45936524f0a7b483
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036651"
---
# <a name="how-atp-safe-attachments-works"></a><span data-ttu-id="4b475-103">Como funcionam os Anexos Seguros da ATP</span><span class="sxs-lookup"><span data-stu-id="4b475-103">How ATP Safe Attachments works</span></span>

## <a name="how-it-works"></a><span data-ttu-id="4b475-104">Como funciona</span><span class="sxs-lookup"><span data-stu-id="4b475-104">How it works</span></span>

<span data-ttu-id="4b475-105">O recurso de anexos seguros de ATP verifica anexos de email de pessoas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="4b475-105">The ATP Safe Attachments feature checks email attachments for people in your organization.</span></span> <span data-ttu-id="4b475-106">Quando uma política de anexos seguros de ATP está implementada e alguém abordado por essa política exibe seus emails no Office 365, seus anexos de email são verificados e as ações apropriadas são tomadas, com base nas suas políticas de anexos seguros de ATP.</span><span class="sxs-lookup"><span data-stu-id="4b475-106">When an ATP Safe Attachments policy is in place and someone covered by that policy views their email in Office 365, their email attachments are checked and appropriate actions are taken, based on your ATP Safe Attachments policies.</span></span> <span data-ttu-id="4b475-107">Dependendo de como suas políticas estiverem definidas, as pessoas poderão continuar a trabalhar sem ter sido sabendo que foram enviadas arquivos mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="4b475-107">Depending on how your policies are defined, people can continue working without ever knowing they were sent malicious files.</span></span>
  
<span data-ttu-id="4b475-108">Aqui estão dois exemplos de anexos seguros de ATP no trabalho.</span><span class="sxs-lookup"><span data-stu-id="4b475-108">Here are two examples of ATP Safe Attachments at work.</span></span>
  
- <span data-ttu-id="4b475-109">**Exemplo 1: anexo de email** Suponha que Lee receba uma mensagem de email que tenha um anexo.</span><span class="sxs-lookup"><span data-stu-id="4b475-109">**Example 1: Email attachment** Suppose that Lee receives an email message that has an attachment.</span></span> <span data-ttu-id="4b475-110">Não é óbvio para Lee se esse anexo é seguro ou realmente contém malware projetado para roubar as credenciais de usuário de Lee.</span><span class="sxs-lookup"><span data-stu-id="4b475-110">It is not obvious to Lee whether that attachment is safe or actually contains malware designed to steal Lee's user credentials.</span></span> <span data-ttu-id="4b475-111">Na organização de Lee, um administrador de segurança definiu uma política de anexos seguros de ATP alguns dias atrás.</span><span class="sxs-lookup"><span data-stu-id="4b475-111">In Lee's organization, a security administrator defined an ATP Safe Attachments policy a few days ago.</span></span> <span data-ttu-id="4b475-112">Com o recurso de anexos seguros de ATP, o anexo de email é aberto e testado em um ambiente virtual antes de ser recebido por Lee.</span><span class="sxs-lookup"><span data-stu-id="4b475-112">With the ATP Safe Attachments feature, the email attachment is opened and tested in a virtual environment before Lee receives it.</span></span> <span data-ttu-id="4b475-113">Se o anexo for considerado mal-intencionado, ele será removido automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4b475-113">If the attachment is determined to be malicious, it will be removed automatically.</span></span> <span data-ttu-id="4b475-114">Se o anexo for seguro, ele será aberto conforme o esperado quando o Lee clicar nele.</span><span class="sxs-lookup"><span data-stu-id="4b475-114">If the attachment is safe, it will open as expected when Lee clicks on it.</span></span>

- <span data-ttu-id="4b475-115">**Exemplo 2: arquivo no SharePoint Online** Suponha que Jean recebeu um arquivo e o carregou em uma biblioteca no SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="4b475-115">**Example 2: File in SharePoint Online** Suppose that Jean received a file and uploaded it into a library in SharePoint Online.</span></span> <span data-ttu-id="4b475-116">Jean compartilha o link para o arquivo com o restante da equipe, não sabendo que o arquivo é realmente mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="4b475-116">Jean shares the link to the file with the rest of the team, not knowing that the file is actually malicious.</span></span> <span data-ttu-id="4b475-117">Felizmente, [a ATP para SharePoint, onedrive e Microsoft Teams](atp-for-spo-odb-and-teams.md) detecta o arquivo mal-intencionado e o bloqueia.</span><span class="sxs-lookup"><span data-stu-id="4b475-117">Fortunately, [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) detects the malicious file and blocks it.</span></span> <span data-ttu-id="4b475-118">Alguns dias depois, Chris vai abrir o documento.</span><span class="sxs-lookup"><span data-stu-id="4b475-118">A few days later, Chris goes to open the document.</span></span> <span data-ttu-id="4b475-119">Embora Carla possa ver que o arquivo está lá, Carla não pode abrir ou compartilhar, o que protege o computador de Carla e outros do arquivo mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="4b475-119">Although Chris can see the file is there, Chris cannot open or share it, which protects Chris's computer and others from the malicious file.</span></span>

<span data-ttu-id="4b475-120">As políticas de anexos seguros de ATP podem ser aplicadas a pessoas ou grupos específicos em sua organização ou a todo o seu domínio.</span><span class="sxs-lookup"><span data-stu-id="4b475-120">ATP Safe Attachments policies can be applied to specific people or groups in your organization, or to your entire domain.</span></span> <span data-ttu-id="4b475-121">Além disso, as políticas de anexos seguros de ATP podem ser configuradas para usar anexos de espaço reservado enquanto anexos reais estão sendo verificados.</span><span class="sxs-lookup"><span data-stu-id="4b475-121">In addition, ATP Safe Attachments policies can be configured to use placeholder attachments while actual attachments are being scanned.</span></span> <span data-ttu-id="4b475-122">Para saber mais, confira **[configurar as políticas de anexos seguros de ATP no Office 365](set-up-atp-safe-attachments-policies.md)**.</span><span class="sxs-lookup"><span data-stu-id="4b475-122">To learn more, see **[Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md)**.</span></span>

> [!NOTE]
> <span data-ttu-id="4b475-123">A verificação de anexos seguros de ATP ocorre na mesma região onde seus dados residem.</span><span class="sxs-lookup"><span data-stu-id="4b475-123">ATP Safe Attachments scanning takes place in the same region where your data resides.</span></span> <span data-ttu-id="4b475-124">Para obter mais informações sobre a geografia do Data Center, confira [onde estão seus dados?](https://products.office.com/where-is-your-data-located?geo=All)</span><span class="sxs-lookup"><span data-stu-id="4b475-124">For more information about data center geography, see [Where is your data located?](https://products.office.com/where-is-your-data-located?geo=All)</span></span> 

