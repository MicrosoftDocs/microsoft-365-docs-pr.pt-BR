---
title: Etapa 5. Gerenciamento de dispositivos e aplicativos para locatários do Microsoft 365 para empresas
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
ms.custom:
- Ent_Solutions
description: Implante a opção correta para gerenciamento de dispositivos e aplicativos para seus locatários do Microsoft 365.
ms.openlocfilehash: a581af3ec2ec192112656f1919e27f5b05a41cb1
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908438"
---
# <a name="step-5-device-and-app-management-for-your-microsoft-365-for-enterprise-tenants"></a>Etapa 5. Gerenciamento de dispositivos e aplicativos para locatários do Microsoft 365 para empresas

O Microsoft 365 para empresas inclui recursos para ajudar a gerenciar dispositivos e o uso de aplicativos nesses dispositivos em sua organização com gerenciamento de dispositivo móvel (MDM) e gerenciamento de aplicativo móvel (MAM). Você pode gerenciar dispositivos iOS, Android, macOS e Windows para proteger o acesso aos recursos da sua organização, incluindo seus dados. Por exemplo, você pode impedir que emails são enviados para pessoas de fora da sua organização ou isolar dados da organização de dados pessoais nos dispositivos pessoais do seu funcionário.

Aqui está um exemplo de validação e gerenciamento de usuários, seus dispositivos e seu uso de aplicativos de produtividade local e na nuvem, como o Microsoft Teams.

![Validação e gerenciamento de usuários, dispositivos e aplicativos](../media/tenant-management-overview/tenant-management-device-app-mgmt.png)

Para ajudar você a proteger os recursos da sua organização, o Microsoft 365 para empresas inclui recursos para ajudar a gerenciar dispositivos e seu acesso a aplicativos. Há duas opções de gerenciamento de dispositivos:

- Microsoft Intune, que é uma solução abrangente de gerenciamento de dispositivos e aplicativos para empresas.
- Mobilidade básica e segurança, que é um subconjunto de serviços do Intune incluídos em todos os produtos do Microsoft 365 para gerenciar dispositivos em sua organização. Para obter mais informações, [consulte Recursos de Mobilidade Básica e Segurança.](https://docs.microsoft.com/microsoft-365/admin/basic-mobility-security/capabilities)

Se você tiver o Microsoft 365 E3 ou E5, deverá usar o Intune.

## <a name="microsoft-intune"></a>Microsoft Intune

Você usa [o Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide) para gerenciar o acesso à sua organização usando MDM ou MAM. O MDM é quando os usuários "registram" seus dispositivos no Intune. Depois que um dispositivo é inscrito, ele é um dispositivo gerenciado e pode receber as políticas, regras e configurações da sua organização. Por exemplo, você pode instalar aplicativos específicos, criar uma política de senha, instalar uma conexão VPN e muito mais.

Os usuários com seus próprios dispositivos pessoais podem não querer registrar seus dispositivos ou ser gerenciados pelo Intune e pelas políticas da sua organização. Mas você ainda precisa proteger os recursos e dados da sua organização. Nesse cenário, você pode proteger seus aplicativos usando o MAM. Por exemplo, você pode usar uma política de MAM que exija que um usuário insira um PIN ao acessar o SharePoint no dispositivo.

Você também determinará como gerenciará dispositivos pessoais e dispositivos de propriedade da organização. Talvez você queira tratar os dispositivos de maneira diferente, dependendo de seus usos.

## <a name="identity-and-device-access-configurations"></a>Identidade e configurações de acesso ao dispositivo

A Microsoft fornece um conjunto de configurações de acesso a identidades e [dispositivos](../security/office-365-security/microsoft-365-policies-configurations.md) para garantir uma força de trabalho segura e produtiva. Essas configurações incluem o uso de:

- Políticas de Acesso Condicional do Azure AD
- Conformidade de dispositivos e políticas de proteção de aplicativos do Microsoft Intune
- Políticas de risco de usuário do Azure AD Identity Protection
- Políticas adicionais de aplicativos de nuvem

Aqui está um exemplo da aplicação dessas configurações e políticas para validar e restringir usuários, seus dispositivos e seu uso de aplicativos de produtividade local e na nuvem, como o Microsoft Teams.

![Configurações de acesso a identidades e dispositivos para requisitos e restrições de usuários, dispositivos e uso de aplicativos](../media/tenant-management-overview/tenant-management-device-app-mgmt-golden-config.png)

Para acesso de dispositivos e gerenciamento de aplicativos, use as configurações destes artigos:

- [Pré-requisitos](../security/office-365-security/identity-access-prerequisites.md)
- [Identidade comum e políticas de acesso ao dispositivo](../security/office-365-security/identity-access-policies.md)

## <a name="results-of-step-5"></a>Resultados da Etapa 5

Para o gerenciamento de dispositivos e aplicativos para seu locatário do Microsoft 365, você determinou as configurações e políticas do Intune para validar e restringir os usuários, seus dispositivos e o uso de aplicativos de produtividade local e na nuvem.

Aqui está um exemplo de locatário com gerenciamento de dispositivos e aplicativos do Intune com os novos elementos destacados.

![Exemplo de um locatário com gerenciamento de dispositivos e aplicativos do Intune](../media/tenant-management-overview/tenant-management-tenant-build-step5.png)

Nesta ilustração, o locatário tem:

- Dispositivos de propriedade da organização inscritos no Intune.
- Políticas de dispositivos e aplicativos do Intune para dispositivos inscritos e pessoais.

## <a name="ongoing-maintenance-for-device-and-app-management"></a>Manutenção contínua para gerenciamento de dispositivos e aplicativos

Em uma base contínua, talvez seja necessário: 

- Gerencie o registro do dispositivo.
- Revise suas configurações e políticas para aplicativos, dispositivos e requisitos de segurança adicionais.
