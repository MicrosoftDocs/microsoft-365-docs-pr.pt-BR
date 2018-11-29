---
title: Gerenciamento de dispositivo móvel para a Contoso
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Entenda como a Contoso usa EMS no Microsoft 365 Enterprise para gerenciar seus dispositivos e aplicativos com base nessa plataforma.
ms.openlocfilehash: e6b6f822a8c0ea26b3d899e3531653b19e225d65
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26864670"
---
# <a name="mobile-device-management-for-contoso"></a>Gerenciamento de dispositivo móvel para a Contoso

**Resumo:** entenda como a Contoso usa EMS no Microsoft 365 Enterprise para gerenciar seus dispositivos e aplicativos com base nessa plataforma.

Enterprise Mobility + Security (EMS) no Microsoft 365 Enterprise consiste do Microsoft Intune e um conjunto de serviços do Azure que dão suporte a segurança e ao gerenciamento de aplicativos e dispositivos móveis.

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
- Criou grupos do Azure AD para grupos de dispositivos para registro e configurações do Intune, além de políticas de acesso condicional
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

## <a name="next-step"></a>Próxima etapa

[Saiba](contoso-info-protect.md) como a Contoso usa os recursos de proteção de informações do Microsoft 365 Enterprise para classificar, identificar e proteger ativos digitais fundamentais em sua organização.

## <a name="see-also"></a>Confira também

[Gerenciamento de dispositivo móvel para o Microsoft 365 Enterprise](mobility-infrastructure.md)

[Guia de implantação](deploy-microsoft-365-enterprise.md)

[Guias de laboratório de teste](m365-enterprise-test-lab-guides.md)

