---
title: Teams para dados altamente regulamentados
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Crie um site de equipe seguro para armazenar seus arquivos mais valiosos e confidenciais.
ms.openlocfilehash: d917e14719744dad8a681e15a8547655c3a0457f
ms.sourcegitcommit: d95aab99d7827dbb9248280044748ca05ebec786
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2019
ms.locfileid: "37657798"
---
# <a name="teams-for-highly-regulated-data"></a>Teams para dados altamente regulamentados

Este artigo fornece recomendações e passo a passo para configurar uma equipe privada no Microsoft Teams que bloqueia o acesso aos recursos do Teams, como chats, reuniões e arquivos, somente para membros e proprietários do grupo do Office 365 da equipe. 

Além do acesso privado baseado no grupo do Office 365, este artigo descreve como configurar o site de equipe particular e subjacente do SharePoint, que você pode na seção de **Arquivos** de um canal de equipe e obter a segurança adicional necessária para armazenar dados altamente regulamentados. Neste site de equipe do SharePoint, você pode armazenar e colaborar em arquivos, páginas, um calendário compartilhado, tarefas, um bloco de anotações e listas.

Os elementos de configuração de uma equipe para dados altamente regulamentados são:

- Uma equipe privada com um grupo correspondente do Office 365 que tem contas de usuário de proprietário e membro.
- Segurança adicional no site subjacente do SharePoint para a equipe que:
  - Impede que membros do site concedam acesso a outras pessoas.
  - Impede que não membros do site solicitem acesso a ele.
- Um rótulo de retenção do Office 365 para o site do SharePoint subjacente que é aplicado automaticamente a novos arquivos no site como uma maneira padrão de definir políticas de retenção.
- Uma política de Prevenção contra Perda de Dados (DLP) que usa o rótulo de retenção e impede que os usuários compartilhem ou enviem arquivos para fora da organização.
- Um rótulo de confidencialidade do Office 365 de ou sub-rótulo de um rótulo altamente regulamentado com criptografia habilitada e permissões de Coautor para o grupo da equipe do Office 365. Os usuários aplicam o rótulo ou sub-rótulo aos arquivos armazenados na seção de **Arquivos** da equipe na opção da barra de menus Confidencialidade do Word, Excel e PowerPoint.

Esta é a configuração resultante com um rótulo de confidencialidade.

![A configuração segura do cenário de equipe](./media/secure-teams-highly-regulated-data-scenario/secure-team-final.png)
 
## <a name="phase-1-configure-a-team-for-highly-regulated-data"></a>Fase 1: Configurar uma equipe para dados altamente regulamentados

A configuração de ponta a ponta consiste nas seguintes etapas:

1. Configurações de identidade e acesso a dispositivo.
2. Criação de uma equipe privada.
3. Configuração de site do SharePoint subjacente para segurança adicional.
4. Criação de um rótulo de retenção e uma política DLP.
5. Criação de rótulo ou sub-rótulo de rótulo altamente regulamentado.

### <a name="step-1-configure-identity-and-device-access"></a>Etapa 1: configurações de identidade e acesso a dispositivo.

Para proteger o acesso à equipe e ao site do SharePoint subjacente, assegure-se de ter configurado as[políticas de identidade e acesso a dispositivo](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies) e as [políticas de acesso do SharePoint Online](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies) recomendadas.

### <a name="step-2-create-a-private-team"></a>Etapa 2: criação de uma equipe privada.

Use [essas instruções](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b) para criar uma equipe privada.

Ao criar uma equipe privada, estas são as permissões padrão:

- O grupo do Office 365 para a equipe (o Grupo da Equipe) tem proprietários e membros do grupo
- Do site do SharePoint subjacente para a equipe (o Site da Equipe):
  - Os Administradores de Conjunto de Sites estão configurados para os proprietários de Grupo de Equipe
  - Para o Site de Equipe: 
    - O grupo do SharePoint de Proprietários de Site de Equipe, com o nível de permissão Controle Total, está definido para os proprietários de Grupo de Equipe
    - O grupo do SharePoint de Proprietários de Site de Equipe, com o nível de permissão Editar, está definido para os proprietários de Grupo de Equipe
    - O grupo do SharePoint de Visitantes de Site de Equipe, com o nível de permissão de Leitura, não tem grupos ou contas de usuários

Estas são as permissões padrão para o Site de Equipe.

![As permissões padrão de um Site de Equipe](./media/secure-teams-highly-regulated-data-scenario/secure-team-default-site-permissions.png)
 
>[!Note]
>Se você visualizar o grupo do SharePoint de Proprietários de \<nome da equipe> para o nível de permissão Editar, ele não exibirá os Proprietários de \<nome da equipe>.
>

As permissões resultantes permitem:

- Proprietários de Grupo de Equipe para administrar o site e ter controle total sobre o conteúdo do site.
- Membros de Grupo de Equipe para criar e editar arquivos no site. 

A manutenção de permissões é igual para manutenção de proprietário e membro de equipe.

