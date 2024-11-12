# Java e Spring Boot - Preparação para Entrevista Técnica

Este repositório contém um resumo detalhado dos principais conceitos de Java e Spring Boot, incluindo ferramentas de monitoramento e logging, arquitetura de microserviços, filas de mensagens, design patterns, testes, modificadores de acesso e encapsulamento. Cada tópico é abordado com exemplos práticos de experiência, para demonstrar o uso real em projetos e fornecer uma base sólida para entrevistas técnicas.

---

## 1. Ferramentas de Monitoramento e Logging

- **Grafana**: "O Grafana é uma ferramenta de visualização de dados muito usada para monitorar métricas e criar dashboards. Com o Grafana, consigo integrar várias fontes de dados, como Prometheus, para monitorar APIs, verificar tempos de resposta e acompanhar a saúde do sistema em tempo real. Essa visualização é essencial para detectar anomalias rapidamente."

- **AWS CloudWatch**: "No caso de sistemas na AWS, o CloudWatch é uma ferramenta nativa para monitoramento e logs, onde podemos criar alarmes para monitorar o uso de recursos (CPU, memória) e detectar possíveis falhas antes que impactem o usuário. O CloudWatch Logs, por exemplo, centraliza todos os logs e facilita a análise."

- **Log4J para Logging**: "Utilizo o Log4J para gerenciar logs de acordo com a gravidade. Quando encontro exceções, uso o nível `ERROR` para registrar o problema, e para alertas sobre algo inesperado, mas que não vai interromper o serviço, utilizo `WARNING`. Essa diferenciação é importante para priorizar problemas críticos no monitoramento."

---

## 2. Arquitetura HASH e Microserviços Independentes

- **Arquitetura HASH**: "HASH e HASHFULL são abordagens de estrutura de dados usadas em bancos de dados e sistemas distribuídos para aumentar a eficiência de consultas. HASH ajuda a localizar dados rapidamente em sistemas de chave-valor, enquanto HASHFULL reduz conflitos de hash em grandes volumes de dados."

- **Independência de Microserviços**: "Cada microserviço deve ser totalmente independente, ou seja, ele precisa realizar suas funcionalidades sem depender de outros serviços para operar corretamente. Essa independência permite que o serviço seja escalado ou atualizado de forma isolada, e que falhas não afetem o sistema inteiro. Em outras palavras, um microserviço deve ser coeso e cumprir um propósito específico."

---

## 3. Fila de Mensagens: Kafka e RabbitMQ

- **RabbitMQ**: "Geralmente prefiro RabbitMQ em casos onde a simplicidade é importante, pois ele é fácil de configurar e permite uma comunicação confiável entre serviços. Utilizo RabbitMQ para filas de mensagens simples, onde o sistema se beneficia da estrutura clara de mensagens e não precisa de muitos ajustes."

- **Kafka**: "Kafka é mais usado em casos de alto volume de dados ou quando precisamos de streaming contínuo. Por ser um pouco mais complexo, Kafka costuma ser implementado em sistemas que precisam processar grandes quantidades de dados em tempo real. Muitos bancos e sistemas de dados de grande escala preferem Kafka pela durabilidade e confiabilidade no tratamento de mensagens."

---

## 4. Padrões de Design (Design Patterns)

- **Padrões Criacionais**: "Os padrões criacionais, como o Factory, focam na criação de objetos, tornando o código mais flexível e desacoplado. O Factory é útil para criar instâncias específicas sem expor a lógica de criação para o cliente."

- **Padrões Estruturais**: "Padrões estruturais, como o Adapter, ajudam a estruturar classes e objetos para trabalharem juntos, mesmo que sejam incompatíveis. No Adapter, criamos uma 'ponte' entre classes para garantir que objetos possam interagir sem problemas."

- **Padrões Comportamentais**: "Padrões como o Observer facilitam a comunicação entre objetos sem que eles fiquem dependentes uns dos outros. No Observer, quando um objeto muda de estado, ele notifica automaticamente os dependentes, útil em sistemas com vários módulos interdependentes."

---

## 5. Testes Unitários e de Integração

- **Testes com JUnit e Mockito**: "Em testes unitários mais avançados com JUnit e Mockito, uso o `inOrder` para garantir a sequência correta de chamadas de métodos. Para testar o comportamento de um serviço, faço mocks com Mockito e uso `when-then` para definir o comportamento esperado."

- **Testes de Persistência**: "Em testes de persistência, faço um setup para inserir dados no banco antes do teste, e no teardown (ou método `@After`), limpo os dados para manter a consistência do banco. Isso é importante em testes que precisam de dados reais."

- **Testes de Integração de API**: "Em testes de integração, verifico se uma API funciona conforme o esperado, testando o fluxo entre a aplicação e o banco de dados ou outros serviços. Esse tipo de teste garante que a API lida bem com as integrações e fornece respostas corretas."

---

## 6. Java: Melhorias nas Versões 8, 11, 17 e 21

### Java 8

- **Lambdas e Stream API**: Com as expressões lambda e Stream API, manipulamos coleções com código conciso e funcional.
- **Optional**: Evita `NullPointerException`, tornando o tratamento de valores nulos mais seguro.

### Java 11

- **API de Strings**: Métodos como `isBlank()` e `strip()` otimizam a manipulação de texto.
- **HTTP Client**: Suporta HTTP/2 para chamadas assíncronas.
- **var**: Simplifica a declaração de variáveis locais, reduzindo a verbosidade do código.

### Java 17

- **Pattern Matching para instanceof**: Simplifica a verificação de tipos, reduzindo linhas de código.
- **Records**: Introduz classes imutáveis de forma compacta.
- **Sealed Classes**: Garante controle de herança para segurança em hierarquias complexas.

### Java 21

- **Virtual Threads (Project Loom)**: Threads leves otimizam o uso de recursos em sistemas concorrentes.
- **Pattern Matching for switch**: Expande o uso de pattern matching em validações complexas.

---

## 7. Modificadores de Acesso e `final` em Java

- **public**: Acessível de qualquer lugar.
- **protected**: Acessível no mesmo pacote e em subclasses.
- **private**: Acessível apenas dentro da própria classe, ideal para encapsulamento.

### Modificador `final`

- **final em Variáveis**: Constantes ou valores fixos.
- **final em Métodos**: Impede sobrescrita em subclasses.
- **final em Classes**: Impede extensão, mantendo a classe fixa.

---

## 8. Encapsulamento e Acesso a Objetos e Métodos Privados

"Para garantir encapsulamento em Java, uso atributos `private` e métodos `public` ou `protected` para expor apenas o necessário, com getters e setters para controle. Dessa forma, o estado do objeto é protegido, o acoplamento é reduzido e a manutenção é facilitada."

---

## 9. Lombok: Simplificando o Código em Java

Lombok é uma biblioteca Java que reduz o código boilerplate, como getters, setters, construtores, `equals`, `hashCode`, entre outros, através de anotações. Com Lombok, o código fica mais limpo, legível e fácil de manter, especialmente em classes com muitos atributos. Abaixo estão algumas das anotações mais utilizadas e suas funcionalidades.

### Principais Anotações do Lombok

- **@Getter e @Setter**  
  `@Getter` e `@Setter` geram automaticamente métodos getter e setter para cada campo da classe em que são aplicados.

  - **Exemplo**: Em uma classe de entidade, utilizo `@Getter` e `@Setter` para cada atributo sem precisar escrever manualmente esses métodos, o que reduz a quantidade de código significativamente.

- **@ToString**  
  Gera automaticamente o método `toString()`, que inclui todos os atributos da classe no formato string.

  - **Exemplo**: Ideal para classes de modelo ou DTOs, onde é útil exibir o conteúdo completo da instância. Com `@ToString`, posso visualizar facilmente o estado dos objetos em logs ou depuração.

- **@EqualsAndHashCode**  
  Cria automaticamente os métodos `equals()` e `hashCode()` baseados nos campos da classe.

  - **Exemplo**: Uso `@EqualsAndHashCode` em classes onde é importante que a comparação entre objetos leve em conta todos os atributos ou apenas alguns selecionados. Posso incluir parâmetros específicos para definir quais campos serão considerados na comparação.

- **@NoArgsConstructor, @AllArgsConstructor e @RequiredArgsConstructor**  
  Essas anotações geram construtores automaticamente:

  - `@NoArgsConstructor`: Construtor sem parâmetros.
  - `@AllArgsConstructor`: Construtor com todos os parâmetros para cada campo.
  - `@RequiredArgsConstructor`: Construtor para todos os campos `final` ou `@NonNull`.
  - **Exemplo**: Em classes de modelo, aplico `@AllArgsConstructor` para facilitar a criação de instâncias com todos os valores definidos, e `@NoArgsConstructor` quando preciso de uma instância padrão.

- **@Data**  
  Combina `@Getter`, `@Setter`, `@ToString`, `@EqualsAndHashCode` e `@RequiredArgsConstructor` em uma única anotação.

  - **Exemplo**: Uso `@Data` em classes de entidade ou DTOs, onde preciso de todos esses métodos e quero reduzir o código de maneira eficiente.

- **@Value**  
  Similar a `@Data`, mas para classes imutáveis, tornando todos os campos `final` e a classe `@ToString` e `@EqualsAndHashCode`.

  - **Exemplo**: Em classes que representam constantes ou valores imutáveis, utilizo `@Value` para garantir que nenhuma modificação seja feita após a criação do objeto.

- **@Builder**  
  Cria um builder para a classe, permitindo construir instâncias com uma sintaxe fluente e configurável.

  - **Exemplo**: `@Builder` é útil em classes com muitos atributos opcionais, pois permite construir objetos de maneira legível e flexível.

- **@Slf4j**  
  Adiciona um logger `SLF4J` à classe.
  - **Exemplo**: Em classes onde preciso de logs, aplico `@Slf4j` para evitar instanciar um logger manualmente e escrever logs diretamente com o `log.info`, `log.error`, etc.

### Uso Prático e Benefícios do Lombok

Em projetos, Lombok ajuda a reduzir significativamente o código repetitivo, especialmente em classes de modelo e DTOs, onde geralmente são necessários muitos getters, setters e construtores. Utilizar Lombok melhora a legibilidade do código e reduz o esforço de manutenção, permitindo que o time de desenvolvimento foque na lógica de negócio ao invés de lidar com métodos repetitivos e boilerplate.

---

## 10. Arquitetura Monolítica vs. Microserviços com Spring Boot

### Arquitetura Monolítica

"Uma arquitetura monolítica organiza toda a aplicação em um único projeto. Todas as funcionalidades – desde o backend até o front-end e o banco de dados – estão interligadas. No início, essa abordagem é mais fácil de desenvolver e implantar, pois há apenas um projeto para gerenciar. A comunicação entre as partes é direta e muito rápida. No entanto, à medida que a aplicação cresce, um monólito se torna difícil de escalar e manter, já que qualquer mudança exige a reimplantação de toda a aplicação."

### Arquitetura de Microserviços com Spring Boot

"Com microserviços, a aplicação é dividida em serviços independentes, cada um responsável por uma funcionalidade específica e com seu próprio banco de dados. Essa abordagem oferece escalabilidade e flexibilidade, pois cada serviço pode ser desenvolvido, implantado e escalado separadamente. O Spring Boot é ideal para microserviços porque facilita a criação de serviços leves e autônomos, com configurações automáticas que agilizam o desenvolvimento. Cada serviço comunica-se via APIs REST ou filas de mensagens, o que reduz o acoplamento e melhora a resiliência do sistema."

