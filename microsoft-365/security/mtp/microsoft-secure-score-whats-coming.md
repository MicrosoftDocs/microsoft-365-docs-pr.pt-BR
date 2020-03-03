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
ms.openlocfilehash: efb75f26d66258880c9defa94869f27e18685052
ms.sourcegitcommit: 9224a7a5886c0c5fa0bc12bd9f7234a0eba90023
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42371999"
---
# <a name="whats-coming-in-microsoft-secure-score"></a>O que está acontecendo na pontuação segura da Microsoft?

Para tornar a pontuação segura da Microsoft um melhor representante da postura de segurança e melhorar a usabilidade, estamos fazendo algumas alterações em um futuro próximo. Sua pontuação e a pontuação máxima possível mudarão. No entanto, isso não implica uma alteração na postura de segurança.

Para saber mais sobre as alterações recentes, confira [o que há de novo na pontuação segura da Microsoft?](microsoft-secure-score.md#whats-new)

## <a name="march-16th-2020"></a>16 de março de 2020

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a>Removendo ações de melhoria que não atendem às expectativas para uma medição confiável ou não oferecem uma representação útil de postura de segurança

Para garantir que a pontuação segura da Microsoft seja significativa e que cada ação de melhoria seja mensurável e confiável, estamos removendo as seguintes ações de aprimoramento.

- Armazenar documentos de usuário no OneDrive for Business
- Configurar as políticas de anexo seguro do Office 365 ATP
- Configurar links seguros do Office 365 para verificar URLs
- Não permitir a delegação de caixa de correio
- Permitir links de compartilhamento de convidados anônimos para sites e documentos
- Ativar console do Cloud app Security
- Configurar tempo de expiração para links de compartilhamento externos

### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a>Padrões de segurança de suporte para ações de melhoria do Azure AD

A pontuação segura da Microsoft atualizará as ações de aperfeiçoamento para suportar os [padrões de segurança no Azure ad](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), o que facilita a proteção da sua organização com configurações de segurança pré-configuradas para ataques comuns.

Isso afetará as seguintes ações de melhoria:

- Garantir que todos os usuários possam concluir a autenticação multifator para acesso seguro
- Exigir MFA para funções administrativas
- Habilitar política para bloquear autenticação herdada
