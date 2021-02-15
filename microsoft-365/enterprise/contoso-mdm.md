---
title: Gerenciamento de dispositivo móvel para a Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Entenda como a Contoso usa o Microsoft Intune no Microsoft 365 para empresas para gerenciar seus dispositivos e aplicativos que são executados neles.
ms.openlocfilehash: 6d7783e8c2d9b78b63bf9eefe761fbc52d0b280f
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753985"
---
# <a name="mobile-device-management-for-contoso"></a>Gerenciamento de dispositivo móvel para a Contoso

O Microsoft 365 para empresas inclui o Intune e um conjunto de serviços do Azure que suportam segurança e gerenciamento de aplicativos e dispositivos móveis.

A Contoso tem muitos funcionários habilitados para dispositivos móveis. Alguns têm escritórios em locais da Contoso e outros não têm escritórios. A Contoso precisava de uma maneira de habilitar a produtividade dos funcionários, mas manter os dispositivos, os dados da Contoso armazenados nesses dispositivos e o comportamento do aplicativo seguros.

## <a name="plan"></a>Planejar

A Contoso identificou os seguintes casos de uso do Intune de gerenciamento de dispositivo móvel para o Microsoft 365 para empresas:

- Proteja o email e os dados do Exchange Online para que eles possam ser acessados com segurança por dispositivos móveis.
- Implemente um programa BYOD (traga seu próprio dispositivo) para funcionários da Contoso.
- Emitir telefones de propriedade da organização e tablets compartilhados de uso limitado para funcionários da Contoso.

A Contoso não usa o Intune para:

- Permitir que os funcionários acessem o Microsoft 365 com segurança de um quiosque público não autorizado.
- Proteja o email local e os dados para que eles possam ser acessados com segurança por dispositivos móveis, porque não há servidores locais do Microsoft Exchange.

## <a name="deploy"></a>Implantar

A Contoso configurou sua infraestrutura de gerenciamento de dispositivo móvel da seguinte forma:

- Definir o Intune como a autoridade de gerenciamento de dispositivo móvel (MDM) e usar o Intune no Azure para administrar o conteúdo e gerenciar os dispositivos
- Criou grupos do Azure Active Directory (Azure AD) para dispositivos para registro e configurações do Intune e políticas de Acesso Condicional baseadas em dispositivos

  Para obter mais informações, consulte [Políticas de Acesso Condicional da Contoso.](contoso-identity.md#conditional-access-policies-for-identity-and-device-access)

- Habilitada a plataforma de dispositivo Apple para dar suporte a funcionários com iPads, iMacs e iPhones e iPhones de propriedade corporativa
- Criou políticas de termos e condições específicas da Contoso, que são apresentadas durante a instalação do Portal da Empresa da Contoso em dispositivos móveis
- Para dispositivos que não estão inscritos, implementou um conjunto de políticas de Gerenciamento de Aplicativo Móvel (MAM) para exigir autenticação para acesso aos serviços do Microsoft 365
- Políticas criadas do Intune que imponham:
  - Aplicativos permitidos.
  - Criptografia de dispositivo para ajudar a impedir o acesso não autorizado.
  - Um PIN de seis dígitos ou senha.
  - Um período de tempo de inatividade.
  - Proteção antivírus e malware e atualizações de assinatura com o Windows Defender em dispositivos Windows 10.
  - Atualizações automáticas em dispositivos Windows 10 que incluem as atualizações de segurança mais recentes.
  - Colocar certificados em dispositivos gerenciados.
  - Clara separação de dados pessoais e comerciais. Os administradores ou usuários podem apagar seletivamente dados corporativos do dispositivo, mantendo inalterados dados pessoais, como imagens, contas de email e arquivos pessoais.

A Contoso registrou PCs implantados e smartphones e tablets de propriedade da empresa adicionando-os aos grupos de dispositivos apropriados do Intune. Eles também estabeleceram um programa BYOD para que os funcionários registram seus dispositivos pessoais. Os dispositivos inscritos recebem políticas do Intune, o que resulta em dispositivos gerenciados e protegidos e seus aplicativos. Os dispositivos que não estão inscritos têm políticas de Gerenciamento de Aplicativo Móvel (MAM) que especificam aplicativos permitidos.

Esta é a arquitetura de implantação de gerenciamento de dispositivo móvel da Contoso.

![Infraestrutura de implantação de gerenciamento de dispositivo móvel da Contoso](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a>Próxima etapa

Saiba como a [](contoso-info-protect.md) Contoso usa os recursos de proteção de informações do Microsoft 365 para empresas para classificar, identificar e proteger ativos digitais cruciais em toda a organização.

## <a name="see-also"></a>Confira também

[Gerenciamento de dispositivos para o Microsoft 365](device-management-roadmap-microsoft-365.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Guias de laboratório de teste](m365-enterprise-test-lab-guides.md)

