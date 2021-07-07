---
title: Perguntas frequentes sobre base de teste
description: Revisar perguntas frequentes
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: troubleshooting
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 9d24ecb807e60733471be60353d12789f19be1b4
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322552"
---
# <a name="test-base-faq"></a><span data-ttu-id="068d1-103">Perguntas frequentes sobre base de teste</span><span class="sxs-lookup"><span data-stu-id="068d1-103">Test Base FAQ</span></span>

<span data-ttu-id="068d1-104">**P: Como enviar nossos pacotes para a equipe da Base de Teste?**</span><span class="sxs-lookup"><span data-stu-id="068d1-104">**Q: How do we submit our packages to Test Base team?**</span></span>

<span data-ttu-id="068d1-105">**R:** Envie seus pacotes diretamente para o ambiente da Base de Teste usando nosso portal de autoatendício.</span><span class="sxs-lookup"><span data-stu-id="068d1-105">**A:** Submit your packages directly to the Test Base environment using our self-serve portal.</span></span>

<span data-ttu-id="068d1-106">Para enviar seu pacote de aplicativos, navegue até o Portal do [Azure](https://www.aka.ms/testbaseportal "Página Inicial da Base de Teste") e carregue uma pasta com zipped contendo binários, dependências e scripts de teste do aplicativo por meio do painel do portal da Base de Teste de autoatendência.</span><span class="sxs-lookup"><span data-stu-id="068d1-106">To submit your application package, navigate to the [Azure Portal](https://www.aka.ms/testbaseportal "Test Base Homepage") and upload a zipped folder containing your application's binaries, dependencies, and test scripts via the self-serve Test Base portal dashboard.</span></span> 

<span data-ttu-id="068d1-107">Consulte o guia do usuário de integração para obter mais informações ou entre em contato com nossa equipe para <testbasepreview@microsoft.com> obter assistência e mais informações.</span><span class="sxs-lookup"><span data-stu-id="068d1-107">Please see the onboarding user guide for more information or contact our team at <testbasepreview@microsoft.com> for assistance and more information.</span></span>

<span data-ttu-id="068d1-108">**P: O que são testes OOB (out-of-box) ?**</span><span class="sxs-lookup"><span data-stu-id="068d1-108">**Q: What are Out-of-box (OOB) tests?**</span></span>

<span data-ttu-id="068d1-109">**R:** Os testes OOB (out-of-box) são padronizados, os testes padrão são executados onde os pacotes de aplicativos são instalados, lançados e fechados trinta (30) vezes e, em seguida, desinstalados.</span><span class="sxs-lookup"><span data-stu-id="068d1-109">**A:** Out-of-box (OOB) tests are standardized, default test runs where application packages are installed, launched and closed thirty (30) times, and then uninstalled.</span></span> 

<span data-ttu-id="068d1-110">Os pacotes criados para a Base de Teste terão os seguintes scripts de teste: instalar, iniciar, fechar e, opcionalmente, o script de desinstalação.</span><span class="sxs-lookup"><span data-stu-id="068d1-110">The packages created for Test Base will have the following test scripts: install, launch, close, and optionally the uninstall script.</span></span> 

<span data-ttu-id="068d1-111">Os testes OOB (Out-of-box) fornecem telemetria padronizada em seu aplicativo para comparação entre Windows builds.</span><span class="sxs-lookup"><span data-stu-id="068d1-111">The Out-of-box (OOB) tests provide you with standardized telemetry on your application to compare across Windows builds.</span></span>

<span data-ttu-id="068d1-112">**P: Podemos enviar testes fora dos testes fora da caixa de correio (instalar, iniciar, fechar, desinstalar scripts de teste)?**</span><span class="sxs-lookup"><span data-stu-id="068d1-112">**Q: Can we submit tests outside of the Out-of-box tests (install, launch, close, uninstall test scripts)?**</span></span>

<span data-ttu-id="068d1-113">**R:** Sim, os clientes também podem carregar pacotes de aplicativos para **testes funcionais** por meio do painel do portal de autoatend responsabilidade.</span><span class="sxs-lookup"><span data-stu-id="068d1-113">**A:** Yes, customers can also upload application packages for **functional tests** via the self-serve portal dashboard.</span></span>
<span data-ttu-id="068d1-114">**Testes funcionais** são testes que permitem que os clientes executem seus scripts para executar a funcionalidade personalizada em seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="068d1-114">**Functional tests** are tests that enable customers execute their scripts to run custom functionality on their application.</span></span>


## <a name="testing"></a><span data-ttu-id="068d1-115">Testes</span><span class="sxs-lookup"><span data-stu-id="068d1-115">Testing</span></span>

<span data-ttu-id="068d1-116">**P: Você suporta testes funcionais?**</span><span class="sxs-lookup"><span data-stu-id="068d1-116">**Q: Do you support functional tests?**</span></span>

<span data-ttu-id="068d1-117">**R:** Sim, a Base de Teste dá suporte a testes funcionais.</span><span class="sxs-lookup"><span data-stu-id="068d1-117">**A:** Yes, Test Base supports functional tests.</span></span> <span data-ttu-id="068d1-118">Testes funcionais são testes que permitem que nossos clientes executem seus scripts para executar a funcionalidade personalizada em seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="068d1-118">Functional tests are tests that enable our customers execute their scripts to run custom functionality on their application.</span></span> 

<span data-ttu-id="068d1-119">Para enviar seu pacote de aplicativos para testes funcionais, basta carregar a pasta de zipped contendo binários, dependências e scripts de teste do aplicativo por meio do painel do portal de autoatendência.</span><span class="sxs-lookup"><span data-stu-id="068d1-119">To submit your application package for functional testing, simply upload the zipped folder containing your application's binaries, dependencies, and test scripts via our self-serve portal dashboard.</span></span> 

<span data-ttu-id="068d1-120">Consulte o guia do usuário de integração para obter mais informações ou entre em contato com nossa equipe para <testbasepreview@microsoft.com> obter assistência e mais informações.</span><span class="sxs-lookup"><span data-stu-id="068d1-120">Please see the onboarding user guide for more information or contact our team at <testbasepreview@microsoft.com> for assistance and more information.</span></span>

<span data-ttu-id="068d1-121">**P: Como a Base de Teste lida com nossos dados de teste?**</span><span class="sxs-lookup"><span data-stu-id="068d1-121">**Q: How does Test Base handle our test data?**</span></span>

<span data-ttu-id="068d1-122">**R:** A Base de Teste coleta e gerencia com segurança seus dados de teste no ambiente do Azure.</span><span class="sxs-lookup"><span data-stu-id="068d1-122">**A:** Test Base securely collects and manages your test data on the Azure environment.</span></span> 

<span data-ttu-id="068d1-123">**P: A Base de Teste pode dar suporte aos nossos testes automatizados?**</span><span class="sxs-lookup"><span data-stu-id="068d1-123">**Q: Can Test Base support our automated tests?**</span></span>

<span data-ttu-id="068d1-124">Sim, a Base de Teste oferece suporte a testes automatizados, no entanto, não suportamos testes manuais no momento devido aos recursos de serviço.</span><span class="sxs-lookup"><span data-stu-id="068d1-124">Yes, Test Base supports automated tests however, we do not support manual tests at this time due to service capabilities.</span></span>

<span data-ttu-id="068d1-125">**P: Quais idiomas e estruturas de testes automatizados você suporta?**</span><span class="sxs-lookup"><span data-stu-id="068d1-125">**Q: What languages and frameworks of automated tests do you support?**</span></span>

<span data-ttu-id="068d1-126">**R:** Suportamos todos os idiomas e estruturas.</span><span class="sxs-lookup"><span data-stu-id="068d1-126">**A:** We support all languages and frameworks.</span></span> <span data-ttu-id="068d1-127">Invocamos todos os scripts por meio do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="068d1-127">We invoke all scripts through PowerShell.</span></span> 

<span data-ttu-id="068d1-128">Você também precisará fornecer (carregar) os binários dependentes da estrutura necessária.</span><span class="sxs-lookup"><span data-stu-id="068d1-128">You will also need to provide (upload) the dependent binaries of the required framework.</span></span>

<span data-ttu-id="068d1-129">**P: Em quanto tempo a Base de Teste fornece resultados de teste?**</span><span class="sxs-lookup"><span data-stu-id="068d1-129">**Q: How soon does Test Base provide test results?**</span></span>

<span data-ttu-id="068d1-130">**R:** Para cada teste executado em relação às versões de pré-lançamento, forneceremos resultados dentro de 48 horas no painel [do Portal do Azure.](https://www.aka.ms/testbaseportal "Página Inicial da Base de Teste")</span><span class="sxs-lookup"><span data-stu-id="068d1-130">**A:** For each test that we run against the pre-release builds, we will provide results within 48 hours on your [Azure Portal](https://www.aka.ms/testbaseportal "Test Base Homepage") dashboard.</span></span>

<span data-ttu-id="068d1-131">**P: Você pode reiniciar após a instalação?**</span><span class="sxs-lookup"><span data-stu-id="068d1-131">**Q: Can you reboot after install?**</span></span>

<span data-ttu-id="068d1-132">**R:** Sim, nosso processo dá suporte à reinicialização após a instalação.</span><span class="sxs-lookup"><span data-stu-id="068d1-132">**A:** Yes, our process supports rebooting after installation.</span></span> <span data-ttu-id="068d1-133">Certifique-se de selecionar essa opção na lista de opções "Configurações opcionais" ao definir suas **Tarefas** no portal de integração.</span><span class="sxs-lookup"><span data-stu-id="068d1-133">Be sure to select this option from the “Optional settings” drop list when setting your **Tasks** on the onboarding portal.</span></span>

<span data-ttu-id="068d1-134">Para testes OOB (out-of-box), você pode especificar se uma reinicialização é necessária para o _script Install._</span><span class="sxs-lookup"><span data-stu-id="068d1-134">For Out-of-box (OOB) tests, you can specify whether a reboot is needed for the _Install script._</span></span>

![Imagem de reinicialização](Media/reboot.png)

<span data-ttu-id="068d1-136">Enquanto para testes funcionais, você pode especificar se uma reinicialização é necessária para cada script adicionado.</span><span class="sxs-lookup"><span data-stu-id="068d1-136">While for functional tests, you can specify whether a reboot is required for each script that is added.</span></span>

![Como selecionar testes funcionais](Media/functionalreboot.png)

<span data-ttu-id="068d1-138">**P: Quais Windows você suporta?**</span><span class="sxs-lookup"><span data-stu-id="068d1-138">**Q: What Windows versions do you support?**</span></span>

<span data-ttu-id="068d1-139">**R:** Atualmente, suportamos clientes Windows 10, Windows Server 2016, Windows Server 2016 versão Core, Windows Server 2019 e Windows Server 2019 Core versão.</span><span class="sxs-lookup"><span data-stu-id="068d1-139">**A:** We currently support Windows 10 clients, Windows Server 2016, Windows Server 2016 Core version, Windows Server 2019, and Windows Server 2019 Core version.</span></span>

<span data-ttu-id="068d1-140">**P: Qual é a diferença entre testes de Atualização de Segurança e Testes de Atualização de Recursos?**</span><span class="sxs-lookup"><span data-stu-id="068d1-140">**Q: What is the difference between Security Update tests and Feature Update tests?**</span></span>

<span data-ttu-id="068d1-141">**R:** Para testes de atualização de segurança, testamos as atualizações de segurança de **<ins>pré-lançamento</ins>** mensais em Windows que se concentram em manter nossos usuários sempre seguros e protegidos.</span><span class="sxs-lookup"><span data-stu-id="068d1-141">**A:** For Security update tests, we test against the **<ins>monthly pre-release security updates</ins>** on Windows which are focused on keeping our users always secure and protected.</span></span> <span data-ttu-id="068d1-142">Para os testes de atualização de recursos, testamos as atualizações de recursos de **<ins>pré-lançamento</ins>** anuais que introduzem novos recursos e recursos no Windows.</span><span class="sxs-lookup"><span data-stu-id="068d1-142">For the Feature update tests, we test against the **<ins>bi-annual pre-release feature updates</ins>** which introduces new features and capabilities on Windows.</span></span>

## <a name="debugging-options"></a><span data-ttu-id="068d1-143">Opções de depuração</span><span class="sxs-lookup"><span data-stu-id="068d1-143">Debugging options</span></span>

<span data-ttu-id="068d1-144">**P: Temos acesso às Máquinas Virtuais (VMs) em caso de falhas? O que o Test Base compartilha?**</span><span class="sxs-lookup"><span data-stu-id="068d1-144">**Q: Do we get access to the Virtual Machines (VMs) in case of failures? What does Test Base share?**</span></span>

<span data-ttu-id="068d1-145">**R:** Para que o serviço seja compatível e as atualizações de pré-lançamento sejam seguras, somente a Microsoft tem acesso às VMs.</span><span class="sxs-lookup"><span data-stu-id="068d1-145">**A:** For the service to be compliant and the pre-release updates be secure, only Microsoft has access to the VMs.</span></span> <span data-ttu-id="068d1-146">No entanto, os clientes podem exibir resultados de teste e outras métricas de teste em seu painel de portal, incluindo sinais de falha e travamento, métricas de confiabilidade, memória e utilização de CPU etc. Também geramos e fornecemos logs de testes executados no painel para download e análise posterior.</span><span class="sxs-lookup"><span data-stu-id="068d1-146">However, customers can view test results and other test metrics on their portal dashboard, including crash and hang signals, reliability metrics, memory and CPU utilization etc. We also generate and provide logs of test runs on the dashboard for download and further analysis.</span></span> 

<span data-ttu-id="068d1-147">Também podemos fornecer despejos de memória para depuração de falhas conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="068d1-147">We can also provide memory dumps for crash debugging as needed.</span></span>

<span data-ttu-id="068d1-148">**P: Se houver problemas encontrados durante o teste, quais são as próximas etapas para resolver esses problemas?**</span><span class="sxs-lookup"><span data-stu-id="068d1-148">**Q: If there are issues found during the testing, what are the next steps to resolve these issues?**</span></span>

<span data-ttu-id="068d1-149">**R:** A equipe da Base de Teste realizará um processo de triagem inicial para determinar a causa raiz do erro e, dependendo de nossas descobertas, encaminharemos para o cliente ou equipes internas da Microsoft para depuração.</span><span class="sxs-lookup"><span data-stu-id="068d1-149">**A:** The Test Base team will perform an initial triage process to determine the root cause of the error, and then depending on our findings, we will route to the customer or internal teams within Microsoft for debugging.</span></span> 

<span data-ttu-id="068d1-150">Sempre trabalhamos de perto com nossos clientes em correção conjunta para resolver quaisquer problemas.</span><span class="sxs-lookup"><span data-stu-id="068d1-150">We always work closely with our customers in joint remediation to resolve any issues.</span></span> 

<span data-ttu-id="068d1-151">**P: A Microsoft mantém a versão do patch de segurança até que o problema seja resolvido? Quais resoluções alternativas estão disponíveis?**</span><span class="sxs-lookup"><span data-stu-id="068d1-151">**Q: Does Microsoft hold the release of the security patch until the issue is resolved? What alternate resolutions are available?**</span></span>

<span data-ttu-id="068d1-152">**R:** O objetivo da Base de Teste é garantir que nossos clientes finais conjuntos não enfrentem problemas.</span><span class="sxs-lookup"><span data-stu-id="068d1-152">**A:** The goal of Test Base is to ensure our joint end customers do not face any issues.</span></span> <span data-ttu-id="068d1-153">Trabalharemos com fornecedores de software para resolver quaisquer problemas antes da versão, mas caso a correção não seja viável, temos outras resoluções, como shims e blocos.</span><span class="sxs-lookup"><span data-stu-id="068d1-153">We will work hard with Software Vendors to address any issues before the release, but in case the fix is not feasible we have other resolutions such as shims and blocks.</span></span>

## <a name="miscellaneous"></a><span data-ttu-id="068d1-154">Diversos</span><span class="sxs-lookup"><span data-stu-id="068d1-154">Miscellaneous</span></span>

<span data-ttu-id="068d1-155">**P: Como o serviço funcionará com um servidor local?**</span><span class="sxs-lookup"><span data-stu-id="068d1-155">**Q: How will the service work with an on-prem server?**</span></span>

<span data-ttu-id="068d1-156">**R:** Atualmente, não fornecemos suporte para servidores no momento.</span><span class="sxs-lookup"><span data-stu-id="068d1-156">**A:** We currently do not provide support for on-prem servers.</span></span> <span data-ttu-id="068d1-157">No entanto, se o servidor estiver expondo o ponto de extremidade HTTP, podemos nos conectar a ele pela Internet.</span><span class="sxs-lookup"><span data-stu-id="068d1-157">However, if the server is exposing HTTP endpoint, we can connect to it over the internet.</span></span>

<span data-ttu-id="068d1-158">**P: Who hospeda as VMs?**</span><span class="sxs-lookup"><span data-stu-id="068d1-158">**Q: Who hosts the VMs?**</span></span>

<span data-ttu-id="068d1-159">**R:** A Microsoft provisiona a VM para esse serviço, assumindo a carga de fazer isso do cliente.</span><span class="sxs-lookup"><span data-stu-id="068d1-159">**A:** Microsoft provisions the VM for this service, taking the load of doing so from the customer.</span></span>

<span data-ttu-id="068d1-160">**P: Esse serviço dá suporte a aplicativos web, móveis ou desktop?**</span><span class="sxs-lookup"><span data-stu-id="068d1-160">**Q: Does this service support web, mobile, or desktop applications?**</span></span>

<span data-ttu-id="068d1-161">**R:** Atualmente, nosso foco está em aplicativos de área de trabalho, no entanto, temos planos de integração de aplicativos Web no futuro, mas não suportamos aplicativos móveis no momento.</span><span class="sxs-lookup"><span data-stu-id="068d1-161">**A:** Currently, our focus is on desktop applications, however, we have plans to onboard web applications in the future, but we do not support mobile applications at this time.</span></span>

<span data-ttu-id="068d1-162">**P: Qual é a diferença entre Test Base e VANP?**</span><span class="sxs-lookup"><span data-stu-id="068d1-162">**Q: What is the difference between Test Base and SUVP?**</span></span>

<span data-ttu-id="068d1-163">**R:** A maior diferença entre a Base de Teste e a VANP é que nossos parceiros integram seus aplicativos no ambiente base de teste do Azure para validação, em vez de realizar os próprios testes.</span><span class="sxs-lookup"><span data-stu-id="068d1-163">**A:** The biggest difference between Test Base and SUVP is that our partners onboard their applications onto the Test Base Azure environment for validation runs against pre-release updates instead of carrying out the tests themselves.</span></span> 

<span data-ttu-id="068d1-164">Além do teste de atualizações de segurança de pré-lançamento, suportamos testes de atualizações de recursos de pré-lançamento em nossa plataforma.</span><span class="sxs-lookup"><span data-stu-id="068d1-164">In addition to pre-release security updates testing, we support pre-release feature updates testing on our platform.</span></span> <span data-ttu-id="068d1-165">Temos muitos outros tipos de atualizações e testes do sistema operacional em nosso roteiro.</span><span class="sxs-lookup"><span data-stu-id="068d1-165">We have many other types of updates and OS testing on our roadmap.</span></span>

<span data-ttu-id="068d1-166">**P: Há um custo associado ao serviço?**</span><span class="sxs-lookup"><span data-stu-id="068d1-166">**Q: Is there a cost associated with the service?**</span></span>

<span data-ttu-id="068d1-167">**R:** O serviço Base de Teste será gratuito para os usuários até a Disponibilidade Geral (GA).</span><span class="sxs-lookup"><span data-stu-id="068d1-167">**A:** The Test Base service will be free to users until General Availability (GA).</span></span> <span data-ttu-id="068d1-168">Nesse momento, anunciaremos uma estrutura de custo que estará em vigor para todos os clientes.</span><span class="sxs-lookup"><span data-stu-id="068d1-168">At that time, we will announce a cost structure that will be in effect for all customers.</span></span> 

<span data-ttu-id="068d1-169">**P: Como posso fornecer comentários sobre a Base de Teste?**</span><span class="sxs-lookup"><span data-stu-id="068d1-169">**Q: How can I provide feedback about Test Base?**</span></span>

<span data-ttu-id="068d1-170">**R:** Para compartilhar seus comentários sobre a Base de Teste, selecione o **ícone Comentários** na parte inferior esquerda do portal.</span><span class="sxs-lookup"><span data-stu-id="068d1-170">**A:** To share your feedback about Test Base, select the **Feedback** icon at the bottom left of the portal.</span></span> <span data-ttu-id="068d1-171">Inclua uma captura de tela com seu envio para ajudar a Microsoft a entender melhor seus comentários.</span><span class="sxs-lookup"><span data-stu-id="068d1-171">Include a screenshot with your submission to help Microsoft better understand your feedback.</span></span> 

<span data-ttu-id="068d1-172">Você também pode enviar sugestões de produto e revogar outras ideias em <testbasepreview@microsoft.com> .</span><span class="sxs-lookup"><span data-stu-id="068d1-172">You can also submit product suggestions and upvote other ideas at <testbasepreview@microsoft.com>.</span></span>
