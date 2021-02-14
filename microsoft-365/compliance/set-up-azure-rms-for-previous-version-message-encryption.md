---
title: Configurar o Azure Rights Management para a versão anterior da Criptografia de Mensagens
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
description: A versão anterior da Criptografia de Mensagens do Office 365 depende do Microsoft Azure Rights Management (anteriormente conhecido como Windows Azure Active Directory Rights Management).
ms.openlocfilehash: 879f4ec1db8a8cfe1fe3c8d3b1dd9e1fc68dd687
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44165912"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-message-encryption"></a>Configurar o Azure Rights Management para a versão anterior da Criptografia de Mensagens

Este tópico descreve as etapas que você precisa seguir para ativar e configurar o Azure Rights Management (RMS), parte da Proteção de Informações do Azure, para uso com a versão anterior da Criptografia de Mensagens do Office 365 (OME).

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a>Este artigo só se aplica à versão anterior do OME

Se você ainda não moveu sua organização para os novos recursos do OME, mas já implantou o OME, as informações neste artigo se aplicarão à sua organização. A Microsoft recomenda que você faça um plano para mudar para os novos recursos do OME assim que for razoável para sua organização. Para obter instruções, confira Configurar novos recursos de Criptografia de Mensagem do [Office 365.](set-up-new-message-encryption-capabilities.md) Se você quiser saber mais sobre como os novos recursos funcionam primeiro, confira a Criptografia de Mensagem do [Office 365.](ome.md) O restante deste artigo se refere ao comportamento do OME antes do lançamento dos novos recursos do OME.

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a>Pré-requisitos para usar a versão anterior da Criptografia de Mensagens do Office 365
<a name="warmprereqs"> </a>

A Criptografia de Mensagens do Office 365 (OME), incluindo o IRM, depende do Azure Rights Management (Azure RMS). O Azure RMS é a tecnologia de proteção usada pela Proteção de Informações do Azure. Para usar o OME, sua organização deve incluir uma assinatura do Exchange Online ou do Exchange Online Protection que, por sua vez, inclua uma assinatura do Azure Rights Management.
  
