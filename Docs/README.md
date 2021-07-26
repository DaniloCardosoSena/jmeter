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
