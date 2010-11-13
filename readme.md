GUPA J2ME SDK
================

This repository contains the open source J2ME SDK that allows you to utilize the
above on your website. Except as otherwise noted, the GUPA J2ME SDK
is licensed under the Apache Licence, Version 2.0
(http://www.apache.org/licenses/LICENSE-2.0.html)


Usage
-----

The minimal you'll need to have is in GUPAConsumer class:

	String consumerKey = "YOUR OAUTH CONSUMER KEY";
    String consumerSecret = "YOUR OAUTH CONSUMER SECRET";
    gupa = new GUPAConsumer(consumerKey, consumerSecret);
			

To make [GUPA][GUPA] calls:
	
	Hashtable params = new Hashtable();
    params.put("point", "MULTIPOINT("+azmt_dist_point_1.getString()+", "+azmt_dist_point_2.getString()+")");
    try{
		String response = gupa.api("/basic_calc/azmt_dist", params, null);
		JSONObject jsonResponse = new JSONObject(response);
		if (jsonResponse.getString("error_code").equals("0"))
			new OAuthServiceProviderException(jsonResponse.getString("error_code"));
	}catch(Exception e){
		System.out.println(e.toString());
	}

[GUPA]: http://www.geomatikuygulamalar.com/gupa


Documentation
--------
Our [wiki] can help you develop your own application with it's rich content about GUPA APIs.

[wiki]: http://www.geomatikuygulamalar.com/wiki

Feedback
--------

File bugs or other issues [here][issues].

[issues]: http://github.com/mtrcn/gupa-j2me/issues
