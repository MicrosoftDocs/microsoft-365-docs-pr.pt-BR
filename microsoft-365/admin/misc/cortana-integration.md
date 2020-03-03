---
title: Integração da Cortana com o Office 365
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7257cb50-0d5c-4f7a-ac2e-9fe5d13bb5cb
description: 'Saiba como usar a Cortana, quando estiver integrada ao Office 365. Você pode desativar a Cortana no centro de administração para restringir o acesso aos dados da sua organização. '
ms.openlocfilehash: 8f20c9b96ee57dcdf5da99dc08ffeb72465bc515
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361432"
---
# <a name="cortana-in-office-365"></a><span data-ttu-id="b50bc-104">Cortana no Office 365</span><span class="sxs-lookup"><span data-stu-id="b50bc-104">Cortana in Office 365</span></span>

<span data-ttu-id="b50bc-105">A Cortana é um assistente digital baseado em nuvem e o serviço do Microsoft 365 e do Office 365 que funciona em seus dispositivos e serviços da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b50bc-105">Cortana is a cloud-based digital assistant and Microsoft 365 and Office 365 service that works across your devices and Microsoft services.</span></span> <span data-ttu-id="b50bc-106">A Cortana pode usar as informações armazenadas no Microsoft 365 e no Office 365 para ajudar as pessoas na sua organização a se manter atualizado e a obter ideias, tarefas sugeridas e ajuda com suas reuniões, documentos e contatos.</span><span class="sxs-lookup"><span data-stu-id="b50bc-106">Cortana can use information stored in Microsoft 365 and Office 365 to help people in your organization stay up to date and get insights, suggested tasks, and help with their meetings, documents, and contacts.</span></span>
  
## <a name="info-for-admins"></a><span data-ttu-id="b50bc-107">Informações para administradores</span><span class="sxs-lookup"><span data-stu-id="b50bc-107">Info for admins</span></span>

