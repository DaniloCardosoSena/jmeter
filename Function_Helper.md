## JMeter Function Helper
Options -> Function Helper Dialog (Ctrl + Shift + F1) <br/>
 <br/>
`${__RandomString(11,0123456789,id)}` = Gera valor aleatório de 11 dígitos com números de 0 à 9 e armazena na variável "id". <br/>
`${__RandomFromMultipleVars(AVC|AZL|TAP|ACR,partner)}` = Seleciona randomicamente uma das variávies definidas(AVC, AZL...) para ser valor da variável "partner". <br/>

### Atribui à variável *somaValoresFrete* a somatória das variáveis *salePrice* e *shippingTax*:
Language: javascript (ECMAScript ECMA - 262 Edition 5.1 / Oracle Nashorn 1.8.0_212)
```
var salePrice = vars.get("salePrice");
var shippingTax = vars.get("shippingTax");
vars.put("somaValoresFrete",parseFloat(salePrice) + parseFloat(shippingTax));
```
### Cria arquivo *.csv* no caminho desejado com gravação de resultados:
Language: java (BeanShell 2.0b6 / Bean Shell Engine 1.0)
```
import org.apache.jmeter.services.FileServer;

f = new FileOutputStream("c:/CSVresult.csv", true); 
p = new PrintStream(f); 
p.println( "z${id}" + "," + "cyd${id}" ); // atualize aqui o que vc deseja escrever
p.close();
f.close();
```
