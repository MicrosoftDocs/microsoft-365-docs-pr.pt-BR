---
title: O Logon único Contínuo do Azure AD para o ambiente de teste do Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Resumo: configure e teste o Logon único Contínuo do Azure AD para o ambiente de teste do Microsoft 365.'
ms.openlocfilehash: 10444b094e09705e93cb32c10cd0d41c19913985
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865230"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a>O Logon único Contínuo do Azure AD para o ambiente de teste do Microsoft 365

O Logon Único (SSO) Contínuo do Azure AD dá acesso automático de usuários quando eles estão em seus computadores ou dispositivos conectados à rede da sua organização. O SSO Contínuo do Azure AD fornece aos usuários acesso fácil às aplicativos baseados na nuvem sem precisar de componentes locais adicionais.

Este artigo descreve como você pode configurar seu ambiente de teste do Microsoft 365 para o SSO Contínuo do Azure AD.

Há duas fases para configurar esse ambiente de teste:

1.  Criar o ambiente de teste de empresa simulada do Microsoft 365 com sincronização de hash de senha.
2.  Configure o Azure Active Directory Connect no APP1 para o SSO Contínuo do Azure Active Directory.
    
![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Clique [aqui](https://aka.ms/m365etlgstack) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.
  
## <a name="phase-1-create-the-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: Criar a sincronização de hash de senha do ambiente de teste do Microsoft 365

Siga as instruções em [sincronização de hash de senha para o Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Aqui está a configuração resultante.
  
![Empresa simulada com ambiente de teste de sincronização de hash de senha](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Esta configuração consiste em: 
  
- Assinaturas permanentes ou de avaliação do Office 365 E5 e EMS E5.
- Uma intranet de organização simplificada conectado à Internet, que consiste em máquinas virtuais DC1 APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure. 
- O Azure AD Connect é executado no APP1 para sincronizar periodicamente o domínio TESTLAB do Windows Server AD para o locatário do Azure AD das assinaturas do Office 365 e do EMS E5.

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a>Fase 2: configure o Azure Active Directory Connect no APP1 para o SSO Contínuo do Azure Active Directory

Nesta fase, você configura o Azure AD Connect no APP1 para SSO Contínuo do Azure AD e, em seguida, verifica se isso funciona.

### <a name="configure-azure-ad-connect-on-app1"></a>Configurar o Azure AD Connect no APP1

1. No [Portal do Azure](https://portal.azure.com), entre com a conta de administrador global e conecte-se ao APP1 com a conta TESTLAB\Usuário1.

2. Na área de trabalho do APP1, execute o Azure AD Connect.

3. Na página **Página inicial**, clique em **Configurar**.

4. Na página Tarefas adicionais, clique em **Alterar entrada do usuário** e em **Avançar**.

5. Na página **Conectar ao Azure AD**, digite suas credenciais de conta de administrador global e clique em **Próxima**.

6. Na página **Entrada do usuário**, selecione **Habilitar logon único** e clique em **Avançar**.

7. Na página **Habilitar o logon único**, clique em **Inserir credenciais**.

8. Na caixa de diálogo **Segurança do Windows**, digite **usuário1** e a senha da conta do Usuário1 e clique em **OK**. Clique em **Avançar**.

9. Na página **Pronto para Configurar**, clique em **Configurar**.

10. Na página **Configuração concluída**, clique em **Sair**.

11. No portal do Azure, no painel esquerdo, clique em **Azure Active Directory > Azure AD Connect Health**. Verifique se o recurso **Logon único Contínuo** aparece como **Habilitado**.

Em seguida, teste a capacidade de entrar na assinatura do Office 365 com a conta <strong>usuario1@testlab.</strong>\<seu domínio público>nome de usuário da conta Usuário1.

1. Do Internet Explorer para APP1, clique no ícone de configurações e, em seguida, clique em **Opções da Internet**.
 
2. Em **Opções da Internet**, clique na guia **Segurança**.

3. Clique em **Intranet local** e, em seguida, clique em **Sites**.

4. Na **Intranet Local**, clique em **Avançado**.

5. Em **Adicionar este site à zona**, digite **https<span>://</span>autologon.microsoftazuread-sso.com**, clique em **Adicionar > Fechar > OK > OK**.

6. Encerre o Office 365 e entre novamente, mas desta vez especifique uma conta diferente.

7. Quando for solicitado a entrar, especifique <strong>usuario1@testlab.</strong> \<seu domínio público > nome e, em seguida, clique em **Avançar**. Você deve entrar com êxito como Usuário1 sem precisar fornecer uma senha. Isso prova que o SSO Contínuo está funcionando.

Embora o Usuário1 tenha permissões de administrador de domínio para o domínio do Windows Server Active Directory do TestLab, ele não é um administrador global do Office 365. Portanto, o ícone **Administrador** não estará disponível como opção.

Esta é a configuração resultante:

![A empresa simulada com ambiente de teste de autenticação de passagem](media/pass-through-auth-m365-ent-test-environment/Phase1.png)

 
Esta configuração consiste em:

- Assinaturas permanentes ou de avaliação do Office 365 E5 e EMS E5 com o domínio DNS TESTLAB.\<seu nome de domínio> registrado.
- Uma intranet de organização simplificada conectado à Internet, que consiste em máquinas virtuais DC1 APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure. 
- O Azure AD Connect é executado no APP1 para sincronizar a lista de contas e grupos do locatário do Azure AD de suas assinaturas do Azure AD das assinaturas do Office 365 e do EMS E5 para o domínio TESTLAB do Windows Server AD. 
- O SSO Contínuo do Azure AD está habilitado para que os computadores na intranet simulada podem entrar para usar recursos de nuvem do Microsoft 365 sem especificar uma senha de conta de usuário.

Confira a etapa [Simplificar entrada do usuário](identity-single-sign-on.md) na fase de identidade para informações e links para configurar o Logon único Contínuo do Azure AD em produção.

## <a name="next-step"></a>Próxima etapa

Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.

## <a name="see-also"></a>Confira também

[Guias do Laboratório de Teste do Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implantar o Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentação do Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)


