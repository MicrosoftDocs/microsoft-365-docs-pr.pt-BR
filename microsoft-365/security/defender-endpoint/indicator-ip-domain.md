---
title: Criar indicadores para IPs e URLs/domínios
ms.reviewer: ''
description: Crie indicadores para IPs e URLs/domínios que definem a detecção, prevenção e exclusão de entidades.
keywords: ip, url, domínio, gerenciar, permitido, bloqueado, bloqueado, limpo, mal-intencionado, hash de arquivo, endereço ip, urls, domínio
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e7dc11fe709a6d04b6309706df90f0ebbc177e25
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841061"
---
# <a name="create-indicators-for-ips-and-urlsdomains"></a>Criar indicadores para IPs e URLs/domínios 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



> [!TIP]
> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


O Defender for Endpoint pode bloquear o que a Microsoft considera como IPs/URLs mal-intencionadas, por meio do Windows Defender SmartScreen para navegadores Microsoft e por meio da Proteção de Rede para navegadores que não são da Microsoft ou chamadas feitas fora de um navegador.

O conjunto de dados de inteligência de ameaças para isso foi gerenciado pela Microsoft.

Ao criar indicadores para IPs e URLs ou domínios, agora você pode permitir ou bloquear IPs, URLs ou domínios com base em sua própria inteligência contra ameaças. Você pode fazer isso por meio da página de configurações ou por grupos de máquinas se você considera que determinados grupos estão mais ou menos em risco do que outros.

> [!NOTE]
> Não há suporte Inter-Domain de roteamento sem classe (CIDR) para endereços IP. 

### <a name="before-you-begin"></a>Antes de começar
É importante entender os seguintes pré-requisitos antes da criação de indicadores para IPS, URLs ou domínios:
- A URL/IP permite e bloqueia depende da Proteção de Rede do componente Defender for Endpoint a ser habilitada no modo de bloqueio. Para obter mais informações sobre as instruções de configuração e proteção de rede, consulte [Enable network protection](enable-network-protection.md).
- A versão do cliente Antimalware deve ser 4.18.1906.x ou posterior. 
- Com suporte em máquinas Windows 10, versão 1709 ou posterior. 
- Verifique se **os indicadores de rede personalizados** estão habilitados **Central de Segurança do Microsoft Defender > Configurações > recursos avançados.** Para obter mais informações, consulte [Recursos avançados](advanced-features.md).
- Para dar suporte a indicadores no iOS, consulte [Configure custom indicators](/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators).


> [!IMPORTANT]
> Somente IPs externos podem ser adicionados à lista de indicadores. Os indicadores não podem ser criados para IPs internos.
> Para cenários de proteção da Web, recomendamos usar os recursos integrados no Microsoft Edge. Microsoft Edge aproveita a Proteção de [Rede](network-protection.md) para inspecionar o tráfego de rede e permite blocos para TCP, HTTP e HTTPS (TLS). Se houver políticas de indicador de URL conflitantes, o caminho mais longo será aplicado. Por exemplo, a política de indicador de URL `https:\\support.microsoft.com/en-us/office` tem precedência sobre a política de indicador de URL `https:\\support.microsoft.com` .

> [!NOTE]
> Para todos os outros processos, os cenários de proteção da Web aproveitam a Proteção de Rede para inspeção e imposição: 
> - O IP tem suporte para todos os três protocolos
> - Somente endereços IP únicos são suportados (sem blocos CIDR ou intervalos IP)
> - URLs criptografadas (caminho completo) só podem ser bloqueadas em navegadores de primeira parte (Internet Explorer, Borda)
> - URLS criptografadas (somente FQDN) podem ser bloqueadas fora de navegadores de primeira parte (Internet Explorer, Borda)
> - Os blocos de caminho de URL completos podem ser aplicados no nível de domínio e em todas as URLs não criptografadas
 
> [!NOTE]
> Pode haver até 2 horas de latência (geralmente menos) entre o momento em que a ação é realizada e a URL e o IP sendo bloqueados. 

### <a name="create-an-indicator-for-ips-urls-or-domains-from-the-settings-page"></a>Criar um indicador para IPs, URLs ou domínios na página de configurações

1. No painel de navegação, selecione **Configurações**  >  **Indicadores**.  

2. Selecione a **guia Endereços IP ou URLs/Domínios.**

3. Selecione **Adicionar item**.

4. Especifique os seguintes detalhes:
   - Indicador - Especifique os detalhes da entidade e defina a expiração do indicador.
   - Ação - Especifique a ação a ser tomada e forneça uma descrição.
   - Escopo - Definir o escopo do grupo de máquinas.

5. Revise os detalhes na guia Resumo e clique em **Salvar**.

## <a name="related-topics"></a>Tópicos relacionados
- [Criar indicadores](manage-indicators.md)
- [Criar indicadores para arquivos](indicator-file.md)
- [Criar indicadores com base em certificados](indicator-certificates.md)
- [Gerenciar indicadores](indicator-manage.md)
