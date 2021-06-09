---
title: Controle de aplicativo
description: Como usar o controle do aplicativo e a confiança com aplicativos
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 6f5cc923b5a18b1f45dd186e88228db8c3a891cc
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841298"
---
# <a name="app-control"></a><span data-ttu-id="8b53d-104">Controle de aplicativo</span><span class="sxs-lookup"><span data-stu-id="8b53d-104">App control</span></span>

<span data-ttu-id="8b53d-105">O controle de aplicativo é uma prática de segurança opcional Área de Trabalho Gerenciada da Microsoft que restringe a execução de código em dispositivos cliente.</span><span class="sxs-lookup"><span data-stu-id="8b53d-105">App control is an optional security practice in Microsoft Managed Desktop that restricts the execution of code on client devices.</span></span> <span data-ttu-id="8b53d-106">Esse controle reduz o risco de malware ou scripts mal-intencionados exigindo que somente o código assinado por uma lista de editores aprovado pelo cliente possa ser executado.</span><span class="sxs-lookup"><span data-stu-id="8b53d-106">This control mitigates the risk of malware or malicious scripts by requiring that only code signed by a customer-approved list of publishers can run.</span></span> <span data-ttu-id="8b53d-107">Há muitos benefícios de segurança desse controle, mas ele visa principalmente proteger dados e identidade contra explorações baseadas em cliente.</span><span class="sxs-lookup"><span data-stu-id="8b53d-107">There are many security benefits from this control, but it primarily aims to protect data and identity from client-based exploits.</span></span>

<span data-ttu-id="8b53d-108">Área de Trabalho Gerenciada da Microsoft simplifica o gerenciamento de políticas de controle de aplicativo criando uma política base que habilita os principais cenários de produtividade.</span><span class="sxs-lookup"><span data-stu-id="8b53d-108">Microsoft Managed Desktop simplifies the management of app control policies by creating a base policy that enables core productivity scenarios.</span></span> <span data-ttu-id="8b53d-109">Você pode estender a confiança a outros signatários específicos aos aplicativos e scripts em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="8b53d-109">You can extend trust to other signers that are specific to the apps and scripts in your environment.</span></span> 


<span data-ttu-id="8b53d-110">Qualquer tecnologia de segurança exige um equilíbrio entre a experiência, a segurança e o custo do usuário.</span><span class="sxs-lookup"><span data-stu-id="8b53d-110">Any security technology requires a balance among user experience, security, and cost.</span></span> <span data-ttu-id="8b53d-111">O controle de aplicativo reduz a ameaça de software mal-intencionado em seu ambiente, mas há consequências para o usuário e outras ações para o administrador de IT.</span><span class="sxs-lookup"><span data-stu-id="8b53d-111">App control reduces the threat of malicious software in your environment, but there are consequences to the user and further actions for your IT administrator.</span></span>

<span data-ttu-id="8b53d-112">**Segurança adicional:**</span><span class="sxs-lookup"><span data-stu-id="8b53d-112">**Additional security:**</span></span>

<span data-ttu-id="8b53d-113">Aplicativos ou scripts que não são confiáveis pela política de controle do aplicativo são impedidos de ser executados em dispositivos.</span><span class="sxs-lookup"><span data-stu-id="8b53d-113">Apps or scripts that are not trusted by the app control policy are blocked from running on devices.</span></span>

<span data-ttu-id="8b53d-114">**Suas responsabilidades adicionais:**</span><span class="sxs-lookup"><span data-stu-id="8b53d-114">**Your additional responsibilities:**</span></span>

- <span data-ttu-id="8b53d-115">Você é responsável por testar seus aplicativos para identificar se eles seriam bloqueados pela política de controle do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="8b53d-115">You are responsible for testing your apps to identify whether they would be blocked by the application control policy.</span></span>
- <span data-ttu-id="8b53d-116">Se um aplicativo for (ou seria) bloqueado, você será responsável por identificar os detalhes necessários do signante e solicitar uma alteração por meio do portal administrador.</span><span class="sxs-lookup"><span data-stu-id="8b53d-116">If an app is (or would be) blocked, you are responsible for identifying the needed signer details and requesting a change through the Admin portal.</span></span>

<span data-ttu-id="8b53d-117">**Área de Trabalho Gerenciada da Microsoft responsabilidades:**</span><span class="sxs-lookup"><span data-stu-id="8b53d-117">**Microsoft Managed Desktop responsibilities:**</span></span>

