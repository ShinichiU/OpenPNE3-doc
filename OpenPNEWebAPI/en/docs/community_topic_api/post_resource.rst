.. _community_topic_api_post_resource:

===========================
Community Topic::Post Entry
===========================

Request
=======

The Way to Request
------------------

Do POST to Collection URI.

::

  POST /api.php/feeds/communityTopic/community/{community_id} HTTP/1.1
  Host: example.com
  Content-Type: application/atom+xml; charset=utf-8

Request Parameter
-----------------

None

Request Body
------------

It must be a XML Document that contains all of element in the following example.

::

  <?xml version="1.0" encoding="UTF-8" ?>
  <entry xmlns="http://www.w3.org/2005/Atom">
    <title type="text">Title</title>
    <content type="text">Body</content>
    <author>
      <name>Nickname of Author</name>
      <uri>http://example.com/member/{member_id}</uri>
    </author>
  </entry>

Response
========

Response Header
---------------

Returns HTTP Status Code 201.

The Location Header contains Member URI for new resource.

::

  HTTP/1.1 201 Created
  Location: http://example.com/api.php/feeds/diary/{diary_id}
  Content-Type: application/atom+xml; charset=utf-8

Response Body
-------------

Returns XML Document.

::

  <?xml version="1.0" encoding="UTF-8" ?>
  <entry xmlns="http://www.w3.org/2005/Atom">
    <id>http://example.com/communityTopic/{community_topic_id}</id>
    <published>2009-01-25T19:40:22+09:00</published>
    <updated>2009-01-25T19:40:22+09:00</updated>
    <title type="text">Title</title>
    <content type="text">Body</content>
    <author>
      <name>Nickname of Author</name>
      <uri>http://example.com/member/{member_id}</uri>
    </author>
    <link rel="edit" type="application/atom+xml" href="http://example.com/api.php/feeds/communityTopic/{community_topic_id}"/>
    <link rel="self" type="application/atom+xml" href="http://example.com/api.php/feeds/communityTopic/1"/>
    <link rel="alternate" type="text/html" href="http://example.com/communityTopic/{community_topic_id}"/>
    <link rel="alternate" href="http://example.com/mobile_frontend.php/communityTopic/{community_topic_id}"/>
  </entry>
