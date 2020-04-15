---
title: Plano para a autenticação multifator para Implantações do Office 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: Saiba mais sobre a autenticação multifator no Office 365 e as etapas que você precisa seguir para configurá-lo.
ms.openlocfilehash: 715baeb0355ab203e890f2c87cf0751eff69e7f8
ms.sourcegitcommit: dbbdeca5a6cd048e1bde9e820a8b8a0d6022c7a2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2020
ms.locfileid: "43503990"
---
# <a name="plan-for-multi-factor-authentication-for-office-365-deployments"></a>Plano para a autenticação multifator para Implantações do Office 365

A MFA (autenticação multifator) é um método de autenticação que requer o uso de mais de um método de verificação e adiciona uma segunda camada de segurança a transações e conexões de usuário. Ele funciona solicitando uma etapa de verificação de adição com informações além da senha da conta do usuário, como:
  
- Uma senha gerada aleatoriamente
    
- Uma chamada telefônica
    
- Um cartão inteligente (físico ou virtual) 
    
- Um dispositivo biométrico 
    
## <a name="mfa-in-office-365"></a>MFA no Office 365

O Office 365 usa MFA para segurança de entrada adicional e pode ser gerenciada para cada conta de usuário individual do centro de administração do Microsoft 365. O Office 365 oferece o seguinte subconjunto de recursos de autenticação multifator do Azure como parte da sua assinatura: 
  
- A capacidade de habilitar e impor a MFA para usuários finais
    
- O uso de um aplicativo móvel (on-line e OTP [senha avulsa]) como segundo fator de autenticação
    
- O uso de uma chamada telefônica como segundo fator de autenticação
    
- O uso de uma mensagem SMS como segundo fator de autenticação
    
- Senhas de aplicativo para clientes que não são do navegador (por exemplo, o software de comunicações do Microsoft Lync 2013)
    
- Saudações padrão da Microsoft durante as chamadas de autenticação
    
