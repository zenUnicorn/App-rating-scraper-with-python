# App-rating-scraper-with-python
App-rating-scraper-with python (Slack App).
I will be adding this .README file, so that you can easily get access to the code.

## Step 1
Installation of the app store library using `pip` .
```python
pip install app_store_scraper 

#or

pip3 install app_store_scraper

```

## Step 2
```python
import pandas as pd
import numpy as np
import json

from app_store_scraper import AppStore
slack = AppStore(country='us', app_name='slack', app_id = '618783545')

slack.review(how_many=2000)

```

```python
slack.reviews
```

## Step 3
```python
slackdf = pd.DataFrame(np.array(slack.reviews),columns=['review'])
slackdf2 = slackdf.join(pd.DataFrame(slackdf.pop('review').tolist()))
slackdf2.head()
```

## Step 4
```python
slackdf2.to_csv('Slack-app-reviews.csv')
```

The link to the article will be added here after publishing on FreeCodeCamp.

Happy Coding!

