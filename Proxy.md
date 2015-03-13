GeoXml uses client side technology and is limited by javascripts cross domain restrictions
a proxy script is a work around .. the following is an example (but a completely open example)

be sure to define the path to your proxy as a global variable on the page
var proxy = "/cgi-bin/proxy.php?";

or define your urls in terms of your proxy
var proxypath = "/cgi-bin/proxy.php?";
var url = proxypath+"url="+datasourceurl;


You can and probably should restrict  the values allowed for the url, i $_GET['url']
unless you are building a gateway or similar, use at your own risk._

proxy.php src:
```
<?php
$header[] = "Content-type: text/xml";
$post_data = '';
if(isset($GLOBALS['HTTP_RAW_POST_DATA'])){
    $post_data = $GLOBALS['HTTP_RAW_POST_DATA'];
    $header[] = "Content-length: ".strlen($post_data);
    }
$ch = curl_init( urldecode($_GET['url']) );
curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
curl_setopt($ch, CURLOPT_FOLLOWLOCATION, 1);
curl_setopt($ch, CURLOPT_TIMEOUT, 80);
curl_setopt($ch, CURLOPT_HTTPHEADER, $header);
curl_setopt($ch, CURLOPT_FAILONERROR, 0);
curl_setopt($ch, CURLOPT_VERBOSE, 1);
curl_setopt($ch, CURLOPT_COOKIEFILE, 1);
curl_setopt($ch, CURLOPT_FOLLOWLOCATION, 1);

if ( strlen($post_data)>0 ){
    curl_setopt($ch, CURLOPT_POSTFIELDS, $post_data);
}

$response = curl_exec($ch);
if (curl_errno($ch)) {
    print curl_error($ch);
} else {

    curl_close($ch);
    print $response;
}

?>
```


The above proxy script is fully open, and there are people who will tell you (if you have a rather targeted use like always getting from google or similar single source you might want to change it to test
```
$_GET['url'] 
```

variable to see if the script is being called for your purpose