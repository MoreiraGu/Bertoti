  # Atividade1
What precisely do we mean by software engineering? What distinguishes “software engineering” from “programming” or “computer science”? And why would Google have a unique perspective to add to the corpus of previous software engineering literature written over the past 50 years?
 
The terms “programming” and “software engineering” have been used interchangeably for quite some time in our industry, although each term has a different emphasis and different implications. University students tend to study computer science and get jobs writing code as “programmers.”
 
“Software engineering,” however, sounds more serious, as if it implies the application of some theoretical knowledge to build something real and precise. Mechanical engineers, civil engineers, aeronautical engineers, and those in other engineering disciplines all practice engineering. They all work in the real world and use the application of their theoretical knowledge to create something real. Software engineers also create “something real,” though it is less tangible than the things other engineers create.
 
Unlike those more established engineering professions, current software engineering theory or practice is not nearly as rigorous. Aeronautical engineers must follow rigid guidelines and practices, because errors in their calculations can cause real damage; programming, on the whole, has traditionally not followed such rigorous practices. But, as software becomes more integrated into our lives, we must adopt and rely on more rigorous engineering methods. We hope this book helps others see a path toward more reliable software practices.

*Answer : When we talk about programming or computer science, we are only talking about the tip of the iceberg in the world of technology. When we say "software engineering", we are talking about the structural part of the code, the theoretical part.*

 # Atividade2
Programming Over Time
We propose that “software engineering” encompasses not just the act of writing code, but all of the tools and processes an organization uses to build and maintain that code over time. What practices can a software organization introduce that will best keep its code valuable over the long term? How can engineers make a codebase more sustainable and the software engineering discipline itself more rigorous? We don’t have fundamental answers to these questions, but we hope that Google’s collective experience over the past two decades illuminates possible paths toward finding those answers.
 
One key insight we share in this book is that software engineering can be thought of as “programming integrated over time.” What practices can we introduce to our code to make it sustainable—able to react to necessary change—over its life cycle, from conception to introduction to maintenance to deprecation?
 
The book emphasizes three fundamental principles that we feel software organizations should keep in mind when designing, architecting, and writing their code:
 
Time and Change
How code will need to adapt over the length of its life
 
Scale and Growth
How an organization will need to adapt as it evolves
 
Trade-offs and Costs
How an organization makes decisions, based on the lessons of Time and Change and Scale and Growth


*Answer : The second part of the text talks about how sustainable a code must be to face the changes that time can make and the evolution of programming, being one of the things that a software engineer must think about before making a decision about a project.*


 # Atividade3 
Legibilidade x Perfomance - A legibilidade de um codígo fornece a quem lê um melhor entendimento, porém, perde otimização, é uma troca entre facilidade em manutenção e funcionabilidade

Velocidade x Qualidade - Quando se escreve um código rapidamente, faz com que não aconteça atrasos, porém o código fica mais robusto, podendo gerar futuros bugs que fica mais dificil de resolver

Modularidade x Desempenho - Ao gerar métodos e classes para manter a organização do código, o deixa mais organizado, porém perde a eficiência

 # Atividade4
Gera uma reflexão sobre o entendimento da entrega, ao invés de entregar uma fração de algo perfeito mas inutilizavel, não é tão eficiente quanto entregar algo básico, porém utilizado

 # Atividade5

<pre lang="java"> ```package biblioteca; public class Livro { private String titulo; private String isbn; public Livro(String titulo, String isbn) { this.titulo = titulo; this.isbn = isbn; } public String getTitulo() { return titulo; } public void setTitulo(String titulo) { this.titulo = titulo; } public String getIsbn() { return isbn; } public void setIsbn(String isbn) { this.isbn = isbn; } } ``` ```java package biblioteca; import java.util.LinkedList; import java.util.List; public class Biblioteca { private List<Livro> livros = new LinkedList<>(); public void adicionarLivro(Livro livro) { livros.add(livro); } public Livro buscarPorIsbn(String isbn) { for (Livro livro : livros) { if (livro.getIsbn().equals(isbn)) { return livro; } } return null; } public List<Livro> buscarPorTitulo(String titulo) { List<Livro> encontrados = new LinkedList<>(); for (Livro livro : livros) { if (livro.getTitulo().equalsIgnoreCase(titulo)) { encontrados.add(livro); } } return encontrados; } public List<Livro> getLivros() { return livros; } } ``` ```java package biblioteca; import org.junit.jupiter.api.Assertions; import org.junit.jupiter.api.Test; import java.util.List; class BibliotecaTeste { @Test void testBiblioteca() { Biblioteca biblioteca = new Biblioteca(); biblioteca.adicionarLivro(new Livro("Dom Casmurro", "123456")); biblioteca.adicionarLivro(new Livro("Memórias Póstumas", "654321")); Assertions.assertEquals(2, biblioteca.getLivros().size()); Livro livro = biblioteca.buscarPorIsbn("123456"); Assertions.assertEquals("Dom Casmurro", livro.getTitulo()); List<Livro> encontrados = biblioteca.buscarPorTitulo("Memórias Póstumas"); Assertions.assertEquals(1, encontrados.size()); Assertions.assertEquals("654321", encontrados.get(0).getIsbn()); } } ``` </pre>
