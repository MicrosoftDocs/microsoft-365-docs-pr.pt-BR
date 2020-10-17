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
ms.openlocfilehash: f98f82de50feb2a9f92d1ecc4775c5307b314a72
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487595"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a>O Logon único Contínuo do Azure AD para o ambiente de teste do Microsoft 365

*Este guia de laboratório de teste pode ser usado para ambientes de teste corporativos do Microsoft 365 para Enterprise e Office 365.*

O Sign-On único do Azure Active Directory (SSO sem problemas) entra automaticamente nos usuários quando eles estão em seus computadores ou dispositivos conectados à rede da organização. O SSO direto do Azure AD fornece aos usuários acesso fácil aos aplicativos baseados na nuvem sem precisar de nenhum componente adicional no local.

Este artigo descreve como configurar seu ambiente de teste do Microsoft 365 para SSO direto do Azure AD.

Configurar o SSO contínuo do Azure AD envolve duas fases:
- [Fase 1: configurar a sincronização de hash de senha do ambiente de teste do Microsoft 365](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [Fase 2: configure o Azure Active Directory Connect no APP1 para o SSO Contínuo do Azure Active Directory](#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso)
   
![Guias de laboratório de teste da Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Para obter um mapa Visual para todos os artigos da pilha do guia do laboratório de teste do Microsoft 365 for Enterprise, vá para a [pilha do guia do laboratório de teste da microsoft 365 para empresas](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configurar a sincronização de hash de senha do ambiente de teste do Microsoft 365

Siga as instruções em [sincronização de hash de senha para o Microsoft 365](password-hash-sync-m365-ent-test-environment.md). 

A configuração resultante tem a seguinte aparência:
  
![Empresa simulada com ambiente de teste de sincronização de hash de senha](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Esta configuração consiste em:
  
- Uma assinatura de avaliação ou assinatura paga do Microsoft 365 E5.
- Uma intranet de organização simplificada conectada à Internet, consistindo nas máquinas virtuais DC1, APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure.
- O Azure AD Connect é executado no APP1 para sincronizar periodicamente o domínio do AD DS (serviços de domínio Active Directory) do TESTLAB para o locatário do Azure AD da sua assinatura do Microsoft 365.

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a>Fase 2: configure o Azure Active Directory Connect no APP1 para o SSO Contínuo do Azure Active Directory

Nesta fase, configure o Azure AD Connect no APP1 para o SSO contínuo do Azure AD e, em seguida, verifique se ele funciona.

### <a name="configure-azure-ad-connect-on-app1"></a>Configurar o Azure AD Connect no APP1

1. No [Portal do Azure](https://portal.azure.com), entre com a conta de administrador global e conecte-se ao APP1 com a conta TESTLAB\Usuário1.

2. Na área de trabalho do APP1, execute o Azure AD Connect.

3. Na **página de boas-vindas**, selecione **Configurar**.

4. Na página **tarefas adicionais** , selecione **alterar entrada do usuário**e, em seguida, selecione **Avançar**.

5. Na página **conectar ao Azure ad** , insira as credenciais de sua conta de administrador global e selecione **Avançar**.

6. Na página **entrada do usuário** , selecione **habilitar logon único**e, em seguida, selecione **Avançar**.

7. Na página **habilitar logon único** , selecione **Inserir credenciais**.

8. Na caixa de diálogo **segurança do Windows** , digite **Usuário1** e a senha da conta Usuário1, selecione **OK**e, em seguida, selecione **Avançar**.

9. Na página **pronto para configurar** , selecione **Configurar**.

10. Na página **configuração concluída** , selecione **sair**.

11. No portal do Azure, no painel esquerdo, selecione **Azure Active Directory**  >  **Azure ad Connect**. Verifique se o recurso de **logon único contínuo** aparece como **habilitado**.

Em seguida, teste a capacidade de entrar em sua assinatura com o <strong>user1@testlab.</strong>\<*your public domain*> nome de usuário da conta User1.

1. No Internet Explorer no APP1, selecione o ícone configurações e, em seguida, selecione **Opções da Internet**.
 
2. Em **Opções da Internet**, selecione a guia **segurança** .

3. Selecione **intranet local**e, em seguida, selecione **sites**.

4. Em **intranet local**, selecione **avançado**.

5. Em **Adicionar este site à zona**, digite **https<span>://</span>AutoLogon.microsoftazuread-SSO.com**, selecione **Adicionar**  >  **fechar**  >  **OK**  >  **OK**.

6. Saia e entre novamente, mas desta vez especifique uma conta diferente.

7. Quando solicitado a entrar, especifique <strong>user1@testlab.</strong>\<*your public domain*> nome e, em seguida, selecione **Avançar**. Você deve conseguir entrar como Usuário1 sem que uma senha seja solicitada. Isso prova que o SSO de conexão remota do Azure AD está funcionando.

Observe que, embora o Usuário1 tenha permissões de administrador de domínio para o domínio TESTLAB do AD DS, ele não é um administrador global do Azure AD. Portanto, o ícone **Administrador** não estará disponível como opção.

Esta é a configuração resultante:

![A empresa simulada com ambiente de teste de autenticação de passagem](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

Esta configuração consiste em:

- Uma assinatura paga ou de avaliação do Microsoft 365 E5 com o domínio DNS testlab.\<*your domain name*> registrado.
- Uma intranet de organização simplificada conectada à Internet, consistindo nas máquinas virtuais DC1, APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure.
- O Azure AD Connect é executado no APP1 para sincronizar a lista de contas e grupos do locatário do Azure AD da sua assinatura do Microsoft 365 para o domínio TESTLAB AD DS.
- O SSO direto do Azure Active Directory está habilitado para que os computadores na intranet simulada possam entrar no Microsoft 365 Cloud Resources sem especificar uma senha de conta de usuário.

## <a name="next-step"></a>Próxima etapa

Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.

## <a name="see-also"></a>Confira também

[Guias do Laboratório de Teste do Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Documentação da Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365-enterprise/)
