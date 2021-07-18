# Boas práticas do Vue.js

Uma lista de melhores práticas e guias de estilo para usar no VueJs.

Os pontos abaixo são alguns deles relacionados à funcionalidade / otimização, outros são convenções de nomenclatura e ordem de elementos do VueJs.

## 1. Sempre use 'kebab case' para nomes de eventos personalizados

- Por quê?
  - Porque os eventos serão transformados automaticamente em `kebab-case`. Nós nunca vamos estar ouvindo um evento em `camelCase` ou `PascalCase`, portanto, faz mais sentido declarar o evento da mesma maneira que vamos ouvi-lo: no caso do 'kebab case'.

```javascript
this.$emit('meu-evento');
```

```javascript
v-on:meu-evento //Ouvindo o evento;
```

## 2. Sempre use 'chaves' em loops v-for

- Por quê?
  - É uma prática recomendada comum sempre adicionar uma `:key` aos loops de seu modelo. Uma chave `v-for` sem *:key* pode levar a erros difíceis de encontrar, especialmente com animações.

## 3. Use `PascalCase` ou `kebab-case` para componentes de arquivo único

- Por quê?
  - O PascalCase tem uma melhor integração com os editores e permite uma melhor funcionalidade de preenchimento automático / importação entre os IDEs comumente usados.
  -O caso do kebab é o caminho a percorrer se quisermos evitar problemas com sistemas de arquivos que não diferenciam maiúsculas de minúsculas.

## 4. Nunca use `v-if` no mesmo elemento que `v-for`

- Por quê?
  - Este é um assassino de desempenho, quanto maior a lista, mais desempenho sofrerá com essa prática ruim.

## 5. Nome de `props` devem sempre usar `camelCase` na sua declaração, mas `kebab-case`, nos templates e JSX.

Mau exemplo:
```javascript
props: {
  'greeting-text': String
}
<WelcomeMessage greetingText="hi"/>
```

Bom exemplo:
```javascript
props: {
  greetingText: String
}
<WelcomeMessage greeting-text="hi"/>
```


## Referências

- <https://vuejs.org/v2/style-guide/#Component-instance-options-order-recommended>
- <https://vuejs-tips.github.io/cheatsheet/>
- <https://blog.usejournal.com/vue-js-best-practices-c5da8d7af48d>
