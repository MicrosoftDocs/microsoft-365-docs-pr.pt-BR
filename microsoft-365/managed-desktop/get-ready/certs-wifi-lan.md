---
title: Prepare certificados e perfis de rede da Área de trabalho gerenciada da Microsoft
description: Requisitos de certificado e conectividade wi-fi
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
audience: Admin
ms.openlocfilehash: a59add6f6821824f189703b3dedd35fda313ec31
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574578"
---
# <a name="prepare-certificates-and-network-profiles-for-microsoft-managed-desktop"></a>Prepare certificados e perfis de rede da Área de trabalho gerenciada da Microsoft  
 
A autenticação baseada em certificado é um requisito comum para clientes que usam Área de Trabalho Gerenciada da Microsoft. Você pode exigir que os certificados acessem Wi-Fi ou LAN, para se conectar a soluções VPN ou para acessar recursos internos em sua organização.   
 
Como os dispositivos Área de Trabalho Gerenciada da Microsoft estão ingressados no Azure Active Directory (Azure AD) e são gerenciados pelo Microsoft Intune, você deve implantar esses certificados usando um SCEP (Simple Certificate Enrollment Protocol) ou uma infraestrutura de certificado PKCS (Public Key Cryptography Standard) integrada ao Intune.    
 
## <a name="certificate-requirements"></a>Requisitos de Certificação 
 
Certificados raiz são necessários para implantar certificados por meio de uma infraestrutura SCEP ou PKCS. Outros aplicativos e serviços em sua organização podem exigir certificados raiz para serem implantados em seus Área de Trabalho Gerenciada da Microsoft dispositivos.    
 
Antes de implantar certificados SCEP ou PKCS Área de Trabalho Gerenciada da Microsoft, você deve reunir requisitos para cada serviço que exija um certificado de usuário ou dispositivo em sua organização. Para facilitar essa atividade, você pode usar um dos seguintes modelos de planejamento:  
 
- [Modelo de certificado PKCS](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/PKCS-certificate-template.xlsx) 
- [Modelo de certificado SCEP](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/SCEP-certificate-template.xlsx)

  
## <a name="wi-fi-connectivity-requirements"></a>Wi-Fi de conectividade

Para permitir que um dispositivo seja fornecido automaticamente com a configuração de Wi-Fi necessária para sua rede corporativa, talvez seja necessário um perfil Wi-Fi configuração. Você pode configurar Área de Trabalho Gerenciada da Microsoft para implantar esses perfis em seus dispositivos. Se a segurança de sua rede exigir que os dispositivos façam parte do domínio local, você também precisará avaliar sua infraestrutura de rede Wi-Fi para garantir que seja compatível com dispositivos Área de Trabalho Gerenciada da Microsoft (os dispositivos Área de Trabalho Gerenciada da Microsoft são apenas ingressados no Azure AD). 
 
Antes de implantar uma configuração Wi-Fi em dispositivos Área de Trabalho Gerenciada da Microsoft, será necessário reunir os requisitos da sua organização para cada rede Wi-Fi. Para facilitar essa atividade, você pode usar esse [modelo de perfil WiFi.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/WiFi-profile-template.xlsx)
 
 
## <a name="wired-connectivity-requirements-and-8021x-authentication"></a>Requisitos de conectividade com fio e autenticação 802.1x 
 
Se você usar a autenticação 802.1x para proteger o acesso de dispositivos à sua rede de área local (LAN), você precisará empurrar os detalhes de configuração necessários para seus dispositivos Área de Trabalho Gerenciada da Microsoft. Área de Trabalho Gerenciada da Microsoft dispositivos que executam Windows 10 versão 1809 ou posteriores suportam a implantação de uma configuração 802.1x por meio do provedor de serviços de configuração (CSP) WiredNetwork. Para obter mais informações, consulte [a documentação do CSP WiredNetwork.](/windows/client-management/mdm/wirednetwork-csp) 
 
Antes de implantar um perfil de configuração de rede com fio Área de Trabalho Gerenciada da Microsoft dispositivos, reúna os requisitos da sua organização para sua rede corporativa com fio. Para fazer isso, siga estas etapas: 
 
 
1. Entre em um dispositivo que tenha seu perfil 802.1x existente configurado e esteja conectado à rede LAN.  
2. Abra um prompt de comando com credenciais administrativas. 
3. Encontre o nome da interface lan executando **a interface de exibição da interface netsh.** 
4. Exporte o XML de perfil de LAN executando a pasta de perfil de exportação de **lan netsh=.  Interface="interface_name"**. 
5. Se você precisar testar seu perfil exportado em um dispositivo Área de Trabalho Gerenciada da Microsoft, execute **netsh lan add profile filename="PATH_AND_FILENAME.xml" interface="INTERFACE_NAME"**. 
 
 
## <a name="deploy-certificate-infrastructure"></a>Implantar infraestrutura de certificado  
 
Se você já tiver uma infraestrutura SCEP ou PKCS existente com o Intune e essa abordagem atender aos seus requisitos, você também poderá usá-la para Área de Trabalho Gerenciada da Microsoft. Se nenhuma infraestrutura scep ou PKCS já existir, você terá que preparar uma.  
 
Para obter mais informações, [consulte Configure a certificate profile for your devices in Microsoft Intune](/intune/certificates-configure). 
 
 
 
## <a name="deploy-a-lan-profile"></a>Implantar um perfil de LAN 
 
Depois que seu perfil de LAN for exportado, você poderá preparar a política para Área de Trabalho Gerenciada da Microsoft seguindo estas etapas:   
 
1. Crie um perfil personalizado no Microsoft Intune para o perfil de LAN usando as configurações a seguir (consulte Usar configurações personalizadas para Windows 10 [dispositivos no Intune](/intune/custom-settings-windows-10)). Em **Custom OMA-URI Configurações**, selecione **Adicionar** e insira os seguintes valores: 
    - Nome: *Perfil de LAN Workplace-Windows 10* 
    - Descrição: insira uma descrição que fornece uma visão geral da configuração e quaisquer outros detalhes importantes. 
    - OMA-URI (sensível a minúsculas): Insira *./Device/Vendor/MSFT/WiredNetwork/LanXML*
    - Tipo de dados: selecione **Cadeia de caracteres (arquivo XML)**. 
    - XML personalizado: Upload arquivo XML exportado.
2. Envie uma solicitação de Suporte Área de Trabalho Gerenciada da Microsoft operações de IT usando o portal de administração do Área de Trabalho Gerenciada da Microsoft para revisar e implantar o perfil de configuração em "Dispositivos de Local de Trabalho Modernos – Teste". Área de Trabalho Gerenciada da Microsoft As Operações de TI permitirão que você saiba quando a solicitação for concluída por meio da solicitação de Suporte no portal de administração.
 
## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Implantar certificados e perfil de Wi-Fi/VPN 
 
 
Para implantar certificados e perfis, siga estas etapas:

1. Crie um perfil para cada um dos certificados Raiz e Intermediário (consulte [Criar perfis de certificado confiáveis](/intune/protect/certificates-configure#step-3-create-trusted-certificate-profiles). Cada um desses perfis deve ter uma descrição que inclua uma data de expiração no formato DD/MM/YYYY. **Os perfis de certificado sem uma data de expiração não serão implantados.**
2. Crie um perfil para cada certificado SCEP ou PKCS (consulte [Create a SCEP certificate profile](/intune/protect/certificates-scep-configure#create-a-scep-certificate-profile) or Create a [PKCS certificate profile](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) Cada um desses perfis deve ter uma descrição que inclua uma data de expiração no formato DD/MM/YYYY. **Os perfis de certificado sem uma data de expiração não serão implantados.**
3. Crie um perfil para cada rede Wi-Fi corporativa (consulte [Configurações de Wi-Fi para Windows 10 e dispositivos posteriores](/intune/wi-fi-settings-windows)).
4. Crie um perfil para cada VPN corporativa (consulte Windows 10 e Windows configurações de dispositivo holográfico para adicionar conexões [VPN usando o Intune](/intune/vpn-settings-windows-10)).
5. Envie uma solicitação de Suporte intitulada "Implantação de Certificado" ou "Implantação de Perfil de Wi-Fi" para operações de ÁREA DE TRABALHO GERENCIADA DA MICROSOFT usando o portal de administração do Área de Trabalho Gerenciada da Microsoft para revisar e implantar o perfil de configuração em "Dispositivos de Local de Trabalho Modernos – Teste". Área de Trabalho Gerenciada da Microsoft As Operações de TI permitirão que você saiba quando a solicitação foi concluída por meio da solicitação de Suporte no portal de administração. 
 
## <a name="steps-to-get-ready"></a>Etapas para se preparar

1. Revise [os pré-requisitos para Área de Trabalho Gerenciada da Microsoft](prerequisites.md).
2. Use [ferramentas de avaliação de preparação.](readiness-assessment-tool.md)
3. [Pré-requisitos para contas de convidado](guest-accounts.md)
4. [Configuração de rede na Área de Trabalho Gerenciada da Microsoft](network.md)
5. [Preparar certificados e perfis de rede para Área de Trabalho Gerenciada da Microsoft](certs-wifi-lan.md) (Este artigo)
6. [Preparar o acesso aos recursos locais da Área de Trabalho Gerenciada da Microsoft](authentication.md)
7. [Aplicativos na Área de Trabalho Gerenciada da Microsoft](apps.md)
8. [Preparar unidades mapeadas da Área de Trabalho Gerenciada da Microsoft](mapped-drives.md)
9. [Preparar recursos de impressão da Área de Trabalho Gerenciada da Microsoft](printing.md) 
