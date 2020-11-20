# SOLID - O Princípio da responsabilidade única aplicado a Programação orientada a objetos
###### Autor: Eric Sales Vitor Junior
###### Data: 20/11/2020
**SOLID** é um acronimo criado por *Michael Feathers*. Em que cada letra se relaciona a um tópico de boas práticas de programação.
> **S** --- Single responsibility principle (**Princípio da responsabilidade única**)\
> **O** --- Open/closed principle (**Principio aberto/fechado**)\
> **L** --- Liskov Substitution Principle (**Princípio da substituição de Liskov**)\
> **I** --- Interface Segregation Principle (**Princípio da Segregação da Interface**)\
> **D** --- Dependency Inversion Principle (**Princípio da inversão da dependência**)

Nesse breve artigo iremos abordar o primeiro principio da **SOLID** que é o **princípio da responsabilidade única** que nós diz que **"Uma classe deve ter um, e somente um, motivo para mudar"**, ou seja se eu preciso fazer apenas uma alteração essa alteração deve envolver apenas uma classe, em outras palavras "*uma classe deve ter apenas um motivo para mudar*”. Um exemplo pode facilitar a compreensão:

```c++
class estado{
	public:
		double calc_idh();

		int get_pupulacao();
		double get_area();
		int get_idade();

		double calc_pib();

	private:
		//Atributos
};
```
> **Nota**: exemplo escrito em C++

Vejamos que a classe **estado** possui os métodos *calc_idh* e *calc_pib* que são atributos que não somente estados possuem, países e cidades também possuem PIB e um IDH se futuramente desejar se expandir para incluir cidades ou países teríamos que refazer os métodos *calc_idh* e *calc_pib* e não poderíamos reaproveitar linhas de código. Conforme o código for crescendo fica difícil realizar a manutenção desde. E para arrumar esse problema aplicamos o princípio da responsabilidade única. Vejamos o exemplo:

```c++
class estado{
	public:
		int get_pupulacao();
		double get_area();
		int get_idade();
	
	private:
		//Atributos
};

class IDH{
	public:
		double calc_idh();

	private:
		//Atributos
};

class PIB{
	public:
		double calc_pib();

	private:
		//Atributos
};
```
Temos agora uma divisão das responsabilidades em que cada classe responde sobre a sua responsabilidade. Perceba que não temos mais uma classe que faz tudo, isso torna o código muito mais fácil de ler e modificar já que se temos uma modificação para fazer basta procurar a classe responsável.

