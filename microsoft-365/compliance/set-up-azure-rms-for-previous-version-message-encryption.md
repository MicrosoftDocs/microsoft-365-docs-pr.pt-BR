---
title: Configurar o Gerenciamento de Direitos do Azure para a versão anterior da Criptografia de Mensagens
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2cba47b3-f09e-4911-9207-ac056fcb9db7
description: A versão anterior do Criptografia de Mensagens do Office 365 depende Microsoft Azure Gerenciamento de Direitos (anteriormente conhecido como gerenciamento de direitos Windows Azure Active Directory direitos).
ms.openlocfilehash: 978a8027c79de574b80aeedabcbbd51fa6f9e2a0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919487"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-message-encryption"></a>Configurar o Gerenciamento de Direitos do Azure para a versão anterior da Criptografia de Mensagens

Este tópico descreve as etapas que você precisa seguir para ativar e configurar o Azure Rights Management (RMS), parte da Proteção de Informações do Azure, para uso com a versão anterior do Criptografia de Mensagens do Office 365 (OME).

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a>Este artigo só se aplica à versão anterior do OME

Se você ainda não moveu sua organização para os novos recursos OME, mas já implantou o OME, as informações neste artigo se aplicarão à sua organização. A Microsoft recomenda que você faça um plano para mover para os novos recursos OME assim que for razoável para sua organização. Para obter instruções, [consulte Set up new Criptografia de Mensagens do Office 365 capabilities](set-up-new-message-encryption-capabilities.md). Se você quiser saber mais sobre como os novos recursos funcionam primeiro, [consulte Criptografia de Mensagens do Office 365](ome.md). O restante deste artigo refere-se ao comportamento OME antes da versão dos novos recursos OME.

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a>Pré-requisitos para usar a versão anterior do Criptografia de Mensagens do Office 365
<a name="warmprereqs"> </a>

Criptografia de Mensagens do Office 365 (OME), incluindo IRM, depende do Azure Rights Management (Azure RMS). O Azure RMS é a tecnologia de proteção usada pela Proteção de Informações do Azure. Para usar o OME, sua organização deve incluir uma assinatura Exchange Online ou Proteção do Exchange Online que, por sua vez, inclui uma assinatura de Gerenciamento de Direitos do Azure.
  
- Se você não tiver certeza do que sua assinatura inclui, consulte as descrições Exchange Online de serviço para Política de Mensagem, Recuperação [e Conformidade.](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)

- Se você tiver o Azure Rights Management, mas ele não estiver definido para o Exchange Online ou Proteção do Exchange Online, este artigo explica como ativar o Gerenciamento de Direitos do Azure e, em seguida, descreve a melhor maneira de configurar o OME para trabalhar com o Gerenciamento de Direitos do Azure.

- Se você já definiu o OME para trabalhar com o Gerenciamento de Direitos do Azure para Exchange Online ou Proteção do Exchange Online, dependendo de como você a configurar, talvez esteja pronto para começar a usar o OME e seus novos recursos imediatamente. Este artigo explica como determinar se você definiu o OME corretamente, o que fazer se precisar alterar sua configuração e o que acontece se você optar por não alterar sua configuração. Por exemplo, para usar os novos recursos, você deve usar o Azure RMS com o OME. Não é possível usar os novos recursos com um RMS do Active Directory local.

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a>Ativar o Gerenciamento de Direitos do Azure para a versão anterior do OME no Office 365

Você precisa ativar o Gerenciamento de Direitos do Azure para que os usuários em sua organização possam aplicar proteção de informações às mensagens enviadas e abrir mensagens e arquivos protegidos pelo serviço de Gerenciamento de Direitos do Azure. Para obter instruções, [consulte Ativando o Gerenciamento de Direitos do Azure](/azure/information-protection/activate-service). Depois de concluir a ativação, retorne aqui e continue com as tarefas deste artigo.
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a>Configurar a versão anterior do OME para usar o Azure RMS importando domínios de publicação confiáveis (TPDs)

Um TPD é um arquivo XML que contém informações sobre as configurações de gerenciamento de direitos da sua organização. Por exemplo, o TPD contém informações sobre o certificado licenciador do servidor (SLC) usado para assinar e criptografar certificados e licenças, as URLs usadas para licenciamento e publicação, e assim por diante. Você importa o TPD para sua organização usando Windows PowerShell.
  
