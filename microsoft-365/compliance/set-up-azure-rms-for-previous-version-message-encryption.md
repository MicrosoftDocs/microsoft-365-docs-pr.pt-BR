---
title: Configurar o Azure Rights Management para a versão anterior de criptografia de mensagem do Office 365
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
description: A versão anterior da criptografia de mensagem do Office 365 depende do Microsoft Azure Rights Management (anteriormente conhecido como gerenciamento de direitos do Windows Azure Active Directory).
ms.openlocfilehash: a6ba18982a65ff9687374b9e5dc370646817d96d
ms.sourcegitcommit: 550ea6f093ec35182e7c65a2811e9bfb07ec7d01
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2019
ms.locfileid: "38684845"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-office-365-message-encryption"></a>Configurar o Azure Rights Management para a versão anterior de criptografia de mensagem do Office 365

Este tópico descreve as etapas que você precisa seguir para ativar e configurar o Azure Rights Management (RMS), parte da proteção de informações do Azure, para uso com a versão anterior do Office 365 Message Encryption (OME).

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a>Este artigo aplica-se somente à versão anterior do OME
Se você ainda não tiver movido a sua organização do Office 365 para os novos recursos do OME, mas já tiver implantado o OME, as informações neste artigo se aplicam à sua organização. A Microsoft recomenda que você faça um plano para migrar para os novos recursos do OME assim que for razoável para sua organização. Para obter instruções, consulte [configurar novos recursos de criptografia de mensagem do Office 365](set-up-new-message-encryption-capabilities.md). Se quiser saber mais sobre como os novos recursos funcionam primeiro, confira criptografia de [mensagem do Office 365](ome.md). O restante deste artigo refere-se ao comportamento OME antes do lançamento dos novos recursos do OME.

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a>Pré-requisitos para usar a versão anterior da criptografia de mensagem do Office 365
<a name="warmprereqs"> </a>

A criptografia de mensagem do Office 365 (OME), incluindo o IRM, depende do Azure Rights Management (Azure RMS). O Azure RMS é a tecnologia de proteção usada pela proteção de informações do Azure. Para usar o OME, sua organização do Office 365 deve incluir uma assinatura do Exchange Online ou do Exchange Online Protection que, por sua vez, inclui uma assinatura do Azure Rights Management.
  
