---
title: Trabalhar com Serviços de consultoria da Microsoft
description: preparação e etapas a serem seguidas para trabalhar com MCS para empacotar seus aplicativos
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação, aplicativos, MCS, pacotes
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: d2a6c09e1bcb84885e607d133c14e26e08e3c621
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530158"
---
# <a name="working-with-microsoft-consulting-services"></a><span data-ttu-id="39785-104">Trabalhar com Serviços de consultoria da Microsoft</span><span class="sxs-lookup"><span data-stu-id="39785-104">Working with Microsoft Consulting Services</span></span>

<span data-ttu-id="39785-105">Você pode entrar com o Microsoft Consulting Services (MCS) para obter seus aplicativos empacotados para uso com a área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="39785-105">You can engage with Microsoft Consulting Services (MCS) to get your apps packaged for use with Microsoft Managed Desktop.</span></span> <span data-ttu-id="39785-106">Para obter detalhes exatos, trabalhe com seu representante de conta para entrar em contato com a MCS e o escopo de seu projeto de pacote de aplicativos específico.</span><span class="sxs-lookup"><span data-stu-id="39785-106">For exact details, work with your account representative to contact MCS and scope your specific app packaging project.</span></span>

## <a name="roles-and-responsibilities"></a><span data-ttu-id="39785-107">Funções e responsabilidades</span><span class="sxs-lookup"><span data-stu-id="39785-107">Roles and responsibilities</span></span>

<span data-ttu-id="39785-108">Para trabalhar com o pacote de aplicativos MCS, **você deve fornecer estes elementos**:</span><span class="sxs-lookup"><span data-stu-id="39785-108">To work with MCS app packaging, **you must provide these elements**:</span></span>

- <span data-ttu-id="39785-109">Os arquivos do instalador de origem (por exemplo, setup.exe ou. msi).</span><span class="sxs-lookup"><span data-stu-id="39785-109">The source installer files (e.g., setup.exe or .msi).</span></span>
- <span data-ttu-id="39785-110">As instruções de instalação, especificando detalhes sobre como a instalação final deve ser verificada.</span><span class="sxs-lookup"><span data-stu-id="39785-110">The installation instructions, specifying details about how the final installation should look.</span></span> <span data-ttu-id="39785-111">Por exemplo, deve haver um atalho de área de trabalho para o aplicativo?</span><span class="sxs-lookup"><span data-stu-id="39785-111">For example, should there be a desktop shortcut to the app?</span></span> <span data-ttu-id="39785-112">O que a visibilidade do aplicativo deve ser?</span><span class="sxs-lookup"><span data-stu-id="39785-112">What should the app's visibility be?</span></span> <span data-ttu-id="39785-113">O aplicativo deve se conectar a um servidor e, em caso afirmativo, qual deles?</span><span class="sxs-lookup"><span data-stu-id="39785-113">Should the app connect to a server and if so, which one?</span></span> <span data-ttu-id="39785-114">Para obter detalhes, consulte o [modelo de solicitação de pacotes de aplicativos](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).</span><span class="sxs-lookup"><span data-stu-id="39785-114">For details, see the [application packaging request template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).</span></span>
- <span data-ttu-id="39785-115">Você deve executar seu próprio teste de aceitação para verificar se o aplicativo funciona conforme você precisa para o seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="39785-115">You must perform your own acceptance testing to verify that the app works as you need it to in your environment.</span></span>

<span data-ttu-id="39785-116">**O MCS cuidará destas ações:**</span><span class="sxs-lookup"><span data-stu-id="39785-116">**MCS will take care of these actions:**</span></span>

- <span data-ttu-id="39785-117">Verificar se o aplicativo é proibido ou restrito no ambiente de área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="39785-117">Checking whether the app is prohibited or restricted in the Microsoft Managed Desktop environment.</span></span>
- <span data-ttu-id="39785-118">Teste de instalação, início e desinstalação do aplicativo para garantir a compatibilidade com o Windows 10.</span><span class="sxs-lookup"><span data-stu-id="39785-118">Testing of installation, starting, and uninstallation of the app to ensure compatibility with Windows 10.</span></span> <span data-ttu-id="39785-119">Se o MCS descobrir um problema de compatibilidade, ele enviará o aplicativo para o [aplicativo da área de trabalho garantir](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) o programa para correção.</span><span class="sxs-lookup"><span data-stu-id="39785-119">If MCS discovers a compatibility issue, they will hand off the app to the [Desktop App Assure](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) program for remediation.</span></span>
- <span data-ttu-id="39785-120">Empacotar o aplicativo para sua especificação e, em seguida, testar a implantação do aplicativo usando o Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="39785-120">Packaging the app to your specification and then testing app deployment by using Microsoft Intune.</span></span>

