**Entity Produtos**
----
  Dados dos produtos do cliente.

* **URL**

  http://vmadmin.neoquard.com.br/api/v1/produtos?uid=:uid&token=:token

* **Method:**

  `POST`
  
*  **URL Params**

   **Required:**
   
   `uid=[string]` Código do usuário. <br />
   `token=[string]` Chave de acesso.

* **Fields description**

    `referencia=[string]` Código (Informe aqui o código do seu ERP).<br/>
    `ds_mat=[string]` Descrição do produto ou serviço.<br/>
    `referencia_forn=[string]` Código do fornecedor.<br/>
    `preco_venda=[double]` Valor unitário de venda.<br/>
    `ds_marca=[string]` Descrição da marca.<br/>
    `dados_tec=[string]` Dados técnicos.<br/>
    `idum=[string]`Código da unidade de medida.<br/>
    `estoque_real=[string]`Quantidade em estoque.<br/>
    `vlr_custo=[string]`Valor do custo.<br/>
    `cod_barras=[string]`Código de barras.<br/>
    `cod_sim1=[string]`<br/>
    `cod_sim2=[string]`<br/>
    `cod_sim3=[string]`<br/>
    `cod_sim4=[string]`<br/>
    `cod_sim5=[string]`<br/>
    `perc_comissao=[string]`Percentual de comissão.<br/>
    `ativo=[string]`Status de ativo.<br/>
    `tipo=[string]`P=produto, S=Serviço.<br/>
    `grade=[string]`<br/>
    `tamanho=[string]`<br/>
    `cor=[string]`<br/>
    `calc_estoque=[string]`<br/>
    `sidag=[string]`Código da empresa.<br/>
    `sidat=[string]`Código da filial.<br/>
    `integra_estoque=[string]`<br/>
    `integra_id=[string]`<br/>
    `sidmaterial=[string]`<br/>
    `_rev=[string]`<br/>

* **Json body example**
    ```json
     {
        "referencia": "1", 
        "ds_mat": "Relógio",
        "referencia_forn": "A0001",
        "preco_venda": 100.23,
        "ds_marca": "Aqua",
        "dados_tec": "Relógio de pulso",
        "idum": "Un",
        "estoque_real": 100,
        "vlr_custo": 50.32,
        "cod_barras": "0000000001",
        "cod_sim1": "",
        "cod_sim2": "",
        "cod_sim3": "",
        "cod_sim4": "",
        "cod_sim5": "",
        "perc_comissao": 0,
        "ativo": "S",
        "tipo": "",
        "grade": "",
        "tamanho": "",
        "cor": "",
        "calc_estoque": "S",
        "sidag": "29d62c70a6a711e6845b3722a8a76e67",
        "sidat": "29f37870a6a711e6845b3722a8a76e67",
        "integra_estoque": "",
        "integra_id": "",
        "sidmaterial": "",
        "_rev": "" 
    }
    ```



* **Success Response:**
 
    ```json
    { 
        error: false, 
        msg: "ok", 
        produto:
            { 
                "sidmaterial": "1be5387078f011e68d9b75e32d56f4d3",
                "_rev": "1" 
            }
    } 
    ```
    >ATENÇÃO:<br>
    >SALVE OS DOIS CAMPOS DE RETORNO ('sidmaterial' e '_rev') NO SEU ERP PARA FUTURAS ATUALIZAÇÕES.
 
  
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
    POST /api/v1/produtos?uid=8048a35ead8c45b796ce04e52d1dd489&amp;token=bc6338fcb6df436584bf5de2f11a98ae HTTP/1.1
    Host: vmadmin.neoquard.com.br
    Content-Type: application/json
    Cache-Control: no-cache

    {
    "referencia": "1", 
    "ds_mat": "Relógio",
    "referencia_forn": "A0001",
    "preco_venda": 100.23,
    "ds_marca": "Aqua",
    "dados_tec": "Relógio de pulso",
    "idum": "Un",
    "estoque_real": 100,
    "vlr_custo": 50.32,
    "cod_barras": "0000000001",
    "cod_sim1": "",
    "cod_sim2": "",
    "cod_sim3": "",
    "cod_sim4": "",
    "cod_sim5": "",
    "perc_comissao": 0,
    "ativo": "S",
    "tipo": "",
    "grade": "",
    "tamanho": "",
    "cor": "",
    "calc_estoque": "S",
    "sidag": "29d62c70a6a711e6845b3722a8a76e67",
    "sidat": "29f37870a6a711e6845b3722a8a76e67",
    "integra_estoque": "",
    "integra_id": "",
    "sidmaterial": "",
    "_rev": "" 
    }
    ```
