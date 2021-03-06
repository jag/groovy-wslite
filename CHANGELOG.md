## 0.7.0 (2012-04-02)

* Fix [setSoapActionHeaderIfNotPresent treats the empty string same as null] (/jwagenleitner/groovy-wslite/issues/39)

## 0.6.0 (2012-02-18)

* gzip encoding now on by default for requests

## 0.5.2 (2011-12-29)

* Fix for SOAP 1.2 action header (thanks @jladenfors)
* RESTClient JSON fixes
* Fix [JSON builder does not handle properly GStrings] (/jwagenleitner/groovy-wslite/issues/33)

## 0.5.1 (2011-12-11)

* Fixed [IncompatibleClassChangeError when exceptions are thrown and using JDK 7] (/jwagenleitner/groovy-wslite/issues/31)

## 0.5.0 (2011-12-05)

* Auto detect soap version for SOAPClient.send(String)
* Replaced custom HTTPHeaderMap with a case-insensitive key comparator TreeMap
* Adopted Semantic Versioning

## 0.4 (2011-10-14)

* Added per client/request Proxy support

[List of issues resolved] (/jwagenleitner/groovy-wslite/issues?milestone=4&state=closed)

## 0.3 (2011-09-21)

[List of issues resolved] (/jwagenleitner/groovy-wslite/issues?sort=created&direction=desc&state=closed&page=1&milestone=2)

## 0.2 (2011-09-10)

[List of issues resolved] (/jwagenleitner/groovy-wslite/issues?sort=created&direction=desc&state=closed&page=1&milestone=1)

#### Important changes to note

* SOAPClient
 * responses now include both the HTTPRequest `response.httpRequest` and HTTPResponse `response.httpResponse`
 * `response.http` was changed to `response.httpResponse`
 * `response.Envelope` was changed to `response.envelope`
 * exceptions now include `httpRequest` and `httpResponse` objects.
 * a `SOAPFaultException` is now being thrown anytime there is a Envelope/Body/Fault element in the response.  The
 properties `faultcode/faultstring/faultactor/detail` have been removed (these only applied to SOAP 1.1 faults).
 Instead you can access the Fault via GPathResult using `soapFaultException.fault`.

* RESTClient
 * `response.XML -> response.xml`, `response.JSON -> response.json`, `response.TEXT -> response.text`
 * exceptions now include request/response objects (if available)

* Common
 * `trustAllSSLCerts` connection parameter renamed to `sslTrustAllCerts`
 *  New connection parameters `sslTrustStoreFile` and `sslTrustStorePassword` enable trusting SSL connection based on a
 custom trust store file (see SSL section of README)
 *  Requests no longer default to trusting all SSL certs.  You must set `sslTrustAllCerts` (see SSL section of README)

## 0.1 (2011-03-27)

* Initial release
