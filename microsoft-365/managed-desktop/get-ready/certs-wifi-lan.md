---
title: Preparar certificados e perfis de rede da Área de Trabalho Gerenciada da Microsoft
description: certs/WiFi/LAN
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 0c3edda92e28b45b7f7b48c1d5002014f71116f6
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596568"
---
# <a name="prepare-certificates-and-network-profiles-for-microsoft-managed-desktop"></a>Preparar certificados e perfis de rede da Área de Trabalho Gerenciada da Microsoft  
 
A autenticação baseada em certificado é um requisito comum para os clientes que usam a área de trabalho gerenciada da Microsoft. Você pode exigir que os certificados acessem o Wi-Fi ou LAN, para se conectarem às soluções VPN ou para acessar recursos internos em sua organização.   
 
Como os dispositivos de área de trabalho gerenciada da Microsoft fazem parte do Azure Active Directory (Azure AD) e são gerenciados pelo Microsoft Intune, você deve implantar esses certificados usando um protocolo de registro de certificado simples (SCEP) ou padrão de criptografia de chave pública (PKCS) infraestrutura de certificado integrada ao Intune.    
 
## <a name="certificate-requirements"></a>Requisitos de Certificação 
 
Os certificados raiz são necessários para implantar certificados por meio de uma infraestrutura de SCEP ou PKCS. Outros aplicativos e serviços em sua organização podem exigir que certificados raiz sejam implantados em seus dispositivos de área de trabalho gerenciada da Microsoft.    
 
Antes de implantar o SCEP ou certificados PKCS para a área de trabalho gerenciada da Microsoft, você deve coletar requisitos para cada serviço que exija um usuário ou certificado de dispositivo em sua organização. Para simplificar isso, você pode usar um dos seguintes modelos de planejamento:  
 
- [Modelo de certificado PKCS](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/PKCS-certificate-template.xlsx) 
- [Modelo de certificado SCEP](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/SCEP-certificate-template.xlsx)

