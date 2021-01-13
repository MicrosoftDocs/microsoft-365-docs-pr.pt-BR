---
title: Controle de aplicativo
description: Como usar o controle de aplicativo e a confiança com aplicativos
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
# <a name="app-control"></a><span data-ttu-id="a1dcd-104">Controle de aplicativo</span><span class="sxs-lookup"><span data-stu-id="a1dcd-104">App control</span></span>

<span data-ttu-id="a1dcd-105">O controle de aplicativo é uma prática de segurança opcional na Área de Trabalho Gerenciada da Microsoft que restringe a execução de código em dispositivos cliente.</span><span class="sxs-lookup"><span data-stu-id="a1dcd-105">App control is an optional security practice in Microsoft Managed Desktop that restricts the execution of code on client devices.</span></span> <span data-ttu-id="a1dcd-106">Esse controle reduz o risco de malware ou scripts mal-intencionados exigindo que somente o código assinado por uma lista de editores aprovada pelo cliente possa ser executado.</span><span class="sxs-lookup"><span data-stu-id="a1dcd-106">This control mitigates the risk of malware or malicious scripts by requiring that only code signed by a customer-approved list of publishers can run.</span></span> <span data-ttu-id="a1dcd-107">Há muitos benefícios de segurança desse controle, mas ele visa principalmente proteger os dados e a identidade contra explorações baseadas no cliente.</span><span class="sxs-lookup"><span data-stu-id="a1dcd-107">There are many security benefits from this control, but it primarily aims to protect data and identity from client-based exploits.</span></span>

<span data-ttu-id="a1dcd-108">A Área de Trabalho Gerenciada da Microsoft simplifica o gerenciamento de políticas de controle de aplicativo criando uma política base que habilita os principais cenários de produtividade.</span><span class="sxs-lookup"><span data-stu-id="a1dcd-108">Microsoft Managed Desktop simplifies the management of app control policies by creating a base policy that enables core productivity scenarios.</span></span> <span data-ttu-id="a1dcd-109">Você pode estender a confiança para outros signatários específicos para os aplicativos e scripts em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="a1dcd-109">You can extend trust to other signers that are specific to the apps and scripts in your environment.</span></span> 


<span data-ttu-id="a1dcd-110">Qualquer tecnologia de segurança exige um equilíbrio entre a experiência do usuário, a segurança e o custo.</span><span class="sxs-lookup"><span data-stu-id="a1dcd-110">Any security technology requires a balance among user experience, security, and cost.</span></span> <span data-ttu-id="a1dcd-111">O controle de aplicativo reduz a ameaça de software mal-intencionado em seu ambiente, mas há consequências para o usuário e outras ações para seu administrador de IT.</span><span class="sxs-lookup"><span data-stu-id="a1dcd-111">App control reduces the threat of malicious software in your environment, but there are consequences to the user and further actions for your IT administrator.</span></span>

<span data-ttu-id="a1dcd-112">**Segurança adicional:**</span><span class="sxs-lookup"><span data-stu-id="a1dcd-112">**Additional security:**</span></span>

<span data-ttu-id="a1dcd-113">Aplicativos ou scripts que não são confiáveis pela política de controle de aplicativo são impedidos de ser executados em dispositivos.</span><span class="sxs-lookup"><span data-stu-id="a1dcd-113">Apps or scripts that are not trusted by the app control policy are blocked from running on devices.</span></span>

<span data-ttu-id="a1dcd-114">**Suas responsabilidades adicionais:**</span><span class="sxs-lookup"><span data-stu-id="a1dcd-114">**Your additional responsibilities:**</span></span>

- <span data-ttu-id="a1dcd-115">Você é responsável por testar seus aplicativos para identificar se eles seriam bloqueados pela política de controle de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="a1dcd-115">You are responsible for testing your apps to identify whether they would be blocked by the application control policy.</span></span>
- <span data-ttu-id="a1dcd-116">Se um aplicativo for (ou seria bloqueado), você é responsável por identificar os detalhes de signante necessários e solicitar uma alteração por meio do portal de administração.</span><span class="sxs-lookup"><span data-stu-id="a1dcd-116">If an app is (or would be) blocked, you are responsible for identifying the needed signer details and requesting a change through the Admin portal.</span></span>

<span data-ttu-id="a1dcd-117">**Responsabilidades da Área de Trabalho Gerenciada da Microsoft:**</span><span class="sxs-lookup"><span data-stu-id="a1dcd-117">**Microsoft Managed Desktop responsibilities:**</span></span>

