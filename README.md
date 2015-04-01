
# Documentação de como escrever um NASA CSS 

Aqui segue uma documentação de escrita para desenvolvimento CSS.
Fazendo de tudo para seguir os melhores padrões existentes e com a intenção de
fazer um simples arquivo css se tornar uma obra de arte no desenvolvimento web.

> "A mente que se abre a uma nova idéia jamais voltará ao seu tamanho original." - Albert Einstein

Esse é um documento vivo e novas ideias são sempre bem-vindas. Por favor
contribua.


## Índice

1. [Princípios](#principles)
2. [Espaços em branco](#whitespace)
3. [Comentários](#comments)
4. [Formatação](#format)
5. [Nomeando](#naming)
6. [Exemplo prático](#example)
7. [Organização](#organization)
8. [Build e deploy](#build-and-deployment)
9. [Otimização](#otimization)

[Agradecimentos](#acknowledgements)


<a name="principles"></a>
## 1. Princípios
> "Organização é o princípio de tudo, mantê-la significa competência." - Alfredo Valente Júnior

* Todo código deve parecer como se tivesse sido escrito
  por uma única pessoa, mesmo tendo sido escrito por uma equipe.
  Se dentro de sua equipe é possivel indentificar pelo código quem
  o escreveu alguma coisa está errada.
* O padrão proposto tem que ser cumprido senão de nada adianta seguir
  qualquer padrão.
* //Aqui ainda falta coisas a refletir


<a name="whitespace"></a>
## 2. Espaços em branco

Apenas um estilo deve existir em todo o projeto. Seja sempre consistente na
utilização de espaços em branco. Use espaços em branco para melhorar a
legibilidade.

* _Nunca_ misture espaços e tabs para indentação.
* Escolha entre indentação suave (espaços) ou tabulação. Atenha-se à sua
  escolha sem falhar. (Preferência: espaços)
* Se usar espaços, escolha o número de caracteres usados por nível de
  indentação.  (Preferência: 4 espaços)

Dica: configure seu editor para "mostrar invisíveis". Isso irá permitir que
você elimine espaços em branco da quebra de linha, elimine espaços em branco de
linhas vazias sem indentação e evite commits poluídos.

Dica: use um [EditorConfig](http://editorconfig.org/) arquivo (ou equivalente) para ajudar a menter a convenção básica de espaços em branco que você aceitou para sua base de código.


<a name="comments"></a>
## 3. Comentários

Código bem comentado é extremamente importante. Tire tempo para descrever
componentes, como eles funcionam, suas limitações, e o modo como são
construídos. Não deixe outros no time adivinharem o propósito de códigos
incomuns ou não óbvios.

Estilo de comentário deve ser simples e consistente dentro de uma única base de
código.

* Coloque comentários em uma nova linha acima do seu assunto.
* Evite comentários no fim da linha.
* Mantenha o comprimento da linha a um máximo sensível, por exemplo, 80
  colunas.
* Faça o uso liberal de comentários para quebrar o código CSS em seções
  distintas.
* Use comentários com iniciais maiúsculas e indentação de texto consistente.

Dica: configure seu editor para lhe prover com atalhos a geração do padrão de
comentários acordado.

#### exemplo com CSS:

```css
/*====================================*\
    Fonts
\*====================================*/

/* Comentário básico */
 
/**
 * Breve descrição usando o estilo de formato de comentário Doxygen
 *
 * A primeira frase da descrição longa começa aqui e continua
 * nesta linha por um tempo finalmente concluindo aqui no final deste parágrafo.
 *
 * A descrição longa é ideal para explicações mais detalhadas e documentação.
 * Ele pode incluir HTML exemplo, URLs, ou qualquer outra informação
 * que seja considerada necessária ou útil.
 *
 * @tag Esta é uma tag chamada 'tag'
 *
 * @todo Esta é uma declaração de tarefas que descreve uma tarefa atômica para ser 
 * concluída numa data posterior. Ela envolve depois de 80 caracteres e as linhas a
 * seguir são Recuado por dois espaços.
 */


```


<a name="format"></a>
## 4. Formatação

O formato de código escolhido deve garantir que o código seja: fácil de ler;
fácil de comentar claramente; minimize a chance de introduzir erros
acidentalmente; e resulte em úteis visualizações de diferença.

* Um seletor discreto por linha em um conjunto de regras com multi-seletores.
* Um único espaço antes da abertura das chaves em um conjunto de regras.
* Uma única declaração por linha em um bloco de declarativo.
* Um nível de indentação para cada declaração.
* Um único espaço depois dos dois pontos de uma declaração.
* Use valores minúsculos e abreviações hexadecimais, por exemplo, `#aaa`.
* Use aspas simples ou duplas de forma consistente. Preferência é por aspas duplas,
   por exemplo, `conteúdo:" "`.
* Citação valores de atributos em seletores, por exemplo, `input [type="checkbox"]`.
* _Onde for permitido_, evitar especificar unidades para zero valores, por exemplo, `margin: 0`.
* Inclua um espaço após cada vírgula em propriedades separadas por vírgula ou valores de funções.
* Sempre inclua um ponto-e-vírgula no fim da última declaração em um bloco
   declarativo.
* Coloque o fechamento das chaves na mesma coluna que o primeiro caracter do
   conjunto de regras.
* Separe cada conjunto de regras por uma linha em branco.

```css
.selector-1,
.selector-2,
.selector-3 {
    -webkit-box-sizing: border-box;
    -moz-box-sizing: border-box;
    box-sizing: border-box;
    display: block;
    color: #333;
    background: #fff;
}
```

#### Ordem de declaração

Declarações devem ser ordenadas segundo um único princípio. Minha preferência é
por propriedades relacionadas para serem agrupadas e por propriedades
estruturalmente importantes (por exemplo, posicionamento e box-model) para
serem declaradas antes de propriedades tipográficas, fundo ou cor.

```css
.selector {
    /* Posicionamento */
    position: absolute;
    z-index: 10;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;

    /* Display & Modelo de Caixa */
    display: inline-block;
    overflow: hidden;
    box-sizing: border-box;
    width: 100px;
    height: 100px;
    padding: 10px;
    border: 10px solid #333;
    margin: 10px;

    /* Outros */
    background: #000;
    color: #fff;
    font-family: sans-serif;
    font-size: 16px;
    text-align: right;
}
```

Ordenação alfabética também é popular, mas a desvantagem é que ela separa as
propriedades relacionadas. Por exemplo, deslocamentos de posição não são mais
agrupados e propriedades do box-model podem acabar propagando ao longo de um
bloco de declaração.

#### Exceções e ligeiros desvios

Grandes blocos de declarações individuais podem atuar de forma diferente,
através da formatação de linha única. Nesse caso, um espaço deve ser
considerado depois da abertura das chaves e antes do fechamento das chaves.

```css
.selector-1 { width: 10%; }
.selector-2 { width: 20%; }
.selector-3 { width: 30%; }
```

Longos valores de propriedades separados por vírgula - como coleções de
degradês ou sombras - podem ser organizados em várias linhas em um esforço para
melhorar a legibilidade e produz visualizações de diferença mais úteis. Existem
vários formatos que poderiam ser usados; um exemplo é mostrado abaixo.

```css
.selector {
    background-image:
        linear-gradient(#fff, #ccc),
        linear-gradient(#f3c, #4ec);
    box-shadow:
        1px 1px 1px #000,
        2px 2px 1px 1px #ccc inset;
}
```

#### Miscelânea

* Use valores hexadecimais em letras minúsculas, por exemplo: `#aaa`.
* Use aspas simples ou duplas de forma consistente. Preferência por aspas
  duplas, por exemplo: `content: ""`.
* Sempre coloque aspas em valores de atributos nos seletores, por exemplo:
  `input[type="checkbox"]`.
* _Onde permitido_, evite especificar unidades para valores-zero, por exemplo:
  `margin: 0`.


<a name="naming"></a>
## 5. Nomeando

Você não é um compilador/compressor de código humano, então não tente ser.

Use nomes claros e previdentes para classes HTML. Escolha um padrão de nomes
compreensível e consistente que faça sentido para arquivos HTML e arquivos
CSS.

```css
/* Exemplo de código com nomes ruins */

.s-scr {
    overflow: auto;
}

.cb {
    background: #000;
}

/* Exemplo de código com bons nomes */

.is-scrollable {
    overflow: auto;
}

.column-body {
    background: #000;
}
```


<a name="example"></a>
## 6. Exemplo prático

Um exemplo de várias convenções.

```css
/* ==========================================================================
   Grid layout
   ========================================================================== */

/*
 * Layout da coluna com scroll horizontal.
 *
 * Isso cria uma única linha de altura completa, não-envolvendo colunas que podem
 * ser navegadas na horizontal dentro de seu pai.
 *
 * Exemplo de HTML:
 *
 * <div class="grid">
 *     <div class="cell cell-5"></div>
 *     <div class="cell cell-5"></div>
 * </div>
 */
 
/**
 * Grid container
 * Deve conter apenas filhos de `.cell`
 */

.grid {
    overflow: visible;
    height: 100%;
    /* Prevent inline-block cells wrapping */
    white-space: nowrap;
    /* Remove inter-cell whitespace */
    font-size: 0;
}

/**
 * Grid cells
 * Largura não-explícita por padrão. Extenda com classes `.cell-n`.
 */

.cell {
    box-sizing: border-box;
    position: relative;
    overflow: hidden;
    width: 20%;
    height: 100%;
    /* Set the inter-cell spacing */
    padding: 0 10px;
    border: 2px solid #333;
    vertical-align: top;
    /* Reset white-space */
    white-space: normal;
    /* Reset font-size */
    font-size: 16px;
}

/* Cell states */

.cell.is-animating {
    background-color: #fffdec;
}

/* Cell dimensions
   ========================================================================== */

.cell-1 { width: 10%; }
.cell-2 { width: 20%; }
.cell-3 { width: 30%; }
.cell-4 { width: 40%; }
.cell-5 { width: 50%; }

/* Cell modifiers
   ========================================================================== */

.cell--detail,
.cell--important {
    border-width: 4px;
}
```


<a name="organization"></a>
## 7. Organização

Organização de código é uma importante parte de qualquer base de código CSS, e
crucial para grandes bases de código.

* Separar logicamente distintas partes do código.
* Usar arquivos separados (concatenados por um processo de build) para ajudar a
  dividir código para componentes distintos.
* Se estiver usando um pré-processador, abstrair partes comuns de código em
  variáveis para cor, tipografia, etc.


<a name="build-and-deployment"></a>
## 8. Build e deploy

Os projetos devem sempre tentar incluir alguns meios genéricos pelos quais sua
fonte possa ser avaliada, testada, comprimida e versionada em preparação para
uso em produção.  Para essa tarefa, o [grunt](https://github.com/cowboy/grunt)
por Ben Alman é uma excelente ferramenta.

<a name="otimization"></a>
## 9. Otimização

Por exemplo não colocar ponto e virgula no último elemento

