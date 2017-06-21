**Entity MovEstoque**
----
  Movimentação de estoque.

* **URL**

  http://vmadmin.neoquard.com.br/api/v1/movestoque?uid=:uid&token=:token

* **Method:**

  `POST`
  
*  **URL Params**

   **Required:**
   
   `uid=[string]` Código do usuário. <br />
   `token=[string]` Chave de acesso.

* **Fields description**

    `operacao=[string]` Código da operação de estoque(Informar o código do estoque do seu ERP).<br/>
    `sinal=[integer]` 1=Entrada, 2=Saída.<br/>
    `qtde=[float]`  Quantidade do estoque movimentada.<br/>
    `estoque=[float]` Quantidade atual do estoque.<br/>
    `dt_mov=[string]` Data e hora do movimento de estoque em UTC.<br/>
    `obs=[string]`Observações.<br/>
    `sidag=[string]`Sid da área geral.<br/>
    `sidat=[string]`Sid da área de trabalho.<br/>
    `uid=[string]`Uid do usuário que fez a movimentação de estoque.<br/>
    `sidmaterial=[string]`Sid do produto.<br/>
    `_rev=[string]`Última versão do estoque. Caso seja um cadastro novo não enviar esta tag. Caso seja uma atualização de estoque sempre deverá ser enviada a revisão do estoque. O programador deve salvar a revisão do estoque para
    poder enviar novas atualizações.<br/>

* **Json body example**
    ```json
    {
        "operacao": "PEI",
        "sinal": 1,
        "qtde": 0,
        "estoque": 0,
        "dt_mov": "2017-06-21T11:54:17.000Z",
        "obs": "Atualização de estoque.",
        "sidag": "1be5387078f011e68d9b75e32d56f4d3",
        "sidat": "1c03bcf078f011e68d9b75e32d56f4d3",
        "uid": "2a50a810567911e7bd181ba09bd652c6",
        "sidmaterial": "5f8d4010567e11e7bd181ba09bd652c6",
        "_rev": "11-c9a5ccdc7f08c7266b675804a8baa9f3"
    }
    ```



* **Success Response:**
 
    ```json
    {
        "error": false,
        "msg": "ok",
        "movestoque": {
            "operacao": "PEI",
            "sinal": 1,
            "qtde": 0,
            "estoque": 0,
            "dt_mov": "2017-06-21T11:54:17.000Z",
            "obs": "Atualização de estoque.",
            "sidag": "1be5387078f011e68d9b75e32d56f4d3",
            "sidat": "1c03bcf078f011e68d9b75e32d56f4d3",
            "uid": "2a50a810567911e7bd181ba09bd652c6",
            "sidmaterial": "5f8d4010567e11e7bd181ba09bd652c6",
            "_rev": "12-0c40ff06d8847bd6899efe85d50d886d",
            "sidmovest": "ea21881056a811e7a718e348747b0656"
        }
    }
    ```
    >ATENÇÃO:<br>
    >SALVE OS DOIS CAMPOS DE RETORNO ('_rev' e 'sidmovest') NO SEU ERP PARA FUTURAS ATUALIZAÇÕES.
 
  
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
    POST /api/v1/movestoque?uid=8048a35ead8c45b796ce04e52d1dd489&token=bc6338fcb6df436584bf5de2f11a98ae HTTP/1.1
    Host: vmadmin.neoquard.com.br
    Content-Type: application/json
    Cache-Control: no-cache

    {
        "operacao": "PEI",
        "sinal": 1,
        "qtde": 0,
        "estoque": 0,
        "dt_mov": "2017-06-21T11:54:17.000Z",
        "obs": "Atualização de estoque.",
        "sidag": "1be5387078f011e68d9b75e32d56f4d3",
        "sidat": "1c03bcf078f011e68d9b75e32d56f4d3",
        "uid": "2a50a810567911e7bd181ba09bd652c6",
        "sidmaterial": "5f8d4010567e11e7bd181ba09bd652c6",
        "_rev": "11-c9a5ccdc7f08c7266b675804a8baa9f3"
    }
    ```