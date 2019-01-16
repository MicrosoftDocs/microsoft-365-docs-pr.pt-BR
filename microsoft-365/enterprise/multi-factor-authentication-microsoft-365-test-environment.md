---
title: Ambiente de teste a autenticação multifator para sua empresa de 365 da Microsoft
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: Configure a autenticação multifator usando mensagens de texto enviadas a um telefone inteligente em seu ambiente de teste do Microsoft 365 Enterprise.
ms.openlocfilehash: 353f09253794670e8107e084acb3a01cd309fd60
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26864681"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a>Ambiente de teste a autenticação multifator para sua empresa de 365 da Microsoft

Para um nível adicional de segurança para entrar no Office 365 ou qualquer serviço ou aplicativo que usa o locatário do Azure AD para sua organização, você pode ativar o Azure a autenticação multifator, que requer mais do que apenas um nome de usuário e uma senha para verificar um conta. Com a autenticação multifator, os usuários são necessários para reconhecer uma chamada telefônica, digite um código de verificação enviado em uma mensagem de texto ou especificar uma senha de app em seus telefones inteligentes após inserir corretamente suas senhas. Eles podem entrar somente depois que esse segundo fator de autenticação foram atendido. 
  
Este artigo descreve como habilitar e testar a autenticação baseada em mensagens de texto de uma conta específica.
  
Há duas fases para configurar a autenticação multifator para uma conta no seu ambiente de teste do Microsoft 365 Enterprise:
  
1. Crie o ambiente de teste do Microsoft 365 Enterprise.
    
2. Habilitar e testar a autenticação multifator para a conta de usuário 2.

![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Clique [aqui](https://aka.ms/m365etlgstack) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Criar o seu ambiente de teste do Microsoft 365 Enterprise

Se você deseja testar a autenticação multifator de forma leve com os requisitos mínimos, siga as instruções na [configuração base leve](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se você deseja testar a autenticação multifator em uma empresa simulada, siga as instruções na [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testar a autenticação multifator não requer que o ambiente de teste de simulado empresarial, que inclui uma intranet simulada conectada à Internet e a sincronização de diretório para uma floresta do Windows Server AD. Ele é fornecido aqui como uma opção para que você possa testar a autenticação multifator e experimentar em um ambiente que representa uma organização típica. 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>Fase 2: Habilitar e testar a autenticação multifator para a conta de usuário 2

Habilite a autenticação multifator para a conta de usuário 2 com estas etapas:
  
1. Abra uma instância privada separada do navegador, vá para o portal do Office ([https://office.com](https://office.com)) e, em seguida, entre com sua conta de administrador global.
    
2. Na página principal do portal, clique em **Admin**.
    
3. Na navegação à esquerda, clique em **Usuários > Usuários ativos**.
    
4. No painel de usuários ativos, clique em **mais > Configuração da autenticação multifator**.
    
5. Na lista, selecione a conta de **usuário 2** .
    
6. Na seção **2 do usuário** , em **etapas rápidas**, clique em **Habilitar**.
    
7. Na caixa de diálogo **sobre como habilitar a autenticação multifator** , clique em **Habilitar a autenticação multifator**.
    
8. Na caixa de diálogo **atualiza bem-sucedida** , clique em **Fechar**.
    
9. Na guia **Página inicial do Microsoft Office** , clique no ícone de conta de usuário no canto superior direito e clique em **Sair**.
    
10. Feche sua instância do navegador.
   
Conclua a configuração da conta do usuário 2 a usar uma mensagem de texto para validação e testá-lo com estas etapas:
  
1. Abra uma nova instância particular do navegador.
    
2. Vá para o portal do Office ([https://office.com](https://office.com)) e o logon com a conta de usuário 2 (Usuário2 @\<nome da organização >. onmicrosoft.com) e a senha.
    
3. Depois de entrar, você precisará configurar a conta para obter mais informações. Clique em **Avançar**.
    
4. Na página **verificação de segurança adicionais** :
    
   - Selecione seu país ou região.
    
   - Digite o número de telefone do telefone inteligente que receberá mensagens de texto.
    
   - **Método**, clique em **Enviar-me um código de mensagem de texto**.
    
5. Clique em **Avançar**.
    
6. Insira o código de verificação da mensagem de texto recebida no seu telefone inteligente e clique em **Verificar**.
    
7. Sobre o **etapa 3: mantenha seus aplicativos existentes** página, registre a senha do aplicativo exibido para a conta de usuário 2 em um local seguro e clique em **concluído**.
    
8. Se essa for a primeira vez você entrou com a conta de usuário 2, você será solicitado alterar a senha. Digite a senha original e uma nova senha duas vezes e, em seguida, clique em **Atualizar senha e entrar**. Registre a nova senha em um local seguro.
    
    Você deverá ver o portal do Office para o usuário 2 na guia **Página inicial do Microsoft Office** do seu navegador.


Consulte a etapa de [Configurar a autenticação multifator](identity-multi-factor-authentication.md) na fase de identidade para obter informações e links para implantar a autenticação multifator na produção.
    
## <a name="next-step"></a>Próxima etapa

Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.

## <a name="see-also"></a>Confira também

[Fase 2: Identidade](identity-infrastructure.md)

[Guias do Laboratório de Teste do Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implantação do Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentação do Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
