---
title: Recursos de proteção na proteção de informações do Azure distribuindo-se para locatários existentes
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ad6f58e-65d7-4c82-8e65-0b773666634d
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Este artigo explica as alterações que estão sendo implantadas nos recursos de proteção da proteção de informações do Azure
ms.openlocfilehash: 070b0d1af0576391ce5f22a827975d1541646454
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203594"
---
# <a name="protection-features-in-azure-information-protection-rolling-out-to-existing-tenants"></a>Recursos de proteção na proteção de informações do Azure distribuindo-se para locatários existentes

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Para ajudar na etapa inicial de proteger suas informações, Iniciando em julho de 2018 todos os locatários qualificados de proteção de informações do Azure terão os recursos de proteção da proteção de informações do Azure ativados por padrão. Os recursos de proteção na proteção de informações do Azure eram conhecidos anteriormente no Office 365 como o gerenciamento de direitos ou o Azure RMS. Se sua organização tiver um plano de serviço do Office E3 ou um plano de serviço mais alto, você agora terá uma partida para proteger as informações por meio da proteção de informações do Azure quando esses recursos forem distribuídos.

## <a name="changes-beginning-july-1-2018"></a>Alterações começando em 1º de julho de 2018

A partir de 1º de julho de 2018, a Microsoft habilitará o recurso de proteção na proteção de informações do Azure para todas as organizações com um dos seguintes planos de assinatura:

- A criptografia de mensagem do Office 365 é oferecida como parte do Office 365 E3 e e5, Microsoft E3 e e5, Office 365 a1, a3 e a5 e Office 365 G3 e G5. Você não precisa de licenças adicionais para receber os novos recursos de proteção do para a proteção de informações do Azure.

- Você também pode adicionar o plano de proteção de informações do Azure 1 aos seguintes planos para receber os novos recursos de criptografia de mensagens do Office 365: Exchange Online plano 1, Exchange Online Plan 2, Office 365 F1, Microsoft 365 Business Basic, Microsoft 365 Business Standard ou Office 365 Enterprise E1.

- Todos os usuários que se beneficiam da criptografia de mensagens do Office 365 precisam ser licenciados para serem cobertos pelo recurso.

- Para obter a lista completa, consulte as [descrições de serviço do Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) para a criptografia de mensagem do Office 365.

Os administradores de locatários podem verificar o status de proteção no portal do administrador do Office 365.

![Captura de tela que mostra que o gerenciamento de direitos no Office 365 está ativado.](../../media/303453c8-e4a5-4875-b49f-e80c3eb7b91e.png)

## <a name="why-are-we-making-this-change"></a>Por que estamos fazendo essa alteração?

A criptografia de mensagem do Office 365 aproveita os recursos de proteção na proteção de informações do Azure. No coração das recentes melhorias na criptografia de mensagens do Office 365 e em nossos investimentos mais amplos para proteção de informações no Microsoft 365, estamos facilitando a ativação e o uso de nossos recursos de proteção, conforme historicamente, as tecnologias de criptografia foram difíceis de configurar. Ao ativar os recursos de proteção na proteção de informações do Azure por padrão, você pode começar rapidamente a proteger seus dados confidenciais.

## <a name="does-this-impact-me"></a>Isso me afeta?

Se sua organização comprou uma licença do Office 365 qualificada, o locatário será afetado por essa alteração.

 **Important!** Se você estiver usando o Active Directory Rights Management Services (AD RMS) em seu ambiente local, você deverá recusar essa alteração imediatamente ou migrar para a proteção de informações do Azure antes de distribuir essa alteração nos próximos 30 dias. Para obter informações sobre como recusar, consulte "Eu uso AD RMS, como faço para sair?" mais adiante neste artigo. Se preferir migrar, confira [Migrate from AD RMS para proteção de informações do Azure.](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)

## <a name="can-i-use-azure-information-protection-with-active-directory-rights-management-services-ad-rms"></a>Posso usar a proteção de informações do Azure com o Active Directory Rights Management Services (AD RMS)?

Não. Este não é um cenário de implantação com suporte. Sem realizar as etapas adicionais de recusa, alguns computadores podem começar automaticamente usando o serviço de gerenciamento de direitos do Azure e também se conectam ao seu cluster AD RMS. Este cenário não é suportado e não tem resultados confiáveis, portanto, é importante que você cancele essa alteração nos próximos 30 dias antes de distribuir esses novos recursos. Para obter informações sobre como recusar, consulte "Eu uso AD RMS, como faço para sair?" mais adiante neste artigo. Se preferir migrar, confira [Migrate from AD RMS para proteção de informações do Azure.](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)

## <a name="how-do-i-know-if-im-using-ad-rms"></a>Como saber se estou usando o AD RMS?

Use estas instruções [para preparar o ambiente para o Azure Rights Management quando você também tiver o Active Directory Rights Management Services (AD RMS)](https://docs.microsoft.com/azure/information-protection/deploy-use/prepare-environment-adrms) para verificar se você implantou o AD RMS:

1. Embora opcional, a maioria das implantações do AD RMS publica o SCP (ponto de conexão de serviço) no Active Directory para que os computadores do domínio possam descobrir o cluster do AD RMS.

Use o ADSI Edit para ver se você tem um SCP publicado no Active Directory: CN = Configuration [Server Name], CN = Services, CN = RightsManagementServices, CN = SCP

2. Se você não estiver usando um SCP, os computadores Windows que se conectam a um cluster do AD RMS devem ser configurados para descoberta de serviço no lado do cliente ou redirecionamento de licenciamento usando o registro do Windows: HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\MSIPC\ServiceLocation ou HKEY_LOCAL_MACHINE \SOFTWARE\Wow6432Node\Microsoft\MSIPC\ServiceLocation

Para obter mais informações sobre essas configurações do registro, consulte [habilitar a descoberta de serviço no lado do cliente usando o registro do Windows](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry) e [redirecionando o tráfego do servidor de licenciamento](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic).

## <a name="i-use-ad-rms-how-do-i-opt-out"></a>Eu uso o AD RMS, como posso sair?

Para recusar a próxima alteração, conclua estas etapas:

1. Usando uma conta corporativa ou de estudante que tenha permissões de administrador global em sua organização, inicie uma sessão do Windows PowerShell e conecte-se ao Exchange Online. Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

2. Execute o cmdlet Set-IRMConfiguration usando a seguinte sintaxe:

  ```powershell
  Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
  ```

## <a name="what-can-i-expect-after-this-change-has-been-made"></a>O que posso esperar após esta alteração ser feita?

Após a habilitação, contanto que você não tenha optado por sair, é possível começar a usar a nova versão da criptografia de mensagem do Office 365 que foi anunciada no [Microsoft Ignite 2017](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801) e aproveita os recursos de criptografia e proteção da proteção de informações do Azure.

![Captura de tela que mostra uma mensagem protegida do OME no Outlook na Web.](../../media/599ca9e7-c05a-429e-ae8d-359f1291a3d8.png)

Para obter mais informações sobre os novos aprimoramentos, confira [criptografia de mensagem do Office 365](../../compliance/ome.md).
