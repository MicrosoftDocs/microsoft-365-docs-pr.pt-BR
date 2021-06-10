---
title: Validar novos dispositivos
description: Antes de ordenar dispositivos, obtenha um de cada modelo e teste-o
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 772636fd72074c8fad30daa3eb25b785519e7772
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245991"
---
# <a name="validate-new-devices"></a><span data-ttu-id="33eb4-103">Validar novos dispositivos</span><span class="sxs-lookup"><span data-stu-id="33eb4-103">Validate new devices</span></span>

<span data-ttu-id="33eb4-104">Se você é completamente novo para Área de Trabalho Gerenciada da Microsoft ou um assinante de longa duração, é melhor testar um exemplo de qualquer modelo de dispositivo que você esteja registrando no serviço pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="33eb4-104">Whether you're completely new to Microsoft Managed Desktop or a long-time subscriber, it's best to test an example of any device model you're enrolling in the service for the first time.</span></span> <span data-ttu-id="33eb4-105">Isso é verdadeiro se você está ordenando dispositivos novos ou reutilando dispositivos existentes, incluindo dispositivos recomendados para Área de Trabalho Gerenciada da Microsoft no site de dispositivos comerciais [Windows 10 Pro](https://www.microsoft.com/windowsforbusiness/view-all-devices) Loja.</span><span class="sxs-lookup"><span data-stu-id="33eb4-105">This is true whether you're ordering brand-new devices or reusing existing ones, including devices recommended for Microsoft Managed Desktop on the [Shop Windows 10 Pro business devices](https://www.microsoft.com/windowsforbusiness/view-all-devices) site.</span></span> <span data-ttu-id="33eb4-106">Nesse site, veja os dispositivos recomendados para uso com o serviço expandindo **Recursos** na área **Filtrar** por área e selecionando **Área de Trabalho Gerenciada da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="33eb4-106">At that site, view the devices recommended for use with the service by expanding **Features** in the **Filter by** area, and then selecting **Microsoft Managed Desktop**.</span></span> <span data-ttu-id="33eb4-107">Validar dispositivos garante que eles entregarão a experiência do usuário esperada.</span><span class="sxs-lookup"><span data-stu-id="33eb4-107">Validating devices ensures that they'll deliver the user experience you expect.</span></span>

## <a name="validate-devices"></a><span data-ttu-id="33eb4-108">Validar dispositivos</span><span class="sxs-lookup"><span data-stu-id="33eb4-108">Validate devices</span></span>

1. <span data-ttu-id="33eb4-109">Veja um ou mais exemplos de novos modelos por meio das etapas nos seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="33eb4-109">Take one or more examples of new models through the steps in the following articles:</span></span>
    - [<span data-ttu-id="33eb4-110">Configurar dispositivos de Área de Trabalho Gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="33eb4-110">Set up Microsoft Managed Desktop devices</span></span>](set-up-devices.md)
    - [<span data-ttu-id="33eb4-111">Localizar a experiência do usuário</span><span class="sxs-lookup"><span data-stu-id="33eb4-111">Localize the user experience</span></span>](localization.md)
    - [<span data-ttu-id="33eb4-112">Experiência da primeira execução com o piloto automático e a página de status do registro</span><span class="sxs-lookup"><span data-stu-id="33eb4-112">First-run experience with Autopilot and the Enrollment Status Page</span></span>](esp-first-run.md)
    - [<span data-ttu-id="33eb4-113">Serviço de localização do Windows 10</span><span class="sxs-lookup"><span data-stu-id="33eb4-113">Windows 10 location service</span></span>](device-location.md)
    - [<span data-ttu-id="33eb4-114">Introdução ao controle de aplicativos</span><span class="sxs-lookup"><span data-stu-id="33eb4-114">Get started with app control</span></span>](get-started-app-control.md)
    - [<span data-ttu-id="33eb4-115">Implantar aplicativos em dispositivos</span><span class="sxs-lookup"><span data-stu-id="33eb4-115">Deploy apps to devices</span></span>](deploy-apps.md)
2. <span data-ttu-id="33eb4-116">Verifique se as experiências a seguir funcionam sem falhas, erros ou prompts:</span><span class="sxs-lookup"><span data-stu-id="33eb4-116">Verify that the following experiences work without any failures, errors, or prompts:</span></span>
    - <span data-ttu-id="33eb4-117">A experiência do Piloto Automático após ingressar na rede e o usuário entrar</span><span class="sxs-lookup"><span data-stu-id="33eb4-117">The Autopilot experience after joining the network and the user signs in</span></span>
    - <span data-ttu-id="33eb4-118">Se você habilitar a Página de Status do [Registro,](esp-first-run.md)ela funcionará.</span><span class="sxs-lookup"><span data-stu-id="33eb4-118">If you've enabled the [Enrollment Status Page](esp-first-run.md), it works.</span></span>
    - <span data-ttu-id="33eb4-119">O usuário pode entrar em Office aplicativos</span><span class="sxs-lookup"><span data-stu-id="33eb4-119">User can sign into to Office applications</span></span>
    - <span data-ttu-id="33eb4-120">OneDrive sincronização de pastas, incluindo Windows Desktop, Documents e Pictures</span><span class="sxs-lookup"><span data-stu-id="33eb4-120">OneDrive folders sync, including Windows Desktop, Documents, and Pictures</span></span>
    - <span data-ttu-id="33eb4-121">O dispositivo recebe atualizações, políticas e aplicativos de linha de negócios</span><span class="sxs-lookup"><span data-stu-id="33eb4-121">Device receives updates, policies, and line-of-business applications</span></span>
3. <span data-ttu-id="33eb4-122">Revise os dispositivos e requisitos de hardware relatados no relatório de inventário de [dispositivos](../working-with-managed-desktop/device-inventory-report.md) para verificar se eles corresponderão ao que você espera.</span><span class="sxs-lookup"><span data-stu-id="33eb4-122">Review the reported devices and hardware requirements in the [Device inventory report](../working-with-managed-desktop/device-inventory-report.md) to check that they match what you expect.</span></span>

<span data-ttu-id="33eb4-123">Se ocorrer algum problema, você poderá [solicitar suporte](../working-with-managed-desktop/admin-support.md) no portal de administração.</span><span class="sxs-lookup"><span data-stu-id="33eb4-123">If any problems occur, you can [request support](../working-with-managed-desktop/admin-support.md) in the Admin portal.</span></span>

<span data-ttu-id="33eb4-124">Se tudo correr bem, você estará pronto para solicitar o restante dos dispositivos validados necessários para sua implantação.</span><span class="sxs-lookup"><span data-stu-id="33eb4-124">If everything goes well, you're ready to order the rest of the validated devices you need for your deployment.</span></span>