---
title: Controles de acesso administrativo no Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
f1.keywords:
- NOCSH
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom: seo-marvel-apr2020
description: Este artigo fornece uma visão geral dos controles de acesso administrativo e da categorização de dados no Microsoft 365.
ms.openlocfilehash: b5063f89e89b6cffffda53a5df3088a80f89c242
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686971"
---
# <a name="administrative-access-controls-in-microsoft-365"></a>Controles de acesso administrativo no Microsoft 365 

A Microsoft investiu pesadamente em sistemas e controles que automatizam a maioria das operações do Microsoft 365 enquanto limitava intencionalmente o acesso ao conteúdo do cliente pela Microsoft. Os seres humanos governam o serviço e o software opera o serviço. Isso permite que a Microsoft gerencie o Microsoft 365 em escala e gerencie os riscos de ameaças internas ao conteúdo do cliente.

Por padrão, os engenheiros da Microsoft têm nenhum privilégio administrativo de pé e zero acesso de pé ao conteúdo do cliente no Microsoft 365. Um engenheiro da Microsoft pode ter acesso limitado, auditado e protegido ao conteúdo de um cliente por um período limitado de tempo. O acesso é apenas quando necessário para operações de serviço e somente quando aprovado por um membro do gerenciamento sênior da Microsoft. Para clientes licenciados de lockbox de clientes, o cliente fornece aprovação de acesso para seu conteúdo hospedado no Microsoft 365.

A Microsoft fornece serviços online usando várias formas de entrega na nuvem:

- **Nuvens públicas:** Inclui versões de vários locatários do Microsoft 365, Azure e outros serviços hospedados na América do Norte, América do Sul, Europa, Ásia, Austrália, etc.
- **Nuvens nacionais:** Inclui todas as nuvens soberana e operadas por terceiros fora dos Estados Unidos (exceto aqueles observados anteriormente), como o Microsoft 365 na China (operado pela 21Vianet) e a Microsoft 365 na Alemanha (operada pela Microsoft, mas em um modelo no qual um data de confiança de dados em alemão, alemães Telekom, controla e monitora o acesso da Microsoft aos dados e sistemas de clientes que contêm dados
- **Nuvens governamentais:** Inclui os serviços do Microsoft 365 e do Azure que estão disponíveis para os clientes do governo dos Estados Unidos.

Para os fins deste artigo, os serviços do Microsoft 365 incluem:

- [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online)
- [Proteção do Exchange Online](https://docs.microsoft.com/Office365/SecurityCompliance/eop/exchange-online-protection-overview)
- [SharePoint Online](https://docs.microsoft.com/sharepoint/sharepoint-online)
- [OneDrive for Business](https://docs.microsoft.com/OneDrive/onedrive)
- [Skype for Business](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online)
- [Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
- [Yammer](https://docs.microsoft.com/yammer/yammer-landing-page)

## <a name="microsoft-365-access-controls"></a>Controles de acesso do Microsoft 365

Para fins de controle de acesso, a Microsoft categoriza os dados do Microsoft 365 como dados do cliente ou outros tipos de dados.

### <a name="customer-data"></a>Dados do cliente

Os dados do cliente são todos os dados fornecidos por ou em nome de um cliente ao usar os serviços do Microsoft 365. Este é o conteúdo do cliente criado diretamente ou carregado pelos usuários do Microsoft 365, incluindo:

- Emails
- Conteúdo do SharePoint Online
- Mensagens instantâneas
- Itens de calendário
- Documentos
- Contatos
- Informações de identificação do usuário final (EUII) (dados exclusivos de um usuário ou que são vinculados a um usuário individual, mas não incluem conteúdo do cliente)

### <a name="other-types-of-data"></a>Outros tipos de dados

Outros tipos de dados incluem:

- **Dados da conta:** Inclui dados administrativos (informações fornecidas por administradores ao inscrever-se ou comprar serviços) e dados de pagamento (informações sobre instrumentos de pagamento, como detalhes do cartão de crédito).
- **Informações de identificação corporativa:** Inclui dados usados para identificar um locatário, dados de uso e não vinculáveis a um usuário individual ou incluído no conteúdo do cliente.
- **Metadados do sistema:** Inclui logs de serviço que contêm definições de configuração, status do sistema, endereços IP da Microsoft e informações técnicas sobre inscrições e locatários.

A Microsoft estabeleceu mecanismos de controle de acesso para garantir que ninguém tenha acesso não aprovado aos dados do cliente ou aos dados de controle de acesso. Os dados de controle de acesso gerenciam o acesso a outros tipos de dados ou funções dentro do ambiente, incluindo acesso ao conteúdo do cliente ou EUII, senhas da Microsoft, certificados de segurança e outros dados relacionados à autenticação. Os mecanismos de controle de acesso também protegem contra acesso físico, lógico ou remoto não aprovado ao ambiente de produção do Microsoft 365.

Há três categorias de controles de acesso usados pela Microsoft para a operação do Microsoft 365:

- Controles de isolamento
- Controles de pessoal
- Controles de tecnologia

Quando combinadas, esses controles ajudam a evitar e detectar ações mal-intencionadas no Microsoft 365. Além dos controles de isolamento, pessoal e tecnologia usados pela Microsoft, há uma quarta categoria de controles: as implementadas por clientes.

O Microsoft 365 permite que você gerencie dados da mesma forma que os dados são gerenciados em ambientes locais. A pessoa que se inscreve na organização do Microsoft 365 se torna automaticamente um administrador global. O administrador global tem acesso a todos os recursos nos portais de gerenciamento e pode:

- Criar ou editar usuários
- Atribuir funções de administrador a outras pessoas
- Redefinir senhas de usuário
- Gerenciar licenças de usuário
- Gerenciar domínios
- Aprovar solicitações de lockbox do cliente

Recomendamos que cada organização configure pelo menos duas contas de administrador. Para organizações de grande porte, recomendamos contas de administração especializadas que atendam a diferentes funções.

Para obter informações sobre como atribuir permissões e funções de administrador, consulte [assign admin Roles](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) e [about admin Roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

## <a name="related-links"></a>Links relacionados

- [Controles de isolamento](microsoft-365-isolation-controls.md)
- [Controles de pessoal](microsoft-365-personnel-controls.md)
- [Controles de tecnologia](microsoft-365-technology-controls.md)
- [Monitorando e auditando controles de acesso ](microsoft-365-monitoring-and-auditing-access-controls.md)
- [Controles de acesso do Yammer Enterprise](microsoft-365-yammer-enterprise-access-controls.md)
