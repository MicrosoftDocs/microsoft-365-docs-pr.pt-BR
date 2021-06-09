---
title: Torne-se um parceiro do Microsoft Defender para Ponto de Extremidade
ms.reviewer: ''
description: Saiba as etapas e requisitos para integrar sua solução com o Microsoft Defender para Ponto de Extremidade e ser um parceiro
keywords: partner, integration, solution validation, certification, requirements, member, misa, application portal
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 35ba1fe85fa9b62770142636d46303b37534b976
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893312"
---
# <a name="become-a-microsoft-defender-for-endpoint-partner"></a>Torne-se um parceiro do Microsoft Defender para Ponto de Extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Para se tornar um parceiro de solução do Defender para Ponto de Extremidade, você precisará seguir e concluir as etapas a seguir.

## <a name="step-1-subscribe-to-a-microsoft-defender-for-endpoint-developer-license"></a>Etapa 1: Inscrever-se em uma licença do Microsoft Defender for Endpoint Developer
Inscreva-se na [licença do Microsoft Defender for Endpoint Developer](https://winatpregistration-prd.trafficmanager.net/Developer/UserAgreement?Length=9). A assinatura permite que você use um locatário do Microsoft Defender para Ponto de Extremidade com até 10 dispositivos para desenvolver soluções que se integram ao Microsoft Defender para Ponto de Extremidade. 

## <a name="step-2-fulfill-the-solution-validation-and-certification-requirements"></a>Etapa 2: atender aos requisitos de validação e certificação de solução
A melhor maneira para os parceiros de tecnologia certificarem que sua integração funciona é fazer com que [](https://securitycenter.microsoft.com/interoperability/partners) um cliente comum aprove o design de integração sugerido (o cliente pode usar a opção Recomendar um parceiro na página Aplicativo de Parceiro no Central de Segurança do Microsoft Defender) e testá-lo e rebaixá-lo para **a** equipe do Microsoft Defender para Ponto de Extremidade.

Depois que a equipe do Microsoft Defender for Endpoint analisar e aprovar a integração, direcionaremos você para ser incluído como parceiro na Associação de Segurança Inteligente da Microsoft.

## <a name="step-3-become-a--microsoft-intelligent-security-association-member"></a>Etapa 3: tornar-se membro da Associação de Segurança Inteligente da Microsoft
[A Associação de Segurança](https://www.microsoft.com/security/partnerships/intelligent-security-association) Inteligente da Microsoft é um programa especificamente para parceiros de segurança da Microsoft para ajudar a enriquecer seus produtos de segurança e melhorar a capacidade de descoberta do cliente de suas integrações com produtos de segurança da Microsoft.

## <a name="step-4-get-listed-in-the-microsoft-defender-for-endpoint-partner-application-portal"></a>Etapa 4: Obter listada no portal de aplicativos de parceiro do Microsoft Defender para Ponto de Extremidade
O Microsoft Defender for Endpoint oferece suporte à descoberta [](partner-applications.md) e integração de aplicativos de terceiros usando a página de parceiro no produto inserida no portal de gerenciamento do Microsoft Defender for Endpoint. 

Para que sua empresa seja listada como um parceiro na página do parceiro no produto, você precisará fornecer as seguintes informações:

1. Um logotipo quadrado (SVG).
2. Nome do produto a ser apresentado.
3. Forneça uma descrição do produto de 15 palavras.
4. Link para a página inicial do cliente para concluir a integração ou postagem de blog que incluirá informações suficientes para os clientes. Qualquer comunicado de imprensa, incluindo o nome do produto do Microsoft Defender for Endpoint, deve ser revisado pelas equipes de marketing e engenharia. Aguarde pelo menos 10 dias para que o processo de revisão seja feito.
5.  Se você usar uma abordagem do Azure AD com vários locatários, será necessário o nome do aplicativo do Azure AD para controlar o uso do aplicativo.
6. Inclua o campo User-Agent em cada chamada de API feita ao Microsoft Defender para o conjunto público de APIs de ponto de extremidade ou APIs de segurança Graph. Isso será usado para fins estatísticos, solução de problemas e reconhecimento de parceiros. Além disso, esta etapa é um requisito para associação no MisA (Associação de Segurança Inteligente da Microsoft).

    Siga estas etapas:
    
    - De definir User-Agent campo em cada cabeçalho de solicitação HTTP para o formato abaixo.

    - `MdePartner-{CompanyName}-{ProductName}/{Version}`
    
    - Por exemplo, User-Agent: `MdePartner-Contoso-ContosoCognito/1.0.0`
    
    - Para obter mais informações, [consulte RFC 2616 section-14.43](https://tools.ietf.org/html/rfc2616#section-14.43).

As parcerias com o Microsoft Defender para Ponto de Extremidade ajudam nossos clientes mútuos a simplificar, integrar e orquestrar ainda mais as defesas. Estamos felizes por você ter escolhido se tornar um parceiro do Microsoft Defender para Ponto de Extremidade e alcançar nosso objetivo comum de proteger efetivamente os clientes e seus ativos, impedindo e respondendo a ameaças modernas juntos.

## <a name="related-topics"></a>Tópicos relacionados
- [Oportunidades para parceiros técnicos](partner-integration.md)
