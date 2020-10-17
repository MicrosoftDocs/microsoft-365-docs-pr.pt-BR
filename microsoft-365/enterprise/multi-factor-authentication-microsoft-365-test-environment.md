---
title: Microsoft 365 para a autenticação multifator do ambiente de teste corporativo
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
- seo-marvel-apr2020
description: Configurar a autenticação multifator usando mensagens de texto enviadas a um telefone inteligente no seu ambiente de teste do Microsoft 365 for Enterprise.
ms.openlocfilehash: f41fe7ad933f85c4b44a1e90529a998651412191
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487135"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a>Autenticação multifator para seu ambiente de teste do Microsoft 365 for Enterprise

*Este guia de laboratório de teste pode ser usado para ambientes de teste corporativos do Microsoft 365 para Enterprise e Office 365.*

Para obter um nível adicional de segurança para entrar no Microsoft 365 ou qualquer serviço ou aplicativo que usa o locatário do Azure AD para sua assinatura, você pode habilitar a autenticação multifator do Azure, que requer mais do que apenas um nome de usuário e senha para verificar uma conta.

Com a autenticação multifator, os usuários precisam confirmar uma chamada telefônica, digitar um código de verificação enviado em uma mensagem de texto ou verificar a autenticação com um aplicativo em seus dispositivos inteligentes após a inserção correta de suas senhas. Eles podem entrar somente após esse segundo fator de autenticação ser satisfeito.
  
Este artigo descreve como habilitar e testar a autenticação baseada em mensagem de texto para uma conta de usuário específica.
  
