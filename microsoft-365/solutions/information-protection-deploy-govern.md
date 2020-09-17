---
title: Controlar informações sujeitas à regulamentação de privacidade de dados
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
ms.custom: ''
description: Use os rótulos e políticas de retenção da Microsoft 365 para gerenciar dados pessoais no seu ambiente do Microsoft 365.
ms.openlocfilehash: 766995b9c758d4ae8cbf7140fb259d208cfb7771
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949247"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="2b4d8-103">Controlar informações sujeitas à regulamentação de privacidade de dados</span><span class="sxs-lookup"><span data-stu-id="2b4d8-103">Govern information subject to data privacy regulation</span></span>

<span data-ttu-id="2b4d8-104">Os controles de governança de informações podem ser empregados no seu ambiente para ajudar a atender às necessidades de conformidade de privacidade de dados, incluindo um número específico da regulamentação geral de proteção de dados (RGPD), HIPAA-alta (o ato de privacidade do atendimento de saúde dos Estados Unidos), lei de proteção para consumidores da Califórnia (CCPA) e o decreto de proteção de dados Brasil (LGPD).</span><span class="sxs-lookup"><span data-stu-id="2b4d8-104">Information governance controls can be employed in your environment to help address data privacy compliance needs, including a number that are specific to General Data Protection Regulation (GDPR), HIPAA-HITECH (the United States health care privacy act), California Consumer Protection Act (CCPA), and the Brazil Data Protection Act (LGPD).</span></span> 

<span data-ttu-id="2b4d8-105">Esses controles basicamente enquadram-se nas seguintes áreas de solução:</span><span class="sxs-lookup"><span data-stu-id="2b4d8-105">These controls primarily fall into the following solution areas:</span></span>

- <span data-ttu-id="2b4d8-106">Diretivas de retenção</span><span class="sxs-lookup"><span data-stu-id="2b4d8-106">Retention policies</span></span>
- <span data-ttu-id="2b4d8-107">Rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="2b4d8-107">Retention labels</span></span>
- <span data-ttu-id="2b4d8-108">Gerenciamento de registros</span><span class="sxs-lookup"><span data-stu-id="2b4d8-108">Records management</span></span>

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a><span data-ttu-id="2b4d8-109">Regulamentações de privacidade de dados que afetam os controles de governança de informações</span><span class="sxs-lookup"><span data-stu-id="2b4d8-109">Data privacy regulations impacting information governance controls</span></span>

<span data-ttu-id="2b4d8-110">Aqui está uma lista de exemplos de regulamentos de privacidade de dados que podem se relacionar aos controles de governança de informações:</span><span class="sxs-lookup"><span data-stu-id="2b4d8-110">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="2b4d8-111">RGPD artigo (13) (2) (a)</span><span class="sxs-lookup"><span data-stu-id="2b4d8-111">GDPR Article (13)(2)(a)</span></span>
- <span data-ttu-id="2b4d8-112">RGPD artigo (5) (1) (f)</span><span class="sxs-lookup"><span data-stu-id="2b4d8-112">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="2b4d8-113">HIPAA-alta (45 CFR 164.312 (c) (2))</span><span class="sxs-lookup"><span data-stu-id="2b4d8-113">HIPAA-HITECH (45 CFR 164.312(c)(2))</span></span>
- <span data-ttu-id="2b4d8-114">HIPAA-alta (45 CFR 164.316 (b) (1) (i))</span><span class="sxs-lookup"><span data-stu-id="2b4d8-114">HIPAA-HITECH (45 CFR 164.316(b)(1)(i))</span></span>
- <span data-ttu-id="2b4d8-115">HIPAA-alta (45 CFR 164.316 (b) (1) (II))</span><span class="sxs-lookup"><span data-stu-id="2b4d8-115">HIPAA-HITECH (45 CFR 164.316(b)(1)(ii))</span></span>
- <span data-ttu-id="2b4d8-116">LGPD artigo 46</span><span class="sxs-lookup"><span data-stu-id="2b4d8-116">LGPD Article 46</span></span>

