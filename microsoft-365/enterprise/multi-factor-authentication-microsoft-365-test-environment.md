---
title: Microsoft 365 para autenticação multifatório do ambiente de teste empresarial
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
description: Configure a autenticação multifatório usando mensagens de texto enviadas para um telefone inteligente em seu Microsoft 365 ambiente de teste empresarial.
ms.openlocfilehash: aeb8940a9499909b8c568d1230f9aa45aee07b3d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923751"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a>Autenticação multifafatório para seu Microsoft 365 para ambiente de teste empresarial

*Este Guia de Laboratório de Teste pode ser usado para Microsoft 365 ambientes de teste corporativos e Office 365 Enterprise de teste.*

Para obter um nível adicional de segurança para entrar no Microsoft 365 ou qualquer serviço ou aplicativo que use o locatário do Azure AD para sua assinatura, você pode habilitar a autenticação multifabilitar do Azure AD, que exige mais do que apenas um nome de usuário e senha para verificar uma conta.

Com a autenticação multifatório, os usuários são obrigados a reconhecer uma chamada telefônica, digitar um código de verificação enviado em uma mensagem de texto ou verificar a autenticação com um aplicativo em seus telefones inteligentes depois de inserir corretamente suas senhas. Eles só podem entrar depois que esse segundo fator de autenticação for satisfeito.
  
Este artigo descreve como habilitar e testar a autenticação baseada em mensagens de texto para uma conta de usuário específica.
  
