---
title: Governe informações sujeitas à regulamentação de privacidade de dados
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Use rótulos e políticas de retenção do Microsoft 365 para gerenciar dados pessoais em seu ambiente do Microsoft 365.
ms.openlocfilehash: 62c2386ac8f9c5b31650df8be2c2a411d8b75959
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928431"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="9e3f6-103">Governe informações sujeitas à regulamentação de privacidade de dados</span><span class="sxs-lookup"><span data-stu-id="9e3f6-103">Govern information subject to data privacy regulation</span></span>

<span data-ttu-id="9e3f6-104">Os controles de governança de informações podem ser empregados em seu ambiente para ajudar a atender às necessidades de conformidade de privacidade de dados, incluindo um número específico do RGPD (Regulamento Geral de Proteção de Dados), HIPAA-HITECH (a lei de privacidade de saúde dos Estados Unidos), a Lei de Proteção do Consumidor da Califórnia (CCPA) e a Lei de Proteção de Dados do Brasil (LGPD).</span><span class="sxs-lookup"><span data-stu-id="9e3f6-104">Information governance controls can be employed in your environment to help address data privacy compliance needs, including a number that are specific to General Data Protection Regulation (GDPR), HIPAA-HITECH (the United States health care privacy act), California Consumer Protection Act (CCPA), and the Brazil Data Protection Act (LGPD).</span></span> 

<span data-ttu-id="9e3f6-105">Esses controles se enquadram principalmente nas seguintes áreas de solução:</span><span class="sxs-lookup"><span data-stu-id="9e3f6-105">These controls primarily fall into the following solution areas:</span></span>

- <span data-ttu-id="9e3f6-106">Diretivas de retenção</span><span class="sxs-lookup"><span data-stu-id="9e3f6-106">Retention policies</span></span>
- <span data-ttu-id="9e3f6-107">Rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="9e3f6-107">Retention labels</span></span>
- <span data-ttu-id="9e3f6-108">Gerenciamento de registros</span><span class="sxs-lookup"><span data-stu-id="9e3f6-108">Records management</span></span>

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a><span data-ttu-id="9e3f6-109">Regulamentos de privacidade de dados que impactam controles de governança de informações</span><span class="sxs-lookup"><span data-stu-id="9e3f6-109">Data privacy regulations impacting information governance controls</span></span>

<span data-ttu-id="9e3f6-110">Aqui está um exemplo de listagem de regulamentos de privacidade de dados que podem estar relacionados aos controles de governança de informações:</span><span class="sxs-lookup"><span data-stu-id="9e3f6-110">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="9e3f6-111">Artigo RGPD (13)(2)(a)</span><span class="sxs-lookup"><span data-stu-id="9e3f6-111">GDPR Article (13)(2)(a)</span></span>
- <span data-ttu-id="9e3f6-112">Artigo RGPD (5)(1)(f)</span><span class="sxs-lookup"><span data-stu-id="9e3f6-112">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="9e3f6-113">HIPAA-HITECH (45 CFR 164.312(c)(2))</span><span class="sxs-lookup"><span data-stu-id="9e3f6-113">HIPAA-HITECH (45 CFR 164.312(c)(2))</span></span>
- <span data-ttu-id="9e3f6-114">HIPAA-HITECH (45 CFR 164.316(b)(1)(i))</span><span class="sxs-lookup"><span data-stu-id="9e3f6-114">HIPAA-HITECH (45 CFR 164.316(b)(1)(i))</span></span>
- <span data-ttu-id="9e3f6-115">HIPAA-HITECH (45 CFR 164.316(b)(1)(ii))</span><span class="sxs-lookup"><span data-stu-id="9e3f6-115">HIPAA-HITECH (45 CFR 164.316(b)(1)(ii))</span></span>
- <span data-ttu-id="9e3f6-116">Artigo 46 do LGPD</span><span class="sxs-lookup"><span data-stu-id="9e3f6-116">LGPD Article 46</span></span>

