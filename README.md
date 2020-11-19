# SOLID
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

		double calc_bolsa_valores();
	private:
		//Atributos
};
```