- Se você não tiver certeza do que sua assinatura inclui, consulte as descrições de serviço do Exchange Online para Política [de Mensagens, Recuperação e Conformidade.](https://technet.microsoft.com/library/exchange-online-message-policy-recovery-and-compliance.aspx)

- Se você tiver o Azure Rights Management, mas ele não estiver definido para o Exchange Online ou o Proteção do Exchange Online, este artigo explica como ativar o Azure Rights Management e descreve a melhor maneira de configurar o OME para trabalhar com o Azure Rights Management.

- Se você já tiver definido o OME para trabalhar com o Azure Rights Management para o Exchange Online ou o Exchange Online Protection, dependendo de como você a tiver definido, talvez esteja pronto para começar a usar o OME e seus novos recursos imediatamente. Este artigo explica como determinar se você definiu o OME corretamente, o que fazer se precisar alterar sua configuração e o que acontece se você optar por não alterar sua configuração. Por exemplo, para usar os novos recursos, você deve usar o Azure RMS com o OME. Não é possível usar os novos recursos com um RMS do Active Directory local.

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a>Ativar o Azure Rights Management para a versão anterior do OME no Office 365

Você precisa ativar o Azure Rights Management para que os usuários em sua organização possam aplicar proteção de informações às mensagens que eles enviam e abrir mensagens e arquivos que foram protegidos pelo serviço Azure Rights Management. Para obter instruções, [confira Ativar o Azure Rights Management.](https://go.microsoft.com/fwlink/p/?LinkId=525775) Depois de concluir a ativação, retorne aqui e continue com as tarefas neste artigo.
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a>Configurar a versão anterior do OME para usar o Azure RMS importando domínios de publicação confiáveis (TPDs)

Um TPD é um arquivo XML que contém informações sobre as configurações de gerenciamento de direitos da sua organização. Por exemplo, o TPD contém informações sobre o certificado licenciador de servidor (SLC) usado para assinatura e criptografia de certificados e licenças, as URLs usadas para licenciamento e publicação e assim por diante. Você importa o TPD para sua organização usando o Windows PowerShell.
  
> [!IMPORTANT]
> Anteriormente, você podia optar por importar TPDs do serviço Active Directory Rights Management (AD RMS) para sua organização. No entanto, fazer isso impedirá que você use os novos recursos do OME e não é recomendável. Se sua organização estiver configurada no momento dessa maneira, a Microsoft recomenda que você crie um plano para migrar de seu Active Directory RMS local para a Proteção de Informações do Azure baseada em nuvem. Para saber mais, confira [Migrar do AD RMS para a Proteção de Informações do Azure.](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) Você não poderá usar os novos recursos do OME até concluir a migração para a Proteção de Informações do Azure.
  
 **Para importar TPDs do Azure RMS**
  
1. [Conecte-se ao Exchange Online usando o PowerShell Remoto.](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)

2. Escolha a URL de compartilhamento de chave que corresponde à localização geográfica da sua organização:

|**Location**|**URL do local de compartilhamento de chaves**|
|:-----|:-----|
|América do Norte  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|União Europeia  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Ásia  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|América do Sul  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Office 365 para agências governamentais (Nuvem de Comunidade Governamental)  <br/> Esse local de compartilhamento de chaves do RMS é reservado para clientes que compraram SKUs do Office 365 para o Governo.  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
  
3. Configure o local de compartilhamento de chaves executando o cmdlet [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.160%29.aspx) da seguinte forma: 

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
   ```
  
   Por exemplo, para configurar o local de compartilhamento de chaves se sua organização estiver localizada na América do Norte:

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
   ```

4. Execute o cmdlet [Import-RMSTrustedPublishingDomain](https://technet.microsoft.com/library/jj200724%28v=exchg.150%29.aspx) com a opção -RMSOnline para importar o TPD do Azure Rights Management: 

   ```powershell
   Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
   ```

   Onde  *TPDName*  é o nome que você deseja usar para o TPD. Por exemplo, "Contoso North American TPD". 

5. Para verificar se você configurou com êxito sua organização para usar o serviço Azure Rights Management, execute o cmdlet [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.160%29.aspx) com a opção -RMSOnline da seguinte maneira:

   ```powershell
   Test-IRMConfiguration -RMSOnline
   ```

   Entre outras coisas, este cmdlet verifica a conectividade com o serviço Azure Rights Management, baixa o TPD e verifica sua validade.

6. Execute o cmdlet [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) da seguinte forma para desabilitar a disponibilidade de modelos do Azure Rights Management no Outlook na Web e no Outlook: 

   ```powershell
   Set-IRMConfiguration -ClientAccessServerEnabled $false
   ```

7. Execute o cmdlet [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) da seguinte forma para habilitar o Azure Rights Management para sua organização de email baseada em nuvem e configurá-lo para usar o Azure Rights Management para a Criptografia de Mensagens do Office 365:

   ```powershell
   Set-IRMConfiguration -InternalLicensingEnabled $true
   ```

8. Para verificar se você importou com êxito o TPD e habilitar o Azure Rights Management, use o cmdlet Test-IRMConfiguration para testar a funcionalidade do Azure Rights Management. Para obter detalhes, confira "Exemplo 1" em [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.150%29.aspx).

## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a>Tenho a versão anterior do OME configurada com o Active Directory Rights Management e não com a Proteção de Informações do Azure, o que devo fazer?
<a name="importTPDs"> </a>

Você pode continuar a usar as regras de fluxo de email existentes da Criptografia de Mensagens do Office 365 com o Active Directory Rights Management, mas não pode configurar ou usar os novos recursos do OME. Em vez disso, você precisa migrar para a Proteção de Informações do Azure. Para obter informações sobre migração e o que isso significa para sua organização, consulte Migrando do [AD RMS para a Proteção de Informações do Azure.](https://docs.microsoft.com/information-protection/deploy-use/prepare-environment-adrms)
  
## <a name="next-steps"></a>Próximas etapas
<a name="importTPDs"> </a>

Depois de concluir a configuração do Azure Rights Management, se quiser habilitar os novos recursos do OME, confira Configurar os novos recursos de Criptografia de Mensagens do [Office 365](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities) com base na Proteção de Informações do Azure.
  
Depois de configurar sua organização para usar os novos recursos do OME, você estará pronto para definir regras de fluxo de emails para proteger mensagens de email com novos [recursos do OME.](define-mail-flow-rules-to-encrypt-email.md)
  
## <a name="related-topics"></a>Tópicos relacionados
<a name="importTPDs"> </a>

[Criptografia no Office 365](encryption.md)
  
[Detalhes de referências técnicas sobre a criptografia no Office 365](technical-reference-details-about-encryption.md)
  
[ O que é o Azure Rights Management? ](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)
