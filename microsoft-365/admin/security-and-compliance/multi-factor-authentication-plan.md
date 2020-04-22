---
title: Planejar a autenticação multifator para implantações do Microsoft 365
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
description: Saiba mais sobre a autenticação multifator no Microsoft 365 e as etapas que você precisa seguir para configurá-lo.
ms.openlocfilehash: 035a79c9db44990dbce09de540e3e483b3cea8df
ms.sourcegitcommit: 7c0470fd7a98911d142bac060c228947c46a6be7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43665663"
---
# <a name="plan-for-multi-factor-authentication-for-microsoft-365-deployments"></a>Planejar a autenticação multifator para implantações do Microsoft 365

A MFA (autenticação multifator) é um método de autenticação que requer o uso de mais de um método de verificação e adiciona uma segunda camada de segurança a transações e conexões de usuário. Ele funciona solicitando uma etapa de verificação de adição com informações além da senha da conta do usuário, como:
  
- Um código de verificação gerado aleatoriamente enviado ao telefone inteligente
    
- Uma chamada telefônica
    
- Um cartão inteligente (físico ou virtual) 
    
- Um dispositivo biométrico 
    
## <a name="mfa-in-microsoft-365"></a>MFA no Microsoft 365

A Microsoft 365 usa a MFA para ajudar a fornecer segurança extra e é gerenciada no centro de administração do Microsoft 365. A Microsoft 365 oferece o seguinte subconjunto de recursos de [autenticação multifator do Azure](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) como parte da assinatura: 
  
- A capacidade de habilitar e impor a MFA para usuários finais
    
- O uso de um aplicativo móvel (on-line e OTP [senha avulsa]) como segundo fator de autenticação
    
- O uso de uma chamada telefônica como segundo fator de autenticação
    
- O uso de uma mensagem de texto SMS (Short Message Service) como um segundo fator de autenticação
    
- Senhas de aplicativo para clientes que não são do navegador (por exemplo, o software de comunicações do Microsoft Lync 2013)
    
- Saudações padrão da Microsoft durante as chamadas de autenticação
    