- <span data-ttu-id="8b53d-118">Área de Trabalho Gerenciada da Microsoft mantém a política base que permite produtos principais da Microsoft, como aplicativos do M365, Windows, Teams, OneDrive e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="8b53d-118">Microsoft Managed Desktop maintains the base policy that enables core Microsoft products like M365 Apps, Windows, Teams, OneDrive, and so on.</span></span>
- <span data-ttu-id="8b53d-119">Área de Trabalho Gerenciada da Microsoft insere seus signatários confiáveis e implanta a política atualizada em seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="8b53d-119">Microsoft Managed Desktop inserts your trusted signers and deploys the updated policy to your devices.</span></span>


## <a name="managing-trust-in-applications"></a><span data-ttu-id="8b53d-120">Gerenciando a confiança em aplicativos</span><span class="sxs-lookup"><span data-stu-id="8b53d-120">Managing trust in applications</span></span>

<span data-ttu-id="8b53d-121">Área de Trabalho Gerenciada da Microsoft cura uma política base que confia nos principais componentes das tecnologias Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8b53d-121">Microsoft Managed Desktop curates a base policy that trusts the core components of Microsoft technologies.</span></span> <span data-ttu-id="8b53d-122">Em *seguida, adicione* confiança para seus próprios aplicativos e scripts informando Área de Trabalho Gerenciada da Microsoft quais deles você já confia.</span><span class="sxs-lookup"><span data-stu-id="8b53d-122">You then *add* trust for your own applications and scripts by informing Microsoft Managed Desktop which of them you already trust.</span></span>

### <a name="base-policy"></a><span data-ttu-id="8b53d-123">Política base</span><span class="sxs-lookup"><span data-stu-id="8b53d-123">Base policy</span></span>

<span data-ttu-id="8b53d-124">Área de Trabalho Gerenciada da Microsoft, em colaboração com especialistas em segurança cibernética da Microsoft, cria e mantém uma política padrão que habilita a maioria dos aplicativos implantados por meio do Microsoft Intune enquanto bloqueia atividades perigosas, como compilação de código ou execução de arquivos não-confidenciais.</span><span class="sxs-lookup"><span data-stu-id="8b53d-124">Microsoft Managed Desktop, in collaboration with Microsoft cybersecurity experts, creates, and maintains a standard policy that enables most apps deployed through Microsoft Intune while blocking dangerous activities like code compilation or execution of untrusted files.</span></span>

<span data-ttu-id="8b53d-125">A política base tem a seguinte abordagem para restringir a execução de software:</span><span class="sxs-lookup"><span data-stu-id="8b53d-125">The base policy takes the following approach to restricting software execution:</span></span>

