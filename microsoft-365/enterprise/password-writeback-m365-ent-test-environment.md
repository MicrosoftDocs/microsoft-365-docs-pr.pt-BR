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
ms.openlocfilehash: f1118c22ad1f65ea29bb14afacb7506a60d1fe1a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921475"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a>Write-back de senha do ambiente de teste do Microsoft 365

*Este Guia de Laboratório de Teste só pode ser usado para Microsoft 365 ambientes de teste corporativos.*

Os usuários podem usar o writeback de senha para atualizar suas senhas por meio do Azure Active Directory (Azure AD), que é replicado para os Serviços de Domínio local do Active Directory (AD DS). Com o writeback de senha, os usuários não têm que atualizar suas senhas por meio do AD DS local onde suas contas de usuário originais são armazenadas. Isso ajuda usuários de roaming ou remotos que não têm uma conexão de acesso remoto à rede local.

Este artigo descreve como configurar seu ambiente de teste Microsoft 365 para writeback de senha.

Configurar seu ambiente de teste para writeback de senha envolve duas fases:
- [Fase 1: configurar a sincronização de hash de senha do ambiente de teste do Microsoft 365](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [Fase 2: Habilitar o write-back de senha para o domínio TESTLAB AD DS](#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)
  
![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Para um mapa visual de todos os artigos na pilha Microsoft 365 guia do laboratório de teste empresarial, vá para o Microsoft 365 para a pilha de guias de laboratório [de teste corporativos.](../downloads/Microsoft365EnterpriseTLGStack.pdf)

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configurar a sincronização de hash de senha do ambiente de teste do Microsoft 365

Primeiro, siga as instruções na [sincronização de hash de senha](password-hash-sync-m365-ent-test-environment.md). Sua configuração resultante tem esta aparência:
  
![Empresa simulada com ambiente de teste de sincronização de hash de senha](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Esta configuração consiste em:
  
- Uma assinatura de avaliação ou assinatura paga do Microsoft 365 E5.
- Uma intranet de organização simplificada conectada à Internet, que consiste nas máquinas virtuais DC1, APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure.
- O Azure AD Connect é executado no APP1 para sincronizar o domínio TESTLAB AD DS com o locatário do Azure AD da sua assinatura do Microsoft 365.

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a>Fase 2: Habilitar o write-back de senha para o domínio TESTLAB AD DS

Primeiro, configure a conta de Usuário 1 com a função de administrador global.

1. No [centro de administração do Microsoft 365](https://portal.microsoft.com), entre com sua conta de administrador global.

2. Selecione **Usuários ativos**.
 
3. Na página **Usuários ativos,** selecione a **conta user1,**

4. No painel **user1,** selecione **Editar** ao lado de **Funções**.

5. No painel **Editar funções de usuário** para usuário1, selecione Administrador **global**, selecione **Salvar** e, em seguida, selecione **Fechar**.

Em seguida, configure a conta de Usuário 1 com as configurações de segurança que permitem a alteração de senhas em nome do domínio de outros usuários do TESTLAB AD DS.

1. No [Portal do Azure](https://portal.azure.com), entre com a conta de administrador global e conecte-se ao APP1 com a conta TESTLAB\Usuário1.

2. Na área de trabalho do APP1, selecione **Iniciar**, insira **ativo** e selecione **Usuários e Computadores do Active Directory.**

3. Na barra de menus, selecione **Exibir**. Se **os recursos avançados** não estão habilitados, selecione-o para habilita-lo.

4. No painel de árvore, selecione e segure (ou clique com o botão direito do mouse) no domínio, selecione **Propriedades** e selecione a **guia** Segurança.

5. Selecione **Avançado**.

6. Na guia **Permissões,** selecione **Adicionar**.

7. Selecione **Selecionar uma entidade principal,** insira **User1** e selecione **OK**.

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

3. Na página **Bem-vindo,** selecione **Configurar**.

4. Na página **Tarefas adicionais,** selecione **Personalizar opções de** sincronização e selecione **Próximo**.

5. Na página **Conexão para o Azure AD,** insira suas credenciais de conta de administrador global e selecione **Next**.

6. Nos **diretórios Conexão e** páginas de filtragem **domínio/UO,** selecione **Próximo**.

7. Na página **Recursos opcionais,** selecione **Writeback de senha** e selecione **Next**.

8. Na página **Pronto para configurar,** selecione **Configurar** e aguarde o final do processo.

9. Quando você vir a configuração terminar, selecione **Sair**.

Agora você está pronto para testar o writeback de senha para usuários em computadores que não estão conectados à rede virtual da intranet simulada.

Sua configuração resultante tem esta aparência:

![A empresa simulada com ambiente de teste de autenticação de passagem](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

Esta configuração consiste em:

- Uma Microsoft 365 E5 de avaliação ou assinaturas pagas com o domínio DNS TESTLAB.\<*your domain name*> registrado.
- Uma intranet de organização simplificada conectada à Internet, que consiste nas máquinas virtuais DC1, APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure.
- O Azure AD Connect é executado no APP1 para sincronizar a lista de contas e grupos do locatário do Azure AD da sua assinatura do Microsoft 365 no domínio TESTLAB AD DS.
- O write-back de senha está habilitado para que os usuários possam alterar as próprias senhas pelo Azure AD sem precisar se conectar à intranet simplificada.

## <a name="next-step"></a>Próxima etapa

Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.

## <a name="see-also"></a>Confira também

[Guias do Laboratório de Teste do Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Documentação do Microsoft 365 para empresas](/microsoft-365-enterprise/)