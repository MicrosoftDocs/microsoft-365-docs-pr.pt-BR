---
title: Automatizar o licenciamento e a associação de grupo para seu ambiente de teste do Microsoft 365 para empresas
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
description: Configure o licenciamento baseado em grupo e a associação de grupo dinâmica em seu ambiente de teste do Microsoft 365 para empresas.
ms.openlocfilehash: d770e7be3b0b55855f1fee26a45d55260c3074cb
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487571"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a>Automatizar o licenciamento e a associação de grupo para seu ambiente de teste do Microsoft 365 para empresas

*Este Guia de Laboratório de Teste só pode ser usado para o Microsoft 365 para ambientes de teste corporativos.*

O licenciamento baseado em grupo atribui ou remove automaticamente licenças para uma conta de usuário com base na associação ao grupo. A associação de grupo dinâmico adiciona ou remove membros a um grupo com base em propriedades de conta de usuário, como **Departamento** ou **País.** Este artigo apresenta demonstrações sobre como adicionar e remover membros do grupo em seu ambiente de teste do Microsoft 365 para empresas.

Configurar o licenciamento automático e a associação de grupo dinâmica em seu ambiente de teste do Microsoft 365 para empresas envolve duas fases:

- [Fase 1: Criar seu ambiente de teste do Microsoft 365 para empresas](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Configurar e testar a associação dinâmica de grupo e o licenciamento automático](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 para empresas, vá para a Pilha de Guias de Laboratório de Teste do [Microsoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)para empresas.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: Criar seu ambiente de teste do Microsoft 365 para empresas

Se você quiser testar apenas o licenciamento automatizado e a associação de grupo de maneira leve com os requisitos mínimos, siga as instruções na configuração [de base leve.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Se você quiser testar o licenciamento automatizado e a associação de grupo em uma empresa simulada, siga as instruções na autenticação [de passagem.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> O teste automatizado de licenciamento e associação de grupo não exige o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta do AD DS (Serviços de Domínio Active Directory). Ele é fornecido aqui como uma opção para que você possa testar o licenciamento automatizado e a associação a um grupo e fazer testes com ele em um ambiente que representa uma organização típica.
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>Fase 2: Configurar e testar a associação dinâmica de grupo e o licenciamento automático

Primeiro, crie um novo grupo chamado Vendas e adicione uma regra  de associação de grupo dinâmica para que as contas de usuário com o Departamento definido como **Vendas** in joinam automaticamente no grupo Vendas.

1. Em uma instância privada do navegador da Internet, entre no Centro de administração do [Microsoft 365](https://admin.microsoft.com) com a conta de administrador global da sua assinatura de laboratório de teste do Microsoft 365 E5.
2. Em uma guia separada do navegador, vá para o portal do Azure em [https://portal.azure.com](https://portal.azure.com) .
3. No portal do Azure, insira **grupos na** caixa de pesquisa e selecione **Grupos.**
4. no painel **Todos os grupos,** selecione **Novo grupo.**
5. No **tipo de grupo,** selecione **Microsoft 365**.
6. In **Group name**, enter **Sales**.
7. No **tipo de associação,** selecione **Usuário dinâmico.**
8. Selecione **membros do usuário dinâmico.**
9. No painel **Regras de associação** dinâmica: 
   - Selecione a **propriedade de** departamento.
   - Selecione o **operador Equals.**
   - Na caixa **Valor,** insira **Vendas**.
10. Selecione **Salvar**.
11. Selecione **Criar**.

Em seguida, configure o grupo de vendas para que os membros sejam atribuídos automaticamente à licença do Microsoft 365 E5.

1. Selecione o **grupo vendas** e, em seguida, selecione **Licenças**.
2. No painel **Atualizar atribuições de licença,** selecione **Microsoft 365 E5** e, em seguida, **selecione Salvar**.
3. No navegador, feche a guia do portal do Azure.

Em seguida, teste a associação de grupo dinâmico e o licenciamento automático na conta do Usuário 4:

1. Na guia **Microsoft Office Home** no navegador, selecione **Admin**.
2. Na guia **Centro de administração do Microsoft 365,** selecione Usuários **ativos.**
3. Na página **Usuários ativos,** selecione a **conta do Usuário 4.**
4. No painel **Usuário 4,** selecione **Editar** para **licenças de produto.**
5. No painel **Licenças de** produto, desabilite a licença do **Microsoft 365 E5** e selecione **Salvar**  >  **Fechar.**
6. Nas propriedades da conta do Usuário 4, verifique se nenhuma licença de produto foi atribuída e se não há associações de grupo.
7. Para **informações de contato,** selecione **Editar**.
8. No painel **Editar informações de** contato, selecione Informações de **contato.**
9. In the **Department** box, enter **Sales**, and then select **Save**  >  **Close**.
10. Aguarde alguns minutos e selecione periodicamente o ícone Atualizar no canto superior direito do painel de contas do Usuário 4. 

No momento, você deverá ver o:

- **Propriedade de associações** de grupo atualizada com o **grupo** vendas.
- **Propriedade de licenças** de produto atualizada com a **licença do Microsoft 365 E5.**

Consulte estes artigos para implantar a associação de grupo dinâmica e o licenciamento automático na produção:

- [Licenciamento baseado em grupo no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [Grupos dinâmicos no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a>Próxima etapa

Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.

## <a name="see-also"></a>Confira também

[Mapa de identidade](identity-roadmap-microsoft-365.md)

[Guias do Laboratório de Teste do Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Documentação do Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365-enterprise/)