- <span data-ttu-id="8b53d-126">Os arquivos executados pelos administradores terão permissão para serem executados.</span><span class="sxs-lookup"><span data-stu-id="8b53d-126">Files run by administrators will be allowed to run.</span></span>
- <span data-ttu-id="8b53d-127">Os arquivos em locais que *não estão* em diretórios que podem ser escritos pelo usuário terão permissão para serem executados.</span><span class="sxs-lookup"><span data-stu-id="8b53d-127">Files in locations that are *not* in user-writable directories will be allowed to run.</span></span>
- <span data-ttu-id="8b53d-128">Os arquivos são assinados por [um signante confiável](#signer-requests).</span><span class="sxs-lookup"><span data-stu-id="8b53d-128">Files are signed by a [trusted signer](#signer-requests).</span></span>
- <span data-ttu-id="8b53d-129">A maioria dos arquivos assinados pela Microsoft será executado, no entanto, alguns são bloqueados para evitar ações de alto risco, como a compilação de código.</span><span class="sxs-lookup"><span data-stu-id="8b53d-129">Most files signed by Microsoft will run, however some are blocked to prevent high-risk actions like code compilation.</span></span>


<span data-ttu-id="8b53d-130">Se um usuário diferente de um administrador poderia ter adicionado um aplicativo ou script a um dispositivo (ou seja, ele está em um diretório que pode ser escrito pelo usuário), não permitiremos que ele seja executado, a menos que ele já tenha sido especificamente permitido por um administrador.</span><span class="sxs-lookup"><span data-stu-id="8b53d-130">If a user other than an administrator could have added an app or script to a device (that is, it's in a user-writable directory), we won't allow it to execute unless it has already been specifically allowed by an administrator.</span></span> <span data-ttu-id="8b53d-131">Se um usuário for tentado instalar malware, se uma vulnerabilidade em um aplicativo que o usuário executa tentar instalar malware ou se um usuário tentar executar intencionalmente um aplicativo ou script não autorizado, nossa política interromperá a execução.</span><span class="sxs-lookup"><span data-stu-id="8b53d-131">If a user is tricked into trying to install malware, if a vulnerability in an app the user runs attempts to install malware, or if a user intentionally tries to run an unauthorized app or script, our policy will stop execution.</span></span>

### <a name="signer-requests"></a><span data-ttu-id="8b53d-132">Solicitações de signator</span><span class="sxs-lookup"><span data-stu-id="8b53d-132">Signer requests</span></span>

<span data-ttu-id="8b53d-133">Você nos informa quais aplicativos são fornecidos por editores de software em que você confia, arquivando uma *solicitação de signatário.*</span><span class="sxs-lookup"><span data-stu-id="8b53d-133">You inform us of which apps are provided by software publishers you trust by filing a *signer request*.</span></span> <span data-ttu-id="8b53d-134">Ao fazer isso, adicionamos essas informações de confiança à política de controle do aplicativo de linha de base e permitimos que qualquer software assinado com o certificado desse editor seja executado em seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="8b53d-134">By doing so, we add that trust information into the baseline application control policy and allow any software signed with that publisher's certificate to run on your devices.</span></span>

## <a name="audit-and-enforced-policies"></a><span data-ttu-id="8b53d-135">Políticas auditadas e impostas</span><span class="sxs-lookup"><span data-stu-id="8b53d-135">Audit and Enforced policies</span></span>

<span data-ttu-id="8b53d-136">Área de Trabalho Gerenciada da Microsoft usa duas políticas Microsoft Intune para fornecer controle de aplicativo:</span><span class="sxs-lookup"><span data-stu-id="8b53d-136">Microsoft Managed Desktop uses two Microsoft Intune policies to provide app control:</span></span>

### <a name="audit-policy"></a><span data-ttu-id="8b53d-137">Política de auditoria</span><span class="sxs-lookup"><span data-stu-id="8b53d-137">Audit policy</span></span>
<span data-ttu-id="8b53d-138">Essa política cria logs para registrar se um aplicativo ou script seria bloqueado pela política imposta.</span><span class="sxs-lookup"><span data-stu-id="8b53d-138">This policy creates logs to record whether an app or script would be blocked by the Enforced policy.</span></span> <span data-ttu-id="8b53d-139">As políticas de auditoria não impõem regras de controle de aplicativos e são destinadas a fins de teste para identificar se um aplicativo exigirá uma isenção do publisher.</span><span class="sxs-lookup"><span data-stu-id="8b53d-139">Audit policies don't enforce app control rules and are meant for testing purposes to identify whether an application will require a publisher exemption.</span></span> <span data-ttu-id="8b53d-140">Ele registra avisos (eventos 8003 ou 8006) no Visualizador de Eventos em vez de bloquear a execução ou a instalação de aplicativos ou scripts especificados.</span><span class="sxs-lookup"><span data-stu-id="8b53d-140">It logs warnings (8003 or 8006 events) in Event Viewer instead of blocking the execution or installation of specified apps or script.</span></span>

### <a name="enforced-policy"></a><span data-ttu-id="8b53d-141">Política imposta</span><span class="sxs-lookup"><span data-stu-id="8b53d-141">Enforced policy</span></span>
<span data-ttu-id="8b53d-142">Essa política bloqueia a execução de aplicativos e scripts não-confianças e cria logs sempre que um aplicativo ou script é bloqueado.</span><span class="sxs-lookup"><span data-stu-id="8b53d-142">This policy blocks untrusted apps and scripts from running and creates logs whenever an app or script is blocked.</span></span> <span data-ttu-id="8b53d-143">As políticas impostas impedem que os usuários padrão executem aplicativos ou scripts armazenados em diretórios que podem ser gravados pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="8b53d-143">Enforced policies prevent standard users from executing apps or scripts stored in user-writable directories.</span></span>

<span data-ttu-id="8b53d-144">Os dispositivos no grupo Teste têm uma política de Auditoria aplicada para que você possa usá-los para validar se algum aplicativo causará problemas.</span><span class="sxs-lookup"><span data-stu-id="8b53d-144">Devices in the Test group have an Audit policy applied so that you can use them to validate whether any applications will cause issues.</span></span> <span data-ttu-id="8b53d-145">Todos os outros grupos (First, Fast e Broad) usam uma política imposta, para que os usuários nesses grupos não sejam capazes de executar aplicativos ou scripts não-não-confianças.</span><span class="sxs-lookup"><span data-stu-id="8b53d-145">All other groups (First, Fast, and Broad) use an Enforced policy, so users in those groups won't be able to run untrusted apps or scripts.</span></span>







