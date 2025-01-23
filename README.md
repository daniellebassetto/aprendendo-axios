# Aprendendo Axios

Este projeto tem como objetivo explorar as funcionalidades do Axios, uma biblioteca popular para requisições HTTP. A aplicação demonstra o uso de requisições `GET` e `POST`, interceptores, headers globais, e a criação de uma instância personalizada.

## 📃 Documentação
Acesse a documentação oficial do axios neste link: https://axios-http.com/

## 🌟 Funcionalidades

1. **Requisições GET e POST**: 
   - Obtenção de dados com `GET` e envio de dados com `POST`.
   - Manipulação de requisições e respostas para exibir dados na tela.

2. **Headers Globais**:
   - Configuração de headers comuns, como `Accept` e `Authorization`, usando um arquivo `global.js`.

3. **Interceptores**:
   - Uso de interceptores para executar ações antes de uma requisição ou de uma resposta ser processada.

4. **Instância Personalizada**:
   - Criação de uma instância do Axios com `baseURL` configurado, centralizando chamadas a uma API.

5. **Interação Dinâmica**:
   - Exibição de dados de usuários e criação de posts por meio de um formulário.

## 🛠️ Tecnologias Utilizadas

- **HTML5**
- **JavaScript**
- **Axios**

## 🚀 Exemplos de Uso

### Requisição GET
A requisição `GET` é utilizada para buscar dados e exibi-los na página. 
```javascript
const getData = async () => {
  try {
    const response = await postsFetch.get("/users", {
      headers: {
        "content-type": "application/json",
        custom: "header",
      },
    });
    console.log(response);
    return response.data;
  } catch (error) {
    console.log(error.response);
  }
};
```

### Requisição POST
A requisição `POST` permite enviar novos dados para a API.
```javascript
form.addEventListener("submit", (e) => {
  e.preventDefault();

  postsFetch.post("/posts", {
    title: titleInput.value,
    body: bodyInput.value,
    userId: 1,
  });
});
```

### Instância Personalizada
No arquivo `custom.js`, configuramos uma instância do Axios com um `baseURL`:
```javascript
const postsFetch = axios.create({
  baseURL: "https://jsonplaceholder.typicode.com",
});
```

### Headers Globais
No arquivo `global.js`, definimos headers comuns para todas as requisições:
```javascript
axios.defaults.headers.common["Accept"] = "application/json";
axios.defaults.headers.common["Authorization"] = "TOKENDOAPP";
```

### Interceptores
Interceptores foram configurados para modificar ou inspecionar as requisições e respostas:
```javascript
// Requisição
postsFetch.interceptors.request.use(
  (config) => {
    console.log("Antes da requisição...");
    return config;
  },
  (error) => Promise.reject(error)
);

// Resposta
postsFetch.interceptors.response.use(
  (response) => {
    console.log("Antes da resposta...");
    return response;
  },
  (error) => Promise.reject(error)
);
```

## 📝 Como Executar

1. Clone este repositório:
   ```bash
   git clone https://github.com/daniellebassetto/aprendendo-axios.git
   cd aprendendo-axios
   ```

2. Abra o arquivo `index.html` no navegador para visualizar o projeto.

## 🤝 Contribuições

Contribuições são **muito bem-vindas**! 💡  
Abra uma *issue* ou envie um *pull request* para melhorias e sugestões. Vamos deixar esse projeto ainda mais incrível juntos! 🎉

## 📜 Licença

Este projeto está sob a **Licença MIT**. 📝  
Sinta-se livre para usá-lo, modificá-lo e compartilhá-lo! 😊


## 🌟 Obrigado por conferir este projeto! 🌟  
Se você gostou, deixe uma estrela ⭐ no repositório e compartilhe com seus amigos. 🚀
