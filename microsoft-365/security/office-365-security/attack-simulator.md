---
title: Simulador de Ataque no Office 365
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 6fb88e6b79c0949c7ddc26eabda2bb04ea1fa3bf
ms.sourcegitcommit: 4986032867b8664a215178b5e095cbda021f3450
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "41957406"
---
# <a name="attack-simulator-in-office-365"></a>Simulador de Ataque no Office 365

**Resumo** Se você for um administrador global do Office 365 ou um administrador de segurança e sua organização tiver o Office 365 Advanced Threat Protection Plan 2, que inclui os [recursos de investigação e resposta contra ameaças](office-365-ti.md), você poderá usar o simulador de ataques para executar cenários de ataque realísticos em sua organização. Isso pode ajudá-lo a identificar e encontrar usuários vulneráveis antes que um ataque real afete o resultado final. Leia este artigo para saber mais.

## <a name="the-attacks"></a>Os ataques

Três tipos de simulação de ataque estão disponíveis atualmente:

- [Coleta de credenciais do spear-phishing Attack](#credential-harvest-spear-phishing-attack)

- [Anexo de Spear-ataque de phishing](#attachment-spear-phishing-attack)

- [Ataque de irrigação de senha](#password-spray-attack)

- [Ataque de senha de força bruta](#brute-force-password-attack)

Para que um ataque seja iniciado com êxito, certifique-se de que a conta que você está usando para executar ataques simulados esteja usando a autenticação multifator. Além disso, você deve ser um administrador global do Office 365 ou um administrador de segurança. (Para saber mais sobre funções e permissões, confira [permissões no centro de conformidade & segurança do Office 365](permissions-in-the-security-and-compliance-center.md).)

Para acessar o simulador de conformidade, &amp; no centro de conformidade de segurança, escolha **simulador de ataque**de **Gerenciamento** \> de ameaças.

## <a name="before-you-begin"></a>Antes de começar...

Verifique se você e sua organização atendem aos seguintes requisitos para o simulador de ataques:

- O email da sua organização está hospedado no Exchange Online. (O simulador de ataque não está disponível para os servidores de email locais.)

- Você é um administrador global do Office 365 ou administrador de segurança

- Campanhas de phishing coletam e processam eventos por um período de 30 dias, dados de campanha históricos estarão disponíveis por até 90 dias após a campanha ser iniciada.

- A [autenticação multifator/acesso condicional](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) está ativada, por pelo menos a conta de administrador global do Office 365 e os administradores de segurança que usarão o simulador de ataques. (Idealmente, a autenticação multifator/acesso condicional está ativada para todos os usuários da sua organização.)

- Sua organização tem o [plano de proteção avançada contra ameaças do Office 365](office-365-atp.md), com o simulador &amp; de ataques visível no centro de conformidade de segurança (vá para o \> **simulador de ataques**de **Gerenciamento de ameaças** )

    ![Gerenciamento de ameaças-simulador de ataques](../media/ThreatMgmt-AttackSimulator.png)

## <a name="credential-harvest-spear-phishing-attack"></a>Coleta de credenciais do spear-phishing Attack

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

## <a name="attachment-spear-phishing-attack"></a>Anexo de Spear-ataque de phishing

Phishing é um termo genérico para um amplo conjunto de ataques de classe como um ataque de estilo de engenharia social. Esse ataque está voltado ao anexo de spear phishing, um ataque mais direcionado para um grupo específico de pessoas ou uma organização. Normalmente, um ataque personalizado com algum reconhecimento executado e usando um nome de exibição que irá gerar confiança no destinatário, como uma mensagem de email que parece ser proveniente de um executivo dentro da sua organização.

Esse ataque se concentra em permitir que você manipule quem a mensagem parece ter originado alterando o nome de exibição e o endereço de origem, mas desta vez, em vez de oferecer uma URL para tentar e atrair o usuário final para clicar, oferecemos um anexo que estamos tentando obter usuário final para abrir o. 

### <a name="to-simulate-a-attachment-spear-phishing-attack"></a>Para simular um ataque de spear-phishing de anexo

1. Siga as etapas acima, tendo esse horário em que você clicou em **ataque de anexo** na página de aterrissagem.

2. À medida que você avança no assistente, você vê duas opções para configurar. O **tipo de anexo**, damos suporte a dois tipos de anexo, **. docx** ou **. pdf**. O **nome do anexo**, use este campo para criar um nome de anexo significativo para a campanha.

## <a name="password-spray-attack"></a>Ataque de irrigação de senha

Um ataque de irrigação de senha em uma organização é geralmente usado após um ator incorreto ter adquirido com êxito uma lista de usuários válidos do locatário. O ator ruim sabe sobre senhas comuns que as pessoas utilizam. Esse é um ataque amplamente usado, pois é um ataque barato que é executado e é mais difícil de detectar abordagens de força bruta.

Esse ataque se concentra em permitir que você especifique uma senha comum para uma grande base de destino de usuários.

**Observação importante** a execução do ataque de irrigação de senha contra contas de usuário finais que já têm autenticação multifator resultará em uma tentativa malsucedida para essas contas no relatório. Isso se deve ao fato de a autenticação multifator ser uma das principais mechanims para ajudar a proteger contra ataques de irrigação de senha, portanto, é esperado.

### <a name="to-simulate-a-password-spray-attack"></a>Para simular um ataque de irrigação de senha

1. No [centro de &amp; conformidade de segurança](https://protection.office.com), escolha \> **simulador de ataque**de **Gerenciamento de ameaças** .

2. Especifique um nome de campanha significativo para o ataque.

3. Especifique os destinatários de destino. Podem ser indivíduos ou grupos em sua organização. Um destinatário direcionado deve ter uma caixa de correio do Exchange Online para que o ataque seja bem-sucedido.

4. Especifique uma senha a ser usada para o ataque. Por exemplo, uma senha comum e relevante que você pode tentar `Summer2019`é. Outro pode ser `Fall2019`ou `Password1`.

5. Escolha **concluir** para iniciar o ataque.

## <a name="brute-force-password-attack"></a>Ataque de senha de força bruta

Um ataque de senha de força bruta em relação a uma organização é geralmente usado após um ator incorreto ter adquirido com êxito uma lista de usuários principais do locatário. Esse ataque se concentra em tentar um conjunto de senhas em uma única conta de usuário.

**Observação importante** a execução de ataques de senha de força bruta contra contas de usuário finais que já têm autenticação multifator resultará em uma tentativa malsucedida para essas contas no relatório. Isso se deve ao fato de a autenticação multifator ser uma das principais mechanims para ajudar a proteger contra ataques de senha de força bruta, portanto, é esperado.

### <a name="to-simulate-a-brute-force-password-attack"></a>Para simular um ataque de senha de força bruta

1. No [centro de &amp; conformidade de segurança](https://protection.office.com), escolha \> **simulador de ataque**de **Gerenciamento de ameaças** .

2. Especifique um nome de campanha significativo para o ataque.

3. Especifique o destinatário de destino. Um destinatário direcionado deve ter uma caixa de correio do Exchange Online para que o ataque seja bem-sucedido.

4. Especifique um conjunto de senhas a ser usado para o ataque. Para fazer isso, você pode usar um arquivo de texto (. txt) para sua lista de senhas. O arquivo de texto não pode exceder 10 MB em tamanho de arquivo. Use uma senha por linha e certifique-se de incluir um retorno de disco rígido após a última senha em sua lista.

5. Escolha **concluir** para iniciar o ataque.



Visite o [mapa do Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) para ver o que está em desenvolvimento, o que está saindo e o que já foi iniciado.

## <a name="see-also"></a>Confira também

[Descrição do Serviço da Proteção Avançada contra Ameaças do Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

[Proteção Avançada contra Ameaças do Office 365](office-365-atp.md)