- Se você não tiver certeza sobre o que sua assinatura inclui, consulte as descrições de serviço do Exchange Online para [política, recuperação e conformidade de mensagens](https://technet.microsoft.com/library/exchange-online-message-policy-recovery-and-compliance.aspx).

- Se você não tiver uma assinatura do Azure RMS para Exchange Online ou proteção do Exchange Online, você deverá comprar uma assinatura e ativá-la primeiro.

    Para obter informações sobre como adquirir uma assinatura para o Azure Rights Management, consulte [Azure Rights Management](https://portal.office.com/Signup/MainSignUp15.aspx?&amp;OfferId=9DF77AF9-DAAE-4d51-8E0E-EEEADD4866B8&amp;dl=RIGHTSMANAGEMENT). A seção a seguir oferece informações sobre como ativar o Azure Rights Management.

- Se você tiver o Azure Rights Management, mas ele não estiver configurado para o Exchange Online ou o Exchange Online Protection, este artigo explica como ativar o Azure Rights Management e, em seguida, descreve a melhor maneira de configurar o OME para trabalhar com o Azure Rights Management.

- Se você já configurou o OME para trabalhar com o Azure Rights Management for Exchange Online ou o Exchange Online Protection, dependendo de como você configurou, você pode estar pronto para começar a usar o OME e seus novos recursos imediatamente. Este artigo explica como determinar se você definiu o OME corretamente, o que fazer se você precisar alterar sua configuração e o que acontecerá se você optar por não alterar sua configuração. Por exemplo, para usar os novos recursos, você deve usar o Azure RMS com o OME. Você não pode usar os novos recursos com um RMS do Active Directory local.

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a>Ativar o Azure Rights Management para a versão anterior do OME no Office 365

Você precisa ativar o Azure Rights Management para que os usuários em sua organização possam aplicar a proteção de informações às mensagens que enviam e abrir mensagens e arquivos que foram protegidos pelo serviço de gerenciamento de direitos do Azure. Para obter instruções, consulte [ativando o Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=525775). Após concluir a ativação, retorne aqui e continue com as tarefas deste artigo.
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a>Configurar a versão anterior do OME para usar o Azure RMS importando domínios de publicação confiáveis (TPDs)

Um TPD é um arquivo XML que contém informações sobre as configurações de gerenciamento de direitos da sua organização. Por exemplo, o TPD contém informações sobre o SLC (certificado de licenciante do servidor) usado para assinar e criptografar certificados e licenças, as URLs usadas para licenciamento e publicação e assim por diante. Importe o TPD para a sua organização do Office 365 usando o Windows PowerShell.
  
> [!IMPORTANT]
> Anteriormente, você poderia optar por importar o TPDs do Active Directory Rights Management Service (AD RMS) para sua organização do Office 365. No entanto, isso impedirá que você use os novos recursos do OME e não seja recomendado. Se sua organização do Office 365 estiver atualmente configurada dessa forma, a Microsoft recomenda que você crie um plano para migrar do seu RMS do Active Directory local para a proteção de informações do Azure baseada em nuvem. Para saber mais, confira [migrar do AD RMS para a proteção de informações do Azure](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms). Você não poderá usar os novos recursos do OME até concluir a migração para a proteção de informações do Azure.
  
 **Para importar o TPDs do Azure RMS**
  
1. [Conecte-se ao Exchange Online usando o PowerShell remoto](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).

2. Escolha a URL de compartilhamento de chave que corresponde à localização geográfica da sua organização do Office 365:

|**Location**|**URL do local de compartilhamento de chave**|
|:-----|:-----|
|América do Norte  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|União Europeia  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Ásia  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|América do Sul  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Office 365 para agências governamentais (Nuvem de Comunidade Governamental)  <br/> Esse local de compartilhamento de chave do RMS é reservado para clientes que compraram o Office 365 para SKUs governamentais.  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
   
3. Configure o local de compartilhamento de chave executando o cmdlet [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.160%29.aspx) da seguinte maneira: 
    
  ```powershell
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
  ```

    Por exemplo, para configurar o local de compartilhamento de chave se sua organização estiver localizada na América do Norte:

  ```powershell
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
  ```

4. Execute o cmdlet [Import-RMSTrustedPublishingDomain](https://technet.microsoft.com/library/jj200724%28v=exchg.150%29.aspx) com a opção-RMSOnline para importar o TPD do Azure Rights Management: 

  ```powershell
  Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
  ```

    Onde *TPDName* é o nome que você deseja usar para o TPD. Por exemplo, "contoso North American TPD". 

5. Para verificar se você configurou com êxito sua organização do Office 365 para usar o serviço de gerenciamento de direitos do Azure, execute o cmdlet [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.160%29.aspx) com a opção-RMSOnline da seguinte maneira: 

  ```powershell
  Test-IRMConfiguration -RMSOnline
  ```

    Entre outras coisas, este cmdlet verifica a conectividade com o serviço Azure Rights Management, baixa o TPD e verifica sua validade.

6. Execute o cmdlet [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) da seguinte maneira para desabilitar os modelos de gerenciamento de direitos do Azure para que eles fiquem disponíveis no Outlook na Web e no Outlook: 

  ```powershell
  Set-IRMConfiguration -ClientAccessServerEnabled $false
  ```

7. Execute o cmdlet [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) da seguinte maneira para habilitar o Azure Rights Management para sua organização de email baseada em nuvem e configurá-lo para usar o Azure Rights Management para a criptografia de mensagem do Office 365: 

  ```powershell
  Set-IRMConfiguration -InternalLicensingEnabled $true
  ```

8. Para verificar se você importou com êxito o TPD e habilitou o Azure Rights Management, use o cmdlet Test-IRMConfiguration para testar a funcionalidade de gerenciamento de direitos do Azure. Para obter detalhes, confira "Exemplo 1" em [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.150%29.aspx).

## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a>Tenho a versão anterior do OME configurada com o Active Directory Rights Management e a proteção de informações do Azure, o que eu faço?
<a name="importTPDs"> </a>

Você pode continuar a usar suas regras de fluxo de emails de criptografia de mensagem do Office 365 existentes com o Active Directory Rights Management, mas não pode configurar ou usar os novos recursos do OME. Em vez disso, você precisa migrar para a proteção de informações do Azure. Para obter informações sobre a migração e o que isso significa para a sua organização, confira [Migrate from AD RMS para proteção de informações do Azure](https://docs.microsoft.com/information-protection/deploy-use/prepare-environment-adrms).
  
## <a name="next-steps"></a>Próximas etapas
<a name="importTPDs"> </a>

Depois de concluir a instalação do Azure Rights Management, se você quiser habilitar os novos recursos do OME, confira [configurar os novos recursos de criptografia de mensagens do Office 365 criados sobre a proteção de informações do Azure.](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e)
  
Depois de configurar sua organização para usar os novos recursos do OME, você está pronto para [definir regras de fluxo de emails para proteger as mensagens de email com novos recursos do ome](define-mail-flow-rules-to-encrypt-email.md).
  
## <a name="related-topics"></a>Tópicos relacionados
<a name="importTPDs"> </a>

[Criptografia no Office 365](encryption.md)
  
[Detalhes de referências técnicas sobre a criptografia no Office 365](technical-reference-details-about-encryption.md)
  
[O que é o Azure Rights Management?](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)
