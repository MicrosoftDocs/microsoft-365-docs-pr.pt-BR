---
title: Configuração de Pontuação de conformidade da Microsoft
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Saiba como entrar, configurar permissões e entender seu painel para a pontuação de conformidade da Microsoft, que ajuda a simplificar e automatizar avaliações de riscos.
ms.openlocfilehash: 7bff479d4cd7e3f200f7fc169eb351299eec8a39
ms.sourcegitcommit: 3eae8fe39cea912d29e211a1c9fd035d6b606f91
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2019
ms.locfileid: "38793645"
---
# <a name="microsoft-compliance-score-preview-setup"></a>Configuração da Pontuação de conformidade da Microsoft (versão prévia)

## <a name="before-you-begin"></a>Antes de começar

O administrador global do Microsoft 365 da sua organização provavelmente será o primeiro usuário a ter acesso à pontuação de conformidade. Recomendamos a entrada de administrador global e defina as permissões do usuário, conforme descrito abaixo, ao visitar a pontuação de conformidade pela primeira vez.

## <a name="sign-in"></a>Entrar

1. Vá para o [centro de conformidade da microsoft 365](https://compliance.microsoft.com/) e **entre** com sua conta de administrador global do Microsoft 365.
2. Selecione a **Pontuação de conformidade** no painel de navegação esquerdo. Em seguida, você deve ver seu [painel de Pontuação de conformidade com sua pontuação](#understand-the-compliance-score-dashboard).

## <a name="set-user-permissions-and-assign-roles"></a>Definir permissões de usuário e atribuir funções

A pontuação de conformidade usa um modelo de permissão RBAC (controle de acesso baseado em função). Somente os usuários atribuídos a uma função podem acessar a pontuação de conformidade, e as ações permitidas por cada usuário são restringidas por tipo de função.

### <a name="where-to-set-permissions"></a>Onde definir permissões

O administrador global da sua organização pode definir permissões de usuário no centro de conformidade da Microsoft 365 ou no Azure Active Directory (Azure AD). Depois que as funções são definidas em qualquer um desses locais, os usuários poderão acessar a pontuação de conformidade (bem como o Gerenciador de conformidade).

Observe que as funções do Gerenciador de conformidade existentes **não são** transferidas para a pontuação de conformidade.  Isso significa que, se você já tiver atribuído uma função ao gerente de conformidade, essa função não concederá acesso à pontuação de conformidade. Seu administrador global precisará definir permissões e uma função para você no centro de conformidade da Microsoft 365 ou no Azure AD para que você possa acessar a pontuação de conformidade.

### <a name="role-types"></a>Tipos de função

A tabela abaixo mostra como cada função do centro de conformidade da Microsoft 365 mapeia as funções do Gerenciador de conformidade existentes e as funções permitidas por cada função.


| O usuário pode: | Função centro de conformidade da Microsoft 365 | Função de gerente de conformidade | 
| :------------- | :-------------: | :------------: |
| **Ler mas não editar dados**| Leitor global do Azure AD  | Leitor global do Azure AD | 
| **Ler mas não editar dados**| Leitor de segurança | Leitor do Gerenciador de conformidade  | 
| **Editar dados**| Administrador de conformidade | Colaborador do gerente de conformidade | 
| **Editar resultados de teste**| Administrador de conformidade | Consultor do Gerenciador de conformidade | 
| **Gerenciar avaliações e dados de modelo e locatário**| Administrador de conformidade<br>Administrador de dados de conformidade<br>Administrador de segurança | Administrador do Gerenciador de conformidade | 
| **Atribuir usuários**| Administrador global | Administração do portal | 

> [!NOTE]
> Quando você passar da Pontuação de conformidade para o gerente de conformidade para concluir uma tarefa (por exemplo, para gerenciar avaliações), o navegador abrirá uma nova guia e uma caixa de diálogo será exibida. Na seção superior com o cabeçalho, "já é um cliente dos serviços de nuvem da Microsoft? Entre em sua conta, "selecione **entrar no** Gerenciador de conformidade do Access; Não será necessário inserir novamente suas credenciais.

### <a name="how-to-set-permissions-and-roles-in-the-microsoft-365-compliance-center"></a>Como definir permissões e funções no centro de conformidade da Microsoft 365

Para definir permissões no centro de conformidade da Microsoft 365:

1. Vá para o [centro de conformidade da Microsoft 365](https://compliance.microsoft.com) e entre com sua conta de administrador global.
2. Selecione **permissões** no painel de navegação à esquerda. A partir daqui, você pode exibir funções e atribuir permissões.

Para obter detalhes, leia [as funções e permissões no centro de conformidade da Microsoft 365](../security/office-365-security/microsoft-security-and-compliance.md#required-licenses-and-permissions).

## <a name="understand-the-compliance-score-dashboard"></a>Entender o painel de Pontuação de conformidade

O painel de Pontuação de conformidade foi projetado para fornecer uma visão geral da postura de conformidade atual.

![Pontuação de conformidade-painel](media/compliance-score-dashboard.png "Painel de Pontuação de conformidade")

### <a name="overall-compliance-score"></a>Pontuação de conformidade geral

Sua pontuação de conformidade, destacada em destaque na parte superior, mostra uma porcentagem com base nos pontos obtidos para a conclusão das ações de melhorias que lidam com os principais padrões e regulamentações de proteção de dados. 

Quando você chegar à pontuação de conformidade pela primeira vez, sua pontuação inicial se baseará na linha de base de proteção de dados interna da Microsoft 365 — um conjunto de controles que inclui normas e padrões comuns do setor. Como a pontuação de conformidade verifica seu sistema de soluções existentes da Microsoft 365, ela fornece uma avaliação inicial da postura de conformidade com base nas configurações de privacidade e segurança atualmente habilitadas pela sua organização.

À medida que você adiciona avaliações que são relevantes para sua organização, sua pontuação fica ainda mais significativa. Saiba mais sobre [como sua pontuação é calculada](compliance-score-methodology.md).

### <a name="key-improvement-actions"></a>Ações de melhoria de chave

Esta seção lista as principais ações de aprimoramento que você pode tomar agora para fazer o maior impacto positivo em sua pontuação geral de conformidade. Ele lista ações que não foram concluídas ou falharam com a avaliação com altos riscos.

### <a name="solutions-that-affect-your-score"></a>Soluções que afetam sua pontuação

Esta seção mostra quais soluções contêm ações com a maior oportunidade de afetar positivamente sua pontuação e quantas ações de melhorias pendentes você tem em cada solução.

### <a name="compliance-score-breakdown"></a>Divisão de Pontuação de conformidade

Esta seção oferece uma visão mais detalhada da sua pontuação de duas maneiras diferentes:

- **Categories**: mostra a porcentagem de sua pontuação geral nas categorias de proteção de dados, como "proteger informações" ou "gerenciar dispositivos".
- **Avaliações**: mostra a porcentagem do seu progresso no gerenciamento de Avaliações para padrões específicos de conformidade e proteção de dados, normas ou leis, como RGPD ou NIST 800-53.

### <a name="filtering-your-dashboard-view"></a>Filtrando o modo de exibição do painel

Você pode filtrar o modo de exibição do painel para ver apenas os itens relacionados a normas e padrões específicos, soluções, tipos de ações, grupos ou categorias de proteção de dados. Filtrar o modo de exibição dessa forma também filtrará a pontuação no painel, mostrando quantos pontos você alcançou do total de pontos possíveis com base nos critérios de filtro.

Para aplicar filtros:

1. Selecione **filtro** no lado superior direito do painel.
2. Selecione os critérios de filtro no painel **filtros** de submenu e selecione **aplicar**.

Você verá sua pontuação ajustada em tempo real e só verá as ações de aprimoramento, soluções e informações de divisão de pontuação que correspondem aos critérios de filtro. Se você sair da Pontuação de conformidade, sua exibição filtrada permanecerá quando você entrar novamente.

Para remover filtros:

- No cabeçalho **filtros aplicados** acima da Pontuação de conformidade, selecione o **X** ao lado do filtro individual que você deseja remover; ou
- Selecione **filtro** no lado superior direito do painel e, em seguida, selecione **limpar filtros**.

## <a name="next-step"></a>Próxima etapa

Visite [trabalhando com a pontuação de conformidade](working-with-compliance-score.md) para entender o fluxo de trabalho de como realizar ações para melhorar sua pontuação.