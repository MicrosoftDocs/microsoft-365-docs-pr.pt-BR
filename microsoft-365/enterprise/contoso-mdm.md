---
title: Gerenciamento de dispositivo móvel para a Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Entenda como a Contoso usa Intune no Microsoft 365 Enterprise para gerenciar seus dispositivos e aplicativos com base nessa plataforma.
ms.openlocfilehash: 7232c89cc105525cc57facd5a1b9de06426adbca
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068358"
---
# <a name="mobile-device-management-for-contoso"></a>Gerenciamento de dispositivo móvel para a Contoso

O Microsoft 365 Enterprise inclui o Microsoft Intune e um conjunto de serviços do Azure que dão suporte a segurança, ao gerenciamento de aplicativos e dispositivos móveis.

A Contoso tem vários funcionários com dispositivos móveis, alguns em escritórios da Contoso e alguns dos quais não têm escritórios. A Contoso precisa de uma maneira de habilitar a produtividade mas manter a proteção nos dispositivos, nos dados da Contoso armazenados nesses dispositivos e no comportamento dos aplicativos.

## <a name="plan"></a>Planejar

No início da análise de gerenciamento de dispositivo móvel para o Microsoft 365 Enterprise, a Contoso identificou os seguintes casos de uso do Intune:

- Proteger os dados e emails do Exchange Online para que possam ser acessados com segurança em dispositivos móveis
- Implementar um programa "traga seu próprio dispositivo" (BYOD) para funcionários da Contoso
- Emitir telefones e tablets pertencentes à organização e tablets compartilhados de uso limitado para funcionários da Contoso

A Contoso não está usando o Intune para:

- Permitir aos funcionários acessar com segurança o Office 365 de um kiosk público não gerenciado
- Proteger dados e emails locais para que possam ser acessados com segurança em dispositivos móveis, já que não há mais servidores locais do Microsoft Exchange.

## <a name="deploy"></a>Implantar

A Contoso configurou sua infraestrutura de gerenciamento de dispositivo móvel da seguinte forma:

- Configurou o Intune como a autoridade de Gerenciamento de Dispositivo Móvel (MDM) e está usando o Intune no Azure para administrar o conteúdo e gerenciar os dispositivos
- Criou grupos do Azure AD para dispositivos para registro e configurações do Intune, além de políticas de acesso condicional baseadas no dispositivo.

  Confira [políticas de acesso condicional da Contoso](contoso-identity.md#conditional-access-policies-for-identity-and-device-access) para saber mais.

- Habilitou a plataforma de dispositivos Apple para dar suporte a funcionários com iPads, iPhones e iMacs e celulares de propriedade corporativa com base no iPhone
- Criou políticas de termos e condições específicas da Contoso, que são apresentadas durante a instalação do Portal da Empresa da Contoso em dispositivos móveis
- Para dispositivos que não estão registrados, um conjunto de políticas de Gerenciamento de Aplicativo Móvel (MAM) para exigir autenticação para acesso aos serviços do Office 365
- Políticas criadas do Intune que imponham:
  - Aplicativos permitidos
  - Criptografia de dispositivos para ajudar a impedir o acesso não autorizado
  - Um PIN de seis dígitos ou senha
  - Um tempo limite de inatividade
  - Proteção antivírus e contra malware, e atualizações de assinaturas com o Windows Defender em dispositivos Windows 10
  - Atualizações automáticas em dispositivos Windows 10 que incluem as atualizações de segurança mais recentes
  - Enviar certificados para dispositivos gerenciados
  - Clara separação de dados pessoais e comerciais. Os administradores ou usuários podem apagar seletivamente dados corporativos do dispositivo, mantendo inalterados dados pessoais, como imagens, contas de email e arquivos pessoais.

Depois de implantar, a Contoso registrou os PCs, smartphones e tablets de propriedade da empresa adicionando-os aos grupos de dispositivos apropriados do Intune, e gradualmente implementou um programa BYOD para os funcionários poderem registrar seus dispositivos pessoais. Os dispositivos registrados receberam políticas do Intune, resultando em dispositivos e aplicativos gerenciados e seguros. Dispositivos não registrados têm políticas de gerenciamento de aplicativo móvel (MAM) que especificam aplicativos permitidos.

Esta é a arquitetura de implantação de gerenciamento de dispositivo móvel da Contoso.

![Infraestrutura de implantação de gerenciamento de dispositivo móvel da Contoso.](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a>Próxima etapa

[Saiba](contoso-info-protect.md) como a Contoso usa os recursos de proteção de informações do Microsoft 365 Enterprise para classificar, identificar e proteger ativos digitais fundamentais em sua organização.

## <a name="see-also"></a>Confira também

[Gerenciamento de dispositivo móvel para o Microsoft 365 Enterprise](mobility-infrastructure.md)

[Guia de implantação](deploy-microsoft-365-enterprise.md)

[Guias de laboratório de teste](m365-enterprise-test-lab-guides.md)

