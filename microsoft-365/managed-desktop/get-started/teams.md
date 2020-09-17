---
title: Microsoft Teams
description: Como o Microsoft Teams é instalado nos dispositivos e atualizado posteriormente
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação, aplicativos, aplicativos de linha de negócios, aplicativos LOB
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: ITPro
ms.openlocfilehash: ea2ef7637a8d360e3b598aec4852425d977ae4ec
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950899"
---
# <a name="microsoft-teams"></a><span data-ttu-id="42b88-104">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="42b88-104">Microsoft Teams</span></span>

<span data-ttu-id="42b88-105">O Microsoft [Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) é um [aplicativo de mensagens](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) para sua organização que também fornece um espaço de trabalho para colaboração e comunicação em tempo real, reuniões e compartilhamento de arquivos e aplicativos.</span><span class="sxs-lookup"><span data-stu-id="42b88-105">[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) is a [messaging app](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) for your organization that also provides a workspace for real-time collaboration and communication, meetings, and file and app sharing.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="42b88-106">Implantação inicial</span><span class="sxs-lookup"><span data-stu-id="42b88-106">Initial deployment</span></span>

<span data-ttu-id="42b88-107">A maioria dos fornecedores de hardware ainda não incluiu o Teams como parte de suas imagens, portanto, o Microsoft Managed desktop implanta o Teams em seus dispositivos usando o Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="42b88-107">Most hardware vendors don't yet include Teams as a part of their images, so Microsoft Managed Desktop deploys Teams to your devices by using Microsoft Intune.</span></span> <span data-ttu-id="42b88-108">Todos os dispositivos gerenciados têm o [pacote Teams. msi](https://docs.microsoft.com/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) instalado, garantindo que todos os usuários que entram em um dispositivo tenham o Microsoft Teams prontos para usar.</span><span class="sxs-lookup"><span data-stu-id="42b88-108">All managed devices have the [Teams .msi package](https://docs.microsoft.com/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) installed, ensuring that all users who sign in to a device have Microsoft Teams ready to use.</span></span> <span data-ttu-id="42b88-109">Quando o pacote termina de instalar pela primeira vez, o Microsoft Teams é iniciado automaticamente e adiciona um atalho à área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="42b88-109">When the package first finishes installing, Teams automatically starts and adds a shortcut to the desktop.</span></span>

### <a name="microsoft-intune-changes"></a><span data-ttu-id="42b88-110">Alterações do Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="42b88-110">Microsoft Intune changes</span></span>

<span data-ttu-id="42b88-111">O Microsoft Managed desktop adiciona dois aplicativos à sua organização do Azure AD para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="42b88-111">Microsoft Managed Desktop adds two applications to your Azure AD organization for Microsoft Teams.</span></span> <span data-ttu-id="42b88-112">Eles são implantados em clientes de 64 bits ou 32 bits conforme apropriado para o dispositivo:</span><span class="sxs-lookup"><span data-stu-id="42b88-112">They are deployed to either 64-bit or 32-bit clients as appropriate for the device:</span></span>  

- <span data-ttu-id="42b88-113">Local de trabalho moderno – instalador de todo o computador do teams x64</span><span class="sxs-lookup"><span data-stu-id="42b88-113">Modern Workplace – Teams Machine Wide Installer x64</span></span>  
- <span data-ttu-id="42b88-114">Local de trabalho moderno – x32 de instalador de todo o computador de equipes</span><span class="sxs-lookup"><span data-stu-id="42b88-114">Modern Workplace – Teams Machine Wide Installer x32</span></span>

## <a name="updates"></a><span data-ttu-id="42b88-115">Atualizações</span><span class="sxs-lookup"><span data-stu-id="42b88-115">Updates</span></span>

<span data-ttu-id="42b88-116">O Teams segue um caminho de atualização separado dos aplicativos da Microsoft 365 para empresas e o cliente de desktop atualiza-se automaticamente.</span><span class="sxs-lookup"><span data-stu-id="42b88-116">Teams follows a separate update path from Microsoft 365 Apps for enterprise and the desktop client updates itself automatically.</span></span> <span data-ttu-id="42b88-117">O Microsoft Teams verifica as atualizações em intervalos de algumas horas, baixa-as e aguarda o computador ficar ocioso antes de instalar silenciosamente a atualização.</span><span class="sxs-lookup"><span data-stu-id="42b88-117">Teams checks for updates every few hours, downloads them, and then waits for the computer to be idle before silently installing the update.</span></span>  

<span data-ttu-id="42b88-118">O grupo de produtos Teams não permite que os administradores controlem atualizações, portanto, o Microsoft Managed desktop usa o [canal de atualização automática padrão](https://docs.microsoft.com/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating).</span><span class="sxs-lookup"><span data-stu-id="42b88-118">The Teams product group doesn't allow admins to control updates, so Microsoft Managed Desktop uses the [standard automatic update channel](https://docs.microsoft.com/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating).</span></span>

### <a name="manually-updating-teams"></a><span data-ttu-id="42b88-119">Atualizando manualmente o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="42b88-119">Manually updating Teams</span></span>

<span data-ttu-id="42b88-120">Os usuários individuais também podem baixar atualizações selecionando **verificar se há atualizações**   no menu suspenso de **perfil**   no canto superior direito do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="42b88-120">Individual users can also download updates by selecting **Check for updates** on the **Profile** drop-down menu at the top right of the app.</span></span> <span data-ttu-id="42b88-121">Se uma atualização estiver disponível, ela será baixada e instalada silenciosamente quando o computador estiver ocioso.</span><span class="sxs-lookup"><span data-stu-id="42b88-121">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

## <a name="delivery-optimization-of-updates"></a><span data-ttu-id="42b88-122">Otimização de entrega de atualizações</span><span class="sxs-lookup"><span data-stu-id="42b88-122">Delivery optimization of updates</span></span>

<span data-ttu-id="42b88-123">A otimização de entrega para atualizações do teams é ativada por padrão e não requer nenhuma ação de administradores ou usuários.</span><span class="sxs-lookup"><span data-stu-id="42b88-123">Delivery optimization for Teams updates is turned on by default and requires no action from admins or users.</span></span> 