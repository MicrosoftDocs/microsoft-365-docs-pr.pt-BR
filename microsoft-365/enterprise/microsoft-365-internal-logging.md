---
title: Log interno do Microsoft 365 para o Microsoft 365 Engineering
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Neste artigo, encontre uma explicação sobre como o log interno para o Microsoft 365 Engineering Teams funciona.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 08f87ba682a88a7efd93735b160af49bf5468ca2
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332503"
---
# <a name="internal-logging-for-microsoft-365-engineering"></a>Log interno para engenharia do Microsoft 365

Além dos eventos e dados de log disponíveis para os clientes, há também um sistema de coleta de dados de log interno disponível para engenheiros da Microsoft 365 na Microsoft. Muitos tipos diferentes de dados de log são carregados dos servidores da Microsoft 365 para um serviço de computação de dados interno e global chamado Cosmos. Cada equipe de serviço carrega logs de auditoria de seus respectivos servidores no banco de dados do cosmos para agregação e análise. Essa transferência de dados ocorre em uma conexão TLS validada pelo FIPS 140-2 em portas e protocolos especificamente aprovados usando uma ferramenta de automação proprietária chamada ODL (Office Data Loader). As ferramentas usadas no Microsoft 365 para coletar e processar registros de auditoria não permitem alterações permanentes ou irreversíveis no conteúdo do registro de auditoria original ou na ordenação do tempo.

As equipes de serviço usam o cosmos como um repositório centralizado para conduzir uma análise de uso do aplicativo, medir o desempenho operacional e do sistema e procurar anormalidades e padrões que possam indicar problemas ou problemas de segurança. Cada equipe de serviço carrega uma linha de base de logs no cosmos, dependendo do que estão procurando analisar, que geralmente incluem:

- Logs de eventos
- Logs do AppLocker
- Dados de desempenho
- Dados do System Center
- Registros de detalhes da chamada
- Dados de qualidade da experiência
- Logs de servidor Web do IIS
- Logs do SQL Server
- Dados de syslog
- Logs de auditoria de segurança

Antes de carregar dados no cosmos, o aplicativo do ODL usa um serviço de depuração para ofuscar quaisquer campos que contenham dados do cliente, como informações de locatário e informações de identificação do usuário final, e substitua esses campos por um valor de hash. Os logs anônimos e de hash são reconfigurados e, em seguida, carregados no cosmos. As equipes de serviço executam consultas com escopo em seus dados no cosmos para correlação, alerta e relatórios. O período de retenção de dados de log de auditoria no cosmos é determinado pelas equipes de serviço; a maioria dos dados de log de auditoria é mantida por 90 dias ou mais para suportar investigações de incidentes de segurança e para atender aos requisitos de retenção regulamentar.

O acesso aos dados do Microsoft 365 armazenados no cosmos é restrito a pessoal autorizado. A Microsoft restringe o gerenciamento da funcionalidade de auditoria ao subconjunto limitado de membros da equipe de serviço responsáveis pela funcionalidade de auditoria. Esses membros da equipe não têm a capacidade de modificar ou excluir dados do cosmos, e todas as alterações nos mecanismos de registro em log para cosmos são registradas e auditadas.

Cada equipe de serviço acessa seus dados de log para análise por meio da autorização de determinados aplicativos para realizar uma análise específica. Por exemplo, a equipe de segurança do Microsoft 365 usa dados do cosmos por meio de um analisador de log de eventos proprietário para correlacionar, alertar e gerar relatórios acionáveis sobre possíveis atividades suspeitas no ambiente de produção do Microsoft 365. Os relatórios desses dados são usados para corrigir as vulnerabilidades e para melhorar o desempenho geral do serviço. Se um alerta ou relatório específico exigir mais investigações, a equipe de serviço poderá solicitar que os dados sejam importados de volta para o serviço do Microsoft 365. Como o log específico que está sendo importado do cosmos está em criptografado e a equipe de serviço não tem acesso a chaves de descriptografia, o log de destino é transmitido de forma programática através de um serviço de descriptografia que retorna os resultados do escopo para a equipe de serviço autorizada. Quaisquer vulnerabilidades encontradas neste exercício são relatadas e escalonadas usando os canais de gerenciamento de incidentes de segurança padrão da Microsoft.
