---
title: Recomendações de política de senha
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9fa2539a-2211-41fd-85a0-bc37b9619ca4
description: Aprenda a tornar a sua organização mais segura contra ataques de senha e por que você deve bloquear senhas comuns e habilitar a autenticação multifator baseada em risco.
ms.openlocfilehash: d3f86a6e85ab2f8e469a57ea98a661e4cc453673
ms.sourcegitcommit: 9063c7a50a1d7dd6d2e1ca44f53d3c26f21f4ae8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2021
ms.locfileid: "52073860"
---
# <a name="password-policy-recommendations"></a><span data-ttu-id="69b98-103">Recomendações de política de senha</span><span class="sxs-lookup"><span data-stu-id="69b98-103">Password policy recommendations</span></span>

<span data-ttu-id="69b98-104">Como administrador de uma organização, você é responsável por definir a política de senha para usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="69b98-104">As the admin of an organization, you're responsible for setting password policy for users in your organization.</span></span> <span data-ttu-id="69b98-105">Definir a política de senha pode ser complicado e confuso, e este artigo fornece recomendações para tornar a sua organização mais segura contra ataques de senha.</span><span class="sxs-lookup"><span data-stu-id="69b98-105">Setting password policy can be complicated and confusing, and this article provides recommendations to make your organization more secure against password attacks.</span></span>
  
<span data-ttu-id="69b98-106">Para determinar a frequência com que as senhas do Microsoft 365 expiram em sua organização, confira [Definir política de expiração de senha para o Office 365](../manage/set-password-expiration-policy.md).</span><span class="sxs-lookup"><span data-stu-id="69b98-106">To determine how often Microsoft 365 passwords expire in your organization, see [Set password expiration policy for Microsoft 365](../manage/set-password-expiration-policy.md).</span></span>

<span data-ttu-id="69b98-107">Para obter mais informações sobre senhas do Microsoft 365, consulte:</span><span class="sxs-lookup"><span data-stu-id="69b98-107">For more information about Microsoft 365 passwords, see:</span></span>