<span data-ttu-id="b50bc-108">A conformidade é um compromisso que a Microsoft faz para clientes corporativos.</span><span class="sxs-lookup"><span data-stu-id="b50bc-108">Compliance is a commitment that Microsoft makes to enterprise customers.</span></span> [<span data-ttu-id="b50bc-109">Saiba mais sobre a estrutura de conformidade da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b50bc-109">Learn more about the Microsoft compliance framework.</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=2109173)

<span data-ttu-id="b50bc-110">Consistente com outros serviços do Microsoft 365 e do Office 365, os recursos de Cortana compatíveis são protegidos e protegidos sujeitos aos termos de serviço online que incluem um conjunto de promessas envolvendo proteção de dados do usuário contra perdas acidentais, alterações divulgação ou acesso não autorizado, ou destruição ilegal.</span><span class="sxs-lookup"><span data-stu-id="b50bc-110">Consistent with other Microsoft 365 and Office 365 services, compliant Cortana features are protected and secured subject to the Online Service Terms that includes a set of promises involving protection of user data against accidental loss, alteration, unauthorized disclosure or access, or unlawful destruction.</span></span> <span data-ttu-id="b50bc-111">Todos os outros recursos da Cortana (ou seja, serviços de conexão opcional conectados) estão sujeitos ao [contrato de serviços da Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=2109174) e à política de privacidade da [Microsoft.](https://go.microsoft.com/fwlink/p/?LinkId=2109175)</span><span class="sxs-lookup"><span data-stu-id="b50bc-111">All other Cortana features (i.e., Cortana optional connected services) are subject to the [Microsoft Services Agreement](https://go.microsoft.com/fwlink/p/?LinkId=2109174) and  [Microsoft Privacy Statement.](https://go.microsoft.com/fwlink/p/?LinkId=2109175)</span></span>

<span data-ttu-id="b50bc-112">Os serviços da Cortana são divididos em duas categorias de dados, **compatíveis** e **serviços opcionais conectados**, que você pode controlar.</span><span class="sxs-lookup"><span data-stu-id="b50bc-112">Cortana services are broken into two data categories, **compliant** and **optional connected services**, which you can control.</span></span>

## <a name="turn-off-cortana-optional-connected-services"></a><span data-ttu-id="b50bc-113">Desativar serviços conectados opcionais da Cortana</span><span class="sxs-lookup"><span data-stu-id="b50bc-113">Turn off Cortana optional connected services</span></span>

<span data-ttu-id="b50bc-114">Os serviços conectados opcionais da Cortana podem ser desativados para os funcionários da sua organização.</span><span class="sxs-lookup"><span data-stu-id="b50bc-114">Cortana optional connected services can be turned off for employees at your organization.</span></span> <span data-ttu-id="b50bc-115">Isso desativará os serviços conectados opcionais da Cortana na Cortana no Windows e o aplicativo móvel da Cortana.</span><span class="sxs-lookup"><span data-stu-id="b50bc-115">This will disable Cortana optional connected services in Cortana on Windows and the Cortana mobile app.</span></span> <span data-ttu-id="b50bc-116">Isso inclui lembretes, listas, tarefas e outros recursos da Cortana.</span><span class="sxs-lookup"><span data-stu-id="b50bc-116">This includes Cortana reminders, lists, tasks, and other features.</span></span> <span data-ttu-id="b50bc-117">Os serviços na categoria compatível (ou seja, as experiências OST da Cortana), como o email de resumo da Cortana e jogar meus emails no Outlook Mobile, permanecerão ativos.</span><span class="sxs-lookup"><span data-stu-id="b50bc-117">Services in the compliant category (i.e., Cortana OST experiences), such as Cortana’s Briefing email, and Play My Emails in Outlook mobile, will remain active.</span></span>

1. <span data-ttu-id="b50bc-118">No centro de administração do Microsoft 365\*\*\*\* , **selecione** > configurações e selecione **Cortana**.</span><span class="sxs-lookup"><span data-stu-id="b50bc-118">In the Microsoft 365 admin center, select **Settings** > **Settings** and select **Cortana**.</span></span>

4. <span data-ttu-id="b50bc-119">Marque a caixa de seleção **permitir que as experiências conectadas opcionais da Cortana usem os dados hospedados pela Microsoft da sua organização** para habilitar ou desabilitar experiências conectadas da Cortana.</span><span class="sxs-lookup"><span data-stu-id="b50bc-119">Select the checkbox for **Allow Cortana optional connected experiences to use your organizations's Microsoft hosted data** to enable or disable Cortana connected experiences.</span></span>

5. <span data-ttu-id="b50bc-120">Selecione **Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="b50bc-120">Select **Save changes**.</span></span>

## <a name="turn-off-cortana-ost-experiences"></a><span data-ttu-id="b50bc-121">Desativar as experiências OST da Cortana</span><span class="sxs-lookup"><span data-stu-id="b50bc-121">Turn off Cortana OST experiences</span></span>

<span data-ttu-id="b50bc-122">Os funcionários da sua organização podem recusar experiências do OST da Cortana individualmente, seguindo as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="b50bc-122">Your organization's employees can opt out of Cortana OST experiences individually by following the steps below.</span></span>

1. <span data-ttu-id="b50bc-123">Abra o Outlook Mobile.</span><span class="sxs-lookup"><span data-stu-id="b50bc-123">Open Outlook mobile.</span></span>

2. <span data-ttu-id="b50bc-124">Vá para **configurações**.</span><span class="sxs-lookup"><span data-stu-id="b50bc-124">Go to **Settings**.</span></span>
  
3. <span data-ttu-id="b50bc-125">Selecione **reproduzir meus emails**.</span><span class="sxs-lookup"><span data-stu-id="b50bc-125">Select **Play My Emails**.</span></span>

4. <span data-ttu-id="b50bc-126">Mova a alternância para desativá-la nas contas que você deseja desabilitar.</span><span class="sxs-lookup"><span data-stu-id="b50bc-126">Move the toggle to off on the accounts you want to disable.</span></span>

### <a name="briefing-email"></a><span data-ttu-id="b50bc-127">Email de resumo</span><span class="sxs-lookup"><span data-stu-id="b50bc-127">Briefing email</span></span>

<span data-ttu-id="b50bc-128">Desabilitar a Cortana na barra de tarefas não desabilitará o email de resumo da Cortana.</span><span class="sxs-lookup"><span data-stu-id="b50bc-128">Disabling Cortana on the taskbar won't disable Cortana’s Briefing email.</span></span> <span data-ttu-id="b50bc-129">Os funcionários devem cancelar a assinatura individualmente.</span><span class="sxs-lookup"><span data-stu-id="b50bc-129">Employees must unsubscribe individually.</span></span> <span data-ttu-id="b50bc-130">As pessoas da sua organização podem recusar o email de resumo da Cortana selecionando **cancelar assinatura** no rodapé da mensagem.</span><span class="sxs-lookup"><span data-stu-id="b50bc-130">Individuals from your organization can opt out of Cortana’s Briefing email by selecting **Unsubscribe** in the footer of the message.</span></span>
