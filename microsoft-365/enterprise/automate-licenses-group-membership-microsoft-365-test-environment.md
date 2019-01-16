---
title: Automatizar a associação de grupo e licenciamento para o seu ambiente de teste do Microsoft 365 Enterprise
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
description: Configure o licenciamento do grupo e a associação ao grupo dinâmico em seu ambiente de teste do Microsoft 365 Enterprise.
ms.openlocfilehash: 45a78af202f2d9ab029683aae4d95ed9a3370b08
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26865067"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a>Automatizar a associação de grupo e licenciamento para o seu ambiente de teste do Microsoft 365 Enterprise

Licenciamento baseado no grupo automaticamente atribui ou remove licenças para uma conta de usuário com base na associação de grupo. A associação ao grupo dinâmico adiciona ou remove membros a um grupo com base em Propriedades de conta de usuário, como departamento ou país. Este artigo orienta uma demonstração de ambos no seu ambiente de teste do Microsoft 365 Enterprise.

Há duas fases para configurar a participação no grupo de licenciamento automático e dinâmicas no seu ambiente de teste do Microsoft 365 Enterprise:

1. Crie o ambiente de teste do Microsoft 365 Enterprise.
2. Configurar e testar a associação ao grupo dinâmico e licenciamento automático.

![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Clique [aqui](https://aka.ms/m365etlgstack) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Criar o seu ambiente de teste do Microsoft 365 Enterprise

Se você quiser testar automatizada de licenciamento e participação no grupo em uma maneira leve com os requisitos mínimos, siga as instruções na [configuração base leve](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se você deseja testar automatizada de licenciamento e a participação no grupo em uma empresa simulada, siga as instruções na [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testando automatizada de licenciamento e a associação de grupo não requer o ambiente de teste de simulado empresarial, que inclui uma intranet simulada conectada à Internet e a sincronização de diretório para uma floresta do Windows Server AD. Ele é fornecido aqui como uma opção para que você possa testar automatizada de licenciamento e a associação ao grupo e experimentar em um ambiente que representa uma organização típica. 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>Fase 2: Configurar e testar a associação ao grupo dinâmico e licenciamento automático

Primeiro, você pode cria um novo grupo de vendas e adicionar uma regra de associação de grupo dinâmico de modo que as contas de usuário com o departamento definido como vendas são automaticamente adicionadas ao grupo de vendas.

1. Usando uma instância particular do seu navegador da Internet, entrar no portal do Office em [https://office.com](https://office.com) com a conta de administrador global de sua assinatura de avaliação do Office 365 E5.
2. Em uma guia separada do navegador, vá para o portal do Windows Azure em [https://portal.azure.com](https://portal.azure.com).
3. No Portal do Azure, clique em **Azure Active Directory > Usuários e grupos > Todos os grupos**.
4. No blade **todos os grupos** , clique em **novo grupo**.
5. Em **tipo de grupo**, selecione **Office 365**.
6. Em **nome do grupo**, digite **vendas**.
7. Em **tipo de associação**, selecione **usuário dinâmico** .
8. Clique em **Adicionar consulta dinâmica**.
9. Em **Adicionar usuários onde**, selecione **departamento**.
10. No campo seguinte, selecione **Igual a**.
11. No campo próximo, digite **vendas**.
12. Clique em **Adicionar consulta** e, em seguida, clique em **Criar**.
13. Feche as lâminas de **grupo** e **os grupos de grupos a todos** .

Em seguida, você configurar o grupo de vendas para que os membros são automaticamente atribuídos E5 do Office 365 e mobilidade corporativos + segurança E5 licenças.

1. No blade **Visão geral** do Azure Active Directory, clique em **licenças > todos os produtos**.
2. Na lista, escolha **Enterprise Mobility + Security E5** e **Office 365 Enterprise E5** e clique em **Atribuir**.
3. No blade **atribuir licença** , clique em **usuários e grupos**.
4. Na lista de grupos, selecione o grupo de **vendas** .
5. Clique em **Selecionar** e clique em **Atribuir**.
6. Feche a guia do Portal do Azure no navegador.

Em seguida, você teste a associação ao grupo dinâmico e licenciamento automático na conta do usuário 4. 

1. Na guia **Página inicial do Microsoft Office** no seu navegador, clique em **Admin**.
2. A partir da guia do **Centro de administração do Office** , clique em **usuários ativos**.
3. Na página **usuários ativos** , clique na conta de **usuário 4** .
4. No painel de **4 de usuário** , clique em **Editar** para **licenças de produto**.
5. No painel de **licenças do produto** , ative a **mobilidade corporativos + segurança E5** e licenças do **Office 365 Enterprise E5** desativada e clique em **Salvar > fechar**.
6. Nas propriedades da conta de usuário 4, verifique não se tiverem sido atribuída a nenhuma licença do produto e não há nenhuma associações de grupo.
7. Para **obter informações de contato**, clique em **Editar** .
8. No painel de **informações de contato de editar** , clique em **informações de contato**.
9. No campo **departamento** , digite **vendas**e clique em **Salvar > fechar**.
10. Aguarde alguns minutos e clique no ícone Atualizar no canto superior direito do painel de conta de usuário 4 periodicamente. 

No momento, você deverá ver a:

- Propriedade de **associações de grupo** atualizada com o grupo de **vendas** .
- Propriedade de **licenças de produto** atualizada com as licenças de **mobilidade corporativos + E5 de segurança** e o **Office 365 Enterprise E5** .

Consulte estas etapas na fase de identidade para obter informações e links para implantar a associação ao grupo dinâmico e licenciamento automático na produção:

- [Configurar licenciamentos automáticos](identity-group-based-licensing.md)
- [Configurar associações de grupo dinâmico](identity-automatic-group-membership.md)

## <a name="next-step"></a>Próxima etapa

Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.

## <a name="see-also"></a>Confira também

[Fase 2: Identidade](identity-infrastructure.md)

[Guias do Laboratório de Teste do Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implantação do Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentação do Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
