---
title: Visão geral das APIs do Microsoft 365 defender
description: Saiba mais sobre as APIs disponíveis no Microsoft 365 defender
keywords: API, APIs, visão geral, incidente, incidentes, busca de ameaças, Microsoft 365 defender
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 1a75a561e60c05208e8ea302505f9644ac0bc044
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719185"
---
# <a name="overview-of--microsoft-365-defender-apis"></a>Visão geral das APIs do Microsoft 365 defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

O Microsoft 365 defender foi criado na parte superior de uma plataforma pronta para integração.

Use as APIs do Microsoft 365 defender para automatizar fluxos de trabalho com base no incidente compartilhado e nas tabelas de busca avançada.

- **[Incidentes combinados](api-incident.md)** enfocam o que é crítico ao agrupar o escopo de ataque completo e todos os ativos impactados juntos na API de incidentes.

- **[Busca de ameaças entre produtos](api-advanced-hunting.md)** -Aproveite o conhecimento organizacional da equipe de segurança para procurar sinais de comprometimento, criando suas próprias consultas personalizadas para buscar dados brutos coletados por vários produtos de proteção.

Juntamente com essas APIs específicas do Microsoft 365 defender, cada um dos outros produtos de segurança expõem [APIs adicionais](api-articles.md) para ajudá-lo a aproveitar seus recursos exclusivos.

## <a name="learn-more"></a>Saiba mais

| **Entender como acessar as APIs** |
|-|
| [Saiba mais sobre cotas de API e licenciamento](api-terms.md) |
| [Acessar as APIs do Microsoft 365 defender](api-access.md) |
| **Build apps** |
| [Criar um aplicativo "Olá mundo"](api-hello-world.md) |
| [Criar um aplicativo para acessar as APIs do Microsoft 365 defender em nome de um usuário](api-create-app-user-context.md) |
| [Criar um aplicativo para acessar o Microsoft 365 defender sem um usuário](api-create-app-web.md) |
| [Criar um aplicativo com acesso de parceiro multilocatário às APIs do Microsoft 365 defender](api-partner-access.md) |
| **Solucionar problemas e manter seus aplicativos** |
| [Entender códigos de erro da API](api-error-codes.md) |
| [Gerenciar segredos em seus aplicativos com o Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/) |
| [Implementar a autorização do OAuth 2,0 para entrar no usuário](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |
