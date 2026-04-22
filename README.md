JDBC DAO Project
Sobre o projeto

Este repositório demonstra a implementação do padrão DAO (Data Access Object) utilizando JDBC em Java.
O objetivo é separar a lógica de acesso a dados da lógica de negócio, tornando o código mais organizado, reutilizável e fácil de manter.
Tecnologias utilizadas

    Java SE

    JDBC (Java Database Connectivity)

    MySQL (pode ser adaptado para outros bancos)

Estrutura do projeto

    src/ → código fonte principal

        dao/ → classes DAO responsáveis pelo acesso ao banco

        entities/ → classes de modelo (entidades)

        db/ → utilitários de conexão e tratamento de exceções

        application/ → classes de teste e execução

Configuração

    Crie um banco de dados no MySQL (exemplo: coursejdbc).

    Configure as tabelas necessárias (exemplo: department, seller).

    Ajuste o arquivo de conexão (db.properties) com suas credenciais:
    properties

    user=root
    password=1234
    url=jdbc:mysql://localhost:3306/coursejdbc
    useSSL=false

    Compile e execute o projeto.

Exemplos de uso
Criando um novo registro
java

Seller newSeller = new Seller(null, "João", "joao@gmail.com", new Date(), 3000.0, department);
sellerDao.insert(newSeller);
System.out.println("Inserted! New id = " + newSeller.getId());

Atualizando um registro
java

Seller seller = sellerDao.findById(1);
seller.setName("Maria");
sellerDao.update(seller);
System.out.println("Update completed!");

Deletando um registro
java

sellerDao.deleteById(3);
System.out.println("Delete completed!");

Padrão DAO

O padrão DAO facilita:

    Encapsular operações de banco em classes específicas.

    Reduzir duplicação de código SQL.

    Manter a aplicação desacoplada da camada de persistência.

Licença

Este projeto é de uso livre para fins de estudo e aprendizado.
