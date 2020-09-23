---
title: Requisitos de localização de dados pessoais em Russo
description: Saiba como coletar dados pessoais, gravação de dados pessoais do cidadãos da Rússia, systematization, acúmulo, armazenamento, esclarecimento e extração são executados nos serviços e bancos de dados da Microsoft localizados na Rússia.
keywords: Microsoft 365, conformidade, ofertas
localization_priority: None
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: 29c56d525375162926d34bd298bbbd660964438d
ms.sourcegitcommit: e5ac81132cc5fd248350627a3cc7b3c640f53b6e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48208153"
---
# <a name="russian-personal-data-localization-requirements"></a>Requisitos de localização de dados pessoais em Russo

A partir de 1º de setembro de 2015, as organizações que são consideradas operadores de dados pessoais devem garantir que, ao coletar dados pessoais, a gravação de dados pessoais do cidadãos da Rússia, o systematization, o acúmulo, o armazenamento, os esclarecimentos (atualização, alteração) e a extração sejam realizados por meio dos bancos de dados localizados na Rússia (requisito de localização de dados pessoais). <sup>1</sup>

Os serviços online da Microsoft disponíveis para organizações (incluindo, mas não se limitar a instituições educacionais) (hereinafter referidos como ' cliente '), incluindo aqueles que permitem o processamento de dados pessoais, como Microsoft Azure, Microsoft 365, Dynamics 365 e a plataforma de energia, são fornecidos de centros de processamento de dados localizados fora da Rússia (para mais informações, visite a [central de confiabilidade da Microsoft](https://www.microsoft.com/trust-center)).

Com base no tipo e conteúdo das informações processadas pelos sistemas de informações do cliente, esses sistemas, incluindo aqueles que usam os produtos da Microsoft em nuvem, podem ser considerados um sistema de informações de dados pessoais (' PDIS ', ' ISPD '). Nos casos em que o cliente gostaria de usar o Microsoft Online Services em um sistema que se qualifica como o PDIS por meio da arquitetura e dos tipos de informações processados, a Microsoft convida seus clientes para considerar, entre outras coisas, as soluções disponíveis especificadas abaixo. Todos os cenários fornecidos estão disponíveis para os clientes como uma opção adicional para ofertas de negócios padrão.

Deve-se observar que é o cliente como operador de dados pessoais do PDIS, que é responsável pela conformidade e que deve analisar e avaliar os requisitos legais aplicáveis para localização de dados pessoais e, por sua própria, determinar, de forma independente, medidas suficientes para garantir que o processamento de dados pessoais no PDIS esteja em conformidade com a legislação de dados pessoais em Russo. <sup>2</sup>

## <a name="subscribing-to-microsoft-online-services"></a>Inscrever-se nos serviços online da Microsoft

### <a name="microsoft-id-management"></a>Gerenciamento de ID da Microsoft

A Microsoft solicita que os clientes considerem inscrever-se nos serviços online da Microsoft — Microsoft Azure, Microsoft 365, Dynamics 365 e plataforma de energia — por meio de um parceiro do Microsoft Cloud Solution Provider (CSP). Consulte esta [lista de parceiros de CSP](https://pinpoint.microsoft.com/search?type=services&campaign=691) para obter mais informações.

### <a name="managing-user-identity-and-access-for-microsoft-online-services"></a>Gerenciando identidades de usuário e acesso para serviços online da Microsoft

Para os serviços online da Microsoft, como o Microsoft Azure, o Microsoft 365, o Dynamics 365 e a plataforma de energia, a verificação e o gerenciamento de acesso do usuário são realizados por meio [do Azure Active Directory (AAD)](https://azure.microsoft.com/services/active-directory/). Observe que casos em que um cliente da Microsoft usa um sistema de gerenciamento de identificação local para serviços de nuvem da Microsoft (como o Windows Server Active Directory (AD) ou qualquer outro sistema de gerenciamento de ID), o cliente tem uma oportunidade de integrar rapidamente esse sistema ao Azure Active Directory (AAD) por meio do Azure AD Connect. Consulte a opção [Azure ad Connect](https://docs.microsoft.com/azure/active-directory/cloud-provisioning/) para obter mais informações. Os clientes da Microsoft também podem considerar o uso de aplicativos e soluções de fornecedores terceirizados para o gerenciamento de seus usuários e a integração do sistema de identificação local com o Azure AD.

## <a name="use-microsoft-compliance-manager-to-assess-your-risk"></a>Usar o gerente de conformidade da Microsoft para avaliar seus riscos

O [Gerenciador de conformidade da Microsoft](compliance-manager.md) é um recurso do centro de conformidade da [Microsoft 365](microsoft-365-compliance-center.md) para ajudá-lo a entender a postura de conformidade da sua organização e realizar ações para ajudar a reduzir os riscos. O gerente de conformidade oferece um modelo Premium para criar uma avaliação para esta regulamentação. Encontre o modelo na página **modelos de avaliação** no Gerenciador de conformidade. Saiba como [criar avaliações no Gerenciador de conformidade](compliance-manager-assessments.md).

## <a name="questions-and-support"></a>Perguntas e suporte

Para perguntas técnicas e de cobrança, consulte os recursos de suporte da Microsoft abaixo. Para outras perguntas ou esclarecimentos, entre em contato com a [equipe de privacidade](https://support.microsoft.com/gp/privacy-page)da Microsoft.

### <a name="microsoft-azure"></a>Microsoft Azure

- **Site**: [suporte do Microsoft Azure](https://aka.ms/GetAzureSupport)
- **Chamada gratuita**: 8 800 200 8001
- **Chamada local**: 495 916 7171
- **Suporte online**: enviar consultas pelo [portal do Azure](https://portal.azure.com)

### <a name="microsoft-365"></a>Microsoft 365

- **Chamada gratuita**: 8 10 800 2548 1044
- **Chamada local**: 499 922 8623
- **Suporte online**: enviar consultas através do [centro de administração](https://portal.office.com/)

### <a name="dynamics-365"></a>Dynamics 365

- **Chamada gratuita**: 8 10 800 2548 1044
- **Chamada local**: 499 922 8623
- **Suporte online**: enviar consultas através do [portal de suporte do Dynamics](https://dynamics.microsoft.com/support/)

### <a name="power-platform"></a>Plataforma de energia

- **Chamada gratuita**: 8 10 800 2548 1044
- **Chamada local**: 499 922 8623
- **Suporte online**: enviar consultas através do [suporte à plataforma de energia](https://docs.microsoft.com/power-platform/admin/get-help-support)

> [!NOTE]
> <sup>1</sup> n º de leis federais 242-FZ (edição com data de 12.31.2014) ' sobre a inserção de emendas em certas atitudes legislativas da Federação Russa sobre como esclarecer o procedimento para processamento de dados pessoais em redes de informações e de telecomunicações <br>
> <sup>2</sup> leis federais de no. 152-FZ em dados pessoais a partir de 7,27. 2006<br>
