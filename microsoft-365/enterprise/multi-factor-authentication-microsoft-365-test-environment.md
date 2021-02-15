---
title: Autenticação multifa factor do ambiente de teste do Microsoft 365 para empresas
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
description: Configure a autenticação multifatório usando mensagens de texto enviadas para um smartphone em seu ambiente de teste do Microsoft 365 para empresas.
ms.openlocfilehash: 4c59405c1ce59cafaf0309e2314e5cbfa4eb080a
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558437"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a>Autenticação multifatório para seu ambiente de teste do Microsoft 365 para empresas

*Este Guia de Laboratório de Teste pode ser usado para ambientes de teste do Microsoft 365 para empresas e do Office 365 Enterprise.*

Para obter um nível adicional de segurança para entrar no Microsoft 365 ou qualquer serviço ou aplicativo que use o locatário do Azure AD para sua assinatura, você pode habilitar a autenticação multifatório do Azure AD, que exige mais do que apenas um nome de usuário e senha para verificar uma conta.

Com a autenticação multifatório, os usuários precisam confirmar uma chamada telefônica, digitar um código de verificação enviado em uma mensagem de texto ou verificar a autenticação com um aplicativo em seus smartphones depois de inserir corretamente suas senhas. Eles só poderão entrar depois que esse segundo fator de autenticação for atendido.
  
Este artigo descreve como habilitar e testar a autenticação baseada em mensagem de texto para uma conta de usuário específica.
  