Esta é a configuração resultante até o momento.

![Etapa 2 da configuração segura do cenário de equipe](./media/secure-teams-highly-regulated-data-scenario/secure-team-step2.png)
 
### <a name="step-3-configure-the-underlying-sharepoint-site-for-additional-security"></a>Etapa 3: Configuração do site subjacente do SharePoint para segurança adicional

No Site da Equipe, defina estas configurações de permissão.

1. Na barra de ferramentas, clique no ícone de configurações e, em seguida, clique em **Permissões do site**.
2. No painel **Permissões do site**, em **Configurações de Compartilhamento**, clique em **Alterar configurações de compartilhamento**.
3. Em **Permissões de compartilhamento**, **Somente proprietários do site podem compartilhar arquivos, pastas e o site**.
4. Desabilite **Permitir solicitações de acesso** e clique em **Salvar**.

Com essas configurações, a capacidade de membros do Grupo de Equipe compartilharem o Site da Equipe com outros membros ou para que não membros possam solicitar acesso ao site é desabilitada.

Esta é a configuração resultante até o momento.

![Etapa 3 da configuração segura do cenário de equipe](./media/secure-teams-highly-regulated-data-scenario/secure-team-step3.png)

 
### <a name="step-4-create-a-retention-label-and-dlp-policy"></a>Etapa 4: Criação de um rótulo de retenção e uma política DLP.

