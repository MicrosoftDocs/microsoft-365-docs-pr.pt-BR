---
title: Redefinição de senha do ambiente de teste do Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/30/2018
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
description: 'Resumo: configurar e testar a redefinição de senha do ambiente de teste do Microsoft 365.'
ms.openlocfilehash: a90cb362a2831bf0bcf3fe05932e3a4345d52b2e
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865261"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a>Redefinição de senha do ambiente de teste do Microsoft 365

O SSPR (autoatendimento de redefinição de senha) do Microsoft Azure AD permite aos usuários redefinir ou desbloquear as senhas ou contas. 

Este artigo descreve como configurar e testar a redefinição de senhas no ambiente de teste do Microsoft 365 em duas fases:

1.  Criar o ambiente de teste de empresa simulada do Microsoft 365 com sincronização de hash de senha.
2.  Configurar e testar a redefinição de senha da conta Usuário 2.
    
![Guias de Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Clique [aqui](https://aka.ms/m365etlgstack) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configurar a sincronização de hash de senha do ambiente de teste do Microsoft 365

Siga as instruções em [sincronização de hash de senha para o Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Aqui está a configuração resultante.
  
![A empresa simulada com ambiente de teste de autenticação de passagem](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
Esta configuração consiste em: 
  
- Assinaturas permanentes ou de avaliação do Office 365 E5 e EMS E5.
- Uma intranet de organização simplificada conectado à Internet, que consiste em máquinas virtuais DC1 APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure. 
- O Azure AD Connect é executado no APP1 para sincronizar o domínio TESTLAB do Windows Server AD com o locatário do Microsoft Azure AD das assinaturas do Office 365 e do EMS E5.

## <a name="phase-2-configure-and-test-password-reset"></a>Fase 2: configurar e testar a redefinição de senhas

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
10. Em uma guia separada do mesmo navegador, acesse [https://portal.office.com](https://portal.office.com) e entre com o nome da conta do Usuário 2 e a nova senha. Você verá a página do **Office Home**.

Confira informações e links para configurar a redefinição de senhas em produção na etapa [Simplificar a redefinição de senhas](identity-password-reset.md), na fase Identidade.

## <a name="next-step"></a>Próxima etapa

Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.

## <a name="see-also"></a>Confira também

[Guias do Laboratório de Teste do Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implantar o Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentação do Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
