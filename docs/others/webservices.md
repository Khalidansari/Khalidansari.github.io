---
layout: default
---
# Web Services

Parts of WSDL:
    1. Definitions - namespace, self reference of wsdl
    2. Messages - request & response objects (with part > parameter for request and return value for response)
    3. PortType - Method name + request/response (Can be of four types - two types of one ways and two types of two ways)
    4. Binding - How the request/response will be transmitted (SOAP, HTTP). Service ports are also called endpoints.
    5. Types (optional) - Inside this element we define both simple type and complex types of data types.

Mapping
    1. Operation > Public methods
    2. Complex type > Inner class
    3. TargetNameSpace > Class name
    4. WSDL port name > Stub class which is a Inner class with invoke method

Joke: Authoring wsdl without any editors is like great punishment for misbehaving developers

SOAP: Was created by Microsoft as a platform neutral alternative to COBRA, which is a platform specific technology. SOAP is transfer in a specific XML (soap header, soap body (payload), soap envelope(main node), soap fault(in case of error)). It is a XML based protocol.

------------------------------------------------------------------
GET /StockPrice HTTP/1.1
Host: example.org
Content-Type: application/soap+xml; charset=utf-8
Content-Length: nnn

<?xml version="1.0"?>
<env:Envelope xmlns:env="http://www.w3.org/2003/05/soap-envelope"
   xmlns:s="http://www.example.org/stock-service">
   <env:Body>
     <s:GetStockQuote>
          <s:TickerSymbol>IBM</s:TickerSymbol>
     </s:GetStockQuote>
   </env:Body>
</env:Envelope>

The response:

HTTP/1.1 200 OK
Content-Type: application/soap+xml; charset=utf-8
Content-Length: nnn

<?xml version="1.0"?>
<env:Envelope xmlns:env="http://www.w3.org/2003/05/soap-envelope"
   xmlns:s="http://www.example.org/stock-service">
   <env:Body>
     <s:GetStockQuoteResponse>
          <s:StockPrice>45.25</s:StockPrice>
     </s:GetStockQuoteResponse>
   </env:Body>
</env:Envelope>
-------------------------------------------------------------------------
REST

The request:

GET /StockPrice/IBM HTTP/1.1
Host: example.org
Accept: text/xml
Accept-Charset: utf-8

The response:

HTTP/1.1 200 OK
Content-Type: text/xml; charset=utf-8
Content-Length: nnn

<?xml version="1.0"?>
<s:Quote xmlns:s="http://example.org/stock-service">
     <s:TickerSymbol>IBM</s:TickerSymbol>
     <s:StockPrice>45.25</s:StockPrice>
</s:Quote>

-------------------------------------------------------------------------------
JAXB - Java Architecture for XML Binding (Converts XML to Java classes and vice versa)
JAXP - Java API for XML Parsing (DOM Constructs whole document in-memory while SAX does not and hence is faster)
SAX - Simple API for XML 
DOM - Document Object Model 
XSLT - XML Stylesheet Language for Transformation
XSD - XML Schema: Specification to write XMLs
JAX-WS ( Moved towards document style WS from RPC)
SOAP: Simple Object Access Protocol
REST - Representational State Transfer
JSON - Javascript Object Notation (Alternative to XML, created for better human readability)

Note: Use REST until there is a reason to use SOAP
-------------------------------------------------------------------
Differences:
---------------
1. SOAP uses only XML to exchange data while REST uses all types of data for exchange and uses standard HTTP. REST
    can use JSON also but SOAP can not.
2. SOAP can perform ACID transactions while REST cannot. 
3. SOAP is good for enterprise apps while REST is good for Internet Apps.
4. REST has no WSDL interface
5. SOAP can work over HTTP, FTP, SMTP, JMS while REST can work only over HTTP

XSLT - Mainly used for applying data to XML template (e.g. generating PDF, HTML)
            XSLT Input + XML Template > XSLT Processor > Document

Web Service Protocol Stack 
-----------------------------------
1. Transport Protocol - HTTP
2. Messaging Protocol - SOAP
3. Description Protocol - WSDL
4. Discovery Protocol - UDDI - Used to search available APIs. Not widely adopted.

REST - Uses existing methods of HTTP while SOAP allows user to create any method. 

GLUE and WSIF - are tools through which we can call webservice on command prompt easily, without doing any extra work. It download wsdl, created the java classes, compiles them and then call the service all by itself.
--------------------------------------

SOAP Request example:

POST /InStock HTTP/1.1
Host: www.example.org
Content-Type: application/soap+xml; charset=utf-8
Content-Length: 299
SOAPAction: "http://www.w3.org/2003/05/soap-envelope"
 
<?xml version="1.0"?>
<soap:Envelope xmlns:soap="http://www.w3.org/2003/05/soap-envelope">
  <soap:Header>
  </soap:Header>
  <soap:Body>
    <m:GetStockPrice xmlns:m="http://www.example.org/stock">
      <m:StockName>IBM</m:StockName>
    </m:GetStockPrice>
  </soap:Body>
</soap:Envelope>