Configurar a autenticação multifatório para uma conta no ambiente de teste do Microsoft 365 para empresas envolve duas fases e uma terceira fase opcional:
- [Fase 1: Criar seu ambiente de teste do Microsoft 365 para empresas](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Habilitar e testar a autenticação multifatória para a conta do Usuário 2](#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)
- [Fase 3: Habilitar e testar a autenticação multifacional com uma política de acesso condicional](#phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy)

![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 para empresas, vá para a Pilha de Guias de Laboratório de Teste do [Microsoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)para empresas.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: Criar seu ambiente de teste do Microsoft 365 para empresas

Se você só quiser testar a autenticação multifatare de maneira leve com os requisitos mínimos, siga as instruções na configuração [de base leve.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Se você quiser testar a autenticação multifa factor em uma empresa simulada, siga as instruções na [autenticação de passagem.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> O teste da autenticação multifatório não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta do AD DS (Serviços de Domínio Active Directory). Ele é fornecido aqui como uma opção para que você possa testar a autenticação multifatório e experimentá-la em um ambiente que representa uma organização típica.
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>Fase 2: Habilitar e testar a autenticação multifatória para a conta do Usuário 2

Habilita a autenticação multifabilitar para a conta do Usuário 2 com estas etapas:
  
1. Abra uma instância separada e privada do navegador, vá para o Centro de administração do Microsoft 365 ( ) e entre com sua [https://portal.microsoft.com](https://portal.microsoft.com) conta de administrador global.
    
2. Na navegação à esquerda, selecione **Usuários**  >  **Ativos.**
    
3. No painel Usuários ativos, selecione **autenticação multifator.**
    
4. Na lista, selecione a **conta do Usuário 2.**
    
5. Na seção **Usuário 2,** em Etapas **Rápidas,** selecione **Habilitar**.
    
6. In the **About enabling multi-factor auth** dialog box, select **Enable multi-factor auth**.
    
7. Na caixa **de diálogo Atualizações bem-sucedida,** selecione **Fechar**.
    
8. Na guia centro de administração do **Microsoft 365,** selecione o ícone da conta de usuário no canto superior direito e selecione **Sair.**
    
9. Feche a instância do navegador.
   
Conclua a configuração da conta do Usuário 2 para usar uma mensagem de texto para validação e testá-la com estas etapas:
  
1. Abra uma nova instância privada do navegador.
    
2. Vá para o [Centro de administração do Microsoft 365](https://admin.microsoft.com) e entre com o nome e a senha da conta do Usuário 2.
    
3. Depois de entrar, você será solicitado a configurar a conta para obter mais informações. Selecione **Avançar**.
    
4. Na página **Verificação de segurança** adicional:
    
   - Selecione seu país ou região.
    
   - Insira o número de telefone do smartphone que receberá mensagens de texto.
    
   - In **Method**, select **Send me a code by text message**.
    
5. Selecione **Avançar**.
    
6. Insira o código de verificação da mensagem de texto recebida em seu smartphone e selecione **Verificar**.
    
7. Na Etapa **3: Mantenha sua página de aplicativos existentes,** selecione **Done**.
    
8. Se esta for a primeira vez que você se inscreveu com a conta do Usuário 2, será solicitado a alterar a senha. Insira a senha original e uma nova senha duas vezes e selecione **Atualizar senha e entre.** Grave a nova senha em um local seguro.
    
    Você deverá ver o portal do Office para o Usuário 2 na **guia Microsoft Office Home** do navegador.

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a>Fase 3: Habilitar e testar a autenticação multifacional com uma política de acesso condicional

*Essa fase só pode ser usada para um ambiente de teste do Microsoft 365 para empresas.*

Nesta fase, você habilita a autenticação multifacional para a conta do Usuário 3 usando um grupo e uma política de acesso condicional.

Em seguida, crie um novo grupo chamado MFAUsers e adicione a conta do Usuário 3 a ele.

1. Na guia centro de administração do **Microsoft 365,** selecione **Grupos** na navegação à esquerda e selecione **Grupos.**
2. Selecione **Adicionar um grupo.**
3. In the **Choose a group type** pane, select **Security**, and then select **Next**.
4. In the **Set up the basics** pane, select **Create group**, and then select **Close**.
5. In the **Review and finish adding group** pane, enter **MFAUsers**, and then select **Next**.
6. Na lista de grupos, selecione o **grupo MFAUsers.**
7. No painel **MFAUsers,** selecione **Membros** e selecione **Exibir tudo e gerenciar membros.**
8. No painel **MFAUsers,** selecione **Adicionar** membros, selecione a conta do Usuário **3** e, em **seguida, selecione Salvar**  >    >  **Fechar.**

Em seguida, crie uma política de acesso condicional para exigir autenticação multifator para membros do grupo MFAUsers.

1. Em uma nova guia do navegador, vá para [https://portal.azure.com](https://portal.azure.com) .
2. Selecione Acesso Condicional de Segurança do **Azure Active**  >    >  Directory.
3. No painel **Acesso condicional – Políticas,** selecione **Nova política.**
4. No painel **Novo,** digite **MFA** para contas de usuário **na** caixa Nome.
5. Na seção **Atribuições,** selecione **Usuários e grupos.**
6. On the **Include** tab of the **Users and groups** pane, select Select users and **groups** Users  >  **and groups**  >  **Select**.
7. No painel **Selecionar,** selecione o grupo **MFAUsers** e selecione **Selecionar**  >  **Feito.**
8. Na seção **Controles de** acesso do **novo** painel, selecione **Conceder**.
9. No painel **Conceder,** selecione Exigir autenticação **multifator** e selecione **Selecionar**.
10. No painel **Novo,** selecione Ativado **para** **Habilitar política** e, em seguida, selecione **Criar**.
11. Feche o **portal do Azure e** as guias do Centro de administração do Microsoft **365.**

Para testar essa política, saia e entre com a conta do Usuário 3. Você deve ser solicitado a configurar a MFA. Isso demonstra que a política MFAUsers está sendo aplicada.

## <a name="next-step"></a>Próxima etapa

Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.

## <a name="see-also"></a>Confira também

[Mapa de identidade](identity-roadmap-microsoft-365.md)

[Guias do Laboratório de Teste do Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Documentação do Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365-enterprise/)
