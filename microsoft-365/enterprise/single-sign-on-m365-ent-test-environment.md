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
ms.openlocfilehash: 3ba229a62f66cad715f604bab91cd12032da7be8
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685767"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a>O Logon único Contínuo do Azure AD para o ambiente de teste do Microsoft 365

*Este guia de laboratório de teste pode ser usado para ambientes de teste corporativos do Microsoft 365 para Enterprise e Office 365.*

O Logon Único (SSO) Contínuo do Azure AD dá acesso automático de usuários quando eles estão em seus computadores ou dispositivos conectados à rede da sua organização. O SSO Contínuo do Azure AD fornece aos usuários acesso fácil às aplicativos baseados na nuvem sem precisar de componentes locais adicionais.

Este artigo descreve como você pode configurar seu ambiente de teste do Microsoft 365 para o SSO Contínuo do Azure AD.

Há duas etapas para fazer a configuração:

1.    Criar o ambiente de teste de empresa simulada do Microsoft 365 com sincronização de hash de senha.
2.    Configurar o Azure Active Directory Connect no APP1 para o SSO Contínuo do Azure Active Directory.
    
![Guias de laboratório de teste da Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Clique [aqui](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver um mapa visual de todos os artigos na pilha do Guia de Laboratório de Teste do Microsoft 365 para empresas.
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configurar a sincronização de hash de senha do ambiente de teste do Microsoft 365

Siga as instruções em [sincronização de hash de senha para o Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Aqui está a configuração resultante.
  
![Empresa simulada com ambiente de teste de sincronização de hash de senha](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Esta configuração consiste em: 
  
- Uma assinatura de avaliação ou assinatura paga do Microsoft 365 E5.
- Uma intranet de organização simplificada conectado à Internet, que consiste em máquinas virtuais do DC1 APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure. 
- O Azure AD Connect é executado no APP1 para sincronizar o domínio dos Serviços de domínio Active Directory (AD DS) do TESTLAB com o locatário do Azure AD da sua assinatura do Microsoft 365 periodicamente.

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a>Fase 2: configure o Azure Active Directory Connect no APP1 para o SSO Contínuo do Azure Active Directory

Nesta fase, você configura o Azure AD Connect no APP1 para SSO Contínuo do Azure AD e, em seguida, verifica se isso funciona.

### <a name="configure-azure-ad-connect-on-app1"></a>Configurar o Azure AD Connect no APP1

1. No [Portal do Azure](https://portal.azure.com), entre com a conta de administrador global e conecte-se ao APP1 com a conta TESTLAB\Usuário1.

2. Na área de trabalho do APP1, execute o Azure AD Connect.

3. Na **Página inicial**, clique em **Configurar**.

4. Na página **Tarefas Adicionais**, clique em **Alterar entrada do usuário** e em **Avançar**.

5. Na página **Conectar ao Azure AD**, digite suas credenciais de conta de administrador global e clique em **Próxima**.

6. Na página **Entrada do usuário**, selecione **Habilitar logon único** e clique em **Avançar**.

7. Na página **Habilitar o logon único**, clique em **Inserir credenciais**.

8. Na caixa de diálogo **Segurança do Windows**, digite **usuário1** e a senha da conta do Usuário1 e clique em **OK**. Clique em **Avançar**.

9. Na página **Pronto para Configurar**, clique em **Configurar**.

10. Na página **Configuração concluída**, clique em **Sair**.

11. No portal do Azure, no painel esquerdo, clique em **Azure Active Directory > Azure AD Connect Health**. Verifique se o recurso **Logon único Contínuo** aparece como **Habilitado**.

Em seguida, teste a capacidade de entrar em sua assinatura com o <strong>user1@testlab.</strong>\<your public domain> nome de usuário da conta User1.

1. Do Internet Explorer para APP1, clique no ícone de configurações e, em seguida, clique em **Opções da Internet**.
 
2. Em **Opções da Internet**, clique na guia **Segurança**.

3. Clique em **Intranet local** e, em seguida, clique em **Sites**.

4. Na **Intranet Local**, clique em **Avançado**.

5. Em **Adicionar este site à zona**, digite **https<span>://</span>autologon.microsoftazuread-sso.com**, clique em **Adicionar > Fechar > OK > OK**.

6. Saia e entre novamente, mas desta vez especifique uma conta diferente.

7. Quando solicitado a entrar, especifique <strong>user1@testlab.</strong>\<your public domain> nome e clique em **Avançar**. Você deve conseguir entrar como Usuário1 sem que uma senha seja solicitada. Isso prova que o SSO de conexão remota do Azure AD está funcionando.

Observe que, embora o Usuário1 tenha permissões de administrador de domínio para o domínio TESTLAB do AD DS, ele não é um administrador global do Azure AD. Portanto, o ícone **Administrador** não estará disponível como opção.

Esta é a configuração resultante:

![A empresa simulada com ambiente de teste de autenticação de passagem](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

 
Esta configuração consiste em:

- Uma assinatura paga ou de avaliação do Microsoft 365 E5 com o domínio DNS testlab.\<your domain name> registrado.
- Uma intranet de organização simplificada conectado à Internet, que consiste em máquinas virtuais do DC1 APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure. 
- O Azure AD Connect é executado no APP1 para sincronizar a lista de contas e grupos do locatário do Azure AD da sua assinatura do Microsoft 365 para o domínio TESTLAB AD DS. 
- O SSO Contínuo do Azure AD está habilitado para que os computadores na intranet simulada possam entrar para usar recursos de nuvem do Microsoft 365 sem especificar uma senha de conta de usuário.

## <a name="next-step"></a>Próxima etapa

Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.

## <a name="see-also"></a>Confira também

[Guias do Laboratório de Teste do Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Documentação da Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365-enterprise/)


