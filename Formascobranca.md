**Entity Formas de Cobrança**
----
  Dados das formas de cobrança que estarão disponíveis para o vendedor selecionar quando for realizar a venda.

* **URL**

  http://vmadmin.neoquard.com.br/api/v1/formascobranca?uid=:uid&token=:token

* **Method:**

  `POST`
  
*  **URL Params**

   **Required:**
   
   `uid=[string]` Código do usuário. <br />
   `token=[string]` Chave de acesso.

* **Fields description**

    `referencia=[string]` Código (Informe aqui o código do seu ERP).<br/>
    `ds_cob=[string]` Descrição da forma de cobrança.<br/>
    `ativo=[string]`  Ativa. Valores válidos 'S' ou 'N'. <br/>
    `sidag=[string]` Código da empresa.<br/>
    `sidat=[string]` Código da filial.<br/>
    `sidcobranca=[string]`ID da forma de cobrança criada.<br/>
    `_rev=[string]`Versão do documento criado.<br/>

* **Json body example**
    ```json
     { 
        "referencia": "1",
        "ds_cob": "Dinheiro",
        "ativo": "S",
        "sidag": "1be5387078f011e68d9b75e32d56f4d3",
        "sidat": "1c03bcf078f011e68d9b75e32d56f4d3",
        "sidcobranca": "",
        "_rev": "" 
    }
    ```



* **Success Response:**
 
    ```json
    { 
        error: false, 
        msg: "ok", 
        formacobranca:
            { 
                "sidcobranca": "1be5387078f011e68d9b75e32d56f4d3",
                "_rev": "1" 
            }
    } 
    ```
    >ATENÇÃO:<br>
    >SALVE OS DOIS CAMPOS DE RETORNO ('sidcobranca' e '_rev') NO SEU ERP PARA FUTURAS ATUALIZAÇÕES.
 
  
* **Error Response:**

    ```json
    { 
        error: true, 
        msg: "Error processing the request"
    } 
    ```

  OR

  * **Code:** 401 UNAUTHORIZED <br />
   ```json
     { 
       message : "Invalid uid or token in the url params." 
     } 
    ```
* **Example in HTTP:**

  ```HTTP
    POST /api/v1/formascobranca?uid=8048a35ead8c45b796ce04e52d1dd489&amp;token=bc6338fcb6df436584bf5de2f11a98ae HTTP/1.1
    Host: vmadmin.neoquard.com.br
    Content-Type: application/json
    Cache-Control: no-cache

    { 
        "referencia": "1",
        "ds_cob": "Dinheiro",
        "ativo": "S",
        "sidag": "1be5387078f011e68d9b75e32d56f4d3",
        "sidat": "1c03bcf078f011e68d9b75e32d56f4d3",
        "sidcobranca": "",
        "_rev": "1" 
    }
    ```
