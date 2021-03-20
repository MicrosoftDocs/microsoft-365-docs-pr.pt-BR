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
description: Configure o licenciamento baseado em grupo e a associação dinâmica de grupo em seu ambiente de teste do Microsoft 365 para empresas.
ms.openlocfilehash: 26840e2884202a0fa9c4bb563f3d7c653482ef87
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905363"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a>Automatizar o licenciamento e a associação de grupo para seu ambiente de teste do Microsoft 365 para empresas

*Este Guia de Laboratório de Teste só pode ser usado para o Microsoft 365 para ambientes de teste corporativos.*

O licenciamento baseado em grupo atribui ou remove automaticamente licenças para uma conta de usuário com base na associação ao grupo. A associação de grupo dinâmica adiciona ou remove membros a um grupo com base nas propriedades da conta de usuário, como **Departamento** ou **País.** Este artigo explica as demonstrações de como adicionar e remover membros do grupo no ambiente de teste do Microsoft 365 para empresas.

Configurar o licenciamento automático e a associação dinâmica de grupo no ambiente de teste do Microsoft 365 para empresas envolve duas fases:

- [Fase 1: criar seu ambiente de teste do Microsoft 365 para empresas](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Configurar e testar a associação dinâmica do grupo e o licenciamento automático](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Para um mapa visual de todos os artigos na pilha guia de laboratório de teste do Microsoft 365 para empresas, vá para [o Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: criar seu ambiente de teste do Microsoft 365 para empresas

Se você quiser testar apenas o licenciamento automatizado e a associação de grupo de forma leve com os requisitos mínimos, siga as instruções em [Configuração base leve.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Se você quiser testar o licenciamento automatizado e a associação de grupo em uma empresa simulada, siga as instruções em [Autenticação passagem.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> Testar o licenciamento automatizado e a associação ao grupo não exige o ambiente de teste empresarial simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos Serviços de Domínio do Active Directory (AD DS). Ele é fornecido aqui como uma opção para que você possa testar o licenciamento automatizado e a associação ao grupo e experimentá-lo em um ambiente que representa uma organização típica.
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>Fase 2: Configurar e testar a associação dinâmica do grupo e o licenciamento automático

Primeiro, crie um novo grupo chamado Vendas e adicione uma regra dinâmica de associação de grupo para que as contas de usuário com o **Departamento** definidas como **Vendas** insuem automaticamente no grupo Vendas.

1. Em uma instância privada do navegador da Internet, entre no Centro de administração do [Microsoft 365](https://admin.microsoft.com) com a conta de administrador global da sua assinatura do laboratório de teste do Microsoft 365 E5.
2. Em uma guia separada do navegador, vá para o portal do Azure em [https://portal.azure.com](https://portal.azure.com) .
3. No portal do Azure, insira **grupos** na caixa de pesquisa e selecione **Grupos**.
4. no painel **Todos os grupos,** selecione **Novo grupo**.
5. Em **Tipo de grupo,** selecione **Microsoft 365**.
6. Em **Nome do grupo,** insira **Vendas**.
7. Em **Tipo de associação,** selecione **Usuário dinâmico**.
8. Selecione **Membros do usuário dinâmico**.
9. No painel **Regras de associação** dinâmicas: 
   - Selecione a **propriedade department.**
   - Selecione o **operador Equals.**
   - Na caixa **Valor,** digite **Vendas**.
10. Selecione **Salvar**.
11. Selecione **Criar**.

Em seguida, configure o grupo Vendas para que os membros sejam atribuídos automaticamente à licença do Microsoft 365 E5.

1. Selecione o **grupo Vendas** e selecione **Licenças**.
2. No painel **Atualizar atribuições de** licença, selecione **Microsoft 365 E5** e selecione **Salvar**.
3. No navegador, feche a guia portal do Azure.

Em seguida, teste a associação dinâmica do grupo e o licenciamento automático na conta usuário 4:

1. Na guia **Microsoft Office Página** 1 do navegador, selecione **Admin**.
2. Na guia Centro de administração **do Microsoft 365,** selecione **Usuários ativos**.
3. Na página **Usuários ativos,** selecione a **conta Usuário 4.**
4. No painel **Usuário 4,** selecione **Editar** para **licenças de produto.**
5. No painel **Licenças de** produto, desabilite a licença do **Microsoft 365 E5** e selecione **Salvar**  >  **Fechar.**
6. Nas propriedades da conta Usuário 4, verifique se nenhuma licença de produto foi atribuída e se não há associações de grupo.
7. Para **obter informações de contato,** selecione **Editar**.
8. No painel **Editar informações de** contato, selecione Informações de **contato**.
9. Na caixa **Departamento,** digite **Vendas** e, em seguida, selecione **Salvar**  >  **Fechar**.
10. Aguarde alguns minutos e selecione periodicamente o ícone Atualizar no canto superior direito do painel de contas Usuário 4. 

Com o tempo, você deve ver o:

- **Propriedade de associações de** grupo atualizada com o **grupo Vendas.**
- **Propriedade de licenças** de produto atualizada com a **licença do Microsoft 365 E5.**

Consulte estes artigos para implantar a associação dinâmica de grupo e o licenciamento automático na produção:

- [Licenciamento baseado em grupo no Azure Active Directory](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [Grupos dinâmicos no Azure Active Directory](/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a>Próxima etapa

Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.

## <a name="see-also"></a>Confira também

[Roteiro de identidade](identity-roadmap-microsoft-365.md)

[Guias do Laboratório de Teste do Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Documentação do Microsoft 365 para empresas](/microsoft-365-enterprise/)