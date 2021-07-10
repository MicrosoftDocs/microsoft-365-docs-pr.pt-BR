---
title: Saiba mais sobre os comentários da Microsoft para sua organização
f1.keywords:
- NOCSH
ms.author: Kwekua
author: Kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Saiba mais sobre comentários que seus usuários podem enviar para a Microsoft sobre produtos microsoft.
ms.openlocfilehash: 7b8798847559e84a6ea10079aab010a08d8eaa42
ms.sourcegitcommit: 7dc3b4dec05299abb4290a6e3d1ebe0fdc622ed7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/10/2021
ms.locfileid: "53363926"
---
# <a name="learn-about-microsoft-feedback-for-your-organization"></a>Saiba mais sobre os comentários da Microsoft para sua organização

O feedback do usuário é um sinal crítico para a Microsoft entender as experiências do usuário com produtos da Microsoft. A Microsoft valoriza as opiniões dos usuários. Os comentários dos usuários vão diretamente para nossos engenheiros e nos ajudam a moldar o futuro dos produtos e serviços da Microsoft para todos os nossos usuários.  
Neste tópico, você encontrará informações sobre quais tipos de comentários existem, como coletamos, o que coletamos e como lidamos com os dados.

Como administrador, você pode gerenciar o sinal de feedback para sua organização. Estamos introduzindo um novo conjunto de configurações de política para ajudá-lo a gerenciar o conjunto de comentários do usuário dentro dos aplicativos Microsoft 365 para sua organização. Essas configurações de política ajudarão você a direcionar Azure Active Directory grupos e configurar a experiência de coleta de comentários para sua organização. Os comentários dos usuários vão diretamente para nossos engenheiros e nos ajudam a moldar o futuro dos produtos e serviços da Microsoft para todos os nossos usuários. Você pode saber mais sobre essas configurações de política, a quais aplicativos eles se aplicam e práticas recomendadas em [Gerenciar comentários da Microsoft para sua organização.](../manage/manage-feedback-ms-org.md)

## <a name="feedback-types"></a>Tipos de comentários

### <a name="in-product-feedback"></a>Comentários no produto

Se os usuários estão usando um dos aplicativos da Microsoft e desejam fornecer comentários, há várias maneiras de fazer isso de dentro dos aplicativos que estão usando. Os usuários podem usar essas diferentes maneiras de compartilhar comentários de produtos e recursos conosco. Uma das maneiras mais comuns de compartilhar comentários por meio de aplicativos da Microsoft está no menu Ajuda. Selecionar **Comentários** de Ajuda na maioria dos aplicativos microsoft inicia uma página de comentários, que permite que os usuários  >   enviem comentários para a Microsoft.

#### <a name="in-product-feedback-examples"></a>Exemplos de feedback no produto

:::image type="content" source="../../media/In-appfeedbackbackstage.png" alt-text="Captura de tela: Exemplo de feedback no produto":::
:::image type="content" source="../../media/In-appfeedbackwindows.png" alt-text="Captura de tela: Windows exemplo de feedback no produto":::
:::image type="content" source="../../media/TeamsIn-appFeedback.png" alt-text="Captura de tela: Teams exemplo de feedback no produto":::

### <a name="in-product-surveys"></a>Pesquisas no produto

Os usuários também podem taxar sua experiência e fornecer informações adicionais sobre sua experiência por meio de prompts de pesquisa iniciados pelo sistema. Esses prompts ocorrem dentro do Microsoft 365 de vez em quando. Quando solicitado, os usuários podem escolher se querem fornecer comentários. Os prompts de pesquisa normalmente aparecem na parte inferior direita do aplicativo. Se o usuário decidir fornecer comentários, descartar o prompt ou permitir que o prompt desapareça por conta própria, esse usuário não verá a pesquisa novamente por algum tempo. A Microsoft também aproveita um processo de governança para limitar o número dessas pesquisas iniciadas pelo sistema.  A intenção da governança é garantir que os usuários não sejam sobrecarregados pelo número de prompts de pesquisa.

:::image type="content" source="../../media/feedback-love.png" alt-text="Captura de tela: Exemplo de solicitação de feedback no produto":::

:::image type="content" source="../../media/feedback-excel.png" alt-text="Captura de tela: Exemplo de solicitação de feedback no produto":::

## <a name="what-kind-of-feedback-is-best"></a>Que tipo de comentários é melhor?

Comentários detalhados e ativas são vitais para fazer alterações e melhorias nos produtos Microsoft. Se os usuários têm problemas ou sugestões de como podemos melhorar, queremos ouvi-los. A seguir estão algumas dicas e exemplos sobre comentários ativas enviados à Microsoft.

