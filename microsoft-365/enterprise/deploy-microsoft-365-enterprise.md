---
title: Implantar o Microsoft 365 Enterprise
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 11/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Entenda os recursos que você pode usar para implantar o Microsoft 365 Enterprise na sua organização.
ms.openlocfilehash: ba0dd4d8af9f647b5368fdaa55837d3fe482fb55
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865217"
---
# <a name="deploy-microsoft-365-enterprise"></a><span data-ttu-id="f4a60-103">Implantar o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f4a60-103">Deploy Microsoft 365 Enterprise</span></span>

<span data-ttu-id="f4a60-104">O Microsoft 365 Enterprise é uma combinação do Office 365, Enterprise Mobility + Security (EMS) e Windows 10 Enterprise que:</span><span class="sxs-lookup"><span data-stu-id="f4a60-104">Microsoft 365 Enterprise is a combination of Office 365, Enterprise Mobility + Security (EMS), and Windows 10 Enterprise that:</span></span> 

- <span data-ttu-id="f4a60-105">tem segurança inteligente;</span><span class="sxs-lookup"><span data-stu-id="f4a60-105">Has intelligent security.</span></span>
- <span data-ttu-id="f4a60-106">está integrado para oferecer simplicidade;</span><span class="sxs-lookup"><span data-stu-id="f4a60-106">Is integrated for simplicity.</span></span>
- <span data-ttu-id="f4a60-107">desbloqueia a criatividade;</span><span class="sxs-lookup"><span data-stu-id="f4a60-107">Unlocks creativity.</span></span>
- <span data-ttu-id="f4a60-108">foi criado para trabalho em equipe.</span><span class="sxs-lookup"><span data-stu-id="f4a60-108">Is built for teamwork.</span></span>

<span data-ttu-id="f4a60-p101">Você não consegue esses benefícios apenas obtendo as licenças para esses três produtos, mas sim implantando-os, juntamente com seus recursos, de uma maneira específica. Esta documentação apresenta a orientação passo-a-passo para a implantação e a configuração corretas e obrigatórias para esses produtos e seus recursos.</span><span class="sxs-lookup"><span data-stu-id="f4a60-p101">These benefits are not realized just by obtaining the licenses for these three products, but by deploying them and their features in a specific way. This documentation set guides you through that deployment and the correct and required configuration of these products and their features.</span></span>

<span data-ttu-id="f4a60-111">Há duas fases principais para a implantação do Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="f4a60-111">There are two main phases to deploying Microsoft 365 Enterprise:</span></span>

1. <span data-ttu-id="f4a60-112">Primeiro, implante a [infraestrutura de base](deploy-foundation-infrastructure.md) exigida para a segurança interna e a integração para o gerenciamento simplificado. Isso torna mais fácil garantir que o software-cliente esteja atualizado de acordo com as mais recentes melhorias de segurança e produtividade.</span><span class="sxs-lookup"><span data-stu-id="f4a60-112">First, deploy the required [foundation infrastructure](deploy-foundation-infrastructure.md) for built-in security and integration for simplified management, which makes it easier to ensure your client software is updated with the latest productivity and security enhancements.</span></span>
2. <span data-ttu-id="f4a60-113">Em seguida, implante o conjunto opcional de [cargas de trabalho e cenários](deploy-workloads.md) acima da infraestrutura de base para desbloquear a criatividade e o trabalho de equipe em sua organização.</span><span class="sxs-lookup"><span data-stu-id="f4a60-113">Next, deploy a set of optional [workloads and scenarios](deploy-workloads.md) on top of the foundation infrastructure, to unlock creativity and teamwork in your organization.</span></span>

<span data-ttu-id="f4a60-114">A figura a seguir mostra a relação entre a infraestrutura de base, as cargas de trabalho e os cenários, assim como o seu percurso pelo conteúdo.</span><span class="sxs-lookup"><span data-stu-id="f4a60-114">The following figure shows the relationship between the foundation infrastructure and the workloads and scenarios and your path through the content.</span></span>

