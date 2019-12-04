# Medialogia api wrapper

# Installation

Install using `pip`...

    pip install medialogia-api-wrapper

## Medialogia api documentation
* http://sm.howto.mlg.ru/wp-content/uploads/2019/01/Rukovodstvo-po-API.pdf

### Usage
```python
from medialogia import Client
client = Client('<login>', '<password>')

# create report
client.create_report(search_query='query', author_urls=['http://test.ru'], blog_urls=['http://test,ru'])

# delete report
client.delete_report(report_id='<report_id>')

# get reports
from datetime import datetime
reports = client.get_reports(report_id='<report_id>',
                   date_from=datetime(2019, 11, 20, 0, 0, 0),
                   date_to=datetime(2019, 11, 23, 0, 0, 0))

# get posts by objects
reports_by_objs = client.get_posts_by_objects(
                   report_id='<report_id>',
                   date_from=datetime(2019, 11, 20, 0, 0, 0),
                   date_to=datetime(2019, 11, 23, 0, 0, 0)
)

# update report
client.update_report.create_report(search_query='query', author_urls=['http://test.ru'], blog_urls=['http://test,ru'])

# get posts with sort
post_with_sorts = client.get_posts_with_sort(
                   report_id='<report_id>',
                   date_from=datetime(2019, 11, 20, 0, 0, 0),
                   date_to=datetime(2019, 11, 23, 0, 0, 0),
                   sort_type=1,
                   page_size=50,
                   page_index=1)

# get posts from timestamp
posts_from_timestamp = client.get_posts_from_timestamp(
                        report_id='<report_id>',
                        timestamp=datetime(2019, 11, 20, 0, 0, 0),
                        page_index=1,
                        page_size=5)
# create report by post urls
client.create_report_by_post_urls(post_urls=['http://test.ru'])

# create report history
report_history = client.create_report_history(report_id='<report_id>', date_from=datetime(2019, 11, 20, 0, 0, 0))
```

#### TODO
* examples
* tests