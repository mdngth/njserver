njserver
========

node js server for smart home

TODO 1. need https proto

    http://book.mixu.net/node/ch10.html

    openssl genrsa -out privatekey.pem 1024
    openssl req -new -key privatekey.pem -out certrequest.csr
    openssl x509 -req -in certrequest.csr -signkey privatekey.pem -out certificate.pem

    // HTTPS
    var https = require('https');
    // read in the private key and certificate
    var pk = fs.readFileSync('./privatekey.pem');
    var pc = fs.readFileSync('./certificate.pem');
    var opts = { key: pk, cert: pc };
    // create the secure server
    var serv = https.createServer(opts, function(req, res) {
      console.log(req);
      res.end();
    });
    // listen on port 443
    serv.listen(443, '0.0.0.0');

    official docs - http://nodejs.org/api/https.html

TODO 2. authentication (passport js)
