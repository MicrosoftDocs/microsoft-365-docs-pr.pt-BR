---
title: Visão geral do gerenciamento e APIs
ms.reviewer: ''
description: Saiba mais sobre as ferramentas de gerenciamento e categorias de API no Microsoft Defender para Ponto de Extremidade
keywords: integração, api, siem, rbac, acesso, portal, integração, investigação, resposta, entidades, entidades, contexto do usuário, contexto do aplicativo, streaming
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: 34fb58c2e32f69cda064bb6db4b180c78ba5d451
ms.sourcegitcommit: f0118e61e490496cb23189cc5c73b23e2ba939be
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2021
ms.locfileid: "52780148"
---
# <a name="overview-of-management-and-apis"></a>Visão geral do gerenciamento e APIs 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mgt-apis-abovefoldlink)


O Defender for Endpoint oferece suporte a uma ampla variedade de opções para garantir que os clientes possam adotar facilmente a plataforma. 

Reconhecendo que os ambientes e estruturas do cliente podem variar, o Defender for Endpoint foi criado com flexibilidade e controle granular para se ajustar a requisitos variados do cliente. 

## <a name="endpoint-onboarding-and-portal-access"></a>Integração do ponto de extremidade e acesso ao portal 

A integração de dispositivos está totalmente integrada ao Microsoft Endpoint Manager e Microsoft Intune para dispositivos cliente e ao Azure Defender para dispositivos de servidor, fornecendo uma experiência completa de configuração, implantação e monitoramento. Além disso, o Microsoft Defender para Ponto de Extremidade oferece suporte à Política de Grupo e outras ferramentas de terceiros usadas para gerenciamento de dispositivos.

O Defender para Ponto de Extremidade fornece controle fino sobre o que os usuários com acesso ao portal podem ver e fazer por meio da flexibilidade do controle de acesso baseado em função (RBAC). O modelo RBAC dá suporte a todos os sabores da estrutura de equipes de segurança:
- Organizações e equipes de segurança distribuídas globalmente
- Equipes de operações de segurança de modelo hierárqueo
- Divisões totalmente segregadas com equipes de operações globais de segurança centralizadas simples 

## <a name="available-apis"></a>APIs disponíveis
A solução do Microsoft Defender para Ponto de Extremidade foi criada sobre uma plataforma pronta para integração.

O Defender for Endpoint expõe grande parte de seus dados e ações por meio de um conjunto de APIs programáticas. Essas APIs permitirão que você automatize fluxos de trabalho e inove com base nos recursos do Defender para Ponto de Extremidade.

![Imagem da API disponível e integração no Microsoft Defender para Ponto de Extremidade](images/mdatp-apis.png)  

As APIs do Defender para Ponto de Extremidade podem ser agrupadas em três:
- APIs do Microsoft Defender para Ponto de Extremidade 
- API de streaming de dados não processados
- Integração SIEM

## <a name="microsoft-defender-for-endpoint-apis"></a>APIs do Microsoft Defender para Ponto de Extremidade

O Defender for Endpoint oferece um modelo de API em camadas expondo dados e recursos em um modelo estruturado, claro e fácil de usar, exposto por meio de um modelo de autorização e autenticação padrão baseado no Azure AD que permite o acesso no contexto de usuários ou aplicativos SaaS. O modelo de API foi projetado para expor entidades e recursos de forma consistente. 

Assista a este vídeo para uma visão geral rápida do Defender para APIs do Ponto de Extremidade. 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

A **API** de Investigação expõe a riqueza do Defender para o Ponto de Extremidade - expondo entidades calculadas ou 'perfilada' (por exemplo, dispositivo, usuário e arquivo) e eventos discretos (por exemplo, criação de processo e criação de arquivo) que normalmente descreve um comportamento relacionado a uma entidade, permitindo o acesso a dados por meio de interfaces de investigação permitindo um acesso baseado em consulta aos dados. Para obter mais informações, consulte [APIs com suporte.](exposed-apis-list.md)

A **API** de Resposta expõe a capacidade de tomar ações no serviço e em dispositivos, permitindo que os clientes ingeram indicadores, gerenciem configurações, status de alerta, bem como ações de resposta em dispositivos programaticamente, como isolar dispositivos da rede, arquivos de quarentena e outros. 

## <a name="raw-data-streaming-api"></a>API de streaming de dados não processados 
A API de streaming de dados brutos do Defender for Endpoint oferece a capacidade para os clientes enviarem eventos e alertas em tempo real de suas instâncias conforme ocorrem em um único fluxo de dados, fornecendo um mecanismo de entrega de alta taxa de transferência de baixa latência.

As informações do evento Defender for Endpoint são empurradas diretamente para o armazenamento do Azure para retenção de dados de longo prazo ou para hubs de eventos do Azure para consumo por serviços de visualização ou mecanismos de processamento de dados adicionais. 

Para obter mais informações, consulte [RAW data streaming API](raw-data-export.md).

A nova Microsoft 365 API de Streaming do Defender inclui eventos de email e alerta, além de eventos de dispositivo. Para obter mais informações, [consulte Microsoft 365 API de Streaming do Defender.](../defender/streaming-api.md)


## <a name="siem-api"></a>SIEM API
Quando você habilita a integração de informações de segurança e gerenciamento de eventos (SIEM), ele permite que você retire detecções do Central de Segurança do Microsoft Defender usando sua solução SIEM ou conectando-se diretamente à API REST de detecções. Isso ativa a seção detalhes de acesso do conector SIEM com valores pré-preenchidos e um aplicativo é criado em seu locatário Azure Active Directory (Azure AD). Para obter mais informações, consulte [Integração siem](enable-siem-integration.md).

## <a name="related-topics"></a>Tópicos relacionados
- [Acessar as APIs do Microsoft Defender para Pontos de Extremidade ](apis-intro.md)
- [APIs com suporte](exposed-apis-list.md)
- [Oportunidades para parceiros técnicos](partner-integration.md)

