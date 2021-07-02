---
title: Usar Microsoft OneDrive Learning interoperabilidade de ferramentas
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Crie e grade atribuições, crie e crie e crie conteúdo do curso e colabore em arquivos em tempo real com o novo aplicativo de interoperabilidade de ferramentas Microsoft OneDrive Learning ferramentas.
ms.openlocfilehash: 985a316bac689b9bc6c53ab65782d548fcad0db8
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256930"
---
# <a name="integrate-microsoft-onedrive-lti-with-canvas"></a>Integrar Microsoft OneDrive LTI com Canvas

A integração Microsoft OneDrive LTI com o Canvas é um processo de duas etapas. A primeira etapa habilita Microsoft OneDrive em Canvas, e a segunda etapa disponibiliza o Microsoft OneDrive LTI nos cursos do Canvas.

## <a name="recommended-browser-settings"></a>Configurações recomendadas do navegador

- Os cookies devem ser habilitados para Microsoft OneDrive.
- Pop-ups não devem ser bloqueados para Microsoft OneDrive.

> [!NOTE]
> - Os cookies não estão habilitados por padrão no modo de navegação anônima do Chrome e precisarão ser habilitados.
> - Microsoft OneDrive LTI funciona no modo privado no Microsoft Edge navegador. Verifique se você não bloqueou cookies (que estão habilitados por padrão).

## <a name="enable-microsoft-onedrive-lti-in-canvas"></a>Habilitar Microsoft OneDrive LTI no Canvas

> [!IMPORTANT]
> A pessoa que executa essa integração deve ser um administrador do Canvas e um administrador do Microsoft 365 locatário.

1. Entre no portal de <a href="https://onedrivelti.microsoft.com/admin" target="_blank">registro Microsoft OneDrive LTI</a>
1. Selecione o **botão Consentimento do** Administrador e aceite as permissões.
1. Selecione o **botão Criar novo Locatário LTI.** Na página Registro LTI, selecione **Tela** no menu suspenso e insira a URL base da sua instância do Canvas.

> [!NOTE]
> Se sua instância do Canvas for, por exemplo, https://contoso.test.instructure.com ]( https://contoso.test.instructure.com) , a URL completa deverá ser inserida.

:::image type="content" source="media/OneDrive-LTI-07.png" alt-text="A página de administração do locatário LTI, com um campo suspenso para escolher a plataforma de consumidor LTI e um campo de texto de URL.":::

4. Copie o JSON selecionando o botão **Copiar** (um ícone à direita que mostra duas páginas uma sobre a outra). Isso será usado para gerar a chave no Canvas.

:::image type="content" source="media/OneDrive-LTI-08.png" alt-text="Uma imagem mostrando o botão de cópia que copiará o texto JSON exibido e o disponibiliza para geração de chaves no Canvas.":::

5. Entre em sua instância do Canvas como administrador e selecione **Chaves** do Desenvolvedor no menu no lado esquerdo da página. No menu suspenso, crie uma chave de desenvolvedor escolhendo **a tecla LTI** na listada no canto superior direito da página.

:::image type="content" source="media/OneDrive-LTI-14.png" alt-text="Uma captura de tela mostrando a barra de navegação à esquerda com chaves do desenvolvedor selecionadas e a entrada da chave LTI selecionada em uma lista listada à direita da página.":::

6. Na página Configurar, no **menu** suspenso Método, selecione Colar **JSON** como o método e colar o texto JSON que você copiou na Etapa 5 no campo de texto que aparece.
7. Salve a chave e ela se tornará disponível no Canvas em um **estado** Off. A tecla **Ligar e** copiar a chave dada na coluna **Detalhes** a ser usada na próxima etapa.

:::image type="content" source="media/OneDrive-LTI-19.png" alt-text="A página Canvas com a chave definida em um estado off. Ele precisará ser ligado e a chave precisará ser copiada da coluna de detalhes nesta página.":::

8. Retorne ao portal Microsoft OneDrive registro LTI e colar a chave no campo **ID do Cliente canvas.** Selecione **Próximo** quando estiver pronto.

:::image type="content" source="media/OneDrive-LTI-20.png" alt-text="A página de registro do locatário LTI, que mostra o texto JSON e a caixa de texto na qual a chave deve ser copiada.":::

9. Revise e salve suas alterações. Uma mensagem será exibida no registro bem-sucedido.
10. Os detalhes do registro também podem ser revisados selecionando o botão **Exibir Locatários LTI** na home page.

## <a name="enable-microsoft-onedrive-lti-in-canvas-courses"></a>Habilitar Microsoft OneDrive LTI em Cursos de Tela

Um administrador do Canvas pode habilitar Microsoft OneDrive LTI para todos os cursos. Se Microsoft OneDrive LTI for necessário em um curso específico (e não todos os cursos), o educador do curso precisará seguir as mesmas etapas dentro das configurações do curso.

1. Entre como administrador e vá para **a** seção Configurações.
2. Vá até a **seção Aplicativos** e selecione o botão **Exibir Configurações do** Aplicativo.
3. Selecione o **botão Adicionar Aplicativo.**
4. Na lista **suspenso Tipo de** Configuração, escolha a opção Por **ID do** Cliente.
5. Colar o valor da chave de desenvolvedor gerada anteriormente no campo **ID do** Cliente e selecione o **botão Enviar.**

:::image type="content" source="media/OneDrive-LTI-31.png" alt-text="A página adicionar aplicativo, mostrando a opção Por ID do cliente no menu suspenso Tipo de configuração.":::

## <a name="collaboration-settings-for-microsoft-onedrive-lti-in-canvas-courses"></a>Colaboração Configurações para Microsoft OneDrive LTI em Cursos de Tela

> [!NOTE]
> Para que a colaboração funcione para educadores e alunos, você não deve habilitar a configuração de colaboração. Para garantir que a configuração não está habilitada, siga as etapas abaixo.

1. Entre como administrador e vá para **a** seção Configurações.
1. Vá para **a seção Opções de** Recursos e vá para a seção **Curso.**
1. De definir o recurso Ferramenta de Colaborações **Externas** para não estar habilitado.

> [!NOTE]
> A colaboração pode ser atribuída a alunos individuais e a grupos de alunos. A atribuição a alunos individuais funciona por padrão. Para poder atribuir colaboração ao grupo de alunos, siga estas etapas:

1. Faça logon como administrador e vá para a seção **Chaves do** Desenvolvedor.
1. Encontre a chave com o valor 17000000000710 e de defini-la como **On**.
