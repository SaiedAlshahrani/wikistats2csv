# Wikistats-to-CSV

```
              ▌│║▌║▌█║▌║║▌│║▌│║▌║▌█║▌█║▌║│▌║│▌║│█║│▌║▌│█║▌│▌║│▌║║▌║▌█║▌║│▌
              ▌│║▌║▌█║▌║║▌│║▌│║▌║▌█║WIKISTATS-TO-CSV║▌│█║▌│▌║│▌║║▌║▌█║▌║│▌
              ▌│║▌║▌█║▌║║▌│║▌│║▌║▌█║▌█║▌║│▌║│▌║│█║│▌║▌│█║▌│▌║│▌║║▌║▌█║▌║│▌
```

Wikistats-to-CSV is a Python package/wrapper and command line interface (CLI) that downloads Wikipedia Statistics for a given Wikipedia in a format of CSV  from [Wikimedia Statistics](https://stats.wikimedia.org) project. 

## Install:

Wikistats-to-CSV (wikistats2csv) requires Python >=3 and the installation of a few Python packages such as `lxml==4.9.1`, `rich==12.5.1`, `pandas==1.4.3`, `selenium==3.141.0`, and `geckodriver-autoinstaller==0.1.0`. For convenience, we included the installation of these packages as a part of the setup process of Wikistats-to-CSV (wikistats2csv).  If you encounter installation errors, you might need to install these packages using `pip` manually. To download Wikistats-to-CSV (wikistats2csv), use this command:

```bash
pip install wikistats2csv
```

## Usage:

### * As CLI:

#### >> Long Flags:

```bash
$ wikistats2csv --wiki en --metric content --query pages-to-date --period all-years --filter page-type-all --interval monthly

              ▌│║▌║▌█║▌║║▌│║▌│║▌║▌█║▌█║▌║│▌║│▌║│█║│▌║▌│█║▌│▌║│▌║║▌║▌█║▌║│▌
              ▌│║▌║▌█║▌║║▌│║▌│║▌║▌█║WIKISTATS-TO-CSV║▌│█║▌│▌║│▌║║▌║▌█║▌║│▌
              ▌│║▌║▌█║▌║║▌│║▌│║▌║▌█║▌█║▌║│▌║│▌║│█║│▌║▌│█║▌│▌║│▌║║▌║▌█║▌║│▌

## Downloaded `english--pages-to-date--page-type-all--all-years--monthly.csv` successfully :-)

** Quick glance at `english--pages-to-date--page-type-all--all-years--monthly.csv` file:
                        month  total.non-content  total.content           timeRange.start             timeRange.end
0    2001-01-01T00:00:00.000Z                 28             37  2001-01-01T00:00:00.000Z  2001-02-01T00:00:00.000Z
1    2001-02-01T00:00:00.000Z                 51            175  2001-02-01T00:00:00.000Z  2001-03-01T00:00:00.000Z
..                        ...                ...            ...                       ...                       ...
257  2022-06-01T00:00:00.000Z           36945305        6518484  2022-06-01T00:00:00.000Z  2022-07-01T00:00:00.000Z
258  2022-07-01T00:00:00.000Z           37088260        6534151  2022-07-01T00:00:00.000Z  2022-08-01T00:00:00.000Z
```

#### >> Short Flags:

```bash
$ wikistats2csv -w ar -m content -q pages-to-date -p all-years -f page-type-all -i monthly

              ▌│║▌║▌█║▌║║▌│║▌│║▌║▌█║▌█║▌║│▌║│▌║│█║│▌║▌│█║▌│▌║│▌║║▌║▌█║▌║│▌
              ▌│║▌║▌█║▌║║▌│║▌│║▌║▌█║WIKISTATS-TO-CSV║▌│█║▌│▌║│▌║║▌║▌█║▌║│▌
              ▌│║▌║▌█║▌║║▌│║▌│║▌║▌█║▌█║▌║│▌║│▌║│█║│▌║▌│█║▌│▌║│▌║║▌║▌█║▌║│▌

## Downloaded `arabic--pages-to-date--page-type-all--all-years--monthly.csv` successfully :-)

** Quick glance at `arabic--pages-to-date--page-type-all--all-years--monthly.csv` file:
                        month  total.non-content  total.content           timeRange.start             timeRange.end
0    2001-01-01T00:00:00.000Z                  0            591  2001-01-01T00:00:00.000Z  2001-02-01T00:00:00.000Z
1    2001-02-01T00:00:00.000Z                  0            591  2001-02-01T00:00:00.000Z  2001-03-01T00:00:00.000Z
..                        ...                ...            ...                       ...                       ...
257  2022-06-01T00:00:00.000Z            5508072        1173410  2022-06-01T00:00:00.000Z  2022-07-01T00:00:00.000Z
258  2022-07-01T00:00:00.000Z            5538121        1180401  2022-07-01T00:00:00.000Z  2022-08-01T00:00:00.000Z 
```

### * As Python Package:

```python
>>> from wikistats2csv import Helper
>>> from wikistats2csv import Content
>>> 
>>> Content.pages_to_date(wiki='es', period='all-years', filter='page-type-all', interval='monthly')

## Downloaded `spanish--pages-to-date--page-type-all--all-years--monthly.csv` successfully :-)

** Quick glance at `spanish--pages-to-date--page-type-all--all-years--monthly.csv` file:
                        month  total.non-content  total.content           timeRange.start             timeRange.end
0    2001-01-01T00:00:00.000Z                  0              0  2001-01-01T00:00:00.000Z  2001-02-01T00:00:00.000Z
1    2001-02-01T00:00:00.000Z                  0              0  2001-02-01T00:00:00.000Z  2001-03-01T00:00:00.000Z
..                        ...                ...            ...                       ...                       ...
257  2022-06-01T00:00:00.000Z            3896209        1786321  2022-06-01T00:00:00.000Z  2022-07-01T00:00:00.000Z
258  2022-07-01T00:00:00.000Z            3903963        1792329  2022-07-01T00:00:00.000Z  2022-08-01T00:00:00.000Z 
```

## Supported Features:

### Content Metrics:

| Queries*/Functions**                                    | Periods                                                 | Filters                                                                                                                                                                                                                                                                                                                   | Intervals      |
|:-------------------------------------------------------:|:-------------------------------------------------------:|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:--------------:|
| absolute-bytes-difference/<br>absolute_bytes_difference | all-years, one-year, two-years, three-months, one-month | no-filter, page-type-content, page-type-non-content, page-type-all, editor-type-user, editor-type-name-bot, editor-type-anonymous, editor-type-group-bot, editor-type-all                                                                                                                                                 | daily, monthly |
| edited-pages/edited_pages                               | all-years, one-year, two-years, three-months, one-month | no-filter, page-type-content, page-type-non-content, page-type-all, editor-type-user, editor-type-name-bot, editor-type-anonymous, editor-type-group-bot, editor-type-all, activity-level-1-to-4-edits, activity-level-5-to-24-edits, activity-level-25-to-99-edits, activity-level-100-or-more-edits, activity-level-all | daily, monthly |
| net-bytes-difference/<br>net_bytes_difference           | all-years, one-year, two-years, three-months, one-month | no-filter, page-type-content, page-type-non-content, page-type-all, editor-type-user, editor-type-name-bot, editor-type-anonymous, editor-type-group-bot, editor-type-all                                                                                                                                                 | daily, monthly |
| pages-to-date/pages_to_date                             |                                                         |                                                                                                                                                                                                                                                                                                                           |                |
|                                                         |                                                         |                                                                                                                                                                                                                                                                                                                           |                |
|                                                         |                                                         |                                                                                                                                                                                                                                                                                                                           |                |
|                                                         |                                                         |                                                                                                                                                                                                                                                                                                                           |                |
|                                                         |                                                         |                                                                                                                                                                                                                                                                                                                           |                |
|                                                         |                                                         |                                                                                                                                                                                                                                                                                                                           |                |

   * CLI Queries.         ** Py Functions.
