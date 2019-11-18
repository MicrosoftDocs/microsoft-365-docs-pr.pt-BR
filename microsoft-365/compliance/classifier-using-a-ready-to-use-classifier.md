---
title: Usando um classificador pronto para uso (visualização)
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: A Microsoft 365 vem com uma série de para usar os classificadores de aprendizado de máquina que você pode usar para identificar e rotular o conteúdo em sua organização. Este tópico mostra como se preparar para usar esses classificadores prontos para usar.
ms.openlocfilehash: 3387d8fa91e88ec966e570e8eca339ebaa45fa27
ms.sourcegitcommit: 7c977771fc295ca1e4e9b16a6d05faee8edeadad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "38689986"
---
# <a name="using-a-ready-to-use-classifier-preview"></a><span data-ttu-id="692b1-104">Usando um classificador pronto para uso (visualização)</span><span class="sxs-lookup"><span data-stu-id="692b1-104">Using a ready to use classifier (preview)</span></span>

<span data-ttu-id="692b1-105">A Microsoft treinado e testou o número de classificadores usando conjuntos de dados de amostra muito grandes pode ajudar a identificar determinadas categorias de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="692b1-105">Microsoft has trained and tested number of classifiers using very large sample data sets can help to identify certain categories of content.</span></span> <span data-ttu-id="692b1-106">Confira introdução [aos classificadores estagiários (visualização)](classifier-getting-started-with.md).</span><span class="sxs-lookup"><span data-stu-id="692b1-106">See [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span> <span data-ttu-id="692b1-107">Esses classificadores aparecem no `Ready to use` grupo por padrão.</span><span class="sxs-lookup"><span data-stu-id="692b1-107">These classifiers show up in the `Ready to use` group by default.</span></span>

- <span data-ttu-id="692b1-108">**Linguagem ofensiva**: detecta itens de texto que contêm obscenidades, slurs, taunts e expressões disfarçadas (que são expressões que têm o mesmo significado de um termo mais ofensivo).</span><span class="sxs-lookup"><span data-stu-id="692b1-108">**Offensive Language**: detects text items which contain profanities, slurs, taunts, and disguised expressions (which are expressions that have the same meaning as a more offensive term).</span></span>
- <span data-ttu-id="692b1-109">**Currículos**: detecta itens que são contas de texto das qualificações pessoais, educacionais, profissionais, experiência de trabalho e outras informações de identificação pessoal de um candidato</span><span class="sxs-lookup"><span data-stu-id="692b1-109">**Resumes**: detects items which are textual accounts of an applicant's personal, educational, professional qualifications, work experience and other personally identifying information</span></span>
- <span data-ttu-id="692b1-110">**SourceCode**: detecta itens que contêm um conjunto de instruções e instruções escritas em linguagens de programação de computador amplamente usadas.</span><span class="sxs-lookup"><span data-stu-id="692b1-110">**SourceCode**: detects items which contain a set of instructions and statements written in widely used computer programming languages.</span></span>
- <span data-ttu-id="692b1-111">**Assédio**: detecta uma categoria específica de itens de texto de linguagem ofensiva relacionadas à conduta ofensiva direcionada uma ou várias pessoas com base nas seguintes características: raça, étnica, Religion, origem nacional, sexo, orientação sexual, idade, deficiência.</span><span class="sxs-lookup"><span data-stu-id="692b1-111">**Harassment**: detects a specific category of offensive language text items related to offensive conduct targeting one or multiple individuals based on the following traits: race, ethnicity, religion, national origin, gender, sexual orientation, age, disability.</span></span>
- <span data-ttu-id="692b1-112">**Profanação**: detecta uma categoria específica de itens de texto de idioma ofensivo que contêm expressões que constrangim a maioria das pessoas</span><span class="sxs-lookup"><span data-stu-id="692b1-112">**Profanity**: detects a specific category of offensive language text items which contain expressions that embarrass most people</span></span>
- <span data-ttu-id="692b1-113">**Ameaça**: detecta uma categoria específica de itens de texto de linguagem ofensiva relacionadas a ameaças para confirmar a violência ou danos físicos ou danos a uma pessoa ou a uma propriedade</span><span class="sxs-lookup"><span data-stu-id="692b1-113">**Threat**: detects a specific category of offensive language text items related to threats to commit violence or do physical harm or damage to a person or property</span></span>

> [!NOTE]
> <span data-ttu-id="692b1-114">Antes de usar os classificadores pronto para usar no seu fluxo de trabalho de classificação e rotular, você deve testá-lo em um exemplo de conteúdo da sua organização que você se sente que é a categoria para verificar se suas previsões de classificação atendem às suas expectativas.</span><span class="sxs-lookup"><span data-stu-id="692b1-114">Before using ready to use classifiers in your classification and labeling workflow, you should test it against a sample of your organization's content that you feel fits the category to verify that its classification predictions meet your expectations.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="692b1-115">Observe que a linguagem ofensiva, assédio, profanação e classificadores de ameaças só funcionam com o texto pesquisável não é completo nem completo.</span><span class="sxs-lookup"><span data-stu-id="692b1-115">Please note that the offensive language, harassment, profanity, and threat classifiers only work with searchable text are not exhaustive or complete.</span></span>  <span data-ttu-id="692b1-116">Além disso, os padrões culturais e de idioma mudam continuamente e, em claro, a Microsoft reserva-se o direito de atualizar esses classificadores em seu critério.</span><span class="sxs-lookup"><span data-stu-id="692b1-116">Further, language and cultural standards continually change, and in light of these realities, Microsoft reserves the right to update these classifiers in its discretion.</span></span> <span data-ttu-id="692b1-117">Embora os classificadores possam ajudar sua organização a monitorar o ofensivo e outros idiomas usados, os classificadores não resolvem as conseqüências de tal linguagem e não se destinam a fornecer o único meio de monitoramento ou resposta ao uso de esse idioma.</span><span class="sxs-lookup"><span data-stu-id="692b1-117">While the classifiers may assist your organization in monitoring offensive and other language used, the classifiers do not address consequences of such language and are not intended to provide your organization’s sole means of monitoring or responding to the use of such language.</span></span> <span data-ttu-id="692b1-118">Sua organização, e não a Microsoft ou suas subsidiárias, permanece responsável por todas as decisões relacionadas ao monitoramento, imposição, bloqueio, remoção e retenção de qualquer conteúdo identificado por um classificador treinado.</span><span class="sxs-lookup"><span data-stu-id="692b1-118">Your organization, and not Microsoft or its subsidiaries, remains responsible for all decisions related to monitoring, enforcement, blocking, removal and retention of any content identified by a pre-trained classifier.</span></span>

## <a name="how-to-prepare-for-and-use-a-ready-to-use-classifier"></a><span data-ttu-id="692b1-119">Como preparar e usar um classificador pronto para usar</span><span class="sxs-lookup"><span data-stu-id="692b1-119">How to prepare for and use a ready to use classifier</span></span>

1. <span data-ttu-id="692b1-120">Colete itens de conteúdo de teste descartáveis que você sente que pertencem à categoria do classificador pronto para usar (correspondências positivas) e aqueles que não devem ser incluídos (correspondências negativas) na categoria que você está testando.</span><span class="sxs-lookup"><span data-stu-id="692b1-120">Collect disposable test content items that you feel belong in the category of the ready to use classifier (positive matches) and ones that should not be included (negative matches) in the category you are testing.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="692b1-121">Os itens de exemplo não devem ser criptografados e devem estar em inglês.</span><span class="sxs-lookup"><span data-stu-id="692b1-121">The sample items must not be encrypted and they must be in English.</span></span>

2. <span data-ttu-id="692b1-122">Crie uma pasta dedicada do SharePoint Online, aguarde pelo menos uma hora para a pasta ser adicionada ao índice de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="692b1-122">Create a dedicated SharePoint Online folder, wait at least an hour for the folder to be added to the search index.</span></span> <span data-ttu-id="692b1-123">Anote a URL da pasta.</span><span class="sxs-lookup"><span data-stu-id="692b1-123">Make note of the folder URL.</span></span>

3. <span data-ttu-id="692b1-124">Entre no centro de conformidade da Microsoft 365 com administrador de conformidade ou acesso à função de administrador de segurança e abra **o centro de conformidade** da Microsoft 365 ou a guia**de políticas de gerenciamento de registros (visualização)** > \*\*\*\* do **Centro** > de segurança da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="692b1-124">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Records management (preview)** > **Label policies** tab.</span></span>

4. <span data-ttu-id="692b1-125">Escolha `Auto-apply a label`.</span><span class="sxs-lookup"><span data-stu-id="692b1-125">Choose `Auto-apply a label`.</span></span>

5. <span data-ttu-id="692b1-126">Escolha `Choose a label to auto-apply`.</span><span class="sxs-lookup"><span data-stu-id="692b1-126">Choose `Choose a label to auto-apply`.</span></span>

6. <span data-ttu-id="692b1-127">Escolha `Create new labels` e crie um rótulo para uso apenas com este teste.</span><span class="sxs-lookup"><span data-stu-id="692b1-127">Choose `Create new labels` and create a label for use just with this test.</span></span> <span data-ttu-id="692b1-128">Ao fazer isso, deixe `Retention` definido como desativado.</span><span class="sxs-lookup"><span data-stu-id="692b1-128">When you do this, leave `Retention` set to off.</span></span> <span data-ttu-id="692b1-129">Você não deseja ativar nenhuma retenção ou outras ações.</span><span class="sxs-lookup"><span data-stu-id="692b1-129">You don't want to turn on any retention or other actions.</span></span> <span data-ttu-id="692b1-130">Nesse caso, você usará o uso do rótulo de retenção simplesmente como um rótulo de texto, sem impor qualquer ação.</span><span class="sxs-lookup"><span data-stu-id="692b1-130">In this case, you'll be using using the retention label simply as a text label, without enforcing any actions.</span></span> <span data-ttu-id="692b1-131">Por exemplo, você pode criar um rótulo de retenção chamado "teste de classificador SourceCode" sem ações e, em seguida, aplicar automaticamente esse rótulo de retenção ao conteúdo com o classificador do código-fonte como uma condição.</span><span class="sxs-lookup"><span data-stu-id="692b1-131">For example, you can create a retention label named "SourceCode classifier test" with no actions, and then auto-apply that retention label to content with that has Source code classifier as a condition.</span></span> <span data-ttu-id="692b1-132">Para saber mais sobre a criação de rótulos de retenção, confira [visão geral dos rótulos de retenção](labels.md).</span><span class="sxs-lookup"><span data-stu-id="692b1-132">To learn more about creating retention labels, see [Overview of retention labels](labels.md).</span></span>
  
7. <span data-ttu-id="692b1-133">Escolha `Auto-apply a label` e, `Choose a label to auto-apply`em seguida.</span><span class="sxs-lookup"><span data-stu-id="692b1-133">Choose `Auto-apply a label` and then `Choose a label to auto-apply`.</span></span> <span data-ttu-id="692b1-134">Para saber mais sobre como usar a condição com base em aplicar automaticamente um rótulo, confira [aplicar automaticamente a política de rótulo de retenção com base em uma condição](labels.md#applying-a-retention-label-automatically-based-on-conditions).</span><span class="sxs-lookup"><span data-stu-id="692b1-134">To learn more about using condition based auto-apply a label see, [auto-apply retention label policy based on a condition](labels.md#applying-a-retention-label-automatically-based-on-conditions).</span></span>

8. <span data-ttu-id="692b1-135">Escolha seu rótulo de teste na lista e escolha `Next`.</span><span class="sxs-lookup"><span data-stu-id="692b1-135">Choose your test label from the list and choose `Next`.</span></span>

9. <span data-ttu-id="692b1-136">Escolha `Apply label to content that matches a trainable classifier`.</span><span class="sxs-lookup"><span data-stu-id="692b1-136">Choose `Apply label to content that matches a trainable classifier`.</span></span>

![selecionar classificador como uma condição](media/classifier-pre-trained-apply-label-match-trainable-classifier.png)<span data-ttu-id="692b1-138">.</span><span class="sxs-lookup"><span data-stu-id="692b1-138"></span></span>

10. <span data-ttu-id="692b1-139">Escolha seu classificador na lista, neste caso`Source Code`</span><span class="sxs-lookup"><span data-stu-id="692b1-139">Choose your classifier from the list, in this case `Source Code`</span></span>

11. <span data-ttu-id="692b1-140">Nomeie a política, por exemplo, "código-fonte pronto para usar o teste do classificador".</span><span class="sxs-lookup"><span data-stu-id="692b1-140">Name the policy, for example "Source code ready to use classifier test".</span></span>

12. <span data-ttu-id="692b1-141">Escolha `Let me choose specific locations`.</span><span class="sxs-lookup"><span data-stu-id="692b1-141">Choose `Let me choose specific locations`.</span></span>

13. <span data-ttu-id="692b1-142">Desative todos os locais `SharePoint sites` , exceto `Choose sites`e escolha.</span><span class="sxs-lookup"><span data-stu-id="692b1-142">Turn off all locations except `SharePoint sites` and choose `Choose sites`.</span></span>

14. <span data-ttu-id="692b1-143">Insira a URL do site na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="692b1-143">Enter the URL for the site from step 2.</span></span>

15. <span data-ttu-id="692b1-144">Finalize o assistente e escolha`Auto-apply`</span><span class="sxs-lookup"><span data-stu-id="692b1-144">Finish the wizard and choose `Auto-apply`</span></span>

16. <span data-ttu-id="692b1-145">Coloque os itens de teste na pasta dedicada do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="692b1-145">Place the test items into the dedicated SharePoint Online folder.</span></span>

17. <span data-ttu-id="692b1-146">Permite que uma hora para o rótulo seja aplicada.</span><span class="sxs-lookup"><span data-stu-id="692b1-146">Allow an hour for the label to be applied.</span></span>

18. <span data-ttu-id="692b1-147">Verifique as propriedades dos documentos do rótulo para ver se o classificador incluiu e excluiu o conteúdo de teste conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="692b1-147">Check the properties of the documents for the label to see if the classifier included and excluded the test content as you expected.</span></span>

19. <span data-ttu-id="692b1-148">Revise os itens que foram rotulados.</span><span class="sxs-lookup"><span data-stu-id="692b1-148">Review the items that were labeled .</span></span>

20. <span data-ttu-id="692b1-149">Exclua o conteúdo e a política de etiqueta se você tiver concluído o teste.</span><span class="sxs-lookup"><span data-stu-id="692b1-149">Delete the content, and the label policy if you are done with your testing.</span></span>

<span data-ttu-id="692b1-150">Confira também:</span><span class="sxs-lookup"><span data-stu-id="692b1-150">See also:</span></span>

- [<span data-ttu-id="692b1-151">Introdução aos classificadores de treinamento (visualização)</span><span class="sxs-lookup"><span data-stu-id="692b1-151">Getting started with trainable classifiers (preview)</span></span>](classifier-getting-started-with.md)
- [<span data-ttu-id="692b1-152">Visão geral de rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="692b1-152">Overview of retention labels</span></span>](labels.md)
- [<span data-ttu-id="692b1-153">Aplicar automaticamente a política de rótulo de retenção com base em uma condição</span><span class="sxs-lookup"><span data-stu-id="692b1-153">Auto-apply retention label policy based on a condition</span></span>](labels.md#applying-a-retention-label-automatically-based-on-conditions)