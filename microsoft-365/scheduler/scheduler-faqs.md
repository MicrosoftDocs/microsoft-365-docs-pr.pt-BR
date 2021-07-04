---
title: Agendador de Microsoft 365 perguntas frequentes
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: Agendador de Microsoft 365 perguntas frequentes
ms.openlocfilehash: 423660785e51a61cbff9fa2849b9466feddfc1c1
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289662"
---
# <a name="scheduler-for-microsoft-365-faqs"></a>Agendador de Microsoft 365 perguntas frequentes

**Pergunta:** Como o Agendador se integra a outros recursos Cortana, como *Cortana* para Windows, Email de *Reunião* Diária e *Reproduzir Meus Emails?*</br>
O agendador é um serviço independente de outros Cortana recursos. Outros Cortana recursos podem ser desabilitados no nível do locatário, e o Agendador ainda pode ser habilitado usando o endereço cortana@yourdomain.com email. Atualmente, os usuários só podem interagir com o Agendador por email.

**Pergunta:** Isso só funciona com Outlook? Há suporte para outros produtos de email?</br>
Desde que você tenha uma licença, diferente dos três requisitos acima, os usuários podem enviar emails cortana@yourdomain.com de qualquer cliente de email em qualquer dispositivo.

**Pergunta:** Os contatos podem estar em uma lista de contatos pessoais Outlook GAL ou outro equivalente da empresa?</br>
Os participantes da reunião podem ser qualquer pessoa com um endereço de email dentro ou fora da empresa. Infelizmente, o Agendador não pode traduzir nomes automaticamente para endereços de email/alias procurando-os na GAL hoje.

**Pergunta:** Posso usar o Agendador com minha versão instalada (local) do Outlook?</br>
O agendador requer Exchange Online. Não funciona com Exchange Server (on-prem). Funciona com qualquer cliente de email, Outlook Desktop, OWA, iOS, android, gmail e assim por diante.

**Pergunta:** O Outlook precisa ser aberto em segundo plano?</br>
Outlook precisa ser aberto em segundo plano. Tudo o que você precisa fazer é enviar Cortana um email e confiar nele para fazer a maior parte do trabalho.

## <a name="frequently-asked-trust-and-privacy-questions"></a>Perguntas frequentes sobre confiança e privacidade

**Pergunta:** Como funciona o Agendador?</br>
O agendador usa a Inteligência de Agendamento (AI) aumentada com assistentes humanos. Se os modelos de IA gerarem uma necessidade de suporte na linguagem natural de comunicação com o Cortana, a solicitação de reunião escalona para um humano para revisão e conclusão.

**Pergunta:** Who os humanos que analisam solicitações escalonados? </br>
Os assistentes de agendador são certificados do Microsoft Supplier Security and Privacy Assurance (SSPA) para obter informações pessoais e altamente confidenciais.

**Pergunta:** O que os Assistentes SSPA podem exibir?</br>
O agendador e os Assistentes SSPA podem exibir os emails endereçados a Cortana. Em uma troca de email encadeada, somente os emails que incluem o endereço de email do Cortana serão processados, e não os emails anteriores no thread antes de Cortana foi adicionado.

**Pergunta:** Os dados do cliente são mantidos no Programador de Dados Flow? </br>
O agendador armazena todo o conteúdo do cliente dentro dos limites do locatário e mantém os dados de acordo com as diretrizes do RGPD, Microsoft 365 Políticas de Confiança & Privacidade e políticas de email de locatários.

**Pergunta:** Como o Agendador processa os dados de livre/ocupado dos participantes internos? </br>
A automação do agendador usa o *serviço findMeetingTimes* para identificar os horários que estão mutuamente disponíveis para os participantes e o organizador. Esse serviço alimenta outras Outlook experiências como *Tempos Sugeridos* no formulário Outlook reunião. As informações do participante de livre/ocupado não são consumidas explicitamente como blocos de livre/ocupado.

**Pergunta:** O RGPD do Agendador está em conformidade? </br>
Sim.

**Pergunta:** Who tem acesso à caixa de correio Cortana de correio? </br>
O agendador processa solicitações de reunião e emails associados que são enviados para a caixa de correio Cortana locatário. A Microsoft não tem outro acesso à caixa de correio Cortana, exceto por meio da aprovação do Lockbox, a pedido do administrador do locatário.

**Pergunta:** Os dados do cliente são usados para treinamento de modelos de IA?</br>
Nenhum conteúdo do cliente do Agendador para Microsoft 365 pode ser usado para conjuntos de treinamento de dados. Todo o conteúdo do cliente reside no locatário do cliente.

**Pergunta:** O Agendador processará emails criptografados?</br>
Não, os emails criptografados serão rejeitados pelo fluxo de trabalho do Agendador.
