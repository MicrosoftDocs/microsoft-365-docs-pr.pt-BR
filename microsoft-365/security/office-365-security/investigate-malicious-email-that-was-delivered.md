---
title: Investigar emails mal-intencionados que foram entregues no Office 365, encontrar e investigar emails mal-intencionados
keywords: TIMailData-Inline, incidente de segurança, incidente, ATP PowerShell, malware de email, usuários comprometidos, phishing de email, malware de email, ler os títulos de email, ler os títulos, abrir os títulos de email, ações especiais
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 12/16/2020
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
ms.collection:
- M365-security-compliance
description: Saiba como usar os recursos de investigação e resposta de ameaças para encontrar e investigar emails mal-intencionados.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b36e16f5351ab30ac8150fbc3e87feb9ca4a6453
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286628"
---
# <a name="investigate-malicious-email-that-was-delivered-in-office-365"></a>Investigar emails mal-intencionados que foram entregues no Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**

- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

[O Microsoft Defender para Office 365](office-365-atp.md) permite investigar atividades que colocam as pessoas em sua organização em risco e tomar medidas para proteger sua organização. Por exemplo, se você faz parte da equipe de segurança da sua organização, pode encontrar e investigar mensagens de email suspeitas que foram entregues. Você pode fazer isso usando o [Explorador de Ameaças (ou detecções em tempo real).](threat-explorer.md)

> [!NOTE]
> Ir para o artigo de correção [aqui](remediate-malicious-email-delivered-office-365.md).

## <a name="before-you-begin"></a>Antes de começar

Verifique se os seguintes requisitos são atendidos:

- Sua organização tem [o Microsoft Defender para Office 365](office-365-atp.md) e as [licenças são atribuídas aos usuários.](../../admin/manage/assign-licenses-to-users.md)

- [o log de](../../compliance/turn-audit-log-search-on-or-off.md) auditoria está ligado para sua organização.

- Sua organização tem políticas definidas para anti-spam, anti-malware, anti-phishing e assim por diante. Veja [Proteger contra ameaças no Office 365.](protect-against-threats.md)

- Você é um administrador global ou tem a função Administrador de Segurança ou Pesquisa e Limpeza atribuída no Centro de Conformidade & Segurança. Consulte [Permissões no Centro de Conformidade e & Segurança.](permissions-in-the-security-and-compliance-center.md) Para algumas ações, você também deve ter uma nova função de visualização atribuída.

### <a name="preview-role-permissions"></a>Permissões de função de visualização

Para executar determinadas ações, como exibir os títulos das mensagens ou baixar o conteúdo da mensagem de email, você deve ter uma nova função chamada *Visualização* adicionada a outro grupo de funções apropriado. A tabela a seguir esclarece as funções e permissões necessárias.

****

|Atividade|Grupo de função|Função de visualização necessária?|
|---|---|---|
|Usar o Explorador de Ameaças (e detecções em tempo real) para analisar ameaças |Administrador Global <p> Administrador de Segurança <p> Leitor de segurança|Não|
|Use o Explorador de Ameaças (e detecções em tempo real) para exibir os headers de mensagens de email, bem como visualizar e baixar mensagens de email em quarentena|Administrador Global <p> Administrador de Segurança <p> Leitor de segurança|Não|
|Use o Explorador de Ameaças para exibir os headers, visualizar emails (somente na página de entidade de email) e baixar mensagens de email entregues às caixas de correio|Administrador Global <p> Administrador de Segurança <p> Leitor de segurança <p> Visualização|Sim|
|

