---
title: Write-back de senha do ambiente de teste do Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/20/2018
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
description: 'Resumo: configure o write-back de senha do ambiente de teste do Microsoft 365.'
ms.openlocfilehash: 748ccaf8601d9e9564d176f2368e3cc71f926208
ms.sourcegitcommit: 369f07db4e457334900314a2575f2f75cff5ce9c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/07/2018
ms.locfileid: "27201605"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a>Write-back de senha do ambiente de teste do Microsoft 365

O write-back de senha permite aos usuários atualizar as senhas pelo Azure Active Directory (AD), o que é então replicado para o Windows Server Active Directory (AD) local. Com o write-back de senha, os usuários não precisam atualizar senhas pelo Windows Server AD local, onde as contas de usuários originais são armazenadas. Isso ajuda os usuários móveis ou remotos que não têm uma conexão de acesso remoto à rede local.

Este artigo descreve como você pode configurar seu ambiente de teste do Microsoft 365 para o write-back de senha.

Há duas etapas para fazer a configuração:

1.  Criar o ambiente de teste de empresa simulada do Microsoft 365 com sincronização de hash de senha.
2.  Habilitar o write-back de senha para o domínio TESTLAB do Windows Server AD.
    
![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Clique [aqui](https://aka.ms/m365etlgstack) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configurar a sincronização de hash de senha do ambiente de teste do Microsoft 365

Siga as instruções em [sincronização de hash de senha para o Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Aqui está a configuração resultante.
  
![Empresa simulada com ambiente de teste de sincronização de hash de senha](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Esta configuração consiste em: 
  
- Assinaturas permanentes ou de avaliação do Office 365 E5 e EMS E5.
- Uma intranet de organização simplificada conectado à Internet, que consiste em máquinas virtuais DC1 APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure. 
- O Azure AD Connect é executado no APP1 para sincronizar o domínio TESTLAB do Windows Server AD com o locatário do Microsoft Azure AD das assinaturas do Office 365 e do EMS E5.

## <a name="phase-2-enable-password-writeback-for-the-testlab-windows-server-ad-domain"></a>Fase 2: habilitar o write-back de senha para o domínio TESTLAB do Windows Server AD

Primeiro, configure a conta de Usuário 1 com a função de administrador global.

1. No [portal do Office](https://office.com), entre com sua conta de administrador global.

2. Clique no bloco **Administração**. Na nova guia do navegador **Centro de administração do Microsoft 365**, clique em **Usuários ativos**.
 
3. Na página **Usuários ativos**, clique na conta **usuário1**,

4. No painel **usuário1**, clique em **Editar** ao lado de **Funções**.

5. No painel **Editar funções de usuário** de usuário1, clique em **Administrador global**. Clique em **Salvar** e depois em **Fechar**.

Configure a conta do Usuário 1 com as configurações de segurança que permitam alterar as senhas em nome de outros usuários no domínio TESTLAB do Windows Server AD.

1. No [Portal do Azure](https://portal.azure.com), entre com a conta de administrador global e conecte-se ao APP1 com a conta TESTLAB\Usuário1.

2.  Na área de trabalho do APP1, clique em **Iniciar**, digite **ativo** e clique em **Usuários e Computadores do Active Directory**.

3. Clique em **Modo de exibição** na barra de menus. Se **Recursos avançados** não estiver habilitado, clique nele para habilitá-lo.

4. No painel de árvore, clique com botão direito no seu domínio, clique em **Propriedades** e depois na guia **Segurança**.

5. Clique em **Avançado**.

6. Na guia **Permissões**, clique em **Adicionar**.

7. Clique em **Selecionar uma entidade de segurança**, digite **Usuário1** e clique em **OK**.

8. Em **Aplica-se a**, selecione **Objetos de usuário descendente**.

9. Em **Permissões**, selecione o seguinte:

    - Alterar senha
    - Redefinir senha

10. Em **Propriedades**, selecione o seguinte:
    - Gravar lockoutTime
    - Gravar pwdLastSet

11. Clique em **OK** três vezes para salvar as alterações.

12. Feche **Usuários e Computadores do Active Directory**.

Configure o Azure AD Connect em APP1 para write-back de senha.

1. Se necessário, conecte ao APP1 com a conta TESTLAB\Usuário1.

2. Na área de trabalho de APP1, clique duas vezes em **Azure AD Connect**.

3. Na **Página inicial**, clique em **Configurar**.

4. Na página **Tarefas adicionais**, clique em **Personalizar as opções de sincronização** e depois em **Avançar**.

5. Na página **Conectar-se ao Azure AD**, digite as credenciais de conta do Usuário 1 e clique em **Avançar**.

6. Nas páginas **Conectar os diretórios** e **Filtrar domínio/UO**, clique em **Avançar**.

7. Na página **Recursos opcionais**, selecione **Write-back de senha** e clique em Avançar. 

8. Na página **Pronto para configurar**, clique em **Configurar** e aguarde que o processo seja concluído.

9. Ao concluir a configuração, clique em **Sair**.

Agora você está pronto para testar o write-back de senha para os usuários em computadores que não estão conectados à rede virtual da sua intranet simulada.

Esta é a configuração resultante:

![A empresa simulada com ambiente de teste de autenticação de passagem](media/pass-through-auth-m365-ent-test-environment/Phase1.png)

Esta configuração consiste em:

- Assinaturas permanentes ou de avaliação do Office 365 E5 e EMS E5 com o domínio DNS TESTLAB.\<seu nome de domínio> registrado.
- Uma intranet de organização simplificada conectado à Internet, que consiste em máquinas virtuais DC1 APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure. 
- O Azure AD Connect é executado no APP1 para sincronizar a lista de contas e grupos do locatário do Azure AD de suas assinaturas do Azure AD das assinaturas do Office 365 e do EMS E5 para o domínio TESTLAB do Windows Server AD. 
- O write-back de senha está habilitado para que os usuários possam alterar as próprias senhas pelo Azure AD sem precisar se conectar à intranet simplificada.

Confira informações e links para configurar o write-back de senhas em produção na etapa [Simplificar a atualização de senhas](identity-password-writeback.md), na fase Identidade.

## <a name="next-step"></a>Próxima etapa

Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.

## <a name="see-also"></a>Confira também

[Guias do Laboratório de Teste do Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implantar o Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentação do Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)


