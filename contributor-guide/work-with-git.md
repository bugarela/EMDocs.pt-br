<properties pageTitle="Comandos do Git para criação de um novo artigo ou atualização de um artigo existente" description="Etapas para trabalhar com repositórios de GitHub com conteúdo técnico do Azure ." metaKeywords="" services="" solutions="" documentationCenter="" authors="v-jocgar" videoId="" scriptId="" manager="robmazz" />

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm="" ms.workload="" ms.date="02/24/2016" ms.author="v-jocgar" />

# Como trabalhar com Git

Tarefas Pendentes:
- [ ] Nº 22 Substituir URL do EMS para artigos concluídos (veja o final das instruções)

## Processo padrão (trabalhando em uma ramificação)
Execute as etapas neste artigo para criar uma ramificação de trabalho local em seu computador para que você possa criar um novo artigo para a seção de documentação técnica do Microsoft.com/ems ou atualizar um artigo existente.

1. Inicie o Git Bash. 

2. Altere para o repositório `emdocs`:

        cd emdocs
        
3. Crie uma nova ramificação de trabalho:

        git checkout <branchname>

4. Crie uma nova ramificação de trabalho local:

        git pull origin master:<branchname>

5. Crie seu novo artigo ou faça alterações em um artigo existente. Use Atom (http://atom.io) como seu editor de Markdown (ou outro editor de sua preferência) para criar e abrir novos arquivos de Markdown. Depois de criar ou modificar o artigo e as imagens, vá para a próxima etapa.

6. Adicione e confirme quaisquer arquivos novos que você criou:

        git add <path-to-file>
        git commit –m "<comment>"
        
   Ou, para confirmar somente os arquivos específicos que você modificou:

        git commit -a –m "<comment>"

7. Informe a sua origem que você criou a ramificação de trabalho local:

        git push origin <branchname>

8. Envie as alterações por push para a ramificação no GitHub:

        git push origin <branchname>

9. Quando você estiver pronto para enviar seu conteúdo para a ramificação mestre para preparação, validação e/ou publicação, na interface de usuário do GitHub, crie uma Solicitação Pull de sua ramificação para a ramificação mestre.

10. O destinatário da solicitação pull analisa sua solicitação pull, fornece comentários e/ou aceita sua solicitação pull. 

11. Como opção, verifique o artigo publicado ou as alterações em
<span style="color:red;">É necessário obter a URL correta para exibir os artigos publicados.</span>
 http://docs.microsoft.com/ems/articles/name-of-your-article-without-the-MD-extension


<!--HONumber=Mar16_HO1-->


