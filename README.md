# Escapando das ferramentas de qualidade #sqn

Hoje, olhando jornal, em tempos de quarentena do coronavírus, a notícia era de que havia uma super população, dentro do mercado público de Porto Alegre, de pessoas comprando peixe para a sexta-feira santa. O comentário do jornalista foi mais ou menos assim: "Se a povo não tem consciência dos seus atos, a fiscalização deve agir". Não tive como não fazer um link com o assunto aqui, principalmente após entrevistarem uma pessoa que estava no local que disse que a culpa era do estado por não dizer claramente se pode ou não fazer o que estavam fazendo.

Por experiência, e pela história que contei acima, não confie em ninguém, nem em si mesmo, quando o assunto é qualidade. Por isso existe várias técnicas para testar e garantir a qualidade de um código ou uma aplicação:

- TDD
- teste cruzado
- integração contínua
- ...

A fiscalização no nosso código pode ser feita manualmente ou com auxílio de ferramentase para amos a regra é a mesma, NÃO PARE DE FISCALIZAR. Não desligue a regra do linter porque uma parte da aplicação não vai usar ela. Você pode até estar sabendo o que está fazendo, mas o quem chegar no projeto vai fazer errado, não será avisado e vai achar que está certo, aí quero ver você convencer ele do contrário.

Abaixo algumas "piadas" do que pode acontecer se a ficalização baixar a guarda.

## Testes unitários

Ah os testes, "foram feitos para serem quebrados" (o mal em pessoa).

Identificando de que lado você está:

- se ninguém pedir vocês faz testes? (não - mal | sim - bom)
- você se baseia na cobertura exigida ou em garantir que nenhum cenário ficou sem testar? (1 - mal | 2 - bom)

Jornada do vilão

1. Tentar atualizar o teste para se adaptar ao novo código.
2. Botar para ignorar aquele teste para alguma hora resolvê-lo.
3. Remove ele de uma vez que não vai mais incomodar.

Jornada do mocinho

1. Cria uns testes e incentivar a galera.
2. Ninguém mais fez teste, porque:
  - Não sabe como cria um teste.
  - Não sabe como testa aquela parte da aplicação.
  - Não acha que seja importante naquela parte do código
3. O mocinho investe em treinamentos.
4. O pessoal começa fazer testes, mas também começa a quebrar os testes dos outros.
5. O mocinho coloca um pre-commit validando os testes
6. Não sabe como, mas os testes ainda continuam quebrando (pessoal desliga os pre-commits)
7. Mocinho cria integração contínua validando os testes
8. Galera diz que isso está atrasando o deploy

## Linter

Jornada do bem contra o mau

- **mocinho** - vou colocar esse linter aqui, meus colegas vão ver que o código deles estão com erros e vão poder melhorar a escrita deles.
- **vilão** - Qualquer um consegue aguentar ver um sublinhadinho vermelho.
- **mocinho** - Mas que coisa, o contraste da tela do meu colega deve estar ruim e ele não viu o erro ali, ou talvez não botou a extensão que precisava, por garantia vou incluir isso no build aí se não escrever certo não ele vai perceber que não funcionou.
- **vilão** - Que m#### é essa? Não bilda mais? Ah esse negócio de linter, para o que eu estou fazendo não tem sentido, vou desligar essas regras aqui.
- **mocinho** - 😔 Oi colega, eu vi que você desligou várias regras do nosso linter, poderia saber por quê?
- **vilão** - Eu vi que tava sublinhando por uns motivos bobos, que não tinha sentido no que eu estava desenvolvendo.
- **mocinho** - Mas o linter serve para todo o projeto, então se você desligar, afetará todos os outros.
- **vilão** - Verdade, não farei mais.
- **vilão** - Nossa, o linter ta pedindo para eu quebrar essa linha porque passa de 80 caracteres, mas vai ficar muito feio. Hmmm da para desligar o linter nessa linha aqui.
- **mocinho** - 😠 Ah não, maldito, o que você está pensando ao desligar toda regra que ele não quer seguir?
- **vilão** - Não vi sentido nelas
- **mocinho** - 😤 mas isso é para nosso código ter um padrão e se essa regra está aí é porque tem um motivo
- **vilão** - Ta, ta certo, entendi agora.
- **vilão** - Qual a forma mais fácil de tirar esse sublinhado? Já que meus colegas chatos não me deixaram desligar a regra...
- **mocinho** - 🥴

## Git Hooks

Jornada do vilão

1. Eu sei que tem um negócio aqui que verifica o commit, mas dessa vez ele não rodou, melhor pra mim.
2. descobri o comando `git commit --no-verify` agora esse negócio não me pega mais.

## Prettier

1. Se ele não fizer o trabalho dele, não vai ser eu que vou.
2. Essa vírgula não vai mudar a vida de ninguém.

## Escolha o seu lado

As conversas e jornadas mostradas acima são exemplos extremos de conflitos que podem acontecer quando a ideias divergentes entre os membros de uma equipe. Já se questionou de que lado você está?
