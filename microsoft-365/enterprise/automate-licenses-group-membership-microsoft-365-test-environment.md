---
title: Automatizar o licenciamento e a associação de grupo para seu ambiente de teste do Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Configure o licenciamento baseado em grupo e a associação de grupos dinâmicos em seu ambiente de teste do Microsoft 365 Enterprise.
ms.openlocfilehash: b1f3bc4a44e66d162360e82295c8f2877131cd07
ms.sourcegitcommit: fb3815ee186b2b3ec790ee32a9d7b1628d623b0b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/22/2019
ms.locfileid: "39202472"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a>Automatizar o licenciamento e a associação de grupo para seu ambiente de teste do Microsoft 365 Enterprise

*Este Guia de Laboratório de Testes pode ser usado apenas em ambientes de teste do Microsoft 365 Enterprise.*

O licenciamento baseado em grupo atribui ou remove automaticamente licenças de uma conta de usuário com base na associação de grupo. A associação de grupo dinâmico adiciona ou remove membros de um grupo com base nas propriedades da conta de usuário, como departamento ou país. Este artigo orienta você através de uma demonstração do ambiente de teste do Microsoft 365 Enterprise.

Há duas fases para configurar o licenciamento automático e a associação de grupo dinâmico no ambiente de teste do Microsoft 365 Enterprise:

1. Criar o ambiente de teste do Microsoft 365 Enterprise.
2. Configurar e testar a associação de grupo dinâmico e o licenciamento automático.

![Guias de Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Clique [aqui](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Criar o ambiente de teste do Microsoft 365 Enterprise

Se você só quiser testar o licenciamento automatizado e a associação de grupo de forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se você quiser testar o licenciamento automatizado e a associação de grupo em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testar o licenciamento automatizado e a associação de grupo não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos serviços de domínio Active Directory (AD DS). Ele é fornecido aqui como uma opção para que você possa testar o licenciamento e a associação de grupo automatizados e experimentá-lo em um ambiente que representa uma organização típica. 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>Fase 2: configurar e testar a associação de grupo dinâmico e o licenciamento automático

Primeiro, você cria um novo grupo de vendas e adiciona uma regra de associação de grupo dinâmico para que as contas de usuário com o departamento definida como vendas sejam automaticamente adicionadas ao grupo vendas.

1. Usando uma instância privada do navegador da Internet, entre no portal do Office 365 em [https://portal.office.com](https://portal.office.com) com a conta de administrador global da sua assinatura de laboratório de teste do Office 365 e5.
2. Em uma guia separada do navegador, vá para o portal do Azure em [https://portal.azure.com](https://portal.azure.com).
3. No Portal do Azure, clique em **Azure Active Directory > Usuários e grupos > Todos os grupos**.
4. Na folha **todos os grupos** , clique em **novo grupo**.
5. Em **tipo de grupo**, selecione **Office 365**.
6. Em **nome do grupo**, digite **vendas**.
7. Em **tipo de associação**, selecione **usuário dinâmico** .
8. Clique em **Adicionar consulta dinâmica**.
9. Em **Adicionar usuários onde**, selecione **departamento**.
10. No campo seguinte, selecione **Igual a**.
11. No campo seguinte, digite **Sales**.
12. Clique em **Adicionar consulta** e, em seguida, clique em **Criar**.
13. Feche as lâminas **Group** e **groups-All Groups** .

Em seguida, configure o grupo de vendas para que os Membros recebam automaticamente a licença do Microsoft 365 e5.

1. Na folha **visão geral** do Azure Active Directory, clique em **licenças > todos os produtos**.
2. Na lista, selecione **Micrsooft 365 E5**e clique em **atribuir**.
3. Na folha **atribuir licença** , clique em **usuários e grupos**.
4. Na lista de grupos, selecione o grupo **vendas** .
5. Clique em **Selecionar** e clique em **Atribuir**.
6. Feche a guia do Portal do Azure no navegador.

Em seguida, teste a associação de grupo dinâmico e o licenciamento automático na conta do usuário 4. 

1. Na guia **Microsoft Office Home** no navegador, clique em **administrador**.
2. Na guia **centro de administração do Microsoft 365** , clique em **usuários ativos**.
3. Na página **usuários ativos** , clique na conta do **usuário 4** .
4. No painel **usuário 4** , clique em **Editar** para **licenças de produto**.
5. No painel **licenças de produto** , desabilite a licença do **Microsoft 365 E5** e clique em **salvar > fechar**.
6. Nas propriedades da conta do usuário 4, verifique se nenhuma licença de produto foi atribuída e se não há associações de grupo.
7. Clique em **Editar** para obter **informações de contato**.
8. No painel **Editar informações de contato** , clique em **informações de contato**.
9. No campo **Departamento** , digite **vendas**e clique em **salvar > fechar**.
10. Aguarde alguns minutos e clique periodicamente no ícone atualizar no canto superior direito do painel usuário 4 da conta. 

No momento, você verá:

- Propriedade de **associações de grupo** atualizada com o grupo **Sales** .
- Propriedade **Product licenses** atualizada com a licença do **Microsoft 365 E5** .

Consulte estas etapas na fase de identidade para obter informações e links para implantar a associação de grupo dinâmico e o licenciamento automático em produção:

- [Configurar licenciamentos automáticos](identity-use-group-management.md#identity-group-license)
- [Configurar a associação de grupo dinâmica](identity-use-group-management.md#identity-dyn-groups)

## <a name="next-step"></a>Próxima etapa

Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.

## <a name="see-also"></a>Confira também

[Fase 2: Identidade](identity-infrastructure.md)

[Guias do Laboratório de Teste do Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implantação do Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentação do Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
