---
title: O Logon único Contínuo do Azure AD para o ambiente de teste do Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Resumo: configure e teste o Logon único Contínuo do Azure AD para o ambiente de teste do Microsoft 365.'
ms.openlocfilehash: 7fcbc82cfb35c598358c8160dd06427c2a9c59a2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904859"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a>O Logon único Contínuo do Azure AD para o ambiente de teste do Microsoft 365

*Este Guia de Laboratório de Teste pode ser usado para Microsoft 365 ambientes de teste corporativos e Office 365 Enterprise de teste.*

O Azure AD Seamless Single Sign-On (SSO contínuo) conecta automaticamente os usuários quando estão em seus PCs ou dispositivos conectados à rede da organização. O SSO Contínuo do Azure AD fornece aos usuários acesso fácil a aplicativos baseados em nuvem sem precisar de componentes locais adicionais.

Este artigo descreve como configurar seu ambiente de Microsoft 365 de teste para o SSO contínuo do Azure AD.

Configurar o SSO contínuo do Azure AD envolve duas fases:
- [Fase 1: configurar a sincronização de hash de senha do ambiente de teste do Microsoft 365](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [Fase 2: configure o Azure Active Directory Connect no APP1 para o SSO Contínuo do Azure Active Directory](#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso)
   
![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Para um mapa visual de todos os artigos na pilha Microsoft 365 guia do laboratório de teste empresarial, vá para o Microsoft 365 para a pilha de guias de laboratório [de teste corporativos.](../downloads/Microsoft365EnterpriseTLGStack.pdf)
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configurar a sincronização de hash de senha do ambiente de teste do Microsoft 365

Siga as instruções na [sincronização de hash de senha para Microsoft 365](password-hash-sync-m365-ent-test-environment.md). 

Sua configuração resultante tem esta aparência:
  
![Empresa simulada com ambiente de teste de sincronização de hash de senha](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Esta configuração consiste em:
  
- Uma assinatura de avaliação ou assinatura paga do Microsoft 365 E5.
- Uma intranet de organização simplificada conectada à Internet, que consiste nas máquinas virtuais DC1, APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure.
- O Azure AD Conexão é executado no APP1 para sincronizar periodicamente o domínio testlab active directory domain Services (AD DS) com o locatário do Azure AD de sua assinatura Microsoft 365.

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a>Fase 2: configure o Azure Active Directory Connect no APP1 para o SSO Contínuo do Azure Active Directory

Nesta fase, configure o Azure AD Conexão app1 para SSO contínuo do Azure AD e verifique se ele funciona.

### <a name="configure-azure-ad-connect-on-app1"></a>Configurar o Azure AD Connect no APP1

1. No [Portal do Azure](https://portal.azure.com), entre com a conta de administrador global e conecte-se ao APP1 com a conta TESTLAB\Usuário1.

2. Na área de trabalho APP1, execute o Azure AD Conexão.

3. Na página **Bem-vindo,** selecione **Configurar**.

4. Na página **Tarefas adicionais,** selecione **Alterar a login do** usuário e selecione **Próximo**.

5. Na página **Conexão para o Azure AD,** insira suas credenciais de conta de administrador global e selecione **Next**.

6. Na página **Login do** usuário, selecione Habilitar **logom único** e selecione **Próximo**.

7. Na página **Habilitar entrada** única, selecione **Inserir credenciais**.

8. Na caixa **Segurança do Windows** caixa de diálogo, insira **user1** e a senha da conta user1, selecione **OK** e selecione **Próximo**.

9. Na página **Pronto para Configurar,** selecione **Configurar**.

10. Na página **Configuração completa,** selecione **Sair**.

11. No portal do Azure, no painel esquerdo, selecione Azure Active Directory  >  **Azure AD Conexão**. Verifique se o **recurso de logom único** contínuo aparece como **Habilitado**.

Em seguida, teste a capacidade de entrar em sua assinatura com o <strong>user1@testlab.</strong>\<*your public domain*> nome de usuário da conta User1.

1. No Internet Explorer no APP1, selecione o ícone de configurações e selecione **Opções da Internet**.
 
2. Em **Opções da Internet,** selecione a **guia** Segurança.

3. Selecione **Intranet Local** e, em seguida, selecione **Sites**.

4. Na **intranet local,** selecione **Avançado**.

5. Em **Adicionar este site à zona**, insira **https <span>://</span>autologon.microsoftazuread-sso.com**, selecione Adicionar   >  **Fechar**  >  **OK**  >  **OK**.

6. Saia e entre novamente, mas desta vez especifique uma conta diferente.

7. Quando solicitado a entrar, especifique <strong>user1@testlab.</strong>\<*your public domain*> name e, em seguida, selecione **Next**. Você deve conseguir entrar como Usuário1 sem que uma senha seja solicitada. Isso prova que o SSO de conexão remota do Azure AD está funcionando.

Observe que, embora o Usuário1 tenha permissões de administrador de domínio para o domínio TESTLAB do AD DS, ele não é um administrador global do Azure AD. Portanto, o ícone **Administrador** não estará disponível como opção.

Esta é a configuração resultante:

![A empresa simulada com ambiente de teste de autenticação de passagem](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

Esta configuração consiste em:

- Uma Microsoft 365 E5 de avaliação ou assinaturas pagas com o testlab de domínio DNS.\<*your domain name*> registrado.
- Uma intranet de organização simplificada conectada à Internet, que consiste nas máquinas virtuais DC1, APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure.
- O Azure AD Connect é executado no APP1 para sincronizar a lista de contas e grupos do locatário do Azure AD da sua assinatura do Microsoft 365 para o domínio TESTLAB AD DS.
- O SSO Contínuo do Azure AD está habilitado para que os computadores na intranet simulada possam entrar Microsoft 365 recursos de nuvem sem especificar uma senha de conta de usuário.

## <a name="next-step"></a>Próxima etapa

Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.

## <a name="see-also"></a>Confira também

[Guias do Laboratório de Teste do Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Documentação do Microsoft 365 para empresas](/microsoft-365-enterprise/)