![](./media/deploy-microsoft-365-enterprise/m365-deploy-content-arch.png)

<span data-ttu-id="f4a60-115">A segurança é concebida em todas as fases da infraestrutura de base.</span><span class="sxs-lookup"><span data-stu-id="f4a60-115">Security is built into all phases of the foundation infrastructure.</span></span>

## <a name="fasttrack"></a><span data-ttu-id="f4a60-116">FastTrack</span><span class="sxs-lookup"><span data-stu-id="f4a60-116">FastTrack</span></span>

<span data-ttu-id="f4a60-p102">O FastTrack é um benefício contínuo e reutilizável que está disponível como parte da sua assinatura. Esse serviço é oferecido pelos engenheiros da Microsoft para ajudá-lo a migrar para a nuvem de acordo com seu próprio ritmo. O FastTrack também proporciona acesso a parceiros qualificados para realizar serviços adicionais, conforme necessário. Com mais de 40.000 clientes habilitados até o momento, o FastTrack ajuda a maximizar o ROI, agiliza a implantação e aumenta a adoção em toda a organização. Consulte a página sobre o [FastTrack para o Microsoft 365](https://fasttrack.microsoft.com/microsoft365).</span><span class="sxs-lookup"><span data-stu-id="f4a60-p102">FastTrack is an ongoing and repeatable benefit—available as part of your subscription—that is delivered by Microsoft engineers to help you move to the cloud at your own pace. FastTrack also gives you access to qualified partners for additional services, as needed. With over 40,000 customers enabled to date, FastTrack helps maximize ROI, accelerate deployment, and increase adoption across your organization. See [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365).</span></span>

<span data-ttu-id="f4a60-p103">Se desejar aproveitar as vantagens do FastTrack para implantar o Microsoft 365 Enterprise, você pode usar o [consultor de implantação do Microsoft 365 do FastTrack](https://aka.ms/microsoft365setupguide) para obter instruções sobre como implantar e configurar a infraestrutura de base. Você deve estar conectado como um administrador global em um locatário do Office 365 ou do Microsoft 365 para acessar essa página.</span><span class="sxs-lookup"><span data-stu-id="f4a60-p103">If you want to take advantage of FastTrack to deploy Microsoft 365 Enterprise, you can use the FastTrack [Microsoft 365 deployment advisor](https://aka.ms/microsoft365setupguide) for guidance on how to deploy and set up your foundation infrastructure. You must be signed on as a global administrator in an Office 365 or Microsoft 365 tenant in order to access this page.</span></span>

## <a name="take-a-test-drive"></a><span data-ttu-id="f4a60-123">Faça um test drive</span><span class="sxs-lookup"><span data-stu-id="f4a60-123">Take a test drive</span></span>

<span data-ttu-id="f4a60-p104">Use o Microsoft 365 Enterprise antes da implantação de produção ou da implantação de opções específicas com os TLGs (Guias de Laboratório de Teste). Os TLGs são artigos modulares e prescritivos que orientam você na configuração da infraestrutura ou do recurso em um ambiente simplificado, mas representativo, usando assinaturas de avaliação ou pagas.</span><span class="sxs-lookup"><span data-stu-id="f4a60-p104">Play with Microsoft 365 Enterprise prior to production deployment or the deployment of specific options with Test Lab Guides (TLGs). TLGs are modular, prescriptive articles that step you through the configuration of infrastructure or a feature in a simplified but representative environment using trial or paid subscriptions.</span></span> 

<span data-ttu-id="f4a60-126">Com os TLGs, você pode demonstrar, personalizar ou compilar uma prova de conceito de uma configuração, carga de trabalho ou cenário de ponta a ponta complexos.</span><span class="sxs-lookup"><span data-stu-id="f4a60-126">With TLGs, you can demonstrate, customize, or build a proof of concept of a complex configuration, workload, or end-to-end scenario.</span></span>

<span data-ttu-id="f4a60-127">Para saber mais, confira [Guias do Laboratório de Teste do Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="f4a60-127">For more information, see [Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>

![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

## <a name="how-customers-use-microsoft-365-enterprise"></a><span data-ttu-id="f4a60-129">Como os clientes usam o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f4a60-129">How customers use Microsoft 365 Enterprise</span></span>

<span data-ttu-id="f4a60-130">Confira nestes recursos como os clientes estão usando o Microsoft 365 Enterprise como solução completa e inteligente que promove a criatividade e o trabalho em equipe com segurança para todos:</span><span class="sxs-lookup"><span data-stu-id="f4a60-130">See these resources to learn how customers are using Microsoft 365 Enterprise as their complete, intelligent solution that empowers everyone to be creative and work together securely:</span></span>

- <span data-ttu-id="f4a60-131">Serviços de saúde</span><span class="sxs-lookup"><span data-stu-id="f4a60-131">Health services</span></span>
  - [<span data-ttu-id="f4a60-132">Leila idealiza um espaço de trabalho onde a colaboração interna e externa ajuda na inovação e acelera o tempo de chegada ao mercado de novos medicamentos</span><span class="sxs-lookup"><span data-stu-id="f4a60-132">Lilly envisions a workplace where internal and external collaboration help enable innovation and accelerate time-to-market for new medicines</span></span>](https://aka.ms/Eli_CLS)
  - [<span data-ttu-id="f4a60-133">Inovadora tecnologia do setor de saúde acelera a prevenção do diabetes na nuvem </span><span class="sxs-lookup"><span data-stu-id="f4a60-133">Healthcare technology innovator accelerates diabetes prevention in the cloud </span></span>](https://aka.ms/Soleracasestudy)
  - [<span data-ttu-id="f4a60-134">O Adventist Health System está aprimorando os cuidados de serviços de saúde com o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f4a60-134">Adventist Health System is enhancing healthcare delivery using Microsoft 365</span></span>](https://aka.ms/adventisthealth)
  - [<span data-ttu-id="f4a60-135">A Abrona acelera a conformidade com o RGPD e aumenta a produtividade com o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f4a60-135">Abrona accelerates GDPR compliance and increases productivity with Microsoft 365</span></span>](https://aka.ms/Abrona)
  - [<span data-ttu-id="f4a60-136">A Centra adota a transformação e melhora o atendimento aos pacientes com as ferramentas comerciais inteligentes do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f4a60-136">Centra embraces transformation, improves patient care with Microsoft 365 intelligent business tools</span></span>](https://aka.ms/Centra_Health)
  - [<span data-ttu-id="f4a60-137">A Advocate Aurora Health ajuda os pacientes a viver bem usando a solução de coordenação de cuidados da Microsoft para melhorar a colaboração</span><span class="sxs-lookup"><span data-stu-id="f4a60-137">Advocate Aurora Health helps patients live well using Microsoft care coordination solution to enhance collaboration</span></span>](https://aka.ms/Advocate_)
- <span data-ttu-id="f4a60-138">Serviços financeiros</span><span class="sxs-lookup"><span data-stu-id="f4a60-138">Financial services</span></span>
  - [<span data-ttu-id="f4a60-139">O TD Bank capacita os funcionários com a tecnologia adaptativa no Office 365 e Windows 10</span><span class="sxs-lookup"><span data-stu-id="f4a60-139">TD Bank empowers employees with assistive technology in Office 365 and Windows 10</span></span>](https://aka.ms/tdbankgroup)
  - [<span data-ttu-id="f4a60-140">Start-up familiar de declarações de imposto de renda elege solução integrada para ajudar a expandir os negócios</span><span class="sxs-lookup"><span data-stu-id="f4a60-140">Family tax preparation startup chooses all-in-one solution to help grow business</span></span>](https://aka.ms/SOSCaseStudy)
- <span data-ttu-id="f4a60-141">Transportes</span><span class="sxs-lookup"><span data-stu-id="f4a60-141">Transportation</span></span>
  - [<span data-ttu-id="f4a60-142">A Qantas capacita os funcionários para fazer o melhor trabalho possível com o Microsoft 365, aprimorando a experiência do cliente</span><span class="sxs-lookup"><span data-stu-id="f4a60-142">Qantas empowers employees to do their best work with Microsoft 365, enhancing customer experience</span></span>](https://aka.ms/Qantas_CS)
  - [<span data-ttu-id="f4a60-143">A Amtrak mantém sua empresa móvel à frente do cronograma com o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f4a60-143">Amtrak keeps its mobile enterprise running ahead of schedule with Microsoft 365</span></span>](https://aka.ms/Amtrak_)
- <span data-ttu-id="f4a60-144">Fabricação</span><span class="sxs-lookup"><span data-stu-id="f4a60-144">Manufacturing</span></span>
  - [<span data-ttu-id="f4a60-145">Siderúrgica elimina custos com hardware e simplifica a tecnologia da informação, ganhando produtividade móvel na nuvem</span><span class="sxs-lookup"><span data-stu-id="f4a60-145">Steel company eliminates hardware costs, streamlines IT, and gains mobile productivity in the cloud</span></span>](https://aka.ms/Steeledalecasestudy)
  - [<span data-ttu-id="f4a60-146">Fornecedora de equipamentos de bordado capacita a empresa com serviços baseados na nuvem e faz divulgação para outras pequenas empresas</span><span class="sxs-lookup"><span data-stu-id="f4a60-146">Embroidery equipment supplier empowers its business with cloud-based services, spreads word to other small businesses</span></span>](https://aka.ms/PriorityLLCCaseStudy)
  - [<span data-ttu-id="f4a60-147">Empresa familiar mostra ao mundo o trabalho dos seus funcionários com deficiências</span><span class="sxs-lookup"><span data-stu-id="f4a60-147">Father and son business shows the world what employees with disabilities can achieve</span></span>](https://aka.ms/JCSCaseStudy)
  - [<span data-ttu-id="f4a60-148">Empresa do setor de coco ganha mobilidade aprimorada, melhores métricas e aumento da produtividade, modernizando as ferramentas de colaboração</span><span class="sxs-lookup"><span data-stu-id="f4a60-148">Coconut company gains improved mobility, better metrics, and increased productivity by modernizing collaboration tools</span></span>](https://aka.ms/SilvermillCS)
  - [<span data-ttu-id="f4a60-149">Inovador japonês de sucesso encontra flexibilidade durável e segurança avançada com o Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="f4a60-149">Thriving Japanese innovator finds future-proof flexibility and enhanced security with Microsoft 365 Business</span></span>](https://aka.ms/DreamFactoryCaseStudy)
- <span data-ttu-id="f4a60-150">Engenharia</span><span class="sxs-lookup"><span data-stu-id="f4a60-150">Engineering</span></span>
   - [<span data-ttu-id="f4a60-151">A frequência aumenta o ritmo da empresa com ferramentas de colaboração móvel</span><span class="sxs-lookup"><span data-stu-id="f4a60-151">Cadence increases the pace of business with mobile collaboration tools</span></span>](https://customers.microsoft.com/story/cadence-partner-professional-services-microsoft-365)
- <span data-ttu-id="f4a60-152">Serviços professionais</span><span class="sxs-lookup"><span data-stu-id="f4a60-152">Professional services</span></span>
  - [<span data-ttu-id="f4a60-153">Firma de advocacia de imóveis de elite promove expansão com uma plataforma completa baseada na nuvem </span><span class="sxs-lookup"><span data-stu-id="f4a60-153">Boutique business and real estate law firm supports expansion with comprehensive cloud-based platform </span></span>](https://aka.ms/Lieserskaffcasestudy)
  - [<span data-ttu-id="f4a60-154">Empresa de tecnologia esportiva ajuda os atletas a alcançar desempenho máximo por meio de análise e feedback de saúde</span><span class="sxs-lookup"><span data-stu-id="f4a60-154">Sports technology company helps athletes reach their peak through biofeedback and analytics </span></span>](https://aka.ms/KMOTIONCasestudy)
  - [<span data-ttu-id="f4a60-155">A transformação digital e a nuvem capacitam associação comercial para atender melhor aos membros </span><span class="sxs-lookup"><span data-stu-id="f4a60-155">Digital transformation and the cloud empower business association to serve its members better </span></span>](https://aka.ms/AIMCS)
- <span data-ttu-id="f4a60-156">Serviços de energia</span><span class="sxs-lookup"><span data-stu-id="f4a60-156">Energy services</span></span>
  - [<span data-ttu-id="f4a60-157">A Schlumberger refina o trabalho em equipe global com o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f4a60-157">Schlumberger refines global teamwork with Microsoft 365</span></span>](https://aka.ms/Schlumberger_)
- <span data-ttu-id="f4a60-158">Construção</span><span class="sxs-lookup"><span data-stu-id="f4a60-158">Construction</span></span>
  - [<span data-ttu-id="f4a60-159">A busca por solução de segurança de dados desvenda recursos de colaboração do Microsoft 365 em empreiteira</span><span class="sxs-lookup"><span data-stu-id="f4a60-159">Search for data security solution unearths collaborative capabilities of Microsoft 365 at general contracting company</span></span>](https://aka.ms/Transbluecasestudy)
- <span data-ttu-id="f4a60-160">Consultoria</span><span class="sxs-lookup"><span data-stu-id="f4a60-160">Consulting</span></span>
  - [<span data-ttu-id="f4a60-161">ERM contribui para um futuro mais sustentável com o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f4a60-161">ERM contributes to a more sustainable future with Microsoft 365</span></span>](https://aka.ms/ERM_CS)
- <span data-ttu-id="f4a60-162">Instituições sem fins lucrativos</span><span class="sxs-lookup"><span data-stu-id="f4a60-162">Non-profit</span></span>
  - [<span data-ttu-id="f4a60-163">Mover para a nuvem economiza até 500 mil dólares de instituições sem fins lucrativos, melhorando a segurança, mobilidade e colaboração </span><span class="sxs-lookup"><span data-stu-id="f4a60-163">Move to the cloud saves nonprofit $500,000 while improving security, mobility, and collaboration </span></span>](https://aka.ms/MOWCaseStudy)
  
## <a name="how-microsoft-uses-microsoft-365-enterprise"></a><span data-ttu-id="f4a60-164">Como a Microsoft usa o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f4a60-164">How Microsoft uses Microsoft 365 Enterprise</span></span>

<span data-ttu-id="f4a60-165">Dê uma olhada na TI da Microsoft e saiba como eles implantaram o Microsoft 365 Enterprise e como os funcionários da Microsoft o usam todos os dias.</span><span class="sxs-lookup"><span data-stu-id="f4a60-165">Take a peek inside Microsoft IT and learn how they deployed Microsoft 365 Enterprise and how Microsoft employees use it every day.</span></span>

### <a name="networking"></a><span data-ttu-id="f4a60-166">Rede</span><span class="sxs-lookup"><span data-stu-id="f4a60-166">Networking</span></span>

- [<span data-ttu-id="f4a60-167">Otimização do desempenho da rede com o Microsoft Office 365</span><span class="sxs-lookup"><span data-stu-id="f4a60-167">Optimizing network performance for Microsoft Office 365</span></span>](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365)

### <a name="identity"></a><span data-ttu-id="f4a60-168">Identidade</span><span class="sxs-lookup"><span data-stu-id="f4a60-168">Identity</span></span>

- [<span data-ttu-id="f4a60-169">Gerenciamento de identidades de usuários e acesso seguro da Microsoft</span><span class="sxs-lookup"><span data-stu-id="f4a60-169">Managing user identities and secure access at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/931/Managing-user-identities-and-secure-access-at-Microsoft)
- [<span data-ttu-id="f4a60-170">Usar o Azure AD Privileged Identity Management para acesso elevado</span><span class="sxs-lookup"><span data-stu-id="f4a60-170">Using Azure AD Privileged Identity Management for elevated access</span></span>](https://www.microsoft.com/itshowcase/Article/Content/887/Using-Azure-AD-Privileged-Identity-Management-for-elevated-access)

### <a name="windows-10-enterprise"></a><span data-ttu-id="f4a60-171">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f4a60-171">Windows 10 Enterprise</span></span>

- [<span data-ttu-id="f4a60-172">Preparo da organização para uma implantação perfeita do Windows 10</span><span class="sxs-lookup"><span data-stu-id="f4a60-172">Preparing your organization for a seamless Windows 10 deployment</span></span>](https://www.microsoft.com/itshowcase/windows10deployment?wt.mc_id=bmkg_itsc)
- [<span data-ttu-id="f4a60-173">Adoção do Windows como serviço na Microsoft</span><span class="sxs-lookup"><span data-stu-id="f4a60-173">Adopting Windows as a service at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/851/Adopting-Windows-as-a-service-at-Microsoft)
- [<span data-ttu-id="f4a60-174">Implantar o Windows 10 na Microsoft como uma atualização in-loco</span><span class="sxs-lookup"><span data-stu-id="f4a60-174">Deploying Windows 10 at Microsoft as an in-place upgrade</span></span>](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- [<span data-ttu-id="f4a60-175">Implementação de autenticação segura do usuário com o Windows Hello para Empresas</span><span class="sxs-lookup"><span data-stu-id="f4a60-175">Implementing strong user authentication with Windows Hello for Business</span></span>](https://www.microsoft.com/itshowcase/Article/Content/756/Implementing-strong-user-authentication-with-Windows-Hello-for-Business)
- <span data-ttu-id="f4a60-176">[Implantação do Windows 10: dicas e truques da TI da Microsoft](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (vídeo)</span><span class="sxs-lookup"><span data-stu-id="f4a60-176">[Windows 10 deployment: tips and tricks from Microsoft IT](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (video)</span></span>
- [<span data-ttu-id="f4a60-177">A Proteção Avançada contra Ameaças do Windows Defender ajuda a detectar ameaças sofisticadas</span><span class="sxs-lookup"><span data-stu-id="f4a60-177">Windows Defender ATP helps detect sophisticated threats</span></span>](https://www.microsoft.com/itshowcase/Article/Content/854/Windows-Defender-ATP-helps-detect-sophisticated-threats)
- <span data-ttu-id="f4a60-178">[Proteção da empresa moderna com o Windows Defender e a Proteção Avançada contra Ameaças do Windows Defender](https://www.microsoft.com/itshowcase/Article/Content/903/Securing-the-modern-enterprise-with-Windows-Defender-and-Windows-Defender-ATP) (vídeo)</span><span class="sxs-lookup"><span data-stu-id="f4a60-178">[Securing the modern enterprise with Windows Defender and Windows Defender ATP](https://www.microsoft.com/itshowcase/Article/Content/903/Securing-the-modern-enterprise-with-Windows-Defender-and-Windows-Defender-ATP) (video)</span></span>

### <a name="office-365-proplus"></a><span data-ttu-id="f4a60-179">Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="f4a60-179">Office 365 ProPlus</span></span>

- [<span data-ttu-id="f4a60-180">Preparo da organização para uma implantação perfeita do Office 365 ProPlus 2016</span><span class="sxs-lookup"><span data-stu-id="f4a60-180">Preparing your organization for a seamless Office 365 ProPlus 2016 deployment</span></span>](https://www.microsoft.com/itshowcase/Office365adoption)
- [<span data-ttu-id="f4a60-181">Implantar e atualizar o Microsoft Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="f4a60-181">Deploying and updating Microsoft Office 365 ProPlus</span></span>](https://www.microsoft.com/itshowcase/Article/Content/757/Deploying-and-updating-Microsoft-Office-365-ProPlus)
- <span data-ttu-id="f4a60-182">[Canais de automação e atualização ajudam a implantar o Microsoft Office 365 ProPlus](https://www.microsoft.com/itshowcase/Article/Content/794/Automation-and-update-channels-help-deploy-Microsoft-Office-365-ProPlus) (vídeo)</span><span class="sxs-lookup"><span data-stu-id="f4a60-182">[Automation and update channels help deploy Microsoft Office 365 ProPlus](https://www.microsoft.com/itshowcase/Article/Content/794/Automation-and-update-channels-help-deploy-Microsoft-Office-365-ProPlus) (video)</span></span>

### <a name="mobility-and-device-management"></a><span data-ttu-id="f4a60-183">Mobilidade e gerenciamento de dispositivos</span><span class="sxs-lookup"><span data-stu-id="f4a60-183">Mobility and device management</span></span>

- [<span data-ttu-id="f4a60-184">Gerenciar a produtividade móvel moderna com o Enterprise Mobility + Security</span><span class="sxs-lookup"><span data-stu-id="f4a60-184">Managing modern mobile productivity with Enterprise Mobility + Security</span></span>](https://www.microsoft.com/itshowcase/Article/Content/972/Managing-modern-mobile-productivity-with-Enterprise-Mobility--Security)
- [<span data-ttu-id="f4a60-185">Conectar-se para trabalhar no dispositivo Windows 10 com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="f4a60-185">Connecting to work on your Windows 10 device with Microsoft Intune</span></span>](https://www.microsoft.com/itshowcase/Article/Content/783/Connecting-to-work-on-your-Windows-10-device-with-Microsoft-Intune)
- [<span data-ttu-id="f4a60-186">Habilitar a produtividade móvel para dispositivos iOS, OS X e Android da Microsoft</span><span class="sxs-lookup"><span data-stu-id="f4a60-186">Enabling mobile productivity for iOS, OS X, and Android devices at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/773/Enabling-mobile-productivity-for-iOS-OS-X-and-Android-devices-at-Microsoft)

### <a name="security-and-information-protection"></a><span data-ttu-id="f4a60-187">Segurança e proteção de informações</span><span class="sxs-lookup"><span data-stu-id="f4a60-187">Security and information protection</span></span>

- [<span data-ttu-id="f4a60-188">Proteção de arquivos na nuvem com a Proteção de Informações do Azure</span><span class="sxs-lookup"><span data-stu-id="f4a60-188">Protecting files in the cloud with Azure Information Protection</span></span>](https://www.microsoft.com/itshowcase/Article/Content/924/Protecting-files-in-the-cloud-with-Azure-Information-Protection)
- [<span data-ttu-id="f4a60-189">A Microsoft usa inteligência contra ameaças para proteger, detectar e responder a ameaças</span><span class="sxs-lookup"><span data-stu-id="f4a60-189">Microsoft uses threat intelligence to protect, detect, and respond to threats</span></span>](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [<span data-ttu-id="f4a60-190">A Microsoft impede tentativas de phishing com o Office 365</span><span class="sxs-lookup"><span data-stu-id="f4a60-190">Microsoft thwarts phishing attempts with Office 365</span></span>](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

### <a name="microsoft-teams"></a><span data-ttu-id="f4a60-191">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f4a60-191">Microsoft Teams</span></span>

- [<span data-ttu-id="f4a60-192">A implantação do Microsoft Teams simplifica a colaboração e melhora o trabalho em equipe</span><span class="sxs-lookup"><span data-stu-id="f4a60-192">Deploying Microsoft Teams streamlines collaboration and improves teamwork</span></span>](https://www.microsoft.com/itshowcase/Article/Content/1013/Deploying-Microsoft-Teams-streamlines-collaboration-and-improves-teamwork)
- [<span data-ttu-id="f4a60-193">O Microsoft Teams amplia a colaboração no ambiente de trabalho moderno da Microsoft</span><span class="sxs-lookup"><span data-stu-id="f4a60-193">Microsoft Teams increases collaboration in the modern workplace at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/1012/Microsoft-Teams-increases-collaboration-in-the-modern-workplace-at-Microsoft)

### <a name="data-migration"></a><span data-ttu-id="f4a60-194">Migração de dados</span><span class="sxs-lookup"><span data-stu-id="f4a60-194">Data migration</span></span>

- [<span data-ttu-id="f4a60-195">A Microsoft migra 150 mil caixas de correio para o Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f4a60-195">Microsoft migrates 150,000 mailboxes to Exchange Online</span></span>](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [<span data-ttu-id="f4a60-196">SharePoint para a nuvem: saiba como a Microsoft realizou a própria migração</span><span class="sxs-lookup"><span data-stu-id="f4a60-196">SharePoint to the cloud: Learn how Microsoft ran its own migration</span></span>](https://www.microsoft.com/itshowcase/Article/Content/691/SharePoint-to-the-cloud-Learn-how-Microsoft-ran-its-own-migration)

## <a name="how-the-contoso-corporation-deployed-microsoft-365-enterprise"></a><span data-ttu-id="f4a60-197">Como a Contoso Corporation implantou o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f4a60-197">How the Contoso Corporation deployed Microsoft 365 Enterprise</span></span>

<span data-ttu-id="f4a60-p105">A Contoso Corporation é um conglomerado fictício mas representativo de fabricantes globais, com sede em Paris. Confira como a [Contoso implantou o Microsoft 365 Enterprise](contoso-case-study.md) e lidou com grandes decisões de projeto e detalhes de implementação de redes, identidade, Windows 10 Enterprise, Office 365 ProPlus, gerenciamento de dispositivos móveis, proteção da informação e segurança.</span><span class="sxs-lookup"><span data-stu-id="f4a60-p105">The Contoso Corporation is a fictional but representative global manufacturing conglomerate with its headquarters in Paris. See how [Contoso deployed Microsoft 365 Enterprise](contoso-case-study.md) and addressed major design decisions and implementation details for networking, identity, Windows 10 Enterprise, Office 365 ProPlus, mobile device management, information protection, and security.</span></span> 

![](./media/contoso-overview/contoso-icon.png)

## <a name="additional-microsoft-365-solutions"></a><span data-ttu-id="f4a60-200">Soluções adicionais do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f4a60-200">Additional Microsoft 365 solutions</span></span>

- [<span data-ttu-id="f4a60-201">Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="f4a60-201">Microsoft 365 Business</span></span>](https://docs.microsoft.com/microsoft-365/business/)
 
  <span data-ttu-id="f4a60-202">Reúne a melhor produtividade disponível e as funcionalidades de colaboração do Office 365 com o gerenciamento de dispositivo e as soluções de segurança para proteger os dados comerciais de pequenas e médias empresas (PME).</span><span class="sxs-lookup"><span data-stu-id="f4a60-202">Bring together the best-in-class productivity and collaboration capabilities of Office 365 with device management and security solutions to safeguard business data for small and midsize businesses (SMB).</span></span>

- [<span data-ttu-id="f4a60-203">Microsoft 365 Education</span><span class="sxs-lookup"><span data-stu-id="f4a60-203">Microsoft 365 Education</span></span>](https://docs.microsoft.com/education)
 
  <span data-ttu-id="f4a60-204">Permite aos educadores desbloquear a criatividade, além de promover o trabalho em equipe e fornecer uma experiência simples e segura em uma única solução acessível, criada para fins educacionais.</span><span class="sxs-lookup"><span data-stu-id="f4a60-204">Empower educators to unlock creativity, promote teamwork, and provide a simple and safe experience in a single, affordable solution built for education.</span></span>

## <a name="next-step"></a><span data-ttu-id="f4a60-205">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="f4a60-205">Next step</span></span>

<span data-ttu-id="f4a60-206">Use o [FastTrack](https://fasttrack.microsoft.com/microsoft365) ou inicie a [infraestrutura de base](deploy-foundation-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="f4a60-206">Use [FastTrack](https://fasttrack.microsoft.com/microsoft365) or get started with the [foundation infrastructure](deploy-foundation-infrastructure.md).</span></span>
