---
title: Simulador de Ataque no Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
description: Como administrador global do Office 365, você pode usar o simulador de ataques para executar cenários de ataque realistas em sua organização. Isso pode ajudá-lo a identificar e encontrar usuários vulneráveis antes que um ataque real atinja sua empresa.
ms.openlocfilehash: bb68850587647f7e96c940de10e3da23cd5e83de
ms.sourcegitcommit: 84d88a857e82b1a8a0d466057a2e330e8b1692e4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "37306175"
---
# <a name="attack-simulator-in-office-365"></a>Simulador de Ataque no Office 365

**Resumo** Se você for um administrador global do Office 365 ou um administrador de segurança e sua organização tiver o Office 365 Advanced Threat Protection Plan 2, que inclui os [recursos de investigação e resposta contra ameaças](office-365-ti.md), você poderá usar o simulador de ataque para executar cenários de ataque realísticos em sua organização. Isso pode ajudá-lo a identificar e encontrar usuários vulneráveis antes que um ataque real afete o resultado final. Leia este artigo para saber mais.

## <a name="the-attacks"></a>Os ataques

Três tipos de simulação de ataque estão disponíveis atualmente:

- [Nome de exibição spear-phishing Attack](#display-name-spear-phishing-attack)

- [Ataque de irrigação de senha](#password-spray-attack)

- [Ataque de senha de força bruta](#brute-force-password-attack)

Para que um ataque seja iniciado com êxito, certifique-se de que a conta que você está usando para executar ataques simulados esteja usando a autenticação multifator. Além disso, você deve ser um administrador global do Office 365 ou um administrador de segurança. (Para saber mais sobre funções e permissões, confira [permissões no centro de conformidade & segurança do Office 365](permissions-in-the-security-and-compliance-center.md).)

Para acessar o simulador de conformidade, &amp; no centro de conformidade de segurança, escolha **simulador de ataque**de **Gerenciamento** \> de ameaças.

## <a name="before-you-begin"></a>Antes de começar...

Verifique se você e sua organização atendem aos seguintes requisitos para o simulador de ataques:

- O email da sua organização está hospedado no Exchange Online. (O simulador de ataque não está disponível para os servidores de email locais.)

- Você é um administrador global do Office 365 ou administrador de segurança

- A [autenticação multifator/acesso condicional](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication?view=o365-worldwide) está ativada, por pelo menos a conta de administrador global do Office 365 e os administradores de segurança que usarão o simulador de ataques. (Idealmente, a autenticação multifator/acesso condicional está ativada para todos os usuários da sua organização.)

- Sua organização tem o [plano de proteção avançada contra ameaças do Office 365](office-365-atp.md), com o simulador &amp; de ataques visível no centro de conformidade de segurança (vá para o \> **simulador de ataques**de **Gerenciamento de ameaças** )

    ![Gerenciamento de ameaças-simulador de ataques](../media/ThreatMgmt-AttackSimulator.png)

## <a name="display-name-spear-phishing-attack"></a>Nome de exibição spear-phishing Attack

Phishing é um termo genérico para um amplo conjunto de ataques de classe como um ataque de estilo de engenharia social. Esse ataque está voltado para o spear phishing, um ataque mais direcionado para um grupo específico de pessoas ou uma organização. Normalmente, um ataque personalizado com algum reconhecimento executado e usando um nome de exibição que irá gerar confiança no destinatário, como uma mensagem de email que parece ser proveniente de um executivo dentro da sua organização.

Esse ataque se concentra em permitir que você manipule quem a mensagem parece ter originado alterando o nome de exibição e o endereço de origem. Quando os ataques de spear-phishing forem bem-sucedidos, cyberattackers obter acesso às credenciais dos usuários.

### <a name="to-simulate-a-spear-phishing-attack"></a>Para simular um ataque de spear-phishing

![Redigir corpo de email](../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

Você pode criar o editor de HTML avançado diretamente no próprio campo de **corpo de email** ou trabalhar com o código-fonte HTML.

1. No [centro de &amp; conformidade de segurança](https://protection.office.com), escolha \> **simulador de ataque**de **Gerenciamento de ameaças** .

2. Especifique um nome de campanha significativo para o ataque ou selecione um modelo.

   ![Página de início de phishing](../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

3. Especifique os destinatários de destino. Podem ser indivíduos ou grupos em sua organização. Cada destinatário de destino deve ter uma caixa de correio do Exchange Online para que o ataque seja bem-sucedido.

   ![Seleção de destinatário](../media/faf8c2e0-6175-4cd7-8265-0c8e727f4d0f.jpg)

4. Configure os detalhes de email de phishing.

   ![Configurar detalhes de email](../media/f043608f-f8ce-4aae-be28-86e8ecc524a9.jpg)

   A formatação HTML pode ser complexa ou básica quanto às necessidades de sua campanha. Como o formato de email é HTML, você pode inserir imagens e texto para aprimorar o believability. Você tem controle sobre qual será a aparência da mensagem recebida no cliente de recebimento de email.

5. Especifique o texto para o campo **de (nome)** . Este é o campo que mostra o **nome de exibição** no cliente de recebimento de email.

6. Especifique o texto ou o campo **de** . Este é o campo que aparece como o endereço de email do remetente no cliente de recebimento de email.

   Você pode inserir um namespace de email existente dentro da sua organização (isso fará com que o endereço de email seja realmente resolvido no cliente de recebimento, facilitando um modelo de confiança muito alto) ou você pode inserir um endereço de email externo. O endereço de email que você especificar não precisa realmente existir, mas ele precisa seguir o formato de um endereço SMTP válido, como `user@domainname.extension`.

7. Usando o seletor suspenso, selecione uma URL de servidor de logon de phishing que reflita o tipo de conteúdo que você terá dentro de seu ataque. Várias URLs com temas são fornecidas para você escolher, como entrega de documentos, técnica, folha de pagamento, etc. Isso é efetivamente a URL para a qual os usuários direcionados são solicitados a clicar.

8. Especifique uma URL da página de aterrissagem personalizada. O uso dessa forma redirecionará os usuários para uma URL que você especificar no final de um ataque bem-sucedido. Se você tiver treinamento de conscientização interna, por exemplo, você pode especificar isso aqui.

9. Especifique o texto do campo **assunto** . Este é o campo que aparece como o **nome da entidade** no cliente de recebimento de email.

10. Redija o **corpo do email** que o destino receberá.

    `${username}`Insere o nome do destino no corpo do email.

    `${loginserverurl}`Insere a URL que os usuários de destino devem clicar

11. Escolha **Avançar e** **concluir** para iniciar o ataque. A mensagem de email de spear phishing é entregue às caixas de correio dos destinatários de destino.

## <a name="password-spray-attack"></a>Ataque de irrigação de senha

Um ataque de irrigação de senha em uma organização é geralmente usado após um ator incorreto ter adquirido com êxito uma lista de usuários válidos do locatário. O ator ruim sabe sobre senhas comuns que as pessoas utilizam. Esse é um ataque amplamente usado, pois é um ataque barato que é executado e é mais difícil de detectar abordagens de força bruta.

Esse ataque se concentra em permitir que você especifique uma senha comum para uma grande base de destino de usuários.

### <a name="to-simulate-a-password-spray-attack"></a>Para simular um ataque de irrigação de senha

1. No [centro de &amp; conformidade de segurança](https://protection.office.com), escolha \> **simulador de ataque**de **Gerenciamento de ameaças** .

2. Especifique um nome de campanha significativo para o ataque.

3. Especifique os destinatários de destino. Podem ser indivíduos ou grupos em sua organização. Um destinatário direcionado deve ter uma caixa de correio do Exchange Online para que o ataque seja bem-sucedido.

4. Especifique uma senha a ser usada para o ataque. Por exemplo, uma senha comum e relevante que você pode tentar `Summer2019`é. Outro pode ser `Fall2019`ou `Password1`.

5. Escolha **concluir** para iniciar o ataque.

## <a name="brute-force-password-attack"></a>Ataque de senha de força bruta

Um ataque de senha de força bruta em relação a uma organização é geralmente usado após um ator incorreto ter adquirido com êxito uma lista de usuários principais do locatário. Esse ataque se concentra em tentar um conjunto de senhas em uma única conta de usuário.

### <a name="to-simulate-a-brute-force-password-attack"></a>Para simular um ataque de senha de força bruta

1. No [centro de &amp; conformidade de segurança](https://protection.office.com), escolha \> **simulador de ataque**de **Gerenciamento de ameaças** .

2. Especifique um nome de campanha significativo para o ataque.

3. Especifique o destinatário de destino. Um destinatário direcionado deve ter uma caixa de correio do Exchange Online para que o ataque seja bem-sucedido.

4. Especifique um conjunto de senhas a ser usado para o ataque. Para fazer isso, você pode usar um arquivo de texto (. txt) para sua lista de senhas. O arquivo de texto não pode exceder 10 MB em tamanho de arquivo. Use uma senha por linha e certifique-se de incluir um retorno de disco rígido após a última senha em sua lista.

5. Escolha **concluir** para iniciar o ataque.

## <a name="new-features-in-attack-simulator"></a>Novos recursos no simulador de ataques

Novos recursos foram adicionados recentemente ao simulador de ataques. Entre eles:

- Recursos avançados de relatórios. A capacidade de ver dados como o tempo mais rápido (ou mais lento) para abrir uma mensagem de email de simulação de ataque, o tempo mais rápido (ou mais lento) para clicar em um link na mensagem e mais visualizações.

- Editor de modelos de email. A capacidade de criar um modelo de email personalizado e reutilizável que você pode usar para simulações de ataque futuras.

- Importação de destinatário de CSV. A capacidade de usar um arquivo. csv para importar sua lista de destinatários de destino em vez de usar o seletor de catálogo de endereços.

Mais novos recursos serão disponibilizados em breve para o simulador de ataques. Entre eles:

- Simulação de phishing de carga de anexos. A capacidade de usar um anexo como a carga de simulação de phishing no lugar de uma URL.

Visite o [mapa do Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) para ver o que está em desenvolvimento, o que está saindo e o que já foi iniciado.

## <a name="see-also"></a>Confira também

[Descrição do Serviço da Proteção Avançada contra Ameaças do Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

[Proteção Avançada contra Ameaças do Office 365](office-365-atp.md)
