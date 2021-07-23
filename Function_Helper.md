## JMeter Function Helper
Options -> Function Helper Dialog (Ctrl + Shift + F1)
 <br/>
`${__RandomString(11,0123456789,id)}` = Gera valor aleatório de 11 dígitos com números de 0 à 9 e armazena na variável "id". <br/>
`${__RandomFromMultipleVars(AVC|AZL|TAP|ACR,partner)}` = Seleciona randomicamente uma das variávies definidas(AVC, AZL...) para ser valor da variável "partner". <br/>
 <br/>
 <br/>
### Atribui à variável somaValoresFrete a somatória das variáveis salePrice e shippingTax:
```
var salePrice = vars.get("salePrice");
var shippingTax = vars.get("shippingTax");
vars.put("somaValoresFrete",parseFloat(salePrice) + parseFloat(shippingTax)); <br/>
```
### Cria arquivo .csv no caminho desejado com gravação de resultados:
```
import org.apache.jmeter.services.FileServer;

f = new FileOutputStream("c:/CSVresult.csv", true); 
p = new PrintStream(f); 
p.println( "z${id}" + "," + "cyd${id}" ); // atualize aqui o que vc deseja escrever
p.close();
f.close();
```
