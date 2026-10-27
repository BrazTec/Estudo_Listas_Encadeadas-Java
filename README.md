# Anotações de Java: listas encadeadas

Material didático para comparar quatro estruturas que armazenam elementos `String`. Os fontes ficam em `AED-Java-master/src/`.

## Mapa de leitura

| Pasta sob `src/` | Estrutura | Classe principal |
| --- | --- | --- |
| `LSE/src/listaSimplesmenteEncadeada/` | Simplesmente encadeada | `SLinkedList` |
| `LDE/src/listaDuplamenteEncadeada/` | Duplamente encadeada | `DLinkedList` |
| `LCSE/src/listaCircularSimplesmenteEncadeada/` | Circular simples | `CSLinkedList` |
| `LCDE/src/listaCircularDuplamenteEncadeada/` | Circular dupla | `CDLinkedList` |

Cada variante possui uma classe de nó, uma exceção para remoção em lista vazia e testes em sua pasta `src/tests/`. Os nomes de pacote incluem as pastas intermediárias, por exemplo `LSE.src.listaSimplesmenteEncadeada`.

## Conceitos presentes

- Nós guardam o elemento e referências para o próximo nó; nas listas duplas, também para o anterior.
- As listas lineares mantêm `head`, `tail` e `size`.
- As circulares mantêm `tail`; o início é `tail.getNext()`. Com um único nó, a ligação fecha sobre ele mesmo.
- Todas oferecem `addHead`, `addTail`, `removeFirst`, `getSize` e `toString`. `removeLast` existe em LDE, LCSE e LCDE, mas não em LSE.
- Na circular simples, remover o último requer percorrer os nós para encontrar o anterior. Na dupla, a referência `prev` permite encontrá-lo diretamente.

## Como estudar e executar

Configure um JDK e marque `AED-Java-master/src` como raiz de fontes. Para os testes, adicione JUnit Jupiter (JUnit 5) na IDE e execute as quatro classes `*Test`. Não há configuração Maven/Gradle nem dependências de teste incluídas.

Os testes verificam inserções, remoções, representação textual e exceções em lista vazia. Sua existência não comprova execução nesta revisão documental.

`src/Main.java` é o exemplo inicial da IDE e não demonstra as listas. A pasta `out/production/` contém arquivos `.class` versionados; use os fontes de `src/` como referência e recompile no seu ambiente.

## Roteiro sugerido

1. Leia o nó e `SLinkedList`, acompanhando alterações de `head` e `tail`.
2. Compare com `DLinkedList` e a manutenção de `prev`.
3. Estude a condição de parada do percurso circular.
4. Simule lista vazia, um nó e vários nós; compare com os testes.

Não é uma biblioteca de coleções pronta para produção. Esta revisão mantém fontes, testes, configuração da IDE e arquivos compilados existentes.
