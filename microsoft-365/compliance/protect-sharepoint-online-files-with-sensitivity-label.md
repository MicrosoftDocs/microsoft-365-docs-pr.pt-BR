---
title: Proteger arquivos do SharePoint Online com um rótulo de confidencialidade
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/27/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
ms.custom:
- Ent_Solutions
ms.assetid: 5b9c8e41-25d2-436d-89bb-9aecb9ec2b80
description: 'Resumo: aplique a Proteção de Informações do Azure para proteger arquivos em um site de equipe altamente confidencial do SharePoint Online.'
ms.openlocfilehash: 8d802d8c2b5202e51089659264b2e2c14f14ad3d
ms.sourcegitcommit: 1c90bcc5c56f24895f01c3e0423c3f6b73715c13
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44214625"
---
# <a name="protect-sharepoint-online-files-with-a-sensitivity-label"></a>Proteger arquivos do SharePoint Online com um rótulo de confidencialidade

Use as etapas deste artigo para configurar um rótulo de confidencialidade para fornecer criptografia e permissões aos arquivos. Esses arquivos podem ser adicionados a uma biblioteca do SharePoint configurada para proteção altamente confidencial. Ou abra um arquivo diretamente do site e aplique o rótulo. A proteção de criptografia e permissões vai junto com um arquivo, mesmo quando ele é baixado do site. 

Essas etapas são parte de uma solução maior de configuração da proteção altamente confidencial para sites do SharePoint e os arquivos dentro desses sites. Para saber mais, confira [Sites e arquivos seguros do SharePoint Online](../security/office-365-security/secure-sharepoint-online-sites-and-files.md). 

Usar rótulos de confidencialidade em arquivos no SharePoint Online não é recomendável para todos os clientes, mas é uma opção para os clientes que precisam deste nível de proteção em um subconjunto de arquivos.

Algumas observações importantes sobre esta solução:
- Se a sua organização ainda não [habilitou rótulos de confidencialidade para os arquivos do Office no SharePoint e no OneDrive (visualização pública)](/microsoft-365/compliance/sensitivity-labels-sharepoint-onedrive-files): Quando a criptografia for aplicada aos arquivos armazenados no Office 365, o serviço não poderá processar o conteúdo desses arquivos. Coautoria, descoberta eletrônica, pesquisa, Delve e outros recursos de colaboração não funcionam. Políticas de Prevenção contra perdas de dados (DLP) só funcionam com metadados (incluindo rótulos), mas não com o conteúdo desses arquivos (como números de cartão de crédito em arquivos).

- Essa solução requer que o usuário selecione um rótulo que aplique a proteção. Se você precisar de criptografia automática e da capacidade do SharePoint de indexar e inspecionar os arquivos, considere usar o IRM (Gerenciamento de Direitos de Informação) no SharePoint Online. Ao configurar uma biblioteca do SharePoint para IRM, os arquivos são criptografados automaticamente quando baixados para edição.  O IRM do SharePoint inclui limitações que podem influenciar sua decisão. Para saber mais, confira [Configurar o IRM (Gerenciamento de Direitos de Informação) no centro de administração do SharePoint](https://docs.microsoft.com/microsoft-365/compliance/set-up-irm-in-sp-admin-center).

## <a name="admin-setup"></a>Configuração de administrador

Para obter esse nível adicional de segurança para arquivos em um site de equipe específico do SharePoint Online, configure um rótulo de confidencialidade personalizado que seja seu próprio rótulo ou um sub-rótulo do rótulo geral para dados altamente regulamentados. Apenas membros do grupo do Microsoft 365 no site de equipe do SharePoint Online verão o rótulo ou o sub-rótulo personalizado na lista de rótulos.

- Use um rótulo de confidencialidade quando precisar de um pequeno número de rótulos para uso global e equipes privadas individuais.

- Use um sub-rótulo de confidencialidade quando houver um grande número de rótulos ou quiser organizar rótulos paras equipes altamente confidenciais sob um rótulo de uso geral para arquivos muito confidenciais.

Use [estas instruções](encryption-sensitivity-labels.md) para configurar um rótulo separado ou um sub-rótulo com as seguintes configurações:

- O nome do rótulo ou do sub-rótulo contém o nome do site de equipe
- A criptografia está ativada
- O grupo do Microsoft 365 da site equipe possui permissões de coautoria

Depois de criar, publique o novo rótulo ou sub-rótulo para seus usuários, que poderão, aplicá-los a arquivos localmente antes de carregá-los para a equipe ou, posteriormente, quando o arquivo estiver armazenado na equipe.
 
Assim que os usuários puderem selecionar o rótulo de confidencialidade na opção **Confidencialidade** na faixa de opções da **Página Inicial** do Microsoft Word, Excel e PowerPoint.
  
> [!NOTE]
> Caso tenha vários sites de equipe do SharePoint Online altamente confidenciais, crie vários rótulos de confidencialidade. 
  
## <a name="adding-permissions-for-external-users"></a>Adicionando permissões para usuários externos
Há duas maneiras de conceder aos usuários externos o acesso aos arquivos protegidos com o rótulo de confidencialidade. Em ambos os casos, os usuários externos devem ter uma conta do Azure AD. Se os usuários externos não forem membros de uma organização que usa o Azure AD, eles poderão obter uma conta do Azure AD individual usando essa página de inscrição: [https://aka.ms/aip-signup](https://aka.ms/aip-signup).

 - Adicione usuários externos ao grupo do Office 365 para o site da equipe. Você precisará primeiro adicionar a conta como um usuário B2B no seu diretório. Pode levar algumas horas para o [cache de associação de grupo pelo Azure Rights Management](https://docs.microsoft.com/azure/information-protection/plan-design/prepare#group-membership-caching-by-azure-information-protection).  
 - Adicione contas de usuários externos diretamente à configuração do rótulo. Você pode adicionar todos os usuários de uma organização (por exemplo: Fabrikam.com), um grupo do Microsoft 365 (por exemplo: um grupo de finanças dentro de uma organização) ou um usuário individual. Por exemplo, você pode adicionar uma equipe externa de reguladores às permissões do seu rótulo de confidencialidade.

## <a name="see-also"></a>Confira também

[Diretrizes de segurança da Microsoft para campanhas políticas, instituições sem fins lucrativos e outras organizações do Agile](/security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[Adoção da nuvem e de soluções híbridas](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
