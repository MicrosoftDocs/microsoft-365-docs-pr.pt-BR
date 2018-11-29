---
title: Critérios de saída de infraestrutura de gerenciamento de dispositivo móvel
description: Microsoft 365 Enterprise inclui o gerenciamento de dispositivos móveis usando o Microsoft Intune. Examine os requisitos e pré-requisitos, configurar Intune usando seu recurso do Active Directory do Azure, registrar iOS, macOS, Android e Windows dispositivos, implantar apps, crie um perfil de configurar, usar uma política de conformidade e habilitar o acesso condicional para dispositivos móveis gerenciamento de dispositivo com Microsoft 365 Enterprise.
keywords: 365 da Microsoft, Microsoft 365 Enterprise, Microsoft 365 documentação, gerenciamento de dispositivos móveis, Intune
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/10/2018
ms.topic: article
audience: ITPro
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
ms.custom: microsoft-intune
ms.openlocfilehash: b511052698f42a07df5fc25aeaad7fc7f00c2a6e
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26864850"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a><span data-ttu-id="3a91c-105">Critérios de saída de infraestrutura de gerenciamento de dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="3a91c-105">Mobile device management infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

<span data-ttu-id="3a91c-106">*Isso se aplica às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="3a91c-106">*This applies to the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="3a91c-107">Antes de passar para a próxima fase no processo de implantação, certifique-se de que sua configuração atende aos seguintes requisitos de infraestrutura de gerenciamento de dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="3a91c-107">Before you move on to the next phase in the deployment process, ensure that your configuration meets the following requirements for mobile device management infrastructure.</span></span>

- <span data-ttu-id="3a91c-108">O Intune está configurado, incluindo a criação de grupos e usuários do Azure AD para aplicar as regras da sua organização para dispositivos.</span><span class="sxs-lookup"><span data-stu-id="3a91c-108">Intune is set up, including the creation of Azure AD users and groups to apply your organization's rules for devices.</span></span>
- <span data-ttu-id="3a91c-109">Você registrou dispositivos no Intune para que eles possam receber as políticas que você criou.</span><span class="sxs-lookup"><span data-stu-id="3a91c-109">You have enrolled devices in Intune so that the devices can receive the policies you create.</span></span>
- <span data-ttu-id="3a91c-110">Os aplicativos são adicionados aos dispositivos para que os usuários tenham acesso a serviços de nuvem do Microsoft 365 da sua organização, como o Exchange Online e o SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="3a91c-110">Apps are added to devices so your users get access to your organization's Microsoft 365 cloud services, such as Exchange Online and SharePoint Online.</span></span>
- <span data-ttu-id="3a91c-111">As configurações e os recursos estão definidos e aplicados aos seus dispositivos usando os usuários e os grupos do Azure AD que você criar, o que pode incluir habilitar antivírus e restringir aplicativos específicos.</span><span class="sxs-lookup"><span data-stu-id="3a91c-111">Features and settings are configured and applied to your devices using the Azure AD users and groups you create, which might include enabling anti-virus and restricting specific apps.</span></span>
- <span data-ttu-id="3a91c-p102">As políticas de conformidade estão prontas para exigir um firewall ou tamanho de senha em um dispositivo. Se os dispositivos não estiverem em conformidade, o acesso condicional bloqueará o acesso aos dados da organização.</span><span class="sxs-lookup"><span data-stu-id="3a91c-p102">Compliance policies are in place to require a firewall or a password length on a device. If devices aren't compliant, conditional access blocks access to your organization's data.</span></span>

## <a name="next-phase"></a><span data-ttu-id="3a91c-114">Próxima fase</span><span class="sxs-lookup"><span data-stu-id="3a91c-114">Next phase</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| <span data-ttu-id="3a91c-115">A próxima fase no processo de implantação de ponta a ponta para Microsoft 365 Enterprise é a [proteção de informações](infoprotect-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="3a91c-115">Your next phase in the end-to-end deployment process for Microsoft 365 Enterprise is [information protection](infoprotect-infrastructure.md).</span></span> |
