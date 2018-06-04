# To ensure the security of your API, you must sign the API request. Alibaba Cloud uses the signature in the request to verify the identity of the person who calls the API. {#concept_sqb_c21_12b .concept}

Each time you manually call an API, you must use the AccessKey secret to calculate the HMAC value of the encoded and sorted request string as defined RFC 2104. The calculated HMAC value is the value of the signature parameter in the request.

For Test.
