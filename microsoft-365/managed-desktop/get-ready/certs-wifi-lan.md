---
title: Prepare certificados e perfis de rede da Área de trabalho gerenciada da Microsoft
description: certs/wifi/lan
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 9f4490711c1ea051afe9d8efb081a2f7a141f8ba
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909113"
---
# <a name="prepare-certificates-and-network-profiles-for-microsoft-managed-desktop"></a>Prepare certificados e perfis de rede da Área de trabalho gerenciada da Microsoft  
 
A autenticação baseada em certificado é um requisito comum para clientes que usam a Área de Trabalho Gerenciada da Microsoft. Você pode exigir que os certificados acessem Wi-Fi ou LAN, para se conectar a soluções VPN ou para acessar recursos internos em sua organização.   
 
Como os dispositivos da Área de Trabalho Gerenciada da Microsoft estão ingressados no Azure Active Directory (Azure AD) e são gerenciados pelo Microsoft Intune, você deve implantar esses certificados usando um SCEP (Simple Certificate Enrollment Protocol) ou uma infraestrutura de certificado PKCS (Public Key Cryptography Standard) integrada ao Intune.    
 
## <a name="certificate-requirements"></a>Requisitos de Certificação 
 
Certificados raiz são necessários para implantar certificados por meio de uma infraestrutura SCEP ou PKCS. Outros aplicativos e serviços em sua organização podem exigir certificados raiz para serem implantados em seus dispositivos da Área de Trabalho Gerenciada da Microsoft.    
 
Antes de implantar certificados SCEP ou PKCS na Área de Trabalho Gerenciada da Microsoft, você deve reunir requisitos para cada serviço que exija um certificado de usuário ou dispositivo em sua organização. Para facilitar essa atividade, você pode usar um dos seguintes modelos de planejamento:  
 
- [Modelo de certificado PKCS](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/PKCS-certificate-template.xlsx) 
- [Modelo de certificado SCEP](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/SCEP-certificate-template.xlsx)

  
## <a name="wi-fi-connectivity-requirements"></a>Wi-Fi de conectividade

Para permitir que um dispositivo seja fornecido automaticamente com a configuração de Wi-Fi necessária para sua rede corporativa, talvez seja necessário um perfil Wi-Fi configuração. Você pode configurar a Área de Trabalho Gerenciada da Microsoft para implantar esses perfis em seus dispositivos. Se a segurança de sua rede exigir que os dispositivos façam parte do domínio local, talvez você também precise avaliar sua infraestrutura de rede Wi-Fi para garantir que seja compatível com dispositivos da Área de Trabalho Gerenciada da Microsoft (os dispositivos da Área de Trabalho Gerenciada da Microsoft são apenas ingressados no Azure AD). 
 
Antes de implantar uma configuração Wi-Fi em dispositivos da Área de Trabalho Gerenciada da Microsoft, será necessário reunir os requisitos da sua organização para cada Wi-Fi de rede. Para facilitar essa atividade, você pode usar esse [modelo de perfil WiFi.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/WiFi-profile-template.xlsx)
 
 
## <a name="wired-connectivity-requirements-and-8021x-authentication"></a>Requisitos de conectividade com fio e autenticação 802.1x 
 
Se você usar a autenticação 802.1x para proteger o acesso de dispositivos à rede local (LAN), você precisará empurrar os detalhes de configuração necessários para seus dispositivos da Área de Trabalho Gerenciada da Microsoft. Os dispositivos da Área de Trabalho Gerenciada da Microsoft que executam o Windows 10, versão 1809 ou posterior suportam a implantação de uma configuração 802.1x por meio do provedor de serviços de configuração do WiredNetwork (CSP). Para obter mais informações, consulte [a documentação do CSP WiredNetwork.](/windows/client-management/mdm/wirednetwork-csp) 
 
Antes de implantar um perfil de configuração de rede com fio em dispositivos da Área de Trabalho Gerenciada da Microsoft, reúna os requisitos da sua organização para sua rede corporativa com fio. Para fazer isso, siga estas etapas: 
 
 
1. Entre em um dispositivo que tenha seu perfil 802.1x existente configurado e esteja conectado à rede LAN.  
2. Abra um prompt de comando com credenciais administrativas. 
3. Encontre o nome da interface lan executando **a interface de exibição da interface netsh.** 
4. Exporte o XML de perfil de LAN executando a pasta de perfil de exportação de **lan netsh=.  Interface="interface_name"**. 
5. Se você precisar testar seu perfil exportado no dispositivo da Área de Trabalho Gerenciada da Microsoft, execute **netsh lan add profile filename="PATH_AND_FILENAME.xml" interface="INTERFACE_NAME"**. 
 
 
## <a name="deploy-certificate-infrastructure"></a>Implantar infraestrutura de certificado  
 