## <a name="app-delivery-schedule"></a><span data-ttu-id="39785-121">Agenda de entrega do aplicativo</span><span class="sxs-lookup"><span data-stu-id="39785-121">App delivery schedule</span></span>

<span data-ttu-id="39785-122">Inicie o processo de empacotamento carregando as informações do aplicativo para o portal de área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="39785-122">Start the packaging process by uploading the app information to the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="39785-123">A equipe de empacotamento revisa novos envios a cada quinta-feira.</span><span class="sxs-lookup"><span data-stu-id="39785-123">The packaging team reviews new submissions every Thursday.</span></span> <span data-ttu-id="39785-124">Após a revisão e o empacotamento, os aplicativos empacotados são entregues na sexta-feira a seguir.</span><span class="sxs-lookup"><span data-stu-id="39785-124">After review and packaging, the packaged apps are delivered the following Friday.</span></span> <span data-ttu-id="39785-125">Até cinco aplicativos por semana podem ser empacotados para iniciar, mas o serviço pode ser dimensionado para atender às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="39785-125">Up to five apps per week can be packaged to start but the service can scale to meet your needs.</span></span>

![calendário mostrando o fluxo de aplicativos em uma quinta-feira (o 21, neste exemplo), a validação de mídia no dia seguinte, empacotando na segunda-feira (o 25º) e entrega de aplicativos na sexta-feira subsequente (o dia 29)](../../media/MCS-cal.png)

<span data-ttu-id="39785-127">Você será notificado assim que o aplicativo for entregue.</span><span class="sxs-lookup"><span data-stu-id="39785-127">You'll be notified once the app has been delivered.</span></span> <span data-ttu-id="39785-128">Nesse ponto, você tem 21 dias para executar o teste de aceitação e aprovar o trabalho no portal de área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="39785-128">At that point, you have 21 days to perform acceptance testing and sign off on the work in the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="39785-129">Se descobrir algum problema com o aplicativo durante o teste de aceitação, rejeite o aplicativo no portal de área de trabalho gerenciada da Microsoft e você será conectado por email com um empacotador MCS para entender e resolver o problema.</span><span class="sxs-lookup"><span data-stu-id="39785-129">If discover some problem with the app during your acceptance testing, reject the app in the Microsoft Managed Desktop portal and you will be connected via email with an MCS packager to understand and resolve the issue.</span></span>

## <a name="testing-accounts-and-environment"></a><span data-ttu-id="39785-130">Testando contas e ambientes</span><span class="sxs-lookup"><span data-stu-id="39785-130">Testing accounts and environment</span></span>

<span data-ttu-id="39785-131">Para a equipe de embalagens concluir a migração para o Microsoft Intune, recomendamos que você forneça determinadas permissões:</span><span class="sxs-lookup"><span data-stu-id="39785-131">For the packaging team to complete the migration to Microsoft Intune we recommend that you provide certain permissions:</span></span>
 
-   <span data-ttu-id="39785-132">Acesso aos recursos de implantação de aplicativos do Microsoft Intune para o packager adicionar e atribuir o aplicativo</span><span class="sxs-lookup"><span data-stu-id="39785-132">Access to Microsoft Intune’s App Deployment capabilities for the packager to add and assign the app</span></span> 
-   <span data-ttu-id="39785-133">Grupos de teste, contas de usuário e licenças para que os compactadores possam testar os aplicativos</span><span class="sxs-lookup"><span data-stu-id="39785-133">Test groups, user accounts, and licenses for the packagers to be able to test the apps</span></span>

<span data-ttu-id="39785-134">O MCS usará essas permissões para executar as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="39785-134">MCS will use those permissions to perform the following actions:</span></span>
 
-   <span data-ttu-id="39785-135">Garantir que o aplicativo funcione na máquina virtual configurada para a área de trabalho gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="39785-135">Ensuring that the app works on virtual machine configured for Microsoft Managed Desktop</span></span>
-   <span data-ttu-id="39785-136">Carregar o aplicativo no Microsoft Intune para implantação em seus usuários</span><span class="sxs-lookup"><span data-stu-id="39785-136">Uploading the app to Microsoft Intune for deployment to your users</span></span>

<span data-ttu-id="39785-137">Sem essas permissões, é possível para o MCS avançar, mas eles não poderão carregar os aplicativos para o seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="39785-137">Without these permissions, it is possible for MCS to move forward, but they will not be able to upload the applications to your environment.</span></span>


