---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - ruby
  - python
  - javascript

toc_footers:
  - <a href='https://rapidapi.com/newscatcher-api-newscatcher-api-default/api/free-news/pricing'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true

code_clipboard: true
---

# Introduction
```
█▀▀ █▀█ █▀▀ █▀▀   █▄░█ █▀▀ █░█░█ █▀   ▄▀█ █▀█ █  
█▀░ █▀▄ ██▄ ██▄   █░▀█ ██▄ ▀▄▀▄▀ ▄█   █▀█ █▀▀ █  
```



Welcome to the documentation for Free News API by [NewsCatcher](https://newscatcherapi.com/)!
 
**This is an absolutely free API for all your non-commercial use cases!** No credit card required to subscribe.

<aside class="notice">
    This API exists because we saw many developers, indie hackers, students, data scientsts, etc. willing to build something "cool" & non-commercial with news data. 
    
    </br> </br> So, we decided to make something you can actually rely on without thinking about how not to exceed the "trial" plan.

</aside>

Just one rule: put our website into [credits](https://newscatcherapi.com/) of whatever you're planning to release. 



## Free News API features

* unlimited API calls (1 call/second rate limit)
* ~120,000 news articles per day for [contributors](#contributors) (~70,000 for basic users)
* filter by keyword, language, topic, country, source, published time for contributors (just keyword & language by default)


This API documentation page was created with [Slate](https://github.com/slatedocs/slate). That's a super cool & open-sourced tool to write documentations!

# Contributors

<aside class="notice">
    "Contributors" is simply a plan that gives  more access to the Free News API. 
</aside>

We're just going to ask you to fill [this Google Form](https://docs.google.com/forms/d/e/1FAIpQLSdmhTLIonkyIx7mE41SaN1X0cZbiRTz7v9TTPflR8RJnMR5vA/viewform). It will help us better understand you (our user). 

In exchange, you get more data:


| **Feature**         |         Contributor Plan        |            Basic Plan            |
|---------------------|:-------------------------------:|:--------------------------------:|
| **API Calls**       |            unlimited            |             unlimited            |
| **Request Rate**    |    can be increased on demand   |             1 req/sec            |
| **Sources**         | ~top 800<br>(~120k articles/day) | ~top 400<br>(~70k articles/day) |
| **Filters**         |               ALL               |        `q` and `lang` only       |
| **Articles/call**   |       100 max (50 default)      |        25 max (25 default)       |
| **Historical Data** |        Up to 1 month old        |         Up to 1 week old         |


## How to obtain "Contributor Plan"
1. Fill the [form](https://docs.google.com/forms/d/e/1FAIpQLSdmhTLIonkyIx7mE41SaN1X0cZbiRTz7v9TTPflR8RJnMR5vA/viewform). It will take you approx 5 mins to complete
2. You will be invited to the plan within 24 business hours



## A list of great projects built with Free News API
* [Their News](https://www.their.news/)
* [Browser for NewsCatcher Free API](https://newscatcher-browser.vercel.app/)



# Authentication

Authentication is done via RapidAPI. You will receive an API key that you'd have to pass into a `HEADER`

1. Create a [RapidAPI](https://rapidapi.com/) account. Go to  __[rapidapi.com](https://rapidapi.com/)__. You can sign up using email, Google, Github, or Facebook.
2.  Go to the **Pricing page** of the [Free News API](https://rapidapi.com/newscatcher-api-newscatcher-api-default/api/free-news/pricing). Choose a **Basic Plan**. Just click on **Select Plan** button. That's it.
3. Go to ***Endpoint*** tab. Test any endpoint. You can choose Code Snippet for almost any programming language or terminal. Your unique API key will be already pasted.


# Example Call



```shell
curl --request GET \
	--url 'https://free-news.p.rapidapi.com/v1/search?q=bitcoin&lang=en&page=1&page_size=25' \
	--header 'x-rapidapi-host: free-news.p.rapidapi.com' \
	--header 'x-rapidapi-key: <YOUR API KEY>'
```

```python
import requests

url = "https://free-news.p.rapidapi.com/v1/search"

querystring = {"q":"bitcoin","lang":"en","page":"1","page_size":"25"}

headers = {
    'x-rapidapi-key': "<YOUR API KEY>",
    'x-rapidapi-host': "free-news.p.rapidapi.com"
    }

response = requests.request("GET", url, headers=headers, params=querystring)

print(response.text)
```

```ruby
require 'uri'
require 'net/http'
require 'openssl'

url = URI("https://free-news.p.rapidapi.com/v1/search?q=bitcoin&lang=en&page=1&page_size=25")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["x-rapidapi-key"] = '<YOUR API KEY>'
request["x-rapidapi-host"] = 'free-news.p.rapidapi.com'

response = http.request(request)
puts response.read_body
```

```javascript
import axios from "axios";

const options = {
  method: 'GET',
  url: 'https://free-news.p.rapidapi.com/v1/search',
  params: {q: 'bitcoin', lang: 'en', page: '1', page_size: '25'},
  headers: {
    'x-rapidapi-key': '<YOUR API KEY>',
    'x-rapidapi-host': 'free-news.p.rapidapi.com'
  }
};

axios.request(options).then(function (response) {
	console.log(response.data);
}).catch(function (error) {
	console.error(error);
});
```
> Make sure to replace `<YOUR API KEY>` with your API key.

An example of a call that search for all mentions of 'bitcoin' in English articles


# Example Response Object

> The above command returns JSON structured like this:

```json
{
    "status": "ok",
    "total_hits": 430,
    "page": 1,
    "total_pages": 215,
    "page_size": 25,
    "articles": [
        {
            "title": "bitcoin: Moving beyond Bitcoin to the next crypto revolution in 2021",
            "author": null,
            "published_date": "2021-03-31 10:29:00",
            "published_date_precision": "full",
            "link": "https://economictimes.indiatimes.com/markets/stocks/news/moving-beyond-bitcoin-to-the-next-crypto-revolution-in-2021/articleshow/81773999.cms",
            "clean_url": "indiatimes.com",
            "summary": "ET Spotlight SpecialThe dramatic rise in Bitcoin value has put cryptocurrency on the map in the investment space. Since its inception - not over a decade ago, Bitcoin has surpassed great heights in terms of value. It is the biggest cryptocurrency\n with a $1 trillion economy. While Bitcoin is the largest cryptocurrency, there are over 5000+ cryptocurrencies currently in circulation, many of which are listed on the CoinSwitch\n Kuber app. However, most people are unaware of these currencies. Severa",
            "rights": "indiatimes.com",
            "rank": 325,
            "topic": "economics",
            "country": "IN",
            "language": "en",
            "authors": [],
            "media": "https://img.etimg.com/thumb/msid-81773937,width-1070,height-580,imgsize-101309,overlay-etmarkets/photo.jpg",
            "is_opinion": false,
            "twitter_account": "@EconomicTimes",
            "_score": 10.445324,
            "_id": "d249a630bc9e1b76287940503041b1f4"
        },
        {
            "title": "Bitcoin and the Future of Decentralized Finance",
            "author": null,
            "published_date": "2021-03-31 12:58:12",
            "published_date_precision": "full",
            "link": "https://hbr.org/podcast/2021/03/bitcoin-and-the-future-of-decentralized-finance",
            "clean_url": "hbr.org",
            "summary": "You have 1 free articles left this month. You are reading your last free article for this month. Create an account to read 2 more. \n \n\n March 31, 2021 Meltem Demirors, Chief Strategy Officer at CoinShares, joins Azeem Azhar to explore the potential and politics of cryptocurrencies: from the ideological origins of Bitcoin to the new wave of decentralized financial products that could disrupt traditional finance.\nThey also discuss:\n\nWhy the values of the Cypherpunk community are enshrined in Bitco",
            "rights": "hbr.org",
            "rank": 273,
            "topic": "news",
            "country": null,
            "language": "en",
            "authors": [],
            "media": "https://hbr.org/resources/images/article_assets/2019/04/Exponential_View-WordPress.png",
            "is_opinion": false,
            "twitter_account": "@harvardbiz",
            "_score": 10.325988,
            "_id": "9380a6166913f551633fb7095fd9ded9"
        }
    ],
    "user_input": {
        "q": "bitcoin",
        "lang": "en",
        "from": "2021-03-25 00:00:00",
        "sort_by": "relevancy",
        "page": 1,
        "size": 25
    }
}
```



# API Specs

<aside class="notice">
    There is only one endpoint called "/v1/search"
</aside>

## Request Parameters

| Parameter   |    Type    | Format, Examples                                                                                              | Description                                                                                                                                              | Basic Plan | Contributor Plan |   |
|-------------|:----------:|---------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------|:----------:|:----------------:|---|
| `q`         |  *string*  |        See Advanced Querying section below                                                                                                     | What you are searching for                                                                                                                               |     [x]    |        [x]       |   |
| `lang`      |  *string*  |         Following languages are also changing the searching model: `af`, `ar`, `bg`, `bn`, `ca`, `cn`, `cs`, `cy`, `da`, `de`, `el`, `en`, `es`, `et`, `fa`, `fi`, `fr`, `gu`, `he`, `hi`, `hr`, `hu`, `id`, `it`, `ja`, `kn`, `ko`, `lt`, `lv`, `mk`, `ml`, `mr`, `ne`, `nl`, `no`, `pa`, `pl`, `pt`, `ro`, `ru`, `sk`, `sl`, `so`, `sq`, `sv`, `sw`, `ta`, `te`, `th`, `tl`, `tr`, `tw`, `uk`, `ur`, `vi`                                                                                                      | Specifies the language of the search.                                                                      |     [x]    |        [x]       |   |
| `search_in` |  *string*  |                                                                                                               | By default, we search what you specified in q in both title and summary of the article. <br>However, you can limit this to either `title` or `summary`   |     [ ]    |        [x]       |   |
| `from`      | *datetime* |                `YYYY/mm/dd`                                                                                               | From which point in time to start the search. No specific format is required.<br>Default timezone is UTC                                                 |     [ ]    |        [x]       |   |
| `to`        | *datetime* |                 `YYYY/mm/dd`                                                                                              | Until which point in time to search for. Default timezone is UTC                                                                                         |     [ ]    |        [x]       |   |
| `country`   |  *string*  | [2-letter code](https://www.iban.com/country-codes). US, for example.                                                                            | Country to which you want to narrow your search. This parameter is [experimental]. <br>We advise you to use it in conjunction with the `lang` parameter. |     [ ]    |        [x]       |   |
| `topic`     |  *string*  | `news`, `sport`, <br>`tech`, `world`, <br>`finance`, `politics`, <br>`business`, `economics`, `entertainment`, <br>`beauty`, `gaming`| The topic to which you want to restrict the articles of your choice. <br>This parameter is [experimental].                                               |     [ ]    |        [x]       |   |
| `sources`   |   *list*   | `source1`,`source2`, `source3`, <br>or `source1` if only 1 source                                             | One or more news resources to filter your search. <br>It should be the normal form of the URL, for example, nytimes.com, theguardian.com                 |     [ ]    |        [x]       |   |
| `page`      |    *int*   |                                                                                                               | Number of the page. Use it to scroll through the results.                                                                                                |     [x]    |        [x]       |   |
| `page_size` |    *int*   |                                                                                                               | How many articles to return per page.                                                                                                                    |     [x]    |        [x]       |   |


### Advanced Querying

* **Exact Match ("quotes")**

Use double quotes for **exact match**.

When you want to search for the English (`lang=en`) articles that mention `Tim Cook` you should do the following query:

`q="Tim Cook"`

If you write `q=Tim Cook` then, it will bee treated as `q=Tim OR Cook`. In that case, every article that mentions `tim` or `cook` will match. 

Moreover, if you specify `lang=en` that will also match the articles with `cooking`, `cooked`, and other stems of word `cook`


* **Boolean: AND**
`AND` can also be written as `&&`

`AND` operator makes tokens from both sides to be present in the text. For example, if we want both `Microsoft` and `Tesla` to be present in the returned news articles, our `q` parameter should look as follows:

`q=Microsoft AND Tesla` 

or 

`q=Microsoft && Tesla`


* **Boolean: OR**

`OR` can also be written as `||`

`OR` operator means that either the left or the right sides of `OR` have to be satisfied. 

`OR` is the default operator. When your `q` input is more than 1 word, `OR` operator is added between each word behind the scenes. Therefore, `Apple Microsoft Tesla` is the same as `Apple OR Microsoft OR Tesla`

You should use **Grouping** when you want to logically group a set of tokens. For example:

`q=(Apple AND Cook) OR (Microsoft AND Gates)`

or

`q=(Apple && Cook) || (Microsoft && Gates)`


* **Boolean: NOT**

`NOT` can also be written as `!`

Use `NOT` operator when you want the token from its right to not be present. For example, if we want to search for articles about `Microsoft` and **not** about `Tesla`, our `q` parameter should look as follows:

`q=Microsoft NOT Tesla`

or 

`q=Microsoft !Tesla`


* **MUST (+) & MUST NOT (-)**

Prepend a token with a `+` sign if it **MUST** appear in the searched text

Make sure that your API call is URL encoded. Check the `user_input` object in the Response Body to see how our back-end saw your request.

`+` **will be escaped by default in many situations.**

Prepend a token with a `-` sign if it **MUST NOT** appear in the searched text

For example, if we want to search for news articles that contain `Elon Musk` but not `Grimes`, we have to write:

`q=Elon Musk -Grimes`

"But wait, the query above will also match the documents where only `Elon` or `Musk`  are present" Shouldn't we write `+Elon +Musk -Grimes` ?

If we write `+Elon +Musk -Grimes` that will mean that `Elon` and `Musk` should be present in the text, however, not in that particular. The "correct" query should look like this:

`q="Elon Musk" -Grimes`

In this case, we will search for exact match of `"Elon Musk"` , plus, `Grimes` must not be present. 

**Pro Tip**. In general, you should always put person and company names into quotes


_______
## Return Body
> JSON return body example:

```json
{
    "status": "ok",
    "total_hits": 430,
    "page": 1,
    "total_pages": 215,
    "page_size": 25,
    "articles": [
        {
            "title": "bitcoin: Moving beyond Bitcoin to the next crypto revolution in 2021",
            "author": null,
            "published_date": "2021-03-31 10:29:00",
            "published_date_precision": "full",
            "link": "https://economictimes.indiatimes.com/markets/stocks/news/moving-beyond-bitcoin-to-the-next-crypto-revolution-in-2021/articleshow/81773999.cms",
            "clean_url": "indiatimes.com",
            "summary": "ET Spotlight SpecialThe dramatic rise in Bitcoin value has put cryptocurrency on the map in the investment space. Since its inception - not over a decade ago, Bitcoin has surpassed great heights in terms of value. It is the biggest cryptocurrency\n with a $1 trillion economy. While Bitcoin is the largest cryptocurrency, there are over 5000+ cryptocurrencies currently in circulation, many of which are listed on the CoinSwitch\n Kuber app. However, most people are unaware of these currencies. Severa",
            "rights": "indiatimes.com",
            "rank": 325,
            "topic": "economics",
            "country": "IN",
            "language": "en",
            "authors": [],
            "media": "https://img.etimg.com/thumb/msid-81773937,width-1070,height-580,imgsize-101309,overlay-etmarkets/photo.jpg",
            "is_opinion": false,
            "twitter_account": "@EconomicTimes",
            "_score": 10.445324,
            "_id": "d249a630bc9e1b76287940503041b1f4"
        },
        {
            "title": "Bitcoin and the Future of Decentralized Finance",
            "author": null,
            "published_date": "2021-03-31 12:58:12",
            "published_date_precision": "full",
            "link": "https://hbr.org/podcast/2021/03/bitcoin-and-the-future-of-decentralized-finance",
            "clean_url": "hbr.org",
            "summary": "You have 1 free articles left this month. You are reading your last free article for this month. Create an account to read 2 more. \n \n\n March 31, 2021 Meltem Demirors, Chief Strategy Officer at CoinShares, joins Azeem Azhar to explore the potential and politics of cryptocurrencies: from the ideological origins of Bitcoin to the new wave of decentralized financial products that could disrupt traditional finance.\nThey also discuss:\n\nWhy the values of the Cypherpunk community are enshrined in Bitco",
            "rights": "hbr.org",
            "rank": 273,
            "topic": "news",
            "country": null,
            "language": "en",
            "authors": [],
            "media": "https://hbr.org/resources/images/article_assets/2019/04/Exponential_View-WordPress.png",
            "is_opinion": false,
            "twitter_account": "@harvardbiz",
            "_score": 10.325988,
            "_id": "9380a6166913f551633fb7095fd9ded9"
        }
    ],
    "user_input": {
        "q": "bitcoin",
        "lang": "en",
        "from": "2021-03-25 00:00:00",
        "sort_by": "relevancy",
        "page": 1,
        "size": 25
    }
}
```


|Object     |Sub Object    |Description                                                                                                                                                                                                      |Open|
|-----------|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----|
|status     |              |Returns ok if everything went well.   Returns error in case of an error (plus 2 additional fields in case of error — error_code and message)                                                                     |    |
|total_hits |              |How many news articles match your search criterion. Maximum is 10,000                                                                                                                                            |    |
|page       |              |Page where you are at                                                                                                                                                                                            |    |
|total_pages|              |How many pages you can access given your page_size parameter                                                                                                                                                     |    |
|page_size  |              |How many items are present in articles object                                                                                                                                                                    |    |
|articles:  |              |News articles found. list                                                                                                                                                                                        |    |
|           |`title`         |Title of the article                                                                                                                                                                                             |    |
|           |`author`        |Author of the article                                                                                                                                                                                            |    |
|           |`published_date`|Published date & time                                                                                                                                                                                            |    |
|           |`published_date_precision`         |Shows how well we think we detected the published date                                                                                                                                                                                          |    |
|           |`link`          |Full URL of the article                                                                                                                                                                                          |    |
|           |`clean_url`     |URL of the article's source                                                                                                                                                                                      |    |
|           |`summary`       |first 500 characters of the article body                                                                                                                                                                                          |    |
|           |`rights`        |Copyright                                                                                                                                                                                                        |    |
|           |`rank`          |Rank of the source website (clean_url)                                                                                                                                                                           |    |
|           |`topic`         |Topic of the article [experimental]                                                                                                                                                                              |    |
|           |`country`       |Country of the publisher [experimental]                                                                                                                                                                          |    |
|           |`language`      |Language of the article                                                                                                                                                                                          |    |
|           |`authors`        |Authors of the article                                                                                                                                                                                            |    |
|           |`media`         |Thumbnail media of the article                                                                                                                                                                                               |    |
|           |`is_opinion`     |Opinion article or not                                                                                                                                                                                      |    |
|           |`twitter_account`     |Twitter account of the publisher                                                                                                                                                                                  |    |
|           |`_id`           |Newscatcher API's unique identifier for each news article                                                                                                                                                        |    |
|           |`_score`        |How well the article is matching your search criteria. _score is different for each search you make. The best matching article has the highest score                                                             |    |
|user_input:|              |Object that returns how our backend saw your request. It shows you which parameters have been used to perform a search. Useful for debugging, especially to check if there is any problem with URL encoding. list|    |
|           |q             |                                                                                                                                                                                                                 |    |
|           |search_in     |                                                                                                                                                                                                                 |    |
|           |lang          |                                                                                                                                                                                                                 |    |
|           |country       |                                                                                                                                                                                                                 |    |
|           |from          |                                                                                                                                                                                                                 |    |
|           |to            |                                                                                                                                                                                                                 |    |
|           |ranked_only   |                                                                                                                                                                                                                 |    |
|           |from_rank     |                                                                                                                                                                                                                 |    |
|           |to_rank       |                                                                                                                                                                                                                 |    |
|           |sort_by       |                                                                                                                                                                                                                 |    |
|           |page          |                                                                                                                                                                                                                 |    |
|           |size          |                                                                                                                                                                                                                 |    |
|           |sources       |                                                                                                                                                                                                                 |    |
|           |not_sources   |                                                                                                                                                                                                                 |    |
|           |topic         |                                                                                                                                                                                                                 |    |




# Debugging

Internally, we try to catch all the problems that might arise with your search. You have to worry only when you get error code `400` because that (usually) means that you did something wrong. We will return an error message that should help you understand what went wrong.

If you see a `500` status code — that means that something is wrong on our side.

While developing, look at `user_input` object that returns all of your parameters. If you made a mistake, or some characters were not correctly parsed because of the URL-encoding, you will see that.