Use [estas instruções](https://docs.microsoft.com/microsoft-365/compliance/protect-sharepoint-online-files-with-office-365-labels-and-dlp) para:

1. Crie e publique um rótulo de retenção para dados altamente regulamentados (se necessário).
2. Configure o Site de Equipe para o rótulo de retenção criado na etapa 1.
3. Crie uma política DLP para dados altamente regulamentados que usam o rótulo de retenção criado na etapa 2 e impede que os usuários enviem arquivos para fora da organização. Você também pode configurar a política para requisitos adicionais, como os de regulamentos do setor financeiro e de saúde, com base nos [modelos de política DLP](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies#dlp-policy-templates).

Esta é a configuração resultante até o momento.

![Etapa 4 da configuração segura do cenário de equipe](./media/secure-teams-highly-regulated-data-scenario/secure-team-step4.png)
 
### <a name="step-5-create-the-label-or-a-sublabel-of-the-highly-regulated-label"></a>Etapa 5: criação de rótulo ou sub-rótulo de rótulo altamente regulamentado.

Ao contrário de um rótulo de confidencialidade para dados altamente regulamentados que qualquer pessoa pode aplicar a qualquer arquivo, uma equipe segura precisa de seu próprio rótulo ou sub-rótulo, assim os arquivos atribuídos:

- São criptografados e a criptografia acompanha o arquivo.
- Contêm permissões personalizadas para que somente os membros do grupo de sites possam abri-lo.

Para atingir esse nível adicional de segurança para os arquivos armazenados no Site de Equipe, você deve configurar um novo rótulo de confidencialidade, que é um sub-rótulo do rótulo geral para arquivos altamente regulamentados. Somente os membros do Grupo de Equipe vão vê-los na lista de rótulos.

Use um rótulo de confidencialidade quando precisar de um pequeno número de rótulos para uso global e equipes privadas individuais. Use um sub-rótulo de confidencialidade quando houver um grande número de rótulos ou quiser organizar rótulos para equipes privadas sob o rótulo altamente regulamentado.

[Use estas instruçõess](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) para configurar um rótulo separado ou um sub-rótulo com as seguintes configurações:

- O nome do rótulo contém o nome da equipe
- A criptografia está ativada
- O Grupo de Equipe tem permissões de Coautoria

Esta é a configuração resultante com o novo rótulo.

![Etapa 5 da configuração segura do cenário de equipe](./media/secure-teams-highly-regulated-data-scenario/secure-team-final.png)

Esta é a relação entre o rótulo de confidencialidade e o Grupo de Equipe.

![Relação entre o Grupo de Equipe e as permissões de rótulo](./media/secure-teams-highly-regulated-data-scenario/secure-team-label-permissions.png)


>[!Note]
>Se você configurar o rótulo ou sub-rótulo de confidencialidade para permissões definidas pelo usuário ou com uma data de validade, não poderá abrir o arquivo no Teams ou no SharePoint. Você deve usar um aplicativo do Office.
>

### <a name="custom-permissions"></a>Permissões personalizadas

Você também pode configurar permissões de site do SharePoint personalizadas para o Site da Equipe e, se necessário, seu rótulo de confidencialidade correspondente. Veja dois exemplos.

#### <a name="example-1-delegating-sharepoint-site-administration"></a>Exemplo 1: delegar a administração de sites do SharePoint

Se o proprietário da equipe não tiver experiência em administração do SharePoint ou desejar delegar a administração do Site de Equipe, ele poderá adicionar a conta de usuário de um administrador do SharePoint à lista de proprietários da equipe. No entanto, o administrador do SharePoint teria acesso total à equipe e a todos os seus recursos e poderia abrir um arquivo com o rótulo de confidencialidade aplicado. 

Para evitar essa concessão excessiva de privilégios, adicione a conta de usuário do administrador do SharePoint ao grupo de Proprietários do SharePoint de Site de Equipe nas configurações de permissões avançadas do site. O administrador do SharePoint pode administrar o site, mas não poderá acessar a equipe e nenhum de seus recursos ou abrir os arquivos com o rótulo de confidencialidade atribuído.

#### <a name="example-2-allowing-view-only-access-to-labeled-files"></a>Exemplo 2: permitir acesso somente de exibição a arquivos rotulados

Se algum membro da equipe precisar visualizar somente o conteúdo dos arquivos rotulados no Site da Equipe, adicione suas contas de usuário individuais ao:

- Grupo do SharePoint de Visitantes de \<nome da equipe>, que por padrão tem o nível de permissão de Leitura. 
- O rótulo de confidencialidade com as permissões de Visualizador.

Estas são as permissões resultantes do rótulo.

![Exemplo de permissões personalizadas para exibir arquivos rotulados](./media/secure-teams-highly-regulated-data-scenario/secure-team-custom-view-permissions.png)
 
Os visitantes do site poderão acessar o Site da Equipe diretamente e visualizar o conteúdo dos arquivos aos quais o sub-rótulo foi aplicado. No entanto, como eles não são membros do Grupo de Equipe, não poderão acessar a equipe ou nenhum de seus recursos.


## <a name="phase-2-drive-user-adoption-for-team-members"></a>Fase 2: Impulsionar a adoção do usuário para membros da equipe

Com a equipe no local, é hora de impulsionar a adoção dessa equipe e sua segurança adicional aos membros da equipe.

### <a name="step-1-train-your-users"></a>Etapa 1: treinar os usuários

Os membros do Grupo de Equipe podem acessar a equipe e todos os seus recursos, incluindo chats, reuniões e outros aplicativos. Ao trabalhar com arquivos da seção de **Arquivos** de um canal, os membros do Grupo de Equipe devem atribuir o rótulo ou sub-rótulo de confidencialidade aos arquivos criados para a equipe segura. Veja um exemplo.

![Exemplo de um rótulo aplicado a um arquivo em uma equipe segura](./media/secure-teams-highly-regulated-data-scenario/secure-team-label-applied.png)
 
Quando o rótulo for aplicado ao arquivo, ele será protegido. Os membros do Grupo de Equipe podem abri-lo no Teams e colaborar em tempo real. Ele é criptografado e inclui as permissões de Coautor definidas para os membros do Grupo de Equipe. Se o arquivo sair do site e for encaminhado para um usuário mal-intencionado, eles terão que fornecer as credenciais de uma conta de usuário que seja membro do Grupo de Equipe para abrir o arquivo e exibir seu conteúdo. 

Treine os membros da sua equipe:

- Sobre a importância de usar a nova equipe para bate-papos, reuniões, arquivos e outros recursos do Site da Equipe e as consequências de um vazamento de dados altamente regulamentados, como ramificações legais, multas regulatórias, ransomware ou perda de vantagem competitiva.
- Como acessar a equipe.
- Como criar novos arquivos no site e carregar novos arquivos armazenados localmente.
- Como a política DLP bloqueia o compartilhamento de arquivos externamente por parte do usuário.
- Como rotular arquivos com o rótulo personalizado ou sub-rótulo da equipe.
- Como o rótulo ou o sub-rótulo protege os arquivos, mesmo quando vazam do site.

Esse treinamento deve incluir exercícios práticos para que os membros da sua equipe possam experimentar esses recursos e seus resultados.

### <a name="step-2-conduct-periodic-reviews-of-usage-and-address-team-member-feedback"></a>Etapa 2: Realize análises de uso periódicas e gerencie os comentários dos membros da equipe

Nas semanas após o treinamento:

- Aborde rapidamente os comentários dos membros da equipe e ajuste as políticas e configurações.
- Analise o uso da equipe e compare-o com as expectativas de uso.
- Verifique se os arquivos altamente regulamentados foram rotulados corretamente com o rótulo ou sub-rótulo de confidencialidade personalizado.

  Você pode verificar quais arquivos têm um rótulo atribuído exibindo uma pasta no SharePoint e adicionando a coluna **Confidencialidade** por meio da opção **Mostrar/ocultar colunas** da **coluna Adicionar**.

Repita o treinamento dos usuários conforme necessário.

## <a name="see-also"></a>Confira também

[Sites do SharePoint para dados altamente regulamentados](teams-sharepoint-online-sites-highly-regulated-data.md)

[Cargas de trabalho e cenários do Microsoft 365 Enterprise](deploy-workloads.md)

[Biblioteca de produtividade do Microsoft 365](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)

[Guia de implantação](deploy-microsoft-365-enterprise.md)
