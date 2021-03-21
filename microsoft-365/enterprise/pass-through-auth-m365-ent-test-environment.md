---
title: Autenticação de passagem para seu ambiente de teste do Microsoft 365
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
- TLG
- Ent_TLGs
ms.assetid: ''
description: 'Resumo: configure a autenticação de passagem para seu ambiente de teste do Microsoft 365.'
ms.openlocfilehash: cdbb6927fb8ca0001e3089c7169ce9046208e8f8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921523"
---
# <a name="pass-through-authentication-for-your-microsoft-365-test-environment"></a>Autenticação de passagem para seu ambiente de teste do Microsoft 365

*Este Guia de Laboratório de Teste pode ser usado para ambientes de teste do Microsoft 365 para empresas e office 365 Enterprise.*

As organizações que desejem usar diretamente a própria infraestrutura do Active Directory Domain Services (AD DS) local para a autenticação em serviços e aplicativos baseados na nuvem da Microsoft podem usar a autenticação de passagem. Este artigo descreve como configurar seu ambiente de teste do Microsoft 365 para autenticação de passagem, resultando na seguinte configuração:
  
![A empresa simulada com ambiente de teste de autenticação de passagem](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
Há duas fases para configurar esse ambiente de teste:

1.    Criar o ambiente de teste de empresa simulada do Microsoft 365 com sincronização de hash de senha.
2.    Configurar o Azure AD Connect no APP1 para autenticação de passagem.
    
![Guias de laboratório de teste da Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Clique [aqui](../downloads/Microsoft365EnterpriseTLGStack.pdf) para ver um mapa visual de todos os artigos na pilha do Guia de Laboratório de Teste do Microsoft 365 para empresas.
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configurar a sincronização de hash de senha do ambiente de teste do Microsoft 365

Siga as instruções em [sincronização de hash de senha para o Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Aqui está a configuração resultante.
  
![Empresa simulada com ambiente de teste de sincronização de hash de senha](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Esta configuração consiste em: 
  
- Avaliação ou assinatura paga do Microsoft 365 E5.
- Uma intranet de organização simplificada conectado à Internet, que consiste em máquinas virtuais do DC1 APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure. O Azure AD Connect é executado no APP1 para sincronizar o domínio TESTLAB AD DS com o locatário do Azure AD das suas assinaturas do Microsoft 365 periodicamente.

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-pass-through-authentication"></a>Fase 2: configurar o Azure AD Connect no APP1 para autenticação de passagem

Nesta fase, você configura o Azure AD Connect no APP1 para usar autenticação de passagem e verifica se ela funciona.

### <a name="configure-azure-ad-connect-on-app1"></a>Configurar o Azure AD Connect no APP1

1.    No [Portal do Azure](https://portal.azure.com), entre com a conta de administrador global e conecte-se ao APP1 com a conta TESTLAB\Usuário1.

2.    Na área de trabalho do APP1, execute o Azure AD Connect.

3.    Na **Página inicial**, clique em **Configurar**.

4.    Na página Tarefas adicionais, clique em **Alterar entrada do usuário** e em **Avançar**.

5.    Na página **Conectar ao Azure AD**, digite suas credenciais de conta de administrador global e clique em **Próxima**.

6.    Na página **Entrada de usuário**, clique em **Autenticação de passagem** e clique em **Avançar**.

7.    Na página **Pronto para configurar**, clique em **Configurar**.

8.    Na página **Configuração concluída**, clique em **Sair**.

9.    No portal do Azure, no painel esquerdo, clique em **Azure Active Directory > Azure AD Connect Health**. Verifique se o recurso **Autenticação de passagem** aparece como **Habilitado**.

10.    Clique em **Autenticação de passagem**. O painel **Autenticação de passagem** lista os servidores onde estão instalados os Agentes de Autenticação. Você verá APP1 na lista. Feche o painel **Autenticação de passagem**.

Em seguida, teste a capacidade de entrar em sua assinatura com o <strong>user1@testlab.</strong>\<your public domain> nome de usuário da conta User1.

1. Na APP1, saia e entre novamente, mas desta vez especifique uma conta diferente.

2. Quando for pedido um nome de usuário e senha, especifique <strong>user1@testlab.</strong>\<your public domain> e a senha do User1. Você deve conseguir entrar como Usuario1.

Observe que, embora o Usuário1 tenha permissões de administrador de domínio para o domínio TESTLAB do AD DS, ele não é um administrador global. Portanto, o ícone **Administrador** não estará disponível como opção.

Esta é a configuração resultante:

![A empresa simulada com ambiente de teste de autenticação de passagem](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
Esta configuração consiste em:

- Uma avaliação do Microsoft 365 E5 ou assinaturas pagas com o testlab de domínio DNS.\<your domain name> registrado.
- Uma intranet simplificada da organização conectada à Internet, consistindo nas máquinas virtuais DC1, APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure. Um Agente de autenticação é executado no APP1 para lidar com solicitações de autenticação de passagem do locatário do Azure AD da sua assinatura do Microsoft 365.

## <a name="next-step"></a>Próxima etapa

Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.

## <a name="see-also"></a>Confira também

[Guias do Laboratório de Teste do Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Documentação do Microsoft 365 para empresas](/microsoft-365-enterprise/)