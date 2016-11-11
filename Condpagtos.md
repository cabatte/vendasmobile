**Entity Condições de Pagamentos**
----
  Dados das condições de pagamentos que estarão disponíveis para o vendedor selecionar quando for realizar a venda.

* **URL**

  http://vmadmin.neoquard.com.br/api/v1/condpagtos?uid=:uid&token=:token

* **Method:**

  `POST`
  
*  **URL Params**

   **Required:**
   
   `uid=[string]` Código do usuário. <br />
   `token=[string]` Chave de acesso.

* **Data Params**

    `referencia=[string]` Código.<br/>
    `ds_cond=[string]` Descrição da Condição de Pagamentos.<br/>
    `dias=[string]` Dias de vencimento Exemplo: 0,30,60,90.<br/>
    `ativo=[string]` Indica se a condição de pagamento está ativa. Valores válidos 'S' ou 'N'. <br/>
    `sidag=[string]` Código da empresa.<br/>
    `sidat=[string]` Código da filial.<br/>
    `sidcondpagto=[string]` ID da condição de pagamento criada.<br/>
    `_rev=[string]` <br/>

* **Success Response:**

  * **Code:** 200 <br />
    Content:
    ```json
    { 
        error: false, 
        msg: "ok", 
        condpagto: 
            { 
                "sidcondpagto": "1be5387078f011e68d9b75e32d56f4d3",
                "_rev": "1" 
            }
    } 
    ```

    >ATENÇÃO:<br>
    >SALVE OS DOIS CAMPOS DE RETORNO ('sidcondpagto' e '_rev') NO SEU ERP PARA FUTURAS ATUALIZAÇÕES.
 
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
    POST /api/v1/condpagtos?uid=8048a35ead8c45b796ce04e52d1dd489&amp;token=bc6338fcb6df436584bf5de2f11a98ae HTTP/1.1
    Host: vmadmin.neoquard.com.br
    Content-Type: application/json
    Cache-Control: no-cache

    { 
        "referencia": "1",
        "ds_cond": "3x sem juros",
        "dias": "30,60,90",
        "ativo": "S",
        "sidag": "1be5387078f011e68d9b75e32d56f4d3",
        "sidat": "1c03bcf078f011e68d9b75e32d56f4d3",
        "sidcondpagto": "",
        "_rev": "1" 
    }
    ```
