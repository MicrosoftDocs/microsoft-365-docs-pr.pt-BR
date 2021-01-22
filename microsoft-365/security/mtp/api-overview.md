---
title: Visão geral das APIs do Microsoft 365 Defender
description: Saiba mais sobre as APIs disponíveis no Microsoft 365 Defender
keywords: api, apis, visão geral, incidentes, incidentes, busca de ameaças, microsoft 365 defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 8e06d4b4f7c895b532091c73e8269411fb38bf21
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930997"
---
# <a name="overview-of--microsoft-365-defender-apis"></a>Visão geral das APIs do Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Algumas informações estão relacionadas a produtos de pré-lançamento que podem ser substancialmente modificados antes de serem lançadas comercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

O Microsoft 365 Defender foi criado com base em uma plataforma pronta para integração.

Use as APIs do Microsoft 365 Defender para automatizar fluxos de trabalho com base no incidente compartilhado e tabelas de busca avançada.

- **[Fila de incidentes combinados](api-incident.md)** - Concentre-se no que é crítico agrupando o escopo completo do ataque e todos os ativos afetados na API do incidente.

- **[Busca de](api-advanced-hunting.md)** ameaças entre produtos - Aproveite o conhecimento organizacional da sua equipe de segurança para procurar sinais de comprometimento, criando suas próprias consultas personalizadas para sift sobre dados brutos coletados em vários produtos de proteção.

Juntamente com essas APIs específicas do Microsoft 365 Defender, cada um dos nossos outros produtos de segurança [expõem APIs adicionais](api-articles.md) para ajudá-lo a aproveitar seus recursos exclusivos.

## <a name="learn-more"></a>Saiba mais

| **Entender como acessar as APIs** |
|-|
| [Saiba mais sobre cotas e licenciamento da API](api-terms.md) |
| [Acessar as APIs do Microsoft 365 Defender](api-access.md) |
| **Build apps** |
| [Criar um aplicativo "Hello world"](api-hello-world.md) |
| [Criar um aplicativo para acessar as APIs do Microsoft 365 Defender em nome de um usuário](api-create-app-user-context.md) |
| [Criar um aplicativo para acessar o Microsoft 365 Defender sem um usuário](api-create-app-web.md) |
| [Criar um aplicativo com acesso de parceiro multi-locatário às APIs do Microsoft 365 Defender](api-partner-access.md) |
| **Solucionar problemas e manter seus aplicativos** |
| [Compreender os códigos de erro da API](api-error-codes.md) |
| [Gerenciar segredos em seus aplicativos com o Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/) |
| [Implementar a autorização do OAuth 2.0 para entrar no usuário](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |
