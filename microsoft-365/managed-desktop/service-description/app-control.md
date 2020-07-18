---
title: Controle de aplicativos
description: ''
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: e9d33df0ae11d01c8c214fbe0f001a16e8f4908d
ms.sourcegitcommit: 63887d742c59cc660fc85537b335e98a9dc66fbe
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2020
ms.locfileid: "45170681"
---
# <a name="app-control"></a><span data-ttu-id="5563d-103">Controle de aplicativos</span><span class="sxs-lookup"><span data-stu-id="5563d-103">App control</span></span>

<span data-ttu-id="5563d-104">O controle de aplicativos é uma prática de segurança opcional na área de trabalho gerenciada da Microsoft que restringe a execução de código em dispositivos cliente.</span><span class="sxs-lookup"><span data-stu-id="5563d-104">App control is an optional security practice in Microsoft Managed Desktop that restricts the execution of code on client devices.</span></span> <span data-ttu-id="5563d-105">Esse controle reduz o risco de malware ou scripts mal-intencionados exigindo que apenas o código assinado por uma lista de editores aprovada pelo cliente possa ser executado.</span><span class="sxs-lookup"><span data-stu-id="5563d-105">This control mitigates the risk of malware or malicious scripts by requiring that only code signed by a customer-approved list of publishers can run.</span></span> <span data-ttu-id="5563d-106">Há muitos benefícios de segurança desse controle, mas destina-se principalmente a proteger dados e identidades de explorações baseadas no cliente.</span><span class="sxs-lookup"><span data-stu-id="5563d-106">There are many security benefits from this control, but it primarily aims to protect data and identity from client-based exploits.</span></span>

<span data-ttu-id="5563d-107">O Microsoft Managed desktop simplifica o gerenciamento de políticas de controle de aplicativos criando uma política de base que permite cenários de produtividade principal.</span><span class="sxs-lookup"><span data-stu-id="5563d-107">Microsoft Managed Desktop simplifies the management of app control policies by creating a base policy that enables core productivity scenarios.</span></span> <span data-ttu-id="5563d-108">Você pode estender a confiança para os assinadores adicionais que são específicos para os aplicativos e scripts em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="5563d-108">You can extend trust to additional signers that are specific to the apps and scripts in your environment.</span></span> 


<span data-ttu-id="5563d-109">Qualquer tecnologia de segurança requer um equilíbrio entre a experiência do usuário, a segurança e o custo.</span><span class="sxs-lookup"><span data-stu-id="5563d-109">Any security technology requires a balance among user experience, security, and cost.</span></span> <span data-ttu-id="5563d-110">O controle de aplicativos reduz a ameaça de software mal-intencionado em seu ambiente, mas há conseqüências para o usuário final e ações adicionais para seu administrador de ti.</span><span class="sxs-lookup"><span data-stu-id="5563d-110">App control reduces the threat of malicious software in your environment, but there are consequences to the end user and additional actions for your IT administrator.</span></span>

<span data-ttu-id="5563d-111">**Segurança adicional:**</span><span class="sxs-lookup"><span data-stu-id="5563d-111">**Additional security:**</span></span>

<span data-ttu-id="5563d-112">Os aplicativos ou scripts que não são confiáveis pela política de controle de aplicativos são impedidos de serem executados em dispositivos.</span><span class="sxs-lookup"><span data-stu-id="5563d-112">Apps or scripts that are not trusted by the app control policy are blocked from running on devices.</span></span>

<span data-ttu-id="5563d-113">**Suas responsabilidades adicionais:**</span><span class="sxs-lookup"><span data-stu-id="5563d-113">**Your additional responsibilities:**</span></span>

- <span data-ttu-id="5563d-114">Você é responsável por testar seus aplicativos para identificar se eles serão bloqueados pela política de controle de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="5563d-114">You are responsible for testing your apps to identify whether they would be blocked by the application control policy.</span></span>
- <span data-ttu-id="5563d-115">Se um aplicativo estiver bloqueado, você será responsável por identificar os detalhes necessários do signatário e solicitar uma alteração por meio do portal de administração.</span><span class="sxs-lookup"><span data-stu-id="5563d-115">If an app is (or would be) blocked, you are responsible for identifying the needed signer details and requesting a change through the Admin portal.</span></span>

<span data-ttu-id="5563d-116">**Responsabilidades de área de trabalho gerenciada da Microsoft:**</span><span class="sxs-lookup"><span data-stu-id="5563d-116">**Microsoft Managed Desktop responsibilities:**</span></span>

- <span data-ttu-id="5563d-117">A área de trabalho gerenciada da Microsoft mantém a política básica que permite os principais produtos da Microsoft, como aplicativos do M365, Windows, Teams, OneDrive e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="5563d-117">Microsoft Managed Desktop maintains the base policy that enables core Microsoft products like M365 Apps, Windows, Teams, OneDrive, and so on.</span></span>
- <span data-ttu-id="5563d-118">A área de trabalho gerenciada da Microsoft insere seus assinantes confiáveis e implanta a política atualizada para seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="5563d-118">Microsoft Managed Desktop inserts your trusted signers and deploys the updated policy to your devices.</span></span>


## <a name="managing-trust-in-applications"></a><span data-ttu-id="5563d-119">Gerenciando a confiança em aplicativos</span><span class="sxs-lookup"><span data-stu-id="5563d-119">Managing trust in applications</span></span>

<span data-ttu-id="5563d-120">O Microsoft Managed desktop organizada uma política básica que confia nos principais componentes das tecnologias da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5563d-120">Microsoft Managed Desktop curates a base policy that trusts the core components of Microsoft technologies.</span></span> <span data-ttu-id="5563d-121">Em seguida, você *adiciona* confiança para seus próprios aplicativos e scripts, informando a área de trabalho gerenciada da Microsoft de que você já confia.</span><span class="sxs-lookup"><span data-stu-id="5563d-121">You then *add* trust for your own applications and scripts by informing Microsoft Managed Desktop which of them you already trust.</span></span>

### <a name="base-policy"></a><span data-ttu-id="5563d-122">Política de base</span><span class="sxs-lookup"><span data-stu-id="5563d-122">Base policy</span></span>

<span data-ttu-id="5563d-123">A área de trabalho gerenciada da Microsoft, em colaboração com especialistas do Microsoft cybersecurity, cria e mantém uma política padrão que permite que a maioria dos aplicativos implantados por meio do Microsoft Intune bloqueie atividades perigosas, como compilação de código ou execução de arquivos não confiáveis.</span><span class="sxs-lookup"><span data-stu-id="5563d-123">Microsoft Managed Desktop, in collaboration with Microsoft cybersecurity experts, creates and maintains a standard policy that enables most apps deployed through Microsoft Intune while blocking dangerous activities like code compilation or execution of untrusted files.</span></span>

<span data-ttu-id="5563d-124">A política básica utiliza a seguinte abordagem para restringir a execução do software:</span><span class="sxs-lookup"><span data-stu-id="5563d-124">The base policy takes the following approach to restricting software execution:</span></span>

