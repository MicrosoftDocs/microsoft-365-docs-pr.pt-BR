---
title: Configurar o Microsoft Defender ATP para recursos do iOS
description: Descreve como implantar o Microsoft Defender ATP para recursos iOS
keywords: microsoft, defender, atp, ios, configurar, recursos, ios
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 8b9f4372321bfa17ce5c11081ca274a3360e18dd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053403"
---
# <a name="configure-microsoft-defender-for-endpoint-for-ios-features"></a>Configurar o Microsoft Defender para Ponto de Extremidade para recursos do iOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

> [!NOTE]
> O Defender for Endpoint para iOS usaria uma VPN para fornecer o recurso de Proteção da Web. Esta não é uma VPN regular e é uma VPN local/auto-loop que não faz o tráfego fora do dispositivo.

## <a name="conditional-access-with-defender-for-endpoint-for-ios"></a>Acesso condicional com o Defender para Ponto de Extremidade para iOS  
O Microsoft Defender for Endpoint para iOS juntamente com o Microsoft Intune e o Azure Active Directory permite a aplicação de políticas de conformidade de dispositivo e acesso condicional com base nos níveis de risco do dispositivo. O Defender for Endpoint é uma solução MTD (Mobile Threat Defense) que você pode implantar para aproveitar esse recurso por meio do Intune.

Para obter mais informações sobre como configurar o Acesso Condicional com o Defender para Ponto de Extremidade para iOS, consulte [Defender for Endpoint e Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).

## <a name="web-protection-and-vpn"></a>Proteção da Web e VPN

Por padrão, o Defender para Ponto de Extremidade para iOS inclui e habilita o recurso de proteção da Web. [A proteção da Web](web-protection-overview.md) ajuda a proteger dispositivos contra ameaças da Web e proteger os usuários contra ataques de phishing. O Defender para Ponto de Extremidade para iOS usa uma VPN para fornecer essa proteção. Observe que esta é uma VPN local e, ao contrário da VPN tradicional, o tráfego de rede não é enviado fora do dispositivo.

Embora habilitada por padrão, pode haver alguns casos que exigem que você desabilite a VPN. Por exemplo, você deseja executar alguns aplicativos que não funcionam quando uma VPN está configurada. Nesses casos, você pode optar por desabilitar a VPN do aplicativo no dispositivo seguindo as etapas abaixo:

1. Em seu dispositivo iOS, abra o aplicativo **Configurações,** clique ou toque em **Geral** **e,** em seguida, VPN .
1. Clique ou toque no botão "i" do Microsoft Defender ATP.
1. Desative o **Connect On Demand para** desabilitar a VPN.

    > [!div class="mx-imgBorder"]
    > ![Vpn config connect on demand](images/ios-vpn-config.png)

> [!NOTE]
> A Proteção da Web não estará disponível quando a VPN estiver desabilitada. Para habilitar a Proteção Web de novo, abra o aplicativo Microsoft Defender para Ponto de Extremidade no dispositivo e clique ou toque em **Iniciar VPN**.

## <a name="co-existence-of-multiple-vpn-profiles"></a>Co-existência de vários perfis VPN

O iOS da Apple não dá suporte a várias VPNs em todo o dispositivo para serem ativas simultaneamente. Embora vários perfis VPN possam existir no dispositivo, apenas uma VPN pode estar ativa por vez.


## <a name="configure-compliance-policy-against-jailbroken-devices"></a>Configurar a política de conformidade em dispositivos com cadeia de segurança

Para proteger os dados corporativos de serem acessados em dispositivos iOS de cadeia, recomendamos que você defina a seguinte política de conformidade no Intune.

> [!NOTE]
> No momento, o Microsoft Defender para Ponto de Extremidade para iOS não oferece proteção contra cenários de jailbreak. Se usado em um dispositivo jailbroken, em cenários específicos, os dados que são usados pelo aplicativo, como sua id de email corporativa e imagem de perfil corporativo (se disponível) podem ser expostos localmente

Siga as etapas a seguir para criar uma política de conformidade contra dispositivos com cadeia de segurança.

1. No [Centro de administração do Microsoft Endpoint Manager,](https://go.microsoft.com/fwlink/?linkid=2109431)vá para **Políticas** de Conformidade  ->  **de**  ->  **Dispositivos Criar Política**. Selecione "iOS/iPadOS" como plataforma e clique em **Criar**.

    > [!div class="mx-imgBorder"]
    > ![Criar Política](images/ios-jb-policy.png)

2. Especifique um nome da política, por exemplo "Política de Conformidade para Jailbreak".
3. Na página configurações de conformidade, clique para expandir a seção **Saúde do** Dispositivo e clique **em Bloquear** para **dispositivos jailbroken.**

    > [!div class="mx-imgBorder"]
    > ![Configurações de Política](images/ios-jb-settings.png)

4. Na seção *Ação para não conformidade,* selecione as ações de acordo com seus requisitos e selecione **Próximo**.

    > [!div class="mx-imgBorder"]
    > ![Ações de política](images/ios-jb-actions.png)

5. Na seção *Atribuições,* selecione os grupos de usuários que você deseja incluir para esta política e selecione **Próximo**.
6. Na seção **Review+Create,** verifique se todas as informações inseridas estão corretas e selecione **Criar**.

## <a name="configure-custom-indicators"></a>Configurar indicadores personalizados

O Defender para Ponto de Extremidade para iOS também permite que os administradores configurem indicadores personalizados em dispositivos iOS. Para obter mais informações sobre como configurar indicadores personalizados, consulte [Manage indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).

> [!NOTE]
> O Defender para Ponto de Extremidade para iOS dá suporte à criação de indicadores personalizados apenas para endereços IP e URLs/domínios.

## <a name="report-unsafe-site"></a>Relatar site não seguro

Sites de phishing personificam sites confiáveis com o objetivo de obter suas informações pessoais ou financeiras. Visite a [página Fornecer comentários sobre a](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) proteção de rede se quiser relatar um site que pode ser um site de phishing.
