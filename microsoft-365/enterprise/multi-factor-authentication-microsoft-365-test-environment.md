---
title: Autenticação multifator para seu ambiente de teste do Microsoft 365 Enterprise
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Configurar a autenticação multifator usando mensagens de texto enviadas a um telefone inteligente no seu ambiente de teste do Microsoft 365 Enterprise.
ms.openlocfilehash: ae8cab25a20cc75992eecc600219d9f1dd869b63
ms.sourcegitcommit: 8e655c6cbb91bfb97efda9a99c39fac33eaa974a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44213135"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a>Autenticação multifator para seu ambiente de teste do Microsoft 365 Enterprise

*Este Guia de Laboratório de Testes pode ser usado para ambientes de teste corporativo do Microsoft 365 Enterprise e do Office 365.*

Para obter um nível adicional de segurança para entrar no Microsoft 365 ou qualquer serviço ou aplicativo que usa o locatário do Azure AD para sua assinatura, você pode habilitar a autenticação multifator do Azure, que requer mais do que apenas um nome de usuário e senha para verificar uma conta. 

Com a autenticação multifator, os usuários precisam confirmar uma chamada telefônica, digitar um código de verificação enviado em uma mensagem de texto ou verificar a autenticação com um aplicativo em seus dispositivos inteligentes após a inserção correta de suas senhas. O acesso só será possível depois que esse segundo fator de autenticação for atendido. 
  
Este artigo descreve como habilitar e testar a autenticação baseada em mensagem de texto para uma conta de usuário específica.
  
Há duas fases para configurar a autenticação multifator para uma conta no seu ambiente de teste do Microsoft 365 Enterprise:
  
1. Criar o ambiente de teste do Microsoft 365 Enterprise.
    
2. Habilite e teste a autenticação multifator para a conta do usuário 2.

3. Habilite e teste a autenticação multifator com uma política de acesso condicional (opcional).