<span data-ttu-id="2b4d8-117">Para obter mais informações sobre essas regulamentações, consulte o [artigo sobre como avaliar riscos de privacidade de dados e identificar informações confidenciais](information-protection-deploy-assess.md).</span><span class="sxs-lookup"><span data-stu-id="2b4d8-117">For more information on these regulations, see the [assess data privacy risks and identify sensitive information article](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="2b4d8-118">Para o controle de informações, as regulamentações de privacidade de dados normalmente chamam o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2b4d8-118">For information governance, data privacy regulations typically call for the following:</span></span>

- <span data-ttu-id="2b4d8-119">Você deve empregar um esquema técnico para retenção e exclusão de dados pessoais armazenados no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2b4d8-119">You should employ a technical scheme for retention and deletion for personal data stored in Microsoft 365.</span></span>
- <span data-ttu-id="2b4d8-120">Se você for armazenar dados pessoais, informe o assunto sobre quanto tempo os dados serão armazenados, que é uma prática padrão agora em sistemas Web front-end.</span><span class="sxs-lookup"><span data-stu-id="2b4d8-120">If you're going to store personal data, inform the subject of how long the data will be stored, which is a standard practice now on front-end web systems.</span></span>
- <span data-ttu-id="2b4d8-121">Dados pessoais devem ser protegidos contra processamento acidental, perda ou alteração usando métodos verificáveis.</span><span class="sxs-lookup"><span data-stu-id="2b4d8-121">Personal data should be protected against accidental processing, loss, or alteration using verifiable methods.</span></span>
- <span data-ttu-id="2b4d8-122">Qualquer ação executada em relação a dados pessoais deve ser documentada e essa documentação deve ser mantida por um período especificado.</span><span class="sxs-lookup"><span data-stu-id="2b4d8-122">Any action executed against personal data should be documented and that documentation should be retained for a specified period.</span></span>

<span data-ttu-id="2b4d8-123">Como as leis de privacidade de dados não são muito específicas quando se trata de retenção e exclusão de dados, outros fatores precisam ser levados em consideração que podem ditar as diretrizes de controle de informações para informações pessoais armazenadas na sua assinatura do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2b4d8-123">Because the data privacy regulations are not very specific when it comes to data retention and deletion, other factors need to be taken into consideration that may dictate information governance guidelines for personal information stored in your Microsoft 365 subscription.</span></span> <span data-ttu-id="2b4d8-124">Estes são alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="2b4d8-124">Here are a few examples:</span></span>

- <span data-ttu-id="2b4d8-125">Expirar as contas de consumo após 5 anos de inatividade e requer a exclusão ou a anonimato dos dados da conta após esse ponto, exigindo orquestração entre o sistema que armazena os dados e fluxos de trabalho relacionados a notificações e outras automação.</span><span class="sxs-lookup"><span data-stu-id="2b4d8-125">Aging out consumer accounts after 5 years of inactivity and requires deletion or anonymization of account data after that point, requiring orchestration between the system storing the data and workflows related to notifications and other automation.</span></span>
- <span data-ttu-id="2b4d8-126">Configurar regras para manter políticas e procedimentos relacionados ao RGPD por três anos após terem sido substituídos, que se alinham com o agendamento de retenção da organização para políticas e procedimentos.</span><span class="sxs-lookup"><span data-stu-id="2b4d8-126">Configuring rules for keeping policies and procedures related to GDPR around for three years after they've been superseded, which aligns with the organization's retention schedule for policies and procedures.</span></span>
- <span data-ttu-id="2b4d8-127">Manter uma assinatura separada para comunicação com os consumidores por meio de sua organização de suporte.</span><span class="sxs-lookup"><span data-stu-id="2b4d8-127">Maintaining a separate subscription for communicating with consumers through its support organization.</span></span> <span data-ttu-id="2b4d8-128">Todas as comunicações de email foram mantidas e excluídas após duas semanas para reduzir qualquer dívida de privacidade no sistema.</span><span class="sxs-lookup"><span data-stu-id="2b4d8-128">All email communications were retained and deleted after two weeks to reduce any privacy debt buildup in the system.</span></span>

<span data-ttu-id="2b4d8-129">Uma pergunta importante a ser respondida é:</span><span class="sxs-lookup"><span data-stu-id="2b4d8-129">A key question to answer is:</span></span> 

- <span data-ttu-id="2b4d8-130">Quanto tempo as informações que contêm dados pessoais precisam ser mantidas por razões de negócios válidas para evitar as práticas de "mantê-lo para sempre"?</span><span class="sxs-lookup"><span data-stu-id="2b4d8-130">How long does information containing personal data need to be kept around for valid business reasons to avoid "keep it forever" practices?</span></span> <span data-ttu-id="2b4d8-131">Isso deve ser balanceado com as necessidades de retenção para continuidade de negócios.</span><span class="sxs-lookup"><span data-stu-id="2b4d8-131">This must be balanced with retention needs for business continuity.</span></span>

<span data-ttu-id="2b4d8-132">Independentemente das razões legais e comerciais para manter informações pessoais ou excluí-las, a Microsoft fornece vários recursos para implementar o esquema de governança de dados no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2b4d8-132">Regardless of the legal and business reasons for keeping personal information around or deleting it, Microsoft provides a number of capabilities to implement your data governance scheme in Microsoft 365.</span></span>

## <a name="managing-information-governance-in-microsoft-365"></a><span data-ttu-id="2b4d8-133">Gerenciando o controle de informações no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2b4d8-133">Managing information governance in Microsoft 365</span></span>

<span data-ttu-id="2b4d8-134">Para começar, consulte [gerenciar governança de informações](../compliance/manage-information-governance.md) e [retenção de dados, exclusão e destruição no Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span><span class="sxs-lookup"><span data-stu-id="2b4d8-134">To begin, see [Manage information governance](../compliance/manage-information-governance.md) and [Data Retention, Deletion and Destruction in Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a><span data-ttu-id="2b4d8-135">Desenvolver agendas de retenção de dados para contêineres, emails e conteúdo</span><span class="sxs-lookup"><span data-stu-id="2b4d8-135">Develop data retention schedules for containers, email, and content</span></span>

<span data-ttu-id="2b4d8-136">Lembre-se do seguinte:</span><span class="sxs-lookup"><span data-stu-id="2b4d8-136">Keep the following in mind:</span></span>

- <span data-ttu-id="2b4d8-137">O estabelecimento de um agendamento de retenção de dados para tipos de informações definidos deve ser considerado um pré-requisito para implementar qualquer esquema de retenção ou de exclusão.</span><span class="sxs-lookup"><span data-stu-id="2b4d8-137">Establishing a data retention schedule for defined information types should be considered a prerequisite to implementing any retention or deletion scheme.</span></span>

- <span data-ttu-id="2b4d8-138">Dado o número de tipos de informação que a maioria das organizações considera importantes e os cronogramas de retenção de registros grandes correspondentes que vão junto com eles, a implementação de uma estratégia de retenção de dados e gerenciamento de registros requer planejamento.</span><span class="sxs-lookup"><span data-stu-id="2b4d8-138">Given the number of information types that most organizations consider important and the corresponding large records retention schedules that go along with them, implementing a data retention and records management strategy requires planning.</span></span> 

- <span data-ttu-id="2b4d8-139">A chave para estabelecer uma estratégia de governança de dados efetiva desse tipo é focar nas funções de negócios de prioridade mais alta e os tipos de informações que exigem gerenciamento mais formal.</span><span class="sxs-lookup"><span data-stu-id="2b4d8-139">The key to establishing an effective data governance strategy of this type is to focus on the highest priority business functions and information types that require more formal management.</span></span> <span data-ttu-id="2b4d8-140">Os exemplos são contratos legais, demonstrativos financeiros e documentação de conformidade normativa.</span><span class="sxs-lookup"><span data-stu-id="2b4d8-140">Examples are legal contracts, financial statements, and regulatory compliance documentation.</span></span> <span data-ttu-id="2b4d8-141">Tente evitar ter um agendamento de retenção separado para cada tipo de informação único.</span><span class="sxs-lookup"><span data-stu-id="2b4d8-141">Try to avoid having a separate retention schedule for every single information type.</span></span> <span data-ttu-id="2b4d8-142">Tente utilizar categorias gerais o máximo possível, por exemplo, com agendas de retenção de sete anos para conteúdo de negócios em geral.</span><span class="sxs-lookup"><span data-stu-id="2b4d8-142">Try to utilize general categories as much as possible, for example, with retention schedules of 7 years for general business content.</span></span>

- <span data-ttu-id="2b4d8-143">Depois que os tipos de informações pessoais no ambiente são mais conhecidos, estabeleça agendas de retenção e exclusão para esse tipo de conteúdo e ajuste sua arquitetura de informações para facilitar a governança desse tipo de informação.</span><span class="sxs-lookup"><span data-stu-id="2b4d8-143">Once the personal information types in your environment are better known, establish retention and deletion schedules for this type of content and adjust your information architecture to make governance of this sort of information easier.</span></span> <span data-ttu-id="2b4d8-144">Por exemplo, isole informações pessoais em sites, bibliotecas ou pastas separadas com acesso controlado.</span><span class="sxs-lookup"><span data-stu-id="2b4d8-144">For example, isolate personal information in separate sites, libraries, or folders with controlled access.</span></span>

### <a name="retention-policies-and-retention-labels"></a><span data-ttu-id="2b4d8-145">Políticas de retenção e rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="2b4d8-145">Retention policies and retention labels</span></span>

<span data-ttu-id="2b4d8-146">Use [as políticas de retenção e os rótulos de retenção](../compliance/retention.md) para reter ou excluir o conteúdo no Microsoft 365 que contém ou deve conter dados pessoais.</span><span class="sxs-lookup"><span data-stu-id="2b4d8-146">Use [retention policies and retention labels](../compliance/retention.md) to retain or delete content in Microsoft 365 that contains or is expected to contain personal data.</span></span>

### <a name="records-management"></a><span data-ttu-id="2b4d8-147">Gerenciamento de registros</span><span class="sxs-lookup"><span data-stu-id="2b4d8-147">Records management</span></span>

<span data-ttu-id="2b4d8-148">Use rótulos de retenção que declarem o conteúdo um registro para implementar uma [solução de gerenciamento de registros](../compliance/records-management.md) para dados no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2b4d8-148">Use retention labels that declare content a record to implement a [records management solution](../compliance/records-management.md) for data in Microsoft 365.</span></span>

<span data-ttu-id="2b4d8-149">Para a privacidade dos dados, as solicitações de entidades de dados (DSRs) recebidas pelo departamento jurídico são declaradas como um registro e podem ser armazenadas indefinidamente ou descartadas com provas, para cumprir as especificações de retenção de atividade regulamentar.</span><span class="sxs-lookup"><span data-stu-id="2b4d8-149">For data privacy, data subject requests (DSRs) received by the legal department are declared a record and can be stored indefinitely or disposed of with proof, to adhere to regulatory activity retention specifications.</span></span>

