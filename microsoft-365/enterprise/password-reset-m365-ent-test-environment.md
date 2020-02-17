---
title: Redefinição de senha do ambiente de teste do Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/13/2019
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
ms.openlocfilehash: c8d5ed0c7feac98afd3230a305f4ab1f850ca7f8
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066137"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a>Redefinição de senha do ambiente de teste do Microsoft 365

*Este Guia de Laboratório de Testes pode ser usado apenas em ambientes de teste do Microsoft 365 Enterprise.*

A redefinição de senha de autoatendimento (SSPR) do Azure Active Directory (Azure AD) permite que os usuários redefinam ou desbloqueiem suas senhas ou contas. 

Este artigo descreve como você pode configurar e testar redefinições de senha em seu ambiente de teste do Microsoft 365 em três fases:

1.  Criar o ambiente de teste do Microsoft 365 Enterprise.
2.  Ativar write-back de senha.
3.  Configure e teste a redefinição de senha da conta do Usuário 3.
    
![Guias do Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Clique [aqui](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configurar a sincronização de hash de senha do ambiente de teste do Microsoft 365

Primeiro, siga as instruções em [sincronização de hash de senha](password-hash-sync-m365-ent-test-environment.md). Aqui está sua configuração resultante.
  
![Empresa simulada com ambiente de teste de sincronização de hash de senha](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Esta configuração consiste em: 
  
- Assinaturas de avaliação ou pagas do Microsoft 365 E5 ou Office 365 E5.
- Uma intranet de organização simplificada conectado à Internet, que consiste em máquinas virtuais do DC1 APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure. 
- O Azure AD Connect é executado no APP1 para sincronizar o domínio TESTLAB do Active Directory Domain Services (AD DS) com o locatário do Azure AD de assinatura do Microsoft 365 ou do Office 365.

## <a name="phase-2-enable-password-writeback"></a>Fase 2: Ativar o write-back de senha

Siga as instruções da [Fase 2 do Guia do laboratório de teste de write-back de senha](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).

O write-back de senha precisa estar habilitado para que você possa usar a redefinição de senha.
  
## <a name="phase-3-configure-and-test-password-reset"></a>Fase 3: Configurar e testar a redefinição de senha

Nesta fase, você configura a redefinição de senhas no locatário do Microsoft Azure AD por meio de uma associação de grupo, e verifica se ela funciona.

Primeiro, habilite a redefinição de senhas para as contas em um grupo específico do Azure AD.

1. Abra o [https://portal.azure.com](https://portal.azure.com) em uma instância privada do navegador e entre com as credenciais da conta de administrador global.
2. No Portal do Azure, clique em **Azure Active Directory > Grupos > Novo grupo**.
3. Defina o **Tipo de grupo** como **Segurança**, **Nome do grupo** como **PWReset** e o**Tipo de associação** como **Atribuído**. 
4. Clique em **Membros**, localize e selecione **Usuário 3**, em seguida, clique em **Selecionar**e, logo depois, clique em **Criar**.
5. Feche o painel de **Grupos**.
6. No painel de Azure Active Directory, clique em**Redefinição de senha**na barra de navegação à esquerda.
7. No painel **Redefinição de senha-Propriedades**, vá até a opção **Redefinição da Senha de Autoatendimento Habilitada** e escolha **Selecionado**.
8. Clique **Selecionar grupo**, selecione o grupo **PWReset** e, em seguida, clique em **Selecionar > Salvar**.
9. Feche a instância privada do navegador.

Em seguida, teste a redefinição de senha para a conta do Usuário 3.

1. Abra outra instância privada do navegador e vá para [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).
2. Entre usando as credenciais da conta do Usuário 3.
3. Em **Mais informações**, clique em **Avançar**. 
5. Em **Não perca o acesso à sua conta**, defina o telefone de autenticação com um número de celular e o email de autenticação com uma conta de email pessoal ou de trabalho.
7. Depois de verificar ambos, clique em **Parece bom** e feche a instância privada do navegador.
8. Abra uma nova instância privada do navegador e vá para [https://aka.ms/sspr](https://aka.ms/sspr).
9. Digite o nome da conta do Usuário 3, digite os caracteres do CAPTCHA e clique em **Avançar**.
10. Na **etapa de verificação 1**, clique em **Inserir o meu email alternativo** e em **Enviar email**. Quando receber o email, digite o código de verificação e clique em **Avançar**.
11. No **Retornar à sua conta**, digite uma nova senha para a conta do Usuário 3 e clique em **Concluir**. Anote a senha alterada da conta do Usuário 3 e armazene-a em um local seguro.
12. Em uma guia separada do mesmo navegador, vá para [https://portal.office.com](https://portal.office.com) e entre com o nome da conta do Usuário 3 e sua nova senha. Você verá a **home page do Microsoft Office**.

Confira informações e links para configurar a redefinição de senhas em produção na etapa [Simplificar a redefinição de senhas](identity-secure-your-passwords.md#identity-pw-reset), na fase Identidade.

## <a name="next-step"></a>Próxima etapa

Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.

## <a name="see-also"></a>Confira também

[Guias do Laboratório de Teste do Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implantar o Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentação do Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
