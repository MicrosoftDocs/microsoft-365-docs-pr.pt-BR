---
title: Ativar a Proteção contra Ameaças da Microsoft no centro de segurança do Microsoft 365
description: Saiba como habilitar a Proteção contra Ameaças da Microsoft e iniciar a integração do seu incidente de segurança e resposta.
keywords: introdução, habilitar MTP, proteção contra ameaças da Microsoft, M365, segurança, local dos dados, permissões necessárias, qualificação para licença, página Configurações
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 8f966060ebc9a30166647b397b93f2b45356df74
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083712"
---
# <a name="turn-on-microsoft-threat-protection"></a>Habilitar a Proteção contra Ameaças da Microsoft

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

A Proteção contra Ameaças da Microsoft unifica o processo de resposta a incidentes, integrando os principais recursos da Proteção Avançada contra Ameaças da Microsoft (ATP), da ATP do Office 365, do Microsoft Cloud App Security e da ATP do Azure. Essa experiência unificada adiciona recursos avançados que podem acessados no centro de segurança do Microsoft 365.

## <a name="check-license-eligibility-and-required-permissions"></a>Verificar a qualificação de licenças e as permissões necessárias
Os clientes com o Microsoft 365 e5, a Microsoft 365 E5 Security ou uma combinação equivalente de licenças podem usar a proteção contra ameaças da Microsoft. Para obter mais informações [leia os requisitos de licenciamento](prerequisites.md#licensing-requirements).

Você deve ser um **administrador global** ou um **administrador de segurança** no [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) para ativar a proteção contra ameaças da Microsoft.

## <a name="start-using-the-service"></a>Começar a usar o serviço
A proteção contra ameaças da Microsoft agrega dados dos vários serviços integrados. Ele processará e armazenará dados centralmente para identificar novas insights e tornar os fluxos de trabalho de resposta centralizados possíveis.

Antes de ativar o serviço, o centro de segurança do Microsoft 365 ([Security.Microsoft.com](https://security.microsoft.com)) não mostra os **incidentes** e as opções da **central de ações** no painel de navegação.

![Imagem do painel de navegação do centro de segurança do Microsoft 365 sem](../../media/mtp-off.png)
o Microsoft Threat Protection recursos*Microsoft 365 Security Center com a proteção contra ameaças da Microsoft desativada*

Para ativar a proteção contra ameaças da Microsoft, selecione **configurações** no painel de navegação. Na **[página Configurações](https://security.microsoft.com/settings)**, vá para**aceitação/** aceitação de **proteção** > contra ameaças da Microsoft.

>[!NOTE]
>Se você não vir **as configurações** no painel de navegação ou não conseguir acessar a página, verifique suas permissões e licenças.

### <a name="select-data-center-location"></a>Selecionar local do Data Center
Se o Microsoft Defender ATP tiver sido provisionado para sua organização, os dados serão armazenados e processados no mesmo local do data center que você selecionou para [os dados do Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy). Caso não tenha o Microsoft Defender ATP, será solicitado que você escolha um novo local de data center especificamente para a Proteção contra Ameaças da Microsoft. 

Você precisa fornecer consentimento antes que os dados sejam compartilhados entre os serviços e agregados.

### <a name="confirm-that-the-service-is-on"></a>Confirmar se o serviço está ativado
Depois que o serviço é provisionado, ele adiciona:

- [Gerenciamento de incidentes](incidents-overview.md)
- Uma central de ações para gerenciar [investigações e respostas automatizadas](mtp-autoir.md)
- Recursos de [Busca avançada](advanced-hunting-overview.md) para as páginas de **Busca** existentes

![Imagem do painel de navegação do centro de segurança do Microsoft 365 com](../../media/mtp-on.png)
o Microsoft Threat Protection apresenta a*central de segurança da Microsoft 365 com gerenciamento de incidentes e outros recursos de proteção contra ameaças da Microsoft*

### <a name="getting-azure-atp-data"></a>Obter dados da ATP do Azure
Para compartilhar dados da ATP do Azure com a Proteção contra Ameaças da Microsoft, verifique se a integração do Microsoft Cloud App Security e da ATP do Azure está ativada. [Saiba mais sobre esta integração](https://docs.microsoft.com/cloud-app-security/aatp-integration) 


## <a name="turn-off-microsoft-threat-protection"></a>Desabilitar a Proteção contra Ameaças da Microsoft
Para parar de usar o serviço de Proteção contra Ameaças da Microsoft, vá para **Configurações** > ** Proteção contra Ameaças da Microsoft** > **Aceitar/Recusar** no centro de segurança do Microsoft 365. Desmarque a opção **Ativar a Proteção contra Ameaças da Microsoft** e salve as alterações.

Os dados serão excluídos permanentemente e os recursos correspondentes serão removidos da central de segurança do Microsoft 365.

## <a name="get-assistance"></a>Obter assistência

A equipe de suporte da Microsoft pode ajudar a provisionar ou desprovisionar o serviço e os recursos relacionados em seu locatário. Para obter ajuda, selecione **precisa de ajuda?** no centro de segurança do Microsoft 365. Ao entrar em contato com o suporte, mencione a proteção contra ameaças da Microsoft.

## <a name="related-topics"></a>Tópicos relacionados

- [Visão geral da Proteção contra Ameaças da Microsoft](microsoft-threat-protection.md)
- [Requisitos de licenciamento e outros pré-requisitos](prerequisites.md)
- [Visão geral do Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Visão geral da ATP do Office 365](../office-365-security/office-365-atp.md)
- [Visão geral do Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Visão geral da ATP do Azure](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Armazenamento de dados da ATP do Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
