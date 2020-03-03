---
title: Recomendações de política de senha para o Office 365
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9fa2539a-2211-41fd-85a0-bc37b9619ca4
description: Aprenda a tornar a sua organização mais segura contra ataques de senha e por que você deve bloquear senhas comuns e habilitar a autenticação multifator baseada em risco.
ms.openlocfilehash: 7136243aa0a358a59e4be6c348f53ca459e8a65d
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361322"
---
# <a name="password-policy-recommendations-for-office-365"></a>Recomendações de política de senha para o Office 365
 
Como administrador de uma organização do Office 365, você é responsável por definir a política de senha para usuários em sua organização. Definir a política de senha pode ser complicado e confuso, e este artigo fornece recomendações para tornar a sua organização mais segura contra ataques de senha.
  
Para determinar a frequência com que as senhas do Office 365 expiram em sua organização, confira [Definir política de expiração de senha para o Office 365](../manage/set-password-expiration-policy.md).
  
## <a name="understanding-password-recommendations"></a>Compreendendo as recomendações de senha

As boas práticas de senha se enquadram em algumas categorias amplas:
  
- **Resistir a ataques comuns** Isso envolve a escolha de onde os usuários inserem senhas (dispositivos conhecidos e confiáveis com boa detecção de malware, sites validados) e a escolha de qual senha escolher (comprimento e exclusividade).

- **Conter ataques bem-sucedidos** Conter ataques de hackers bem-sucedidas consiste em limitar a exposição a um serviço específico ou impedir completamente esse dano, se a senha de um usuário for roubada. Por exemplo, garantir que uma violação de suas credenciais de rede social não torne sua conta bancária vulnerável ou não permita que uma conta mal protegida aceite links de redefinição para uma conta importante.

- **Noções básicas sobre a natureza humana** Muitas práticas válidas de senha falham diante dos comportamentos humanos naturais. Entender a natureza humana é fundamental porque a pesquisa mostra que quase todas as regras que você impõe aos usuários resultam em um enfraquecimento da qualidade da senha. Requisitos de comprimento, requisitos especiais de caracteres e requisitos de alteração de senha resultam na normalização de senhas, o que facilita para os invasores adivinharem ou decifrarem senhas.

## <a name="password-guidelines-for-administrators"></a>Diretrizes de senha para administradores

O principal objetivo de um sistema de senhas mais seguro é a diversidade de senhas. Você quer que sua política de senha contenha várias senhas diferentes e difíceis de adivinhar. Aqui estão algumas recomendações para manter sua organização o mais segura possível.
  
- Manter um requisito de comprimento mínimo de 8 caracteres (maior não é necessariamente melhor)