- **Título conciso e descritivo**   Títulos descritivos e específicos nos ajudam a entender o problema relatado. Exemplo: Excel **lista de** arquivos recentes não inclui arquivos OneDrive adicionados recentemente.
- **Foco em um problema de cada vez**   Forneça comentários para um problema ou recomendação de um item por vez. Isso garante que os logs e os dados corretos sejam recebidos com cada envio e possam ser atribuídos para acompanhamento. Se você tiver mais de um problema, envie uma nova solicitação de comentários para cada problema. Isso nos ajuda a identificar o volume de comentários que estamos recebendo em um problema específico.
- **Gravar detalhes na caixa Descrição**   As informações sobre seu dispositivo, sistema operacional e aplicativos são incluídas automaticamente em cada feedback relatado. Adicione informações adicionais sobre um problema que você acha importante. Por exemplo, inclua etapas detalhadas para reproduzir o problema.

## <a name="how-microsoft-uses-feedback"></a>Como a Microsoft usa comentários

A Microsoft usa comentários para melhorar os produtos da Microsoft. Recebemos comentários do usuário na forma de perguntas, problemas, elogios e sugestões. Asseguramos que esses comentários sejam voltados para as equipes apropriadas, que usam comentários para identificar, priorizar e fazer melhorias nos produtos microsoft. Os comentários são essenciais para que nossas equipes de produtos entendam as experiências do usuário e influenciam diretamente a prioridade de correções e melhorias.

### <a name="what-do-we-collect"></a>O que coletamos?

Quando um usuário envia comentários, as informações do aplicativo geralmente são coletadas juntamente com classificações de aplicativos e descrições de comentários.  Se você habilitar a política, podemos permitir que os usuários enviem capturas de tela e logs para nos ajudar a depurar e resolver problemas que o usuário pode estar executando. Aqui estão os itens mais comuns coletados ou calculados.

- **Comentários**   O usuário enviou comentários no idioma original.
- **Aplicativo**   Produto Da Microsoft, nós temos os comentários.
- **Data enviada**   Data e hora que nós temos os comentários.
- **ID do usuário**   Id do Azure Active directory ou endereço de email do usuário autenticado enviando os comentários. Comentários anônimos são permitidos, mas não mostrados neste modo de exibição.
- **Email do Usuário**   Se o usuário estiver de acordo com o fornecimento de seu endereço de email para acompanhamento.
- **Idioma ou idioma do comentário**   Idioma original em que o comentário foi enviado.
- **Tipo de comentários**   Comentários de pesquisa ou comentários no aplicativo.
- **Perguntas de pesquisa**   Perguntas que fizemos ao usuário durante a pesquisa.
- **Respostas de pesquisa**   Respostas do usuário às perguntas de pesquisa.
- **Canal**   Canal do produto Microsoft relacionado aos comentários.
- **Com build de aplicativo**   Número de com build do produto Microsoft que foi capturado no envio.
- **Idioma do aplicativo**   Idioma do produto Microsoft que foi capturado no envio.
- **Anexos**   Foram quaisquer anexos (ou seja, capturas de tela, arquivos) coletados como parte dos comentários? (Sim/Não).
- **TenantId**   Se os comentários são enviados de uma conta Azure Active Directory, que TenantId foi associado.

## <a name="how-can-i-see-my-users-feedback"></a>Como posso ver os comentários do meu usuário?

Para atender às obrigações legais da Microsoft para os clientes, estamos trabalhando em uma nova experiência no Centro de administração do Microsoft 365 que permite que os administradores excluam, excluam e exportem os dados de feedback para suas organizações. Como parte da responsabilidade do controlador de dados, os clientes são donos de todos os dados de comentários do usuário e essa funcionalidade ajudará os administradores a fornecer transparência direta nas experiências dos usuários com produtos Microsoft 365 e permitir que os dados de comentários do usuário sejam fornecidos como parte de qualquer Solicitação de Titulares de Dados. Os administradores globais e os administradores de dados de conformidade terão a capacidade de exibir, exportar e excluir comentários do usuário. Todos os outros administradores, bem como leitores, poderão exibir e exportar dados de comentários, mas não poderão executar tarefas relacionadas à conformidade ou ver informações sobre quem postou os comentários (como nome de usuário, email ou nome do dispositivo). Para acessar os dados de comentários da sua organização, entre no Centro de administração do Microsoft 365 e personalize a navegação para mostrar o nó de saúde. Acesse essa experiência selecionando **Comentários do Produto** no nó Saúde.

## <a name="data-handling-and-privacy"></a>Tratamento de dados e privacidade

Entendemos que, ao usar nossos serviços de nuvem, você está nos confiando um dos seus ativos mais valiosos: seus dados. Asseguramos que os comentários recebidos sejam armazenados e manipulados em regras de governança da Microsoft e que ele só possa ser acessado para usos aprovados. Não usamos seu email, chat, arquivos ou outro conteúdo pessoal para direcionar anúncios para você. Quando coletamos dados, os usamos para melhorar suas experiências.

Para saber mais sobre como protegemos a privacidade e a confidencialidade de seus dados e como garantimos que eles serão usados apenas de forma consistente com suas expectativas, revise nossos princípios de privacidade na Central de Confiabilidade da [Microsoft.](https://www.microsoft.com/trust-center/privacy)