<span data-ttu-id="9e3f6-117">Para obter mais informações sobre esses regulamentos, consulte o artigo avaliar riscos de privacidade de dados e [identificar informações confidenciais.](information-protection-deploy-assess.md)</span><span class="sxs-lookup"><span data-stu-id="9e3f6-117">For more information on these regulations, see the [assess data privacy risks and identify sensitive information article](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="9e3f6-118">Para governança de informações, os regulamentos de privacidade de dados normalmente chamam o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9e3f6-118">For information governance, data privacy regulations typically call for the following:</span></span>

- <span data-ttu-id="9e3f6-119">Você deve empregar um esquema técnico para retenção e exclusão de dados pessoais armazenados no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9e3f6-119">You should employ a technical scheme for retention and deletion for personal data stored in Microsoft 365.</span></span>
- <span data-ttu-id="9e3f6-120">Se você vai armazenar dados pessoais, informe o assunto de quanto tempo os dados serão armazenados, que é uma prática padrão agora em sistemas Web front-end.</span><span class="sxs-lookup"><span data-stu-id="9e3f6-120">If you're going to store personal data, inform the subject of how long the data will be stored, which is a standard practice now on front-end web systems.</span></span>
- <span data-ttu-id="9e3f6-121">Os dados pessoais devem ser protegidos contra processamento acidental, perda ou alteração usando métodos verificáveis.</span><span class="sxs-lookup"><span data-stu-id="9e3f6-121">Personal data should be protected against accidental processing, loss, or alteration using verifiable methods.</span></span>
- <span data-ttu-id="9e3f6-122">Qualquer ação executada contra dados pessoais deve ser documentada e essa documentação deve ser mantida por um período especificado.</span><span class="sxs-lookup"><span data-stu-id="9e3f6-122">Any action executed against personal data should be documented and that documentation should be retained for a specified period.</span></span>

<span data-ttu-id="9e3f6-123">Como os regulamentos de privacidade de dados não são muito específicos quando se trata de retenção e exclusão de dados, outros fatores precisam ser considerados que podem ditar diretrizes de governança de informações para informações pessoais armazenadas em sua assinatura do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9e3f6-123">Because the data privacy regulations are not very specific when it comes to data retention and deletion, other factors need to be taken into consideration that may dictate information governance guidelines for personal information stored in your Microsoft 365 subscription.</span></span> <span data-ttu-id="9e3f6-124">Veja alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="9e3f6-124">Here are a few examples:</span></span>

- <span data-ttu-id="9e3f6-125">O apagamento das contas de consumidor após 5 anos de inatividade e requer exclusão ou anonimização dos dados da conta após esse ponto, exigindo a orquestração entre o sistema que armazenará os dados e fluxos de trabalho relacionados a notificações e outras automações.</span><span class="sxs-lookup"><span data-stu-id="9e3f6-125">Aging out consumer accounts after 5 years of inactivity and requires deletion or anonymization of account data after that point, requiring orchestration between the system storing the data and workflows related to notifications and other automation.</span></span>
- <span data-ttu-id="9e3f6-126">Configurar regras para manter políticas e procedimentos relacionados ao RGPD por três anos após a superação, que se alinha ao cronograma de retenção da organização para políticas e procedimentos.</span><span class="sxs-lookup"><span data-stu-id="9e3f6-126">Configuring rules for keeping policies and procedures related to GDPR around for three years after they've been superseded, which aligns with the organization's retention schedule for policies and procedures.</span></span>
- <span data-ttu-id="9e3f6-127">Mantendo uma assinatura separada para se comunicar com os consumidores por meio de sua organização de suporte.</span><span class="sxs-lookup"><span data-stu-id="9e3f6-127">Maintaining a separate subscription for communicating with consumers through its support organization.</span></span> <span data-ttu-id="9e3f6-128">Todas as comunicações de email foram mantidas e excluídas após duas semanas para reduzir qualquer acúmulo de dívidas de privacidade no sistema.</span><span class="sxs-lookup"><span data-stu-id="9e3f6-128">All email communications were retained and deleted after two weeks to reduce any privacy debt buildup in the system.</span></span>

<span data-ttu-id="9e3f6-129">Uma pergunta importante a ser respondeda é:</span><span class="sxs-lookup"><span data-stu-id="9e3f6-129">A key question to answer is:</span></span> 

- <span data-ttu-id="9e3f6-130">Por quanto tempo as informações que contêm dados pessoais precisam ser mantidas por motivos comerciais válidos para evitar práticas de "mantê-los para sempre"?</span><span class="sxs-lookup"><span data-stu-id="9e3f6-130">How long does information containing personal data need to be kept around for valid business reasons to avoid "keep it forever" practices?</span></span> <span data-ttu-id="9e3f6-131">Isso deve ser balanceado com as necessidades de retenção para a continuidade dos negócios.</span><span class="sxs-lookup"><span data-stu-id="9e3f6-131">This must be balanced with retention needs for business continuity.</span></span>

<span data-ttu-id="9e3f6-132">Independentemente dos motivos legais e comerciais para manter informações pessoais ou excluí-los, a Microsoft fornece vários recursos para implementar seu esquema de governança de dados no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9e3f6-132">Regardless of the legal and business reasons for keeping personal information around or deleting it, Microsoft provides a number of capabilities to implement your data governance scheme in Microsoft 365.</span></span>

## <a name="managing-information-governance-in-microsoft-365"></a><span data-ttu-id="9e3f6-133">Gerenciando a governança de informações no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9e3f6-133">Managing information governance in Microsoft 365</span></span>

<span data-ttu-id="9e3f6-134">Para começar, consulte [Manage information governance and](../compliance/manage-information-governance.md) Data [Retention, Deletion and Destruction in Microsoft 365](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span><span class="sxs-lookup"><span data-stu-id="9e3f6-134">To begin, see [Manage information governance](../compliance/manage-information-governance.md) and [Data Retention, Deletion and Destruction in Microsoft 365](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a><span data-ttu-id="9e3f6-135">Desenvolver agendamentos de retenção de dados para contêineres, email e conteúdo</span><span class="sxs-lookup"><span data-stu-id="9e3f6-135">Develop data retention schedules for containers, email, and content</span></span>

<span data-ttu-id="9e3f6-136">Lembre-se do seguinte:</span><span class="sxs-lookup"><span data-stu-id="9e3f6-136">Keep the following in mind:</span></span>

- <span data-ttu-id="9e3f6-137">O estabelecimento de um cronograma de retenção de dados para tipos de informações definidos deve ser considerado um pré-requisito para implementar qualquer esquema de retenção ou exclusão.</span><span class="sxs-lookup"><span data-stu-id="9e3f6-137">Establishing a data retention schedule for defined information types should be considered a prerequisite to implementing any retention or deletion scheme.</span></span>

- <span data-ttu-id="9e3f6-138">Dado o número de tipos de informações que a maioria das organizações considera importantes e os agendamentos de retenção de registros grandes correspondentes que acompanham eles, implementar uma estratégia de gerenciamento de registros e retenção de dados requer planejamento.</span><span class="sxs-lookup"><span data-stu-id="9e3f6-138">Given the number of information types that most organizations consider important and the corresponding large records retention schedules that go along with them, implementing a data retention and records management strategy requires planning.</span></span> 

- <span data-ttu-id="9e3f6-139">A chave para estabelecer uma estratégia eficaz de governança de dados desse tipo é se concentrar nas funções comerciais de maior prioridade e nos tipos de informações que exigem gerenciamento mais formal.</span><span class="sxs-lookup"><span data-stu-id="9e3f6-139">The key to establishing an effective data governance strategy of this type is to focus on the highest priority business functions and information types that require more formal management.</span></span> <span data-ttu-id="9e3f6-140">Exemplos são contratos legais, demonstrações financeiras e documentação de conformidade regulamentar.</span><span class="sxs-lookup"><span data-stu-id="9e3f6-140">Examples are legal contracts, financial statements, and regulatory compliance documentation.</span></span> <span data-ttu-id="9e3f6-141">Tente evitar ter um cronograma de retenção separado para cada tipo de informação.</span><span class="sxs-lookup"><span data-stu-id="9e3f6-141">Try to avoid having a separate retention schedule for every single information type.</span></span> <span data-ttu-id="9e3f6-142">Tente utilizar categorias gerais o máximo possível, por exemplo, com agendamentos de retenção de 7 anos para conteúdo comercial geral.</span><span class="sxs-lookup"><span data-stu-id="9e3f6-142">Try to utilize general categories as much as possible, for example, with retention schedules of 7 years for general business content.</span></span>

- <span data-ttu-id="9e3f6-143">Depois que os tipos de informações pessoais em seu ambiente são mais conhecidos, estabeleça cronogramas de retenção e exclusão para esse tipo de conteúdo e ajuste sua arquitetura de informações para facilitar a governança desse tipo de informação.</span><span class="sxs-lookup"><span data-stu-id="9e3f6-143">Once the personal information types in your environment are better known, establish retention and deletion schedules for this type of content and adjust your information architecture to make governance of this sort of information easier.</span></span> <span data-ttu-id="9e3f6-144">Por exemplo, isole informações pessoais em sites, bibliotecas ou pastas separados com acesso controlado.</span><span class="sxs-lookup"><span data-stu-id="9e3f6-144">For example, isolate personal information in separate sites, libraries, or folders with controlled access.</span></span>

### <a name="retention-policies-and-retention-labels"></a><span data-ttu-id="9e3f6-145">Políticas de retenção e rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="9e3f6-145">Retention policies and retention labels</span></span>

<span data-ttu-id="9e3f6-146">Use [políticas de retenção e rótulos](../compliance/retention.md) de retenção para reter ou excluir conteúdo no Microsoft 365 que contém ou deve conter dados pessoais.</span><span class="sxs-lookup"><span data-stu-id="9e3f6-146">Use [retention policies and retention labels](../compliance/retention.md) to retain or delete content in Microsoft 365 that contains or is expected to contain personal data.</span></span>

### <a name="records-management"></a><span data-ttu-id="9e3f6-147">Gerenciamento de registros</span><span class="sxs-lookup"><span data-stu-id="9e3f6-147">Records management</span></span>

<span data-ttu-id="9e3f6-148">Use rótulos de retenção que declarem um registro de conteúdo para implementar [uma](../compliance/records-management.md) solução de gerenciamento de registros para dados no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9e3f6-148">Use retention labels that declare content a record to implement a [records management solution](../compliance/records-management.md) for data in Microsoft 365.</span></span>

<span data-ttu-id="9e3f6-149">Para privacidade de dados, as solicitações de entidades de dados (DSRs) recebidas pelo departamento jurídico são declaradas um registro e podem ser armazenadas indefinidamente ou descartadas com prova, para aderir às especificações de retenção de atividades regulamentares.</span><span class="sxs-lookup"><span data-stu-id="9e3f6-149">For data privacy, data subject requests (DSRs) received by the legal department are declared a record and can be stored indefinitely or disposed of with proof, to adhere to regulatory activity retention specifications.</span></span>