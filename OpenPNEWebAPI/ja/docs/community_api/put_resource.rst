.. _community_api_put_resource:

============================
コミュニティ::エントリの更新
============================

リクエスト
==========

リクエストの方法
----------------

メンバ URI に対して PUT リクエストをおこなう。

::

  POST /api.php/feeds/community/{community_id} HTTP/1.1
  Host: example.com
  Content-Type: application/atom+xml; charset=utf-8

リクエストパラメータ
--------------------

なし

リクエスト本文
--------------

以下のサンプルに登場する要素をすべて含めた XML 文書である必要がある。

::

  <?xml version="1.0" encoding="UTF-8" ?>
  <entry xmlns="http://www.w3.org/2005/Atom">
    <id>http://example.com/community/{community_id}</id>
    <title type="text">コミュニティタイトル</title>
    <content type="text">コミュニティ本文</content>
    <author>
      <name>メンバーのニックネーム</name>
      <uri>http://example.com/member/{member_id}</uri>
    </author>
  </entry>


レスポンス
==========

レスポンスヘッダ
----------------

HTTPステータスコード 200 を返す。

::

  HTTP/1.1 200 Ok
  Content-Type: application/atom+xml; charset=utf-8

レスポンス本文
--------------

XML 文書を返す。

::

  <?xml version="1.0" encoding="UTF-8" ?>
  <entry xmlns="http://www.w3.org/2005/Atom">
    <id>http://example.com/community/{community_id}</id>
    <published>2009-01-25T19:40:22+09:00</published>
    <updated>2009-01-25T19:40:22+09:00</updated>
    <title type="text">コミュニティタイトル</title>
    <content type="text">コミュニティ本文</content>
    <author>
      <name>投稿したメンバーのニックネーム</name>
      <uri>http://example.com/member/{member_id}</uri>
    </author>
    <link rel="edit" type="application/atom+xml" href="http://example.com/api.php/feeds/community/{community_id}"/>
    <link rel="self" type="application/atom+xml" href="http://example.com/api.php/feeds/community/1"/>
    <link rel="alternate" type="text/html" href="http://example.com/community/{community_id}"/>
    <link rel="alternate" href="http://example.com/mobile_frontend.php/community/{community_id}"/>
  </entry>