![Guias do Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Clique [aqui](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver um mapa visual de todos os artigos na pilha do Guia do Test Lab do Microsoft 365 Enterprise.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: criar o ambiente de teste do Microsoft 365 Enterprise

Se você só quiser testar a autenticação multifator de forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se você quiser testar a autenticação multifator em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testar a autenticação multifator não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos serviços de domínio Active Directory (AD DS). É fornecida aqui como uma opção para que você possa testar a autenticação multifator e experimentá-la em um ambiente que representa uma organização típica. 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>Fase 2: habilitar e testar a autenticação multifator para a conta do usuário 2

Habilite a autenticação multifator para a conta do usuário 2 com estas etapas:
  
1. Abra uma instância separada e privada do navegador, vá para o centro de administração do Microsoft 365 ( [https://portal.microsoft.com](https://portal.microsoft.com) ) e entre com sua conta de administrador global.
    
2. Na navegação à esquerda, clique em **Usuários > Usuários ativos**.
    
3. No painel usuários ativos, clique em **autenticação multifator**.
    
4. Na lista, selecione a conta do **usuário 2** .
    
5. Na seção **usuário 2** , em **etapas rápidas**, clique em **habilitar**.
    
6. Na caixa de diálogo **sobre como habilitar a autenticação multifator** , clique em **habilitar autenticação multifator**.
    
7. Na caixa de diálogo **atualizações com êxito** , clique em **fechar**.
    
8. Na guia **centro de administração do Microsoft 365** **, clique no**ícone da conta de usuário no canto superior direito e clique em sair.
    
9. Feche a instância do navegador.
   
Conclua a configuração da conta do usuário 2 para usar uma mensagem de texto para validação e testá-la com estas etapas:
  
1. Abra uma nova instância privada do navegador.
    
2. Vá para o portal do Office 365 ( [https://portal.office.com](https://portal.office.com) ) e entre com o nome da conta e a senha do usuário 2.
    
3. Após entrar, você será solicitado a configurar a conta para obter mais informações. Clique em **Avançar**.
    
4. Na página **verificação de segurança adicional** :
    
   - Selecione seu país ou região.
    
   - Digite o número de telefone do telefone inteligente que receberá mensagens de texto.
    
   - Em **método**, clique em **enviar um código por mensagem de texto**.
    
5. Clique em **Avançar**.
    
6. Insira o código de verificação da mensagem de texto recebida no telefone inteligente e clique em **verificar**.
    
7. Na página **etapa 3: manter seus aplicativos existentes** , clique em **concluído**.
    
8. Se esta é a primeira vez que você entrou com a conta de usuário 2, você é solicitado a alterar a senha. Digite a senha original e uma nova senha duas vezes e clique em **Atualizar senha e entrar**. Registre a nova senha em um local seguro.
    
    Você deve ver o portal do Office para o usuário 2 na guia **Microsoft Office Home** do navegador.

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a>Fase 3: habilitar e testar a autenticação multifator com uma política de acesso condicional

*Esta fase só pode ser usada para um ambiente de teste do Microsoft 365 Enterprise.*

Nesta fase, habilite a autenticação multifator para a conta do usuário 3 usando um grupo e uma política de acesso condicional.

Em seguida, crie um novo grupo chamado MFAUsers e adicione a ele 3 conta de usuário.

1. Na guia **centro de administração do Microsoft 365** , clique em **grupos** na navegação à esquerda e, em seguida, clique em **grupos**.
2. Clique em **Adicionar um grupo**.
3. No painel **escolher um tipo de grupo** , selecione **segurança**e clique em **Avançar**.
4. No painel **Configurar o básico** , clique em **Criar grupo**e, em seguida, clique em **Fechar**.
5. No painel **revisar e concluir a adição de grupo** , digite **MFAUsers**e clique em **Avançar**.
6. Na lista de grupos, clique no grupo **MFAUsers** .
7. No painel **MFAUsers** , clique em **Membros**e, em seguida, clique em **Exibir todos e gerenciar Membros**.
8. No painel **MFAUsers** , clique em **adicionar membros**, selecione a conta do **usuário 3** e, em seguida, clique em **salvar > fechar > fechar**.

Em seguida, crie uma política de acesso condicional para exigir a autenticação multifator para os membros do grupo MFAUsers.

1. Em uma nova guia do navegador, vá para [https://portal.azure.com](https://portal.azure.com) .
2. Clique em **Azure Active Directory > segurança > acesso condicional**.
3. No painel **acesso condicional – políticas** , clique em **nova política**.
4. No painel **novo** , digite **MFA para contas de usuário** em **nome**.
5. Na seção **atribuições** , clique em **usuários e grupos**.
6. Na guia **incluir** do painel **usuários e grupos** , clique em **Selecionar usuários e grupos > usuários e grupos > selecionar**.
7. No painel **selecionar** , clique no grupo **MFAUsers** e, em seguida, clique em **selecionar > concluído**.
8. Na seção **controles de acesso** do painel **novo** , clique em **conceder**.
9. No painel **conceder** , clique em **exigir autenticação multifator**e clique em **selecionar**.
10. No painel **novo** , **clique em ativar** para **habilitar a política**e clique em **criar**.
11. Feche as guias **portal do Azure** e **centro de administração do Microsoft 365** .

Para testar esta política, saia e entre com a conta do usuário 3. Você deve ser solicitado a configurar a MFA. Isso demonstra que a política MFAUsers está sendo aplicada.

Consulte a etapa [Configurar a autenticação multifator](identity-secure-user-sign-ins.md#identity-mfa) na fase Identity para obter informações e links para implantar a autenticação multifator em produção.
    
## <a name="next-step"></a>Próxima etapa

Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.

## <a name="see-also"></a>Confira também

[Fase 2: Identidade](identity-infrastructure.md)

[Guias do Laboratório de Teste do Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implantação do Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentação do Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
