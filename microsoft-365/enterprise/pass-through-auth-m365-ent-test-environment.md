---
title: Autenticação de passagem para seu ambiente de teste do Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/13/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: ''
description: 'Resumo: configure a autenticação de passagem para seu ambiente de teste do Microsoft 365.'
ms.openlocfilehash: 98e0ad4b216fdc3940c0077cb308d6271ffed678
ms.sourcegitcommit: 7ae0389cf06e2f481ee646556720ab3f3e93ea32
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2019
ms.locfileid: "38757718"
---
# <a name="pass-through-authentication-for-your-microsoft-365-test-environment"></a>Autenticação de passagem para seu ambiente de teste do Microsoft 365

*Este Guia de Laboratório de Testes pode ser usado para ambientes de teste corporativo do Microsoft 365 Enterprise e do Office 365.*

As organizações que desejem usar diretamente a própria infraestrutura do Active Directory Domain Services (AD DS) local para a autenticação em serviços e aplicativos baseados na nuvem da Microsoft podem usar a autenticação de passagem. Este artigo descreve como configurar seu ambiente de teste do Microsoft 365 para autenticação de passagem, resultando na seguinte configuração:
  
![A empresa simulada com ambiente de teste de autenticação de passagem](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
Há duas fases para configurar esse ambiente de teste:

1.  Criar o ambiente de teste de empresa simulada do Microsoft 365 com sincronização de hash de senha.
2.  Configurar o Azure AD Connect no APP1 para autenticação de passagem.
    
![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Clique [aqui](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configurar a sincronização de hash de senha do ambiente de teste do Microsoft 365

Siga as instruções em [sincronização de hash de senha para o Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Aqui está a configuração resultante.
  
![Empresa simulada com ambiente de teste de sincronização de hash de senha](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Esta configuração consiste em: 
  
- Assinatura de avaliação ou assinatura paga do Microsoft 365 E5 ou Office 365 E5.
- Uma intranet de organização simplificada conectado à Internet, que consiste em máquinas virtuais do DC1 APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure. O Azure AD Connect é executado periodicamente no APP1 para sincronizar o domínio TESTLAB do AD DS com o locatário do Azure AD de sua assinatura do Microsoft 365 ou Office 365.

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-pass-through-authentication"></a>Fase 2: configurar o Azure AD Connect no APP1 para autenticação de passagem

Nesta fase, você configura o Azure AD Connect no APP1 para usar autenticação de passagem e verifica se ela funciona.

### <a name="configure-azure-ad-connect-on-app1"></a>Configurar o Azure AD Connect no APP1

1.  No [Portal do Azure](https://portal.azure.com), entre com a conta de administrador global e conecte-se ao APP1 com a conta TESTLAB\Usuário1.

2.  Na área de trabalho do APP1, execute o Azure AD Connect.

3.  Na **Página inicial**, clique em **Configurar**.

4.  Na página Tarefas adicionais, clique em **Alterar entrada do usuário** e em **Avançar**.

5.  Na página **Conectar ao Azure AD**, digite suas credenciais de conta de administrador global e clique em **Próxima**.

6.  Na página **Entrada de usuário**, clique em **Autenticação de passagem**e clique em **Avançar**.

7.  Na página **Pronto para configurar**, clique em **Configurar**.

8.  Na página **Configuração concluída**, clique em **Sair**.

9.  No portal do Azure, no painel esquerdo, clique em **Azure Active Directory > Azure AD Connect Health**. Verifique se o recurso **Autenticação de passagem** aparece como **Habilitado**.

10. Clique em **Autenticação de passagem**. O painel **Autenticação de passagem** lista os servidores onde estão instalados os Agentes de Autenticação. Você verá APP1 na lista. Feche o painel **Autenticação de passagem**.

Em seguida, teste a capacidade de entrar na assinatura do Office 365 com a conta <strong>usuario1@testlab.</strong>\<seu domínio público>nome de usuário da conta Usuário1.

1. No APP1, encerre o Office 365 e entre novamente, mas desta vez especifique uma conta diferente.

2. Quando solicitado a fornecer o nome de usuário e a senha, especifique <strong>usuario1@testlab.</strong>\<seu domínio público> e a senha de Usuario1. Você deve conseguir entrar como Usuario1.

Observe que, embora o Usuario1 tenha permissões de administrador de domínio para o domínio TESTLAB do AD DS, ele não é um administrador global do Office 365. Portanto, o ícone **Administrador** não estará disponível como opção.

Esta é a configuração resultante:

![A empresa simulada com ambiente de teste de autenticação de passagem](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
Esta configuração consiste em:

- Assinaturas pagas ou de avaliação do Microsoft 365 E5 ou do Office 365 E5 com o domínio DNS testlab.\<seu nome de domínio> registrado.
- Uma intranet de organização simplificada conectada à Internet, composta pelas máquinas virtuais DC1, APP1 e CLIENT1, em uma sub-rede de uma Rede Virtual do Microsoft Azure. Um Agente de Autenticação é executado no APP1 para processar as solicitações de autenticação de passagem do locatário do Azure AD nas assinaturas do Microsoft 365 ou do Office 365. 

## <a name="next-step"></a>Próxima etapa

Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.

## <a name="see-also"></a>Confira também

[Guias do Laboratório de Teste do Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implantar o Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentação do Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)


