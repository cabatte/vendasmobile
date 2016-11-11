**Entity Empresas**
----
  Teremos nesta entidade os dados de cadastros dos clientes (pessoas físicas e jurídidcas).

* **URL**

  http://vmadmin.neoquard.com.br/api/v1/empresas?uid=:uid&token=:token

* **Method:**

  `POST`
  
*  **URL Params**

   **Required:**
   
   `uid=[string]` Código do usuário. <br />
   `token=[string]` Chave de acesso.

* **Data Params**

    `referencia`: Código.<br/>
    `nome=[string]` Nome ou razão social do cliente.<br/>
    `nome_fantasia=[string]` Nome de fantasia.<br/>
    `cnpj_cpf=[string]` CNPJ/CPF.<br/>
    `inscricao_est=[string]` Inscrição estadual.<br/>
    `fone=[string]` Fone princiapl. Exemplo: (47) 99632-0000.<br/>
    `fone2=[string]` Fone alternativo.<br/>
    `fax=[string]` Fax.<br/>
    `cep=[string]` CEP do cliente. Exemplo: 88308000.<br/>
    `endereco=[string]` Endereço do cliente.<br/>
    `bairro=[string]` Bairro.<br/>
    `nro_endereco=[string]` Nro. do endereço.<br/>
    `complemento=[string]` Complemento.<br/>
    `ds_cidade=[string]` Cidade.<br/>
    `iduf=[string]` UF.<br/>
    `email_comprador=[string]` Email do comprador.<br/>
    `fone_comprador=[string]` Fone do comprador.<br/>
    `contato_comprador=[string]` Contato do comprador.<br/>
    `obs=[string]` Observações.<br/>
    `obs_financeiras=[string]` Observações financeiras.<br/>
    `email=[string]` E-mail.<br/>
    `end_web=[string]` Endereço web da página do cliente.<br/>
    `skype=[string]` Skype.<br/>
    `facebook=[string]` Facebook.<br/>
    `bloqueado=[string]` Status de bloqueado (S/N).<br/>
    `msg_alerta=[string]` Mensagem de alerta que será exibido ao fazer a venda.<br/>
    `tipo_emp=[string]` Fixo S.<br/>
    `tipo_emp_for=[string]` Fixo N.<br/>
    `tipo_emp_tra=[string]` Fixo N.<br/>
    `tipo_emp_vend=[string]` Fixo N.<br/>
    `tipo_emp_func=[string]` Fixo N.<br/>
    `gps_lat=[string]` 0.<br/>
    `gps_lng=[string]` 0.<br/>
    `ativo=[string]` Status de ativo (S/N).<br/>
    `sidag=[string]` Sid da empresa.<br/>
    `sidempresa=[string]` <br/>
    `_rev=[string]` 

* **Success Response:**

  * **Code:** 200 <br />
    Content:
    ```json
    { 
        error: false, 
        msg: "ok", 
        empresa: 
            { 
                "sidempresa": "1be5387078f011e68d9b75e32d56f4d3",
                "_rev": "1" 
            }
    } 
    ```

    >ATENÇÃO:<br>
    >SALVE OS DOIS CAMPOS DE RETORNO ('sidempresa' e '_rev') NO SEU ERP PARA FUTURAS ATUALIZAÇÕES.
 
* **Error Response:**

  * **Code:** 404 NOT FOUND <br />
   Content:
    ```json
    { 
        error: true, 
        msg: "Error processing the request"
    } 
    ```

  OR

  * **Code:** 401 UNAUTHORIZED <br />
    **Content:** `{ error : "You are unauthorized to make this request." }`


* **Exemplo em HTTP:**

  ```HTTP
    POST /api/v1/empresas?uid=8048a35ead8c45b796ce04e52d1dd489&amp;token=bc6338fcb6df436584bf5de2f11a98ae HTTP/1.1
    Host: vmadmin.neoquard.com.br
    Content-Type: application/json
    Cache-Control: no-cache
    
    { 
        "referencia": "1",
        "nome": "Nome do cliente",
        "nome_fantasia": "",
        "cnpj_cpf": "",
        "inscricao_est": "",
        "fone": "(47) 99632-0000",
        "fone2": "",
        "fax": "",
        "cep": "88308000",
        "endereco": "Avenida Governador Adolfo Konder",
        "bairro": "São Vicente",
        "nro_endereco": "",
        "complemento": "até 960 - lado par",
        "ds_cidade": "Itajaí",
        "iduf": "SC",
        "email_comprador": "",
        "fone_comprador": "",
        "contato_comprador": "",
        "obs": "",
        "obs_financeiras": "",
        "email": "email@gmail.com",
        "end_web": "",
        "skype": "",
        "facebook": "",
        "bloqueado": "N",
        "msg_alerta": "",
        "tipo_emp": "",
        "tipo_emp_for": "",
        "tipo_emp_tra": "",
        "tipo_emp_vend": "",
        "tipo_emp_func": "",
        "gps_lat": "0",
        "gps_lng": "0",
        "ativo": "S",
        "sidag": "1be5387078f011e68d9b75e32d56f4d3",
        "sidempresa": "",
        "_rev": "1" 
    }
    ```