Se você já tiver uma infraestrutura scep ou PKCS existente com o Intune e essa abordagem atender aos seus requisitos, você também poderá usá-la para a Área de Trabalho Gerenciada da Microsoft. Se nenhuma infraestrutura scep ou PKCS já existir, você terá que preparar uma.  
 
Para obter mais informações, [consulte Configure a certificate profile for your devices in Microsoft Intune](/intune/certificates-configure). 
 
 
 
## <a name="deploy-a-lan-profile"></a>Implantar um perfil de LAN 
 
Depois que seu perfil de LAN for exportado, você poderá preparar a política para a Área de Trabalho Gerenciada da Microsoft seguindo estas etapas:   
 
1. Crie um perfil personalizado no Microsoft Intune para o perfil de LAN usando as seguintes configurações (consulte Usar configurações personalizadas para [dispositivos Windows 10 no Intune](/intune/custom-settings-windows-10)). Em **Configurações personalizadas do OMA-URI,** selecione **Adicionar** e insira os seguintes valores: 
    - Nome: *Perfil de LAN Workplace-Windows 10* 
    - Descrição: insira uma descrição que fornece uma visão geral da configuração e quaisquer outros detalhes importantes. 
    - OMA-URI (sensível a minúsculas): Insira *./Device/Vendor/MSFT/WiredNetwork/LanXML*
    - Tipo de dados: selecione **Cadeia de caracteres (arquivo XML)**. 
    - XML personalizado: Carregar o arquivo XML exportado.
2. Envie uma solicitação de Suporte às Operações de IT gerenciadas da Área de Trabalho da Microsoft usando o portal de Administração da Área de Trabalho Gerenciada da Microsoft para revisar e implantar o perfil de configuração em "Dispositivos de Trabalho Modernos – Teste". As Operações de TI da Área de Trabalho Gerenciada da Microsoft permitirão que você saiba quando a solicitação for concluída por meio da solicitação de Suporte no portal de administração.
 
## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Implantar certificados e perfil de Wi-Fi/VPN 
 
 
Para implantar certificados e perfis, siga estas etapas:

1. Crie um perfil para cada um dos certificados Raiz e Intermediário (consulte [Criar perfis de certificado confiáveis](/intune/protect/certificates-configure#step-3-create-trusted-certificate-profiles). Cada um desses perfis deve ter uma descrição que inclua uma data de expiração no formato DD/MM/YYYY. **Os perfis de certificado sem uma data de expiração não serão implantados.**
2. Crie um perfil para cada certificado SCEP ou PKCS (consulte [Create a SCEP certificate profile](/intune/protect/certificates-scep-configure#create-a-scep-certificate-profile) or Create a [PKCS certificate profile](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) Cada um desses perfis deve ter uma descrição que inclua uma data de expiração no formato DD/MM/YYYY. **Os perfis de certificado sem uma data de expiração não serão implantados.**
3. Crie um perfil para cada rede Wi-Fi corporativa (consulte [Configurações de Wi-Fi para Dispositivos Windows 10 e posteriores](/intune/wi-fi-settings-windows)).
4. Crie um perfil para cada VPN corporativa (consulte Configurações do dispositivo Windows 10 e Windows Holographic para adicionar conexões [VPN usando o Intune](/intune/vpn-settings-windows-10)).
5. Envie uma solicitação de Suporte intitulada "Implantação de Certificado" ou "Implantação de Perfil wi-fi" para operações de IT da Área de Trabalho Gerenciada da Microsoft usando o portal de Administração da Área de Trabalho Gerenciada da Microsoft para revisar e implantar o perfil de configuração em "Dispositivos de Trabalho Modernos – Teste". As Operações de TI da Área de Trabalho Gerenciada da Microsoft permitirão que você saiba quando a solicitação foi concluída por meio da solicitação de Suporte no portal de administração. 
 
