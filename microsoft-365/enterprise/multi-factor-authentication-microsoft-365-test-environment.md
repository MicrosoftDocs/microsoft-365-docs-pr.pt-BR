---
title: Autenticação multifator para seu ambiente de teste do Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Configurar a autenticação multifator usando mensagens de texto enviadas a um telefone inteligente no seu ambiente de teste do Microsoft 365 Enterprise.
ms.openlocfilehash: 8e202936451030718c0c86601c2c621c50f78e1a
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291136"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a>Autenticação multifator para seu ambiente de teste do Microsoft 365 Enterprise

Para obter um nível adicional de segurança para entrar no Office 365 ou qualquer serviço ou aplicativo que usa o locatário do Azure AD para sua organização, você pode habilitar a autenticação multifator do Azure, que requer mais do que apenas um nome de usuário e senha para verificar um Count. Com a autenticação multifator, os usuários precisam confirmar uma chamada telefônica, digitar um código de verificação enviado em uma mensagem de texto ou especificar uma senha de aplicativo em seus telefones inteligentes após inserir corretamente suas senhas. O acesso só será possível depois que esse segundo fator de autenticação for atendido. 
  
Este artigo descreve como habilitar e testar a autenticação baseada em mensagem de texto para uma conta específica.
  
Há duas fases para configurar a autenticação multifator para uma conta no seu ambiente de teste do Microsoft 365 Enterprise:
  
1. Crie o ambiente de teste do Microsoft 365 Enterprise.
    
2. Habilite e teste a autenticação multifator para a conta do usuário 2.

![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Clique [aqui](https://aka.ms/m365etlgstack) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: criar seu ambiente de teste do Microsoft 365 Enterprise

Se você só quiser testar a autenticação multifator de forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se você quiser testar a autenticação multifator em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testar a autenticação multifator não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos serviços de domínio Active Directory (AD DS). É fornecida aqui como uma opção para que você possa testar a autenticação multifator e experimentá-la em um ambiente que representa uma organização típica. 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>Fase 2: habilitar e testar a autenticação multifator para a conta do usuário 2

Habilite a autenticação multifator para a conta do usuário 2 com estas etapas:
  
1. Abra uma instância separada e privada do navegador, vá para o portal do Office ([https://office.com](https://office.com)) e entre com sua conta de administrador global.
    
2. Na página principal do portal, clique em **Admin**.
    
3. Na navegação à esquerda, clique em **Usuários > Usuários ativos**.
    
4. No painel usuários ativos, clique em **mais > configuração de autenticação**multifator.
    
5. Na lista, selecione a conta do **usuário 2** .
    
6. Na seção **usuário 2** , em **etapas rápidas**, clique em **habilitar**.
    
7. Na caixa de diálogo **sobre como habilitar a autenticação** multifator, clique em **habilitar autenticação**multifator.
    
8. Na caixa de diálogo **atualizações com êxito** , clique em **fechar**.
    
9. Na guia **Microsoft Office Home** , clique no ícone da conta de usuário no canto superior direito e clique em **** sair.
    
10. Feche a instância do navegador.
   
Conclua a configuração da conta do usuário 2 para usar uma mensagem de texto para validação e testá-la com estas etapas:
  
1. Abra uma nova instância privada do navegador.
    
2. Vá para o portal do Office[https://office.com](https://office.com)() e entre com a conta do usuário 2 (Usuário2\<@ Organization name>. onmicrosoft. com) e a senha.
    
3. Após entrar, você será solicitado a configurar a conta para obter mais informações. Clique em **Avançar**.
    
4. Na página **verificação de segurança adicional** :
    
   - Selecione seu país ou região.
    
   - Digite o número de telefone do telefone inteligente que receberá mensagens de texto.
    
   - Em **método**, clique em **enviar um código por mensagem de texto**.
    
5. Clique em **Avançar**.
    
6. Insira o código de verificação da mensagem de texto recebida no telefone inteligente e clique em **verificar**.
    
7. Na página **etapa 3: manter seus aplicativos existentes** , registre a senha do aplicativo exibida para a conta do usuário 2 em um local seguro e clique em **concluído**.
    
8. Se esta é a primeira vez que você entrou com a conta de usuário 2, você é solicitado a alterar a senha. Digite a senha original e uma nova senha duas vezes e clique em **Atualizar senha e entrar**. Registre a nova senha em um local seguro.
    
    Você deve ver o portal do Office para o usuário 2 na guia **Microsoft Office Home** do navegador.


Consulte a etapa [Configurar a autenticação](identity-multi-factor-authentication.md#identity-mfa) multifator na fase Identity para obter informações e links para implantar a autenticação multifator em produção.
    
## <a name="next-step"></a>Próxima etapa

Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.

## <a name="see-also"></a>Confira também

[Fase 2: Identidade](identity-infrastructure.md)

[Guias do Laboratório de Teste do Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implantação do Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentação do Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
