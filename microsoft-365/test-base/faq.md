---
title: Perguntas frequentes sobre base de teste
description: Revisar perguntas frequentes
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: troubleshooting
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 9d24ecb807e60733471be60353d12789f19be1b4
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322552"
---
# <a name="test-base-faq"></a>Perguntas frequentes sobre base de teste

**P: Como enviar nossos pacotes para a equipe da Base de Teste?**

**R:** Envie seus pacotes diretamente para o ambiente da Base de Teste usando nosso portal de autoatendício.

Para enviar seu pacote de aplicativos, navegue até o Portal do [Azure](https://www.aka.ms/testbaseportal "Página Inicial da Base de Teste") e carregue uma pasta com zipped contendo binários, dependências e scripts de teste do aplicativo por meio do painel do portal da Base de Teste de autoatendência. 

Consulte o guia do usuário de integração para obter mais informações ou entre em contato com nossa equipe para <testbasepreview@microsoft.com> obter assistência e mais informações.

**P: O que são testes OOB (out-of-box) ?**

**R:** Os testes OOB (out-of-box) são padronizados, os testes padrão são executados onde os pacotes de aplicativos são instalados, lançados e fechados trinta (30) vezes e, em seguida, desinstalados. 

Os pacotes criados para a Base de Teste terão os seguintes scripts de teste: instalar, iniciar, fechar e, opcionalmente, o script de desinstalação. 

Os testes OOB (Out-of-box) fornecem telemetria padronizada em seu aplicativo para comparação entre Windows builds.

**P: Podemos enviar testes fora dos testes fora da caixa de correio (instalar, iniciar, fechar, desinstalar scripts de teste)?**

**R:** Sim, os clientes também podem carregar pacotes de aplicativos para **testes funcionais** por meio do painel do portal de autoatend responsabilidade.
**Testes funcionais** são testes que permitem que os clientes executem seus scripts para executar a funcionalidade personalizada em seu aplicativo.


## <a name="testing"></a>Testes

**P: Você suporta testes funcionais?**

**R:** Sim, a Base de Teste dá suporte a testes funcionais. Testes funcionais são testes que permitem que nossos clientes executem seus scripts para executar a funcionalidade personalizada em seu aplicativo. 

Para enviar seu pacote de aplicativos para testes funcionais, basta carregar a pasta de zipped contendo binários, dependências e scripts de teste do aplicativo por meio do painel do portal de autoatendência. 

Consulte o guia do usuário de integração para obter mais informações ou entre em contato com nossa equipe para <testbasepreview@microsoft.com> obter assistência e mais informações.

**P: Como a Base de Teste lida com nossos dados de teste?**

**R:** A Base de Teste coleta e gerencia com segurança seus dados de teste no ambiente do Azure. 

**P: A Base de Teste pode dar suporte aos nossos testes automatizados?**

Sim, a Base de Teste oferece suporte a testes automatizados, no entanto, não suportamos testes manuais no momento devido aos recursos de serviço.

**P: Quais idiomas e estruturas de testes automatizados você suporta?**

**R:** Suportamos todos os idiomas e estruturas. Invocamos todos os scripts por meio do PowerShell. 

Você também precisará fornecer (carregar) os binários dependentes da estrutura necessária.

**P: Em quanto tempo a Base de Teste fornece resultados de teste?**

**R:** Para cada teste executado em relação às versões de pré-lançamento, forneceremos resultados dentro de 48 horas no painel [do Portal do Azure.](https://www.aka.ms/testbaseportal "Página Inicial da Base de Teste")

**P: Você pode reiniciar após a instalação?**

**R:** Sim, nosso processo dá suporte à reinicialização após a instalação. Certifique-se de selecionar essa opção na lista de opções "Configurações opcionais" ao definir suas **Tarefas** no portal de integração.

Para testes OOB (out-of-box), você pode especificar se uma reinicialização é necessária para o _script Install._

![Imagem de reinicialização](Media/reboot.png)

Enquanto para testes funcionais, você pode especificar se uma reinicialização é necessária para cada script adicionado.

![Como selecionar testes funcionais](Media/functionalreboot.png)

**P: Quais Windows você suporta?**

**R:** Atualmente, suportamos clientes Windows 10, Windows Server 2016, Windows Server 2016 versão Core, Windows Server 2019 e Windows Server 2019 Core versão.

**P: Qual é a diferença entre testes de Atualização de Segurança e Testes de Atualização de Recursos?**

**R:** Para testes de atualização de segurança, testamos as atualizações de segurança de **<ins>pré-lançamento</ins>** mensais em Windows que se concentram em manter nossos usuários sempre seguros e protegidos. Para os testes de atualização de recursos, testamos as atualizações de recursos de **<ins>pré-lançamento</ins>** anuais que introduzem novos recursos e recursos no Windows.

## <a name="debugging-options"></a>Opções de depuração

**P: Temos acesso às Máquinas Virtuais (VMs) em caso de falhas? O que o Test Base compartilha?**

**R:** Para que o serviço seja compatível e as atualizações de pré-lançamento sejam seguras, somente a Microsoft tem acesso às VMs. No entanto, os clientes podem exibir resultados de teste e outras métricas de teste em seu painel de portal, incluindo sinais de falha e travamento, métricas de confiabilidade, memória e utilização de CPU etc. Também geramos e fornecemos logs de testes executados no painel para download e análise posterior. 

Também podemos fornecer despejos de memória para depuração de falhas conforme necessário.

**P: Se houver problemas encontrados durante o teste, quais são as próximas etapas para resolver esses problemas?**

**R:** A equipe da Base de Teste realizará um processo de triagem inicial para determinar a causa raiz do erro e, dependendo de nossas descobertas, encaminharemos para o cliente ou equipes internas da Microsoft para depuração. 

Sempre trabalhamos de perto com nossos clientes em correção conjunta para resolver quaisquer problemas. 

**P: A Microsoft mantém a versão do patch de segurança até que o problema seja resolvido? Quais resoluções alternativas estão disponíveis?**

**R:** O objetivo da Base de Teste é garantir que nossos clientes finais conjuntos não enfrentem problemas. Trabalharemos com fornecedores de software para resolver quaisquer problemas antes da versão, mas caso a correção não seja viável, temos outras resoluções, como shims e blocos.

## <a name="miscellaneous"></a>Diversos

**P: Como o serviço funcionará com um servidor local?**

**R:** Atualmente, não fornecemos suporte para servidores no momento. No entanto, se o servidor estiver expondo o ponto de extremidade HTTP, podemos nos conectar a ele pela Internet.

**P: Who hospeda as VMs?**

**R:** A Microsoft provisiona a VM para esse serviço, assumindo a carga de fazer isso do cliente.

**P: Esse serviço dá suporte a aplicativos web, móveis ou desktop?**

**R:** Atualmente, nosso foco está em aplicativos de área de trabalho, no entanto, temos planos de integração de aplicativos Web no futuro, mas não suportamos aplicativos móveis no momento.

**P: Qual é a diferença entre Test Base e VANP?**

**R:** A maior diferença entre a Base de Teste e a VANP é que nossos parceiros integram seus aplicativos no ambiente base de teste do Azure para validação, em vez de realizar os próprios testes. 

Além do teste de atualizações de segurança de pré-lançamento, suportamos testes de atualizações de recursos de pré-lançamento em nossa plataforma. Temos muitos outros tipos de atualizações e testes do sistema operacional em nosso roteiro.

**P: Há um custo associado ao serviço?**

**R:** O serviço Base de Teste será gratuito para os usuários até a Disponibilidade Geral (GA). Nesse momento, anunciaremos uma estrutura de custo que estará em vigor para todos os clientes. 

**P: Como posso fornecer comentários sobre a Base de Teste?**

**R:** Para compartilhar seus comentários sobre a Base de Teste, selecione o **ícone Comentários** na parte inferior esquerda do portal. Inclua uma captura de tela com seu envio para ajudar a Microsoft a entender melhor seus comentários. 

Você também pode enviar sugestões de produto e revogar outras ideias em <testbasepreview@microsoft.com> .