---

## 11. Principais Anotações do Spring

1. **@SpringBootApplication**  
   Combina três anotações principais: `@Configuration`, `@EnableAutoConfiguration` e `@ComponentScan`. Essa anotação é o ponto de entrada de uma aplicação Spring Boot, iniciando a configuração e o escaneamento de componentes automaticamente.

2. **@RestController e @Controller**  
   `@RestController` é usada para classes que respondem diretamente a requisições REST, como JSON, facilitando o desenvolvimento de APIs. Já `@Controller` é usada em aplicações com MVC, permitindo renderizar páginas HTML.

3. **@RequestMapping e @GetMapping/@PostMapping**  
   `@RequestMapping` define o mapeamento de requisições para métodos ou classes e pode definir endpoints e métodos HTTP. `@GetMapping` e `@PostMapping` são versões específicas para GET e POST, tornando o código mais limpo e legível.

4. **@Service**  
   Indica que uma classe implementa lógica de negócios, geralmente desacoplada dos controladores e repositórios. Essa separação facilita a manutenção e os testes.

5. **@Repository**  
   Aplica-se a classes que interagem diretamente com o banco de dados, como repositórios JPA. Ela também ajuda no tratamento automático de exceções de banco de dados.

6. **@Autowired**  
   Permite a injeção de dependência automática, facilitando o gerenciamento de componentes e a criação de um código menos acoplado.

7. **@Transactional**  
   Utilizada para garantir que operações de banco de dados sejam executadas em uma única transação, oferecendo rollback automático em caso de erro.

---

## 12. Ecossistema Spring

- **Spring Boot**
- Fornece configurações automáticas e inicialização rápida para criar aplicações independentes de produção.

- **Spring Data**
- Simplifica a interação com bancos de dados, permitindo a implementação de repositórios sem muito código.

- **Spring Security**
- Gerencia autenticação e autorização, oferecendo uma camada de segurança para as aplicações.

- **Spring Cloud**
- Facilita a construção de sistemas distribuídos com suporte para service discovery, configuração centralizada e comunicação entre microserviços.

- **Spring Batch**
- Ideal para processamento em lote de grandes volumes de dados, com suporte para jobs complexos e gestão de falhas.

---

## 13. Bancos de Dados Relacionais vs. Não Relacionais

- Bancos Relacionais: Utilizam tabelas para armazenar dados e organizam informações em relações bem definidas. São ideais para dados estruturados e que requerem ACID (Atomicidade, Consistência, Isolamento, Durabilidade), como MySQL e PostgreSQL.

- Bancos Não Relacionais (NoSQL): Armazenam dados de maneira mais flexível, como em documentos (MongoDB), colunas (Cassandra) ou grafos (Neo4j). São indicados para dados não estruturados e aplicações que necessitam de escalabilidade horizontal.

---

## 14. Principais Serviços de AWS

- **EC2** - Máquinas virtuais para hospedar aplicações e ambientes de desenvolvimento.

- **S3** - Armazenamento escalável de objetos para arquivos e backups.

- **RDS** - Banco de dados relacional gerenciado para MySQL, PostgreSQL, entre outros.

- **Lambda** - Funções serverless que executam código sob demanda.

- **Cognito** - Serviço de autenticação e autorização para gerenciar identidades de usuários.

---

## 15. Clean Code e Clean Architecture

- **Clean Code**
- Envolve escrever código claro, conciso e fácil de manter. Princípios como nomes significativos, simplicidade e DRY (Don’t Repeat Yourself) ajudam a criar um código limpo e legível.

- **Clean Architecture**
- Uma abordagem para organizar código de maneira modular, separando as camadas de negócios, interface de usuário e infraestrutura. A arquitetura limpa facilita testes e manutenção, além de permitir que cada camada seja independente.

---

Este repositório é uma referência para revisão de conceitos e boas práticas em Java e Spring Boot, proporcionando uma base sólida para entrevistas técnicas.