> [!NOTE]
> *A* visualização é uma função e não um grupo de funções; a função De visualização deve ser adicionada a um grupo de função existente para o Office 365 (em [https://protection.office.com](https://protection.office.com) ). Vá para **Permissões e** edite um grupo de função existente ou adicione um novo grupo de funções com a função **Visualização** atribuída.
> A função administrador global é atribuída ao centro de administração do Microsoft 365 ( ), e as funções administrador de segurança e leitor de segurança são atribuídas no Centro de conformidade de segurança <https://admin.microsoft.com> & ( <https://protection.office.com> ). Para saber mais sobre funções e permissões, consulte Permissões no Centro de Conformidade e [& Segurança.](permissions-in-the-security-and-compliance-center.md)

Entendemos que a visualização e o download de emails são atividades confidenciais e, portanto, a auditoria está habilitada para isso. Depois que um administrador executa essas atividades em emails, os logs de auditoria são gerados para o mesmo e podem ser vistos no Centro de Conformidade e Segurança do Office 36 & 5 ( [https://protection.office.com](https://protection.office.com) ). Vá para a **pesquisa**  >  **de log de Auditoria de** Pesquisa e filtre o nome do administrador na seção Pesquisa. Os resultados filtrados mostrarão a atividade **AdminMailAccess**. Selecione uma linha para exibir detalhes na **seção Mais informações** sobre email visualizado ou baixado.

## <a name="find-suspicious-email-that-was-delivered"></a>Encontrar emails suspeitos que foram entregues

O Explorador de Ameaças é um relatório poderoso que pode atender a várias finalidades, como localizar e excluir mensagens, identificar o endereço IP de um remetente de email mal-intencionado ou iniciar um incidente para investigação posterior. O procedimento a seguir se concentra no uso do Explorer para encontrar e excluir emails mal-intencionados das caixas de correio do destinatário.

> [!NOTE]
> As pesquisas padrão no Explorer atualmente não incluem itens em Destaque.  Isso se aplica a todos os visualizações, por exemplo, exibições de malware ou phishing. Para incluir itens em Destaque, você precisa adicionar um conjunto de ações **de** entrega para incluir **Removido pela ZAP.** Se você incluir todas as opções, você verá todos os resultados da ação de entrega, incluindo itens em destaque.

1. **Navegue até o Explorador de** Ameaças: acesse e entre usando sua conta de trabalho ou de estudante do Office <https://protection.office.com> 365. Isso leva você para o Centro de Conformidade & segurança.

2. No início rápido de navegação à esquerda, escolha **Explorador de gerenciamento de** \> **ameaças.**

    ![Explorer com campos Ação de Entrega e Local de Entrega.](../../media/ThreatExFields.PNG)

    Você pode notar a nova **coluna Ações** especiais. Esse recurso destina-se a dizer aos administradores o resultado do processamento de um email. A **coluna Ações especiais** pode ser acessada no mesmo local que a ação de **entrega** e o local **de entrega.** Ações especiais podem ser atualizadas no final da linha do tempo de email do Explorador de Ameaças, que é um novo recurso destinado a melhorar a experiência de busca para administradores.

3. **Exibições no Explorador de Ameaças:** no menu **Exibir,** escolha **Todos os emails.**

    ![Menu Exibir Explorador de Ameaças e Email - Malware, Phishing, Envios e Todas as opções de Email, além de Conteúdo - Malware.](../../media/tp-InvestigateMalEmail-viewmenu.png)

    O *modo* de exibição malware é atualmente o padrão e captura emails em que uma ameaça de malware é detectada. O *modo de* exibição phishing opera da mesma maneira, para phishing.

    No entanto, *Todas as exibições* de email listam todos os emails recebidos pela organização, independentemente de as ameaças ter sido detectadas ou não. Como você pode imaginar, isso é uma grande quantidade de dados, e é por isso que essa exibição mostra um espaço reservado que solicita a aplicação de um filtro. (Essa exibição só está disponível para clientes do Defender para Office 365 P2.)

    *A exibição* De envios mostra todos os emails enviados pelo administrador ou usuário que foram relatados à Microsoft.

4. **Pesquisar e filtrar no Explorador de Ameaças:** os filtros aparecem na parte superior da página na barra de pesquisa para ajudar os administradores em suas investigações. Observe que vários filtros podem ser aplicados ao mesmo tempo e vários valores separados por vírgula adicionados a um filtro para restringir a pesquisa. Lembre-se:

    - Os filtros fazem correspondência exata na maioria das condições de filtro.
    - O filtro de assunto usa uma consulta CONTAINS.
    - Os filtros de URL funcionam com ou sem protocolos (por ex. https).
    - O domínio da URL, o caminho da URL, o domínio da URL e os filtros de caminho não exigem um protocolo para filtrar.
    - Você deve clicar no ícone Atualizar sempre que alterar os valores de filtro para obter resultados relevantes.

5. **Filtros avançados:** com esses filtros, você pode criar consultas complexas e filtrar seu conjunto de dados. Clicar em *Filtros Avançados* abre um menu com opções.

   A filtragem avançada é uma ótima adição aos recursos de pesquisa. Um filtro **BOOLEAN NOT** foi introduzido em *Recipient*, *Sender* e *Sender domain* para permitir que os administradores investiguem excluindo valores. Esta opção aparece no parâmetro selection *Contains none of*. **NOT** permitirá que os administradores excluam caixas de correio de alerta, caixas de correio de resposta padrão de suas investigações e é útil para casos em que os administradores pesquisam por um assunto específico (subject="Attention") onde o Destinatário pode ser definido como nenhum dos contoso.com *. \@* Esta é uma pesquisa de valor exato.

   ![O filtro Avançado Recipients - "Contém nenhum de".](../../media/tp-InvestigateMalEmail-AdvancedFilter.png)

   *A filtragem por horas* ajudará a equipe de segurança da sua organização a se detalhar rapidamente. A menor duração de tempo permitida é de 30 minutos. Se você puder restringir a ação suspeita por período de tempo (por exemplo, ocorreu há três horas), isso limitará o contexto e ajudará a identificar o problema.

   ![A opção de filtragem por horas para restringir a quantidade de equipes de segurança de dados a processar e cuja duração mais curta é de 30 minutos.](../../media/tp-InvestigateMalEmail-FilterbyHours.png)

6. **Campos no Explorador** de Ameaças: o Explorador de Ameaças expõe muito mais informações de email relacionadas à segurança, como ação de entrega *,* local de entrega *,* ação especial *,* *direcionalidade*, *substituições* e ameaça de *URL*. Ele também permite que a equipe de segurança da sua organização investigue com uma certeza mais alta.

    *A ação de* entrega é a ação realizada em um email devido a políticas ou detecções existentes. Aqui estão as possíveis ações que um email pode tomar:

    - **Entregue** – o email foi entregue à caixa de entrada ou pasta de um usuário e o usuário pode acessá-lo diretamente.
    - **Lixo eletrônico** (Entregue ao lixo eletrônico) – o email foi enviado para a pasta de lixo eletrônico ou a pasta excluída do usuário, e o usuário tem acesso a mensagens de email em sua pasta Lixo Eletrônico ou Excluído.
    - **Bloqueado** – todas as mensagens de email que estão em quarentena, que falharam ou foram retiradas. (Isso é completamente inacessível pelo usuário.)
    - **Substituído –** qualquer email em que anexos mal-intencionados são substituídos por arquivos .txt que afirmam que o anexo foi mal-intencionado

    **Local de** entrega: o filtro de local de entrega está disponível para ajudar os administradores a entender onde a mensagem suspeita de email mal-intencionado terminou e quais ações foram realizadas nele. Os dados resultantes podem ser exportados para planilha. Os locais de entrega possíveis são:

    - **Caixa de entrada ou pasta** – O email está na Caixa de Entrada ou em uma pasta específica, de acordo com suas regras de email.
    - **Local ou externo** – a caixa de correio não existe na nuvem, mas é local.
    - **Pasta lixo** eletrônico – O email está na pasta Lixo Eletrônico do usuário.
    - **Pasta itens excluídos** – O email está na pasta Itens Excluídos de um usuário.
    - **Quarentena** – O email em quarentena, e não na caixa de correio de um usuário.
    - **Falha** – O email não conseguiu alcançar a caixa de correio.
    - **Descartado** – O email foi perdido em algum lugar no fluxo de emails.

    **Direcionalidade:** essa opção permite que sua equipe de operações de segurança filtre pela "direção" de onde um email vem ou está indo. Os valores de direcionalidade são Entrada *,* Saída e *Dentro da* organização (correspondentes aos emails que vêm para sua organização de fora, enviados para fora da sua organização ou enviados internamente para sua organização, respectivamente).  Essas informações podem ajudar as equipes de operações de segurança a identificar a falsa e a representação, porque uma incompatibilidade entre o valor de direcionalidade (por ex. *A entrada*), e o domínio do remetente *(que* parece ser um domínio interno) serão evidentes! O valor de direcionalidade é separado e pode ser diferente do Rastreamento de Mensagem. Os resultados podem ser exportados para planilha.

    **Substituições:** esse filtro usa as informações que aparecem na guia de detalhes do email e as usa para expor onde as políticas organizacionais, ou de usuário, para permitir e bloquear emails foram *substituídos.* O mais importante sobre esse filtro é que ele ajuda a equipe de segurança da sua organização a ver quantos emails suspeitos foram entregues devido à configuração. Isso lhes dá a oportunidade de modificar as permites e os blocos conforme necessário. Esse conjunto de resultados desse filtro pode ser exportado para planilha.

    ****

    |Substituições do Explorador de Ameaças|O que eles significam|
    |---|---|
    |Permitido pela Política da Organização|Os emails foram permitidos na caixa de correio conforme indicado pela política da organização.|
    |Bloqueado pela política da organização|O email foi impedido de ser entregue na caixa de correio, conforme indicado pela política da organização.|
    |Extensão de arquivo bloqueada pela Política da Organização|O arquivo foi impedido de ser entregue na caixa de correio, conforme indicado pela política da organização.|
    |Permitido pela Política de Usuário|Os emails foram permitidos na caixa de correio conforme indicado pela política de usuário.|
    |Bloqueado pela Política de Usuário|O email foi impedido de ser entregue na caixa de correio, conforme indicado pela política de usuário.|
    |

    **Ameaça de URL**: o campo  de ameaça de URL foi incluído na guia detalhes de um email para indicar a ameaça apresentada por uma URL. As ameaças apresentadas por uma URL podem incluir *Malware,* *Phishing* ou  *Spam,* e uma URL sem ameaça dirá *Nenhum* na seção de ameaças.

7. **Exibição da linha do** tempo do email: talvez sua equipe de operações de segurança precise se adecarcar aos detalhes do email para investigar mais. A linha do tempo do email permite que os administradores vejam as ações realizadas em um email, desde a entrega até a pós-entrega. Para exibir uma linha do tempo de email, clique no assunto de uma mensagem de email e, em seguida, clique na linha do tempo do email. (Ele aparece entre outros títulos no painel, como Resumo ou Detalhes.) Esses resultados podem ser exportados para planilha.

    A linha do tempo do email será aberta para uma tabela que mostra todos os eventos de entrega e pós-entrega do email. Se não houver mais ações no email, você deverá ver um único evento para a entrega original que declara um resultado, como Bloqueado *,* com um veredito como *Phish*. Os administradores podem exportar toda a linha do tempo do email, incluindo todos os detalhes na guia e no email (como Assunto, Remetente, Destinatário, Rede e ID da Mensagem). A linha do tempo do email reduz a randomização porque há menos tempo gasto verificando locais diferentes para tentar entender os eventos que aconteceram desde que o email chegou. Quando ocorrem vários eventos ao mesmo tempo em um email, ou quase, esses eventos aparecem em um modo de exibição de linha do tempo.

8. **Visualização/download:** o Explorador de Ameaças fornece à sua equipe de operações de segurança os detalhes necessários para investigar emails suspeitos. Sua equipe de operações de segurança pode:

    - [Verifique a ação de entrega e o local.](#check-the-delivery-action-and-location)

    - [Veja a linha do tempo do seu email.](#view-the-timeline-of-your-email)

### <a name="check-the-delivery-action-and-location"></a>Verificar a ação de entrega e o local

No [Explorador de Ameaças (e detecções](threat-explorer.md)  em tempo  real), agora você tem colunas Ação de Entrega e Local de Entrega em vez da coluna Status de **Entrega** anterior. Isso resulta em uma imagem mais completa de onde suas mensagens de email chegarão. Parte da meta dessa alteração é facilitar as investigações para as equipes de operações de segurança, mas o resultado líquido é saber rapidamente a localização das mensagens de email com problemas.

O Status de Entrega agora está dividido em duas colunas:

- **Ação de** entrega - Qual é o status deste email?

- **Local de** entrega - Para onde esse email foi roteado como resultado?

A ação de entrega é a ação realizada em um email devido a políticas ou detecções existentes. Aqui estão as possíveis ações que um email pode tomar:

- **Entregue** – o email foi entregue à caixa de entrada ou pasta de um usuário e o usuário pode acessá-lo diretamente.

- **Lixo eletrônico** – o email foi enviado para a pasta de lixo eletrônico ou pasta excluída do usuário, e o usuário tem acesso a mensagens de email na pasta Lixo Eletrônico ou Excluído.

- **Bloqueado** – todas as mensagens de email que estão em quarentena, que falharam ou foram retiradas. (Isso é completamente inacessível pelo usuário.)

- **Substituído –** qualquer email em que anexos mal-intencionados são substituídos por arquivos .txt que afirmam que o anexo foi mal-intencionado.

O local de entrega mostra os resultados de políticas e detecções que são executados após a entrega. Ele está vinculado a uma Ação de Entrega. Esse campo foi adicionado para dar uma ideia da ação tomada quando um email com problema é encontrado. Aqui estão os valores possíveis de local de entrega:

- **Caixa de entrada ou pasta** – O email está na caixa de entrada ou em uma pasta (de acordo com suas regras de email).

- **Local ou externo** – a caixa de correio não existe na nuvem, mas é local.

- **Pasta lixo** eletrônico – O email está na pasta Lixo Eletrônico do usuário.

- **Pasta itens excluídos** – O email está na pasta Itens Excluídos de um usuário.

- **Quarentena** – O email em quarentena, e não na caixa de correio de um usuário.

- **Falha** – O email não conseguiu alcançar a caixa de correio.

- **Descartado** – O email se perde em algum lugar no fluxo de emails.

### <a name="view-the-timeline-of-your-email"></a>Exibir a linha do tempo do seu email

**Linha do tempo** do email é um campo no Explorador de Ameaças que facilita a busca para sua equipe de operações de segurança. Quando vários eventos ocorrem ao mesmo tempo ou quase ao mesmo tempo em um email, esses eventos aparecem em um modo de exibição de linha do tempo. Alguns eventos que ocorrem após a entrega de emails são capturados na **coluna Ações** especiais. Combinar informações da linha do tempo de uma mensagem de email com ações especiais que foram realizadas após a entrega oferece aos administradores informações sobre políticas e tratamento de ameaças (como onde o email foi roteado e, em alguns casos, qual foi a avaliação final).

> [!IMPORTANT]
> Ir para um tópico de correção [aqui](remediate-malicious-email-delivered-office-365.md).

## <a name="related-topics"></a>Tópicos relacionados

[Correção de emails mal-intencionados entregues no Office 365](remediate-malicious-email-delivered-office-365.md)

[Obter o Microsoft Defender para Office 365](office-365-ti.md)

[Proteger contra ameaças no Office 365](protect-against-threats.md)

[Exibir relatórios do Defender para Office 365](view-reports-for-atp.md)
