## JMeter Function Helper
Options -> Function Helper Dialog (Ctrl + Shift + F1) <br/>
 <br/>
`${__RandomString(11,0123456789,id)}` = Gera valor aleatório de 11 dígitos com números de 0 à 9 e armazena na variável *"id"*. <br/>
`${__RandomFromMultipleVars(AVC|AZL|TAP|ACR,partner)}` = Seleciona randomicamente uma das variáveis definidas(AVC, AZL...) para ser valor da variável *"partner"*. <br/>
`${__RandomDate(dd-MM-yyyy,01-01-2001,01-01-2100,pt_BR,dateRandom)}` = Gera data aleatória com range definido(01/2001 à 01/2100) e atribui resultado na variável *"dateRandom"*. <br/>
`${__time(dd/MM/yyyy,dateNow)}` = Gera data atual no formato desejado e guarda na variável *"dateNow"*. <br/>
`${__time(HH:mm:ss,timeNow)}` = Gera horário atual no formato desejado e guarda na variável *"timeNow"*. <br/>
`${__timeShift(dd-MM-yy,now,P2D,pt_BR,dayPlus)}` = Gera data atual + 2 dias a frente(P2D - *plus 2 days*) no formato desejado e guarda na variável *"dayPlus"*. <br/>
 - "PT20.345S" parses as "20.345 seconds" <br/>
 - "PT15M" parses as "15 minutes" <br/>
 - "PT10H" parses as "10 hours" <br/>
 - "P2D" parses as "+ 2 days" <br/>
 - "P-2D" parses as "-2 days" <br/>
 - "P365D" parses as "365 days(1 year)" <br/>
 - "P2DT3H4M" parses as "2 days, 3 hours and 4 minutes" <br/>
 - "P-6H3M" parses as "-6 hours and +3 minutes" <br/>
 <br/>

## JSR223
### Atribui à variável *somaValoresFrete* a somatória das variáveis *salePrice* e *shippingTax*:
Language: javascript (ECMAScript ECMA - 262 Edition 5.1 / Oracle Nashorn 1.8.0_212)
```sh
var salePrice = vars.get("salePrice");
var shippingTax = vars.get("shippingTax");
vars.put("somaValoresFrete",parseFloat(salePrice) + parseFloat(shippingTax));
```
### Cria arquivo *.csv* no caminho desejado com gravação de resultados:
Language: java (BeanShell 2.0b6 / Bean Shell Engine 1.0)
```sh
import org.apache.jmeter.services.FileServer;

f = new FileOutputStream("c:/CSVresult.csv", true); 
p = new PrintStream(f); 
p.println( "z${id1}" + "," + "cyd${id2}" ); // atualize aqui o que vc deseja escrever
p.close();
f.close();
```