- Não exigir requisitos de composição de caracteres. Por exemplo, \*&amp;(^%$

- Não exigir redefinições de senha periódicas obrigatórias para contas de usuários

- Proíba senhas comuns, para evitar senhas mais vulneráveis no seu sistema

- Instrua seus usuários para não reutilizarem as senhas da organização para fins não relacionados ao trabalho

- Impor registro para [autenticação multifator](../security-and-compliance/set-up-multi-factor-authentication.md)

- Ativar desafios de autenticação multifator baseados em risco

### <a name="password-guidance-for-your-users"></a>Diretrizes de senha para os seus usuários

Aqui estão algumas diretrizes de senha para usuários da sua organização. Lembre-se de permitir que seus usuários saibam sobre essas recomendações e aplicar as políticas de senha recomendadas no nível da organização.
  
- Não use uma senha igual ou similar a uma que você usa em outros sites

- Não use uma única palavra, por exemplo, **senha** ou uma frase habitualmente utilizada com **euamovocê**

- Torne as senhas difíceis de adivinhar, mesmo para quem sabe muito sobre você, como nomes e aniversários de seus amigos e familiares, suas bandas favoritas e frases que você gosta de usar

## <a name="some-common-approaches-and-their-negative-impacts"></a>Algumas abordagens comuns e seus impactos negativos

Essas são algumas das práticas de gerenciamento de senhas mais usadas, mas a pesquisa nos alerta sobre seus impactos negativos.
  
### <a name="password-expiration-requirements-for-users"></a>Requisitos de expiração de senha para usuários

Os requisitos de expiração de senha causam mais danos do que bem, porque fazem com que os usuários selecionem senhas previsíveis, compostas por palavras e números sequenciais intimamente relacionados entre si. Nesses casos, a próxima senha poderá ser prevista com base na senha anterior. Os requisitos de expiração de senha não oferecem benefícios de contenção, porque os cibercriminosos quase sempre usam credenciais assim que os comprometem.
  
### <a name="requiring-long-passwords"></a>Exigir senhas longas

Os requisitos de tamanho da senha (maiores que cerca de 10 caracteres) podem resultar em comportamento do usuário previsível e indesejável. Por exemplo, os usuários que precisam ter uma senha de 16 caracteres podem escolher padrões de repetição como **quatroquatroquatroquatro** ou **senhasenha** que atendem aos requisitos de comprimento de caractere, mas não são difíceis de adivinhar. Além disso, os requisitos de tamanho aumentam as chances de os usuários adotar outras práticas inseguras, como anotar suas senhas, reutilizá-las ou armazená-las descriptografadas em seus documentos. Para incentivar os usuários a pensar em uma senha exclusiva, recomendamos manter um requisito de comprimento mínimo de 8 caracteres. 
  
### <a name="requiring-the-use-of-multiple-character-sets"></a>Exigir o uso de vários conjuntos de caracteres

Os requisitos de complexidade de senha reduzem o espaço principal e fazem com que os usuários ajam de maneiras previsíveis, causando mais danos do que bem. A maioria dos sistemas aplica alguns níveis de requisitos de complexidade de senha. Por exemplo, as senhas precisam ter caracteres das três categorias a seguir:
  
- caracteres maiúsculos

- caracteres minúsculos

- caracteres não alfanuméricos

A maioria das pessoas usa padrões semelhantes, por exemplo, uma letra maiúscula na primeira posição, um símbolo na última e um número na última 2. Os cibercriminosos sabem disso, então executam seus ataques de dicionário usando as substituições mais comuns, "$" para "s", "@" para "a", "1" para "l". Forçar seus usuários a escolher uma combinação de caracteres maiúsculos e minúsculos, dígitos, caracteres especiais têm um efeito negativo. Alguns requisitos de complexidade impedem que os usuários usem senhas seguras e memoráveis ​​e os forçam a criar senhas menos seguras e menos memoráveis.
  
## <a name="successful-patterns"></a>Padrões Bem-sucedidos

Por outro lado, aqui estão algumas recomendações para o incentivo à diversidade de senhas.
  
### <a name="ban-common-passwords"></a>Bloquear senhas comuns

O requisito de senha mais importante que você deve colocar para os usuários ao criar senhas é proibir o uso de senhas comuns para reduzir a suscetibilidade da sua organização a ataques de senha de força bruta. As senhas comuns de usuário incluem, **abdcefg**, **senha**, **macaco**.
  
### <a name="educate-users-to-not-re-use-organization-passwords-anywhere-else"></a>Instrua os usuários a não reutilizar senhas da organização em outro local

Uma das mensagens mais importantes a serem transmitidas aos usuários da organização é não reutilizar a senha da organização em nenhum outro lugar. O uso de senhas da organização em sites externos aumenta significativamente a probabilidade de que os cibercriminosos comprometam essas senhas.
  
### <a name="enforce-multi-factor-authentication-registration"></a>Impor registro de Autenticação Multifator

Verifique se os usuários atualizam informações de contato e segurança, como um endereço de email alternativo, um número de telefone ou um dispositivo registrado para notificações por push, para que possam responder aos desafios de segurança e serem notificados de eventos de segurança. As informações atualizadas de contato e segurança ajudam os usuários a verificar sua identidade se esquecerem sua senha ou se outra pessoa tentar assumir sua conta. Ele também fornece um canal de notificação fora da banda no caso de eventos de segurança, como tentativas de logon ou senhas alteradas. 
  
Para saber mais, confira [Configurar a autenticação multifator](../security-and-compliance/set-up-multi-factor-authentication.md).
  
### <a name="enable-risk-based-multi-factor-authentication"></a>Habilitar a autenticação multifator baseada em risco

A autenticação multifatorial baseada em risco garante que, quando o sistema detectar atividades suspeitas, ele poderá desafiar o usuário a garantir que ele seja o proprietário legítimo da conta. 
  
## <a name="want-to-know-more-recommended-reading"></a>Deseja saber mais? Leitura recomendada

- [Senhas Fortes da Web Realizam Qualquer Coisa?](https://go.microsoft.com/fwlink/p/?linkid=861008)

- [Portfólios de Senhas e Usuário Finito](https://go.microsoft.com/fwlink/p/?linkid=861014)

- [Evitando Senhas Fracas Lendo as Mentes dos Usuários](https://go.microsoft.com/fwlink/p/?linkid=861015)

- [Escolhendo Senhas Seguras](https://go.microsoft.com/fwlink/p/?linkid=861016)

- [Hora de repensar as alterações de senha obrigatórias](https://go.microsoft.com/fwlink/p/?linkid=861018)

- [As piores Senhas do 2015](https://go.microsoft.com/fwlink/p/?linkid=861020)

- [Baixar arquivos da Web](https://go.microsoft.com/fwlink/p/?linkid=861029)