- <span data-ttu-id="a1dcd-118">A Área de Trabalho Gerenciada da Microsoft mantém a política base que habilita os principais produtos da Microsoft, como aplicativos do M365, Windows, Teams, OneDrive e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="a1dcd-118">Microsoft Managed Desktop maintains the base policy that enables core Microsoft products like M365 Apps, Windows, Teams, OneDrive, and so on.</span></span>
- <span data-ttu-id="a1dcd-119">A Área de Trabalho Gerenciada da Microsoft insere seus signatários confiáveis e implanta a política atualizada em seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="a1dcd-119">Microsoft Managed Desktop inserts your trusted signers and deploys the updated policy to your devices.</span></span>


## <a name="managing-trust-in-applications"></a><span data-ttu-id="a1dcd-120">Gerenciando a confiança em aplicativos</span><span class="sxs-lookup"><span data-stu-id="a1dcd-120">Managing trust in applications</span></span>

<span data-ttu-id="a1dcd-121">A Área de Trabalho Gerenciada da Microsoft reúne uma política base que confia nos principais componentes das tecnologias da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a1dcd-121">Microsoft Managed Desktop curates a base policy that trusts the core components of Microsoft technologies.</span></span> <span data-ttu-id="a1dcd-122">Em *seguida, adicione* confiança para seus próprios aplicativos e scripts informando a Área de Trabalho Gerenciada da Microsoft em quais deles você já confia.</span><span class="sxs-lookup"><span data-stu-id="a1dcd-122">You then *add* trust for your own applications and scripts by informing Microsoft Managed Desktop which of them you already trust.</span></span>

### <a name="base-policy"></a><span data-ttu-id="a1dcd-123">Política base</span><span class="sxs-lookup"><span data-stu-id="a1dcd-123">Base policy</span></span>

<span data-ttu-id="a1dcd-124">A Área de Trabalho Gerenciada da Microsoft, em colaboração com especialistas em segurança cibernética da Microsoft, cria e mantém uma política padrão que habilita a maioria dos aplicativos implantados por meio do Microsoft Intune, bloqueando atividades perigosas, como compilação de código ou execução de arquivos não-confidenciais.</span><span class="sxs-lookup"><span data-stu-id="a1dcd-124">Microsoft Managed Desktop, in collaboration with Microsoft cybersecurity experts, creates, and maintains a standard policy that enables most apps deployed through Microsoft Intune while blocking dangerous activities like code compilation or execution of untrusted files.</span></span>

<span data-ttu-id="a1dcd-125">A política base tem a seguinte abordagem para restringir a execução de software:</span><span class="sxs-lookup"><span data-stu-id="a1dcd-125">The base policy takes the following approach to restricting software execution:</span></span>

