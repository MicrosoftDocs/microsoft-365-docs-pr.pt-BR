---
title: Proteger arquivos em equipes com rótulos de confidencialidade
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: 5b9c8e41-25d2-436d-89bb-9aecb9ec2b80
description: 'Resumo: aplique rótulos confidenciais para proteger arquivos em uma equipe altamente confidencial.'
ms.openlocfilehash: b263aeae335b83cadb45b16d70a2a45d56f1cbd3
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083360"
---
# <a name="protect-files-in-teams-with-sensitivity-labels"></a><span data-ttu-id="71e48-103">Proteger arquivos em equipes com rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="71e48-103">Protect files in teams with sensitivity labels</span></span>


<span data-ttu-id="71e48-104">Ao contrário de um rótulo de confidencialidade para dados altamente regulamentados que qualquer pessoa pode aplicar a qualquer arquivo, uma equipe altamente segura precisa de seu próprio rótulo ou sub-rótulo para que os arquivos atribuídos:</span><span class="sxs-lookup"><span data-stu-id="71e48-104">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a highly confidential team needs its own label or sublabel so that assigned files:</span></span>

- <span data-ttu-id="71e48-105">Sejam individualmente criptografados.</span><span class="sxs-lookup"><span data-stu-id="71e48-105">Are individually encrypted.</span></span>
- <span data-ttu-id="71e48-106">Contenham permissões personalizadas para que somente membros da equipe possam abri-lo.</span><span class="sxs-lookup"><span data-stu-id="71e48-106">Contain custom permissions so that only members of the team can open it.</span></span>

<span data-ttu-id="71e48-107">Para obter esse nível de segurança adicional para arquivos armazenados no site subjacente do SharePoint de uma equipe, configure um rótulo de confidencialidade personalizado que seja seu próprio rótulo ou um sub-rótulo do rótulo geral para dados altamente regulamentados.</span><span class="sxs-lookup"><span data-stu-id="71e48-107">To accomplish this additional level of security for files stored in the underlying SharePoint site of a team, you must configure a customized sensitivity label that is either its own label or a sublabel of the general label for highly regulated data.</span></span> <span data-ttu-id="71e48-108">Somente os membros da equipe verão o rótulo ou o sub-rótulo personalizado na lista de rótulos.</span><span class="sxs-lookup"><span data-stu-id="71e48-108">Only team members will see the customized label or sublabel in their list of labels.</span></span>

<span data-ttu-id="71e48-109">Use um rótulo de confidencialidade quando precisar de um pequeno número de rótulos para uso global e equipes privadas individuais.</span><span class="sxs-lookup"><span data-stu-id="71e48-109">Use a sensitivity label when you need a small number of labels for both global use and individual private teams.</span></span> 

<span data-ttu-id="71e48-110">Use um sub-rótulo de confidencialidade quando houver um grande número de rótulos ou quiser organizar rótulos paras equipes altamente confidenciais sob o rótulo altamente regulamentado.</span><span class="sxs-lookup"><span data-stu-id="71e48-110">Use a sensitivity sublabel when you have a large number of labels or want to organize labels for highly confidential teams under the highly regulated label.</span></span>

<span data-ttu-id="71e48-111">Use [estas instruções](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) para configurar um rótulo separado ou um sub-rótulo com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="71e48-111">Use [these instructions](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a separate label or a sublabel with the following settings:</span></span>

- <span data-ttu-id="71e48-112">O nome do rótulo ou do sub-rótulo contém o nome da equipe</span><span class="sxs-lookup"><span data-stu-id="71e48-112">The name of the label or sublabel contains the name of the team</span></span>
- <span data-ttu-id="71e48-113">A criptografia está ativada</span><span class="sxs-lookup"><span data-stu-id="71e48-113">Encryption is enabled</span></span>
- <span data-ttu-id="71e48-114">O grupo do Office 365 para a equipe tem permissões de coautoria</span><span class="sxs-lookup"><span data-stu-id="71e48-114">The Office 365 group for the team has Co-Author permissions</span></span>

<span data-ttu-id="71e48-115">Depois de criar, publique o novo rótulo ou sub-rótulo para seus usuários, que poderão, aplicá-los a arquivos localmente antes de carregá-los para a equipe ou, posteriormente, quando o arquivo estiver armazenado na equipe.</span><span class="sxs-lookup"><span data-stu-id="71e48-115">After creating, publish the new label or sublabel for your users, who can then apply them to files either locally before uploading them to the team or later once the file is stored in the team.</span></span>

<span data-ttu-id="71e48-116">Esta é a configuração da equipe altamente confidencial que usa rótulos de confidencialidade para criptografia e permissões de arquivos.</span><span class="sxs-lookup"><span data-stu-id="71e48-116">Here is the configuration of the highly confidential team that uses sensitivity labels for file encryption and permissions.</span></span>

![Proteção de nível de linha de base para uma equipe pública.](../../media/highly-confidential-team-dlp-sensitivity-labels.png)


## <a name="see-also"></a><span data-ttu-id="71e48-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="71e48-118">See Also</span></span>

[<span data-ttu-id="71e48-119">Proteger arquivos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="71e48-119">Secure files in Microsoft Teams</span></span>](secure-files-in-teams.md)
  
[<span data-ttu-id="71e48-120">Adoção da nuvem e de soluções híbridas</span><span class="sxs-lookup"><span data-stu-id="71e48-120">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
