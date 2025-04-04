---
title: chrome_settings_overrides
slug: Mozilla/Add-ons/WebExtensions/manifest.json/chrome_settings_overrides
---
{{AddonSidebar}}

`chrome_settings_overrides` キーを使ってブラウザー設定を上書きします。2 つの設定が利用できます:

- `"homepage"`、これによりブラウザーのホームページを上書きできます。
- `"search_provider"`、これにより新しい検索エンジンを追加できます。

```json
"chrome_settings_overrides" : {
  "homepage": "https://developer.mozilla.org/"
}
```

```json
"chrome_settings_overrides": {
  "search_provider": {
    "name": "Discogs",
    "search_url": "https://www.discogs.com/search/?q={searchTerms}",
    "keyword": "disc",
    "favicon_url": "https://www.discogs.com/favicon.ico"
  }
}
```

<table class="properties">
  <tbody>
    <tr>
      <th colspan="2" scope="row">
        マニフェストキー: <code>chrome_settings_overrides</code>
      </th>
    </tr>
    <tr>
      <th scope="row">型</th>
      <td><code>Object</code></td>
    </tr>
    <tr>
      <th scope="row">必須</th>
      <td>No</td>
    </tr>
  </tbody>
</table>

## 構文

`chrome_settings_overrides` キーは次のプロパティを持つオブジェクトです:

<table class="fullwidth-table standard-table">
  <thead>
    <tr>
      <th scope="col">名前</th>
      <th scope="col">型</th>
      <th scope="col">説明</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>homepage</code></td>
      <td><code>String</code></td>
      <td>
        <p>Defines the page to be used as the browser's homepage.</p>
        <p>The replacement is given as a URL. The URL may:</p>
        <ul>
          <li>
            point to a file bundled with the extension, in which case it is
            given as a URL relative to the manifest.json file
          </li>
          <li>be a remote URL, such as "https://developer.mozilla.org/".</li>
        </ul>
        <p>
          If two or more extensions both set this value, then the setting from
          the most recently installed one will take precedence.
        </p>
        <p>
          To override new tabs, use "<a
            href="/ja/Add-ons/WebExtensions/manifest.json/chrome_url_overrides"
            >chrome_url_overrides</a
          >" instead.
        </p>
        <p>
          This is a
          <a
            href="/ja/Add-ons/WebExtensions/Internationalization#Internationalizing_manifest.json"
            >localizable property</a
          >.
        </p>
      </td>
    </tr>
    <tr>
      <td><code>search_provider</code></td>
      <td><code>Object</code></td>
      <td>
        <p>Defines a search provider to add to the browser.</p>
        <p>
          The search provider has a name and a primary search URL. Alternative
          URLs may be provided, including URLs for more specialized searches
          like image search. In the URL you supply, use
          "<code>{searchTerms}</code>" to interpolate the search term into the
          URL, like:
          <code>https://www.discogs.com/search/?q={searchTerms}</code>. You can
          also provide POST parameters to be sent along with the search.
        </p>
        <p>
          The search provider will be presented to the user alongside the
          built-in providers. If you include the
          <code>is_default</code> property and set it to <code>true</code>, the
          new search provider will be the default option. By supplying the
          <code>keyword</code> property, you enable the user to select your
          search provider by typing the keyword into the search/address bar
          before the search term.
        </p>
        <p>
          This is an object with the properties listed below. All string
          properties are
          <a
            href="/ja/Add-ons/WebExtensions/Internationalization#Internationalizing_manifest.json"
            >localizable</a
          >.
        </p>
        <dl>
          <dt><code>name</code></dt>
          <dd>String: The search engine's name, displayed to the user.</dd>
          <dt><code>search_url</code></dt>
          <dd>
            String: URL used by the search engine. This must be an HTTPS URL.
          </dd>
          <dt><code>is_default</code></dt>
          <dd>
            Boolean: True if the search engine should be the default choice.
          </dd>
          <dt><code>alternate_urls {{optional_inline}}</code></dt>
          <dd>
            Array of String: An array of alternative URLs that can be used
            instead of <code>search_url</code>.
          </dd>
          <dt><code>encoding {{optional_inline}}</code></dt>
          <dd>
            String: Encoding of the search term, specified as a
            <a
              href="https://www.iana.org/assignments/character-sets/character-sets.xhtml"
              >standard character encoding name</a
            >, such as "UTF-8".
          </dd>
          <dt><code>favicon_url {{optional_inline}}</code></dt>
          <dd>
            String: URL pointing to an icon for the search engine. This must be
            a absolute HTTP or HTTPS URL.
          </dd>
          <dt><code>image_url {{optional_inline}}</code></dt>
          <dd>String: URL used for image search.</dd>
          <dt><code>image_url_post_params {{optional_inline}}</code></dt>
          <dd>String: POST parameters to send to <code>image_url</code>.</dd>
          <dt><code>instant_url {{optional_inline}}</code></dt>
          <dd>String: URL used for instant search.</dd>
          <dt><code>instant_url_post_params {{optional_inline}}</code></dt>
          <dd>String: POST parameters to send to <code>instant_url</code>.</dd>
          <dt><code>keyword {{optional_inline}}</code></dt>
          <dd>String: Address bar keyword for the search engine.</dd>
          <dt><code>prepopulated_id {{optional_inline}}</code></dt>
          <dd>The ID of a built-in search engine to use.</dd>
          <dt><code>search_url_post_params {{optional_inline}}</code></dt>
          <dd>String: POST parameters to send to <code>search_url</code>.</dd>
          <dt><code>suggest_url {{optional_inline}}</code></dt>
          <dd>String: URL used for search suggestions.</dd>
          <dt><code>suggest_url_post_params {{optional_inline}}</code></dt>
          <dd>String: POST parameters to send to <code>suggest_url</code>.</dd>
        </dl>
      </td>
    </tr>
  </tbody>
</table>

## ブラウザーの互換性

{{Compat("webextensions.manifest.chrome_settings_overrides", 10)}}