- <span data-ttu-id="a1dcd-126">Os arquivos executados pelos administradores poderão ser executados.</span><span class="sxs-lookup"><span data-stu-id="a1dcd-126">Files run by administrators will be allowed to run.</span></span>
- <span data-ttu-id="a1dcd-127">Arquivos em locais que *não estão em* diretórios que podem ser executados pelo usuário poderão ser executados.</span><span class="sxs-lookup"><span data-stu-id="a1dcd-127">Files in locations that are *not* in user-writable directories will be allowed to run.</span></span>
- <span data-ttu-id="a1dcd-128">Os arquivos são assinados por [um signante confiável.](#signer-requests)</span><span class="sxs-lookup"><span data-stu-id="a1dcd-128">Files are signed by a [trusted signer](#signer-requests).</span></span>
- <span data-ttu-id="a1dcd-129">A maioria dos arquivos assinados pela Microsoft será executado, no entanto, alguns são bloqueados para impedir ações de alto risco, como compilação de código.</span><span class="sxs-lookup"><span data-stu-id="a1dcd-129">Most files signed by Microsoft will run, however some are blocked to prevent high-risk actions like code compilation.</span></span>


<span data-ttu-id="a1dcd-130">Se um usuário diferente de um administrador puder ter adicionado um aplicativo ou script a um dispositivo (ou seja, ele está em um diretório que pode ser escrito pelo usuário), não permitiremos que ele seja executado, a menos que ele já tenha sido especificamente permitido por um administrador.</span><span class="sxs-lookup"><span data-stu-id="a1dcd-130">If a user other than an administrator could have added an app or script to a device (that is, it's in a user-writable directory), we won't allow it to execute unless it has already been specifically allowed by an administrator.</span></span> <span data-ttu-id="a1dcd-131">Se um usuário for tentado instalar malware, se uma vulnerabilidade em um aplicativo que o usuário executa tentar instalar malware ou se um usuário tentar executar intencionalmente um aplicativo ou script não autorizado, nossa política interromperá a execução.</span><span class="sxs-lookup"><span data-stu-id="a1dcd-131">If a user is tricked into trying to install malware, if a vulnerability in an app the user runs attempts to install malware, or if a user intentionally tries to run an unauthorized app or script, our policy will stop execution.</span></span>

### <a name="signer-requests"></a><span data-ttu-id="a1dcd-132">Solicitações do signante</span><span class="sxs-lookup"><span data-stu-id="a1dcd-132">Signer requests</span></span>

<span data-ttu-id="a1dcd-133">Você nos informa quais aplicativos são fornecidos por editores de software em que você confia, apresentando uma *solicitação de signatário.*</span><span class="sxs-lookup"><span data-stu-id="a1dcd-133">You inform us of which apps are provided by software publishers you trust by filing a *signer request*.</span></span> <span data-ttu-id="a1dcd-134">Ao fazer isso, adicionamos essas informações de confiança à política de controle do aplicativo de linha de base e permitimos que qualquer software assinado com o certificado desse editor seja executado em seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="a1dcd-134">By doing so, we add that trust information into the baseline application control policy and allow any software signed with that publisher's certificate to run on your devices.</span></span>

## <a name="audit-and-enforced-policies"></a><span data-ttu-id="a1dcd-135">Políticas auditadas e impostas</span><span class="sxs-lookup"><span data-stu-id="a1dcd-135">Audit and Enforced policies</span></span>

<span data-ttu-id="a1dcd-136">A Área de Trabalho Gerenciada da Microsoft usa duas políticas do Microsoft Intune para fornecer controle de aplicativo:</span><span class="sxs-lookup"><span data-stu-id="a1dcd-136">Microsoft Managed Desktop uses two Microsoft Intune policies to provide app control:</span></span>

### <a name="audit-policy"></a><span data-ttu-id="a1dcd-137">Política de auditoria</span><span class="sxs-lookup"><span data-stu-id="a1dcd-137">Audit policy</span></span>
<span data-ttu-id="a1dcd-138">Essa política cria logs para registrar se um aplicativo ou script seria bloqueado pela política imposta.</span><span class="sxs-lookup"><span data-stu-id="a1dcd-138">This policy creates logs to record whether an app or script would be blocked by the Enforced policy.</span></span> <span data-ttu-id="a1dcd-139">As políticas de auditoria não impõem regras de controle de aplicativo e são destinadas a fins de teste para identificar se um aplicativo exigirá uma isenção do editor.</span><span class="sxs-lookup"><span data-stu-id="a1dcd-139">Audit policies don't enforce app control rules and are meant for testing purposes to identify whether an application will require a publisher exemption.</span></span> <span data-ttu-id="a1dcd-140">Ele registra avisos (eventos 8003 ou 8006) no Visualizador de Eventos em vez de bloquear a execução ou a instalação de aplicativos ou scripts especificados.</span><span class="sxs-lookup"><span data-stu-id="a1dcd-140">It logs warnings (8003 or 8006 events) in Event Viewer instead of blocking the execution or installation of specified apps or script.</span></span>

### <a name="enforced-policy"></a><span data-ttu-id="a1dcd-141">Política imposta</span><span class="sxs-lookup"><span data-stu-id="a1dcd-141">Enforced policy</span></span>
<span data-ttu-id="a1dcd-142">Essa política impede a execução de scripts e aplicativos não-confiançados e cria logs sempre que um aplicativo ou script é bloqueado.</span><span class="sxs-lookup"><span data-stu-id="a1dcd-142">This policy blocks untrusted apps and scripts from running and creates logs whenever an app or script is blocked.</span></span> <span data-ttu-id="a1dcd-143">As políticas impostas impedem que os usuários padrão executem aplicativos ou scripts armazenados em diretórios que podem ser gravados pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="a1dcd-143">Enforced policies prevent standard users from executing apps or scripts stored in user-writable directories.</span></span>

<span data-ttu-id="a1dcd-144">Os dispositivos no grupo Teste têm uma política de auditoria aplicada para que você possa usá-los para validar se algum aplicativo causará problemas.</span><span class="sxs-lookup"><span data-stu-id="a1dcd-144">Devices in the Test group have an Audit policy applied so that you can use them to validate whether any applications will cause issues.</span></span> <span data-ttu-id="a1dcd-145">Todos os outros grupos (Primeiro, Rápido e Amplo) usam uma política Imposta, para que os usuários nesses grupos não sejam capazes de executar scripts ou aplicativos não-não-confianças.</span><span class="sxs-lookup"><span data-stu-id="a1dcd-145">All other groups (First, Fast, and Broad) use an Enforced policy, so users in those groups won't be able to run untrusted apps or scripts.</span></span>







