---
title: O que está acontecendo na pontuação segura da Microsoft?
description: Descreve a pontuação segura da Microsoft na central de segurança do Microsoft 365, como os detalhes são calculados e quais administradores de segurança podem esperar.
keywords: segurança, malware, Microsoft 365, M365, Pontuação segura, central de segurança, ações de melhoria
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 4d445d4c917a46b12592308f599570725ace8e9d
ms.sourcegitcommit: 6c7f6ef98c321c80a9254c10bbbb917895b5c156
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/27/2020
ms.locfileid: "42322560"
---
# <a name="whats-coming-in-microsoft-secure-score"></a>O que está acontecendo na pontuação segura da Microsoft?

Para tornar a pontuação segura da Microsoft um melhor representante da postura de segurança e melhorar a usabilidade, estamos fazendo algumas alterações em um futuro próximo. Sua pontuação e a pontuação máxima possível mudarão. No entanto, isso não implica uma alteração na postura de segurança.

Para saber mais sobre as alterações recentes, confira [o que há de novo na pontuação segura da Microsoft?](microsoft-secure-score.md#whats-new)

## <a name="march-2nd-2020"></a>2 de março de 2020

### <a name="removing-improvement-actions-from-intune"></a>Removendo ações de melhoria do Intune

Após uma avaliação das ações de melhoria de Pontuação segura da Microsoft fornecidas pelo Intune, foi decidido que eles não oferecem uma representação útil da postura de segurança dos dispositivos nas organizações. Em vez de se concentrar em políticas, estamos trabalhando para trazer os controles de segurança que avaliam diretamente o estado de configuração dos dispositivos.

As seguintes ações de aprimoramento do Intune serão removidas:

- Habilitar o gerenciamento de dispositivos móveis do Microsoft Intune
- Criar uma política de conformidade do Microsoft Intune para Android
- Criar uma política de conformidade do Microsoft Intune para Android para trabalho
- Criar uma política de proteção de aplicativos do Microsoft Intune para Android
- Criar uma política de proteção de aplicativos do Microsoft Intune para iOS
- Marcar dispositivos sem política de conformidade do Microsoft Intune atribuída como não compatível
- Criar uma política de conformidade do Microsoft Intune para iOS
- Criar uma política de conformidade do Microsoft Intune para o macOS
- Criar uma política de conformidade do Microsoft Intune para o Windows
- Criar um perfil de configuração do Microsoft Intune para Android
- Criar um perfil de configuração do Microsoft Intune para Android para trabalho
- Criar um perfil de configuração do Microsoft Intune para o macOS
- Criar um perfil de configuração do Microsoft Intune para iOS
- Criar um perfil de configuração do Microsoft Intune para Windows
- Habilitar a detecção avançada do jailbreak no Microsoft Intune
- Exigir que todos os dispositivos sejam corrigidos, ter antivírus e firewalls habilitados
- Habilitar a integração ATP do Windows Defender no Microsoft Intune
- Criar uma política de proteção de informações do Windows do Microsoft Intune
- Exigir que todos os dispositivos tenham configurações de segurança avançadas
- Examinar o relatório de dispositivos bloqueados semanalmente

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement"></a>Removendo ações de melhoria que não atendem às expectativas de medição confiável 

Para garantir que a pontuação segura da Microsoft seja significativa e que cada ação de melhoria seja mensurável e confiável, estamos removendo as seguintes ações de aprimoramento.

- Ativar a gravação de dados de auditoria
- Descobrir aplicativos de ti de sombra arriscados e não compatíveis
- Examinar permissões & bloquear aplicativos OAuth arriscados conectados ao seu ambiente
- Configurar o controle de versão em bibliotecas de documentos do SharePoint Online

### <a name="mfa-improvement-action-updates"></a>Atualizações das ações de melhoria da MFA

Para refletir a necessidade de que as empresas garantam o máximo de segurança durante a aplicação de políticas que funcionam com seus negócios, a pontuação segura da Microsoft é remover três ações de melhoria centralizada em relação à autenticação multifator e adição de dois.

Os três que serão removidos:

- Registrar todos os usuários para autenticação multifator
- Exigir MFA para todos os usuários
- Exigir MFA para funções privilegiadas do Azure AD

Novas ações de aprimoramento foram adicionadas:

- Garantir que todos os usuários possam concluir a autenticação multifator para acesso seguro
- Exigir MFA para funções administrativas

 Essas novas ações de melhoria exigirão o registro de seus usuários ou administradores para a autenticação multifator (MFA) em seu diretório e o estabelecimento do conjunto certo de políticas que atendam às suas necessidades organizacionais. O objetivo principal é ter flexibilidade enquanto garante que todos os seus usuários e administradores podem autenticar com vários fatores ou solicitações de verificação de identidade baseadas em risco. Isso pode ter a forma de ter várias políticas que aplicam decisões com escopo ou definir padrões de segurança (chegando a 16 de março) que permitem que a Microsoft decida quando desafiar os usuários para a MFA.

### <a name="removing-review-improvement-actions"></a>Removendo ações de melhoria de "revisão"

Um dos princípios de Pontuação segura é que a pontuação deve ser padronizada e fácil de se relacionar. Ter ações de melhoria que não podem ser mensuráveis ou acionável está causando confusão. Uma pontuação segura da Microsoft faz sentido quando cada recomendação pode ter um efeito claro na pontuação. Revisar as ações de melhoria não são medidas para o mesmo padrão que outras ações de aprimoramento.  

Por esses motivos, todas as ações de melhoria que exigiram uma cadência de revisão serão removidas temporariamente. Nenhuma ação é necessária em sua parte.

## <a name="march-16th-2020"></a>16 de março de 2020

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a>Removendo ações de melhoria que não atendem às expectativas para uma medição confiável ou não oferecem uma representação útil de postura de segurança

Para garantir que a pontuação segura da Microsoft seja significativa e que cada ação de melhoria seja mensurável e confiável, estamos removendo as seguintes ações de aprimoramento.

- Armazenar documentos de usuário no OneDrive for Business
- Configurar as políticas de anexo seguro do Office 365 ATP
- Configurar links seguros do Office 365 para verificar URLs
- Não permitir a delegação de caixa de correio
- Permitir links de compartilhamento de convidados anônimos para sites e documentos
- Ativar console do Cloud app Security

### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a>Padrões de segurança de suporte para ações de melhoria do Azure AD

A pontuação segura da Microsoft atualizará as ações de aperfeiçoamento para suportar os [padrões de segurança no Azure ad](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), o que facilita a proteção da sua organização com configurações de segurança pré-configuradas para ataques comuns.

Isso afetará as seguintes ações de melhoria:

- Garantir que todos os usuários possam concluir a autenticação multifator para acesso seguro
- Exigir MFA para funções administrativas
- Habilitar política para bloquear autenticação herdada
