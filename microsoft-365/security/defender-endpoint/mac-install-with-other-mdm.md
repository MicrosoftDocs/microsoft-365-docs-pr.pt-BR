---
title: Implantação com um sistema MDM (Gerenciamento de Dispositivo Móvel) diferente para o Microsoft Defender ATP para Mac
description: Instale o Microsoft Defender ATP para Mac em outras soluções de gerenciamento.
keywords: microsoft, defender, atp, mac, installation, deploy, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: mavel
author: maximvelichko
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 3343eb433a6ae5c708651abf298bd4f061817543
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764128"
---
# <a name="deployment-with-a-different-mobile-device-management-mdm-system-for-microsoft-defender-for-endpoint-on-macos"></a>Implantação com um sistema MDM (Gerenciamento de Dispositivo Móvel) diferente para o Microsoft Defender para Ponto de Extremidade no macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)
 
## <a name="prerequisites-and-system-requirements"></a>Pré-requisitos e requisitos do sistema

Antes de começar, consulte a página principal do Microsoft Defender para Ponto de Extremidade no [macOS](microsoft-defender-endpoint-mac.md) para obter uma descrição dos pré-requisitos e requisitos do sistema para a versão de software atual.


## <a name="approach"></a>Abordagem

> [!CAUTION]

> Atualmente, a Microsoft dá suporte oficial apenas ao Intune e ao JAMF para implantação e gerenciamento do Microsoft Defender para Ponto de Extremidade no macOS. A Microsoft não faz garantias, expressas ou implícitas, com relação às informações fornecidas abaixo.

Se sua organização usa uma solução MDM (Gerenciamento de Dispositivo Móvel) que não tem suporte oficial, isso não significa que você não pode implantar ou executar o Microsoft Defender para Ponto de Extremidade no macOS.

O Microsoft Defender para Ponto de Extremidade no macOS não depende de recursos específicos do fornecedor. Ele pode ser usado com qualquer solução MDM que oferece suporte aos seguintes recursos:

- Implante um macOS .pkg em dispositivos gerenciados.
- Implantar perfis de configuração do sistema macOS em dispositivos gerenciados.
- Execute uma ferramenta/script arbitrária configurada pelo administrador em dispositivos gerenciados.

A maioria das soluções MDM modernas incluem esses recursos, no entanto, eles podem chamá-los de forma diferente.

No entanto, você pode implantar o Defender sem o último requisito da lista anterior:

- Você não poderá coletar status de forma centralizada
- Se você decidir desinstalar o Defender, precisará fazer logoff no dispositivo cliente localmente como administrador

## <a name="deployment"></a>Implantação

A maioria das soluções MDM usa o mesmo modelo para gerenciar dispositivos macOS, com terminologia semelhante. Use [a implantação baseada em JAMF](mac-install-with-jamf.md) como modelo.

### <a name="package"></a>Pacote

Configurar a implantação [de um pacote de](mac-install-with-jamf.md)aplicativos necessário , com o pacote de instalação (wdav.pkg) baixado do Centro de Segurança do Microsoft [Defender](mac-install-with-jamf.md).

Para implantar o pacote em sua empresa, use as instruções associadas à sua solução MDM.

### <a name="license-settings"></a>Configurações de licença

Configurar um [perfil de configuração do sistema.](mac-install-with-jamf.md) 

Sua solução MDM pode chamá-la de algo como "Perfil de Configurações Personalizadas", pois o Microsoft Defender para Ponto de Extremidade no macOS não faz parte do macOS.

Use a lista de propriedades, jamf/WindowsDefenderATPOnboarding.plist, que pode ser extraída de um pacote de integração baixado do Centro de Segurança do [Microsoft Defender.](mac-install-with-jamf.md)
Seu sistema pode dar suporte a uma lista de propriedades arbitrárias no formato XML. Você pode carregar o arquivo jamf/WindowsDefenderATPOnboarding.plist como está nesse caso.
Como alternativa, pode exigir que você converta a lista de propriedades em um formato diferente primeiro.

Normalmente, seu perfil personalizado tem uma ID, nome ou atributo de domínio. Você deve usar exatamente "com.microsoft.wdav.atp" para esse valor.
O MDM o usa para implantar o arquivo de configurações em **/Library/Managed Preferences/com.microsoft.wdav.atp.plist** em um dispositivo cliente, e o Defender usa esse arquivo para carregar as informações de integração.

### <a name="kernel-extension-policy"></a>Política de extensão de kernel

Configurar uma política de extensão KEXT ou kernel. Use o identificador de **equipe UBF8T346G9** para permitir extensões de kernel fornecidas pela Microsoft.

> [!CAUTION]
> Se seu ambiente consistir em dispositivos Apple Silicon (M1), esses dispositivos não devem receber perfis de configuração com políticas KEXT.
> A Apple não dá suporte a KEXT nesses dispositivos, a implantação desse perfil falharia em máquinas M1.

### <a name="system-extension-policy"></a>Política de extensão do sistema

Configurar uma política de extensão do sistema. Use o identificador de **equipe UBF8T346G9** e aprove os seguintes identificadores de pacote:

- com.microsoft.wdav.epsext
- com.microsoft.wdav.netext

### <a name="full-disk-access-policy"></a>Política de acesso em disco completo

Conceda acesso em disco completo aos seguintes componentes:

- Microsoft Defender para Ponto de Extremidade
    - Identificador: `com.microsoft.wdav`
    - Tipo de identificador: ID do pacote
    - Requisito de código: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

- Extensão de Segurança do Microsoft Defender para Ponto de Extremidade
    - Identificador: `com.microsoft.wdav.epsext`
    - Tipo de identificador: ID do pacote
    - Requisito de código: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

### <a name="network-extension-policy"></a>Política de extensão de rede

Como parte dos recursos de Detecção e Resposta do Ponto de Extremidade, o Microsoft Defender para Ponto de Extremidade no macOS inspeciona o tráfego de soquete e relata essas informações ao portal do Centro de Segurança do Microsoft Defender. A política a seguir permite que a extensão de rede execute essa funcionalidade.

- Tipo de filtro: Plug-in
- Identificador do pacote de plug-in: `com.microsoft.wdav`
- Filtrar o identificador de pacote do provedor de dados: `com.microsoft.wdav.netext`
- Requisito designado do provedor de dados de filtro: `identifier "com.microsoft.wdav.tunnelext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`
- Soquetes de filtro: `true`

## <a name="check-installation-status"></a>Verificar o status da instalação

Execute [o Microsoft Defender para Ponto de](mac-install-with-jamf.md) Extremidade em um dispositivo cliente para verificar o status de integração.
