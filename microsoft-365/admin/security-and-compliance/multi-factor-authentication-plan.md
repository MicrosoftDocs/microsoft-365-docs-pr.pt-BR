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
ms.openlocfilehash: c3d5e83b951e4fd4a05cb18408ecb3d26e397cf9
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42251402"
---
# <a name="plan-for-multi-factor-authentication-for-office-365-deployments"></a>Plano para a autenticação multifator para Implantações do Office 365

A MFA (autenticação multifator) é um método de autenticação que requer o uso de mais de um método de verificação e adiciona uma segunda camada de segurança a transações e conexões de usuário. Ela funciona solicitando dois ou mais dos seguintes métodos de verificação:
  
- Uma senha gerada aleatoriamente
    
- Uma chamada telefônica
    
- Um cartão inteligente (físico ou virtual) 
    
- Um dispositivo biométrico 
    
## <a name="multi-factor-authentication-in-office-365"></a>Autenticação multifator no Office 365

O Office 365 usa a autenticação multifator para ajudar a fornecer segurança extra e é gerenciado no centro de administração do Microsoft 365. O Office 365 oferece o seguinte subconjunto de recursos da autenticação multifator do Azure como parte da assinatura: 
  
- A capacidade de habilitar e aplicar a autenticação multifator para usuários finais
    
- O uso de um aplicativo móvel (on-line e OTP [senha avulsa]) como segundo fator de autenticação
    
- O uso de uma chamada telefônica como segundo fator de autenticação
    
- O uso de uma mensagem SMS como segundo fator de autenticação
    
- Senhas de aplicativo para clientes que não estão no navegador (por exemplo, o software de comunicação Microsoft Lync 2013)
    
- Saudações padrão da Microsoft durante as chamadas de autenticação
    
Para a lista completa de recursos adicionais, confira [a comparação das versões da autenticação multifator do Azure](https://go.microsoft.com/fwlink/?LinkId=506927). Você sempre pode obter a funcionalidade completa comprando o serviço Autenticação Multifator do Azure. 
  
Você recebe um subconjunto de recursos, dependendo se tem uma implantação somente na nuvem para o Office 365 ou um híbrido configurado com logon único e Serviços de Federação do Active Directory (AD FS). 
  
|**Onde você gerencia seu locatário do Office 365?**|**Opções do segundo fator da MFA**|
|:-----|:-----|
|Somente na nuvem  <br/> |MFA do Azure Active Directory (mensagem ou chamada telefônica)  <br/> |
|Configuração híbrida, gerenciada no local  <br/> | Se você gerencia identidades de usuário no local, tem as seguintes opções:  <br/>  Cartão inteligente físico ou virtual (AD FS)  <br/> [MFA do Azure](https://go.microsoft.com/fwlink/p/?LinkId=526677) (módulo para o AD FS)  <br/>  MFA do Azure AD  <br/> |
   
  
A figura a seguir mostra como os aplicativos de dispositivo do Office 2013 (no Windows) permitem aos usuários entrar com MFA. Os aplicativos de dispositivo do Office 2013 dão suporte à autenticação multifator com o uso da [ADAL (biblioteca de autenticação do Active Directory)](https://go.microsoft.com/fwlink/p/?LinkId=526684). O Azure AD hospeda uma página da Web onde os usuários podem entrar. O provedor de identidade pode ser o Azure AD ou um provedor de identidade federada, como o AD FS. A autenticação para usuários federados envolve as seguintes etapas:
  
1. O Azure AD redireciona o usuário para a página da Web de entrada hospedada pelo provedor de identidade do registro para o locatário do Office 365. O provedor de identidade é determinado pelo domínio especificado no nome de entrada do usuário.
    
2. O usuário entra na página de entrada da Web em seu dispositivo. 
    
3. O provedor de identidade retorna um token para o Azure AD quando o usuário é conectado com êxito.
    
4. O Azure AD retorna um JWT (token Web JSON) para o aplicativo de dispositivo do Office e o aplicativo de dispositivo é autenticado usando um JWT com o Office 365. 
    
Isso é detalhado na figura abaixo:
  
![Modern authentication for Office 2013 device apps.](../media/dc37645c-b899-4715-b162-d7653bd0aebd.png)
  
## <a name="software-requirements"></a>Requisitos de software

Para habilitar a MFA para aplicativos clientes do Office 2013, você deve ter o software a seguir instalado (a versão listada abaixo ou uma versão posterior) dependendo se tem uma [Instalações baseadas em clique para executar](#click-to-run-based-installations) ou uma [Instalações baseada em MSI](#msi-based-installations).
  
Para determinar se a instalação do Office é baseada em MSI ou clique para executar:
  
1. Inicie o Outlook 2013.
    
2. No menu **arquivo** , escolha **conta do Office**.
    
3. Para Outlook 2013 instalações de clique para executar, é exibido um item **Opções de Atualização**. Para instalações baseada em MSI, o item **Opções de Atualização** não é exibido. 
    
    ![Graphic that shows how to tell if Office 2013 install is click-to-run or MSI-based](../media/1e75143f-9e37-4e0c-9610-43a80771571e.png)
  
### <a name="click-to-run-based-installations"></a>Instalações baseadas em clique para executar

Para instalações baseadas em clique para executar, você deve ter o software a seguir instalado com a versão do arquivo listado abaixo ou uma versão posterior do arquivo. Se sua versão do arquivo não é igual ou superior à versão do arquivo listada, atualize-a usando as etapas abaixo.
  
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

Para habilitar a MFA, você deve concluir este procedimento:
  
1. Habilitar os clientes para autenticação moderna:
    
  - [Habilitar a Autenticação Moderna do Office 2013 em dispositivos Windows](enable-modern-authentication.md) . 
    
  - Configure o MFA do Azure com serviços de diretório de terceiros.
    
    Consulte os [cenários avançados com a autenticação multifator do Azure e soluções VPN de terceiros](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) para obter informações sobre provedores de identidade específicos aceitos para este programa. 
    
2. [Configurar a autenticação multifator para o Office 365](set-up-multi-factor-authentication.md)
    
3. Explicar aos usuários individuais como entrar usando MFA: [entrar no Office 365 com a verificação em duas etapas](https://support.office.com/article/2b856342-170a-438e-9a4f-3c092394d3cb.aspx).
    
> [!IMPORTANT]
> Se você habilitou seus usuários para o MFA do Azure AD e eles têm algum dispositivo executando o Office 2013 que não está habilitado para a Autenticação Moderna, precisará usar o AppPasswords nesses dispositivos. Mais informações sobre o AppPasswords e quando/onde/como elas devem ser usadas podem ser encontradas aqui: [AppPasswords com a autenticação multifator do Azure](https://go.microsoft.com/fwlink/p/?LinkId=528178). 
  
## <a name="faq"></a>Perguntas frequentes

[Perguntas Frequentes sobre o artigo do wiki de Autenticação Moderna](https://go.microsoft.com/fwlink/p/?LinkId=530064)
  
 **Problemas conhecidos:**
  
[Autenticação Moderna do Office 2013 e do Office 365 ProPlus: Como se preparar para a integração](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 **Solução de problemas da Autenticação Multifator do Azure:**
  
Confira [Solucionar problemas do MFA do Azure](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues).
  
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
   

