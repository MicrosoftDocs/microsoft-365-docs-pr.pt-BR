---
title: Critérios de saída da infraestrutura de gerenciamento de dispositivo móvel
description: O Microsoft 365 Enterprise inclui gerenciamento de dispositivos móveis usando o Microsoft Intune. Revise os requisitos e pré-requisitos, configure o Intune usando seu recurso do Azure Active Directory, registre os dispositivos iOS, macOS, Android e Windows, implante aplicativos, crie um perfil de configuração, use uma política de conformidade e habilite o acesso condicional para dispositivos móveis gerenciamento de dispositivos com o Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, documentação do Microsoft 365, gerenciamento de dispositivos móveis, Intune
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2019
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: 14f216fe352d9108fe69028731f4c94dfb9d19f7
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291228"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a><span data-ttu-id="0d636-105">Critérios de saída da infraestrutura de gerenciamento de dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="0d636-105">Mobile device management infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

<span data-ttu-id="0d636-106">*Isso se aplica às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="0d636-106">*This applies to the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="0d636-107">Certifique-se de que a sua configuração atenda aos requisitos a seguir para a infraestrutura de gerenciamento de dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="0d636-107">Ensure that your configuration meets the following requirements for mobile device management infrastructure.</span></span>

- <span data-ttu-id="0d636-108">O Intune está configurado, incluindo a criação de grupos e usuários do Azure AD para aplicar as regras da sua organização para dispositivos.</span><span class="sxs-lookup"><span data-stu-id="0d636-108">Intune is set up, including the creation of Azure AD users and groups to apply your organization's rules for devices.</span></span>
- <span data-ttu-id="0d636-109">Você registrou dispositivos no Intune para que eles possam receber as políticas que você criou.</span><span class="sxs-lookup"><span data-stu-id="0d636-109">You have enrolled devices in Intune so that the devices can receive the policies you create.</span></span>
- <span data-ttu-id="0d636-110">Os aplicativos são adicionados aos dispositivos para que os usuários tenham acesso a serviços de nuvem do Microsoft 365 da sua organização, como o Exchange Online e o SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="0d636-110">Apps are added to devices so your users get access to your organization's Microsoft 365 cloud services, such as Exchange Online and SharePoint Online.</span></span>
- <span data-ttu-id="0d636-111">As configurações e os recursos estão definidos e aplicados aos seus dispositivos usando os usuários e os grupos do Azure AD que você criar, o que pode incluir habilitar antivírus e restringir aplicativos específicos.</span><span class="sxs-lookup"><span data-stu-id="0d636-111">Features and settings are configured and applied to your devices using the Azure AD users and groups you create, which might include enabling anti-virus and restricting specific apps.</span></span>
- <span data-ttu-id="0d636-p102">As políticas de conformidade estão prontas para exigir um firewall ou tamanho de senha em um dispositivo. Se os dispositivos não estiverem em conformidade, o acesso condicional bloqueará o acesso aos dados da organização.</span><span class="sxs-lookup"><span data-stu-id="0d636-p102">Compliance policies are in place to require a firewall or a password length on a device. If devices aren't compliant, conditional access blocks access to your organization's data.</span></span>



## <a name="results-and-next-steps"></a><span data-ttu-id="0d636-114">Resultados e próximas etapas</span><span class="sxs-lookup"><span data-stu-id="0d636-114">Results and next steps</span></span>

<span data-ttu-id="0d636-115">Seus dispositivos estão registrados no Intune e configurados com as políticas apropriadas.</span><span class="sxs-lookup"><span data-stu-id="0d636-115">Your devices are enrolled in Intune and configured with the appropriate policies.</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| <span data-ttu-id="0d636-116">Se você estiver seguindo as fases da implantação de ponta a ponta do Microsoft 365 Enterprise, sua próxima fase será a [proteção de informações](infoprotect-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="0d636-116">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [information protection](infoprotect-infrastructure.md).</span></span> |
