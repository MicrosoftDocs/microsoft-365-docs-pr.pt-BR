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
ms.openlocfilehash: 1a5c5ae702f16bbf47be83837cf244cdd64278cd
ms.sourcegitcommit: 4988934836eee45c890b9bdd5ef73590656c78ba
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2020
ms.locfileid: "43541102"
---
# <a name="whats-coming-in-microsoft-secure-score"></a>O que está acontecendo na pontuação segura da Microsoft?

Para tornar a pontuação segura da Microsoft um melhor representante da postura de segurança e melhorar a usabilidade, estamos fazendo algumas alterações em um futuro próximo. Sua pontuação e a pontuação máxima possível mudarão. No entanto, isso não implica uma alteração na postura de segurança.

Para saber mais sobre as alterações recentes, confira [o que há de novo na pontuação segura da Microsoft?](microsoft-secure-score.md#whats-new)

## <a name="april-21st-2020"></a>21 de abril de 2020

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a>Removendo ações de melhoria que não atendem às expectativas para uma medição confiável ou não oferecem uma representação útil de postura de segurança

Para garantir que a pontuação segura da Microsoft seja significativa e que cada ação de melhoria seja mensurável e confiável, estamos removendo as seguintes ações de aprimoramento.

- Aplicar proteções de IRM a documentos
- Aplicar políticas de prevenção contra perda de dados

### <a name="adding-azure-ad-improvement-action-in-the-preview-version"></a>Adicionando a ação de melhoria do Azure AD na versão prévia

- Não permitir que os usuários conceda consentimento a aplicativos não gerenciados (atualmente disponível na versão lançada)

### <a name="adding-azure-atp-improvement-actions-in-the-preview-version"></a>Adicionando ações de melhoria da ATP do Azure na versão prévia

- Desabilitar o serviço spooler de impressão em controladores de domínio
- Modificar as delegações Kerberos não seguras para impedir a representação
- Proteger e gerenciar senhas de administrador local com o Microsoft LAPS
- Reduzir o risco de caminho de movimento lateral para entidades confidenciais
- Remover contas inativas de grupos confidenciais
- Remover atributos de histórico de SID não seguros das entidades
- Resolver atributos de conta não seguros
- Parar exposição de credenciais de texto não criptografado
- Parar comunicação de protocolos herdados
- Interromper o uso de codificação fraca

### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations-in-the-preview-version"></a>Suporte para recomendações de segurança do TVM (gerenciamento de vulnerabilidades) de & ameaças ATP da Microsoft defender na versão prévia

- Todas as recomendações de segurança lançadas pelo TVM também estarão disponíveis na pontuação segura da Microsoft