> [!IMPORTANT]
> Anteriormente, você poderia optar por importar TPDs do serviço de Gerenciamento de Direitos do Active Directory (AD RMS) para sua organização. No entanto, isso impedirá que você use os novos recursos OME e não é recomendado. Se sua organização estiver configurada no momento dessa forma, a Microsoft recomenda que você crie um plano para migrar do RMS do Active Directory local para a Proteção de Informações do Azure baseada na nuvem. Para obter mais informações, [consulte Migrating from AD RMS to Azure Information Protection](/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms). Você não poderá usar os novos recursos OME até concluir a migração para a Proteção de Informações do Azure.
  
 **Para importar TPDs do Azure RMS**
  
1. [Conexão usar Exchange Online PowerShell Remoto.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Escolha a URL de compartilhamento de chaves que corresponde à localização geográfica da sua organização:

|**Location**|**URL de local de compartilhamento de chaves**|
|:-----|:-----|
|América do Norte  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|União Europeia  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Ásia  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|América do Sul  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Office 365 para agências governamentais (Nuvem de Comunidade Governamental)  <br/> Esse local de compartilhamento de chaves RMS é reservado para clientes que compraram Office 365 SKUs do Governo.  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
  
3. Configure o local de compartilhamento de chaves executando o cmdlet [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) da seguinte forma: 

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
   ```
  
   Por exemplo, para configurar o local de compartilhamento de chaves se sua organização estiver localizada na América do Norte:

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
   ```

4. Execute o cmdlet [Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain) com a opção -RMSOnline para importar o TPD do Azure Rights Management: 

   ```powershell
   Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
   ```

   Onde  *TPDName*  é o nome que você deseja usar para o TPD. Por exemplo, "Contoso TPD norte-americano". 

5. Para verificar se você configurou com êxito sua organização para usar o serviço de Gerenciamento de Direitos do Azure, execute o cmdlet [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration) com a opção -RMSOnline da seguinte maneira:

   ```powershell
   Test-IRMConfiguration -RMSOnline
   ```

   Entre outras coisas, este cmdlet verifica a conectividade com o serviço de Gerenciamento de Direitos do Azure, baixa o TPD e verifica sua validade.

6. Execute o cmdlet [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) da seguinte forma para desabilitar os modelos de Gerenciamento de Direitos do Azure de estarem disponíveis no Outlook na Web e Outlook: 

   ```powershell
   Set-IRMConfiguration -ClientAccessServerEnabled $false
   ```

7. Execute o cmdlet [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) da seguinte forma para habilitar o Gerenciamento de Direitos do Azure para sua organização de email baseada em nuvem e configurá-lo para usar o Gerenciamento de Direitos do Azure para Criptografia de Mensagens do Office 365:

   ```powershell
   Set-IRMConfiguration -InternalLicensingEnabled $true
   ```

8. Para verificar se você importou com êxito o TPD e habilitar o Gerenciamento de Direitos do Azure, use o cmdlet Test-IRMConfiguration para testar a funcionalidade de Gerenciamento de Direitos do Azure. Para obter detalhes, confira "Exemplo 1" em [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration).

## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a>Tenho a versão anterior do OME configurada com o Gerenciamento de Direitos do Active Directory e não a Proteção de Informações do Azure, o que faço?
<a name="importTPDs"> </a>

Você pode continuar a usar suas regras de fluxo de email Criptografia de Mensagens do Office 365 existentes com o Gerenciamento de Direitos do Active Directory, mas não pode configurar ou usar os novos recursos OME. Em vez disso, você precisa migrar para a Proteção de Informações do Azure. Para obter informações sobre migração e o que isso significa para sua organização, consulte [Migrating from AD RMS to Azure Information Protection](/information-protection/deploy-use/prepare-environment-adrms).
  
## <a name="next-steps"></a>Próximas etapas
<a name="importTPDs"> </a>

Depois de concluir a instalação do Gerenciamento de Direitos do Azure, se quiser habilitar os novos recursos OME, consulte Configurar novos recursos Criptografia de Mensagens do Office 365 do Azure com base na Proteção de Informações do [Azure.](./set-up-new-message-encryption-capabilities.md)
  
Depois de configurar sua organização para usar os novos recursos OME, você estará pronto para Definir regras de fluxo de emails para proteger mensagens de email com novos recursos [OME.](define-mail-flow-rules-to-encrypt-email.md)
  
## <a name="related-topics"></a>Tópicos relacionados
<a name="importTPDs"> </a>

[Criptografia no Office 365](encryption.md)
  
[Detalhes de referências técnicas sobre a criptografia no Office 365](technical-reference-details-about-encryption.md)
  
[ O que é o Azure Rights Management? ](/information-protection/understand-explore/what-is-azure-rms)