Configurar a autenticação multifatória para uma conta em sua Microsoft 365 para o ambiente de teste empresarial envolve duas fases e uma terceira fase opcional:
- [Fase 1: criar seu Microsoft 365 para ambiente de teste empresarial](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Habilitar e testar a autenticação multifatória para a conta do Usuário 2](#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)
- [Fase 3: Habilitar e testar a autenticação multifacional com uma política de acesso condicional](#phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy)

![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Para um mapa visual de todos os artigos na pilha Microsoft 365 guia do laboratório de teste empresarial, vá para o Microsoft 365 para a pilha de guias de laboratório [de teste corporativos.](../downloads/Microsoft365EnterpriseTLGStack.pdf)
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: criar seu Microsoft 365 para ambiente de teste empresarial

Se você quiser apenas testar a autenticação multifa factor de forma leve com os requisitos mínimos, siga as instruções em [Configuração base leve.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Se você quiser testar a autenticação multifa factor em uma empresa simulada, siga as instruções em [Autenticação passagem](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testar a autenticação multifatório não exige o ambiente de teste empresarial simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos Serviços de Domínio do Active Directory (AD DS). Ele é fornecido aqui como uma opção para que você possa testar a autenticação multifa factor e experimentá-la em um ambiente que representa uma organização típica.
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>Fase 2: Habilitar e testar a autenticação multifatória para a conta do Usuário 2

Habilita a autenticação multifabilitar para a conta usuário 2 com estas etapas:
  
1. Abra uma instância separada e privada do navegador, vá para o centro de administração Microsoft 365 ( ), e entre [https://portal.microsoft.com](https://portal.microsoft.com) com sua conta de administrador global.
    
2. Na navegação à esquerda, selecione **Usuários**  >  **Usuários ativos**.
    
3. No painel Usuários ativos, selecione **Autenticação multifator**.
    
4. Na lista, selecione a **conta Usuário 2.**
    
5. Na seção **Usuário 2,** em **Etapas rápidas,** selecione **Habilitar**.
    
6. Na caixa **de diálogo Sobre como habilitar a autenticação** multi-fator, selecione Habilitar **auth multi-factor**.
    
7. Na caixa **de diálogo Atualizações bem-sucedidas,** selecione **Fechar**.
    
8. Na guia **Microsoft 365 centro** de administração, selecione o ícone da conta de usuário no canto superior direito e selecione **Sair**.
    
9. Feche a instância do navegador.
   
Conclua a configuração da conta usuário 2 para usar uma mensagem de texto para validação e testá-la com estas etapas:
  
1. Abra uma nova instância privada do navegador.
    
2. Vá para o [Microsoft 365 de administração](https://admin.microsoft.com) e entre com o nome da conta do Usuário 2 e a senha.
    
3. Depois de entrar, você será solicitado a configurar a conta para obter mais informações. Selecione **Avançar**.
    
4. Na página **Verificação de segurança** adicional:
    
   - Selecione seu país ou região.
    
   - Insira o número de telefone do smartphone que receberá mensagens de texto.
    
   - Em **Método**, selecione **Enviar-me um código por mensagem de texto**.
    
5. Selecione **Avançar**.
    
6. Insira o código de verificação da mensagem de texto recebida em seu smartphone e selecione **Verificar**.
    
7. Na Etapa **3: Mantenha seus aplicativos existentes,** selecione **Feito**.
    
8. Se essa for a primeira vez que você se inscreveu na conta Usuário 2, será solicitado a alterar a senha. Insira a senha original e uma nova senha duas vezes e selecione **Atualizar senha e entre**. Grave a nova senha em um local seguro.
    
    Você deve ver o portal Office para o Usuário 2 na guia **Microsoft Office Home** do navegador.

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a>Fase 3: Habilitar e testar a autenticação multifacional com uma política de acesso condicional

*Essa fase só pode ser usada para um Microsoft 365 para ambiente de teste empresarial.*

Nesta fase, você habilita a autenticação multifacional para a conta usuário 3 usando um grupo e uma política de acesso condicional.

Em seguida, crie um novo grupo chamado MFAUsers e adicione a conta Usuário 3 a ele.

1. Na guia **Microsoft 365 centro de** administração, selecione **Grupos** na navegação à esquerda e selecione **Grupos**.
2. Selecione **Adicionar um grupo**.
3. No painel **Escolher um tipo de** grupo, selecione **Segurança** e, em seguida, selecione **Próximo**.
4. No painel **Configurar as noções básicas,** selecione **Criar grupo** e selecione **Fechar**.
5. No painel **Revisar e concluir a adição de** grupo, insira **MFAUsers** e selecione **Next**.
6. Na lista de grupos, selecione o **grupo MFAUsers.**
7. No painel **MFAUsers,** selecione **Membros** e selecione **Exibir tudo e gerenciar membros**.
8. No painel **MFAUsers,** selecione **Adicionar** membros, selecione a conta Usuário **3** e selecione **Salvar**  >  **Fechar**  >  **Fechar.**

Em seguida, crie uma política de acesso condicional para exigir autenticação multifator para membros do grupo MFAUsers.

1. Em uma nova guia do navegador, vá para [https://portal.azure.com](https://portal.azure.com) .
2. Selecione **Azure Active Directory**  >  **Acesso Condicional** de  >  **Segurança.**
3. No painel **Acesso Condicional – Políticas,** selecione **Nova política**.
4. No painel **Novo,** insira **MFA para contas de usuário** na **caixa** Nome.
5. Na seção **Atribuições,** selecione **Usuários e grupos**.
6. Na guia **Incluir** do painel **Usuários e** grupos, selecione Selecionar usuários **e grupos** Usuários e  >  **grupos**  >  **Selecione**.
7. No painel **Selecionar,** selecione o grupo **MFAUsers** e selecione **Selecionar**  >  **Feito**.
8. Na seção **Controles de** acesso do **painel Novo,** selecione **Conceder**.
9. No painel **Conceder,** selecione **Exigir autenticação multifator** e selecione **Selecionar**.
10. No painel **Novo,** selecione **Ativar para** **Habilitar política** e selecione **Criar**.
11. Feche o **portal do Azure** e **Microsoft 365 de centro de** administração.

Para testar essa política, saia e entre com a conta Usuário 3. Você deve ser solicitado a configurar o MFA. Isso demonstra que a política MFAUsers está sendo aplicada.

## <a name="next-step"></a>Próxima etapa

Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.

## <a name="see-also"></a>Confira também

[Roteiro de identidade](identity-roadmap-microsoft-365.md)

[Guias do Laboratório de Teste do Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Documentação do Microsoft 365 para empresas](/microsoft-365-enterprise/)