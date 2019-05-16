---
title: Cenários e cargas de trabalho do Microsoft 365 Enterprise
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/15/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Integre os usuários de sua organização às cargas de trabalho de produtividade do Microsoft 365 Enterprise.
ms.openlocfilehash: 06dc8683c471de9de7067a3d84673687cddc76c6
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072401"
---
# <a name="microsoft-365-enterprise-workloads-and-scenarios"></a>Cenários e cargas de trabalho do Microsoft 365 Enterprise

Para aproveitar os benefícios da criatividade e do trabalho em equipe do Microsoft 365 Enterprise, implante essas cargas de trabalho em sua infraestrutura de base:

- [Microsoft Teams](teams-workload.md)
- [Exchange Online](exchangeonline-workload.md)
- [SharePoint Online](sharepoint-online-onedrive-workload.md)

Confira a carga de trabalho de [migração](migration-microsoft-365-enterprise-workload.md) para obter um mapa geral para migrar toda a sua organização para o Microsoft 365 Enterprise, o que inclui os produtos de cliente do Microsoft Office, produtos do Office Server local e os dispositivos da Microsoft baseados no Windows.

Os cenários usam recursos e serviços do Microsoft 365 Enterprise de forma integrada para atender às necessidades empresariais. Uma dessas necessidades é proteger dados altamente regulamentados armazenados no Microsoft 365. Os dados altamente regulamentados incluem ativos digitais:

- Sujeitos a regulamentações regionais.
- Mais importantes de sua organização, como segredos comerciais, financeiros ou informações de recursos humanos e estratégias da organização.

Para proteger esses dados de ameaças internas e externas, confira as instruções em [sites do Microsoft Teams e do SharePoint Online para dados altamente regulamentados](teams-sharepoint-online-sites-highly-regulated-data.md). Este cenário oferece orientações passo a passo sobre como configurar um site do SharePoint Online ou uma equipe do Microsoft Teams para armazenar com segurança seus dados mais importantes.

Veja a seguir as cargas de trabalho e os cenários no guia de implantação geral do Microsoft 365 Enterprise:

![](./media/deploy-workloads/m365-deploy-content-arch-workloads.png)

## <a name="foundation-infrastructure-prerequisites"></a>Pré-requisitos da infraestrutura de base

*Idealmente*, você deve implantar as cargas de trabalho e os cenários depois de configurar todas as fases da [infraestrutura de base](deploy-foundation-infrastructure.md). Isso garante que todas as camadas subjacentes estejam prontas para oferecer integração, segurança e a melhor experiência para seus usuários e seus dispositivos.

| Fase | Resultado |
|:-------|:-----|
| Rede | A rede é atualizada para obter um desempenho ideal para os serviços de nuvem do Microsoft 365. |
| Identidade | A identidade é sincronizada e protegida com a autenticação forte de contas de usuário e a proteção para contas de administrador. |
| Windows 10 Enterprise | Os computadores com o Windows 7 ou Windows 8.1 podem ser atualizados para o Windows 10 Enterprise, e os novos dispositivos recebem a instalação do Windows 10 Enterprise. |
| Office 365 ProPlus | Os usuários existentes do Microsoft Office podem ser atualizados para o Office 365 ProPlus. |
| Gerenciamento de dispositivo móvel | Os dispositivos podem ser registrados e gerenciados. |
| Proteção de informações | Os recursos de segurança do Office 365 estão habilitados, e sua sensibilidade ou os rótulos de Proteção de Informações do Azure estão prontos para proteger os documentos. |

Lembre-se de que esse processo é o ideal e pode levar algum tempo para planejar, configurar, testar e desenvolver um piloto, especialmente em grandes organizações com infraestrutura existente e diversos locais. Não é necessário preparar todas essas camadas em todos os locais para aproveitar mais rapidamente o valor empresarial do Microsoft 365 Enterprise. 

Aqui estão algumas cargas de trabalho comuns para implantar imediatamente: 

- Depois que a camada de **Identidade** da infraestrutura de base é implementada para os usuários, muitas organizações implantam:
  - O [Office 365 ProPlus](office365proplus-infrastructure.md) em conjunto com o [OneDrive for Business](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise). O Office 365 ProPlus fornece a segurança da autenticação moderna e a experiência do usuário do cliente mais recente do Microsoft Office. A migração dos arquivos pessoais do usuário para o OneDrive for Business reduz a infraestrutura e a necessidade de dar suporte a pastas base e drivers.
  - O [Exchange Online](exchangeonline-workload.md), para que os usuários possam começar a usar o email baseado na nuvem.
- Se não houver a necessidade imediata de armazenar na nuvem ativos digitais altamente regulamentados, implante o [Microsoft Teams](teams-workload.md) e o [SharePoint Online](sharepoint-online-onedrive-workload.md) para seus usuários, antes da camada de **Proteção de informações**.

É preciso decidir sobre a maneira mais adequada de ordenar e implantar a configuração das fases de pré-requisito da infraestrutura de base a fim de atender às suas necessidades de negócios da melhor forma possível.

### <a name="best-practice"></a>Prática recomendada

É altamente recomendável implantar e implementar a fase de **Identidade** da infraestrutura de base antes de ingressar os usuários nas cargas de trabalho ou nos cenários.

A fase de **Identidade** garante que sua identidade baseada na nuvem, seja ela somente na nuvem ou sincronizada com o Active Directory Domain Services (AD DS) local, contenha as contas e os grupos de usuário e de computador para gerenciar a autenticação e o acesso. É necessária a autenticação forte para todos os usuários com proteção forte de contas de administrador, antes de colocar os ativos digitais da organização na nuvem do Microsoft 365.

Embora seja fundamental e muito importante para o desempenho geral, a implementação da fase de **Rede** pode estar em andamento enquanto estiver ingressando os usuários nas cargas de trabalho; tenha em mente que o aplicativo e o desempenho do serviço do Microsoft 365 melhorarão ao longo do tempo.

Isso vale especialmente para organizações corporativas com vários locais e uma combinação de dispositivos de borda e de conexões com a Internet.
