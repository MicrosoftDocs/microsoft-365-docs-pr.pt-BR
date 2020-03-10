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
ms.openlocfilehash: fa970b28939ad43bf6a2717e603013277bc9130f
ms.sourcegitcommit: cc3b64a91e16ccdaa9c338b9a9056dbe3963ba9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/10/2020
ms.locfileid: "42569174"
---
# <a name="turn-on-microsoft-threat-protection"></a>Habilitar a Proteção contra Ameaças da Microsoft

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

A Proteção contra Ameaças da Microsoft unifica o processo de resposta a incidentes, integrando os principais recursos da Proteção Avançada contra Ameaças da Microsoft (ATP), da ATP do Office 365, do Microsoft Cloud App Security e da ATP do Azure. Essa experiência unificada adiciona recursos avançados que podem acessados no centro de segurança do Microsoft 365.

Para obter a melhor proteção e otimizar a proteção contra ameaças da Microsoft, recomendamos implantar todos os serviços compatíveis em sua rede. Para obter mais informações, [Leia sobre a implantação de serviços com suporte](deploy-supported-services.md).

## <a name="check-license-eligibility-and-required-permissions"></a>Verificar a qualificação de licenças e as permissões necessárias
Uma licença do Microsoft 365 e5, E5 Security ou a5 ou uma combinação válida de licenças oferece acesso a serviços com suporte e concede a você o uso da proteção contra ameaças da Microsoft na central de segurança da Microsoft 365.

Para obter informações detalhadas sobre licenciamento, [Leia os requisitos de licenciamento](prerequisites.md#licensing-requirements).

### <a name="check-your-role"></a>Verificar sua função
Você deve ser um **administrador global** ou um **administrador de segurança** no Azure Active Directory para ativar a proteção contra ameaças da Microsoft. [Exibir suas funções no Azure AD](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="start-using-the-service"></a>Começar a usar o serviço
A proteção contra ameaças da Microsoft agrega dados dos vários serviços integrados. Ele processará e armazenará dados centralmente para identificar novas insights e tornar os fluxos de trabalho de resposta centralizados possíveis.

Antes de ativar o serviço, o centro de segurança do Microsoft 365 ([Security.Microsoft.com](https://security.microsoft.com)) mostra a página de boas-vindas da proteção contra ameaças da Microsoft ao selecionar **incidentes**, a **central de ações**ou a **busca** no painel de navegação. Essas opções de navegação não são mostradas se você não estiver qualificado para usar a proteção contra ameaças da Microsoft.

![Imagem da página de boas-vindas da proteção contra ameaças da Microsoft mostra se a proteção](../../media/mtp-welcome.png)
contra ameaças da Microsoft não foi ativada na*página de boas-vindas do Microsoft 365 Security Center*

Para ativar a proteção contra ameaças da Microsoft, basta concluir o processo na página de boas-vindas. Você também pode ativar a proteção contra ameaças da Microsoft acessando **configurações** ([Security.Microsoft.com/Settings](https://security.microsoft.com/settings)) no painel de navegação e selecionando **proteção contra ameaças da Microsoft**.

>[!NOTE]
>Se você não vir **as configurações** no painel de navegação ou não conseguir acessar a página, verifique suas permissões e licenças.

### <a name="select-data-center-location"></a>Selecionar local do Data Center
Se o Microsoft Defender ATP tiver sido provisionado para sua organização, os dados serão armazenados e processados no mesmo local do data center que você selecionou para [os dados do Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy). Caso não tenha o Microsoft Defender ATP, será solicitado que você escolha um novo local de data center especificamente para a Proteção contra Ameaças da Microsoft. 

Você precisa fornecer consentimento antes que os dados sejam compartilhados entre os serviços e agregados.

### <a name="confirm-that-the-service-is-on"></a>Confirmar se o serviço está ativado
Depois que o serviço é provisionado, ele adiciona:

- [Gerenciamento de incidentes](incidents-overview.md)
- Uma central de ações para gerenciar [investigações e respostas automatizadas](mtp-autoir.md)
- Recursos [avançados de busca](advanced-hunting-overview.md)

![Imagem do painel de navegação do centro de segurança do Microsoft 365 com](../../media/mtp-on.png)
o Microsoft Threat Protection apresenta a*central de segurança da Microsoft 365 com gerenciamento de incidentes e outros recursos de proteção contra ameaças da Microsoft*

### <a name="getting-azure-atp-data"></a>Obter dados da ATP do Azure
Para compartilhar dados da ATP do Azure com a Proteção contra Ameaças da Microsoft, verifique se a integração do Microsoft Cloud App Security e da ATP do Azure está ativada. [Saiba mais sobre esta integração](https://docs.microsoft.com/cloud-app-security/aatp-integration) 


## <a name="turn-off-microsoft-threat-protection"></a>Desabilitar a Proteção contra Ameaças da Microsoft
Para parar de usar o serviço de Proteção contra Ameaças da Microsoft, vá para **Configurações** > ** Proteção contra Ameaças da Microsoft** > **Aceitar/Recusar** no centro de segurança do Microsoft 365. Desmarque a opção **Ativar a Proteção contra Ameaças da Microsoft** e salve as alterações.

Os recursos correspondentes serão removidos da central de segurança do Microsoft 365.

## <a name="get-assistance"></a>Obter assistência

A equipe de suporte da Microsoft pode ajudar a provisionar ou desprovisionar o serviço e os recursos relacionados em seu locatário. Para obter ajuda, selecione **precisa de ajuda?** no centro de segurança do Microsoft 365. Ao entrar em contato com o suporte, mencione a proteção contra ameaças da Microsoft.

## <a name="related-topics"></a>Tópicos relacionados

- [Visão geral da Proteção contra Ameaças da Microsoft](microsoft-threat-protection.md)
- [Requisitos de licenciamento e outros pré-requisitos](prerequisites.md)
- [Implantar serviços com suporte](deploy-supported-services.md)
- [Visão geral do Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Visão geral da ATP do Office 365](../office-365-security/office-365-atp.md)
- [Visão geral do Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Visão geral da ATP do Azure](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Armazenamento de dados da ATP do Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