A configuração da autenticação multifator para uma conta no ambiente de teste do Microsoft 365 for Enterprise envolve duas fases e uma terceira fase opcional:
- [Fase 1: desenvolver seu ambiente de teste do Microsoft 365 for Enterprise](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: habilitar e testar a autenticação multifator para a conta do usuário 2](#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)
- [Fase 3: habilitar e testar a autenticação multifator com uma política de acesso condicional](#phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy)

![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Para obter um mapa Visual para todos os artigos da pilha do guia do laboratório de teste do Microsoft 365 for Enterprise, vá para a [pilha do guia do laboratório de teste da microsoft 365 para empresas](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: desenvolver seu ambiente de teste do Microsoft 365 for Enterprise

Se você só quiser testar a autenticação multifator de forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se você quiser testar a autenticação multifator em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testar a autenticação multifator não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos serviços de domínio Active Directory (AD DS). É fornecida aqui como uma opção para que você possa testar a autenticação multifator e experimentá-la em um ambiente que representa uma organização típica.
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>Fase 2: habilitar e testar a autenticação multifator para a conta do usuário 2

Habilite a autenticação multifator para a conta do usuário 2 com estas etapas:
  
1. Abra uma instância separada e privada do navegador, vá para o centro de administração do Microsoft 365 ( [https://portal.microsoft.com](https://portal.microsoft.com) ) e entre com sua conta de administrador global.
    
2. Na navegação à esquerda, selecione usuários ativos do **usuário**  >  **Active users**.
    
3. No painel usuários ativos, selecione **autenticação multifator**.
    
4. Na lista, selecione a conta do **usuário 2** .
    
5. Na seção **usuário 2** , em **etapas rápidas**, selecione **habilitar**.
    
6. Na caixa de diálogo **sobre como habilitar a autenticação multifator** , selecione **habilitar autenticação multifator**.
    
7. Na caixa de diálogo **atualizações bem-sucedidas** , selecione **fechar**.
    
8. Na guia **centro de administração do Microsoft 365** , selecione o ícone da conta de usuário no canto superior direito e selecione **sair**.
    
9. Feche a instância do navegador.
   
Conclua a configuração da conta do usuário 2 para usar uma mensagem de texto para validação e testá-la com estas etapas:
  
1. Abra uma nova instância privada do navegador.
    
2. Vá para o [centro de administração do Microsoft 365](https://admin.microsoft.com) e entre com o nome da conta e a senha do usuário 2.
    
3. Após entrar, você será solicitado a configurar a conta para obter mais informações. Selecione **Avançar**.
    
4. Na página **verificação de segurança adicional** :
    
   - Selecione seu país ou região.
    
   - Insira o número de telefone inteligente que receberá mensagens de texto.
    
   - Em **método**, selecione **enviar um código por mensagem de texto**.
    
5. Selecione **Avançar**.
    
6. Insira o código de verificação da mensagem de texto recebida no telefone inteligente e selecione **verificar**.
    
7. Na página **etapa 3: manter seus aplicativos existentes** , selecione **concluído**.
    
8. Se esta é a primeira vez que você entrou com a conta de usuário 2, você é solicitado a alterar a senha. Insira a senha original e uma nova senha duas vezes e, em seguida, selecione **Atualizar senha e entrar**. Registre a nova senha em um local seguro.
    
    Você deve ver o portal do Office para o usuário 2 na guia **Microsoft Office Home** do navegador.

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a>Fase 3: habilitar e testar a autenticação multifator com uma política de acesso condicional

*Esta fase só pode ser usada para um ambiente de teste do Microsoft 365 for Enterprise.*

Nesta fase, você habilita a autenticação multifator para a conta do usuário 3 usando um grupo e uma política de acesso condicional.

Em seguida, crie um novo grupo chamado MFAUsers e adicione a ele 3 conta de usuário.

1. Na guia **centro de administração do Microsoft 365** , selecione **grupos** na navegação à esquerda e, em seguida, selecione **grupos**.
2. Selecione **Adicionar um grupo**.
3. No painel **escolher um tipo de grupo** , selecione **segurança**e, em seguida, selecione **Avançar**.
4. No painel **Configurar o básico** , selecione **Criar grupo**e, em seguida, selecione **Fechar**.
5. No painel **revisar e concluir a adição de grupo** , insira **MFAUsers**e, em seguida, selecione **Avançar**.
6. Na lista de grupos, selecione o grupo **MFAUsers** .
7. No painel **MFAUsers** , selecione **Membros**e, em seguida, selecione **Exibir todos e gerenciar Membros**.
8. No painel **MFAUsers** , selecione **adicionar membros**, selecione a conta **usuário 3** e, em seguida, selecione **salvar**  >  **fechar**  >  **fechar**.

Em seguida, crie uma política de acesso condicional para exigir a autenticação multifator para os membros do grupo MFAUsers.

1. Em uma nova guia do navegador, vá para [https://portal.azure.com](https://portal.azure.com) .
2. Selecione acesso condicional de segurança **do Azure Active Directory**  >  **Security**  >  **Conditional Access**.
3. No painel **acesso condicional – políticas** , selecione **nova política**.
4. No painel **novo** , digite **MFA para contas de usuário** na caixa **nome** .
5. Na seção **atribuições** , selecione **usuários e grupos**.
6. Na guia **incluir** do painel **usuários e grupos** , selecione Selecionar **usuários e grupos**  >  **usuários e grupos**  >  **selecionar**.
7. No painel **selecionar** , selecione o grupo **MFAUsers** **e selecione**  >  **concluído**.
8. Na seção **controles de acesso** do painel **novo** , selecione **conceder**.
9. No painel **conceder** , selecione **exigir autenticação multifator**e selecione **selecionar**.
10. No painel **novo** , selecione **Ativar** para **habilitar política**e, em seguida, selecione **criar**.
11. Feche as guias **portal do Azure** e **centro de administração do Microsoft 365** .

Para testar esta política, saia e entre com a conta do usuário 3. Você deve ser solicitado a configurar a MFA. Isso demonstra que a política MFAUsers está sendo aplicada.

## <a name="next-step"></a>Próxima etapa

Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.

## <a name="see-also"></a>Confira também

[Roteiro de identidade](identity-roadmap-microsoft-365.md)

[Guias do Laboratório de Teste do Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Documentação da Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365-enterprise/)
