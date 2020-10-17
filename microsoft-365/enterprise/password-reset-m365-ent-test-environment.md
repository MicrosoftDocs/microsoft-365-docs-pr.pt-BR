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
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Resumo: configurar e testar a redefinição de senha do ambiente de teste do Microsoft 365.'
ms.openlocfilehash: 5d98dcc50f16bc08da787a928beeeacf825201c9
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487419"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a>Redefinição de senha do ambiente de teste do Microsoft 365

*Este guia de laboratório de teste só pode ser usado para o Microsoft 365 para ambientes de teste corporativos.*

A redefinição de senha de autoatendimento (SSPR) do Azure Active Directory (Azure AD) permite que os usuários redefinam ou desbloqueiem suas senhas ou contas.

Este artigo descreve como configurar e testar redefinições de senha no seu ambiente de teste do Microsoft 365.

A configuração do SSPR envolve três fases:
- [Fase 1: configurar a sincronização de hash de senha do ambiente de teste do Microsoft 365](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [Fase 2: Ativar o write-back de senha](#phase-2-enable-password-writeback)
- [Fase 3: Configurar e testar a redefinição de senha](#phase-3-configure-and-test-password-reset)
    
![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Para obter um mapa Visual para todos os artigos da pilha do guia do laboratório de teste do Microsoft 365 for Enterprise, vá para a [pilha do guia do laboratório de teste da microsoft 365 para empresas](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configurar a sincronização de hash de senha do ambiente de teste do Microsoft 365

Primeiro, siga as instruções em [sincronização de hash de senha](password-hash-sync-m365-ent-test-environment.md). 

A configuração resultante tem a seguinte aparência:
  
![Empresa simulada com ambiente de teste de sincronização de hash de senha](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Esta configuração consiste em:
  
- Uma assinatura de avaliação ou assinatura paga do Microsoft 365 E5.
- Uma intranet de organização simplificada conectada à Internet, consistindo nas máquinas virtuais DC1, APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure.
- O Azure AD Connect é executado no APP1 para sincronizar o domínio dos Serviços de domínio Active Directory (AD DS) do TESTLAB com o locatário do Azure AD da sua assinatura do Microsoft 365.

## <a name="phase-2-enable-password-writeback"></a>Fase 2: Ativar o write-back de senha

Siga as instruções da [Fase 2 do Guia do laboratório de teste de write-back de senha](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).

O write-back de senha precisa estar habilitado para que você possa usar a redefinição de senha.
  
## <a name="phase-3-configure-and-test-password-reset"></a>Fase 3: Configurar e testar a redefinição de senha

Nesta fase, configure a redefinição de senha no locatário do Azure AD por meio da Associação de grupo e verifique se ela funciona.

Primeiro, habilite a redefinição de senhas para as contas em um grupo específico do Azure AD.

1. Abra o [https://portal.azure.com](https://portal.azure.com) em uma instância privada do navegador e entre com as credenciais da conta de administrador global.
2. No portal do Azure, selecione **Azure Active Directory**  >  **Groups**  >  **novo grupo**grupos do Azure Active Directory.
3. Defina o **Tipo de grupo** como **Segurança**, **Nome do grupo** como **PWReset** e o**Tipo de associação** como **Atribuído**.
4. Selecione **Membros**, localizar e selecionar **usuário 3**, selecione **selecionar**e, em seguida, selecione **criar**.
5. Feche o painel de **Grupos**.
6. No painel do Azure Active Directory, selecione **redefinição de senha** na navegação à esquerda.
7. No painel **Redefinição de senha-Propriedades**, vá até a opção **Redefinição da Senha de Autoatendimento Habilitada** e escolha **Selecionado**.
8. Selecione **selecionar grupo**, selecione o grupo **PWReset** **e selecione**  >  **salvar**.
9. Feche a instância privada do navegador.

Em seguida, teste a redefinição de senha para a conta do usuário 3.

1. Abra outra instância privada do navegador e vá para [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).
1. Entre usando as credenciais da conta do Usuário 3.
1. Em **mais informações necessárias**, selecione **Avançar**. 
1. Em **Não perca o acesso à sua conta**, defina o telefone de autenticação como seu número de celular e o e-mail de autenticação como sua conta de e-mail pessoal ou profissional.
1. Após a verificação, selecione **boa aparência**e feche a instância privada do navegador.
1. Em uma nova instância privada do navegador, vá para [https://aka.ms/sspr](https://aka.ms/sspr) .
1. Insira o nome da conta do usuário 3, digite os caracteres do CAPTCHA e selecione **Avançar**.
1. Para a **etapa de verificação 1**, selecione email de **meu email alternativo**e, em seguida, selecione **email**. Ao receber o email, insira o código de verificação e, em seguida, selecione **Avançar**.
1. Em **obter novamente a sua conta**, insira uma nova senha para a conta do usuário 3 e selecione **concluir**. Anote a senha alterada da conta do Usuário 3 e armazene-a em um local seguro.
1. Em uma guia separada do mesmo navegador, vá para [https://portal.office.com](https://portal.office.com) e entre com o nome da conta do Usuário 3 e sua nova senha. Você verá a **home page do Microsoft Office**.

## <a name="next-step"></a>Próxima etapa

Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.

## <a name="see-also"></a>Confira também

[Guias do Laboratório de Teste do Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Documentação da Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365-enterprise/)
