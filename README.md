# Desafio Observabilidade Pagar.me

### Objetivo

Esse desafio tem como objetivo garantir o que todos adoramos: ser preguiçosos!
E é por causa disso que gostamos de automatizar tanto. Para conseguir fazer mais com
menos. Ou melhor ainda! Não fazer nada e deixar a máquina trabalhar pra gente.
Ele é dividido em alguns pedaços que, embora separados, andam juntos.

## A aplicação

Crie uma API HTTP simples, em Python, que retorne na sua resposta algum valor
dinâmico, como o horário da requisição, um inteiro aleatório.

Com a aplicação em mãos, sabemos que rodar ela localmente pode ser bem diferente do que
rodar em um servidor de produção.
Alguns problemas comuns da diferença desses ambientes são:

	● Bibliotecas não instaladas
	● Executáveis não instalados
	● Caminhos não configurados
	● E até diversos problemas místicos

Para facilitar a vida, de alguns anos para cá, existe o Docker . Com ele conseguimos diminuir os problemas que citamos acima e diminuir e muito o famoso “funciona na minha máquina”.

Bora aplicar esse conceito então? Faça a sua aplicação funcionar em Docker.

Você vai perceber que mesmo utilizando o docker temos que digitar um comando meio grandinho e “estranho” toda vez que queremos subir o container com a nossa aplicação rodando (isso que estamos falando de um container só, imagina vários ao mesmo tempo).

Lembre-se que somos preguiçosos e o que gostamos de fazer é no máximo digitar poucas coisas no terminal. Lembre-se também, que reinventar a roda é perda de tempo e de dinheiro! A comunidade já fez uma ferramenta que ajuda e muito nisso (e não, não é um shell script).
Detalhe: Essa ferramenta fez tanto sucesso que a própria Docker.inc comprou essa ferramenta e agora ela faz parte do “pacote oficial” de ferramentas.

Use essa ferramenta para facilitar mais ainda a subida da sua aplicação.

## A confiabilidade

Mesmo com todo o cuidado do mundo ao escrever o código de uma aplicação, sabemos que bugs existem e podem acontecer com qualquer aplicação, desde as mais simples até as mais complexas e críticas.

Mesmo com processos de revisão e testes de código, não podemos nos dar ao luxo de ter apenas a camada de código como garantia de qualidade e confiabilidade. Para isso, existem diversos conceitos e ferramentas que nos ajudam a extrair informações de como a aplicação está se comportando durante a sua execução.

Descreva e/ou aplique os conceitos de observabilidade e confiabilidade que você tenha experiência para gerar informações sobre a saúde da aplicação.

## O entregável
Entregue o bundle do repositório git em que você foi fazendo o desafio.
Basta executar um:

```
git bundle create myrepo.bundle --all
```

Lembre-se que o queremos, na medida do possível, é:

	● Rodar um comando e garantir que a sua aplicação está rodando nas nossas máquinas;
	● Ter visibilidade da saúde da aplicação sem precisar olhar em vários lugares diferentes.
E além disso, nos diga, em um arquivo no repositório, como fazer tudo isso.
