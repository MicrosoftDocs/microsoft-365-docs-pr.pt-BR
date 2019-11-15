---
title: Redefinição de senha do ambiente de teste do Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Resumo: configurar e testar a redefinição de senha do ambiente de teste do Microsoft 365.'
ms.openlocfilehash: 4ddcb0718fbb5546a0e37b648b698b46d7e55ec0
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2019
ms.locfileid: "38640720"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a>Redefinição de senha do ambiente de teste do Microsoft 365

A redefinição de senha de autoatendimento (SSPR) do Azure Active Directory (Azure AD) permite que os usuários redefinam ou desbloqueiem suas senhas ou contas. 

Este artigo descreve como você pode configurar e testar redefinições de senha em seu ambiente de teste do Microsoft 365 em três fases:

1.  Criar o ambiente de teste do Microsoft 365 Enterprise.
2.  Ativar write-back de senha.
3.  Configurar e testar a redefinição de senha da conta Usuário 2.
    
![Guias de Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Clique [aqui](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configurar a sincronização de hash de senha do ambiente de teste do Microsoft 365

Primeiro, siga as instruções em [sincronização de hash de senha](password-hash-sync-m365-ent-test-environment.md). Aqui está sua configuração resultante.
  
![Empresa simulada com ambiente de teste de sincronização de hash de senha](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Esta configuração consiste em: 
  
- Assinaturas pagas ou de avaliação do Office 365 E5 e EMS E5.
- Uma intranet de organização simplificada conectado à Internet, que consiste em máquinas virtuais do DC1 APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure. 
- O Azure AD Connect é executado no APP1 para sincronizar o domínio TESTLAB dos Serviços de Domínio do Active Directory (AD DS) ao locatário do Azure AD de suas assinaturas do Office 365 e do EMS E5.


## <a name="phase-2-enable-password-writeback"></a>Fase 2: Ativar o write-back de senha

Siga as instruções da [Fase 2 do Guia do laboratório de teste de write-back de senha](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).

O write-back de senha precisa estar habilitado para que você possa usar a redefinição de senha.
  
## <a name="phase-3-configure-and-test-password-reset"></a>Fase 3: Configurar e testar a redefinição de senha

Nesta fase, você configura a redefinição de senhas no locatário do Microsoft Azure AD por meio de uma associação de grupo, e verifica se ela funciona.

Primeiro, habilite a redefinição de senhas para as contas em um grupo específico do Azure AD.

1. Abra o [https://portal.azure.com](https://portal.azure.com) em uma instância privada do navegador e entre com as credenciais da conta de administrador global.
2. No Portal do Azure, clique em **Azure Active Directory > Grupos > Novo grupo**.
3. Defina **Tipo de grupo** como **Segurança**, **Nome do grupo** como **PWReset** e **Tipo de associação** como **Atribuído**; em seguida, clique em **Criar**.
5. Clique no grupo **PWReset** na lista e, em seguida, clique em **Membros**.
6. Clique em **Adicionar membros**, clique em **Usuário 2** e em **Selecionar**. Feche as páginas **PWReset** e **Grupo**.
7. Na página do Azure Active Directory, clique em **Redefinição de senha**.
8. Na página **Propriedades**, vá até a opção **Redefinição da Senha de Autoatendimento Habilitada** e escolha **Selecionado**.
9. Em **Selecionar grupo**, selecione **PWReset** e clique em **Salvar**.
10. Feche a instância privada do navegador.

Em seguida, teste a redefinição de senha na conta do Usuário 2.

1. Abra outra instância privada do navegador e acesse [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).
2. Entre com as credenciais da conta do Usuário 2.
3. Em **Não perca o acesso à sua conta**, defina o telefone de autenticação com um número de celular e o email de autenticação com uma conta de email pessoal ou de trabalho.
4. Depois de verificar ambos, clique em **Parece bom** e feche a instância privada do navegador.
5. Abra uma nova instância privada do navegador e vá para [https://aka.ms/sspr](https://aka.ms/sspr).
6. Entre com as credenciais da conta do Usuário 2, digite os caracteres do CAPTCHA e clique em **Avançar**.
8. Na **etapa de verificação 1**, clique em **Inserir o meu email alternativo** e em **Enviar email**. Quando receber o email, digite o código de verificação e clique em **Avançar**.
9. Em **Retornar à sua conta**, digite uma nova senha para a conta do Usuário 2 e clique em **Concluir**. Anote a nova senha da conta do Usuário 2 e guarde-a em um local seguro.
10. Em uma guia separada do mesmo navegador, acesse [https://portal.office.com](https://portal.office.com) e entre com o nome da conta do Usuário 2 e sua nova senha. Você verá a **home page do Microsoft Office**.

Confira informações e links para configurar a redefinição de senhas em produção na etapa [Simplificar a redefinição de senhas](identity-secure-your-passwords.md#identity-pw-reset), na fase Identidade.

## <a name="next-step"></a>Próxima etapa

Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.

## <a name="see-also"></a>Confira também

[Guias do Laboratório de Teste do Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implantar o Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentação do Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
