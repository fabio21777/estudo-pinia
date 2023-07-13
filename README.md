# vue com pinia

### oque é o pinia

O Pinia é o gerenciador de estados do Vue3. Com o Pinia, é possível compartilhar estados reativos em toda a aplicação. Esse compartilhamento de estados reativos é extremamente útil quando trabalhamos com componentização.

Para ilustrar melhor, vamos a um exemplo. Suponhamos que em nossa aplicação Vue, precisaremos de modais para exibir mensagens ou notificações para os usuários. Uma solução seria criar um componente modal que seria adicionado a todos os componentes que necessitam do modal.

No entanto, a solução mencionada anteriormente não seria a ideal. Isso porque uma página pode conter diversos componentes que precisam de modal, o que implicaria em adicionar o modal em vários outros componentes. Isso pode se tornar um problema se a sua aplicação escalar.

Para Solucionar o problema podemos ter um unico modal adicionado no "App.vue", qué o componente raiz do projeto podemos passa para todos os componentes uma propriedade chamada modal ativo "activeModal", que poderia ser uma string que identificaria qual modal está ativo no momento, os componentes filhos emitiriam o evento com a string para definimos qual modal ficará ativo, Opa :) !! problema sulucionado

Mas uma vez, essa solução não é a ideal, pois para projetos mais complexos é comum que haja diversos níveis como filho (nível 1), neto (nível 2), bisneto (nível 3), ... muitos tataranetos (nível n). Nesses casos, ocorreria a necessidade de emitir o evento com a minha prop até o componente raiz.  

Para esse caso podemos criar um gerenciado de modais "modalHandle", será um componente vue responsavel por gerencia qual modal está ativo no momento por padrão o valor null representrá que não existe, modal ativo no momento  

### Instalçao pinia
instalando pinia, se vc utilizar o comando ```sh npm create vue@3```, na instalação do projeto vue vc pode escolher utilizar o pinia, instalações padrões do vue não instalam pinia por padrão comando para instalação ```sh npm install pinia```

### Criando p