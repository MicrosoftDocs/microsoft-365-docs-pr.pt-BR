---
title: Usar políticas de prevenção contra perda de dados para aplicativos de nuvem que não são da Microsoft
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Saiba como usar políticas dlp para aplicativos de nuvem que não são da Microsoft.
ms.openlocfilehash: fbba87fc5bb3bbca7e67ba374e202098a22f4a5c
ms.sourcegitcommit: 17d82e5617f0466eb825e15ab88594afcdaf4437
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "53300119"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps-preview"></a>Usar políticas de prevenção contra perda de dados para aplicativos de nuvem que não são da Microsoft (visualização)

As políticas de prevenção contra perda de dados (DLP) para aplicativos de nuvem que não são da Microsoft fazem parte do Microsoft 365 DLP de recursos; usando esses recursos, você pode descobrir e proteger itens confidenciais em Microsoft 365 serviços. Para obter mais informações sobre todas as ofertas de DLP da Microsoft, [consulte Learn about data loss prevention](dlp-learn-about-dlp.md).

Você pode usar políticas de DLP para aplicativos de nuvem que não sejam da Microsoft para monitorar e detectar quando itens confidenciais são usados e compartilhados por meio de aplicativos de nuvem que não são da Microsoft. O uso dessas políticas oferece a visibilidade e o controle necessários para garantir que elas são usadas e protegidas corretamente, e isso ajuda a evitar comportamentos de risco que podem comprometer eles.

## <a name="before-you-begin"></a>Antes de começar

### <a name="skusubscriptions-licensing"></a>Licenciamento SKU/assinaturas

Antes de começar a usar políticas DLP para aplicativos de nuvem que não são da Microsoft, confirme sua assinatura [Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) e quaisquer complementos. Para acessar e usar essa funcionalidade, você deve ter uma dessas assinaturas ou complementos:

- Microsoft 365 E5
- Conformidade do Microsoft 365 E5
- Microsoft 365 E5 Security

### <a name="permissions"></a>Permissões
O usuário que cria a política DLP deve ser:
- Administrador global
- Administrador de conformidade
- Administrador de dados de conformidade

### <a name="prepare-your-cloud-app-security-environment"></a>Preparar seu ambiente Cloud App Security ambiente

As políticas de DLP para aplicativos de nuvem que não são da Microsoft usam Cloud App Security DLP. Para usá-lo, você deve preparar seu ambiente Cloud App Security ambiente. Para obter instruções, consulte [Set instant visibility, protection, and governance actions for your apps](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps).

### <a name="connect-a-non-microsoft-cloud-app"></a>Conexão um aplicativo de nuvem que não seja da Microsoft

Para usar a política de DLP a um aplicativo de nuvem não Microsoft específico, o aplicativo deve estar conectado a Cloud App Security. Para obter informações, consulte:

- [Conexão Box](/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [Conexão Dropbox](/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [Conexão G-Suite](/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [Conexão Salesforce](/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [Conexão Cisco Webex](/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

Depois de conectar seus aplicativos de nuvem Cloud App Security, você pode criar Microsoft 365 DLP para eles.

> [!NOTE]
> Também é possível usar o Microsoft Cloud App Security para criar políticas de DLP para aplicativos de nuvem da Microsoft. No entanto, é recomendável usar o Microsoft 365 para criar e gerenciar políticas de DLP para aplicativos de nuvem da Microsoft.

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a>Criar uma política de DLP para um aplicativo de nuvem que não seja da Microsoft

Quando você selecionar um local para a política DLP, a Microsoft Cloud App Security **local.**

- Para selecionar um aplicativo ou instância específico, selecione **Escolher instância**.
- Se você não selecionar uma instância, a política usará todos os aplicativos conectados em seu Microsoft Cloud App Security locatário.

   ![Locais para aplicar a política](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Box-US e Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

Você pode escolher várias ações para cada aplicativo de nuvem que não seja da Microsoft com suporte. Para cada aplicativo, há diferentes ações possíveis (depende da API do aplicativo na nuvem).

![Criar regra](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

Ao criar uma regra na política DLP, você pode selecionar uma ação para aplicativos de nuvem que não são da Microsoft. Para restringir aplicativos de terceiros, selecione **Restringir Aplicativos de Terceiros.**

![Restringir aplicativos de terceiros](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

> [!NOTE]
> As políticas de DLP aplicadas a aplicativos que não são da Microsoft usam Microsoft Cloud App Security. Quando a política de DLP para um aplicativo não Microsoft é criada, a mesma política será criada automaticamente no Microsoft Cloud App Security.

Para obter informações sobre como criar e configurar políticas DLP, consulte [Create test and tune a DLP policy](./create-test-tune-dlp-policy.md).

## <a name="see-also"></a>Confira também

- [Criar teste e ajustar uma política de DLP](./create-test-tune-dlp-policy.md)
- [Introdução à política DLP padrão](./get-started-with-the-default-dlp-policy.md)
- [Criar uma política DLP a partir de um modelo](./create-a-dlp-policy-from-a-template.md)
