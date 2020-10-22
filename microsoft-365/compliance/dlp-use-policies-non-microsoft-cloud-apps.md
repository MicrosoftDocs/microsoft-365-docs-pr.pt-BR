---
title: Usar políticas de prevenção contra perda de dados para aplicativos de nuvem que não são da Microsoft (versão prévia)
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
description: Saiba como usar políticas de DLP para aplicativos de nuvem que não são da Microsoft.
ms.openlocfilehash: 0b588bf27738a0f9a8078999311294f74e5193c0
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649652"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps-preview"></a>Usar políticas de prevenção contra perda de dados para aplicativos de nuvem que não são da Microsoft (versão prévia)

Políticas de prevenção contra perda de dados (DLP) para aplicativos de nuvem que não são da Microsoft fazem parte do pacote de recursos do Microsoft 365 DLP; usando esses recursos, você pode descobrir e proteger itens confidenciais nos serviços do Microsoft 365. Para obter mais informações sobre todas as ofertas de DLP da Microsoft, consulte [Overview of Data Loss Prevention](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies?view=o365-worldwide).

Você pode usar políticas de DLP para aplicativos de nuvem que não são da Microsoft para monitorar e detectar quando itens confidenciais são usados e compartilhados por aplicativos de nuvem que não são da Microsoft. O uso dessas políticas oferece a visibilidade e o controle de que você precisa para garantir que eles sejam corretamente usados e protegidos, e ajuda a evitar um comportamento arriscado que possa comprometer os usuários.

## <a name="before-you-begin"></a>Antes de começar

### <a name="skusubscriptions-licensing"></a>Licenciamento SKU/assinaturas

Antes de começar a usar políticas DLP para aplicativos de nuvem que não são da Microsoft, confirme sua [assinatura do Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) e outros Complementos. Para acessar e usar essa funcionalidade, você deve ter uma destas assinaturas ou Complementos:

- Microsoft 365 E5
- Conformidade do Microsoft 365 E5
- Segurança do Microsoft 365 E5

### <a name="prepare-your-cloud-app-security-environment"></a>Preparar o ambiente de segurança do seu Cloud app

As políticas de DLP para aplicativos de nuvem que não são da Microsoft usam recursos de DLP do Cloud app Security. Para usá-lo, você deve preparar o ambiente de segurança do seu Cloud app. Para obter instruções, consulte [definir ações instantâneas de visibilidade, proteção e governança para seus aplicativos](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps).

### <a name="connect-a-non-microsoft-cloud-app"></a>Conectar um aplicativo de nuvem que não seja da Microsoft

Para usar a política DLP para um aplicativo de nuvem específico que não seja da Microsoft, o aplicativo deve estar conectado à segurança do aplicativo na nuvem. Para obter informações, consulte:

- [Caixa conectar](https://docs.microsoft.com/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [Conectar o Dropbox](https://docs.microsoft.com/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [Conectar G-Suite](https://docs.microsoft.com/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [Conectar Salesforce](https://docs.microsoft.com/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [Conectar o Cisco WebEx](https://docs.microsoft.com/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

Após conectar seus aplicativos de nuvem à Cloud app Security, você pode criar políticas de DLP da Microsoft 365 para eles.

>[!NOTE]
>Também é possível usar o Microsoft Cloud app Security para criar políticas de DLP para aplicativos de nuvem da Microsoft. No entanto, é recomendável usar o Microsoft 365 para criar e gerenciar políticas de DLP para aplicativos de nuvem da Microsoft.

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a>Criar uma política de DLP para um aplicativo de nuvem que não seja da Microsoft

Ao selecionar um local para a política de DLP, ative o local do **Microsoft Cloud app Security** .

- Para selecionar um aplicativo ou instância específico, selecione **escolher instância**.
- Se você não selecionar uma instância, a política usará todos os aplicativos conectados em seu locatário do Microsoft Cloud app Security.

   ![Locais para aplicar a política](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Box-US e Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

Você pode escolher várias ações para cada aplicativo de nuvem que não seja da Microsoft suportado. Para cada aplicativo, há diferentes ações possíveis (depende da API do aplicativo de nuvem).

![Criar regra](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

Ao criar uma regra na política de DLP, você pode selecionar uma ação para aplicativos de nuvem que não são da Microsoft. Para restringir aplicativos de terceiros, selecione **restringir aplicativos**de terceiros.

![Restringir aplicativos de terceiros](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

Para obter informações sobre como criar e configurar políticas de DLP, consulte [Create Test and ajuste a DLP Policy](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide).

## <a name="see-also"></a>Confira também

- [Criar testar e ajustar uma política de DLP](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide)
- [Introdução à política DLP padrão](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-the-default-dlp-policy?view=o365-worldwide)
- [Criar uma política DLP a partir de um modelo](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template?view=o365-worldwide)
