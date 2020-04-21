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
ms.openlocfilehash: 234ae17ab31d56d1bbd65f1aa8ed29475e9cd155
ms.sourcegitcommit: d818828c66cf98b0b0037ba8b3cb790c940281b7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43583710"
---
# <a name="whats-coming-in-microsoft-secure-score"></a>O que está acontecendo na pontuação segura da Microsoft?

Para tornar a [Pontuação segura da Microsoft](microsoft-secure-score.md) um melhor representante da postura de segurança e melhorar a usabilidade, estamos fazendo algumas alterações em um futuro próximo. Sua pontuação e a pontuação máxima possível mudarão. No entanto, isso não implica uma alteração na postura de segurança.

Para saber mais sobre as alterações recentes, confira [o que há de novo na pontuação segura da Microsoft?](microsoft-secure-score.md#whats-new)

## <a name="april-21st-2020"></a>21 de abril de 2020

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a>Removendo ações de melhoria que não atendem às expectativas para uma medição confiável ou não oferecem uma representação útil de postura de segurança

Para garantir que a pontuação segura da Microsoft seja significativa e que cada ação de melhoria seja mensurável e confiável, estamos removendo as seguintes ações de aprimoramento.

- Aplicar proteções de IRM a documentos
- Aplicar políticas de prevenção contra perda de dados

### <a name="adding-azure-ad-improvement-action-to-preview"></a>Adicionando a ação de melhoria do Azure AD para visualização

Adição da seguinte ação de melhoria do Azure Active Directory para a [versão prévia da Pontuação segura da Microsoft](microsoft-secure-score-preview.md):

- Não permitir que os usuários conceda consentimento a aplicativos não gerenciados (atualmente disponível na versão lançada)

### <a name="adding-azure-atp-improvement-actions-to-preview"></a>Adicionando ações de melhoria da ATP do Azure para visualização

Adicionar as seguintes ações de melhoria avançada de proteção contra ameaças do Azure à [versão prévia da Pontuação segura da Microsoft](microsoft-secure-score-preview.md):

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

### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations-in-preview"></a>Suporte para recomendações de segurança do TVM (gerenciamento de vulnerabilidades) do Microsoft defender & ATP em versão prévia

Todas as recomendações de segurança lançadas pelo TVM agora também estarão disponíveis na [versão prévia da Pontuação segura da Microsoft](microsoft-secure-score-preview.md).
