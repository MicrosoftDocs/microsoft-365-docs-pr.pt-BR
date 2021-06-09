---
title: Trabalhar com Serviços de consultoria da Microsoft
description: Preparação e etapas a seguir para trabalhar com o MCS para empacotar seus aplicativos
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
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
ms.openlocfilehash: 7a967f5e4b2678b55ed87f2eaa68590703c55805
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840881"
---
# <a name="working-with-microsoft-consulting-services"></a><span data-ttu-id="58e02-104">Trabalhar com Serviços de consultoria da Microsoft</span><span class="sxs-lookup"><span data-stu-id="58e02-104">Working with Microsoft Consulting Services</span></span>

<span data-ttu-id="58e02-105">Você pode se envolver com o Microsoft Consulting Services (MCS) para obter seus aplicativos empacotados para uso com Área de Trabalho Gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="58e02-105">You can engage with Microsoft Consulting Services (MCS) to get your apps packaged for use with Microsoft Managed Desktop.</span></span> <span data-ttu-id="58e02-106">Para obter detalhes exatos, trabalhe com seu representante de conta para entrar em contato com MCS e escopo do projeto de empacotamento de aplicativos específico.</span><span class="sxs-lookup"><span data-stu-id="58e02-106">For exact details, work with your account representative to contact MCS and scope your specific app packaging project.</span></span>

## <a name="roles-and-responsibilities"></a><span data-ttu-id="58e02-107">Funções e responsabilidades</span><span class="sxs-lookup"><span data-stu-id="58e02-107">Roles and responsibilities</span></span>

<span data-ttu-id="58e02-108">Para trabalhar com o empacotamento de aplicativos MCS, **você deve fornecer estes elementos:**</span><span class="sxs-lookup"><span data-stu-id="58e02-108">To work with MCS app packaging, **you must provide these elements**:</span></span>

- <span data-ttu-id="58e02-109">Os arquivos do instalador de origem (por exemplo, setup.exe ou .msi).</span><span class="sxs-lookup"><span data-stu-id="58e02-109">The source installer files (for example, setup.exe or .msi).</span></span>
- <span data-ttu-id="58e02-110">As instruções de instalação, especificando detalhes sobre como a instalação final deve ser.</span><span class="sxs-lookup"><span data-stu-id="58e02-110">The installation instructions, specifying details about how the final installation should look.</span></span> <span data-ttu-id="58e02-111">Por exemplo, deve haver um atalho da área de trabalho para o aplicativo?</span><span class="sxs-lookup"><span data-stu-id="58e02-111">For example, should there be a desktop shortcut to the app?</span></span> <span data-ttu-id="58e02-112">Qual deve ser a visibilidade do aplicativo?</span><span class="sxs-lookup"><span data-stu-id="58e02-112">What should the app's visibility be?</span></span> <span data-ttu-id="58e02-113">O aplicativo deve se conectar a um servidor e, em caso algum, qual deles?</span><span class="sxs-lookup"><span data-stu-id="58e02-113">Should the app connect to a server and if so, which one?</span></span> <span data-ttu-id="58e02-114">Para obter detalhes, consulte o modelo [de solicitação de empacotamento de aplicativos](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).</span><span class="sxs-lookup"><span data-stu-id="58e02-114">For details, see the [application packaging request template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).</span></span>
- <span data-ttu-id="58e02-115">Você deve executar seu próprio teste de aceitação para verificar se o aplicativo funciona conforme necessário em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="58e02-115">You must perform your own acceptance testing to verify that the app works as you need it to in your environment.</span></span>

<span data-ttu-id="58e02-116">**O MCS tratará dessas ações:**</span><span class="sxs-lookup"><span data-stu-id="58e02-116">**MCS will take care of these actions:**</span></span>

