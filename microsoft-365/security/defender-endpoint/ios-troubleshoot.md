---
title: Solucionar problemas e encontrar respostas sobre perguntas frequentes relacionadas ao Microsoft Defender para Ponto de Extremidade no iOS
description: Solução de problemas e perguntas frequentes - Microsoft Defender para Ponto de Extremidade no iOS
keywords: microsoft, defender, Microsoft Defender para Endpoint, ios, solução de problemas, perguntas frequentes, como
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
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b82b6993ce9ed5a3f0f3e6e13e8a260a185c9730
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194968"
---
# <a name="troubleshoot-issues-and-find-answers-to-faqs-on-microsoft-defender-for-endpoint-on-ios"></a>Solucionar problemas e encontrar respostas para perguntas frequentes no Microsoft Defender para Endpoint no iOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

Este tópico fornece informações de solução de problemas para ajudá-lo a resolver problemas que podem surgir à medida que você usa o Microsoft Defender para Ponto de Extremidade no iOS.



> [!NOTE]
> O Defender for Endpoint no iOS usaria uma VPN para fornecer o recurso de Proteção da Web. Esta não é uma VPN regular e é uma VPN local/auto-loop que não faz o tráfego fora do dispositivo.

## <a name="apps-dont-work-when-vpn-is-turned-on"></a>Os aplicativos não funcionam quando a VPN está conexões
Há alguns aplicativos que param de funcionar quando uma VPN ativa é detectada. Você pode desabilitar a VPN durante o tempo em que está usando esses aplicativos. 

Por padrão, o Defender para Ponto de Extremidade no iOS inclui e habilita o recurso de proteção da Web. [A proteção da Web](web-protection-overview.md) ajuda a proteger dispositivos contra ameaças da Web e proteger os usuários contra ataques de phishing. O Defender for Endpoint no iOS usa uma VPN para fornecer essa proteção. Observe que esta é uma VPN local e, ao contrário da VPN tradicional, o tráfego de rede não é enviado fora do dispositivo.

Embora habilitada por padrão, pode haver alguns casos que exigem que você desabilite a VPN. Por exemplo, você deseja executar alguns aplicativos que não funcionam quando uma VPN está configurada. Nesses casos, você pode optar por desabilitar a VPN do aplicativo no dispositivo seguindo as etapas abaixo:

1. Em seu dispositivo iOS, abra o aplicativo **Configurações,** clique ou toque em **Geral** **e,** em seguida, VPN .
1. Clique ou toque no botão "i" do Microsoft Defender para Ponto de Extremidade.
1. Desative o **Conexão Sob Demanda para** desabilitar a VPN.

    > [!div class="mx-imgBorder"]
    > ![Vpn config connect on demand](images/ios-vpn-config.png)

> [!NOTE]
> A Proteção da Web não estará disponível quando a VPN estiver desabilitada. Para habilitar a Proteção Web de novo, abra o aplicativo Microsoft Defender para Ponto de Extremidade no dispositivo e clique ou toque em **Iniciar VPN**.

## <a name="co-existence-with-multiple-vpn-profiles"></a>Co-existência com vários perfis VPN

O iOS da Apple não dá suporte a várias VPNs em **todo** o dispositivo para serem ativas simultaneamente. Embora vários perfis VPN possam existir no dispositivo, apenas uma VPN pode estar ativa por vez.

O Microsoft Defender para VPN de Ponto de Extremidade pode co-existir com outras VPNs configuradas como *por aplicativo* ou *"Pessoal"*.

## <a name="battery-consumption"></a>Consumo de bateria

No aplicativo Configurações, o iOS mostra apenas o uso da bateria de aplicativos que ficam visíveis para o usuário por um período específico de tempo. O uso da bateria por aplicativos mostrados na tela é apenas por esse período e é calculado pelo iOS com base em uma infinidade de fatores, incluindo o uso da CPU e da rede. O Microsoft Defender para Ponto de Extremidade usa uma VPN local/loop-back em segundo plano para verificar o tráfego da Web em busca de sites ou conexões mal-intencionadas. Os pacotes de rede de qualquer aplicativo passam por essa verificação e isso faz com que o uso da bateria do Microsoft Defender para o Ponto de Extremidade seja calculado de forma impreciso. O consumo real de bateria do Microsoft Defender para Ponto de Extremidade é muito menor do que o que é mostrado na página Bateria Configurações no dispositivo.

Em média, o uso de bateria por dia pelo Microsoft Defender para Ponto de Extremidade em execução em segundo plano é de aproximadamente **8,81%** da bateria geral consumida nesse dia . Essa métrica é relatada pela Apple com base no uso real do Microsoft Defender para Ponto de Extremidade em dispositivos de usuário final e devido aos motivos mencionados acima também podem ser contabilados para outros aplicativos que têm atividade de rede.

Além disso, a VPN usada é uma VPN local e, ao contrário de uma VPN tradicional, o tráfego de rede não é enviado fora do dispositivo.

## <a name="data-usage"></a>Uso de dados

O Microsoft Defender para Ponto de Extremidade usa uma VPN local/loopback para verificar o tráfego da Web em busca de sites ou conexões mal-intencionadas. Devido a esse motivo, o uso de dados do Microsoft Defender para Ponto de Extremidade pode ser contabilmente impreciso. Também observamos que, se o dispositivo estiver apenas na rede celular, o uso de dados relatados pelo provedor de serviços está muito próximo do consumo real, enquanto no aplicativo Configurações, a Apple mostra cerca de 1,5 x a 2x de dados reais consumidos.

Também temos observações semelhantes com outros serviços VPN e relatamos isso à Apple.

Além disso, é fundamental que o Microsoft Defender para o Ponto de Extremidade seja atualizado com nossos serviços de back-end para oferecer melhor proteção. No entanto, estamos trabalhando na otimização do uso de dados pelo Microsoft Defender para Ponto de Extremidade.

## <a name="report-unsafe-site"></a>Relatar site não seguro

Sites de phishing personificam sites confiáveis com o objetivo de obter suas informações pessoais ou financeiras. Visite a [página Fornecer comentários sobre proteção de rede](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) para relatar um site que pode ser um site de phishing.

## <a name="malicious-site-detected"></a>Site mal-intencionado detectado

O Microsoft Defender para Ponto de Extremidade protege você contra phishing ou outros ataques baseados na Web. Se um site mal-intencionado for detectado, a conexão será bloqueada e um alerta será enviado para o portal da Central de Segurança da organização. O alerta inclui o nome de domínio da conexão, o endereço IP remoto e os detalhes do dispositivo.

Além disso, uma notificação é mostrada no dispositivo iOS. Tocar na notificação abre a tela a seguir para que o usuário revise os detalhes.

> [!div class="mx-imgBorder"]
> ![Imagem do site relatada como notificação não segura](images/ios-phish-alert.png)

## <a name="data-and-privacy"></a>Dados e Privacidade

Para obter detalhes sobre dados coletados e privacidade, consulte Informações de Privacidade [- Microsoft Defender para Ponto de Extremidade no iOS](ios-privacy.md).

