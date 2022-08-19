# Calculadora de Juros Composto
[![NPM](https://img.shields.io/npm/l/react)](https://github.com/wvitorsj/CalculadoraDeJurosComposto/blob/main/LICENCE) 

# Sobre o projeto

Aplicação construída com JAVA Desktop e Swing, além disso utilizamos a classe BigDecimal para as operações matemáticas realizando os arredondamentos com o 
comando RoundingMode.HALF_EVEN, esse é o critério de arredondamento adotado pelo Banco Central como sendo padrão brasileiro para operações financeiras na 
norma ABNT 5891 e 4 (quatro) casas decimais conforme a Resolução 4624 de 18 de Janeiro de 2018.

##BigDecimal e RoundingMode

```java
private BigDecimal toBigDecimal(String valor) {		
		try {
			return new BigDecimal(valor).setScale(4, RoundingMode.HALF_EVEN);
			
		} catch (Exception ex) {
			return BigDecimal.ZERO;
		}
	}
```
Utilizamos os Gerenciadores de Layout FlowLayout e o BorderLayout responsáveis pela distribuição dos 
componentes no painel e saõ inseridos no construtor do painel.

##FlowLayout: Coloca os componentes seguidos uma após o outro.
```java  
  public JPanel getPnlRodape() {
  
		if (pnlRodape == null) {
			pnlRodape = new JPanel(new FlowLayout(FlowLayout.CENTER));			
			btnCalcular = new JButton("Calcular");
			btnLimpar = new JButton("Limpar");
			btnFechar = new JButton("Fechar");			
			pnlRodape.add(btnCalcular);
			pnlRodape.add(btnLimpar);
			pnlRodape.add(btnFechar);			
		}
		return pnlRodape;
	}
 ```
 
  ##BorderLayout: Divide a tela em 5 (cinco) partes centro, esquerda,topo, direita e rodapé. 
 ```java  
  private void inicializar() {
  
		this.setTitle("Calculadora Juros Composto");		
		this.setDefaultCloseOperation(JFrame.DISPOSE_ON_CLOSE);
		//this.setSize(340, 180);		
		this.getContentPane().setLayout(new BorderLayout());
		this.setResizable(false);					
		this.getContentPane().add(getPnlForm(), BorderLayout.CENTER);
		this.getContentPane().add(getPnlRodape(), BorderLayout.PAGE_END);		
		this.pack();
	}
 ```

# Tecnologias utilizadas
## Back end
- Java Desktop
- Swing
- JFrame
- Maven




# Autor

Welton Vitor da S. Jesus

https://www.linkedin.com/in/welton-vitor-da-silva-jesus-21104b206