<span data-ttu-id="69b98-108">[Redefinir senhas](../add-users/reset-passwords.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="69b98-108">[Reset passwords](../add-users/reset-passwords.md) (article)</span></span>

<span data-ttu-id="69b98-109">[Definir a senha de um usuário individual para nunca expirar](../add-users/set-password-to-never-expire.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="69b98-109">[Set an individual user's password to never expire](../add-users/set-password-to-never-expire.md) (artice)</span></span>

<span data-ttu-id="69b98-110">[Permitir aos usuários redefinir suas próprias senhas](../add-users/let-users-reset-passwords.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="69b98-110">[Let users reset their own passwords](../add-users/let-users-reset-passwords.md) (article)</span></span>

<span data-ttu-id="69b98-111">[Reenviar a senha de um usuário - Ajuda do Administrador](../add-users/resend-user-password.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="69b98-111">[Resend a user's password - Admin Help](../add-users/resend-user-password.md) (article)</span></span>
  
## <a name="understanding-password-recommendations"></a><span data-ttu-id="69b98-112">Compreendendo as recomendações de senha</span><span class="sxs-lookup"><span data-stu-id="69b98-112">Understanding password recommendations</span></span>

<span data-ttu-id="69b98-113">As boas práticas de senha se enquadram em algumas categorias amplas:</span><span class="sxs-lookup"><span data-stu-id="69b98-113">Good password practices fall into a few broad categories:</span></span>
  
- <span data-ttu-id="69b98-114">**Resistir a ataques comuns** Isso envolve a escolha de onde os usuários inserem senhas (dispositivos conhecidos e confiáveis com boa detecção de malware, sites validados) e a escolha de qual senha escolher (comprimento e exclusividade).</span><span class="sxs-lookup"><span data-stu-id="69b98-114">**Resisting common attacks** This involves the choice of where users enter passwords (known and trusted devices with good malware detection, validated sites), and the choice of what password to choose (length and uniqueness).</span></span>

- <span data-ttu-id="69b98-115">**Conter ataques bem-sucedidos** Conter ataques de hackers bem-sucedidas consiste em limitar a exposição a um serviço específico ou impedir completamente esse dano, se a senha de um usuário for roubada.</span><span class="sxs-lookup"><span data-stu-id="69b98-115">**Containing successful attacks** Containing successful hacker attacks is about limiting exposure to a specific service, or preventing that damage altogether, if a user's password gets stolen.</span></span> <span data-ttu-id="69b98-116">Por exemplo, garantir que uma violação de suas credenciais de rede social não torne sua conta bancária vulnerável ou não permita que uma conta mal protegida aceite links de redefinição para uma conta importante.</span><span class="sxs-lookup"><span data-stu-id="69b98-116">For example, ensuring that a breach of your social networking credentials doesn't make your bank account vulnerable, or not letting a poorly guarded account accept reset links for an important account.</span></span>

- <span data-ttu-id="69b98-117">**Noções básicas sobre a natureza humana** Muitas práticas válidas de senha falham diante dos comportamentos humanos naturais.</span><span class="sxs-lookup"><span data-stu-id="69b98-117">**Understanding human nature** Many valid password practices fail in the face of natural human behaviors.</span></span> <span data-ttu-id="69b98-118">Entender a natureza humana é fundamental porque a pesquisa mostra que quase todas as regras que você impõe aos usuários resultam em um enfraquecimento da qualidade da senha.</span><span class="sxs-lookup"><span data-stu-id="69b98-118">Understanding human nature is critical because research shows that almost every rule you impose on your users will result in a weakening of password quality.</span></span> <span data-ttu-id="69b98-119">Requisitos de comprimento, requisitos especiais de caracteres e requisitos de alteração de senha resultam na normalização de senhas, o que facilita para os invasores adivinharem ou decifrarem senhas.</span><span class="sxs-lookup"><span data-stu-id="69b98-119">Length requirements, special character requirements, and password change requirements all result in normalization of passwords, which makes it easier for attackers to guess or crack passwords.</span></span>

## <a name="password-guidelines-for-administrators"></a><span data-ttu-id="69b98-120">Diretrizes de senha para administradores</span><span class="sxs-lookup"><span data-stu-id="69b98-120">Password guidelines for administrators</span></span>

<span data-ttu-id="69b98-121">O principal objetivo de um sistema de senhas mais seguro é a diversidade de senhas.</span><span class="sxs-lookup"><span data-stu-id="69b98-121">The primary goal of a more secure password system is password diversity.</span></span> <span data-ttu-id="69b98-122">Você quer que sua política de senha contenha várias senhas diferentes e difíceis de adivinhar.</span><span class="sxs-lookup"><span data-stu-id="69b98-122">You want your password policy to contain lots of different and hard to guess passwords.</span></span> <span data-ttu-id="69b98-123">Aqui estão algumas recomendações para manter sua organização o mais segura possível.</span><span class="sxs-lookup"><span data-stu-id="69b98-123">Here are a few recommendations for keeping your organization as secure as possible.</span></span>
  
- <span data-ttu-id="69b98-124">Manter um requisito de comprimento mínimo de 8 caracteres (maior não é necessariamente melhor)</span><span class="sxs-lookup"><span data-stu-id="69b98-124">Maintain an 8-character minimum length requirement (longer isn't necessarily better)</span></span>

- <span data-ttu-id="69b98-125">Não exigir requisitos de composição de caracteres.</span><span class="sxs-lookup"><span data-stu-id="69b98-125">Don't require character composition requirements.</span></span> <span data-ttu-id="69b98-126">Por exemplo, \*&amp;(^%$</span><span class="sxs-lookup"><span data-stu-id="69b98-126">For example, \*&amp;(^%$</span></span>

- <span data-ttu-id="69b98-127">Não exigir redefinições de senha periódicas obrigatórias para contas de usuários</span><span class="sxs-lookup"><span data-stu-id="69b98-127">Don't require mandatory periodic password resets for user accounts</span></span>

- <span data-ttu-id="69b98-128">Proíba senhas comuns, para evitar senhas mais vulneráveis no seu sistema</span><span class="sxs-lookup"><span data-stu-id="69b98-128">Ban common passwords, to keep the most vulnerable passwords out of your system</span></span>

- <span data-ttu-id="69b98-129">Instrua seus usuários para não reutilizarem as senhas da organização para fins não relacionados ao trabalho</span><span class="sxs-lookup"><span data-stu-id="69b98-129">Educate your users to not re-use their organization passwords for non-work related purposes</span></span>

- <span data-ttu-id="69b98-130">Impor registro para [autenticação multifator](../security-and-compliance/set-up-multi-factor-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="69b98-130">Enforce registration for [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md)</span></span>

- <span data-ttu-id="69b98-131">Ativar desafios de autenticação multifator baseados em risco</span><span class="sxs-lookup"><span data-stu-id="69b98-131">Enable risk-based multi-factor authentication challenges</span></span>

### <a name="password-guidance-for-your-users"></a><span data-ttu-id="69b98-132">Diretrizes de senha para os seus usuários</span><span class="sxs-lookup"><span data-stu-id="69b98-132">Password guidance for your users</span></span>

<span data-ttu-id="69b98-133">Aqui estão algumas diretrizes de senha para usuários da sua organização.</span><span class="sxs-lookup"><span data-stu-id="69b98-133">Here's some password guidance for users in your organization.</span></span> <span data-ttu-id="69b98-134">Lembre-se de permitir que seus usuários saibam sobre essas recomendações e aplicar as políticas de senha recomendadas no nível da organização.</span><span class="sxs-lookup"><span data-stu-id="69b98-134">Make sure to let your users know about these recommendations and enforce the recommended password policies at the organizational level.</span></span>
  
- <span data-ttu-id="69b98-135">Não use uma senha igual ou similar a uma que você usa em outros sites</span><span class="sxs-lookup"><span data-stu-id="69b98-135">Don't use a password that is the same or similar to one you use on any other websites</span></span>

- <span data-ttu-id="69b98-136">Não use uma única palavra, por exemplo, **senha** ou uma frase habitualmente utilizada com **euamovocê**</span><span class="sxs-lookup"><span data-stu-id="69b98-136">Don't use a single word, for example, **password**, or a commonly-used phrase like **Iloveyou**</span></span>

- <span data-ttu-id="69b98-137">Torne as senhas difíceis de adivinhar, mesmo para quem sabe muito sobre você, como nomes e aniversários de seus amigos e familiares, suas bandas favoritas e frases que você gosta de usar</span><span class="sxs-lookup"><span data-stu-id="69b98-137">Make passwords hard to guess, even by those who know a lot about you, such as the names and birthdays of your friends and family, your favorite bands, and phrases you like to use</span></span>

## <a name="some-common-approaches-and-their-negative-impacts"></a><span data-ttu-id="69b98-138">Algumas abordagens comuns e seus impactos negativos</span><span class="sxs-lookup"><span data-stu-id="69b98-138">Some common approaches and their negative impacts</span></span>

<span data-ttu-id="69b98-139">Essas são algumas das práticas de gerenciamento de senhas mais usadas, mas a pesquisa nos alerta sobre seus impactos negativos.</span><span class="sxs-lookup"><span data-stu-id="69b98-139">These are some of the most commonly used password management practices, but research warns us about the negative impacts of them.</span></span>
  
### <a name="password-expiration-requirements-for-users"></a><span data-ttu-id="69b98-140">Requisitos de expiração de senha para usuários</span><span class="sxs-lookup"><span data-stu-id="69b98-140">Password expiration requirements for users</span></span>

<span data-ttu-id="69b98-141">Os requisitos de expiração de senha causam mais danos do que bem, porque fazem com que os usuários selecionem senhas previsíveis, compostas por palavras e números sequenciais intimamente relacionados entre si.</span><span class="sxs-lookup"><span data-stu-id="69b98-141">Password expiration requirements do more harm than good, because these requirements make users select predictable passwords, composed of sequential words and numbers which are closely related to each other.</span></span> <span data-ttu-id="69b98-142">Nesses casos, a próxima senha poderá ser prevista com base na senha anterior.</span><span class="sxs-lookup"><span data-stu-id="69b98-142">In these cases, the next password can be predicted based on the previous password.</span></span> <span data-ttu-id="69b98-143">Os requisitos de expiração de senha não oferecem benefícios de contenção, porque os cibercriminosos quase sempre usam credenciais assim que os comprometem.</span><span class="sxs-lookup"><span data-stu-id="69b98-143">Password expiration requirements offer no containment benefits because cyber criminals almost always use credentials as soon as they compromise them.</span></span> <span data-ttu-id="69b98-144">Confira [Hora de repensar as alterações de senha obrigatórias](https://go.microsoft.com/fwlink/p/?linkid=861018) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="69b98-144">Check out [Time to rethink mandatory password changes](https://go.microsoft.com/fwlink/p/?linkid=861018) for more info.</span></span>
  
### <a name="requiring-long-passwords"></a><span data-ttu-id="69b98-145">Exigir senhas longas</span><span class="sxs-lookup"><span data-stu-id="69b98-145">Requiring long passwords</span></span>

<span data-ttu-id="69b98-146">Os requisitos de tamanho da senha (maiores que cerca de 10 caracteres) podem resultar em comportamento do usuário previsível e indesejável.</span><span class="sxs-lookup"><span data-stu-id="69b98-146">Password length requirements (greater than about 10 characters) can result in user behavior that is predictable and undesirable.</span></span> <span data-ttu-id="69b98-147">Por exemplo, os usuários que precisam ter uma senha de 16 caracteres podem escolher padrões de repetição como **quatroquatroquatroquatro** ou **senhasenha** que atendem aos requisitos de comprimento de caractere, mas não são difíceis de adivinhar.</span><span class="sxs-lookup"><span data-stu-id="69b98-147">For example, users who are required to have a 16-character password may choose repeating patterns like **fourfourfourfour** or **passwordpassword** that meet the character length requirement but aren't hard to guess.</span></span> <span data-ttu-id="69b98-148">Além disso, os requisitos de tamanho aumentam as chances de os usuários adotar outras práticas inseguras, como anotar suas senhas, reutilizá-las ou armazená-las descriptografadas em seus documentos.</span><span class="sxs-lookup"><span data-stu-id="69b98-148">Additionally, length requirements increase the chances that users will adopt other insecure practices, such as writing their passwords down, re-using them, or storing them unencrypted in their documents.</span></span> <span data-ttu-id="69b98-149">Para incentivar os usuários a pensar em uma senha exclusiva, recomendamos manter um requisito de comprimento mínimo de 8 caracteres.</span><span class="sxs-lookup"><span data-stu-id="69b98-149">To encourage users to think about a unique password, we recommend keeping a reasonable 8-character minimum length requirement.</span></span>
  
### <a name="requiring-the-use-of-multiple-character-sets"></a><span data-ttu-id="69b98-150">Exigir o uso de vários conjuntos de caracteres</span><span class="sxs-lookup"><span data-stu-id="69b98-150">Requiring the use of multiple character sets</span></span>

<span data-ttu-id="69b98-151">Os requisitos de complexidade de senha reduzem o espaço principal e fazem com que os usuários ajam de maneiras previsíveis, causando mais danos do que bem.</span><span class="sxs-lookup"><span data-stu-id="69b98-151">Password complexity requirements reduce key space and cause users to act in predictable ways, doing more harm than good.</span></span> <span data-ttu-id="69b98-152">A maioria dos sistemas aplica alguns níveis de requisitos de complexidade de senha.</span><span class="sxs-lookup"><span data-stu-id="69b98-152">Most systems enforce some level of password complexity requirements.</span></span> <span data-ttu-id="69b98-153">Por exemplo, as senhas precisam ter caracteres das três categorias a seguir:</span><span class="sxs-lookup"><span data-stu-id="69b98-153">For example, passwords need characters from all three of the following categories:</span></span>
  
- <span data-ttu-id="69b98-154">caracteres maiúsculos</span><span class="sxs-lookup"><span data-stu-id="69b98-154">uppercase characters</span></span>

- <span data-ttu-id="69b98-155">caracteres minúsculos</span><span class="sxs-lookup"><span data-stu-id="69b98-155">lowercase characters</span></span>

- <span data-ttu-id="69b98-156">caracteres não alfanuméricos</span><span class="sxs-lookup"><span data-stu-id="69b98-156">non-alphanumeric characters</span></span>

<span data-ttu-id="69b98-157">A maioria das pessoas usa padrões semelhantes, por exemplo, uma letra maiúscula na primeira posição, um símbolo na última e um número na última 2.</span><span class="sxs-lookup"><span data-stu-id="69b98-157">Most people use similar patterns, for example, a capital letter in the first position, a symbol in the last, and a number in the last 2.</span></span> <span data-ttu-id="69b98-158">Os cibercriminosos sabem disso, então executam seus ataques de dicionário usando as substituições mais comuns, "$" para "s", "@" para "a", "1" para "l".</span><span class="sxs-lookup"><span data-stu-id="69b98-158">Cyber criminals know this, so they run their dictionary attacks using the most common substitutions, "$" for "s", "@" for "a," "1" for "l".</span></span> <span data-ttu-id="69b98-159">Forçar seus usuários a escolher uma combinação de caracteres maiúsculos e minúsculos, dígitos, caracteres especiais têm um efeito negativo.</span><span class="sxs-lookup"><span data-stu-id="69b98-159">Forcing your users to choose a combination of upper, lower, digits, special characters has a negative effect.</span></span> <span data-ttu-id="69b98-160">Alguns requisitos de complexidade impedem que os usuários usem senhas seguras e memoráveis ​​e os forçam a criar senhas menos seguras e menos memoráveis.</span><span class="sxs-lookup"><span data-stu-id="69b98-160">Some complexity requirements even prevent users from using secure and memorable passwords, and force them into coming up with less secure and less memorable passwords.</span></span>
  
## <a name="successful-patterns"></a><span data-ttu-id="69b98-161">Padrões Bem-sucedidos</span><span class="sxs-lookup"><span data-stu-id="69b98-161">Successful Patterns</span></span>

<span data-ttu-id="69b98-162">Por outro lado, aqui estão algumas recomendações para o incentivo à diversidade de senhas.</span><span class="sxs-lookup"><span data-stu-id="69b98-162">In contrast, here are some recommendations in encouraging password diversity.</span></span>
  
### <a name="ban-common-passwords"></a><span data-ttu-id="69b98-163">Bloquear senhas comuns</span><span class="sxs-lookup"><span data-stu-id="69b98-163">Ban common passwords</span></span>

<span data-ttu-id="69b98-164">O requisito de senha mais importante que você deve colocar para os usuários ao criar senhas é proibir o uso de senhas comuns para reduzir a suscetibilidade da sua organização a ataques de senha de força bruta.</span><span class="sxs-lookup"><span data-stu-id="69b98-164">The most important password requirement you should put on your users when creating passwords is to ban the use of common passwords to reduce your organization's susceptibility to brute force password attacks.</span></span> <span data-ttu-id="69b98-165">As senhas de usuário comuns incluem, **abcdefg**, **senha**, **macaco**.</span><span class="sxs-lookup"><span data-stu-id="69b98-165">Common user passwords include, **abcdefg**, **password**, **monkey**.</span></span>
  
### <a name="educate-users-to-not-re-use-organization-passwords-anywhere-else"></a><span data-ttu-id="69b98-166">Instrua os usuários a não reutilizar senhas da organização em outro local</span><span class="sxs-lookup"><span data-stu-id="69b98-166">Educate users to not re-use organization passwords anywhere else</span></span>

<span data-ttu-id="69b98-167">Uma das mensagens mais importantes a serem transmitidas aos usuários da organização é não reutilizar a senha da organização em nenhum outro lugar.</span><span class="sxs-lookup"><span data-stu-id="69b98-167">One of the most important messages to get across to users in your organization is to not re-use their organization password anywhere else.</span></span> <span data-ttu-id="69b98-168">O uso de senhas da organização em sites externos aumenta significativamente a probabilidade de que os cibercriminosos comprometam essas senhas.</span><span class="sxs-lookup"><span data-stu-id="69b98-168">The use of organization passwords in external websites greatly increases the likelihood that cyber criminals will compromise these passwords.</span></span>
  
### <a name="enforce-multi-factor-authentication-registration"></a><span data-ttu-id="69b98-169">Impor registro de Autenticação Multifator</span><span class="sxs-lookup"><span data-stu-id="69b98-169">Enforce Multi-Factor Authentication registration</span></span>

<span data-ttu-id="69b98-170">Verifique se os usuários atualizam informações de contato e segurança, como um endereço de email alternativo, um número de telefone ou um dispositivo registrado para notificações por push, para que possam responder aos desafios de segurança e serem notificados de eventos de segurança.</span><span class="sxs-lookup"><span data-stu-id="69b98-170">Make sure your users update contact and security information, like an alternate email address, phone number, or a device registered for push notifications, so they can respond to security challenges and be notified of security events.</span></span> <span data-ttu-id="69b98-171">As informações atualizadas de contato e segurança ajudam os usuários a verificar sua identidade se esquecerem sua senha ou se outra pessoa tentar assumir sua conta.</span><span class="sxs-lookup"><span data-stu-id="69b98-171">Updated contact and security information helps users verify their identity if they ever forget their password, or if someone else tries to take over their account.</span></span> <span data-ttu-id="69b98-172">Ele também fornece um canal de notificação fora da banda no caso de eventos de segurança, como tentativas de logon ou senhas alteradas.</span><span class="sxs-lookup"><span data-stu-id="69b98-172">It also provides an out of band notification channel in the case of security events such as login attempts or changed passwords.</span></span> 
  
<span data-ttu-id="69b98-173">Para saber mais, confira [Configurar a autenticação multifator](../security-and-compliance/set-up-multi-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="69b98-173">To learn more, see [Set up multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span>
  
### <a name="enable-risk-based-multi-factor-authentication"></a><span data-ttu-id="69b98-174">Habilitar a autenticação multifator baseada em risco</span><span class="sxs-lookup"><span data-stu-id="69b98-174">Enable risk-based multi-factor authentication</span></span>

<span data-ttu-id="69b98-175">A autenticação multifatorial baseada em risco garante que, quando o sistema detectar atividades suspeitas, ele poderá desafiar o usuário a garantir que ele seja o proprietário legítimo da conta.</span><span class="sxs-lookup"><span data-stu-id="69b98-175">Risk-based multi-factor authentication ensures that when our system detects suspicious activity, it can challenge the user to ensure that they are the legitimate account owner.</span></span> 
  
## <a name="want-to-know-more-recommended-reading"></a><span data-ttu-id="69b98-176">Deseja saber mais?</span><span class="sxs-lookup"><span data-stu-id="69b98-176">Want to know more?</span></span> <span data-ttu-id="69b98-177">Leitura recomendada</span><span class="sxs-lookup"><span data-stu-id="69b98-177">Recommended reading</span></span>

- [<span data-ttu-id="69b98-178">Senhas Fortes da Web Realizam Qualquer Coisa?</span><span class="sxs-lookup"><span data-stu-id="69b98-178">Do Strong Web Passwords Accomplish Anything?</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861008)

- [<span data-ttu-id="69b98-179">Portfólios de Senhas e Usuário Finito</span><span class="sxs-lookup"><span data-stu-id="69b98-179">Password Portfolios and the Finite-Effort User</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861014)

- [<span data-ttu-id="69b98-180">Evitando Senhas Fracas Lendo as Mentes dos Usuários</span><span class="sxs-lookup"><span data-stu-id="69b98-180">Preventing Weak Passwords by Reading Users' Minds</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861015)

- [<span data-ttu-id="69b98-181">Escolhendo Senhas Seguras</span><span class="sxs-lookup"><span data-stu-id="69b98-181">Choosing Secure Passwords</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861016)

- [<span data-ttu-id="69b98-182">Hora de repensar as alterações de senha obrigatórias</span><span class="sxs-lookup"><span data-stu-id="69b98-182">Time to rethink mandatory password changes</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861018)

- [<span data-ttu-id="69b98-183">As piores Senhas do 2015</span><span class="sxs-lookup"><span data-stu-id="69b98-183">Worst Passwords of 2015</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861020)

## <a name="related-content"></a><span data-ttu-id="69b98-184">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="69b98-184">Related content</span></span>

<span data-ttu-id="69b98-185">[Redefinir senhas](../add-users/reset-passwords.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="69b98-185">[Reset passwords](../add-users/reset-passwords.md) (article)</span></span>

<span data-ttu-id="69b98-186">[Definir a senha de um usuário individual para nunca expirar](../add-users/set-password-to-never-expire.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="69b98-186">[Set an individual user's password to never expire](../add-users/set-password-to-never-expire.md) (article)</span></span>

<span data-ttu-id="69b98-187">[Permitir aos usuários redefinir suas próprias senhas](../add-users/let-users-reset-passwords.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="69b98-187">[Let users reset their own passwords](../add-users/let-users-reset-passwords.md) (article)</span></span>

<span data-ttu-id="69b98-188">[Reenviar a senha de um usuário - Ajuda do Administrador](../add-users/resend-user-password.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="69b98-188">[Resend a user's password - Admin Help](../add-users/resend-user-password.md) (article)</span></span>