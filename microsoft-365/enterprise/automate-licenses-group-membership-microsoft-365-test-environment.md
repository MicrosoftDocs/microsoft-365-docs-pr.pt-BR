---
title: Automatizar o licenciamento e a associação de grupo para seu ambiente de teste do Microsoft 365 for Enterprise
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Configure o licenciamento baseado em grupo e a associação de grupos dinâmicos em seu ambiente de teste do Microsoft 365 for Enterprise.
ms.openlocfilehash: d770e7be3b0b55855f1fee26a45d55260c3074cb
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487571"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a>Automatizar o licenciamento e a associação de grupo para seu ambiente de teste do Microsoft 365 for Enterprise

*Este guia de laboratório de teste só pode ser usado para o Microsoft 365 para ambientes de teste corporativos.*

O licenciamento baseado em grupo atribui ou remove automaticamente licenças de uma conta de usuário com base na associação de grupo. A associação de grupo dinâmico adiciona ou remove membros de um grupo com base nas propriedades da conta de usuário, como **Departamento** ou **país**. Este artigo orienta você nas demonstrações de adição e remoção de membros de grupo no seu ambiente de teste do Microsoft 365 for Enterprise.

Configurar o licenciamento automático e a associação de grupo dinâmico no seu ambiente de teste do Microsoft 365 for Enterprise envolve duas fases:

- [Fase 1: desenvolver seu ambiente de teste do Microsoft 365 for Enterprise](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: configurar e testar a associação de grupo dinâmico e o licenciamento automático](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Para obter um mapa Visual para todos os artigos da pilha do guia do laboratório de teste do Microsoft 365 for Enterprise, vá para a [pilha do guia do laboratório de teste da microsoft 365 para empresas](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: desenvolver seu ambiente de teste do Microsoft 365 for Enterprise

Se você quiser testar apenas o licenciamento automatizado e a associação de grupo de forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se você quiser testar o licenciamento automatizado e a associação de grupo em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testar o licenciamento automatizado e a associação de grupo não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos serviços de domínio Active Directory (AD DS). Ele é fornecido aqui como uma opção para que você possa testar o licenciamento e a associação de grupo automatizados e experimentá-lo em um ambiente que representa uma organização típica.
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>Fase 2: configurar e testar a associação de grupo dinâmico e o licenciamento automático

Primeiro, crie um novo grupo chamado vendas e adicione uma regra de associação de grupo dinâmico para que as contas de usuário com o **Departamento** definido como **vendas** ingressem automaticamente no grupo vendas.

1. Em uma instância privada do navegador da Internet, entre no centro de [Administração do microsoft 365](https://admin.microsoft.com) com a conta de administrador global da sua assinatura de laboratório de teste do Microsoft 365 e5.
2. Em uma guia separada do navegador, vá para o portal do Azure em [https://portal.azure.com](https://portal.azure.com) .
3. No portal do Azure, insira **grupos** na caixa de pesquisa e selecione **grupos**.
4. no painel **todos os grupos** , selecione **novo grupo**.
5. Em **tipo de grupo**, selecione **Microsoft 365**.
6. Em **nome do grupo**, insira **vendas**.
7. Em **tipo de associação**, selecione **usuário dinâmico**.
8. Selecione **membros dinâmicos do usuário**.
9. No painel **regras de associação dinâmicas** : 
   - Selecione a propriedade **Department** .
   - Selecione o operador **Equals** .
   - Na caixa **valor** , insira **vendas**.
10. Selecione **Salvar**.
11. Selecione **Criar**.

Em seguida, configure o grupo de vendas para que os Membros recebam automaticamente a licença do Microsoft 365 e5.

1. Selecione o grupo **vendas** e, em seguida, selecione **licenças**.
2. No painel **Atualizar atribuições de licença** , selecione **Microsoft 365 E5**e, em seguida, selecione **salvar**.
3. No navegador, feche a guia portal do Azure.

Em seguida, teste a associação de grupo dinâmico e o licenciamento automático na conta do usuário 4:

1. Na guia **Microsoft Office Home** no navegador, selecione **administrador**.
2. Na guia **centro de administração do Microsoft 365** , selecione **usuários ativos**.
3. Na página **usuários ativos** , selecione a conta do **usuário 4** .
4. No painel **usuário 4** , selecione **Editar** para **licenças de produto**.
5. No painel **licenças de produto** , desabilite a licença do **Microsoft 365 E5** e selecione **salvar**  >  **fechar**.
6. Nas propriedades da conta do usuário 4, verifique se nenhuma licença de produto foi atribuída e se não há associações de grupo.
7. Para obter **informações de contato**, selecione **Editar**.
8. No painel **Editar informações de contato** , selecione **informações de contato**.
9. Na caixa **Departamento** , insira **vendas**e, em seguida, selecione **salvar**  >  **fechar**.
10. Aguarde alguns minutos e, em seguida, selecione periodicamente o ícone **Atualizar** no canto superior direito do painel usuário 4 da conta.

No momento, você deve ver:

- Propriedade de **associações de grupo** atualizada com o grupo **Sales** .
- Propriedade **Product licenses** atualizada com a licença do **Microsoft 365 E5** .

Consulte estes artigos para implantar a associação de grupo dinâmico e o licenciamento automático em produção:

- [Licenciamento baseado em grupo no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [Grupos dinâmicos no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a>Próxima etapa

Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.

## <a name="see-also"></a>Confira também

[Roteiro de identidade](identity-roadmap-microsoft-365.md)

[Guias do Laboratório de Teste do Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Documentação da Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365-enterprise/)
