---
title: Write-back de senha do ambiente de teste do Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/22/2019
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
description: 'Resumo: configure o write-back de senha do ambiente de teste do Microsoft 365.'
ms.openlocfilehash: b999d50b0e98b11638199327bd7ffe7269b261ce
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487123"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a>Write-back de senha do ambiente de teste do Microsoft 365

*Este guia de laboratório de teste só pode ser usado para o Microsoft 365 para ambientes de teste corporativos.*

Os usuários podem usar o Write-back de senha para atualizar suas senhas por meio do Azure Active Directory (Azure AD), que é replicado para os serviços de domínio do Active Directory (AD DS) locais. Com o Write-back de senha, os usuários não precisam atualizar suas senhas através do AD DS local onde suas contas de usuário originais são armazenadas. Isso ajuda os usuários móveis ou remotos que não têm uma conexão de acesso remoto à sua rede local.

Este artigo descreve como configurar seu ambiente de teste do Microsoft 365 para o Write-back de senha.

Configurar seu ambiente de teste para Write-back de senha envolve duas fases:
- [Fase 1: configurar a sincronização de hash de senha do ambiente de teste do Microsoft 365](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [Fase 2: Habilitar o write-back de senha para o domínio TESTLAB AD DS](#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)
  
![Guias de laboratório de teste da Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Para obter um mapa Visual para todos os artigos da pilha do guia do laboratório de teste do Microsoft 365 for Enterprise, vá para a [pilha do guia do laboratório de teste da microsoft 365 para empresas](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configurar a sincronização de hash de senha do ambiente de teste do Microsoft 365

Primeiro, siga as instruções em [sincronização de hash de senha](password-hash-sync-m365-ent-test-environment.md). A configuração resultante tem a seguinte aparência:
  
![Empresa simulada com ambiente de teste de sincronização de hash de senha](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Esta configuração consiste em:
  
- Uma assinatura de avaliação ou assinatura paga do Microsoft 365 E5.
- Uma intranet de organização simplificada conectada à Internet, consistindo nas máquinas virtuais DC1, APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure.
- O Azure AD Connect é executado no APP1 para sincronizar o domínio TESTLAB AD DS com o locatário do Azure AD da sua assinatura do Microsoft 365.

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a>Fase 2: Habilitar o write-back de senha para o domínio TESTLAB AD DS

Primeiro, configure a conta de Usuário 1 com a função de administrador global.

1. No [centro de administração do Microsoft 365](https://portal.microsoft.com), entre com sua conta de administrador global.

2. Selecione **usuários ativos**.
 
3. Na página **usuários ativos** , selecione a conta **Usuário1**

4. No painel **Usuário1** , selecione **Editar** ao lado de **funções**.

5. No painel **Editar funções de usuário** para Usuário1, selecione **administrador global**, selecione **salvar**e, em seguida, selecione **fechar**.

Em seguida, configure a conta de Usuário 1 com as configurações de segurança que permitem a alteração de senhas em nome do domínio de outros usuários do TESTLAB AD DS.

1. No [Portal do Azure](https://portal.azure.com), entre com a conta de administrador global e conecte-se ao APP1 com a conta TESTLAB\Usuário1.

2. Na área de trabalho do APP1, selecione **Iniciar**, digite **ativo**e, em seguida, selecione **usuários e computadores do Active Directory**.

3. Na barra de menus, selecione **Exibir**. Se **recursos avançados** não estiverem habilitados, selecione-o para habilitá-lo.

4. No painel de árvore, selecione e segure (ou clique com o botão direito do mouse) seu domínio, selecione **Propriedades**e, em seguida, selecione a guia **segurança** .

5. Selecione **Avançado**.

6. Na guia **permissões** , selecione **Adicionar**.

7. Selecione **selecionar uma entidade de segurança**, digite **Usuário1**e, em seguida, selecione **OK**.

8. Em **Aplica-se a**, selecione **Objetos de usuário descendente**.

9. Em **Permissões**, selecione o seguinte:

    - **Alterar senha**
    - **Redefinir senha**

10. Em **Propriedades**, selecione o seguinte:
    - **Gravar lockoutTime**
    - **Gravar pwdLastSet**

11. Selecione **OK** três vezes para salvar as alterações.

12. Feche **Usuários e Computadores do Active Directory**.

Configure o Azure AD Connect em APP1 para write-back de senha.

1. Se necessário, conecte ao APP1 com a conta TESTLAB\Usuário1.

2. Na área de trabalho de APP1, clique duas vezes em **Azure AD Connect**.

3. Na **página de boas-vindas**, selecione **Configurar**.

4. Na página **tarefas adicionais** , selecione **Personalizar opções de sincronização**e, em seguida, selecione **Avançar**.

5. Na página **conectar ao Azure ad** , insira as credenciais de sua conta de administrador global e selecione **Avançar**.

6. Na página **conectar diretórios** e **filtros de domínio/ou** , selecione **Avançar**.

7. Na página **recursos opcionais** , selecione **write-back de senha**e, em seguida, selecione **Avançar**.

8. Na página **pronto para configurar** , selecione **Configurar** e aguarde até que o processo seja concluído.

9. Ao ver o término da configuração, selecione **sair**.

Agora você está pronto para testar o Write-back de senha para usuários em computadores que não estão conectados à rede virtual da sua intranet simulada.

A configuração resultante tem a seguinte aparência:

![A empresa simulada com ambiente de teste de autenticação de passagem](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

Esta configuração consiste em:

- Uma assinatura paga ou de avaliação do Microsoft 365 E5 com o domínio DNS TESTLAB.\<*your domain name*> registrado.
- Uma intranet de organização simplificada conectada à Internet, consistindo nas máquinas virtuais DC1, APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure.
- O Azure AD Connect é executado no APP1 para sincronizar a lista de contas e grupos do locatário do Azure AD da sua assinatura do Microsoft 365 no domínio TESTLAB AD DS.
- O write-back de senha está habilitado para que os usuários possam alterar as próprias senhas pelo Azure AD sem precisar se conectar à intranet simplificada.

## <a name="next-step"></a>Próxima etapa

Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.

## <a name="see-also"></a>Confira também

[Guias do Laboratório de Teste do Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Documentação da Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365-enterprise/)


