---
title: Privacidade e armazenamento de dados do Microsoft Defender para Ponto de Extremidade
description: Saiba como o Microsoft Defender for Endpoint lida com privacidade e dados coletados.
keywords: Microsoft Defender para Ponto de Extremidade, Microsoft Defender ATP, armazenamento de dados e privacidade, armazenamento, privacidade, licenciamento, localização geográfica, retenção de dados, dados
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
ms.openlocfilehash: 228a8813bcfff052c7f861dcd2962a94cb58c0fb
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165960"
---
# <a name="microsoft-defender-for-endpoint-data-storage-and-privacy"></a>Privacidade e armazenamento de dados do Microsoft Defender para Ponto de Extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Esta seção aborda algumas das perguntas mais frequentes sobre privacidade e tratamento de dados para o Defender para Ponto de Extremidade.
> [!NOTE]
> Este documento explica os detalhes de armazenamento de dados e privacidade relacionados ao Defender for Endpoint. Para obter mais informações relacionadas ao Defender para Ponto de Extremidade e a outros produtos e serviços, como o Microsoft Defender Antivírus e o Windows 10, consulte [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=827576). Consulte também Perguntas frequentes sobre privacidade do [Windows 10](https://go.microsoft.com/fwlink/?linkid=827577) para obter mais informações.


## <a name="what-data-does-microsoft-defender-for-endpoint-collect"></a>Quais dados o Microsoft Defender for Endpoint coleta?

O Microsoft Defender for Endpoint coletará e armazenará informações de seus dispositivos configurados em um locatário dedicado e segregado do cliente específico do serviço para fins de administração, rastreamento e relatório. 

As informações coletadas incluem dados de arquivo (como nomes de arquivo, tamanhos e hashes), dados de processo (processos em execução, hashes), dados do Registro, dados de conexão de rede (IPs de host e portas) e detalhes do dispositivo (como identificadores de dispositivo, nomes e a versão do sistema operacional).

A Microsoft armazena esses dados com segurança no Microsoft Azure e os mantém de acordo com as práticas de privacidade da Microsoft e com as políticas do Centro de [Confiação da Microsoft.](https://go.microsoft.com/fwlink/?linkid=827578)

Esses dados permitem que o Defender para o Ponto de Extremidade:
- Identificar proativamente indicadores de ataque (IOAs) em sua organização
- Gerar alertas se um possível ataque foi detectado
- Forneça às suas operações de segurança uma exibição em dispositivos, arquivos e URLs relacionadas a sinais de ameaça de sua rede, permitindo que você investigue e explore a presença de ameaças de segurança na rede.

A Microsoft não usa seus dados para publicidade.

## <a name="data-protection-and-encryption"></a>Proteção e criptografia de dados
O serviço Defender para Ponto de Extremidade utiliza tecnologias de proteção de dados de última geração que se baseiam na infraestrutura do Microsoft Azure. 

Há vários aspectos relevantes para a proteção de dados que nosso serviço cuida. A criptografia é uma das mais críticas e inclui criptografia de dados em repouso, criptografia em voo e gerenciamento de chaves com o Key Vault. Para obter mais informações sobre outras tecnologias usadas pelo serviço Defender for Endpoint, consulte Visão geral da [criptografia do Azure.](https://docs.microsoft.com/azure/security/security-azure-encryption-overview) 

Em todos os cenários, os dados são criptografados usando a criptografia [AES](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard) de 256 bits no mínimo.


## <a name="data-storage-location"></a>Local de armazenamento de dados

O Defender for Endpoint opera nos datacenters do Microsoft Azure na União Europeia, no Reino Unido ou nos Estados Unidos. Os dados do cliente coletados pelo serviço podem ser armazenados em: (a) a localização geográfica do locatário conforme identificado durante o provisionamento ou, (b) se o Defender for Endpoint usa outro serviço online da Microsoft para processar esses dados, a localização geográfica conforme definido pelas regras de armazenamento de dados desse outro serviço online.

Os dados do cliente em formato pseudonimizado também podem ser armazenados nos sistemas de armazenamento e processamento central nos Estados Unidos.

Depois de configurado, você não pode alterar o local onde seus dados estão armazenados. Isso fornece uma maneira conveniente de minimizar o risco de conformidade selecionando ativamente os locais geográficos onde seus dados residirão. 

## <a name="is-my-data-isolated-from-other-customer-data"></a>Meus dados estão isolados de outros dados do cliente?
Sim, seus dados são isolados por meio da autenticação de acesso e da segregação lógica com base no identificador do cliente. Cada cliente só pode acessar dados coletados de sua própria organização e dados genéricos que a Microsoft fornece.

## <a name="how-does-microsoft-prevent-malicious-insider-activities-and-abuse-of-high-privilege-roles"></a>Como a Microsoft impede atividades internas mal-intencionadas e abuso de funções de alto privilégio?

Os desenvolvedores e administradores da Microsoft receberam, por design, privilégios suficientes para executar suas obrigações atribuídas para operar e desenvolver o serviço. A Microsoft implanta combinações de controles preventivos, detetives e reativos, incluindo os seguintes mecanismos para ajudar a proteger contra desenvolvedores não autorizados e/ou atividades administrativas:

- Controle de acesso rígido a dados confidenciais
- Combinações de controles que aprimoram muito a detecção independente de atividades mal-intencionadas
- Vários níveis de monitoramento, registro em log e relatórios

Além disso, a Microsoft realiza verificações de verificação em segundo plano de determinadas equipes de operações e limita o acesso a aplicativos, sistemas e infraestrutura de rede em proporção ao nível de verificação em segundo plano. A equipe de operações segue um processo formal quando é necessário acessar a conta de um cliente ou informações relacionadas no desempenho de suas obrigações.

O acesso aos dados para serviços implantados nos data centers do Microsoft Azure Government só é concedido a funcionários operacionais que foram selecionados e aprovados para lidar com dados sujeitos a determinados regulamentos e requisitos governamentais, como FedRAMP, NIST 800.171 (DIB), ITAR, IRS 1075, DoD L4 e CJIS.


## <a name="is-data-shared-with-other-customers"></a>Os dados são compartilhados com outros clientes?
Não. Os dados do cliente são isolados de outros clientes e não são compartilhados. No entanto, informações sobre os dados resultantes do processamento da Microsoft e que não contêm dados específicos do cliente podem ser compartilhadas com outros clientes. Cada cliente só pode acessar dados coletados de sua própria organização e dados genéricos que a Microsoft fornece.

## <a name="how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy"></a>Por quanto tempo a Microsoft armazenará meus dados? Qual é a política de retenção de dados da Microsoft?
**Integração de serviço**<br>
Você pode escolher a política de retenção de dados para seus dados. Isso determina por quanto tempo o Window Defender for Endpoint armazenará seus dados. Há uma flexibilidade de escolher no intervalo de um mês a seis meses para atender às necessidades de conformidade regulamentar da sua empresa.

**Na rescisão ou expiração do contrato**<br>
Seus dados serão mantidos e estarão disponíveis enquanto a licença estiver em período de carência ou no modo suspenso. No final desse período, esses dados serão apagados dos sistemas da Microsoft para torná-los irrecuperáveis, no máximo 180 dias após a rescisão ou expiração do contrato.


## <a name="can-microsoft-help-us-maintain-regulatory-compliance"></a>A Microsoft pode nos ajudar a manter a conformidade regulamentar?

A Microsoft fornece aos clientes informações detalhadas sobre os programas de segurança e conformidade da Microsoft, incluindo relatórios de auditoria e pacotes de conformidade, para ajudar os clientes a avaliar o Defender para serviços de Ponto de Extremidade em relação aos seus próprios requisitos legais e regulamentados. O Defender for Endpoint atingiu várias certificações, incluindo ISO, SOC, FedRAMP High e PCI e continua a buscar certificações nacionais, regionais e específicas do setor adicionais.

Ao fornecer aos clientes serviços compatíveis e verificados independentemente, a Microsoft facilita a conformidade dos clientes com a infraestrutura e os aplicativos executados.

Para obter mais informações sobre os relatórios de certificação do Defender for Endpoint, consulte [Microsoft Trust Center](https://servicetrust.microsoft.com/). 

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-datastorage-belowfoldlink) 
