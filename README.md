## Exemplo do TCC.

### Plugin usando Framework Moça Bonita dentro do WordPress.

> Ferramentas utilizadas para construção e testes do Framework.

- WordPress;
- PHP;
- PHP-PSR;
- PHP-Xdebug;
- Composer;
- Symfony Framework;
- Laravel Framework;
- Docker;
- Docker Compose.

### Links relacionados

[WordPress](https://br.wordpress.org/)

[Framework Moça Bonita](https://github.com/jhorlima/wp-mocabonita)

[Plugin de Exemplo - Agenda de Contato](https://github.com/jhorlima/agenda-contatos)

### Como testar

> É obrigatório ter o Docker e o Docker Compose instalados no computador para executar este projeto.

Para gerar as imagens necessárias da aplicação, execute:

```bash
docker-compose build
```

Depois, é necessário criar os containers, então execute:

```bash
docker-compose up -d
```

*Pronto, a aplicação já está quase pronta para uso! Simples **:D***

*PS: O container do composer pode demorar um pouco mais do que os outros, pois ele é responsável por baixar todas as dependências do plugin, portanto é recomendado esperar ele ser encerrado para ativar o plugin. Execute o comando abaixo para acompanhar este container.*

```bash
docker-compose logs -f composer
```

----------

**Descrição das portas usadas pelos containers**:

 - **80** é usada para acesso ao WordPress.
 - **8080** é usada para acessar o PhpMyAdmin.
 - **3306** é usada para gerenciar o banco de dados MySql.
 - **9000**,  **35729** e **9876** são usadas para realizar debug no PHP.

----------

### Obrigado!