# JMeter Tips

### JMeter - Comandos
```
Execução jmeter por terminal:
sh [caminho do jmeter"/bin/jmeter"] -n -t [caminho robo .jmx] -l [caminho de saida do .CSV/.JTL "aggregateReport.csv"]

Execução jmeter por terminal Smoke(Thread Group) com variáveis:
[Caminho do \bin\jmeter.bat] -Jthreads=5 -Jrampup=60 -Jduration=300 -n -t [caminho robo .jmx] -l

Geração de relatório jmeter charts:
[Caminho do \bin\jmeter.bat] -g [Caminho do arquivo CSV para geração do relatório "agregate.csv"] -o [Caminho onde será salvo o relatório chamado index.html + Nome de uma pasta obrigatoriamente que não exista. Ex: "C:\Users\Relatorio_JMeterCharts"]
```


### JMeter - Saída de arquivos padrões
- BT_1_${__time(yyyyMMdd-HHmmss)}.csv
- BT_2_${__time(yyyyMMdd-HHmmss)}.csv


### JMeter - Ultimate Thread Group - Load Test (40 Vus)
|Start Thread Count   	| Initial Delay, sec   	  | Startup Time, sec  	| Hold Load For, sec  	| Shutdown Time     |
|---	                |---	                  |---	                |---	                |---	            |
| 10   	                | 0  	                  | 300  	        | 3300                  | 0  	            |
| 10   	                | 900  	                  | 300  	        | 2400                  | 0  	            |
| 10  	                | 1800  	          | 300  	        | 1500                  | 0  	            |
| 10  	                | 2700  	          | 300  	        | 600                   | 0  	            |


### JMeter - HTTP Header Manager (REST XML Requests)
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8 <br/>
Accept-Encoding: gzip, deflate <br/>
Accept-Language: pt-BR,pt;q=0.9,en-US;q=0.8,en;q=0.7 <br/>
Cache-Control: no-cache <br/>
Connection: keep-alive <br/>
User-Agent: Mozilla/5.0 (Windows NT 6.1; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/68.0.3440.106 Safari/537.36 <br/>

### JMeter - HTTP Header Manager (REST JSON Requests)
Content-Type: application/json;charset=UTF-8 <br/>
Accept: application/json, text/plain, \*/\* <br/>
Accept-Encoding: gzip, deflate <br/>
Accept-Language: pt-BR,pt;q=0.9,en-US;q=0.8,en;q=0.7 <br/>
Cache-Control: no-cache <br/>
Connection: keep-alive <br/>

### JMeter - HTTP Header Manager (SOAP Requests)
Content-Type: text/xml;charset=UTF-8 <br/>
Accept-Encoding: gzip,deflate <br/>
Connection: Keep-Alive <br/>
SOAPAction: "" <br/>
```sh
Body:
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:bcp="http://bcp.porto.com/">
   <soapenv:Header/>
   <soapenv:Body>
   .
   .
   .
   </soapenv:Body>
</soapenv:Envelope>
```

### JMeter - HTTP Header Manager
- Authorization:	Bearer ${token}
- X-Auth-Token: Bearer ${token}

### JMeter - Jenkins Configs

Configuracao para integracao via parametros JMeter - Thread Group

|Param   	  	| EL / Value  		| Type			| Required				|
|---	                |---	                |---			|---					|
| Number of Threads 	| ${__P(threads,1)}	| Integer		| Yes					|
| Ramp-Up 		| ${__P(rampup,1)}	| Integer		| Yes					|
| Loop-Count 		| ${__P(loopCount,1)}	| Integer		| No (Set true in JMeter is default)	|
| Duration		| ${__P(duration,1)}	| Integer (Seconds)	| Yes					|
| Startup delay		| ${__P(startup,1)}	| Integer (Seconds)	| Yes					|
| Aggregate Report      | ${__P(aggregate)}	| String		| Yes					|


### Schedule Pipeline Jenkins:
```00 22 * * 1```

### Run JMeter With Proxy
Configurar JMETER_HOME nas variáveis de ambiente da máquina; <br/>
Executar CMD: 
```jmeter -H [host] -P [Port]```


### JMeter Recording (URL Patterns to Exclude):
```
.*msg\.yahoo\.com.*
www\.download\.windowsupdate\.com.*
http?://self-repair\.mozilla\.org.*
tiles.*\.mozilla\.com.*
.*detectportal\.firefox\.com.*
.*\.google\.com.*/safebrowsing/.*
.bing\.com.*
toolbar\.google\.com.*
www\.google-analytics\.com.*
www\.google\.com.*
.*\.google\.com.*
.google\.com.*
www\.google\.com.\br.*
clients.*\.google.*
.*toolbar\.yahoo\.com.*
geo\.yahoo\.com.*
```
