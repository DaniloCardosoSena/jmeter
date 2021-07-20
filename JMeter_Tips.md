# JMeter Tips

### JMeter - Saída de arquivos padrões
BT_1_${__time(yyyyMMdd-HHmmss)}.csv <br/>
BT_2_${__time(yyyyMMdd-HHmmss)}.csv


### JMeter - Ultimate Thread Group - Load Test
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
User-Agent: Mozilla/5.0 (Windows NT 6.1; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/68.0.3440.106 Safari/537.36

### JMeter - HTTP Header Manager (REST JSON Requests)
Content-Type: application/json;charset=UTF-8 <br/>
Accept: application/json <br/>
Accept-Encoding: gzip, deflate <br/>
Accept-Language: pt-BR,pt;q=0.9,en-US;q=0.8,en;q=0.7 <br/>
Cache-Control: no-cache <br/>
Connection: keep-alive

### JMeter - HTTP Header Manager (SOAP Requests)
Content-Type: text/xml;charset=UTF-8
Accept-Encoding: gzip,deflate
Connection: Keep-Alive
User-Agent: Apache-HttpClient/4.1.1 (java 1.5)
SOAPAction: ""