>[!NOTE]
>Atualmente, somente os perfis de certificado SCEP têm suporte para a implantação de perfil Wi-Fi para a área de trabalho gerenciada da Microsoft ao usar um tipo EAP. Não há suporte para perfis de certificados PKCS. Consulte [Adicionar configurações de Wi-Fi para dispositivos Windows 10 no Intune](https://docs.microsoft.com/intune/wi-fi-settings-windows) para referência.

  
## <a name="wi-fi-connectivity-requirements"></a>Requisitos de conectividade Wi-Fi

Para permitir que um dispositivo seja fornecido automaticamente com a configuração de Wi-Fi necessária para sua rede corporativa, talvez você precise de um perfil de configuração de Wi-Fi. Você pode configurar a área de trabalho gerenciada da Microsoft para implantar esses perfis em seus dispositivos. Se a sua segurança de rede exigir que os dispositivos façam parte do domínio local, você também pode precisar avaliar sua infraestrutura de rede Wi-Fi para garantir que ela seja compatível com os dispositivos de área de trabalho gerenciada da Microsoft (os dispositivos de área de trabalho gerenciada da Microsoft são associados ao Azure AD somente). 
 
Antes de implantar uma configuração de Wi-Fi nos dispositivos de área de trabalho gerenciada da Microsoft, você será solicitado a coletar os requisitos da sua organização para cada rede Wi-Fi. Para facilitar, você pode usar esse modelo de [perfil WiFi](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/WiFi-profile-template.xlsx).
 
 
## <a name="wired-connectivity-requirements-and-8021x-authentication"></a>Requisitos de conectividade com fio e autenticação 802.1 x 
 
Se você usar a autenticação do 802.1 x para proteger o acesso de dispositivos à sua rede local (LAN), precisará enviar os detalhes de configuração necessários para seus dispositivos de área de trabalho gerenciada da Microsoft. Os dispositivos de área de trabalho gerenciada da Microsoft que executam o Windows 10, versão 1809 ou posterior oferecem suporte à implantação de uma configuração do 802.1 x através do provedor de serviços de configuração do WiredNetwork. Para obter mais informações, consulte a documentação de [CSP do WiredNetwork](https://docs.microsoft.com/windows/client-management/mdm/wirednetwork-csp) . 
 
Antes de implantar um perfil de configuração de rede com fio nos dispositivos de área de trabalho gerenciada da Microsoft, reúna os requisitos de sua organização para sua rede corporativa com fio. Para fazer isso, siga estas etapas: 
 
 
1. Entre em um dispositivo que tenha seu perfil do 802.1 x existente configurado e esteja conectado à rede LAN.  
2. Abra um prompt de comando com credenciais administrativas. 
3. Encontre o nome da interface LAN executando **interface netsh interface show**. 
4. Exporte o XML do perfil de LAN executando a **pasta de perfil de exportação netsh lan =.  Interface = "interface_name"**. 
5. Se você precisar testar seu perfil exportado no dispositivo de área de trabalho gerenciada da Microsoft, execute **netsh lan Add Profile filename = "PATH_AND_FILENAME. xml" interface = "interface_name"**. 
 
 
## <a name="deploy-certificate-infrastructure"></a>Implantar a infraestrutura de certificado  
 
Se você já tiver uma infraestrutura de SCEP ou PKCS existente com o Intune e isso atender aos seus requisitos, você também poderá usá-lo para a área de trabalho gerenciada da Microsoft. Se nenhuma infraestrutura de SCEP ou PKCS já existir, você terá que preparar um.  
 
Para obter mais informações, consulte [configurar um perfil de certificado para seus dispositivos no Microsoft Intune](https://docs.microsoft.com/intune/certificates-configure). 
 
 
 
## <a name="deploy-a-lan-profile"></a>Implantar um perfil de LAN 
 
Depois que seu perfil de LAN tiver sido exportado, você poderá preparar a política para a área de trabalho gerenciada da Microsoft seguindo estas etapas:   
 
1. Crie um perfil personalizado no Microsoft Intune para o perfil de LAN usando as configurações a seguir (consulte [usar configurações personalizadas para dispositivos Windows 10 no Intune](https://docs.microsoft.com/intune/custom-settings-windows-10)). Em **configurações OMA-URI personalizadas**, selecione **Adicionar**e, em seguida, insira os seguintes valores: 
    - Name: *local de trabalho moderno – perfil de LAN do Windows 10* 
    - Descrição: Insira uma descrição que forneça uma visão geral da configuração e quaisquer outros detalhes importantes. 
    - OMA-URI (diferencia maiúscula de minúscula): Enter *./Device/Vendor/MSFT/WiredNetwork/LanXML*
    - Tipo de dados: selecionar **cadeia de caracteres (arquivo XML)**. 
    - XML personalizado: carregue o arquivo XML exportado.
2. Envie uma solicitação de suporte para as operações de ti de área de trabalho gerenciada da Microsoft usando o portal de administração de área de trabalho gerenciada da Microsoft para analisar e implantar o perfil de configuração em "dispositivos do ambiente de trabalho modernos – As operações de ti de área de trabalho gerenciada da Microsoft permitirão que você saiba quando a solicitação é concluída por meio da solicitação de suporte no portal de administração.
 
## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Implantar certificados e o perfil Wi-Fi/VPN 
 
 
Para implantar certificados e perfis, siga estas etapas:

1. Crie um perfil para cada um dos certificados raiz e intermediários (consulte [Create Trusted Certification Profiles](https://docs.microsoft.com/intune/protect/certificates-configure#step-3-create-trusted-certificate-profiles). Cada um desses perfis deve ter uma descrição que inclua uma data de validade no formato DD/MM/AAAA. **Os perfis de certificado sem uma data de expiração não serão implantados.**
2. Criar um perfil para cada SCEP ou certificados PKCS (consulte [criar um perfil de certificado SCEP](https://docs.microsoft.com/intune/protect/certificates-scep-configure#create-a-scep-certificate-profile) ou [criar um perfil de certificado PKCS](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) cada um desses perfis deve ter uma descrição que inclua uma data de expiração no formato dd/mm/aaaa. **Os perfis de certificado sem uma data de expiração não serão implantados.**
3. Criar um perfil para cada rede WiFi corporativa (consulte [configurações de Wi-Fi para dispositivos Windows 10 e posteriores](https://docs.microsoft.com/intune/wi-fi-settings-windows)).
4. Criar um perfil para cada VPN corporativa (consulte [Windows 10 and Windows Holographic device settings to add VPN Connections using Intune](https://docs.microsoft.com/intune/vpn-settings-windows-10)).
5. Enviar uma solicitação de suporte intitulado "implantação de certificado" ou "implantação de perfil Wi-Fi" para operações de ti de área de trabalho gerenciada da Microsoft usando o portal de administração de área de trabalho gerenciada da Microsoft para analisar e implantar o perfil de configuração em "dispositivos de local de trabalho modernos – teste ". As operações de ti de área de trabalho gerenciada da Microsoft permitirão que você saiba quando a solicitação foi concluída por meio da solicitação de suporte no portal de administração. 
 
 
