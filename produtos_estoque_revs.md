**Entity MovEstoque**
----
  Revições de estoque.

* **URL**

  http://vmadmin.neoquard.com.br/api/v1/produtos_estoque_revs/:sidag?uid=:uid&token=:token

* **Method:**

  `GET`
  
*  **URL Params**

   **Required:**
   
   `sidag=[string]` Sid da área geral. <br />
   `uid=[string]` Código do usuário. <br />
   `token=[string]` Chave de acesso.


* **Success Response:**
 
    ```json
        {
        "error": false,
        "msg": "ok",
        "revs": [
            {
                "sid": "5f8d4010567e11e7bd181ba09bd652c6",
                "_revest": "12-0c40ff06d8847bd6899efe85d50d886d",
                "estoque_real": 6
            },
            {
                "sid": "99994010567e11e7bd181ba09bd652c6",
                "_revest": "1-xxxxff06d8847bd6899efe85d50d886d",
                "estoque_real": 12
            }
        ]
    }
    ```

    
* **Fields description**

    `sid=[string]`Sid do produto.<br/>
    `_revest=[string]`Última versão do estoque.<br/>
    `estoque_real=[float]` Quantidade atual do estoque.<br/>

 

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
    POST /api/v1/produtos_estoque_revs/1be5387078f011e68d9b75e32d56f4d3?uid=8048a35ead8c45b796ce04e52d1dd489&token=bc6338fcb6df436584bf5de2f11a98ae HTTP/1.1
    Host: vmadmin.neoquard.com.br
    Content-Type: application/json
    Cache-Control: no-cache

    ```