# JMeter-Docs
### MQ
**Para MQ: (Mensageria)**
- Qual o protocolo de comunicação?
- Qual o modelo de MQ ?
- Qual o Receiver que lê a fila do MQ?
- Como funciona o processo de envio?
 <br />

### Dicas de Investigação
**Lista de Pontos de Atenção em Desenvolvimento de Robôs no JMeter:**
- Encoding: UTF-8
- Checkbox Parâmetros (Encode | Include Equals)
- Clear Cache
- Clear Cookie
- Verificar se não há algum dígito/espaço em branco nos campos de preenchimento ou parâmetros do robô
- Verificar se falta processo de Autenticação da chamada (token)
- Testar chamada no Postman, Insomnia ou Swagger-ui...
- Testar bot em ambientes(máquinas) diferentes
- Verificar se há Headers a mais(desnecessários) ou se falta Headers indispensáveis para chamada (Ex:"Soap", "Json")
- Recriação novo .JMX com componentes novos(sem cópia de parametrôs antigos).


### Dica #1
Arquivos: `java_pid.hprof` & `hs_err_pid.mdmp`<br />
Arquivo Java Dump do JMeter que são salvos automaticamente na pasta */bin*, podem ser excluídos pois consomem muita memória do disco sem necessidade. <br />


### Dica #2
#### Erro JMeter payload com diretório "caminho"
Erro: 400 Bad Request <br />
"code":"SGCB-006","message":"Json invÃ¡lido.","detail":"JSON parse error: Unrecognized character escape '$' <br />
nested exception is com.fasterxml.jackson.databind.JsonMappingException: Unrecognized character escape '$' (code 36) <br />
Source: (PushbackInputStream) <br />
 <br />
> Ao usar \ antes de uma variável para um caminho do Windows, por exemplo C: \ test \ $ {test}, certifique-se de escapar do \ caso contrário, o JMeter não interpretará a variável, exemplo: C: \\ test \\ $ {test}.
Como alternativa, basta usar / em vez do separador de caminho - por exemplo, C: / test / $ {test} - As JVMs do Windows converterão os separadores conforme necessário.
 <br />
Correto: <br />
{                                                                          {<br />
"description": "TesteERP ${id}",                                           "description": "TesteERP ${id}", <br />
"archiveType": "I",                                   Ou                   "archiveType": "I", <br />
"directory": "d:\\\teste\\\destino"                                        "directory": "d:/teste/destino" <br />
}                                                                          }<br />
