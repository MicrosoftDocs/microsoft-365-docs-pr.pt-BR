---
title: Teste funcional na Base de Teste
description: Detalhes sobre como testar seu aplicativo com seus testes funcionais automatizados existentes
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 7b5cb907756ec0fb746d303b3ab629e912bf9c96
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322482"
---
# <a name="functional-testing"></a>Testes funcionais

Como fornecedor de software, agora você pode executar testes funcionais personalizados, usando a estrutura de teste de sua escolha - por meio da Base de Teste de autoatendança para portal M365. 

Quando iniciamos inicialmente o serviço, oferecimos os testes iniciais, que é um conjunto pré-definido de testes orientados por scripts padronizados. Isso, no entanto, não conseguiu obter cobertura completa de teste para muitos Fornecedores de Software Independentes (ISVs). 

Portanto, em resposta aos seus comentários, estamos fornecendo aos nossos ISVs a capacidade de carregar testes funcionais automatizados.

Para usar esse recurso, siga as etapas abaixo:

1. Upload seus arquivos (binários, dependências e scripts) como um único .zip pacote.
2. Escolha se deseja reiniciar as Máquinas Virtuais de teste (VMs) em vários pontos de execução.
3. Gerencie as opções disponíveis para seus scripts.
4. Escolha quando aplicar a atualização Windows na VM durante a execução.

Descrições detalhadas das etapas acima são realçadas abaixo:

**Upload um pacote de teste funcional**

Para começar, navegue até a página Upload, selecione Upload novo aplicativo em Catálogo de aplicativos no menu de navegação do lado esquerdo do portal base de teste do M365 no Azure. A partir daí:

Guia 1 - Insira informações básicas. Forneça o nome e a versão do aplicativo. Na opção Tipo de teste, selecione ```Functional tests``` . 

*Observe que a opção OOB (Out-of-Box) é necessária por padrão.*


![Selecione a guia teste funcional](Media/functional_testing_tab1.png)

Guia 2 - Upload componentes do pacote carregando um arquivo zip com todo o seu teste (binários, dependências, scripts etc.). 

Consulte aka.ms/usl-package-outline para obter detalhes. (Observação: os scripts de teste out-of-box e o conteúdo do teste funcional devem ser colocados no mesmo arquivo zip). Atualmente, o tamanho do arquivo é limitado a 2 GB.

Guia 3 - Configure as tarefas de teste out-of-box e Funcional. Aqui, escolha os caminhos para os scripts do PowerShell que instalarão, iniciarão, fecharão e desinstalarão seu aplicativo (para Out-of-Box), bem como os caminhos para todos os scripts personalizados para executar seu teste funcional. **(Observação: um script para desinstalar seu aplicativo é opcional).**

Atualmente, você pode carregar entre 1 e 8 scripts para seus testes funcionais. (Comentário amavelmente nesta postagem se você precisar de mais scripts!)

![Upload até 8 scripts com testes funcionais](Media/functional_testing_tab3.png)

(Opcional) Configure uma reinicialização após a instalação. Alguns aplicativos exigem uma reinicialização após a instalação. 

Selecione o Script específico na guia Tarefas se quiser que uma reinicialização seja conduzida após ```Reboot After Execution``` a execução desse script.

Guia 4 - Escolha quando a atualização de Windows for instalada: O aplicativo do patch de atualização Windows é feito antes de qualquer script de sua escolha. É recomendável instalar uma atualização Windows após a instalação do aplicativo para imitar de perto os cenários de uso do aplicativo no mundo real.

![A Windows atualização pode ser instalada após um script específico](Media/functional_testing_tab4.png)

Guia 5 - Revisar e criar o pacote. Depois de concluir as etapas listadas acima, selecione ```Create``` para concluir o processo de carregamento.

Depois que seu pacote tiver sido criado, você poderá verificar o status de verificação do pacote.

Executemos um teste inicial para instalar, iniciar, fechar e desinstalar seu aplicativo. Isso nos permite verificar se seu pacote pode ser instalado em nosso serviço sem erros.

O processo de verificação pode levar até 24 horas. Depois que a verificação for concluída, você poderá ver o status no menu, que seria uma ```Manage packages``` das duas entradas:

1. A verificação é bem-sucedida: o pacote será testado automaticamente em relação às atualizações de Windows de pré-lançamento para as builds do sistema operacional selecionadas.
ou
2. Falha na verificação: você precisará investigar os motivos da falha, corrigir o problema e carregar seu pacote de volta.

Você também será notificado de qualquer resultado por meio do ícone de notificação no portal do Azure.
