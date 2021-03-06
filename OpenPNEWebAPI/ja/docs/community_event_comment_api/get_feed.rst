.. _community_event_comment_api_get_feed:

==================================================
コミュニティイベントコメント::エントリの一覧の取得
==================================================

リクエスト
==========

リクエストの方法
----------------

コレクション URI に対して GET リクエストをおこなう。

::

  GET /api.php/feeds/communityEventComment/communityEvent/{community_event_id} HTTP/1.1
  Host: example.com

リクエストパラメータ
--------------------

* :ref:`updated-min <updated-query>` (optional)
* :ref:`updated-max <updated-query>` (optional)
* :ref:`published-min <published-query>` (optional)
* :ref:`published-max <published-query>` (optional)
* :ref:`start <start-query>` (optional)
* :ref:`max-results <max-requests-query>` (optional)

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

XML 文書を返す。取得した件数分 entry 要素を格納する。

::

  <?xml version="1.0" encoding="UTF-8" ?>
  <feed xmlns="http://www.w3.org/2005/Atom"
          xmlns:openSearch="http://a9.com/-/spec/opensearchrss/1.0/">
    <title>コミュニティイベントタイトル</title>
    <id>http://example.com/communityEvent/{community_event_id}</id>
    <updated>2009-01-28T11:23:55+09:00</updated>
    <generator uri="http://www.openpne.jp/">OpenPNE</generator>
    <link rel="self" type="application/atom+xml" href="http://example.com/api.php/feeds/communityEventComment/communityEvent/{community_event_id}"/>
    <link rel="alternate" type="text/html" href="http://example.com/communityEvent/{community_event_id}"/>
    <link rel="http://schemas.google.com/g/2005#feed" type="application/atom+xml" href="http://example.com/api.php/feeds/communityEventComment/communityEvent/{community_event_id}"/>
    <openSearch:totalResults>総件数</openSearch:totalResults>
    <openSearch:startIndex>取得を開始したエントリの番号</openSearch:startIndex>
    <openSearch:itemsPerPage>1ページあたりの件数</openSearch:itemsPerPage>
    <entry>
      <id>http://example.com/communityEventComment/{community_event_comment_id}</id>
      <published>2009-01-28T11:23:55+09:00</published>
      <updated>2009-01-28T11:23:55+09:00</updated>
      <content type="text">コミュニティイベントコメント本文</content>
      <author>
        <name>投稿したメンバーのニックネーム</name>
        <uri>http://example.com/member/{member_id}</uri>
      </author>
      <link rel="self" type="application/atom+xml" href="http://example.com/api.php/feeds/communityEventComment/{community_event_comment_id}"/>
    </entry>
    <entry>
      <id>http://example.com/communityEventComment/{community_event_comment_id}</id>
      <published>2009-01-28T11:23:55+09:00</published>
      <updated>2009-01-28T11:23:55+09:00</updated>
      <content type="text">コミュニティイベントコメント本文</content>
      <author>
        <name>投稿したメンバーのニックネーム</name>
        <uri>http://example.com/member/{member_id}</uri>
      </author>
      <link rel="self" type="application/atom+xml" href="http://example.com/api.php/feeds/communityEventComment/{community_event_comment_id}"/>
    </entry>
  </feed>