Para obter a lista completa de recursos adicionados, confira [autenticação multifator do Azure](https://go.microsoft.com/fwlink/?LinkId=506927). Você sempre pode obter a funcionalidade completa comprando [licenças de autenticação multifator do Azure](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-licensing). 
  
Você Obtém um subconjunto de recursos diferentes, dependendo se você usa a identidade somente na nuvem onde as contas de usuário estão presentes no Microsoft 365, ou a configuração híbrida com logon único e o AD FS (serviços de Federação do Active Directory). 
  
|**Onde você gerencia o Microsoft 365?**|**Opções do segundo fator da MFA**|
|:-----|:-----|
|Somente na nuvem  <br/> | Autenticação multifator do Azure (texto ou chamada telefônica)  <br/> |
|Configuração híbrida, gerenciada no local  <br/> | Se você gerencia identidades de usuário no local, tem as seguintes opções:  <br/> – Cartão inteligente físico ou virtual (AD FS)  <br/> -Autenticação multifator do Azure (módulo para AD FS)  <br/>  -Autenticação multifator do Azure  <br/> |
   
Os aplicativos de dispositivo do Office 2013 dão suporte a MFA por meio do uso da [Adal (biblioteca de autenticação do Active Directory)](https://go.microsoft.com/fwlink/p/?LinkId=526684). O Azure Active Directory (Azure AD) hospeda uma página da Web onde os usuários podem entrar. O provedor de identidade pode ser o Azure AD ou um provedor de identidade federada, como o AD FS. A autenticação para usuários federados envolve as seguintes etapas:
  
1. O Azure AD redireciona o usuário para a página da Web de entrada hospedada pelo provedor de identidade do registro da organização. O provedor de identidade é determinado pelo domínio especificado no nome de entrada do usuário.
    
2. O usuário entra na página de entrada da Web em seu dispositivo. 
    
3. O provedor de identidade retorna um token para o Azure AD quando o usuário é conectado com êxito.
    
4. O Azure AD retorna um token Web JSON (JWT) para o aplicativo de dispositivo do Office e o aplicativo do dispositivo é autenticado usando um JWT com o Microsoft 365. 
    
  
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

Para habilitar a MFA de sua assinatura, siga estas etapas:
  
1. Se necessário: 

  - [Habilitar a autenticação moderna do Office 2013 em dispositivos Windows](enable-modern-authentication.md).
    
  - Configurar a autenticação multifator do Azure com serviços de diretório de terceiros.
    
    Consulte [cenários avançados com a autenticação multifator do Azure e soluções VPN de terceiros](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) para obter informações sobre provedores de identidade específicos aceitos para este programa. 
    
2. [Configure o MFA para o Microsoft 365](set-up-multi-factor-authentication.md).
    
3. Diga aos usuários individuais como entrar pela MFA. Consulte [entrar no Microsoft 365 com MFA](https://support.office.com/en-us/article/sign-in-to-microsoft-365-with-2-step-verification-2b856342-170a-438e-9a4f-3c092394d3cb).

> [!IMPORTANT]
> Se você habilitou seus usuários para a autenticação multifator do Azure e eles tiverem dispositivos que executam o Office 2013 que não estão habilitados para autenticação moderna, eles precisarão usar o AppPasswords nesses dispositivos. Mais informações sobre AppPasswords e quando/onde/como devem ser usadas podem ser encontradas aqui: [senhas de aplicativo com a autenticação multifator do Azure](https://go.microsoft.com/fwlink/p/?LinkId=528178).
  
## <a name="faq"></a>Perguntas frequentes

[Perguntas Frequentes sobre o artigo do wiki de Autenticação Moderna](https://go.microsoft.com/fwlink/p/?LinkId=530064)
  
## <a name="known-issues"></a>Problemas conhecidos

[Office 2013 e Microsoft 365 aplicativos para autenticação moderna corporativa: coisas que você precisa saber antes da integração](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 **Solução de problemas da Autenticação Multifator do Azure:**
  
Confira [solução de problemas da autenticação multifator do Azure](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues).
  
[Como solucionar problemas de entrada com a autenticação moderna do Office 2013 ao usar o AD FS](https://support.microsoft.com/kb/3052203/)
  
 **Quando IDs alternativas não funcionam:**
  
[Como usar o PowerShell para corrigir UPN duplicado](https://go.microsoft.com/fwlink/p/?LinkId=396730)
  
[Script para corrigir UPNs duplicados](https://go.microsoft.com/fwlink/p/?LinkId=396725)
  
 **Filtragem de acesso do cliente:**
  
[Aplicativos do Office 2013 e Microsoft 365 para autenticação moderna corporativa e políticas de filtragem de acesso para cliente: coisas que devem ser conhecidas antes da integração](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 **Quais aplicativos dão suporte a MFA?**
  
|**Windows**|**Mac**|**iOS**|**Celular Android**|**Tablet Android**|
|:-----|:-----|:-----|:-----|:-----|
|A autenticação moderna para Word 2013, Word 2016, Excel 2013, Excel 2016, PowerPoint 2013, PowerPoint 2016, OneNote 2013, OneNote 2016, Project 2013, Project 2016, Visio 2013, Visio 2016, Lync 2013 e Skype for Business tem suporte por esta versão.  <br/> |A autenticação moderna para Word 2016 para Mac, Excel 2016 para Mac e PowerPoint 2016 para Mac tem suporte por esta versão.  <br/> |A autenticação moderna para Word para iPad, Excel para iPad e PowerPoint para iPad tem suporte por esta versão.  <br/> |A autenticação moderna do Word para Android, do Excel para Android e do PowerPoint para Android tem suporte nesta versão.  <br/> |A autenticação moderna do Word para Android, do Excel para Android e do PowerPoint para Android tem suporte nesta versão.  <br/> |
|A autenticação moderna para Outlook 2013 e Outlook 2016 tem suporte por esta versão.  <br/> |A autenticação moderna para Outlook 2016 para Mac tem suporte por esta versão.  <br/> |A autenticação moderna do Outlook para iPad tem suporte por esta versão.  <br/> |||
   