Para a lista completa de recursos adicionais, confira [a comparação das versões da autenticação multifator do Azure](https://go.microsoft.com/fwlink/?LinkId=506927). Você sempre pode obter a funcionalidade completa comprando o serviço Autenticação Multifator do Azure. 
  
Você Obtém um subconjunto diferente de recursos dependendo se você tem uma identidade somente na nuvem ou híbrida para o Office 365 ou autenticação federada com o AD FS (serviços de Federação do Active Directory). 
  
|**Onde você gerencia o locatário do Office 365?** | **Opções de segundo fator da MFA**|

|:-----|:-----| | Somente na nuvem  <br/> | Autenticação multifator do Azure (texto ou chamada telefônica)  <br/> | | Configuração híbrida, gerenciada no local  <br/> | Se você gerenciar a identidade do usuário local, terá as seguintes opções:  <br/>  Cartão inteligente físico ou virtual (ao usar o AD FS)  <br/> [Autenticação multifator do Azure](https://go.microsoft.com/fwlink/p/?LinkId=526677) (módulo para AD FS)  <br/>  Autenticação multifator do Azure Active Directory (Azure AD)  <br/> |
   
  
A figura a seguir mostra como os aplicativos de dispositivo do Office 2013 (no Windows) permitem aos usuários entrar com MFA. 

![Modern authentication for Office 2013 device apps.](../../media/dc37645c-b899-4715-b162-d7653bd0aebd.png)

Os aplicativos de dispositivo do Office 2013 dão suporte à autenticação multifator por meio do uso da [Adal (biblioteca de autenticação do Active Directory)](https://go.microsoft.com/fwlink/p/?LinkId=526684). O Azure AD hospeda uma página da Web onde os usuários podem entrar. O provedor de identidade pode ser o Azure AD ou um provedor de identidade federada, como o AD FS. A autenticação para usuários federados envolve as seguintes etapas:
  
1. O Azure AD redireciona o usuário para a página da Web de entrada hospedada pelo provedor de identidade do registro para o locatário do Office 365. O provedor de identidade é determinado pelo domínio especificado no nome de entrada do usuário.
    
2. O usuário entra na página de entrada da Web em seu dispositivo. 
    
3. O provedor de identidade retorna um token para o Azure AD quando o usuário é conectado com êxito.
    
4. O Azure AD retorna um JWT (token Web JSON) para o aplicativo de dispositivo do Office e o aplicativo de dispositivo é autenticado usando um JWT com o Office 365. 
    
  
## <a name="requirements-for-office-2013-client-apps"></a>Requisitos para os aplicativos cliente do Office 2013

Para habilitar a MFA para aplicativos clientes do Office 2013, você deve ter o software a seguir instalado (a versão listada abaixo ou uma versão posterior) dependendo se tem uma [Instalações baseadas em clique para executar](#click-to-run-based-installations) ou uma [Instalações baseada em MSI](#msi-based-installations).
  
Para determinar se a instalação do Office é baseada em MSI ou clique para executar:
  
1. Inicie o Outlook 2013.
    
2. No menu **arquivo** , escolha **conta do Office**.
    
3. Para Outlook 2013 instalações de clique para executar, é exibido um item **Opções de Atualização**. Para instalações baseada em MSI, o item **Opções de Atualização** não é exibido. 
    
    ![Como saber se a sua instalação do Office 2013 é clique para executar ou com base em MSI](../../media/1e75143f-9e37-4e0c-9610-43a80771571e.png)

Sor obter mais informações, consulte o [FAQ sobre o artigo sobre wiki de autenticação moderna](https://go.microsoft.com/fwlink/p/?LinkId=530064).
  
### <a name="click-to-run-based-installations"></a>Instalações baseadas em clique para executar

Para instalações baseadas em clique para executar, você deve ter o seguinte software instalado, com a versão do arquivo listada abaixo ou uma versão posterior do arquivo. Se sua versão do arquivo não é igual ou superior à versão do arquivo listada, atualize-a usando as etapas abaixo.
  
|**Nome do arquivo**|**Caminho de instalação no seu computador**|**Versão do arquivo**|
|:-----|:-----|:-----|
|Ficheiro. DLL  <br/> |C:\Arquivos de Programas\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL  <br/> |15.0.4753.1001  <br/> |
|CSI. DLL  <br/> |CSI.DLL C:\Arquivos de Programas\Microsoft Office 15\root\office15\csi.dll  <br/> |15.0.4753.1000  <br/> |
|Groove. EXE  <br/> |C:\Arquivos de Programas\Microsoft Office 15\root\office15\GROOVE.exe  <br/> |15.0.4763.1000  <br/> |
|Outlook.exe  <br/> |C:\Arquivos de Programas\Microsoft Office 15\root\office15\OUTLOOK.exe  <br/> |15.0.4753.1002  <br/> |
|Adal. DLL  <br/> |C:\Arquivos de Programas\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL  <br/> |1.0.2016.624  <br/> |
|Iexplore. exe  <br/> |C:\Arquivos de Programas\Internet Explorer  <br/> |varia  <br/> |
   
### <a name="msi-based-installations"></a>Instalações baseada em MSI

Para instalações baseadas em MSI, você deve ter o software a seguir instalado com a versão do arquivo listado abaixo ou uma versão posterior do arquivo. Se sua versão do arquivo não é igual ou superior à versão do arquivo listada, atualize-a usando o link na coluna Atualizar artigo da base de dados.
  
|**Nome do arquivo**|**Caminho de instalação no seu computador**|**Onde obter a atualização**|**Versão**|
|:-----|:-----|:-----|:-----|
|Ficheiro. DLL  <br/> |C:\Arquivos de Programas\Common Files\Microsoft Shared\OFFICE15\MSO.DLL  <br/> |[KB3085480](https://support.microsoft.com/kb/3085480) <br/> |15.0.4753.1001  <br/> |
|CSI. DLL  <br/> |C:\Arquivos de Programas\Common Files\Microsoft Shared\OFFICE15\Csi.dll  <br/> |[KB3085504](https://support.microsoft.com/kb/3085504) <br/> |15.0.4753.1000  <br/> |
|Groove. exe  <br/> |C:\Arquivos de Programas\Microsoft Office\Office15\GROOVE.exe  <br/> |[KB3085509](https://support.microsoft.com/kb/3085509) <br/> |15.0.4763.1000  <br/> |
|Outlook.exe  <br/> |C:\Arquivos de Programas\Microsoft Office\Office15\OUTLOOK.EXE  <br/> |[KB3085495](https://support.microsoft.com/kb/3085495) <br/> |15.0.4753.1002  <br/> |
|Adal. DLL  <br/> |C:\Arquivos de Programas\Common Files\Microsoft Shared\OFFICE15\ADAL.DLL  <br/> |[KB3055000](https://support.microsoft.com/kb/3055000) <br/> |1.0.2016.624  <br/> |
|Iexplore. exe  <br/> |C:\Arquivos de Programas\Internet Explorer  <br/> |[MS14-052](https://support.microsoft.com/kb/2977629) <br/> |Não se aplica  <br/> |
   
## <a name="enable-mfa"></a>Habilitar a MFA

Para habilitar a MFA para sua assinatura do Office 365, siga estas etapas:
  
1. Se necessário, [habilite a autenticação moderna para o Office 2013 em dispositivos Windows](enable-modern-authentication.md).
    
2. Para autenticação federada, configure a autenticação multifator do Azure com o serviço de diretório de terceiros.
    
    Consulte [cenários avançados com a autenticação multifator do Azure e soluções VPN de terceiros](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) para obter informações sobre provedores de identidade específicos aceitos para este programa. 
    
3. [Configurar a autenticação multifator para o Office 365](set-up-multi-factor-authentication.md).
    
4. Informe aos usuários como [Configurar a MFA para sua conta de usuário do Office 365](https://support.office.com/article/set-up-2-step-verification-for-office-365-ace1d096-61e5-449b-a875-58eb3d74de14). Depois de configurar o método de autenticação secundário, suas futuras entradas exigirão MFA.
    
> [!IMPORTANT]
> Se você habilitou seus usuários para a autenticação multifator do Azure e eles tiverem dispositivos que executam o Office 2013 que não estão habilitados para autenticação moderna, eles precisarão usar as senhas de aplicativo. Mais informações sobre senhas de aplicativo e quando/onde/como devem ser usadas podem ser encontradas aqui: [senhas de aplicativo com autenticação de Multi_Factor do Azure](https://go.microsoft.com/fwlink/p/?LinkId=528178). 
  
## <a name="known-issues"></a>Problemas conhecidos
  
[Office 2013 e Office 365 ProPlus autenticação moderna: coisas que você precisa saber antes da integração](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 **Solução de problemas da Autenticação Multifator do Azure:**
  
Confira [solução de problemas da autenticação multifator do Azure](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues).
  
[Como solucionar problemas de entrada com a autenticação moderna do Office 2013 ao usar o AD FS](https://support.microsoft.com/kb/3052203/)
  
 **Quando IDs alternativas não funcionam:**
  
[Como usar o PowerShell para corrigir UPN duplicado](https://go.microsoft.com/fwlink/p/?LinkId=396730)
  
[Script para corrigir UPNs duplicados](https://go.microsoft.com/fwlink/p/?LinkId=396725)
  
 **Filtragem de acesso do cliente:**
  
[Autenticação moderna do Office 2013 e do Office 365 ProPlus e políticas de filtragem de acesso do cliente: Como se preparar para a integração](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 **Quais aplicativos dão suporte a MFA?**
  
|**Windows**|**Mac**|**iOS**|**Celular Android**|**Tablet Android**|
|:-----|:-----|:-----|:-----|:-----|
|A autenticação moderna para Word 2013, Word 2016, Excel 2013, Excel 2016, PowerPoint 2013, PowerPoint 2016, OneNote 2013, OneNote 2016, Project 2013, Project 2016, Visio 2013, Visio 2016, Lync 2013 e Skype for Business tem suporte por esta versão.  <br/> |A autenticação moderna para Word 2016 para Mac, Excel 2016 para Mac e PowerPoint 2016 para Mac tem suporte por esta versão.  <br/> |A autenticação moderna para Word para iPad, Excel para iPad e PowerPoint para iPad tem suporte por esta versão.  <br/> |A autenticação moderna do Word para Android, do Excel para Android e do PowerPoint para Android tem suporte nesta versão.  <br/> |A autenticação moderna do Word para Android, do Excel para Android e do PowerPoint para Android tem suporte nesta versão.  <br/> |
|A autenticação moderna para Outlook 2013 e Outlook 2016 tem suporte por esta versão.  <br/> |A autenticação moderna para Outlook 2016 para Mac tem suporte por esta versão.  <br/> |A autenticação moderna do Outlook para iPad tem suporte por esta versão.  <br/> |||
   