- <span data-ttu-id="5563d-125">Os arquivos executados por administradores poderão ser executados.</span><span class="sxs-lookup"><span data-stu-id="5563d-125">Files run by administrators will be allowed to run.</span></span>
- <span data-ttu-id="5563d-126">Arquivos em locais que *não* estejam em diretórios graváveis pelo usuário poderão ser executados.</span><span class="sxs-lookup"><span data-stu-id="5563d-126">Files in locations that are *not* in user-writable directories will be allowed to run.</span></span>
- <span data-ttu-id="5563d-127">Os arquivos são assinados por um [signatário confiável](#signer-requests).</span><span class="sxs-lookup"><span data-stu-id="5563d-127">Files are signed by a [trusted signer](#signer-requests).</span></span>
- <span data-ttu-id="5563d-128">A maioria dos arquivos assinados pela Microsoft será executada, mas alguns serão bloqueados para impedir ações de alto risco, como a compilação de código.</span><span class="sxs-lookup"><span data-stu-id="5563d-128">Most files signed by Microsoft will run, however some are blocked to prevent high-risk actions like code compilation.</span></span>


<span data-ttu-id="5563d-129">[! Importante] se um usuário que não seja um administrador tiver adicionado um aplicativo ou script a um dispositivo (ou seja, ele está em um diretório de usuário gravável), não permitiremos que ele seja executado, a menos que ele já tenha sido especificamente permitido por um administrador.</span><span class="sxs-lookup"><span data-stu-id="5563d-129">If a user other than an administrator could have added an app or script to a device (that is, it's in a user-writable directory), we won't allow it to execute unless it has already been specifically allowed by an administrator.</span></span> <span data-ttu-id="5563d-130">Se um usuário for enganado para tentar instalar o malware, se uma vulnerabilidade em um aplicativo que o usuário executa tentar instalar o malware ou se um usuário tentar executar um aplicativo ou script não autorizado, nossa política interromperá a execução.</span><span class="sxs-lookup"><span data-stu-id="5563d-130">If a user is tricked into trying to install malware, if a vulnerability in an app the user runs attempts to install malware, or if a user intentionally tries to run an unauthorized app or script, our policy will stop execution.</span></span>

### <a name="signer-requests"></a><span data-ttu-id="5563d-131">Solicitações de signatário</span><span class="sxs-lookup"><span data-stu-id="5563d-131">Signer requests</span></span>

<span data-ttu-id="5563d-132">Você nos informa quais aplicativos são fornecidos pelos fornecedores de software em que confia por meio da criação de uma *solicitação de signatário*.</span><span class="sxs-lookup"><span data-stu-id="5563d-132">You inform us of which apps are provided by software vendors you trust by filing a *signer request*.</span></span> <span data-ttu-id="5563d-133">Ao fazer isso, adicionamos as informações de confiança à política de controle de aplicativos da linha de base e permitem que qualquer software assinado com o certificado do fornecedor seja executado em seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="5563d-133">By doing so, we add that trust information into the baseline application control policy and allow any software signed with that publisher's certificate to run on your devices.</span></span>

## <a name="audit-and-enforced-policies"></a><span data-ttu-id="5563d-134">Políticas de auditoria e impostos</span><span class="sxs-lookup"><span data-stu-id="5563d-134">Audit and Enforced policies</span></span>

<span data-ttu-id="5563d-135">O Microsoft Managed desktop usa duas políticas do Microsoft Intune para fornecer controle de aplicativos:</span><span class="sxs-lookup"><span data-stu-id="5563d-135">Microsoft Managed Desktop uses two Microsoft Intune policies to provide app control:</span></span>

### <a name="audit-policy"></a><span data-ttu-id="5563d-136">Política de auditoria</span><span class="sxs-lookup"><span data-stu-id="5563d-136">Audit policy</span></span>
<span data-ttu-id="5563d-137">Essa política cria logs para registrar se um aplicativo ou script será bloqueado pela política imposta.</span><span class="sxs-lookup"><span data-stu-id="5563d-137">This policy creates logs to record whether an app or script would be blocked by the Enforced policy.</span></span> <span data-ttu-id="5563d-138">As políticas de auditoria não impõem regras de controle de aplicativos e são direcionadas para fins de teste para identificar se um aplicativo exigirá uma isenção de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="5563d-138">Audit policies don't enforce app control rules and are meant for testing purposes to identify whether an application will require a publisher exemption.</span></span> <span data-ttu-id="5563d-139">Ele registra avisos (8003 ou 8006 eventos) no Visualizador de eventos, em vez de bloquear a execução ou a instalação de aplicativos ou scripts especificados.</span><span class="sxs-lookup"><span data-stu-id="5563d-139">It logs warnings (8003 or 8006 events) in Event Viewer instead of blocking the execution or installation of specified apps or script.</span></span>

### <a name="enforced-policy"></a><span data-ttu-id="5563d-140">Política imposta</span><span class="sxs-lookup"><span data-stu-id="5563d-140">Enforced policy</span></span>
<span data-ttu-id="5563d-141">Essa política bloqueia a execução de aplicativos e scripts não confiáveis e cria logs sempre que um aplicativo ou script é bloqueado.</span><span class="sxs-lookup"><span data-stu-id="5563d-141">This policy blocks untrusted apps and scripts from running and creates logs whenever an app or script is blocked.</span></span> <span data-ttu-id="5563d-142">As políticas impostas impedem que os usuários padrão executem aplicativos ou scripts armazenados em diretórios graváveis pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="5563d-142">Enforced policies prevent standard users from executing apps or scripts stored in user-writable directories.</span></span>

<span data-ttu-id="5563d-143">Os dispositivos no grupo de teste têm uma política de auditoria aplicada para que você possa usá-los para validar se algum aplicativo causará problemas.</span><span class="sxs-lookup"><span data-stu-id="5563d-143">Devices in the Test group have an Audit policy applied so that you can use them to validate whether any applications will cause issues.</span></span> <span data-ttu-id="5563d-144">Todos os outros grupos (primeiro, rápido e amplo) usam uma política imposta, portanto, os usuários finais desses grupos não poderão executar aplicativos ou scripts não confiáveis.</span><span class="sxs-lookup"><span data-stu-id="5563d-144">All other groups (First, Fast, and Broad) use an Enforced policy, so end users in those groups won't be able to run untrusted apps or scripts.</span></span>







