# Escapando das ferramentas de qualidade #sqn

Hoje, olhando jornal, em tempos de quarentena do coronavírus, a notícia era de que havia uma super população, dentro do mercado público de Porto Alegre, de pessoas comprando peixe para a sexta-feira santa. O comentário do jornalista foi mais ou menos assim: "Se a povo não tem consciência dos seus atos, a fiscalização deve agir". Não tive como não fazer um link com o assunto aqui, principalmente após entrevistarem uma pessoa que estava no local que disse que a culpa era do estado por não dizer claramente se pode ou não fazer o que estavam fazendo.

Por experiência, e pela história que contei acima, não confie em ninguém, nem em si mesmo, quando o assunto é qualidade. Por isso existe várias técnicas para testar e garantir a qualidade de um código ou uma aplicação:

- TDD
- teste cruzado
- integração contínua
- ...

A fiscalização no nosso código pode ser feita manualmente ou com auxílio de ferramentase para amos a regra é a mesma, NÃO PARE DE FISCALIZAR. Não desligue a regra do linter porque uma parte da aplicação não vai usar ela. Você pode até estar sabendo o que está fazendo, mas o quem chegar no projeto vai fazer errado, não será avisado e vai achar que está certo, aí quero ver você convencer ele do contrário.

### Quebrou o teste?

- Tentar atualizar ele.
- Faz skip dele.
- Remove ele de uma vez que não vai mais incomodar.

### Linter incomodando?

- Qualquer um consegue aguentar ver um sublinhadinho vermelho.
- Se desligar aquela regra vai deixar de sublinhar e normalmente ele sublinha por motivos bobos...
- Qual a forma mais fácil de tirar esse sublinhado? Já que não me deixaram desligar a regra...

### Git Hooks

- Eu sei que tem um negócio aqui que verifica o commit, mas dessa vez ele não rodou, melhor pra mim.
- descobri o comando `git commit --no-verify` agora esse negócio não me pega mais.

### Prettier

- Se ele não fizer o trabalho dele, não vai ser eu que vou.
