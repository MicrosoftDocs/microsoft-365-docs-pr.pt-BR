---
title: Recursos de proteção na Proteção de Informações do Azure sendo implantadas para locatários existentes
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ad6f58e-65d7-4c82-8e65-0b773666634d
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Este artigo explica as alterações que estão sendo roladas para os recursos de proteção na Proteção de Informações do Azure
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 77d45c8521e67c480b9e5557b05eed8ba5dd2645
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203102"
---
# <a name="protection-features-in-azure-information-protection-rolling-out-to-existing-tenants"></a>Recursos de proteção na Proteção de Informações do Azure sendo implantadas para locatários existentes

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Para ajudar na etapa inicial de proteção de suas informações, a partir de julho de 2018, todos os locatários qualificados da Proteção de Informações do Azure terão os recursos de proteção na Proteção de Informações do Azure habilitados por padrão. Os recursos de proteção na Proteção de Informações do Azure eram anteriormente conhecidos no Office 365 como Gerenciamento de Direitos ou Azure RMS. Se a sua organização tiver um plano de serviço do Office E3 ou um plano de serviço superior, você terá um início inicial protegendo informações por meio da Proteção de Informações do Azure quando lançarmos esses recursos.

## <a name="changes-beginning-july-1-2018"></a>Alterações a partir de 1º de julho de 2018

A partir de 1º de julho de 2018, a Microsoft habilita o recurso de proteção na Proteção de Informações do Azure para todas as organizações com um dos seguintes planos de assinatura:

- A Criptografia de Mensagens do Office 365 é oferecida como parte do Office 365 E3 e E5, Microsoft E3 e E5, Office 365 A1, A3 e A5 e Office 365 G3 e G5. Você não precisa de licenças adicionais para receber os novos recursos de proteção com a Proteção de Informações do Azure.

- Você também pode adicionar o Plano 1 de Proteção de Informações do Azure aos seguintes planos para receber os novos recursos de Criptografia de Mensagens do Office 365: Plano 1 do Exchange Online, Plano 2 do Exchange Online, Office 365 F1, Microsoft 365 Business Basic, Microsoft 365 Business Standard ou Office 365 Enterprise E1.

- Cada usuário que se beneficia da Criptografia de Mensagens do Office 365 precisa ser licenciado para ser coberto pelo recurso.

- Para ver a lista completa, consulte as descrições de serviço [do Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) para Criptografia de Mensagens do Office 365.

Os administradores de locatários podem verificar o status de proteção no portal de administrador do Office 365.

![Captura de tela que mostra que o gerenciamento de direitos no Office 365 está ativado.](../../media/303453c8-e4a5-4875-b49f-e80c3eb7b91e.png)

## <a name="why-are-we-making-this-change"></a>Por que estamos fazendo essa alteração?

A Criptografia de Mensagens do Office 365 aproveita os recursos de proteção na Proteção de Informações do Azure. No centro das melhorias recentes para a Criptografia de Mensagens do Office 365 e nossos investimentos mais amplos na proteção de informações no Microsoft 365, estamos facilitando para as organizações ativarem e usarem nossos recursos de proteção, como historicamente, as tecnologias de criptografia têm sido difíceis de configurar. Ao ligar os recursos de proteção na Proteção de Informações do Azure por padrão, você pode começar rapidamente a proteger seus dados confidenciais.

## <a name="does-this-impact-me"></a>Isso me afeta?

Se sua organização comprou uma licença qualificada do Office 365, seu locatário será afetado por essa alteração.

> [!IMPORTANT]
> Se você estiver usando o Active Directory Rights Management Services (AD RMS) em seu ambiente local, deverá optar por não fazer essa alteração imediatamente ou migrar para a Proteção de Informações do Azure antes de lançarmos essa alteração nos próximos 30 dias. Para obter informações sobre como optar por não fazer isso, consulte "Uso o AD RMS, como faço para não participar?" mais adiante neste artigo. Se preferir migrar, consulte [Migrating from AD RMS to Azure Information Protection.](/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms).

## <a name="can-i-use-azure-information-protection-with-active-directory-rights-management-services-ad-rms"></a>Posso usar a Proteção de Informações do Azure com Active Directory Rights Management Services (AD RMS)?

Não. Este não é um cenário de implantação com suporte. Sem seguir as etapas de aceitação adicionais, alguns computadores podem começar a usar automaticamente o serviço de Gerenciamento de Direitos do Azure e também se conectar ao cluster do AD RMS. Esse cenário não é suportado e tem resultados não confiáveis, portanto, é importante que você opte por essa alteração nos próximos 30 dias antes de lançarmos esses novos recursos. Para obter informações sobre como optar por não fazer isso, consulte "Uso o AD RMS, como faço para não participar?" mais adiante neste artigo. Se preferir migrar, consulte [Migrating from AD RMS to Azure Information Protection.](/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)

## <a name="how-do-i-know-if-im-using-ad-rms"></a>Como saber se estou usando o AD RMS?

Use estas instruções de Preparação do ambiente para o Gerenciamento de Direitos do Azure quando você também tiver Active Directory Rights Management Services [(AD RMS)](/azure/information-protection/deploy-use/prepare-environment-adrms) para verificar se você implantou o AD RMS:

1. Embora opcional, a maioria das implantações do AD RMS publica o ponto de conexão de serviço (SCP) no Active Directory para que os computadores de domínio possam descobrir o cluster do AD RMS.

   Use Edit ADSI para ver se você tem um SCP publicado no Active Directory: CN=Configuration [nome do servidor], CN=Services, CN=RightsManagementServices, CN=SCP

2. Se você não estiver usando um SCP, os computadores windows que se conectam a um cluster do AD RMS devem ser configurados para descoberta de serviço do lado do cliente ou redirecionamento de licenciamento usando o Registro do Windows: `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation or HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSIPC\ServiceLocation` .

Para obter mais informações sobre essas configurações do Registro, consulte [Enabling client-side service discovery by using the Windows Registry](/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry) and [Redirecting licensing server traffic](/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic).

## <a name="i-use-ad-rms-how-do-i-opt-out"></a>Uso o AD RMS, como faço para não fazer isso?

Para não participar da alteração futura, conclua estas etapas:

1. Usando uma conta de estudante ou de trabalho que tenha permissões globais de administrador em sua organização, inicie uma sessão Windows PowerShell e conecte-se ao Exchange Online. Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Execute o cmdlet Set-IRMConfiguration usando a seguinte sintaxe:

  ```powershell
  Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
  ```

## <a name="what-can-i-expect-after-this-change-has-been-made"></a>O que posso esperar depois que essa alteração tiver sido feita?

Depois de habilitada, desde que você não tenha optado, você pode começar a usar a nova versão da Criptografia de Mensagens do Office 365 que foi anunciada no [Microsoft Ignite 2017](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801) e aproveita os recursos de criptografia e proteção da Proteção de Informações do Azure.

![Captura de tela que mostra uma mensagem protegida por OME no Outlook na Web.](../../media/599ca9e7-c05a-429e-ae8d-359f1291a3d8.png)

Para obter mais informações sobre os novos aprimoramentos, consulte Criptografia de Mensagem [do Office 365.](../../compliance/ome.md)