- <span data-ttu-id="58e02-117">Verificar se o aplicativo é proibido ou restrito no ambiente Área de Trabalho Gerenciada da Microsoft ambiente.</span><span class="sxs-lookup"><span data-stu-id="58e02-117">Checking whether the app is prohibited or restricted in the Microsoft Managed Desktop environment.</span></span>
- <span data-ttu-id="58e02-118">Teste de instalação, início e desinstalação do aplicativo para garantir a compatibilidade com Windows 10.</span><span class="sxs-lookup"><span data-stu-id="58e02-118">Testing of installation, starting, and uninstallation of the app to ensure compatibility with Windows 10.</span></span> <span data-ttu-id="58e02-119">Se o MCS descobrir um problema de compatibilidade, eles entregarão o aplicativo para o programa [de Garantia](/fasttrack/products-and-capabilities#app-assure) de Aplicativos para correção.</span><span class="sxs-lookup"><span data-stu-id="58e02-119">If MCS discovers a compatibility issue, they will hand off the app to the [App Assure](/fasttrack/products-and-capabilities#app-assure) program for remediation.</span></span>
- <span data-ttu-id="58e02-120">Empacotando o aplicativo para sua especificação e testando a implantação do aplicativo usando Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="58e02-120">Packaging the app to your specification and then testing app deployment by using Microsoft Intune.</span></span>

## <a name="app-delivery-schedule"></a><span data-ttu-id="58e02-121">Cronograma de entrega de aplicativos</span><span class="sxs-lookup"><span data-stu-id="58e02-121">App delivery schedule</span></span>

<span data-ttu-id="58e02-122">Inicie o processo de empacotamento carregando as informações do aplicativo no portal Área de Trabalho Gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="58e02-122">Start the packaging process by uploading the app information to the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="58e02-123">A equipe de empacotamento revisa novos envios toda quinta-feira.</span><span class="sxs-lookup"><span data-stu-id="58e02-123">The packaging team reviews new submissions every Thursday.</span></span> <span data-ttu-id="58e02-124">Após revisão e empacotamento, os aplicativos empacotados são entregues na sexta-feira seguinte.</span><span class="sxs-lookup"><span data-stu-id="58e02-124">After review and packaging, the packaged apps are delivered the following Friday.</span></span> <span data-ttu-id="58e02-125">Até cinco aplicativos por semana podem ser empacotados para iniciar, mas o serviço pode ser dimensionado para atender às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="58e02-125">Up to five apps per week can be packaged to start but the service can scale to meet your needs.</span></span>

![calendar showing app inflow on a Thursday (the 21st in this example), media validation the next day, packaging on the following Monday (the 25th) and app delivery on the subsequent Friday (the 29th)](../../media/MCS-cal.png)

<span data-ttu-id="58e02-127">Você será notificado depois que o aplicativo tiver sido entregue.</span><span class="sxs-lookup"><span data-stu-id="58e02-127">You'll be notified once the app has been delivered.</span></span> <span data-ttu-id="58e02-128">Nesse ponto, você tem 21 dias para realizar testes de aceitação e aprovar o trabalho no Área de Trabalho Gerenciada da Microsoft portal.</span><span class="sxs-lookup"><span data-stu-id="58e02-128">At that point, you have 21 days to perform acceptance testing and approve the work in the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="58e02-129">Se descobrir algum problema com o aplicativo durante o teste de aceitação, rejeite o aplicativo no portal Área de Trabalho Gerenciada da Microsoft e você será conectado por email com um empacotador MCS para entender e resolver o problema.</span><span class="sxs-lookup"><span data-stu-id="58e02-129">If discover some problem with the app during your acceptance testing, reject the app in the Microsoft Managed Desktop portal and you will be connected via email with an MCS packager to understand and resolve the issue.</span></span>

## <a name="testing-accounts-and-environment"></a><span data-ttu-id="58e02-130">Testar contas e ambiente</span><span class="sxs-lookup"><span data-stu-id="58e02-130">Testing accounts and environment</span></span>

<span data-ttu-id="58e02-131">Para que a equipe de empacotamento conclua a migração para Microsoft Intune, recomendamos que você forneça determinadas permissões:</span><span class="sxs-lookup"><span data-stu-id="58e02-131">For the packaging team to complete the migration to Microsoft Intune, we recommend that you provide certain permissions:</span></span>

- <span data-ttu-id="58e02-132">Acesso aos Microsoft Intune de implantação de aplicativos do Microsoft Intune para o empacotador adicionar e atribuir o aplicativo</span><span class="sxs-lookup"><span data-stu-id="58e02-132">Access to Microsoft Intune’s App Deployment capabilities for the packager to add and assign the app</span></span>
- <span data-ttu-id="58e02-133">Testar grupos, contas de usuário e licenças para que os empacotadores sejam capazes de testar os aplicativos</span><span class="sxs-lookup"><span data-stu-id="58e02-133">Test groups, user accounts, and licenses for the packagers to be able to test the apps</span></span>

<span data-ttu-id="58e02-134">O MCS usará essas permissões para executar as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="58e02-134">MCS will use those permissions to perform the following actions:</span></span>

- <span data-ttu-id="58e02-135">Garantir que o aplicativo funcione em máquina virtual configurada para Área de Trabalho Gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="58e02-135">Ensuring that the app works on virtual machine configured for Microsoft Managed Desktop</span></span>
- <span data-ttu-id="58e02-136">Carregando o aplicativo para Microsoft Intune para implantação para seus usuários</span><span class="sxs-lookup"><span data-stu-id="58e02-136">Uploading the app to Microsoft Intune for deployment to your users</span></span>

<span data-ttu-id="58e02-137">Sem essas permissões, é possível que o MCS avance, mas eles não poderão carregar os aplicativos em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="58e02-137">Without these permissions, it is possible for MCS to move forward, but they will not be able to upload the applications to your environment.</span></span>
