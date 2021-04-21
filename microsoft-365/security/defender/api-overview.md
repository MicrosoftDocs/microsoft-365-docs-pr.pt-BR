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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 496ad5695d9cd491817bad5daf3c76a02addefd1
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904183"
---
# <a name="overview-of--microsoft-365-defender-apis"></a>Visão geral das APIs do Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Algumas informações estão relacionadas a produtos pré-lançados que podem ser substancialmente modificados antes de seu lançamento comercial. A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.

O Microsoft 365 Defender foi criado sobre uma plataforma pronta para integração.

Use as APIs do Microsoft 365 Defender para automatizar fluxos de trabalho com base no incidente compartilhado e nas tabelas avançadas de busca.

- **[Fila de incidentes combinados](api-incident.md)** - Concentre-se no que é crítico agrupando o escopo de ataque completo e todos os ativos afetados juntos na API de incidente.

- **[Busca de](api-advanced-hunting.md)** ameaças entre produtos - Aproveite o conhecimento organizacional da equipe de segurança para procurar sinais de comprometimento, criando suas próprias consultas personalizadas para sicar dados brutos coletados em vários produtos de proteção.

Juntamente com essas APIs específicas do Microsoft 365 Defender, cada um dos nossos outros produtos de segurança [expõem APIs](api-articles.md) adicionais para ajudá-lo a tirar proveito de seus recursos exclusivos.


> [!NOTE]
> A transição para o portal unificado não deve afetar os painéis do PowerBi com base nas APIs do Microsoft Defender para Ponto de Extremidade. Você pode continuar a trabalhar com as APIs existentes, independentemente da transição de portal interativo.


## <a name="learn-more"></a>Saiba mais

| **Entenda como acessar as APIs** |
|-|
| [Saiba mais sobre cotas de API e licenciamento](api-terms.md) |
| [Acessar as APIs do Microsoft 365 Defender](api-access.md) |
| **Build apps** |
| [Criar um aplicativo 'Hello world'](api-hello-world.md) |
| [Criar um aplicativo para acessar APIs do Microsoft 365 Defender em nome de um usuário](api-create-app-user-context.md) |
| [Criar um aplicativo para acessar o Microsoft 365 Defender sem um usuário](api-create-app-web.md) |
| [Criar um aplicativo com acesso de parceiro de vários locatários às APIs do Microsoft 365 Defender](api-partner-access.md) |
| **Solucionar problemas e manter seus aplicativos** |
| [Compreender códigos de erro da API](api-error-codes.md) |
| [Gerenciar segredos em seus aplicativos com o Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/) |
| [Implementar a autorização OAuth 2.0 para entrar no usuário](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |