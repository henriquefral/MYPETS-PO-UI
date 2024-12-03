# Projeto com PO-UI! 

PO-UI é um componente em Angular, que fornece uma construção rápida de menus e interfaces. 

É um componente que a a TOTVS vem utilizando em seus programas mais recentes. Portanto, cabe o estudo!

## Pré requisitos

- Instalação do [node.js](https://nodejs.org/en);
- Angular-cli.
  - Instalação por ``` npm install -g @angular-cli@18 ``` (após instalação do node.js).
    - É importante que esteja na versão 18, caso contrário pode dar problemas nas dependências de pacotes do projeto (bem vindo aos projetos em javascript.)
   
O node.js é responsável por executar os códigos JavaScript. Se tornando necessário para usar um componente construído em Javscript.

O angular-cli é uma pacote javascript feito para automatizar a criação de um projeto em angular, com a estrutura já construída.

## Iniciando o projeto

Após instalar o Angular-cli, é preciso criar um novo projeto.

A [documentação oficial do PO-UI](https://po-ui.io/guides/getting-started) sugere que você faça isso sem baixar as dependências, para que seja feita uma conferência antes. 
- ```ng new MYPETS-PO-UI --skip-install```

Porém, você pode fazer a inicialização do projeto normalmente, da seguinte forma:
- ``` ng new MYPETS-PO-UI ```

Assim que inicializar a instalação, ele irá segerir dois pontos:
- O formato de estilização a ser utilizado no projeto: Pode selecionar o formato CSS;
- Se você quer habilitar a renderização do lado do servidor (SSR) e a geração de sites estáticos: Não. Durante os testes eu tentei fazer com o ssr, mas tive alguns impedimentos. Como é uma demonstração, seguiremos o projeto sem o ssr.

Agora entre na pasta raiz do projeto que você acabou de criar.

Após iniciar o projeto, vamos incluir a biblioteca de componentes do PO-UI (finalmente!) com o seguinte comando:
```ng add @po-ui/ng-components```

Durante a instalação, ele irá perguntar se nós queremos configurar o menu lateral, informe que sim e siga.

Ele irá fazer a configuração inicial dos componentes da biblioteca PO-UI. 

Tanbém já recomendo você baixar o tema do PO-UI, fornecido pela TOTVS:
```npm i @totvs/po-theme```

Para subir o projeto no ar, execute o seguinte comando:
``` ng serve ```

E voilá, no terminal onde foi excecutado o comando acima irá aparecer a URL e a porta onde o projeto está hospedado.

Acesse e veja, sua criação tomou vida (não é complexa, muito menos bonita, mas é o primeiro passo!).

Para você dar sequência, você precisa incluir o módulo do PoUi nos componentes da sua aplicação Angular.
No caso do meu projeto, eu precisei editar o app.components.ts. 

Importando o seguinte componente:
```import { PoModule } from '@po-ui/ng-components';```

E adicionando na lista de componentes:
```
@Component({
  selector: 'app-root',
  standalone: true,
  imports: [
    CommonModule,
    RouterOutlet,
    PoToolbarModule,
    PoMenuModule,
    PoPageModule,
    PoModule
  ],
...
```

Se você instalou o po-theme, da TOTVS, você deve ir no arquivo angular.json, e procurar pelo item "styles" no json, ao localizar, adicione os seguintes itens:
```
"styles": [
  "node_modules/@totvs/po-theme/css/po-theme-default-variables.min.css",
  "node_modules/@totvs/po-theme/css/po-theme-default.min.css",
  "node_modules/@po-ui/style/css/po-theme-core.min.css",
]
```


