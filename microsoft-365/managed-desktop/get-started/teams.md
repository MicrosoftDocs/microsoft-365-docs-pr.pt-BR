---
title: Microsoft Teams
description: Como Teams é instalado em dispositivos e atualizado posteriormente
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação, aplicativos, aplicativos de linha de negócios, aplicativos LOB
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: ITPro
ms.openlocfilehash: 01a3adc7829bbb94f36649f69ba6ef15dbe6b3c2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920651"
---
# <a name="microsoft-teams"></a><span data-ttu-id="075bb-104">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="075bb-104">Microsoft Teams</span></span>

<span data-ttu-id="075bb-105">[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) é um aplicativo [de](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) mensagens para sua organização que também fornece um espaço de trabalho para colaboração e comunicação em tempo real, reuniões e compartilhamento de arquivos e aplicativos.</span><span class="sxs-lookup"><span data-stu-id="075bb-105">[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) is a [messaging app](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) for your organization that also provides a workspace for real-time collaboration and communication, meetings, and file and app sharing.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="075bb-106">Implantação inicial</span><span class="sxs-lookup"><span data-stu-id="075bb-106">Initial deployment</span></span>

<span data-ttu-id="075bb-107">A maioria dos fornecedores de hardware ainda não inclui Teams como parte de suas imagens, portanto, Área de Trabalho Gerenciada da Microsoft implanta o Teams em seus dispositivos usando Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="075bb-107">Most hardware vendors don't yet include Teams as a part of their images, so Microsoft Managed Desktop deploys Teams to your devices by using Microsoft Intune.</span></span> <span data-ttu-id="075bb-108">Todos os dispositivos gerenciados têm o pacote [Teams .msi](/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) instalado, garantindo que todos os usuários que entrarem em um dispositivo tenham Microsoft Teams prontos para uso.</span><span class="sxs-lookup"><span data-stu-id="075bb-108">All managed devices have the [Teams .msi package](/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) installed, ensuring that all users who sign in to a device have Microsoft Teams ready to use.</span></span> <span data-ttu-id="075bb-109">Quando o pacote terminar de instalar pela primeira vez, Teams iniciará automaticamente e adicionará um atalho à área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="075bb-109">When the package first finishes installing, Teams automatically starts and adds a shortcut to the desktop.</span></span>

### <a name="microsoft-intune-changes"></a><span data-ttu-id="075bb-110">Microsoft Intune alterações</span><span class="sxs-lookup"><span data-stu-id="075bb-110">Microsoft Intune changes</span></span>

<span data-ttu-id="075bb-111">Área de Trabalho Gerenciada da Microsoft adiciona dois aplicativos à sua organização do Azure AD para Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="075bb-111">Microsoft Managed Desktop adds two applications to your Azure AD organization for Microsoft Teams.</span></span> <span data-ttu-id="075bb-112">Eles são implantados em clientes de 64 ou 32 bits, conforme apropriado para o dispositivo:</span><span class="sxs-lookup"><span data-stu-id="075bb-112">They are deployed to either 64-bit or 32-bit clients as appropriate for the device:</span></span>  

- <span data-ttu-id="075bb-113">Local de trabalho moderno – Teams instalador x64 de toda a máquina</span><span class="sxs-lookup"><span data-stu-id="075bb-113">Modern Workplace – Teams Machine Wide Installer x64</span></span>  
- <span data-ttu-id="075bb-114">Local de trabalho moderno – Teams instalador x32 de toda a máquina</span><span class="sxs-lookup"><span data-stu-id="075bb-114">Modern Workplace – Teams Machine Wide Installer x32</span></span>

## <a name="updates"></a><span data-ttu-id="075bb-115">Atualizações</span><span class="sxs-lookup"><span data-stu-id="075bb-115">Updates</span></span>

<span data-ttu-id="075bb-116">Teams segue um caminho de atualização separado do Microsoft 365 Apps para Grandes Empresas e o cliente da área de trabalho se atualiza automaticamente.</span><span class="sxs-lookup"><span data-stu-id="075bb-116">Teams follows a separate update path from Microsoft 365 Apps for enterprise and the desktop client updates itself automatically.</span></span> <span data-ttu-id="075bb-117">Teams verifica se há atualizações a cada poucas horas, baixa-as e aguarda o computador ficar ocioso antes de instalar silenciosamente a atualização.</span><span class="sxs-lookup"><span data-stu-id="075bb-117">Teams checks for updates every few hours, downloads them, and then waits for the computer to be idle before silently installing the update.</span></span>  

<span data-ttu-id="075bb-118">O Teams de produtos não permite que os administradores controlem as atualizações, portanto, Área de Trabalho Gerenciada da Microsoft usa o canal de atualização [automática padrão](/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating).</span><span class="sxs-lookup"><span data-stu-id="075bb-118">The Teams product group doesn't allow admins to control updates, so Microsoft Managed Desktop uses the [standard automatic update channel](/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating).</span></span>

### <a name="manually-updating-teams"></a><span data-ttu-id="075bb-119">Atualizando manualmente Teams</span><span class="sxs-lookup"><span data-stu-id="075bb-119">Manually updating Teams</span></span>

<span data-ttu-id="075bb-120">Os usuários individuais também podem baixar atualizações selecionando **Verificar** se há atualizações no menu suspenso Perfil no   canto superior direito do  \*\*\*\*   aplicativo.</span><span class="sxs-lookup"><span data-stu-id="075bb-120">Individual users can also download updates by selecting **Check for updates** on the **Profile** drop-down menu at the top right of the app.</span></span> <span data-ttu-id="075bb-121">Se uma atualização estiver disponível, ela será baixada e instalada silenciosamente quando o computador estiver ocioso.</span><span class="sxs-lookup"><span data-stu-id="075bb-121">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

## <a name="delivery-optimization-of-updates"></a><span data-ttu-id="075bb-122">Otimização de entrega de atualizações</span><span class="sxs-lookup"><span data-stu-id="075bb-122">Delivery optimization of updates</span></span>

<span data-ttu-id="075bb-123">A otimização de entrega Teams as atualizações estão ativas por padrão e não exigem nenhuma ação de administradores ou usuários.</span><span class="sxs-lookup"><span data-stu-id="075bb-123">Delivery optimization for Teams updates is turned on by default and requires no action from admins or users.</span></span>