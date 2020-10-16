# Indonesian News API

This project provides a uniform API for various Indonesian news site.

## Supported News Site

This project is under development. No news site is supported at this moment.

## Supported APIs

This section lists all APIs that are supported by this project.

### Search

This API allows you to search for a keyword in a news site.

URL: `/api/v1/search/<news-site-code>/?q=<query>&page=<page>`

Parameters:

- `news-site-code`: The news site code. Look at [Supported News Site section](#supported-news-site) to find out the site
  code for each news site.

- `query`: The search keyword. All non-alphanumeric characters (except spaces) will be removed before sending the search
  request to the corresponding news site.

- `page`: The page number. This parameter uses 1-based index. If it is empty, the program will show the first page.

Response:

```json
[
  {
    "url": "http://domain.com/url-to-the-first-news",
    "title": "First News",
    "date": "date",
    "extraData": {
      "additional-key": "Additional info that is different between each site."
    }
  },
  {
    "url": "http://domain.com/url-to-the-second-news",
    "title": "Second News",
    "date": "date",
    "extraData": {
      "additional-key": "Additional info that is different between each site."
    }
  }
]
```

**Do note that each news site may behave differently if you send a bigger page number than the number of pages that they
have for each search keyword.**

### Homepage

This API allows you to fetch all news that are available in the news site's homepage.

URL: `/api/v1/homepage/<news-site-code>`

Parameters:

- `news-site-code`: The news site code. Look at [Supported News Site section](#supported-news-site) to find out the site
  code for each news site.

Response:

```json
[
  {
    "url": "http://domain.com/url-to-the-first-news",
    "title": "First News",
    "date": "date",
    "extraData": {
      "additional-key": "Additional info that is different between each site."
    }
  },
  {
    "url": "http://domain.com/url-to-the-second-news",
    "title": "Second News",
    "date": "date",
    "extraData": {
      "additional-key": "Additional info that is different between each site."
    }
  }
]
```